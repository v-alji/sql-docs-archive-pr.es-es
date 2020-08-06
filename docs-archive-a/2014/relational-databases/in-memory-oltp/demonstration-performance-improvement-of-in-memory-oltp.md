---
title: 'Demostración: mejora de rendimiento de OLTP en memoria | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c6def45d-d2d4-4d24-8068-fab4cd94d8cc
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4858e4c35263ab3dd1d9fdcf55a2b136dd8eeaf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672975"
---
# <a name="demonstration-performance-improvement-of-in-memory-oltp"></a><span data-ttu-id="cd3b5-102">Demostración: Mejora de rendimiento de OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="cd3b5-102">Demonstration: Performance Improvement of In-Memory OLTP</span></span>
  <span data-ttu-id="cd3b5-103">En este ejemplo se muestran las mejoras de rendimiento al usar OLTP en memoria al hacer una comparación de las diferencias en la respuesta el tiempo de espera cuando se ejecuta una consulta de Transact-SQL idéntica en tablas optimizadas en memoria y basadas en disco tradicionales.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-103">This example shows performance improvements when using In-Memory OLTP by comparing differences in response times when running an identical Transact-SQL query against memory-optimized and traditional disk-based tables.</span></span> <span data-ttu-id="cd3b5-104">Además, también se crea un procedimiento almacenado compilado de forma nativa (basado en la misma consulta) y luego se ejecuta para demostrar que se suelen obtener los mejores tiempos de respuesta al consultar una tabla optimizada en memoria con un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-104">Additionally, a natively-compiled stored procedure is also created (based on the same query) and then run to demonstrate that you typically get the best response times when querying a memory-optimized table with a natively-compiled stored procedure.</span></span> <span data-ttu-id="cd3b5-105">En este ejemplo solo se muestra un aspecto de las mejoras de rendimiento al acceder a los datos en tablas optimizadas en memoria; la eficacia del acceso a datos al realizar inserciones.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-105">This sample only shows one aspect of performance improvements when accessing data in memory-optimized tables; data access efficiency when performing inserts.</span></span> <span data-ttu-id="cd3b5-106">Este ejemplo es de un solo subproceso y no aprovecha las ventajas de simultaneidad de OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-106">This sample is single-threaded and does not take advantage of the concurrency benefits of In-Memory OLTP.</span></span> <span data-ttu-id="cd3b5-107">Una carga de trabajo que utiliza simultaneidad verá mayor mejora de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-107">A workload that uses concurrency will see a greater performance gain.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd3b5-108">Está disponible otro ejemplo que muestra las tablas optimizadas para memoria en [Ejemplo de OLTP en memoria de SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="cd3b5-108">Another sample demonstrating memory-optimized tables is available at [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="cd3b5-109">Para completar este ejemplo, realizará las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd3b5-109">To complete this sample you will perform the following:</span></span>  
  
1.  <span data-ttu-id="cd3b5-110">Crear una base de datos denominada **imoltp** y modificar sus detalles de archivo con el fin de configurarla para usar OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-110">Create a database named **imoltp** and alter its file details to set it up for using In-Memory OLTP.</span></span>  
  
2.  <span data-ttu-id="cd3b5-111">Crear los objetos de base de datos para nuestro ejemplo: tres tablas y un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-111">Create the database objects for our sample: three tables and a natively-compiled stored procedure.</span></span>  
  
3.  <span data-ttu-id="cd3b5-112">Ejecutar las distintas consultas y mostrar los tiempos de respuesta para cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-112">Run the different queries and display the response times for each query.</span></span>  
  
 <span data-ttu-id="cd3b5-113">Para configurar la base de datos **imoltp** en nuestro ejemplo, primero cree una carpeta vacía: **c:\imoltp_data**y luego ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="cd3b5-113">To setup the **imoltp** database for our example, first create an empty folder: **c:\imoltp_data**, and then run the following code:</span></span>  
  
```sql  
USE master  
GO  
  
-- Create a new database.  
CREATE DATABASE imoltp  
GO  
  
-- Prepare the database for In-Memory OLTP by  
-- adding a memory-optimized filegroup to the database.  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_file_group  
    CONTAINS MEMORY_OPTIMIZED_DATA;  
  
-- Add a file (to hold the memory-optimized data) to the new filegroup.  
ALTER DATABASE imoltp ADD FILE (name='imoltp_file', filename='c:\imoltp_data\imoltp_file')  
    TO FILEGROUP imoltp_file_group;  
GO  
  
```  
  
 <span data-ttu-id="cd3b5-114">A continuación, ejecute el siguiente código para crear la tabla basada en disco, dos (2) tablas optimizadas en memoria y el procedimiento almacenado compilado de forma nativa que se usará para mostrar los distintos métodos de acceso a datos:</span><span class="sxs-lookup"><span data-stu-id="cd3b5-114">Next, run the following code to create the disk-based table, two (2) memory-optimized tables, and the natively-compiled stored procedure that will be used to demonstrate the different data access methods:</span></span>  
  
```sql  
USE imoltp  
GO  
  
-- If the tables or stored procedure already exist, drop them to start clean.  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'DiskBasedTable')  
   DROP TABLE [dbo].[DiskBasedTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'InMemTable')  
   DROP TABLE [dbo].[InMemTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'InMemTable2')  
   DROP TABLE [dbo].[InMemTable2]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'usp_InsertData')  
   DROP PROCEDURE [dbo].[usp_InsertData]  
GO  
  
-- Create a traditional disk-based table.  
CREATE TABLE [dbo].[DiskBasedTable] (  
  c1 INT NOT NULL PRIMARY KEY,  
  c2 NCHAR(48) NOT NULL  
)  
GO  
  
-- Create a memory-optimized table.  
CREATE TABLE [dbo].[InMemTable] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a 2nd memory-optimized table.  
CREATE TABLE [dbo].[InMemTable2] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a natively-compiled stored procedure.  
CREATE PROCEDURE [dbo].[usp_InsertData]   
  @rowcount INT,  
  @c NCHAR(48)  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS   
  BEGIN ATOMIC   
  WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @i INT = 1;  
  WHILE @i <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[inMemTable2](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
END  
GO  
  
```  
  
 <span data-ttu-id="cd3b5-115">La instalación se completa y estamos preparados para ejecutar las consultas que mostrarán los tiempos de respuesta al hacer una comparación del rendimiento entre los métodos de acceso de datos.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-115">The setup is complete and we are ready to execute the queries that will display the response times comparing the performance between the data access methods.</span></span>  
  
 <span data-ttu-id="cd3b5-116">Para completar el ejemplo, ejecute el siguiente código varias veces.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-116">To complete the example run the following code multiple times.</span></span> <span data-ttu-id="cd3b5-117">Omita los resultados de la primera ejecución que se ve afectado negativamente por la asignación de memoria inicial.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-117">Ignore the results from the first run which is negatively affected by initial memory allocation.</span></span>  
  
```sql  
SET STATISTICS TIME OFF;  
SET NOCOUNT ON;  
  
-- Delete data from all tables to reset the example.  
DELETE FROM [dbo].[DiskBasedTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[inMemTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[InMemTable2]   
    WHERE [c1]>0  
GO  
  
-- Declare parameters for the test queries.  
DECLARE @i INT = 1;  
DECLARE @rowcount INT = 100000;  
DECLARE @c NCHAR(48) = N'12345678901234567890123456789012345678';  
DECLARE @timems INT;  
DECLARE @starttime datetime2 = sysdatetime();  
  
-- Disk-based table queried with interpreted Transact-SQL.  
BEGIN TRAN  
  WHILE @I <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[DiskBasedTable](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (disk-based table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with interpreted Transact-SQL.  
SET @i = 1;  
SET @starttime = sysdatetime();  
  
BEGIN TRAN  
  WHILE @i <= @rowcount  
    BEGIN  
      INSERT INTO [dbo].[InMemTable](c1,c2) VALUES (@i, @c);  
      SET @i += 1;  
    END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with a natively-compiled stored procedure.  
SET @starttime = sysdatetime();  
  
EXEC usp_InsertData @rowcount, @c;  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with natively-compiled stored procedure).';  
  
```  
  
 <span data-ttu-id="cd3b5-118">Los resultados esperados proporcionan tiempos de respuesta reales que muestran cómo el uso de tablas optimizadas en memoria y procedimientos almacenados compilados de forma nativa suele proporcionar tiempos de respuesta sistemáticamente más rápidos que las mismas cargas de trabajo que se ejecutan en tablas basadas en disco tradicionales.</span><span class="sxs-lookup"><span data-stu-id="cd3b5-118">The expected results provide actual response times showing how using memory-optimized tables and natively-compiled stored procedures typically provides consistently faster response times than the same workloads running against traditional disk-based tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd3b5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd3b5-119">See Also</span></span>  
 <span data-ttu-id="cd3b5-120">[Extensiones de AdventureWorks para mostrar OLTP en memoria](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-120">[Extensions to AdventureWorks to Demonstrate In-Memory OLTP](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="cd3b5-121">[OLTP en memoria &#40;optimización en memoria&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-121">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="cd3b5-122">[Tablas con optimización para memoria](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-122">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="cd3b5-123">[Procedimientos almacenados compilados de forma nativa](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-123">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="cd3b5-124">[Requisitos para utilizar las tablas con optimización para memoria](requirements-for-using-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-124">[Requirements for Using Memory-Optimized Tables](requirements-for-using-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="cd3b5-125">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="cd3b5-126">[Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="cd3b5-126">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 [<span data-ttu-id="cd3b5-127">CREAR procedimientos y tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="cd3b5-127">CREATE PROCEDURE and Memory-Optimized Tables</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
