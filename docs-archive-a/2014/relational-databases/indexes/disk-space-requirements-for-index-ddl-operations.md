---
title: Requisitos de espacio en disco para operaciones DDL de índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- index disk space [SQL Server]
- space [SQL Server], indexes
- indexes [SQL Server], disk space requirements
- temporary disk space [SQL Server]
ms.assetid: 35930826-c870-44c1-a966-a6a4638f62ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4ac25fc1555d6b6cfd8ee97b50d261cf5788f587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677102"
---
# <a name="disk-space-requirements-for-index-ddl-operations"></a><span data-ttu-id="0f1b9-102">Requisitos de espacio en disco para operaciones DDL de índice</span><span class="sxs-lookup"><span data-stu-id="0f1b9-102">Disk Space Requirements for Index DDL Operations</span></span>
  <span data-ttu-id="0f1b9-103">El espacio en disco es una consideración importante a la hora de crear, volver a generar o quitar índices.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-103">Disk space is an important consideration when you create, rebuild, or drop indexes.</span></span> <span data-ttu-id="0f1b9-104">Un espacio en disco inadecuado puede degradar el rendimiento e incluso provocar errores en las operaciones de índice.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-104">Inadequate disk space can degrade performance or even cause the index operation to fail.</span></span> <span data-ttu-id="0f1b9-105">En este tema se proporciona información general que puede ayudar a determinar la cantidad de espacio necesario para las operaciones de lenguaje de definición de datos (DDL).</span><span class="sxs-lookup"><span data-stu-id="0f1b9-105">This topic provides general information that can help you determine the amount of disk space required for index data definition language (DDL) operations.</span></span>  
  
## <a name="index-operations-that-require-no-additional-disk-space"></a><span data-ttu-id="0f1b9-106">Operaciones de índice que no requieren espacio en disco adicional</span><span class="sxs-lookup"><span data-stu-id="0f1b9-106">Index Operations That Require No Additional Disk Space</span></span>  
 <span data-ttu-id="0f1b9-107">Las siguientes operaciones de índice no requieren espacio en disco adicional:</span><span class="sxs-lookup"><span data-stu-id="0f1b9-107">The following index operations require no additional disk space:</span></span>  
  
-   <span data-ttu-id="0f1b9-108">ALTER INDEX REORGANIZE; sin embargo, se requiere espacio de registro.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-108">ALTER INDEX REORGANIZE; however, log space is required.</span></span>  
  
-   <span data-ttu-id="0f1b9-109">DROP INDEX cuando se quita un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-109">DROP INDEX when you are dropping a nonclustered index.</span></span>  
  
-   <span data-ttu-id="0f1b9-110">DROP INDEX cuando se quita un índice clúster sin conexión sin especificar la cláusula MOVE TO y no existen índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-110">DROP INDEX when you are dropping a clustered index offline without specifying the MOVE TO clause and nonclustered indexes do not exist.</span></span>  
  
-   <span data-ttu-id="0f1b9-111">CREATE TABLE (restricciones PRIMARY KEY o UNIQUE).</span><span class="sxs-lookup"><span data-stu-id="0f1b9-111">CREATE TABLE (PRIMARY KEY or UNIQUE constraints)</span></span>  
  
## <a name="index-operations-that-require-additional-disk-space"></a><span data-ttu-id="0f1b9-112">Operaciones de índice que requieren espacio en disco adicional</span><span class="sxs-lookup"><span data-stu-id="0f1b9-112">Index Operations That Require Additional Disk Space</span></span>  
 <span data-ttu-id="0f1b9-113">Todas las demás operaciones DDL de índice requieren espacio temporal en disco adicional para utilizarlo durante la operación y espacio en disco permanente para almacenar la estructura (o estructuras) del nuevo índice.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-113">All other index DDL operations require additional temporary disk space to use during the operation, and permanent disk space to store the new index structure or structures.</span></span>  
  
 <span data-ttu-id="0f1b9-114">Cuando se crea una nueva estructura de índice, se requiere espacio en disco para ambas estructuras, la antigua (origen) y la nueva (destino), en los archivos y grupos de archivos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-114">When a new index structure is created, disk space for both the old (source) and new (target) structures is required in their appropriate files and filegroups.</span></span> <span data-ttu-id="0f1b9-115">La asignación de la estructura antigua no se cancela hasta que no se confirma la transacción de creación del índice.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-115">The old structure is not deallocated until the index creation transaction commits.</span></span>  
  
 <span data-ttu-id="0f1b9-116">Las siguientes operaciones DDL de índice crean estructuras y requieren espacio en disco adicional:</span><span class="sxs-lookup"><span data-stu-id="0f1b9-116">The following index DDL operations create new index structures and require additional disk space:</span></span>  
  
-   <span data-ttu-id="0f1b9-117">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="0f1b9-117">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="0f1b9-118">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="0f1b9-118">CREATE INDEX WITH DROP_EXISTING</span></span>  
  
-   <span data-ttu-id="0f1b9-119">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="0f1b9-119">ALTER INDEX REBUILD</span></span>  
  
-   <span data-ttu-id="0f1b9-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY o UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="0f1b9-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY or UNIQUE)</span></span>  
  
-   <span data-ttu-id="0f1b9-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY o UNIQUE) cuando la restricción se basa en un índice clúster</span><span class="sxs-lookup"><span data-stu-id="0f1b9-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY or UNIQUE) when the constraint is based on a clustered index</span></span>  
  
-   <span data-ttu-id="0f1b9-122">DROP INDEX MOVE TO (se aplica solo a ndices clúster)</span><span class="sxs-lookup"><span data-stu-id="0f1b9-122">DROP INDEX MOVE TO (Applies only to clustered indexes.)</span></span>  
  
## <a name="temporary-disk-space-for-sorting"></a><span data-ttu-id="0f1b9-123">Espacio temporal en disco para ordenación</span><span class="sxs-lookup"><span data-stu-id="0f1b9-123">Temporary Disk Space for Sorting</span></span>  
 <span data-ttu-id="0f1b9-124">Además del espacio en disco necesario para las estructuras de origen y destino, se necesita espacio temporal en disco para la ordenación, a menos que el optimizador de consultas busque un plan de ejecución que no requiera ordenación.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-124">Besides the disk space required for the source and target structures, temporary disk space is required for sorting, unless the query optimizer finds an execution plan that does not require sorting.</span></span>  
  
 <span data-ttu-id="0f1b9-125">Si se requiere ordenación, ésta se produce en un nuevo índice a la vez.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-125">If sorting is required, sorting occurs one new index at a time.</span></span> <span data-ttu-id="0f1b9-126">Por ejemplo, cuando se vuelve a generar un índice clúster con los índices no clúster que van asociados en una instrucción única, los índices se ordenan uno tras otro.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-126">For example, when you rebuild a clustered index and associated nonclustered indexes within a single statement, the indexes are sorted one after the other.</span></span> <span data-ttu-id="0f1b9-127">Por lo tanto, el espacio temporal en disco que se necesita para ordenar solo tiene que ser tan grande como el índice más grande de la operación.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-127">Therefore, the additional temporary disk space that is required for sorting only has to be as large as the largest index in the operation.</span></span> <span data-ttu-id="0f1b9-128">Éste casi siempre se corresponde con el índice clúster.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-128">This is almost always the clustered index.</span></span>  
  
 <span data-ttu-id="0f1b9-129">Si la opción SORT_IN_TEMPDB está establecida en ON, el índice más grande debe caber en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-129">If the SORT_IN_TEMPDB option is set to ON, the largest index must fit into **tempdb**.</span></span> <span data-ttu-id="0f1b9-130">Aunque esta opción aumenta la cantidad de espacio temporal en disco utilizado para crear un índice, puede reducir el tiempo necesario para crear el índice cuando **tempdb** se encuentra en un conjunto de discos diferente al de la base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-130">Although this option increases the amount of temporary disk space that is used to create an index, it may reduce the time that is required to create an index when **tempdb** is on a set of disks different from the user database.</span></span>  
  
 <span data-ttu-id="0f1b9-131">Si SORT_IN_TEMPDB está establecido en OFF (el valor predeterminado), cada índice, incluidos los índices con particiones, se ordena en su espacio en disco de destino y solo se necesita espacio en disco para las nuevas estructuras de índice.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-131">If SORT_IN_TEMPDB is set to OFF (the default) each index, including partitioned indexes, is sorted in its destination disk space; and only the disk space for the new index structures is required.</span></span>  
  
 <span data-ttu-id="0f1b9-132">Para obtener un ejemplo de cálculo de espacio en disco, vea [Index Disk Space Example](index-disk-space-example.md).</span><span class="sxs-lookup"><span data-stu-id="0f1b9-132">For an example of calculating disk space, see [Index Disk Space Example](index-disk-space-example.md).</span></span>  
  
## <a name="temporary-disk-space-for-online-index-operations"></a><span data-ttu-id="0f1b9-133">Espacio temporal en disco para operaciones de índice en línea</span><span class="sxs-lookup"><span data-stu-id="0f1b9-133">Temporary Disk Space for Online Index Operations</span></span>  
 <span data-ttu-id="0f1b9-134">Cuando se realizan operaciones de índice en línea, se necesita espacio temporal en disco adicional.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-134">When you perform index operations online, additional temporary disk space is required.</span></span>  
  
 <span data-ttu-id="0f1b9-135">Cuando se crea un índice clúster, se vuelve a generar o se quita en línea, se crea un índice no clúster temporal para asignar los antiguos marcadores a los nuevos.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-135">If a clustered index is created, rebuilt, or dropped online, a temporary nonclustered index is created to map old bookmarks to new bookmarks.</span></span> <span data-ttu-id="0f1b9-136">Si la opción SORT_IN_TEMPDB está establecida en ON, el índice temporal se crea en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-136">If the SORT_IN_TEMPDB option is set to ON, this temporary index is created in **tempdb**.</span></span> <span data-ttu-id="0f1b9-137">Si SORT_IN_TEMPDB está establecida en OFF, se utiliza el mismo grupo de archivos o esquema de particiones que el índice de destino.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-137">If SORT_IN_TEMPDB is set to OFF, the same filegroup or partition scheme as the target index is used.</span></span> <span data-ttu-id="0f1b9-138">El índice de asignación temporal contiene un registro para cada fila de la tabla y su contenido es la unión de las columnas de marcadores antiguos y nuevos, que incluye los identificadores únicos y los identificadores de registro, y solo una copia única de cualquier columna que se utilice en ambos marcadores.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-138">The temporary mapping index contains one record for each row in the table, and its contents is the union of the old and new bookmark columns, including uniqueifiers and record identifiers and including only a single copy of any column used in both bookmarks.</span></span> <span data-ttu-id="0f1b9-139">Para obtener más información sobre las operaciones de índices en línea, vea [Realizar operaciones de índice en línea](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="0f1b9-139">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f1b9-140">La opción SORT_IN_TEMPDB no se puede establecer para instrucciones DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-140">The SORT_IN_TEMPDB option cannot be set for DROP INDEX statements.</span></span> <span data-ttu-id="0f1b9-141">El índice de asignación temporal se crea siempre en el mismo grupo de archivos o esquema de particiones que el índice de destino.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-141">The temporary mapping index is always created in the same filegroup or partition scheme as the target index.</span></span>  
  
 <span data-ttu-id="0f1b9-142">Las operaciones de índice en línea utilizan versiones de fila para aislar la operación de índice de los efectos de modificaciones efectuadas por otras transacciones.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-142">Online index operations use row versioning to isolate the index operation from the effects of modifications made by other transactions.</span></span> <span data-ttu-id="0f1b9-143">Así se evita la necesidad de solicitar que se compartan bloqueos en filas que se han leído.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-143">This avoids the need for requesting share locks on rows that have been read.</span></span> <span data-ttu-id="0f1b9-144">Las operaciones simultáneas de eliminación y actualización de usuarios durante las operaciones de índice en línea requieren espacio para registros de versión en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0f1b9-144">Concurrent user update and delete operations during online index operations require space for version records in **tempdb**.</span></span> <span data-ttu-id="0f1b9-145">Para obtener más información, vea [Realizar operaciones de índice en línea](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="0f1b9-145">For more information, see [Perform Index Operations Online](perform-index-operations-online.md) .</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0f1b9-146">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0f1b9-146">Related Tasks</span></span>  
 [<span data-ttu-id="0f1b9-147">Ejemplo de espacio en disco del índice</span><span class="sxs-lookup"><span data-stu-id="0f1b9-147">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
 [<span data-ttu-id="0f1b9-148">Espacio en disco del registro de transacciones para operaciones de índice</span><span class="sxs-lookup"><span data-stu-id="0f1b9-148">Transaction Log Disk Space for Index Operations</span></span>](transaction-log-disk-space-for-index-operations.md)  
  
 [<span data-ttu-id="0f1b9-149">Calcular el tamaño de una tabla</span><span class="sxs-lookup"><span data-stu-id="0f1b9-149">Estimate the Size of a Table</span></span>](../databases/estimate-the-size-of-a-table.md)  
  
 [<span data-ttu-id="0f1b9-150">Estimar el tamaño de un índice clúster</span><span class="sxs-lookup"><span data-stu-id="0f1b9-150">Estimate the Size of a Clustered Index</span></span>](../databases/estimate-the-size-of-a-clustered-index.md)  
  
 [<span data-ttu-id="0f1b9-151">Estimar el tamaño de un índice no clúster</span><span class="sxs-lookup"><span data-stu-id="0f1b9-151">Estimate the Size of a Nonclustered Index</span></span>](../databases/estimate-the-size-of-a-nonclustered-index.md)  
  
 [<span data-ttu-id="0f1b9-152">Estimar el tamaño de un montón</span><span class="sxs-lookup"><span data-stu-id="0f1b9-152">Estimate the Size of a Heap</span></span>](../databases/estimate-the-size-of-a-heap.md)  
  
## <a name="related-content"></a><span data-ttu-id="0f1b9-153">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0f1b9-153">Related Content</span></span>  
 [<span data-ttu-id="0f1b9-154">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f1b9-154">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="0f1b9-155">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f1b9-155">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
 [<span data-ttu-id="0f1b9-156">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f1b9-156">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="0f1b9-157">Especificar el factor de relleno para un índice</span><span class="sxs-lookup"><span data-stu-id="0f1b9-157">Specify Fill Factor for an Index</span></span>](specify-fill-factor-for-an-index.md)  
  
 [<span data-ttu-id="0f1b9-158">Reorganizar y volver a generar índices</span><span class="sxs-lookup"><span data-stu-id="0f1b9-158">Reorganize and Rebuild Indexes</span></span>](indexes.md)  
  
  
