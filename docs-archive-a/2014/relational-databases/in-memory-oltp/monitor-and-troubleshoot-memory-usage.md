---
title: Supervisión y solución de problemas de uso de memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 7a458b9c-3423-4e24-823d-99573544c877
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5805ed06ad78040dbdf6c8557e5f548ad57f618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750977"
---
# <a name="monitor-and-troubleshoot-memory-usage"></a><span data-ttu-id="349b1-102">Supervisar y solucionar problemas de uso de memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-102">Monitor and Troubleshoot Memory Usage</span></span>
  [!INCLUDE[hek_1](../../includes/hek-1-md.md)] <span data-ttu-id="349b1-103">consume memoria en patrones distintos que las tablas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="349b1-103">consumes memory in different patterns than disk-based tables.</span></span> <span data-ttu-id="349b1-104">Puede supervisar la cantidad de memoria asignada y usada por las tablas e índices optimizados para memoria en la base de datos mediante las DMV o los contadores de rendimiento suministrados para la memoria y el subsistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="349b1-104">You can monitor the amount of memory allocated and used by memory-optimized tables and indexes in your database using the DMVs or performance counters provided for memory and the garbage collection subsystem.</span></span>  <span data-ttu-id="349b1-105">Esto le ofrece visibilidad en los niveles de sistema y de base de datos, y permite evitar problemas debidos al agotamiento de la memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-105">This gives you visibility at both the system and database level and lets you prevent problems due to memory exhaustion.</span></span>

 <span data-ttu-id="349b1-106">En este tema se trata la supervisión del uso de memoria de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="349b1-106">This topic covers monitoring your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] memory usage.</span></span>


##  <a name="create-a-sample-database-with-memory-optimized-tables"></a><a name="bkmk_CreateDB"></a> <span data-ttu-id="349b1-107">Crear una base de datos de ejemplo con tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-107">Create a sample database with memory-optimized tables</span></span>
 <span data-ttu-id="349b1-108">Puede omitir esta sección si ya tiene una base de datos con tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-108">You can skip this section if you already have a database with memory-optimized tables.</span></span>

 <span data-ttu-id="349b1-109">En los pasos siguientes se crea una base de datos con tres tablas optimizadas para memoria que puede usar en el resto de este tema.</span><span class="sxs-lookup"><span data-stu-id="349b1-109">The following steps create a database with three memory-optimized tables that you can use in the remainder of this topic.</span></span> <span data-ttu-id="349b1-110">En el ejemplo, asignamos la base de datos a un grupo de recursos de servidor de modo que pueda controlar cuánta memoria pueden utilizar las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-110">In the example, we mapped the database to a resource pool so that we can control how much memory can be taken by memory-optimized tables.</span></span>

1.  <span data-ttu-id="349b1-111">Inicie [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="349b1-111">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>

2.  <span data-ttu-id="349b1-112">Haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="349b1-112">Click **New Query**.</span></span>

3.  <span data-ttu-id="349b1-113">Pegue este código en la nueva ventana de consulta y ejecute todas las secciones.</span><span class="sxs-lookup"><span data-stu-id="349b1-113">Paste this code into the new query window and execute each section.</span></span>

    ```
    -- create a database to be used
    CREATE DATABASE IMOLTP_DB
    GO

    ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_xtp_fg CONTAINS MEMORY_OPTIMIZED_DATA
    ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_xtp' , FILENAME = 'C:\Data\IMOLTP_DB_xtp') TO FILEGROUP IMOLTP_DB_xtp_fg;
    GO

    USE IMOLTP_DB
    GO

    -- create the resoure pool
    CREATE RESOURCE POOL PoolIMOLTP WITH (MAX_MEMORY_PERCENT = 60);
    ALTER RESOURCE GOVERNOR RECONFIGURE;
    GO

    -- bind the database to a resource pool
    EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'PoolIMOLTP'

    -- you can query the binding using the catalog view as described here
    SELECT d.database_id
         , d.name
         , d.resource_pool_id
    FROM sys.databases d
    GO

    -- take database offline/online to finalize the binding to the resource pool
    USE master
    GO

    ALTER DATABASE IMOLTP_DB SET OFFLINE
    GO
    ALTER DATABASE IMOLTP_DB SET ONLINE
    GO

    -- create some tables
    USE IMOLTP_DB
    GO

    -- create table t1
    CREATE TABLE dbo.t1 (
           c1 int NOT NULL CONSTRAINT [pk_t1_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- load t1 150K rows
    DECLARE @i int = 0
    BEGIN TRAN
    WHILE (@i <= 150000)
       BEGIN
          INSERT t1 VALUES (@i, 'a', replicate ('b', 8000))
          SET @i += 1;
       END
    Commit
    GO

    -- Create another table, t2
    CREATE TABLE dbo.t2 (
           c1 int NOT NULL CONSTRAINT [pk_t2_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- Create another table, t3 
    CREATE TABLE dbo.t3 (
           c1 int NOT NULL CONSTRAINT [pk_t3_c1] PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 1000000)
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO
    ```

##  <a name="monitoring-memory-usage"></a><span data-ttu-id="349b1-114">Supervisar el uso de la memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-114">Monitoring Memory Usage</span></span>

###  <a name="using-ssmanstudiofull"></a><span data-ttu-id="349b1-115">Usar [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="349b1-115">Using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>
 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="349b1-116">se envía con informes estándar integrados para supervisar la memoria que han usado las tablas en memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-116">ships with built-in standard reports to monitor the memory consumed by in-memory tables.</span></span> <span data-ttu-id="349b1-117">Puede acceder a estos informes mediante el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="349b1-117">You can access these reports using Object Explorer.</span></span> <span data-ttu-id="349b1-118">También puede utilizar el explorador de objetos para supervisar la memoria utilizada por las tablas optimizadas para memoria individuales.</span><span class="sxs-lookup"><span data-stu-id="349b1-118">You can also use the object explorer to monitor memory consumed by individual memory-optimized tables.</span></span>

#### <a name="consumption-at-the-database-level"></a><span data-ttu-id="349b1-119">Consumo en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="349b1-119">Consumption at the database level</span></span>
 <span data-ttu-id="349b1-120">Puede supervisar el uso de memoria en el nivel de base de datos como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="349b1-120">You can monitor memory use at the database level as follows.</span></span>

1.  <span data-ttu-id="349b1-121">Inicie [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] y conéctese a un servidor.</span><span class="sxs-lookup"><span data-stu-id="349b1-121">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and connect to a server.</span></span>

2.  <span data-ttu-id="349b1-122">En el Explorador de objetos, haga clic con el botón secundario en la base de datos en la que desee los informes.</span><span class="sxs-lookup"><span data-stu-id="349b1-122">In Object Explorer, right-click the database you want reports on.</span></span>

3.  <span data-ttu-id="349b1-123">En el menú contextual, seleccione **Informes** -> **Standard Informes** -> **Uso de memoria por los objetos con optimización para memoria**.</span><span class="sxs-lookup"><span data-stu-id="349b1-123">In the context menu select, **Reports** -> **Standard Reports** -> **Memory Usage By Memory Optimized Objects**</span></span>

 <span data-ttu-id="349b1-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="349b1-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span></span>

 <span data-ttu-id="349b1-125">Este informe muestra el uso de memoria de la base de datos que hemos creado antes.</span><span class="sxs-lookup"><span data-stu-id="349b1-125">This report shows memory consumption by the database we created above.</span></span>

 <span data-ttu-id="349b1-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="349b1-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span></span>

###  <a name="using-dmvs"></a><span data-ttu-id="349b1-127">Usar DMVs</span><span class="sxs-lookup"><span data-stu-id="349b1-127">Using DMVs</span></span>
 <span data-ttu-id="349b1-128">Hay varias DMV disponibles para supervisar la memoria utilizada por las tablas optimizadas para memoria, los índices, los objetos del sistema y las estructuras de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="349b1-128">There are a number of DMVs available to monitor memory consumed by memory-optimized tables, indexes, system objects, and by run-time structures.</span></span>

#### <a name="memory-consumption-by-memory-optimized-tables-and-indexes"></a><span data-ttu-id="349b1-129">Uso de memoria de las tablas e índices optimizados para memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-129">Memory consumption by memory-optimized tables and indexes</span></span>
 <span data-ttu-id="349b1-130">Puede encontrar el uso de memoria de todas las tablas de usuario, los índices y los objetos del sistema consultando `sys.dm_db_xtp_table_memory_stats` como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="349b1-130">You can find memory consumption for all user tables, indexes, and system objects by querying `sys.dm_db_xtp_table_memory_stats` as shown here.</span></span>

```sql
SELECT object_name(object_id) AS Name
     , *
   FROM sys.dm_db_xtp_table_memory_stats
```

 <span data-ttu-id="349b1-131">**Salida de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="349b1-131">**Sample Output**</span></span>

```
Name       object_id   memory_allocated_for_table_kb memory_used_by_table_kb memory_allocated_for_indexes_kb memory_used_by_indexes_kb
---------- ----------- ----------------------------- ----------------------- ------------------------------- -------------------------
t3         629577281   0                             0                       128                             0
t1         565577053   1372928                       1200008                 7872                            1942
t2         597577167   0                             0                       128                             0
NULL       -6          0                             0                       2                               2
NULL       -5          0                             0                       24                              24
NULL       -4          0                             0                       2                               2
NULL       -3          0                             0                       2                               2
NULL       -2          192                           25                      16                              16
```

 <span data-ttu-id="349b1-132">Para obtener más información, vea [Sys. dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span><span class="sxs-lookup"><span data-stu-id="349b1-132">For more information, see [sys.dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span></span>

#### <a name="memory-consumption-by-internal-system-structures"></a><span data-ttu-id="349b1-133">Uso de memoria de las estructuras de sistema internas</span><span class="sxs-lookup"><span data-stu-id="349b1-133">Memory consumption by internal system structures</span></span>
 <span data-ttu-id="349b1-134">Los objetos del sistema también usan memoria, por ejemplo, las estructuras transaccionales, los búferes de archivos delta y de datos, las estructuras de recolección de elementos no utilizados, etcétera.</span><span class="sxs-lookup"><span data-stu-id="349b1-134">Memory is also consumed by system objects, such as, transactional structures, buffers for data and delta files, garbage collection structures, and more.</span></span> <span data-ttu-id="349b1-135">Puede encontrar la memoria usada para estos objetos del sistema consultando `sys.dm_xtp_system_memory_consumers` como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="349b1-135">You can find the memory used for these system objects by querying `sys.dm_xtp_system_memory_consumers` as shown here.</span></span>

```sql
SELECT memory_consumer_desc
     , allocated_bytes/1024 AS allocated_bytes_kb
     , used_bytes/1024 AS used_bytes_kb
     , allocation_count
   FROM sys.dm_xtp_system_memory_consumers
```

 <span data-ttu-id="349b1-136">**Salida de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="349b1-136">**Sample Output**</span></span>

```
memory_consumer_ desc allocated_bytes_kb   used_bytes_kb        allocation_count
------------------------- -------------------- -------------------- ----------------
VARHEAP                   0                    0                    0
VARHEAP                   384                  0                    0
DBG_GC_OUTSTANDING_T      64                   64                   910
ACTIVE_TX_MAP_LOOKAS      0                    0                    0
RECOVERY_TABLE_CACHE      0                    0                    0
RECENTLY_USED_ROWS_L      192                  192                  261
RANGE_CURSOR_LOOKSID      0                    0                    0
HASH_CURSOR_LOOKASID      128                  128                  455
SAVEPOINT_LOOKASIDE       0                    0                    0
PARTIAL_INSERT_SET_L      192                  192                  351
CONSTRAINT_SET_LOOKA      192                  192                  646
SAVEPOINT_SET_LOOKAS      0                    0                    0
WRITE_SET_LOOKASIDE       192                  192                  183
SCAN_SET_LOOKASIDE        64                   64                   31
READ_SET_LOOKASIDE        0                    0                    0
TRANSACTION_LOOKASID      448                  448                  156
PGPOOL:256K               768                  768                  3
PGPOOL: 64K               0                    0                    0
PGPOOL:  4K               0                    0                    0
```

 <span data-ttu-id="349b1-137">Para obtener más información, vea [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="349b1-137">For more information see [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span></span>


#### <a name="memory-consumption-at-run-time-when-accessing-memory-optimized-tables"></a><span data-ttu-id="349b1-138">Uso de memoria en tiempo de ejecución al obtener acceso a las tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-138">Memory consumption at run-time when accessing memory-optimized tables</span></span>
 <span data-ttu-id="349b1-139">Puede determinar la memoria utilizada por las estructuras de tiempo de ejecución, como la memoria caché de procedimientos con la consulta siguiente: ejecute esta consulta para obtener la memoria utilizada por las estructuras de tiempo de ejecución como para la caché de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="349b1-139">You can determine the memory consumed by run time structures, such as the procedure cache with the following query: run this query to get the memory used by run-time structures such as for the procedure cache.</span></span> <span data-ttu-id="349b1-140">Todas las estructuras de tiempo de ejecución se etiquetan con XTP.</span><span class="sxs-lookup"><span data-stu-id="349b1-140">All run-time structures are tagged with XTP.</span></span>

```sql
SELECT memory_object_address
     , pages_in_bytes
     , bytes_used
     , type
   FROM sys.dm_os_memory_objects WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="349b1-141">**Salida de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="349b1-141">**Sample Output**</span></span>

```
memory_object_address pages_ in_bytes bytes_used type
--------------------- ------------------- ---------- ----
0x00000001F1EA8040    507904              NULL       MEMOBJ_XTPDB
0x00000001F1EAA040    68337664            NULL       MEMOBJ_XTPDB
0x00000001FD67A040    16384               NULL       MEMOBJ_XTPPROCCACHE
0x00000001FD68C040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD284040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD302040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD382040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD402040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD482040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD502040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD67E040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001F813C040    8192                NULL       MEMOBJ_XTPBLOCKALLOC
0x00000001F813E040    16842752            NULL       MEMOBJ_XTPBLOCKALLOC
```

 <span data-ttu-id="349b1-142">Para obtener más información, vea [Sys. dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="349b1-142">For more information, see [sys.dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span></span>

#### <a name="memory-consumed-by-hek_2-engine-across-the-instance"></a><span data-ttu-id="349b1-143">Memoria usada por el motor de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] en la instancia</span><span class="sxs-lookup"><span data-stu-id="349b1-143">Memory consumed by [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine across the instance</span></span>
 <span data-ttu-id="349b1-144">La memoria asignada al motor de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] y a los objetos optimizados para memoria se administra de la misma forma que cualquier otro consumidor de memoria dentro de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="349b1-144">Memory allocated to the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine and the memory-optimized objects is managed the same way as any other memory consumer within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="349b1-145">Los distribuidores de tipo MEMORYCLERK_XTP tienen en cuenta toda la memoria asignada al motor de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="349b1-145">The clerks of type MEMORYCLERK_XTP accounts for all the memory allocated to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span> <span data-ttu-id="349b1-146">Use la consulta siguiente para encontrar toda la memoria usada por el motor de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="349b1-146">Use the following query to find all the memory used by the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span>

```sql
-- this DMV accounts for all memory used by the hek_2 engine
SELECT type
     , name
     , memory_node_id
     , pages_kb/1024 AS pages_MB 
   FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="349b1-147">En la salida de ejemplo se muestra que la memoria total asignada es un consumo de memoria del sistema de 18 MB y 1358 MB asignados al identificador de base de datos 5.</span><span class="sxs-lookup"><span data-stu-id="349b1-147">The sample output shows that the total memory allocated is 18 MB system-level memory consumption and 1358MB allocated to database id of 5.</span></span> <span data-ttu-id="349b1-148">Puesto que esta base de datos está asignada a un grupo de recursos de servidor dedicado, esta memoria cuenta para ese grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="349b1-148">Since this database is mapped to a dedicated resource pool, this memory is accounted for in that resource pool.</span></span>

 <span data-ttu-id="349b1-149">**Salida de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="349b1-149">**Sample Output**</span></span>

```
type                 name       memory_node_id pages_MB
-------------------- ---------- -------------- --------------------
MEMORYCLERK_XTP      Default    0              18
MEMORYCLERK_XTP      DB_ID_5    0              1358
MEMORYCLERK_XTP      Default    64             0
```

 <span data-ttu-id="349b1-150">Para obtener más información, vea [Sys. dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="349b1-150">For more information, see [sys.dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span></span>

##   <a name="managing-memory-consumed-by-memory-optimized-objects"></a><span data-ttu-id="349b1-151">Administrar la memoria utilizada por los objetos optimizados para memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-151">Managing memory consumed by memory-optimized objects</span></span>
 <span data-ttu-id="349b1-152">Puede controlar la memoria total que han usado las tablas optimizadas para memoria enlazándola a un grupo de recursos con nombre como se describe en el tema [Enlazar una base de datos con tablas optimizadas para memoria a un grupo de recursos de servidor](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="349b1-152">You can control the total memory consumed by memory-optimized tables by binding it to a named resource pool as described in the topic [Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span></span>

##  <a name="troubleshooting-memory-issues"></a><span data-ttu-id="349b1-153">Solucionar problemas de memoria</span><span class="sxs-lookup"><span data-stu-id="349b1-153">Troubleshooting Memory Issues</span></span>
 <span data-ttu-id="349b1-154">La solución de problemas de memoria es un proceso de tres pasos:</span><span class="sxs-lookup"><span data-stu-id="349b1-154">Troubleshooting memory issues is a three step process:</span></span>

1.  <span data-ttu-id="349b1-155">Identificar la cantidad de memoria utilizada por los objetos de la base de datos o de la instancia.</span><span class="sxs-lookup"><span data-stu-id="349b1-155">Identify how much memory is being consumed by the objects in your database or instance.</span></span> <span data-ttu-id="349b1-156">Puede utilizar un conjunto completo de herramientas de supervisión disponibles para las tablas optimizadas para memoria como se describe anteriormente.</span><span class="sxs-lookup"><span data-stu-id="349b1-156">You can use a rich set of monitoring tools available for memory-optimized tables as described earlier.</span></span>  <span data-ttu-id="349b1-157">Por ejemplo, las DMV `sys.dm_db_xtp_table_memory_stats` o `sys.dm_os_memory_clerks`.</span><span class="sxs-lookup"><span data-stu-id="349b1-157">For example the DMVs `sys.dm_db_xtp_table_memory_stats` or `sys.dm_os_memory_clerks`.</span></span>

2.  <span data-ttu-id="349b1-158">Determinar en qué medida aumenta el consumo de memoria y cuánto espacio queda.</span><span class="sxs-lookup"><span data-stu-id="349b1-158">Determine how memory consumption is growing and how much head room you have left.</span></span> <span data-ttu-id="349b1-159">Mediante la supervisión periódica del consumo de memoria, puede saber cuánto aumenta el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-159">By monitoring the memory consumption periodically, you can know how the memory use is growing.</span></span> <span data-ttu-id="349b1-160">Por ejemplo, si ha asignado la base de datos a un grupo de recursos de servidor con nombre, puede supervisar el contador de rendimiento Memoria usada (KB) para ver cómo aumenta el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-160">For example, if you have mapped the database to a named resource pool, you can monitor the performance counter Used Memory (KB) to see how memory usage is growing.</span></span>

3.  <span data-ttu-id="349b1-161">Tome medidas para mitigar los posibles problemas de memoria.</span><span class="sxs-lookup"><span data-stu-id="349b1-161">Take action to mitigate the potential memory issues.</span></span> <span data-ttu-id="349b1-162">Para obtener más información, vea [resolver problemas de memoria insuficiente](resolve-out-of-memory-issues.md).</span><span class="sxs-lookup"><span data-stu-id="349b1-162">For more information, see [Resolve Out Of Memory Issues](resolve-out-of-memory-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="349b1-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="349b1-163">See Also</span></span>
 <span data-ttu-id="349b1-164">[Enlazar una base de datos con tablas optimizadas para memoria a un grupo de recursos](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [MIN_MEMORY_PERCENT cambiar y MAX_MEMORY_PERCENT en un grupo existente](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span><span class="sxs-lookup"><span data-stu-id="349b1-164">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [Change MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on an existing pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span></span>


