---
title: Deshabilitar índices y restricciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.disableindexes.f1
helpviewer_keywords:
- disabled indexes [SQL Server], index operations
- nonclustered indexes [SQL Server], disabling
- disabled indexes [SQL Server], guidelines
- clustered indexes, disabling
- constraints [SQL Server], disabling
- disabled indexes [SQL Server], viewing
- FOREIGN KEY constraints, disabling
- statistical information [SQL Server], indexes
- index disabling [SQL Server]
- indexed views [SQL Server], disabled indexes
ms.assetid: 2198f1af-fa44-47e9-92df-f4fde322ba18
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 40f9de4108be4defeb2353a9e7835c289641a819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749822"
---
# <a name="disable-indexes-and-constraints"></a><span data-ttu-id="dd1c0-102">Deshabilitar índices y restricciones</span><span class="sxs-lookup"><span data-stu-id="dd1c0-102">Disable Indexes and Constraints</span></span>
  <span data-ttu-id="dd1c0-103">En este tema se describe cómo deshabilitar un índice o restricciones en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd1c0-103">This topic describes how to disable an index or constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dd1c0-104">Al deshabilitar un índice, se impide que el usuario pueda tener acceso al mismo y, en el caso de los índices clúster, a los datos de la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-104">Disabling an index prevents user access to the index, and for clustered indexes to the underlying table data.</span></span> <span data-ttu-id="dd1c0-105">La definición del índice se conserva en los metadatos y las estadísticas de índice se mantienen en índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-105">The index definition remains in metadata, and index statistics are kept on nonclustered indexes.</span></span> <span data-ttu-id="dd1c0-106">La deshabilitación de un índice clúster o no clúster en una vista elimina físicamente los datos del índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-106">Disabling a nonclustered or clustered index on a view physically deletes the index data.</span></span> <span data-ttu-id="dd1c0-107">Al deshabilitar un índice clúster en una tabla, se impide el acceso a los datos, que siguen en la tabla pero dejan de estar disponibles para las operaciones de lenguaje de manipulación de datos (DML) hasta que se quite o recompile el índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-107">Disabling a clustered index on a table prevents access to the data; the data still remains in the table, but is unavailable for data manipulation language (DML) operations until the index is dropped or rebuilt.</span></span>  
  
 <span data-ttu-id="dd1c0-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dd1c0-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dd1c0-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="dd1c0-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dd1c0-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="dd1c0-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dd1c0-112">**Para deshabilitar un índice, use:**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-112">**To disable an index, using:**</span></span>  
  
     [<span data-ttu-id="dd1c0-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd1c0-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dd1c0-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd1c0-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dd1c0-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="dd1c0-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dd1c0-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="dd1c0-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="dd1c0-117">El índice no se mantiene mientras está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-117">The index is not maintained while it is disabled.</span></span>  
  
-   <span data-ttu-id="dd1c0-118">El optimizador de consultas no tiene en cuenta el índice deshabilitado a la hora de crear planes de ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-118">The query optimizer does not consider the disabled index when creating query execution plans.</span></span> <span data-ttu-id="dd1c0-119">Además, las consultas que hacen referencia al índice deshabilitado con una sugerencia de tabla generan un error.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-119">Also, queries that reference the disabled index with a table hint fail.</span></span>  
  
-   <span data-ttu-id="dd1c0-120">No puede crear un índice que use el mismo nombre que un índice existente deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-120">You cannot create an index that uses the same name as an existing disabled index.</span></span>  
  
-   <span data-ttu-id="dd1c0-121">Se puede quitar un índice deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-121">A disabled index can be dropped.</span></span>  
  
-   <span data-ttu-id="dd1c0-122">Al deshabilitar un índice único, también se deshabilitan la restricción PRIMARY KEY o UNIQUE y todas las restricciones FOREIGN KEY que hacen referencia a las columnas indizadas de otras tablas.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-122">When disabling a unique index, the PRIMARY KEY or UNIQUE constraint and all FOREIGN KEY constraints that reference the indexed columns from other tables are also disabled.</span></span> <span data-ttu-id="dd1c0-123">Al deshabilitar un índice clúster, se deshabilitan también todas las restricciones FOREIGN KEY entrantes y salientes de la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-123">When disabling a clustered index, all incoming and outgoing FOREIGN KEY constraints on the underlying table are also disabled.</span></span> <span data-ttu-id="dd1c0-124">Los nombres de las restricciones se enumeran en un mensaje de advertencia cuando se deshabilita el índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-124">The constraint names are listed in a warning message when the index is disabled.</span></span> <span data-ttu-id="dd1c0-125">Después de recompilar el índice, se deben habilitar todas las restricciones manualmente mediante la instrucción ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-125">After rebuilding the index, all constraints must be manually enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="dd1c0-126">Los índices no clúster se deshabilitan automáticamente cuando se deshabilita el índice clúster asociado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-126">Nonclustered indexes are automatically disabled when the associated clustered index is disabled.</span></span> <span data-ttu-id="dd1c0-127">No se pueden habilitar hasta que se habilita el índice clúster en la tabla o vista, o bien hasta que se quita el índice clúster en la tabla.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-127">They cannot be enabled until either the clustered index on the table or view is enabled or the clustered index on the table is dropped.</span></span> <span data-ttu-id="dd1c0-128">Los índices no clúster deben habilitarse de forma explícita, a no ser que el índice clúster se haya habilitado mediante la instrucción ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-128">Nonclustered indexes must be explicitly enabled, unless the clustered index was enabled by using the ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="dd1c0-129">La instrucción ALTER INDEX ALL REBUILD vuelve a generar y habilita todos los índices deshabilitados de la tabla, excepto los índices deshabilitados en las vistas.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-129">The ALTER INDEX ALL REBUILD statement rebuilds and enables all disabled indexes on the table, except for disabled indexes on views.</span></span> <span data-ttu-id="dd1c0-130">Los índices en las vistas deben habilitarse en una instrucción ALTER INDEX ALL REBUILD independiente.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-130">Indexes on views must be enabled in a separate ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="dd1c0-131">Al deshabilitar un índice clúster en una tabla también se deshabilitan todos los índices clúster y no clúster en las vistas que hacen referencia a esa tabla.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-131">Disabling a clustered index on a table also disables all clustered and nonclustered indexes on views that reference that table.</span></span> <span data-ttu-id="dd1c0-132">Estos índices deben volverse a generar como los de la tabla a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-132">These indexes must be rebuilt just as those on the referenced table.</span></span>  
  
-   <span data-ttu-id="dd1c0-133">No se puede tener acceso a las filas de datos del índice clúster deshabilitado excepto para quitar o volver a generar el índice clúster.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-133">The data rows of the disabled clustered index cannot be accessed except to drop or rebuild the clustered index.</span></span>  
  
-   <span data-ttu-id="dd1c0-134">Se puede recompilar un índice no clúster deshabilitado en línea cuando la tabla no tenga un índice clúster deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-134">You can rebuild a disabled nonclustered index online when the table does not have a disabled clustered index.</span></span> <span data-ttu-id="dd1c0-135">Sin embargo, siempre debe volver a generar un índice clúster deshabilitado sin conexión si utiliza la instrucción ALTER INDEX REBUILD o CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-135">However, you must always rebuild a disabled clustered index offline if you use either the ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING statement.</span></span> <span data-ttu-id="dd1c0-136">Para obtener más información sobre las operaciones de índices en línea, vea [Realizar operaciones de índice en línea](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="dd1c0-136">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="dd1c0-137">La instrucción CREATE STATISTICS no se puede ejecutar correctamente en una tabla que tenga un índice clúster deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-137">The CREATE STATISTICS statement cannot be successfully executed on a table that has a disabled clustered index.</span></span>  
  
-   <span data-ttu-id="dd1c0-138">La opción de base de datos AUTO_CREATE_STATISTICS crea estadísticas en una columna cuando el índice está deshabilitado y existen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd1c0-138">The AUTO_CREATE_STATISTICS database option creates new statistics on a column when the index is disabled and the following conditions exist:</span></span>  
  
    -   <span data-ttu-id="dd1c0-139">AUTO_CREATE_STATISTICS está establecido en ON.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-139">AUTO_CREATE_STATISTICS is set to ON</span></span>  
  
    -   <span data-ttu-id="dd1c0-140">No hay estadísticas existentes para la columna.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-140">There are no existing statistics for the column.</span></span>  
  
    -   <span data-ttu-id="dd1c0-141">Las estadísticas son obligatorias durante la optimización de consultas.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-141">Statistics are required during query optimization.</span></span>  
  
-   <span data-ttu-id="dd1c0-142">Si un índice clúster está deshabilitado, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no puede devolver información acerca de la tabla subyacente; en su lugar, la instrucción indica que el índice clúster está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-142">If a clustered index is disabled, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) cannot return information about the underlying table; instead, the statement reports that the clustered index is disabled.</span></span> <span data-ttu-id="dd1c0-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) no se puede usar para desfragmentar un índice deshabilitado; la instrucción genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) cannot be used to defragment a disabled index; the statement fails with an error message.</span></span> <span data-ttu-id="dd1c0-144">Puede usar [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) para recompilar un índice deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-144">You can use [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) to rebuild a disabled index.</span></span>  
  
-   <span data-ttu-id="dd1c0-145">Al crear un nuevo índice clúster se habilitan los índices no clúster deshabilitados previamente.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-145">Creating a new clustered index enables previously disabled nonclustered indexes.</span></span> <span data-ttu-id="dd1c0-146">Para obtener más información, consulte [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="dd1c0-146">For more information, see [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dd1c0-147">Seguridad</span><span class="sxs-lookup"><span data-stu-id="dd1c0-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dd1c0-148">Permisos</span><span class="sxs-lookup"><span data-stu-id="dd1c0-148">Permissions</span></span>  
 <span data-ttu-id="dd1c0-149">Para ejecutar ALTER INDEX, se necesita, como mínimo, el permiso ALTER en la tabla o en la vista.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-149">To execute ALTER INDEX, at a minimum, ALTER permission on the table or view is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dd1c0-150">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd1c0-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="dd1c0-151">Para deshabilitar un índice</span><span class="sxs-lookup"><span data-stu-id="dd1c0-151">To disable an index</span></span>  
  
1.  <span data-ttu-id="dd1c0-152">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea deshabilitar un índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable an index.</span></span>  
  
2.  <span data-ttu-id="dd1c0-153">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="dd1c0-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="dd1c0-154">Haga clic en el signo más para expandir la tabla en la que desea deshabilitar un índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-154">Click the plus sign to expand the table on which you want to disable an index.</span></span>  
  
4.  <span data-ttu-id="dd1c0-155">Haga clic en el signo más para expandir la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="dd1c0-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="dd1c0-156">Haga clic con el botón derecho en el índice que quiera deshabilitar y seleccione **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-156">Right-click the index you want to disable and select **Disable**.</span></span>  
  
6.  <span data-ttu-id="dd1c0-157">En el cuadro de diálogo **Deshabilitar índices** , compruebe que el índice correcto se encuentra en la cuadrícula **Índices que va a deshabilitar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-157">In the **Disable Indexes** dialog box, verify that the correct index is in the **Indexes to disable** grid and click **OK**.</span></span>  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="dd1c0-158">Para deshabilitar todos los índices de una tabla</span><span class="sxs-lookup"><span data-stu-id="dd1c0-158">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="dd1c0-159">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea deshabilitar los índices.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-159">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable the indexes.</span></span>  
  
2.  <span data-ttu-id="dd1c0-160">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="dd1c0-160">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="dd1c0-161">Haga clic en el signo más para expandir la tabla en la que desea deshabilitar los índices.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-161">Click the plus sign to expand the table on which you want to disable the indexes.</span></span>  
  
4.  <span data-ttu-id="dd1c0-162">Haga clic con el botón derecho en la carpeta **Índices** y seleccione **Deshabilitar todo**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-162">Right-click the **Indexes** folder and select **Disable All**.</span></span>  
  
5.  <span data-ttu-id="dd1c0-163">En el cuadro de diálogo **Deshabilitar índices** , compruebe que los índices correctos se encuentran en la cuadrícula **Índices que va a deshabilitar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-163">In the **Disable Indexes** dialog box, verify that the correct indexes are in the **Indexes to disable** grid and click **OK**.</span></span> <span data-ttu-id="dd1c0-164">Para quitar un índice de la cuadrícula **Índices que va a deshabilitar** , seleccione el índice y, a continuación, presione la tecla SUPRIMIR.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-164">To remove an index from the **Indexes to disable** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="dd1c0-165">La siguiente información está disponible en el cuadro de diálogo **Deshabilitar índices** :</span><span class="sxs-lookup"><span data-stu-id="dd1c0-165">The following information is available in the **Disable Indexes** dialog box:</span></span>  
  
 <span data-ttu-id="dd1c0-166">**Nombre de índice**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-166">**Index Name**</span></span>  
 <span data-ttu-id="dd1c0-167">Muestra el nombre del índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-167">Displays the name of the index.</span></span> <span data-ttu-id="dd1c0-168">Durante la ejecución, esta columna también muestra un icono que representa el estado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-168">During execution, this column also displays an icon representing the status.</span></span>  
  
 <span data-ttu-id="dd1c0-169">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-169">**Table Name**</span></span>  
 <span data-ttu-id="dd1c0-170">Muestra el nombre de la tabla o vista en la que se ha creado el índice.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-170">Displays the name of the table or view that the index was created on.</span></span>  
  
 <span data-ttu-id="dd1c0-171">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-171">**Index Type**</span></span>  
 <span data-ttu-id="dd1c0-172">Muestra el tipo de índice: **Agrupado**, **No agrupado**, **Espacial**o **XML**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-172">Displays the type of the index: **Clustered**, **Nonclustered**, **Spatial**, or **XML**.</span></span>  
  
 <span data-ttu-id="dd1c0-173">**Estado**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-173">**Status**</span></span>  
 <span data-ttu-id="dd1c0-174">Muestra el estado de la operación de deshabilitación.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-174">Displays the status of the disable operation.</span></span> <span data-ttu-id="dd1c0-175">Los valores posibles tras la ejecución son:</span><span class="sxs-lookup"><span data-stu-id="dd1c0-175">Possible values after execution are:</span></span>  
  
-   <span data-ttu-id="dd1c0-176">En blanco</span><span class="sxs-lookup"><span data-stu-id="dd1c0-176">Blank</span></span>  
  
     <span data-ttu-id="dd1c0-177">Antes de la ejecución, el **Estado** permanece en blanco.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-177">Prior to execution **Status** is blank.</span></span>  
  
-   <span data-ttu-id="dd1c0-178">**En curso**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-178">**In progress**</span></span>  
  
     <span data-ttu-id="dd1c0-179">La deshabilitación de los índices se ha iniciado, pero no ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-179">Disabling of the indexes has been started but is not complete.</span></span>  
  
-   <span data-ttu-id="dd1c0-180">**Success**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-180">**Success**</span></span>  
  
     <span data-ttu-id="dd1c0-181">La operación de deshabilitación ha finalizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-181">The disable operation completed successfully.</span></span>  
  
-   <span data-ttu-id="dd1c0-182">**Error**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-182">**Error**</span></span>  
  
     <span data-ttu-id="dd1c0-183">Se ha encontrado un error durante la operación de deshabilitación de índices; la operación no ha finalizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-183">An error was encountered during the index disable operation, and the operation did not complete successfully.</span></span>  
  
-   <span data-ttu-id="dd1c0-184">**Stopped**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-184">**Stopped**</span></span>  
  
     <span data-ttu-id="dd1c0-185">La deshabilitación del índice no ha finalizado correctamente porque el usuario ha detenido la operación.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-185">The disable of the index was not completed successfully because the user stopped the operation.</span></span>  
  
 <span data-ttu-id="dd1c0-186">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="dd1c0-186">**Message**</span></span>  
 <span data-ttu-id="dd1c0-187">Proporciona el texto de los mensajes de error durante la operación de deshabilitación.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-187">Provides the text of error messages during the disable operation.</span></span> <span data-ttu-id="dd1c0-188">Durante la ejecución, los errores aparecen como hipervínculos.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-188">During execution, errors appear as hyperlinks.</span></span> <span data-ttu-id="dd1c0-189">El texto de los hipervínculos describe el cuerpo del error.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-189">The text of the hyperlinks describes the body of the error.</span></span> <span data-ttu-id="dd1c0-190">La columna **Mensaje** pocas veces es lo suficientemente ancha para poder leer el texto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-190">The **Message** column is rarely wide enough to read the full message text.</span></span> <span data-ttu-id="dd1c0-191">Hay dos maneras de leer el texto completo:</span><span class="sxs-lookup"><span data-stu-id="dd1c0-191">There are two ways to get the full text:</span></span>  
  
-   <span data-ttu-id="dd1c0-192">Mueva el puntero sobre la celda del mensaje para que aparezca la información sobre herramientas con el texto de error.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-192">Move the mouse pointer over the message cell to display a ToolTip with the error text.</span></span>  
  
-   <span data-ttu-id="dd1c0-193">Haga clic en el hipervínculo para mostrar un cuadro de diálogo con el error completo.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-193">Click the hyperlink to display a dialog box displaying the full error.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dd1c0-194">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd1c0-194">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="dd1c0-195">Para deshabilitar un índice</span><span class="sxs-lookup"><span data-stu-id="dd1c0-195">To disable an index</span></span>  
  
1.  <span data-ttu-id="dd1c0-196">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd1c0-196">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd1c0-197">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-197">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dd1c0-198">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-198">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- disables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    DISABLE;  
    ```  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="dd1c0-199">Para deshabilitar todos los índices de una tabla</span><span class="sxs-lookup"><span data-stu-id="dd1c0-199">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="dd1c0-200">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd1c0-200">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd1c0-201">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-201">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dd1c0-202">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dd1c0-202">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Disables all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    DISABLE;  
    ```  
  
 <span data-ttu-id="dd1c0-203">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dd1c0-203">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
