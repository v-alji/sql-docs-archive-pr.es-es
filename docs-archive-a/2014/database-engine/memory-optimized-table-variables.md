---
title: Variables de tabla con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: bd102e95-53e2-4da6-9b8b-0e4f02d286d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: bec720c53c257240ee92274a6391ebc3f17faa25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673874"
---
# <a name="memory-optimized-table-variables"></a><span data-ttu-id="ef375-102">Variables de tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="ef375-102">Memory-Optimized Table Variables</span></span>
  <span data-ttu-id="ef375-103">Además de las tablas optimizadas para memoria (para el acceso eficaz a los datos) y los procedimientos almacenados compilados de forma nativa (para el procesamiento de consultas y la ejecución de lógica de negocios de forma eficaz), [!INCLUDE[hek_2](../includes/hek-2-md.md)] presenta una tercera clase de objeto: el tipo de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="ef375-103">In addition to memory-optimized tables (for efficient data access) and natively compiled stored procedures (for efficient query processing and business logic execution) [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduces a third kind of object: the memory-optimized table type.</span></span> <span data-ttu-id="ef375-104">Una variable de tabla creada mediante un tipo de tabla optimizada para memoria es una variable de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="ef375-104">A table variable created using a memory-optimized table type is a memory-optimized table variable.</span></span>  
  
 <span data-ttu-id="ef375-105">Las variables de tabla con optimización para memoria proporcionan las ventajas siguientes en comparación con las variables de tabla basadas en disco:</span><span class="sxs-lookup"><span data-stu-id="ef375-105">Memory-optimized table variables offer the following advantages when compared to disk-based table variables:</span></span>  
  
-   <span data-ttu-id="ef375-106">Las variables solo se almacenan en memoria.</span><span class="sxs-lookup"><span data-stu-id="ef375-106">The variables are only stored in memory.</span></span> <span data-ttu-id="ef375-107">El acceso a los datos es más eficaz porque el tipo de tabla optimizada para memoria usa el mismo algoritmo optimizado para memoria y las mismas estructuras de datos usadas para las tablas optimizadas para memoria, especialmente cuando se utilizan las variables en los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ef375-107">Data access is more efficient because memory-optimized table type use the same memory-optimized algorithm and data structures used for memory-optimized tables, especially when the variables are used in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="ef375-108">Con variables de tabla optimizada para memoria, no se utiliza tempdb.</span><span class="sxs-lookup"><span data-stu-id="ef375-108">With memory-optimized table variables, there is no tempdb utilization.</span></span> <span data-ttu-id="ef375-109">Las variables de tabla no se almacenan en tempdb y no se utiliza ningún recurso de tempdb.</span><span class="sxs-lookup"><span data-stu-id="ef375-109">Table variables are not stored in tempdb and do not use any resources in tempdb.</span></span>  
  
 <span data-ttu-id="ef375-110">Los escenarios habituales de uso para las variables de tabla optimizada para memoria son:</span><span class="sxs-lookup"><span data-stu-id="ef375-110">The typical usage scenarios for memory-optimized table variables are:</span></span>  
  
-   <span data-ttu-id="ef375-111">Almacenar resultados intermedios y crear conjuntos de resultados únicos basándose en varias consultas en procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ef375-111">Storing intermediate results and creating single result sets based on multiple queries in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="ef375-112">Pasar parámetros con valores de tabla en procedimientos almacenados compilados de forma nativa y procedimientos almacenados interpretados.</span><span class="sxs-lookup"><span data-stu-id="ef375-112">Passing table-valued parameters into natively compiled stored procedures and interpreted stored procedures.</span></span>  
  
-   <span data-ttu-id="ef375-113">Reemplazar las variables de tabla basadas en disco y, en algunos casos, las tablas #temp que son locales a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="ef375-113">Replacing disk-based table variables, and in some cases #temp tables that are local to a stored procedure.</span></span> <span data-ttu-id="ef375-114">Esto es especialmente útil si hay mucha contención de tempdb en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ef375-114">This is particularly useful if there is a lot of tempdb contention in the system.</span></span>  
  
-   <span data-ttu-id="ef375-115">Se pueden usar variables de tabla para simular cursores en los procedimientos almacenados compilados de forma nativa, lo que puede ayudarle a evitar limitaciones del área expuesta en procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ef375-115">Table variables can be used to simulate cursors in natively compiled stored procedures, which can help you work around surface area limitations in natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="ef375-116">Igual que las tablas optimizadas para memoria, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] genera un archivo DLL para cada tipo de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="ef375-116">Like memory-optimized tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] generates a DLL for each memory-optimized table type.</span></span> <span data-ttu-id="ef375-117">(La compilación se invoca cuando se crea el tipo de tabla optimizada para memoria y no cuando se usa para crear variables de tabla optimizada para memoria). Este archivo DLL incluye las funciones para obtener acceso a los índices y recuperar los datos de las variables de tabla.</span><span class="sxs-lookup"><span data-stu-id="ef375-117">(Compilation is invoked when the memory-optimized table type is created and not when used to create memory-optimized table variables.) This DLL includes the functions for accessing indexes and retrieving data from the table variables.</span></span> <span data-ttu-id="ef375-118">Cuando una variable de tabla optimizada para memoria se declara basándose en el tipo de tabla, se crea una instancia de las estructuras de tabla y de índice correspondientes al tipo de tabla en la sesión de usuario.</span><span class="sxs-lookup"><span data-stu-id="ef375-118">When a memory-optimized table variable is declared based on the table type, an instance of the table and index structures corresponding to the table type is created in the user session.</span></span> <span data-ttu-id="ef375-119">La variable de tabla se puede usar del mismo modo que las variables de tabla basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="ef375-119">The table variable can then be used in the same way as disk-based table variables.</span></span> <span data-ttu-id="ef375-120">Puede insertar, actualizar y eliminar filas en la variable de tabla, y puede usar las variables en las consultas de [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef375-120">You can insert, update, and delete rows in the table variable, and you can use the variables in [!INCLUDE[tsql](../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="ef375-121">También puede pasar las variables a procedimientos almacenados compilados de forma nativa e interpretados, como parámetros con valores de tabla (TVP).</span><span class="sxs-lookup"><span data-stu-id="ef375-121">You can also pass the variables into natively compiled and interpreted stored procedures, as table-valued parameters (TVP).</span></span>  
  
 <span data-ttu-id="ef375-122">En el ejemplo siguiente se muestra un tipo de tabla optimizada para memoria del ejemplo de OLTP en memoria basado en AdventureWorks ([Ejemplo de OLTP en memoria de SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span><span class="sxs-lookup"><span data-stu-id="ef375-122">The following sample shows a memory-optimized table type from the AdventureWorks-based In-Memory OLTP sample ([SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span></span>  
  
```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem
   AS TABLE
(
   OrderQty         smallint   NOT NULL,
   ProductID        int        NOT NULL,

   SpecialOfferID   int        NOT NULL
      INDEX  IX_SpecialOfferID  NONCLUSTERED,

   LocalID          int        NOT NULL,

   INDEX IX_ProductID HASH (ProductID)
      WITH ( BUCKET_COUNT = 8 )
)
WITH ( MEMORY_OPTIMIZED = ON );
```  
  
 <span data-ttu-id="ef375-123">El ejemplo muestra que la sintaxis de los tipos de tabla optimizada para memoria es similar a los tipos de tabla basados en disco, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="ef375-123">The sample shows that the syntax of memory-optimized table types is similar to disk-based table types, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="ef375-124">`MEMORY_OPTIMIZED=ON` indica que el tipo de tabla está optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="ef375-124">`MEMORY_OPTIMIZED=ON` indicates that the table type is memory-optimized.</span></span>  
  
-   <span data-ttu-id="ef375-125">El tipo debe tener al menos un índice.</span><span class="sxs-lookup"><span data-stu-id="ef375-125">The type must have at least one index.</span></span> <span data-ttu-id="ef375-126">Como con tablas optimizadas para memoria, puede usar índices de hash e índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="ef375-126">As with memory-optimized tables, you can use hash and nonclustered indexes.</span></span>  
  
     <span data-ttu-id="ef375-127">Para un índice de hash, el número de cubos debe ser aproximadamente de una a dos veces el número de claves de índice único esperadas.</span><span class="sxs-lookup"><span data-stu-id="ef375-127">For a hash index, the bucket count should be about one to two times the number of expected unique index keys.</span></span> <span data-ttu-id="ef375-128">Para obtener más información, vea [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ef375-128">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="ef375-129">Las restricciones de tipo de datos y restricciones en las tablas optimizadas para memoria se aplican también a los tipos de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="ef375-129">The data type and constraint restrictions on memory-optimized tables also apply to memory-optimized table types.</span></span> <span data-ttu-id="ef375-130">Por ejemplo, en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] se admiten las restricciones predeterminadas, pero las restricciones CHECK no.</span><span class="sxs-lookup"><span data-stu-id="ef375-130">For example, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] default constraints are supported, but check constraints are not.</span></span>  
  
 <span data-ttu-id="ef375-131">Al igual que las tablas optimizadas para memoria, las variables de tabla optimizada para memoria</span><span class="sxs-lookup"><span data-stu-id="ef375-131">Like memory-optimized tables, memory-optimized table variables,</span></span>  
  
-   <span data-ttu-id="ef375-132">No admiten planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="ef375-132">Do not support parallel plans.</span></span>  
  
-   <span data-ttu-id="ef375-133">Deben caber en memoria y no usar recursos de disco.</span><span class="sxs-lookup"><span data-stu-id="ef375-133">Must fit in memory and do not use disk resources.</span></span>  
  
 <span data-ttu-id="ef375-134">Existen variables de tabla basadas en disco en tempdb.</span><span class="sxs-lookup"><span data-stu-id="ef375-134">Disk-based table variables exist in tempdb.</span></span> <span data-ttu-id="ef375-135">Las variables de tabla con optimización para memoria existen en la base de datos de usuario (solo no usan almacenamiento y no se recuperan).</span><span class="sxs-lookup"><span data-stu-id="ef375-135">Memory-optimized table variables exist in the user database (but they do not consume storage and are not recovered).</span></span>  
  
 <span data-ttu-id="ef375-136">No puede crear una variable de tabla optimizada para memoria mediante la sintaxis en línea.</span><span class="sxs-lookup"><span data-stu-id="ef375-136">You cannot create a memory-optimized table variable using in-line syntax.</span></span> <span data-ttu-id="ef375-137">A diferencia de las variables de tabla basadas en disco, debe crear un tipo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="ef375-137">Unlike disk-based table variables, you must create a type first.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="ef375-138">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ef375-138">Table-Valued Parameters</span></span>  
 <span data-ttu-id="ef375-139">El script de ejemplo siguiente muestra la declaración de una variable de tabla como el tipo de tabla optimizada para memoria `Sales.SalesOrderDetailType_inmem`, la inserción de tres filas en la variable y el paso de la variable como un TVP a `Sales.usp_InsertSalesOrder_inmem`.</span><span class="sxs-lookup"><span data-stu-id="ef375-139">The following sample script shows the declaration of a table variable as the memory-optimized table type `Sales.SalesOrderDetailType_inmem`, the insert of three rows into the variable, and passing the variable as a TVP into `Sales.usp_InsertSalesOrder_inmem`.</span></span>  
  
```sql  
DECLARE @od Sales.SalesOrderDetailType_inmem,  
  @SalesOrderID uniqueidentifier,  
  @DueDate datetime2 = SYSDATETIME()  
  
INSERT @od (LocalID, ProductID, OrderQty, SpecialOfferID) VALUES  
  (1, 888, 2, 1),  
  (2, 450, 13, 1),  
  (3, 841, 1, 1)  
  
EXEC Sales.usp_InsertSalesOrder_inmem  
  @SalesOrderID = @SalesOrderID,  
  @DueDate = @DueDate,  
 @OnlineOrderFlag = 1,  
  @SalesOrderDetails = @od  
```  
  
 <span data-ttu-id="ef375-140">Los tipos de tabla con optimización para memoria se pueden usar como tipo de los parámetros con valores de tabla (TVP) de procedimientos almacenados y los clientes pueden hacer referencia a ellos exactamente igual que los tipos de tabla basados en disco y los TVP.</span><span class="sxs-lookup"><span data-stu-id="ef375-140">Memory-optimized table types can be used as the type for stored procedure table-valued parameters (TVPs) and can be referenced by clients exactly the same as disk-based table types and TVPs.</span></span> <span data-ttu-id="ef375-141">Por tanto, la invocación de procedimientos almacenados con los TVP optimizados para memoria y los procedimientos almacenados compilados de forma nativa funciona exactamente igual que la invocación de procedimientos almacenados interpretados con TVP basados en disco.</span><span class="sxs-lookup"><span data-stu-id="ef375-141">Therefore, the invocation of stored procedures with memory-optimized TVPs, and natively compiled stored procedures works exactly the same as the invocation of interpreted stored procedures with disk-based TVPs.</span></span>  
  
## <a name="temp-table-replacement"></a><span data-ttu-id="ef375-142">Reemplazo de la tabla #temp</span><span class="sxs-lookup"><span data-stu-id="ef375-142">#temp Table Replacement</span></span>  
 <span data-ttu-id="ef375-143">El ejemplo siguiente muestra tipos de tabla de ejemplo optimizadas para memoria y variables de tabla como una sustitución de tablas #temp locales a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="ef375-143">The following sample shows memory-optimized table types and table variables as a replacement for #temp tables that are local to a stored procedure.</span></span>  
  
```sql  
-- Using SQL procedure and temp table  
CREATE TABLE #tempTable (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
  
CREATE PROCEDURE sqlProc  
AS  
BEGIN  
  TRUNCATE TABLE #tempTable  
  
  INSERT #tempTable VALUES (1)  
  INSERT #tempTable VALUES (2)  
  INSERT #tempTable VALUES (3)  
  SELECT * FROM #tempTable  
END  
GO  
  
-- Using natively compiled stored procedure and table variable  
CREATE TYPE TT AS TABLE (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
GO  
  
CREATE PROCEDURE NCSPProc  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @tableVariable TT  
  INSERT @tableVariable VALUES (1)  
  INSERT @tableVariable VALUES (2)  
  INSERT @tableVariable VALUES (3)  
  SELECT c FROM @tableVariable  
END  
GO  
```  
  
## <a name="creating-a-single-result-set"></a><span data-ttu-id="ef375-144">Crear un único conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="ef375-144">Creating a Single Result Set</span></span>  
 <span data-ttu-id="ef375-145">El ejemplo siguiente muestra cómo almacenar los resultados intermedios y crear conjuntos de resultados únicos basados en varias consultas en procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="ef375-145">The following sample shows how to store intermediate results and create single result sets based on multiple queries in natively compiled stored procedures.</span></span> <span data-ttu-id="ef375-146">El ejemplo está calculando la unión `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span><span class="sxs-lookup"><span data-stu-id="ef375-146">The sample is computing the union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span></span>  
  
```sql  
CREATE DATABASE hk  
GO  
ALTER DATABASE hk ADD FILEGROUP hk_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE hk ADD FILE( NAME = 'hk_mod' , FILENAME = 'c:\data\hk_mod') TO FILEGROUP hk_mod;  
  
USE hk  
GO  
  
CREATE TYPE tab1 AS TABLE (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON)  
  
CREATE TABLE dbo.t1 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
CREATE TABLE dbo.t2 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
  
INSERT INTO dbo.t1 VALUES (1), (2)  
INSERT INTO dbo.t2 VALUES (3), (4)  
GO  
  
CREATE PROCEDURE dbo.p1  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS  
  BEGIN ATOMIC WITH ( TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english' )  
  
    DECLARE @t dbo.tab1  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t1;  
  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t2;  
  
    SELECT c1 FROM @t;  
  END  
GO  
  
EXEC dbo.p1  
GO  
```  
  
## <a name="memory-consumption-for-table-variables"></a><span data-ttu-id="ef375-147">Consumo de memoria para las variables de tabla</span><span class="sxs-lookup"><span data-stu-id="ef375-147">Memory Consumption for Table Variables</span></span>  
 <span data-ttu-id="ef375-148">El consumo de memoria para las variables de tabla es similar al de las tablas optimizadas para memoria, a excepción de los índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="ef375-148">Memory consumption for table variables is similar to memory-optimized tables, with the exception of nonclustered indexes.</span></span> <span data-ttu-id="ef375-149">Si se insertan muchas filas en variables de tabla optimizada para memoria con índices no clúster y si las claves de índice son grandes, estas variables de tabla utilizarán una cantidad de memoria desproporcionada.</span><span class="sxs-lookup"><span data-stu-id="ef375-149">If you insert a lot of rows into memory-optimized table variables with nonclustered indexes and if the index keys are large, these table variables will use a disproportionate amount of memory.</span></span> <span data-ttu-id="ef375-150">Los índices no clúster en variables de tabla grandes requieren proporcionalmente más memoria que un índice no clúster necesitaría para el mismo número de filas insertadas en una tabla (más memoria en las páginas de índice).</span><span class="sxs-lookup"><span data-stu-id="ef375-150">Nonclustered indexes on large table variables require proportionately more memory than a nonclustered index would require for the same number of rows inserted into a table (more memory in the index pages).</span></span>  
  
 <span data-ttu-id="ef375-151">La memoria para las variables de tabla procede del grupo de recursos de servidor del Regulador de recursos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef375-151">Memory for table variables comes from the database's Resource Governor resource pool.</span></span>  
  
 <span data-ttu-id="ef375-152">A diferencia de las tablas optimizadas para memoria, la memoria consumida (incluidas las filas eliminadas) por las variables de tabla se libera cuando la variable de tabla sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="ef375-152">Unlike memory-optimized tables, the memory consumed (including deleted rows) by table variables is freed when the table variable goes out of scope.</span></span>  
  
 <span data-ttu-id="ef375-153">La memoria se cuenta como parte del único consumidor de memoria PGPOOL de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef375-153">Memory is accounted for as part of the single PGPOOL memory consumer of the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef375-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef375-154">See Also</span></span>  
 [<span data-ttu-id="ef375-155">Compatibilidad de Transact-SQL con OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="ef375-155">Transact-SQL Support for In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/transact-sql-support-for-in-memory-oltp.md)  
  
  
