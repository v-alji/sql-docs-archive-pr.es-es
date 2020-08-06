---
title: Reorganización y nueva generación de índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.fragmentation.f1
- sql12.swb.index.reorg.f1
- sql12.swb.index.rebuild.f1
helpviewer_keywords:
- large object defragmenting
- indexes [SQL Server], reorganizing
- index reorganization [SQL Server]
- reorganizing indexes
- defragmenting large object data types
- index fragmentation [SQL Server]
- index rebuilding [SQL Server]
- rebuilding indexes
- indexes [SQL Server], rebuilding
- defragmenting indexes
- nonclustered indexes [SQL Server], defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
- LOB data [SQL Server], defragmenting
- clustered indexes, defragmenting
ms.assetid: a28c684a-c4e9-4b24-a7ae-e248808b31e9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c00f2128bb4c54064511ffff9e8929c9faf4d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749318"
---
# <a name="reorganize-and-rebuild-indexes"></a><span data-ttu-id="133cf-102">Reorganizar y volver a generar índices</span><span class="sxs-lookup"><span data-stu-id="133cf-102">Reorganize and Rebuild Indexes</span></span>
  <span data-ttu-id="133cf-103">En este tema se describe cómo reorganizar o volver a generar un índice fragmentado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="133cf-103">This topic describes how to reorganize or rebuild a fragmented index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="133cf-104">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] mantiene los índices automáticamente cada vez que se realizan operaciones de inserción, actualización o eliminación en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="133cf-104">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically maintains indexes whenever insert, update, or delete operations are made to the underlying data.</span></span> <span data-ttu-id="133cf-105">Con el tiempo, estas modificaciones pueden hacer que la información del índice se disperse por la base de datos (se fragmente).</span><span class="sxs-lookup"><span data-stu-id="133cf-105">Over time these modifications can cause the information in the index to become scattered in the database (fragmented).</span></span> <span data-ttu-id="133cf-106">La fragmentación ocurre cuando los índices tienen páginas en las que la ordenación lógica, basada en el valor de clave, no coincide con la ordenación física dentro del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="133cf-106">Fragmentation exists when indexes have pages in which the logical ordering, based on the key value, does not match the physical ordering inside the data file.</span></span> <span data-ttu-id="133cf-107">Los índices muy fragmentados pueden reducir el rendimiento de la consulta y ralentizar la respuesta de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="133cf-107">Heavily fragmented indexes can degrade query performance and cause your application to respond slowly.</span></span>  
  
 <span data-ttu-id="133cf-108">Puede solucionar la fragmentación del índice reorganizándolo o volviéndolo a generar.</span><span class="sxs-lookup"><span data-stu-id="133cf-108">You can remedy index fragmentation by reorganizing or rebuilding an index.</span></span> <span data-ttu-id="133cf-109">Para los índices con particiones generados en un esquema de partición, puede usar cualquiera de estos métodos en un índice completo o en una sola partición de un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-109">For partitioned indexes built on a partition scheme, you can use either of these methods on a complete index or a single partition of an index.</span></span> <span data-ttu-id="133cf-110">El proceso de volver a crear un índice quita y vuelve a crear el índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-110">Rebuilding an index drops and re-creates the index.</span></span> <span data-ttu-id="133cf-111">Quita la fragmentación, utiliza espacio en disco al compactar las páginas según el valor de factor de relleno especificado o existente y vuelve a ordenar las filas del índice en páginas contiguas.</span><span class="sxs-lookup"><span data-stu-id="133cf-111">This removes fragmentation, reclaims disk space by compacting the pages based on the specified or existing fill factor setting, and reorders the index rows in contiguous pages.</span></span> <span data-ttu-id="133cf-112">Cuando se especifica ALL, todos los índices de la tabla se quitan y se vuelven a generar en una única transacción.</span><span class="sxs-lookup"><span data-stu-id="133cf-112">When ALL is specified, all indexes on the table are dropped and rebuilt in a single transaction.</span></span> <span data-ttu-id="133cf-113">La reorganización de un índice usa muy pocos recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="133cf-113">Reorganizing an index uses minimal system resources.</span></span> <span data-ttu-id="133cf-114">Desfragmenta el nivel hoja de los índices agrupados y no clúster de las tablas y las vistas al volver a ordenar físicamente las páginas de nivel hoja para que coincidan con el orden lógico de los nodos hoja, de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="133cf-114">It defragments the leaf level of clustered and nonclustered indexes on tables and views by physically reordering the leaf-level pages to match the logical, left to right, order of the leaf nodes.</span></span> <span data-ttu-id="133cf-115">La reorganización también compacta las páginas de índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-115">Reorganizing also compacts the index pages.</span></span> <span data-ttu-id="133cf-116">La compactación se basa en el valor de factor de relleno existente.</span><span class="sxs-lookup"><span data-stu-id="133cf-116">Compaction is based on the existing fill factor value.</span></span>  
  
 <span data-ttu-id="133cf-117">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="133cf-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="133cf-118">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="133cf-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="133cf-119">Detectar la fragmentación</span><span class="sxs-lookup"><span data-stu-id="133cf-119">Detecting Fragmentation</span></span>](#Fragmentation)  
  
     [<span data-ttu-id="133cf-120">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="133cf-120">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="133cf-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="133cf-121">Security</span></span>](#Security)  
  
-   <span data-ttu-id="133cf-122">**Para comprobar la fragmentación de un índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="133cf-122">**To check the fragmentation of an index, using:**</span></span>  
  
     [<span data-ttu-id="133cf-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="133cf-123">SQL Server Management Studio</span></span>](#SSMSProcedureFrag)  
  
     [<span data-ttu-id="133cf-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="133cf-124">Transact-SQL</span></span>](#TsqlProcedureFrag)  
  
-   <span data-ttu-id="133cf-125">**Para reorganizar o volver a generar un índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="133cf-125">**To reorganize or rebuild an index, using:**</span></span>  
  
     [<span data-ttu-id="133cf-126">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="133cf-126">SQL Server Management Studio</span></span>](#SSMSProcedureReorg)  
  
     [<span data-ttu-id="133cf-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="133cf-127">Transact-SQL</span></span>](#TsqlProcedureReorg)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="133cf-128">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="133cf-128">Before You Begin</span></span>  
  
###  <a name="detecting-fragmentation"></a><a name="Fragmentation"></a><span data-ttu-id="133cf-129">Detección de fragmentación</span><span class="sxs-lookup"><span data-stu-id="133cf-129">Detecting Fragmentation</span></span>  
 <span data-ttu-id="133cf-130">El primer paso necesario para detectar qué método de desfragmentación utilizar es analizar el índice a fin de determinar la magnitud de la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="133cf-130">The first step in deciding which defragmentation method to use is to analyze the index to determine the degree of fragmentation.</span></span> <span data-ttu-id="133cf-131">Si usa la función del sistema [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), podrá detectar la fragmentación de un índice específico, de todos los índices de una tabla o vista indexada, de todos los índices de una base de datos o de todos los índices de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="133cf-131">By using the system function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), you can detect fragmentation in a specific index, all indexes on a table or indexed view, all indexes in a database, or all indexes in all databases.</span></span> <span data-ttu-id="133cf-132">Para los índices con particiones, **sys.dm_db_index_physical_stats** también proporciona información de la fragmentación para cada partición.</span><span class="sxs-lookup"><span data-stu-id="133cf-132">For partitioned indexes, **sys.dm_db_index_physical_stats** also provides fragmentation information for each partition.</span></span>  
  
 <span data-ttu-id="133cf-133">El conjunto de resultados devuelto por la función **sys.dm_db_index_physical_stats** tiene las columnas siguientes.</span><span class="sxs-lookup"><span data-stu-id="133cf-133">The result set returned by the **sys.dm_db_index_physical_stats** function includes the following columns.</span></span>  
  
|<span data-ttu-id="133cf-134">Columna</span><span class="sxs-lookup"><span data-stu-id="133cf-134">Column</span></span>|<span data-ttu-id="133cf-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="133cf-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="133cf-136">**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="133cf-136">**avg_fragmentation_in_percent**</span></span>|<span data-ttu-id="133cf-137">Porcentaje de fragmentación lógica (páginas de un índice que no funcionan correctamente).</span><span class="sxs-lookup"><span data-stu-id="133cf-137">The percent of logical fragmentation (out-of-order pages in the index).</span></span>|  
|<span data-ttu-id="133cf-138">**fragment_count**</span><span class="sxs-lookup"><span data-stu-id="133cf-138">**fragment_count**</span></span>|<span data-ttu-id="133cf-139">Número de fragmentos (páginas hoja físicamente consecutivas) en el índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-139">The number of fragments (physically consecutive leaf pages) in the index.</span></span>|  
|<span data-ttu-id="133cf-140">**avg_fragment_size_in_pages**</span><span class="sxs-lookup"><span data-stu-id="133cf-140">**avg_fragment_size_in_pages**</span></span>|<span data-ttu-id="133cf-141">Número promedio de páginas en un fragmento del índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-141">Average number of pages in one fragment in an index.</span></span>|  
  
 <span data-ttu-id="133cf-142">Una vez determinada la magnitud de la fragmentación, utilice la siguiente tabla para determinar el mejor método para corregir la fragmentación propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="133cf-142">After the degree of fragmentation is known, use the following table to determine the best method to correct the fragmentation.</span></span>  
  
|<span data-ttu-id="133cf-143">Valor de**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="133cf-143">**avg_fragmentation_in_percent** value</span></span>|<span data-ttu-id="133cf-144">Instrucción correctiva</span><span class="sxs-lookup"><span data-stu-id="133cf-144">Corrective statement</span></span>|  
|-----------------------------------------------|--------------------------|  
|<span data-ttu-id="133cf-145">> 5% y \< = 30%</span><span class="sxs-lookup"><span data-stu-id="133cf-145">> 5% and \< = 30%</span></span>|<span data-ttu-id="133cf-146">ALTER INDEX REORGANIZE</span><span class="sxs-lookup"><span data-stu-id="133cf-146">ALTER INDEX REORGANIZE</span></span>|  
|<span data-ttu-id="133cf-147">> 30%</span><span class="sxs-lookup"><span data-stu-id="133cf-147">> 30%</span></span>|<span data-ttu-id="133cf-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="133cf-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span></span>|

<span data-ttu-id="133cf-149"><sup>1</sup> La regeneración de un índice se puede ejecutar en línea o sin conexión.</span><span class="sxs-lookup"><span data-stu-id="133cf-149"><sup>1</sup> Rebuilding an index can be executed online or offline.</span></span> <span data-ttu-id="133cf-150">La reorganización de un índice siempre se ejecuta en línea.</span><span class="sxs-lookup"><span data-stu-id="133cf-150">Reorganizing an index is always executed online.</span></span> <span data-ttu-id="133cf-151">Para lograr una disponibilidad similar a la opción de reorganización, debe volver a generar los índices en línea.</span><span class="sxs-lookup"><span data-stu-id="133cf-151">To achieve availability similar to the reorganize option, you should rebuild indexes online.</span></span>  
  
> [!TIP]
> <span data-ttu-id="133cf-152">Estos valores proporcionan directrices generales para la determinación del punto en el que debe cambiar entre `ALTER INDEX REORGANIZE` y `ALTER INDEX REBUILD`.</span><span class="sxs-lookup"><span data-stu-id="133cf-152">These values provide a rough guideline for determining the point at which you should switch between `ALTER INDEX REORGANIZE` and `ALTER INDEX REBUILD`.</span></span> <span data-ttu-id="133cf-153">No obstante, los valores reales pueden variar de un caso a otro.</span><span class="sxs-lookup"><span data-stu-id="133cf-153">However, the actual values may vary from case to case.</span></span> <span data-ttu-id="133cf-154">Es importante que experimente la determinación del mejor umbral para su entorno.</span><span class="sxs-lookup"><span data-stu-id="133cf-154">It is important that you experiment to determine the best threshold for your environment.</span></span> <span data-ttu-id="133cf-155">Por ejemplo, si se usa un índice determinado principalmente para operaciones de examen, la eliminación de la fragmentación puede mejorar el rendimiento de estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="133cf-155">For example, if a given index is used mainly for scan operations, removing fragmentation can improve performance of these operations.</span></span> <span data-ttu-id="133cf-156">Las ventajas de rendimiento son menos evidentes para los índices que se usan principalmente para las operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="133cf-156">The performance benefit is less noticeable for indexes that are used primarily for seek operations.</span></span> <span data-ttu-id="133cf-157">Del mismo modo, la eliminación de la fragmentación en un montón (una tabla sin índice agrupado) es especialmente útil para las operaciones de examen de índices no agrupados, pero tiene poco efecto en las operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="133cf-157">Similarly, removing fragmentation in a heap (a table with no clustered index) is especially useful for nonclustered index scan operations, but has little effect in lookup operations.</span></span>

<span data-ttu-id="133cf-158">Los niveles de fragmentación muy bajos (inferiores al 5 por ciento) normalmente no deben tratarse con ninguno de estos comandos, dado que el beneficio de quitar una cantidad de fragmentación tan pequeña es casi siempre ampliamente superado por el costo de reorganizar o volver a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-158">Very low levels of fragmentation (less than 5 percent) should typically not be addressed by either of these commands, because the benefit from removing such a small amount of fragmentation is almost always vastly outweighed by the cost of reorganizing or rebuilding the index.</span></span> 

> [!NOTE]
> <span data-ttu-id="133cf-159">Con frecuencia, cuando se vuelven a generar o se reorganizan los índices pequeños no se reduce la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="133cf-159">Rebuilding or reorganizing small indexes often does not reduce fragmentation.</span></span> <span data-ttu-id="133cf-160">Las páginas de índices pequeños a veces se almacenan en extensiones mixtas.</span><span class="sxs-lookup"><span data-stu-id="133cf-160">The pages of small indexes are sometimes stored on mixed extents.</span></span> <span data-ttu-id="133cf-161">Las extensiones mixtas pueden estar compartidas por hasta ocho objetos, de modo que es posible que no se pueda reducir la fragmentación en un índice pequeño después de reorganizar o volver a generar dicho índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-161">Mixed extents are shared by up to eight objects, so the fragmentation in a small index might not be reduced after reorganizing or rebuilding it.</span></span>

### <a name="index-defragmentation-considerations"></a><span data-ttu-id="133cf-162">Consideraciones sobre la desfragmentación de índices</span><span class="sxs-lookup"><span data-stu-id="133cf-162">Index defragmentation considerations</span></span>
<span data-ttu-id="133cf-163">En determinadas circunstancias, al recompilar un índice agrupado, se recompilarán automáticamente los índices no agrupados que hagan referencia a la clave de agrupación en clústeres, si es necesario cambiar los identificadores físicos o lógicos contenidos en los registros de índices no agrupados.</span><span class="sxs-lookup"><span data-stu-id="133cf-163">Under certain conditions, rebuilding a clustered index will automatically rebuild any nonclustered index that reference the clustering key, if the physical or logical identifiers contained in the nonclustered index records needs to change.</span></span>

<span data-ttu-id="133cf-164">Escenarios que obligan a que todos los índices no agrupados se recompilen automáticamente en una tabla:</span><span class="sxs-lookup"><span data-stu-id="133cf-164">Scenarios that force all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="133cf-165">Creación de un índice agrupado en una tabla</span><span class="sxs-lookup"><span data-stu-id="133cf-165">Creating a clustered index on a table</span></span>
-  <span data-ttu-id="133cf-166">Eliminación de un índice agrupado, lo que hace que la tabla se almacene como un montón</span><span class="sxs-lookup"><span data-stu-id="133cf-166">Removing a clustered index, causing the table to be stored as a heap</span></span>
-  <span data-ttu-id="133cf-167">Cambio de la clave de agrupación en clústeres para incluir o excluir columnas</span><span class="sxs-lookup"><span data-stu-id="133cf-167">Changing the clustering key to include or exclude columns</span></span>

<span data-ttu-id="133cf-168">Escenarios que no requieren recompilar automáticamente en una tabla todos los índices no agrupados:</span><span class="sxs-lookup"><span data-stu-id="133cf-168">Scenarios that do not require all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="133cf-169">Recompilación de un índice agrupado único</span><span class="sxs-lookup"><span data-stu-id="133cf-169">Rebuilding a unique clustered index</span></span>
-  <span data-ttu-id="133cf-170">Recompilación de un índice agrupado que no es único</span><span class="sxs-lookup"><span data-stu-id="133cf-170">Rebuilding a non-unique clustered index</span></span>
-  <span data-ttu-id="133cf-171">Cambio del esquema de índice, como al aplicar un esquema de partición a un índice agrupado o al mover el índice agrupado a un grupo de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="133cf-171">Changing the index schema, such as applying a partitioning scheme to a clustered index or moving the clustered index to a different filegroup</span></span>
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="133cf-172">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="133cf-172">Limitations and Restrictions</span></span>  
  
<span data-ttu-id="133cf-173">Los índices que tienen más de 128 extensiones se vuelven a generar en dos fases independientes: lógica y física.</span><span class="sxs-lookup"><span data-stu-id="133cf-173">Indexes with more than 128 extents are rebuilt in two separate phases: logical and physical.</span></span> <span data-ttu-id="133cf-174">En la fase lógica, las unidades de asignación existentes que utiliza el índice están señaladas para cancelación de asignación las filas de datos se copian y ordenan y luego se mueven a las nuevas unidades de asignación creadas para almacenar el índice recompilado.</span><span class="sxs-lookup"><span data-stu-id="133cf-174">In the logical phase, the existing allocation units used by the index are marked for deallocation, the data rows are copied and sorted, then moved to new allocation units created to store the rebuilt index.</span></span> <span data-ttu-id="133cf-175">En la fase física, las unidades de asignación previamente señaladas para cancelación de asignación se quitan físicamente de las transacciones breves que se realizan en segundo plano y no requieren demasiados bloqueos.</span><span class="sxs-lookup"><span data-stu-id="133cf-175">In the physical phase, the allocation units previously marked for deallocation are physically dropped in short transactions that happen in the background, and do not require many locks.</span></span> <span data-ttu-id="133cf-176">Para obtener más información acerca de las extensiones, consulte la [Guía de arquitectura de páginas y extensiones](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span><span class="sxs-lookup"><span data-stu-id="133cf-176">For more information about extents, refer to the [Pages and Extents Architecture Guide](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span></span>

<span data-ttu-id="133cf-177">La instrucción `ALTER INDEX REORGANIZE` requiere que el archivo de datos que contiene el índice tenga espacio disponible, ya que la operación solo puede asignar páginas de trabajo temporales en el mismo archivo, no en otro archivo del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="133cf-177">The `ALTER INDEX REORGANIZE` statement requires the data file containing the index to have space available, because the operation can only allocate temporary work pages on the same file, not another file within the filegroup.</span></span> <span data-ttu-id="133cf-178">Debido a esto, aunque el grupo de archivos tenga páginas libres disponibles, puede que al usuario le siga apareciendo el error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span><span class="sxs-lookup"><span data-stu-id="133cf-178">So although the filegroup might have free pages available, the user can still encounter error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span></span>

<span data-ttu-id="133cf-179">Se pueden crear y regenerar índices no alineados en una tabla con más de 1000 particiones, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="133cf-179">Creating and rebuilding non-aligned indexes on a table with more than 1,000 partitions is possible, but is not recommended.</span></span> <span data-ttu-id="133cf-180">Si se hace, se puede degradar el rendimiento o consumir excesiva memoria durante estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="133cf-180">Doing so may cause degraded performance or excessive memory consumption during these operations.</span></span>

<span data-ttu-id="133cf-181">No es posible volver a organizar o generar un índice si el grupo de archivos en el que se encuentra está sin conexión o está definido como de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="133cf-181">An index cannot be reorganized or rebuilt if the filegroup in which it is located is offline or set to read-only.</span></span> <span data-ttu-id="133cf-182">Cuando se especifica la palabra clave `ALL` y hay uno o más índices en un grupo de archivos sin conexión o de solo lectura, se produce un error en la instrucción.</span><span class="sxs-lookup"><span data-stu-id="133cf-182">When the keyword `ALL` is specified and one or more indexes are in an offline or read-only filegroup, the statement fails.</span></span>
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="133cf-183">Seguridad</span><span class="sxs-lookup"><span data-stu-id="133cf-183">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="133cf-184">Permisos</span><span class="sxs-lookup"><span data-stu-id="133cf-184">Permissions</span></span>  
 <span data-ttu-id="133cf-185">Debe tener un permiso de `ALTER` sobre la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="133cf-185">Requires `ALTER` permission on the table or view.</span></span> <span data-ttu-id="133cf-186">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="133cf-186">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureFrag"></a> <span data-ttu-id="133cf-187">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="133cf-187">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="133cf-188">Para comprobar la fragmentación de un índice</span><span class="sxs-lookup"><span data-stu-id="133cf-188">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="133cf-189">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que quiera comprobar la fragmentación de un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-189">In Object Explorer, Expand the database that contains the table on which you want to check an index's fragmentation.</span></span>  
  
2.  <span data-ttu-id="133cf-190">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="133cf-190">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="133cf-191">Expanda la tabla en la que quiera comprobar la fragmentación de un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-191">Expand the table on which you want to check an index's fragmentation.</span></span>  
  
4.  <span data-ttu-id="133cf-192">Expanda la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="133cf-192">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="133cf-193">Haga clic con el botón derecho en el índice en el que quiere comprobar la fragmentación y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="133cf-193">Right-click the index of which you want to check the fragmentation and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="133cf-194">Bajo **Seleccionar una página**, seleccione **Fragmentación**.</span><span class="sxs-lookup"><span data-stu-id="133cf-194">Under **Select a page**, select **Fragmentation**.</span></span>  
  
     <span data-ttu-id="133cf-195">La siguiente información está disponible en la página **Fragmentación** :</span><span class="sxs-lookup"><span data-stu-id="133cf-195">The following information is available on the **Fragmentation** page:</span></span>  
  
     <span data-ttu-id="133cf-196">**Llenado de página**</span><span class="sxs-lookup"><span data-stu-id="133cf-196">**Page fullness**</span></span>  
     <span data-ttu-id="133cf-197">Indica el promedio de llenado de las páginas de índice como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="133cf-197">Indicates average fullness of the index pages, as a percentage.</span></span> <span data-ttu-id="133cf-198">100% indica que las páginas de índice están completamente llenas.</span><span class="sxs-lookup"><span data-stu-id="133cf-198">100% means the index pages are completely full.</span></span> <span data-ttu-id="133cf-199">50% indica que, como promedio, las páginas de índice están llenas a la mitad.</span><span class="sxs-lookup"><span data-stu-id="133cf-199">50% means that, on average, each index page is half full.</span></span>  
  
     <span data-ttu-id="133cf-200">**Fragmentación total**</span><span class="sxs-lookup"><span data-stu-id="133cf-200">**Total fragmentation**</span></span>  
     <span data-ttu-id="133cf-201">Porcentaje de fragmentación lógica.</span><span class="sxs-lookup"><span data-stu-id="133cf-201">The logical fragmentation percentage.</span></span> <span data-ttu-id="133cf-202">Indica el número de páginas de un índice que no están almacenadas en orden.</span><span class="sxs-lookup"><span data-stu-id="133cf-202">This indicates the number of pages in an index that are not stored in order.</span></span>  
  
     <span data-ttu-id="133cf-203">**Promedio de tamaño de fila**</span><span class="sxs-lookup"><span data-stu-id="133cf-203">**Average row size**</span></span>  
     <span data-ttu-id="133cf-204">Tamaño medio de una fila de nivel hoja.</span><span class="sxs-lookup"><span data-stu-id="133cf-204">The average size of a leaf level row.</span></span>  
  
     <span data-ttu-id="133cf-205">**Profundidad**</span><span class="sxs-lookup"><span data-stu-id="133cf-205">**Depth**</span></span>  
     <span data-ttu-id="133cf-206">Número de niveles del índice, incluido el nivel hoja.</span><span class="sxs-lookup"><span data-stu-id="133cf-206">The number of levels in the index, including the leaf level.</span></span>  
  
     <span data-ttu-id="133cf-207">**Registros reenviados**</span><span class="sxs-lookup"><span data-stu-id="133cf-207">**Forwarded records**</span></span>  
     <span data-ttu-id="133cf-208">Número de registros de un montón que han reenviado punteros a otra ubicación de datos.</span><span class="sxs-lookup"><span data-stu-id="133cf-208">The number of records in a heap that have forward pointers to another data location.</span></span> <span data-ttu-id="133cf-209">Este estado se produce durante una actualización, cuando no existe suficiente espacio para almacenar la nueva fila en la ubicación original.</span><span class="sxs-lookup"><span data-stu-id="133cf-209">(This state occurs during an update, when there is not enough room to store the new row in the original location.)</span></span>  
  
     <span data-ttu-id="133cf-210">**Filas fantasma**</span><span class="sxs-lookup"><span data-stu-id="133cf-210">**Ghost rows**</span></span>  
     <span data-ttu-id="133cf-211">Número de filas marcadas como eliminadas que todavía no se han quitado.</span><span class="sxs-lookup"><span data-stu-id="133cf-211">The number of rows that are marked as deleted but not yet removed.</span></span> <span data-ttu-id="133cf-212">Estas filas se quitarán en un subproceso de limpieza, cuando el servidor no esté ocupado.</span><span class="sxs-lookup"><span data-stu-id="133cf-212">These rows will be removed by a clean-up thread, when the server is not busy.</span></span> <span data-ttu-id="133cf-213">Este valor no incluye las filas que se retienen debido a una transacción pendiente de aislamiento de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="133cf-213">This value does not include rows that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
     <span data-ttu-id="133cf-214">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="133cf-214">**Index type**</span></span>  
     <span data-ttu-id="133cf-215">Tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-215">The type of index.</span></span> <span data-ttu-id="133cf-216">Los valores posibles son **Índice clúster**, **Índice no clúster**y **XML principal**.</span><span class="sxs-lookup"><span data-stu-id="133cf-216">Possible values are **Clustered index**, **Nonclustered index**, and **Primary XML**.</span></span> <span data-ttu-id="133cf-217">Las tablas también se pueden almacenar como un montón (sin índices), pero en tal caso la página Propiedades del índice no puede abrirse.</span><span class="sxs-lookup"><span data-stu-id="133cf-217">Tables can also be stored as a heap (without indexes), but then this Index Properties page cannot be opened.</span></span>  
  
     <span data-ttu-id="133cf-218">**Filas de nivel de hoja**</span><span class="sxs-lookup"><span data-stu-id="133cf-218">**Leaf-level rows**</span></span>  
     <span data-ttu-id="133cf-219">Número de filas de nivel hoja.</span><span class="sxs-lookup"><span data-stu-id="133cf-219">The number of leaf level rows.</span></span>  
  
     <span data-ttu-id="133cf-220">**Tamaño máximo de la fila**</span><span class="sxs-lookup"><span data-stu-id="133cf-220">**Maximum row size**</span></span>  
     <span data-ttu-id="133cf-221">Tamaño máximo de la fila de nivel de hoja.</span><span class="sxs-lookup"><span data-stu-id="133cf-221">The maximum leaf-level row size.</span></span>  
  
     <span data-ttu-id="133cf-222">**Tamaño mínimo de la fila**</span><span class="sxs-lookup"><span data-stu-id="133cf-222">**Minimum row size**</span></span>  
     <span data-ttu-id="133cf-223">Tamaño mínimo de la fila de nivel de hoja.</span><span class="sxs-lookup"><span data-stu-id="133cf-223">The minimum leaf-level row size.</span></span>  
  
     <span data-ttu-id="133cf-224">**Páginas**</span><span class="sxs-lookup"><span data-stu-id="133cf-224">**Pages**</span></span>  
     <span data-ttu-id="133cf-225">Número total de páginas de datos.</span><span class="sxs-lookup"><span data-stu-id="133cf-225">The total number of data pages.</span></span>  
  
     <span data-ttu-id="133cf-226">**Identificador de la partición**</span><span class="sxs-lookup"><span data-stu-id="133cf-226">**Partition ID**</span></span>  
     <span data-ttu-id="133cf-227">Id. de partición del árbol b que contiene el índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-227">The partition ID of the b-tree containing the index.</span></span>  
  
     <span data-ttu-id="133cf-228">**Filas fantasma de la versión**</span><span class="sxs-lookup"><span data-stu-id="133cf-228">**Version ghost rows**</span></span>  
     <span data-ttu-id="133cf-229">Número de registros fantasma que se retienen debido a una transacción de aislamiento de instantánea pendiente.</span><span class="sxs-lookup"><span data-stu-id="133cf-229">The number of ghost records that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureFrag"></a> <span data-ttu-id="133cf-230">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="133cf-230">Using Transact-SQL</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="133cf-231">Para comprobar la fragmentación de un índice</span><span class="sxs-lookup"><span data-stu-id="133cf-231">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="133cf-232">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="133cf-232">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="133cf-233">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="133cf-233">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="133cf-234">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-234">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find the average fragmentation percentage of all indexes  
    -- in the HumanResources.Employee table.   
    SELECT a.index_id, name, avg_fragmentation_in_percent  
    FROM sys.dm_db_index_physical_stats (DB_ID(N'AdventureWorks2012'), OBJECT_ID(N'HumanResources.Employee'), NULL, NULL, NULL) AS a  
        JOIN sys.indexes AS b ON a.object_id = b.object_id AND a.index_id = b.index_id;   
    GO  
    ```  
  
     <span data-ttu-id="133cf-235">La instrucción anterior puede devolver un conjunto de resultados similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="133cf-235">The statement above might return a result set similar to the following.</span></span>  
  
    ```  
    index_id    name                                                  avg_fragmentation_in_percent  
    ----------- ----------------------------------------------------- ----------------------------  
    1           PK_Employee_BusinessEntityID                          0  
    2           IX_Employee_OrganizationalNode                        0  
    3           IX_Employee_OrganizationalLevel_OrganizationalNode    0  
    5           AK_Employee_LoginID                                   66.6666666666667  
    6           AK_Employee_NationalIDNumber                          50  
    7           AK_Employee_rowguid                                   0  
  
    (6 row(s) affected)  
    ```  
  
 <span data-ttu-id="133cf-236">Para obtener más información, vea [Sys. dm_db_index_physical_stats &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="133cf-236">For more information, see  [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureReorg"></a> <span data-ttu-id="133cf-237">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="133cf-237">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-reorganize-or-rebuild-an-index"></a><span data-ttu-id="133cf-238">Para reorganizar o volver a generar un índice</span><span class="sxs-lookup"><span data-stu-id="133cf-238">To reorganize or rebuild an index</span></span>  
  
1.  <span data-ttu-id="133cf-239">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea reorganizar un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-239">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="133cf-240">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="133cf-240">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="133cf-241">Expanda la tabla en la que desea reorganizar un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-241">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="133cf-242">Expanda la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="133cf-242">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="133cf-243">Haga clic con el botón derecho en el índice que quiera reorganizar y seleccione **Reorganizar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-243">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="133cf-244">En el cuadro de diálogo **Reorganizar índices** , compruebe que el índice correcto se encuentra en la cuadrícula **Índices que se van a reorganizar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-244">In the **Reorganize Indexes** dialog box, verify that the correct index is in the **Indexes to be reorganized** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="133cf-245">Active la casilla **Compactar datos de columnas de objetos de gran tamaño** para especificar que se compacten también todas las páginas que contengan datos de objetos grandes (LOB).</span><span class="sxs-lookup"><span data-stu-id="133cf-245">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="133cf-246">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-246">Click **OK.**</span></span>  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="133cf-247">Para reorganizar todos los índices de una tabla</span><span class="sxs-lookup"><span data-stu-id="133cf-247">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="133cf-248">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea reorganizar los índices.</span><span class="sxs-lookup"><span data-stu-id="133cf-248">In Object Explorer, Expand the database that contains the table on which you want to reorganize the indexes.</span></span>  
  
2.  <span data-ttu-id="133cf-249">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="133cf-249">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="133cf-250">Expanda la tabla en la que desea reorganizar los índices.</span><span class="sxs-lookup"><span data-stu-id="133cf-250">Expand the table on which you want to reorganize the indexes.</span></span>  
  
4.  <span data-ttu-id="133cf-251">Haga clic con el botón derecho en la carpeta **Índices** y seleccione **Reorganizar todo**.</span><span class="sxs-lookup"><span data-stu-id="133cf-251">Right-click the **Indexes** folder and select **Reorganize All**.</span></span>  
  
5.  <span data-ttu-id="133cf-252">En el cuadro de diálogo **Reorganizar índices** , compruebe que los índices adecuados están en **Índices que se van a reorganizar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-252">In the **Reorganize Indexes** dialog box, verify that the correct indexes are in the **Indexes to be reorganized**.</span></span> <span data-ttu-id="133cf-253">Para quitar un índice de la cuadrícula **Índices que se van a reorganizar** , seleccione el índice y, a continuación, presione la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="133cf-253">To remove an index from the **Indexes to be reorganized** grid, select the index and then press the Delete key.</span></span>  
  
6.  <span data-ttu-id="133cf-254">Active la casilla **Compactar datos de columnas de objetos de gran tamaño** para especificar que se compacten también todas las páginas que contengan datos de objetos grandes (LOB).</span><span class="sxs-lookup"><span data-stu-id="133cf-254">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
7.  <span data-ttu-id="133cf-255">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-255">Click **OK.**</span></span>  
  
#### <a name="to-rebuild-an-index"></a><span data-ttu-id="133cf-256">Para volver a generar un índice</span><span class="sxs-lookup"><span data-stu-id="133cf-256">To rebuild an index</span></span>  
  
1.  <span data-ttu-id="133cf-257">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea reorganizar un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-257">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="133cf-258">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="133cf-258">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="133cf-259">Expanda la tabla en la que desea reorganizar un índice.</span><span class="sxs-lookup"><span data-stu-id="133cf-259">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="133cf-260">Expanda la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="133cf-260">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="133cf-261">Haga clic con el botón derecho en el índice que quiera reorganizar y seleccione **Reorganizar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-261">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="133cf-262">En el cuadro de diálogo **Volver a generar índices** , compruebe que el índice correcto se encuentra en la cuadrícula **Índices que se van a volver a generar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-262">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to be rebuilt** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="133cf-263">Active la casilla **Compactar datos de columnas de objetos de gran tamaño** para especificar que se compacten también todas las páginas que contengan datos de objetos grandes (LOB).</span><span class="sxs-lookup"><span data-stu-id="133cf-263">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="133cf-264">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-264">Click **OK.**</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureReorg"></a> <span data-ttu-id="133cf-265">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="133cf-265">Using Transact-SQL</span></span>  
  
#### <a name="to-reorganize-a-defragmented-index"></a><span data-ttu-id="133cf-266">Para reorganizar un índice desfragmentado</span><span class="sxs-lookup"><span data-stu-id="133cf-266">To reorganize a defragmented index</span></span>  
  
1.  <span data-ttu-id="133cf-267">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="133cf-267">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="133cf-268">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="133cf-268">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="133cf-269">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-269">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize the IX_Employee_OrganizationalLevel_OrganizationalNode index on the HumanResources.Employee table.   
  
    ALTER INDEX IX_Employee_OrganizationalLevel_OrganizationalNode ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="133cf-270">Para reorganizar todos los índices de una tabla</span><span class="sxs-lookup"><span data-stu-id="133cf-270">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="133cf-271">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="133cf-271">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="133cf-272">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="133cf-272">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="133cf-273">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-273">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-rebuild-a-defragmented-index"></a><span data-ttu-id="133cf-274">Para volver a generar un índice desfragmentado</span><span class="sxs-lookup"><span data-stu-id="133cf-274">To rebuild a defragmented index</span></span>  
  
1.  <span data-ttu-id="133cf-275">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="133cf-275">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="133cf-276">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="133cf-276">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="133cf-277">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="133cf-277">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="133cf-278">En el ejemplo se vuelve a generar un único índice en la tabla `Employee` .</span><span class="sxs-lookup"><span data-stu-id="133cf-278">The example rebuilds a single index on the `Employee` table.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex1](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex1)]  
  
#### <a name="to-rebuild-all-indexes-in-a-table"></a><span data-ttu-id="133cf-279">Para volver a generar todos los índices de una tabla</span><span class="sxs-lookup"><span data-stu-id="133cf-279">To rebuild all indexes in a table</span></span>  
  
1.  <span data-ttu-id="133cf-280">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="133cf-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="133cf-281">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="133cf-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="133cf-282">Copie y pegue el ejemplo siguiente en la ventana de consulta. En el ejemplo se especifica la palabra clave `ALL`.</span><span class="sxs-lookup"><span data-stu-id="133cf-282">Copy and paste the following example into the query The example specifies the keyword `ALL`.</span></span> <span data-ttu-id="133cf-283">Así se regeneran todos los índices asociados a la tabla.</span><span class="sxs-lookup"><span data-stu-id="133cf-283">This rebuilds all indexes associated with the table.</span></span> <span data-ttu-id="133cf-284">Se especifican tres opciones.</span><span class="sxs-lookup"><span data-stu-id="133cf-284">Three options are specified.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="133cf-285">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="133cf-285">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133cf-286">Consulte también</span><span class="sxs-lookup"><span data-stu-id="133cf-286">See Also</span></span>  
 [<span data-ttu-id="133cf-287">Prácticas recomendadas de desfragmentación de índices de Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="133cf-287">Microsoft SQL Server 2000 Index Defragmentation Best Practices</span></span>](https://technet.microsoft.com/library/cc966523.aspx)  
  
  
