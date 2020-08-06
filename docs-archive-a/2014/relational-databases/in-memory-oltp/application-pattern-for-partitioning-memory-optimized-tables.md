---
title: Patrón de aplicación para crear particiones de tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 3f867763-a8e6-413a-b015-20e9672cc4d1
author: rothja
ms.author: jroth
ms.openlocfilehash: d2633cdf1b631a1d9209adf26f4773e27c4c44c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663474"
---
# <a name="application-pattern-for-partitioning-memory-optimized-tables"></a><span data-ttu-id="18fb3-102">Patrón de aplicación para crear particiones de tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="18fb3-102">Application Pattern for Partitioning Memory-Optimized Tables</span></span>
  [!INCLUDE[hek_2](../../includes/hek-2-md.md)] <span data-ttu-id="18fb3-103">admite un patrón en el que una cantidad limitada de datos activos se conserva en una tabla optimizada para memoria, mientras que los datos a los que se tiene acceso con menor frecuencia se procesan en disco.</span><span class="sxs-lookup"><span data-stu-id="18fb3-103">supports a pattern where a limited amount of active data is kept in a memory-optimized table, while less-frequently accessed data is processed on disk.</span></span> <span data-ttu-id="18fb3-104">Por lo general, esto sería un escenario donde se almacenan datos en función de una clave `datetime`.</span><span class="sxs-lookup"><span data-stu-id="18fb3-104">Typically, this would be a scenario where data is stored based on a `datetime` key.</span></span>  
  
 <span data-ttu-id="18fb3-105">Se pueden emular las tablas con particiones con tablas optimizadas para memoria manteniendo una tabla con particiones y una tabla optimizada para memoria con un esquema común.</span><span class="sxs-lookup"><span data-stu-id="18fb3-105">You can emulate partitioned tables with memory-optimized tables by maintaining a partitioned table and a memory-optimized table with a common schema.</span></span> <span data-ttu-id="18fb3-106">Los datos actuales se insertarían y actualizarían en la tabla optimizada para memoria, mientras que los datos a los que se tiene acceso con menor frecuencia se conservarían en la tabla con particiones tradicional.</span><span class="sxs-lookup"><span data-stu-id="18fb3-106">Current data would be inserted and updated in the memory-optimized table, while less-frequently accessed data would be maintained in the traditional partitioned table.</span></span>  
  
 <span data-ttu-id="18fb3-107">Una aplicación que sabe que los datos activos están en una tabla optimizada para memoria puede utilizar procedimientos almacenados compilados de forma nativa para tener acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="18fb3-107">An application that knows that the active data is in a memory-optimized table can use natively compiled stored procedures to access the data.</span></span> <span data-ttu-id="18fb3-108">En las operaciones que necesitan tener acceso a todos los datos o que pueden no saber qué tabla contiene los datos importantes, se usa [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretado para combinar la tabla optimizada para memoria con la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="18fb3-108">Operations that need to access the entire span of data, or which may not know which table holds relevant data, use interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] to join the memory-optimized table with the partitioned table.</span></span>  
  
 <span data-ttu-id="18fb3-109">Este intercambio de particiones se describe de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="18fb3-109">This partition switch is described as follows:</span></span>  
  
-   <span data-ttu-id="18fb3-110">Inserte los datos de la tabla de OLTP en memoria en una tabla de ensayo, posiblemente usando una fecha límite.</span><span class="sxs-lookup"><span data-stu-id="18fb3-110">Insert data from the In-Memory OLTP table into a staging table, possibly using a cutoff date.</span></span>  
  
-   <span data-ttu-id="18fb3-111">Elimine los mismos datos de la tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="18fb3-111">Delete the same data from the memory-optimized table.</span></span>  
  
-   <span data-ttu-id="18fb3-112">Cambie a la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="18fb3-112">Swap in the staging table.</span></span>  
  
-   <span data-ttu-id="18fb3-113">Agregue la partición activa.</span><span class="sxs-lookup"><span data-stu-id="18fb3-113">Add the active partition.</span></span>  
  
 <span data-ttu-id="18fb3-114">![Conmutación de particiones](../../database-engine/media/hekaton-partitioned-tables.gif "Conmutación de particiones")</span><span class="sxs-lookup"><span data-stu-id="18fb3-114">![Partition switch.](../../database-engine/media/hekaton-partitioned-tables.gif "Partition switch.")</span></span>  
<span data-ttu-id="18fb3-115">Mantenimiento de datos activo</span><span class="sxs-lookup"><span data-stu-id="18fb3-115">Active Data Maintenance</span></span>  
  
 <span data-ttu-id="18fb3-116">Después de eliminar ActiveOrders, las acciones tienen que realizarse durante una ventana de mantenimiento para evitar que las consultan pierdan datos durante el tiempo que transcurre entre la eliminación de los datos y el cambio a la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="18fb3-116">The actions starting with Deleting ActiveOrders need to be done during a maintenance window to avoid queries missing data during the time between deleting data and switching in the staging table.</span></span>  
  
 <span data-ttu-id="18fb3-117">Para obtener un ejemplo relacionado, vea [Creación de particiones en el nivel de aplicación](application-level-partitioning.md).</span><span class="sxs-lookup"><span data-stu-id="18fb3-117">For a related sample, see [Application-Level Partitioning](application-level-partitioning.md).</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="18fb3-118">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="18fb3-118">Code Sample</span></span>  
 <span data-ttu-id="18fb3-119">En el ejemplo siguiente se muestra cómo usar una tabla optimizada para memoria con una tabla basada en disco con particiones.</span><span class="sxs-lookup"><span data-stu-id="18fb3-119">The following sample shows how to use a memory-optimized table with a partitioned disk-based table.</span></span> <span data-ttu-id="18fb3-120">Los datos usados con frecuencia se almacenan en memoria.</span><span class="sxs-lookup"><span data-stu-id="18fb3-120">Frequently-used data is stored in memory.</span></span> <span data-ttu-id="18fb3-121">Para guardar los datos en el disco, cree una nueva partición y cópielos en la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="18fb3-121">To save the data to disk, create a new partition and copy the data to the partitioned table.</span></span>  
  
 <span data-ttu-id="18fb3-122">En la primera parte de este ejemplo se crean la base de datos y los objetos necesarios.</span><span class="sxs-lookup"><span data-stu-id="18fb3-122">The first part of this sample creates the database and necessary objects.</span></span> <span data-ttu-id="18fb3-123">En la segunda parte del ejemplo se muestra cómo mover datos de una tabla optimizada para memoria a una tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="18fb3-123">The second part of the sample shows how to move data from a memory-optimized table into a partitioned table.</span></span>  
  
```sql  
CREATE DATABASE partitionsample;  
GO  
  
-- enable for In-Memory OLTP - change file path as needed  
ALTER DATABASE partitionsample ADD FILEGROUP partitionsample_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE partitionsample ADD FILE( NAME = 'partitionsample_mod' , FILENAME = 'c:\data\partitionsample_mod') TO FILEGROUP partitionsample_mod;  
GO  
  
USE partitionsample;  
GO  
  
-- frequently used portion of the SalesOrders - memory-optimized  
  
CREATE TABLE dbo.SalesOrders_hot (  
   so_id INT IDENTITY PRIMARY KEY NONCLUSTERED,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL INDEX ix_date NONCLUSTERED,  
   so_total MONEY NOT NULL,  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- cold portion of the SalesOrders - partitioned disk-based table  
CREATE PARTITION FUNCTION [ByDatePF](datetime2) AS RANGE RIGHT   
   FOR VALUES();  
GO  
  
CREATE PARTITION SCHEME [ByDateRange]   
   AS PARTITION [ByDatePF]   
   ALL TO ([PRIMARY]);  
GO  
  
CREATE TABLE dbo.SalesOrders_cold (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) ON [ByDateRange](so_date)  
GO  
  
-- table for temporary partitions  
CREATE TABLE dbo.SalesOrders_cold_staging (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date datetime2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold_staging PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc),  
   CONSTRAINT CHK_SalesOrders_cold_staging CHECK (so_date >= '1900-01-01')  
)  
GO  
  
-- aggregate view of the hot and cold data  
CREATE VIEW dbo.SalesOrders  
AS SELECT so_id,  
   cust_id,  
   so_date,  
   so_total,  
   1 AS 'is_hot'  
   FROM dbo.SalesOrders_hot  
   UNION ALL  
   SELECT so_id,  
          cust_id,  
          so_date,  
          so_total,  
          0 AS 'is_hot'  
          FROM dbo.SalesOrders_cold;  
GO  
  
-- move all sales orders up to the split date to cold storage  
CREATE PROCEDURE dbo.usp_SalesOrdersOffloadToCold @splitdate datetime2  
   AS  
   BEGIN  
      BEGIN TRANSACTION;  
      -- create new heap based on the hot data to be moved to cold storage  
      INSERT INTO dbo.SalesOrders_cold_staging WITH( TABLOCKX)  
      SELECT so_id , cust_id , so_date , so_total  
         FROM dbo.SalesOrders_hot WITH ( serializable)  
         WHERE so_date <= @splitdate;  
  
      -- remove moved data  
      DELETE FROM dbo.SalesOrders_hot WITH( SERIALIZABLE)  
         WHERE so_date <= @splitdate;  
  
      -- update partition function, and switch in new partition  
      ALTER PARTITION SCHEME [ByDateRange] NEXT USED [PRIMARY];  
  
      DECLARE @p INT = ( SELECT MAX( partition_number) FROM sys.partitions WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold'));  
      EXEC sp_executesql N'alter table dbo.SalesOrders_cold_staging  
         SWITCH TO dbo.SalesOrders_cold partition @i' , N'@i int' , @i = @p;  
  
      ALTER PARTITION FUNCTION [ByDatePF]()  
      SPLIT RANGE( @splitdate);  
  
      -- modify constraint on staging table to align with new partition  
      ALTER TABLE dbo.SalesOrders_cold_staging DROP CONSTRAINT CHK_SalesOrders_cold_staging;  
  
      DECLARE @s nvarchar( 100) = CONVERT( nvarchar( 100) , @splitdate , 121);  
      DECLARE @sql nvarchar( 1000) = N'alter table dbo.SalesOrders_cold_staging   
         add constraint CHK_SalesOrders_cold_staging check (so_date > ''' + @s + ''')';  
      PRINT @sql;  
      EXEC sp_executesql @sql;  
  
      COMMIT;  
END;  
GO  
  
-- insert sample values in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(1,SYSDATETIME(), 1);   
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the table  
SELECT *  FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE  @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , * FROM sys.dm_db_partition_stats ps  
   WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold');  
  
-- insert more rows in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , partition_number , row_count  FROM sys.dm_db_partition_stats ps  
  WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold') AND index_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="18fb3-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18fb3-124">See Also</span></span>  
 [<span data-ttu-id="18fb3-125">Tablas optimizadas para la memoria</span><span class="sxs-lookup"><span data-stu-id="18fb3-125">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
