---
title: Creación, modificación y eliminación de índices espaciales | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], creating
- spatial indexes [SQL Server], dropping
- spatial indexes [SQL Server], creating
- indexes [SQL Server], dropping
- indexes [SQL Server], modifying
- spatial indexes [SQL Server], modifying
ms.assetid: 00c1b927-8ec5-44cf-87c2-c8de59745735
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 88de17e8c487d9a965f2e236edac064dc2fe4c7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663324"
---
# <a name="create-modify-and-drop-spatial-indexes"></a><span data-ttu-id="ff933-102">Crear, modificar y quitar índices espaciales</span><span class="sxs-lookup"><span data-stu-id="ff933-102">Create, Modify, and Drop Spatial Indexes</span></span>
  <span data-ttu-id="ff933-103">Un índice espacial puede realizar determinadas operaciones de manera más eficaz en una columna `geometry` de `geography` tipo de datos o (una *columna espacial*).</span><span class="sxs-lookup"><span data-stu-id="ff933-103">A spatial index can more efficiently perform certain operations on a column of the `geometry` or `geography` data type (a *spatial column*).</span></span> <span data-ttu-id="ff933-104">Se puede especificar más de un índice espacial en una columna espacial.</span><span class="sxs-lookup"><span data-stu-id="ff933-104">More than one spatial index can be specified on a spatial column.</span></span> <span data-ttu-id="ff933-105">Por ejemplo, esto es útil para indizar diferentes parámetros de teselación en una columna única.</span><span class="sxs-lookup"><span data-stu-id="ff933-105">This is useful, for example, for indexing different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="ff933-106">Existen varias restricciones para la creación de índices espaciales.</span><span class="sxs-lookup"><span data-stu-id="ff933-106">There are a number of restrictions on creating spatial indexes.</span></span> <span data-ttu-id="ff933-107">Para obtener más información, vea [Restricciones en los índices espaciales](#restrictions) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="ff933-107">For more information, see [Restrictions on Spatial Indexes](#restrictions) in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff933-108">Para obtener más información sobre la relación de índices espaciales para partición y para grupos de archivos, vea la sección "Comentarios" en [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ff933-108">For information about the relationship of spatial indexes to partition and to filegroups, see the "Remarks" section in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
##  <a name="creating-modifying-and-dropping-spatial-indexes"></a><a name="creating"></a> <span data-ttu-id="ff933-109">Crear, modificar y quitar índices espaciales</span><span class="sxs-lookup"><span data-stu-id="ff933-109">Creating, Modifying, and Dropping Spatial Indexes</span></span>  
  
###  <a name="to-create-a-spatial-index"></a><a name="create"></a> <span data-ttu-id="ff933-110">Para crear un índice espacial</span><span class="sxs-lookup"><span data-stu-id="ff933-110">To create a spatial index</span></span>  
 <span data-ttu-id="ff933-111">**Para crear un índice espacial mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ff933-111">**To create a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="ff933-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ff933-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-spatial-index-transact-sql)  
  
 <span data-ttu-id="ff933-113">**Para crear un índice espacial mediante el cuadro de diálogo Nuevo índice en Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ff933-113">**To create a spatial index by using the New Index dialog box in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-management-studio"></a><span data-ttu-id="ff933-114">Para crear un índice espacial en Management Studio</span><span class="sxs-lookup"><span data-stu-id="ff933-114">To create a spatial index in Management Studio</span></span>  
  
1.  <span data-ttu-id="ff933-115">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="ff933-115">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ff933-116">Expanda **Bases de datos**, a continuación, la base de datos que contiene la tabla con el índice especificado y, por último, **Tablas**.</span><span class="sxs-lookup"><span data-stu-id="ff933-116">Expand **Databases**, expand the database that contains the table with the specified index, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="ff933-117">Expanda la tabla para la que desee crear el índice.</span><span class="sxs-lookup"><span data-stu-id="ff933-117">Expand the table for which you want to create the index.</span></span>  
  
4.  <span data-ttu-id="ff933-118">Haga clic con el botón derecho en **Índices** y seleccione **Nuevo índice**.</span><span class="sxs-lookup"><span data-stu-id="ff933-118">Right-click **Indexes** and select **New Index**.</span></span>  
  
5.  <span data-ttu-id="ff933-119">En el campo **Nombre de índice** , escriba un nombre para el índice.</span><span class="sxs-lookup"><span data-stu-id="ff933-119">In the **Index name** field, enter a name for the index.</span></span>  
  
6.  <span data-ttu-id="ff933-120">En la lista desplegable **Tipo de índice** , seleccione **Espacial**.</span><span class="sxs-lookup"><span data-stu-id="ff933-120">In the **Index type** drop-down list, select **Spatial**.</span></span>  
  
7.  <span data-ttu-id="ff933-121">Para especificar la columna espacial que desee indizar, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ff933-121">To specify the spatial column that you want to index, click **Add**.</span></span>  
  
8.  <span data-ttu-id="ff933-122">En el cuadro de diálogo **seleccionar columnas de** *\<table name>* , seleccione una columna de tipo `geometry` o Active `geography` la casilla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ff933-122">In the **Select Columns from** *\<table name>* dialog box, select a column of type `geometry` or `geography` by selecting the corresponding check box.</span></span> <span data-ttu-id="ff933-123">Las demás columnas espaciales se convierten en no editables.</span><span class="sxs-lookup"><span data-stu-id="ff933-123">Any other spatial columns then become uneditable.</span></span> <span data-ttu-id="ff933-124">Si desea seleccionar una columna espacial diferente, primero debe borrar la columna actualmente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff933-124">If you want to select a different spatial column, you must first clear the currently selected column.</span></span> <span data-ttu-id="ff933-125">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff933-125">When finished, click **OK**.</span></span>  
  
9. <span data-ttu-id="ff933-126">Compruebe su selección de columna en la cuadrícula **Columnas de clave de índice** .</span><span class="sxs-lookup"><span data-stu-id="ff933-126">Verify your column selection in the **Index key columns** grid.</span></span>  
  
10. <span data-ttu-id="ff933-127">En el panel **Seleccionar una página** del cuadro de diálogo **Propiedades del índice** , haga clic en **Espacial**.</span><span class="sxs-lookup"><span data-stu-id="ff933-127">In the **Select a page** pane of the **Index Properties** dialog box, click **Spatial**.</span></span>  
  
11. <span data-ttu-id="ff933-128">En la página **Espacial** , especifique los valores que desee usar para las propiedades espaciales del índice.</span><span class="sxs-lookup"><span data-stu-id="ff933-128">On the **Spatial** page, specify the values that you want to use for the spatial properties of the index.</span></span>  
  
     <span data-ttu-id="ff933-129">Al crear un índice en una `geometry` columna de tipo, debe especificar las coordenadas **( *`X-min`* , *`Y-min`* )** y **( *`X-max`* , *`Y-max`* )** del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ff933-129">When creating an index on a `geometry` type column, you must specify the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="ff933-130">En el caso de un índice en una `geography` columna de tipo, los campos de cuadro de límite pasan a ser de solo lectura después de especificar el esquema de teselación de **cuadrícula de geografía** , ya que la teselación de cuadrícula de geografía no usa un cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="ff933-130">For an index on a `geography` type column, the bounding-box fields become read-only after you specify the **Geography grid** tessellation scheme, because geography grid tessellation does not use a bounding box.</span></span>  
  
     <span data-ttu-id="ff933-131">Opcionalmente, puede especificar valores no predeterminados para el campo **Celdas por objeto** y para la densidad de cuadrícula en cualquier nivel del esquema de teselación.</span><span class="sxs-lookup"><span data-stu-id="ff933-131">Optionally, you can specify nondefault values for the **Cells Per Object** field and for the grid density at any level of the tessellation scheme.</span></span> <span data-ttu-id="ff933-132">El número predeterminado de celdas por objeto es 16 para [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] u 8 para [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] o posterior y la densidad de cuadrícula predeterminada es **Media** para [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff933-132">The default number of cells per object is 16 for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or 8 for [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] or higher, and the default grid density is **Medium** for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span>  
  
     <span data-ttu-id="ff933-133">Puede seleccionar GEOMETRY_AUTO_GRID o GEOGRAPHY_AUTO_GRID para el esquema de teselación en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff933-133">You can select GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID for tessellation scheme in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ff933-134">Cuando se seleccionan GEOMETRY_AUTO_GRID o GEOGRAPHY_AUTO_GRID, se deshabilitan las opciones de densidad de cuadrícula Nivel 1, Nivel 2, Nivel 3 Nivel 4.</span><span class="sxs-lookup"><span data-stu-id="ff933-134">When GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID is selected, then Level 1, Level 2, Level 3, and Level 4 grid density options are disabled.</span></span>  
  
     <span data-ttu-id="ff933-135">Para obtener más información acerca de estas propiedades, vea [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="ff933-135">For more information about these properties, see [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span></span>  
  
12. <span data-ttu-id="ff933-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff933-136">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff933-137">Para crear otro índice espacial en la misma columna o en otra columna espacial diferente, repita los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="ff933-137">To create another spatial index on the same or a different spatial column, repeat the preceding steps.</span></span>  
  
  
 <span data-ttu-id="ff933-138">**Para crear un índice espacial mediante el Diseñador de tablas en Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ff933-138">**To create a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-table-designer"></a><span data-ttu-id="ff933-139">Para crear un índice espacial en el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="ff933-139">To create a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="ff933-140">En el Explorador de objetos, haga clic con el botón derecho en la tabla para la que quiere crear un índice espacial y luego haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="ff933-140">In Object Explorer, right-click the table for which you want to create a spatial index, and then click **Design**.</span></span>  
  
     <span data-ttu-id="ff933-141">La tabla se abre en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="ff933-141">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="ff933-142">Seleccione una columna `geometry` o `geography` para el índice.</span><span class="sxs-lookup"><span data-stu-id="ff933-142">Select a `geometry` or `geography` column for the index.</span></span>  
  
3.  <span data-ttu-id="ff933-143">En el menú **Diseñador de tablas** , haga clic en **Índice espacial**.</span><span class="sxs-lookup"><span data-stu-id="ff933-143">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
4.  <span data-ttu-id="ff933-144">En el cuadro de diálogo **Índices espaciales** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ff933-144">In the **Spatial Indexes** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="ff933-145">Seleccione el nuevo índice en la lista **Índice espacial seleccionado** y configure las propiedades del índice espacial en la cuadrícula de la derecha.</span><span class="sxs-lookup"><span data-stu-id="ff933-145">Select the new index in the **Selected Spatial Index** list, and in the grid to the right, set the properties for the spatial index.</span></span> <span data-ttu-id="ff933-146">Para obtener información sobre las propiedades, vea [Cuadro de diálogo Índices espaciales &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ff933-146">For information about the properties, see [Spatial Indexes Dialog Box &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
  
###  <a name="to-alter-a-spatial-index"></a><a name="alter"></a> <span data-ttu-id="ff933-147">Para modificar un índice espacial</span><span class="sxs-lookup"><span data-stu-id="ff933-147">To alter a spatial index</span></span>  
  
-   [<span data-ttu-id="ff933-148">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ff933-148">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ff933-149">Para cambiar opciones específicas de un índice espacial, como BOUNDING_BOX o GRID, puede usar una instrucción CREATE SPATIAL INDEX que especifica DROP_EXISTING = ON, o quitar el índice espacial y crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="ff933-149">To change options that are specific to a spatial index, such as BOUNDING_BOX or GRID, you can either use a CREATE SPATIAL INDEX statement that specifies DROP_EXISTING = ON, or drop the spatial index and create a new one.</span></span> <span data-ttu-id="ff933-150">Para ver un ejemplo, consulte [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ff933-150">For an example, see [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
-   [<span data-ttu-id="ff933-151">Modificar un índice</span><span class="sxs-lookup"><span data-stu-id="ff933-151">Modify an Index</span></span>](../indexes/modify-an-index.md)  
  
-   [<span data-ttu-id="ff933-152">Mover un índice existente a un grupo de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="ff933-152">Move an Existing Index to a Different Filegroup</span></span>](../indexes/move-an-existing-index-to-a-different-filegroup.md)  
  
  
###  <a name="to-drop-a-spatial-index"></a><a name="drop"></a> <span data-ttu-id="ff933-153">Para quitar un índice espacial</span><span class="sxs-lookup"><span data-stu-id="ff933-153">To drop a spatial index</span></span>  
 <span data-ttu-id="ff933-154">**Para quitar un índice espacial mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ff933-154">**To drop a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="ff933-155">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ff933-155">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 <span data-ttu-id="ff933-156">**Para quitar un índice mediante Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ff933-156">**To drop an index by using Management Studio**</span></span>  
 [<span data-ttu-id="ff933-157">Eliminar un índice</span><span class="sxs-lookup"><span data-stu-id="ff933-157">Delete an Index</span></span>](../indexes/delete-an-index.md)  
  
 <span data-ttu-id="ff933-158">**Para quitar un índice espacial mediante el Diseñador de tablas en Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ff933-158">**To drop a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-drop-a-spatial-index-in-table-designer"></a><span data-ttu-id="ff933-159">Para quitar un índice espacial en el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="ff933-159">To drop a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="ff933-160">En el Explorador de objetos, haga clic con el botón derecho en la tabla cuyo índice espacial quiere eliminar y elija **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="ff933-160">In Object Explorer, right-click the table with the spatial index you want to delete and click **Design**.</span></span>  
  
     <span data-ttu-id="ff933-161">La tabla se abre en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="ff933-161">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="ff933-162">En el menú **Diseñador de tablas** , haga clic en **Índice espacial**.</span><span class="sxs-lookup"><span data-stu-id="ff933-162">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
     <span data-ttu-id="ff933-163">Se abrirá el cuadro de diálogo **Índice espacial** .</span><span class="sxs-lookup"><span data-stu-id="ff933-163">The **Spatial Index** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ff933-164">Haga clic en el índice que desee eliminar en la columna **Índice espacial seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="ff933-164">Click the index you want to delete in the **Selected Spatial Index** column.</span></span>  
  
4.  <span data-ttu-id="ff933-165">Haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ff933-165">Click **Delete**.</span></span>  
  
  
##  <a name="restrictions-on-spatial-indexes"></a><a name="restrictions"></a> <span data-ttu-id="ff933-166">Restricciones en los índices espaciales</span><span class="sxs-lookup"><span data-stu-id="ff933-166">Restrictions on Spatial Indexes</span></span>  
 <span data-ttu-id="ff933-167">Un índice espacial solamente puede crearse en una columna de tipo `geometry` o `geography`.</span><span class="sxs-lookup"><span data-stu-id="ff933-167">A spatial index can be created only on a column of type `geometry` or `geography`.</span></span>  
  
### <a name="table-and-view-restrictions"></a><span data-ttu-id="ff933-168">Restricciones de las vistas y tablas</span><span class="sxs-lookup"><span data-stu-id="ff933-168">Table and View Restrictions</span></span>  
 <span data-ttu-id="ff933-169">Los índices espaciales solo se pueden definir en una tabla que tenga una clave principal.</span><span class="sxs-lookup"><span data-stu-id="ff933-169">Spatial indexes can be defined only on a table that has a primary key.</span></span> <span data-ttu-id="ff933-170">El número máximo de columnas de clave principal en la tabla es de 15.</span><span class="sxs-lookup"><span data-stu-id="ff933-170">The maximum number of primary key columns on the table is 15.</span></span>  
  
 <span data-ttu-id="ff933-171">El tamaño máximo de los registros de clave de índice es 895 bytes.</span><span class="sxs-lookup"><span data-stu-id="ff933-171">The maximum size of index key records is 895 bytes.</span></span> <span data-ttu-id="ff933-172">Los tamaños mayores producen un error.</span><span class="sxs-lookup"><span data-stu-id="ff933-172">Larger sizes raise an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff933-173">No se pueden cambiar los metadatos de clave principal mientras un índice espacial está definido en una tabla.</span><span class="sxs-lookup"><span data-stu-id="ff933-173">Primary key metadata cannot be changed while a spatial index is defined on a table.</span></span>  
  
 <span data-ttu-id="ff933-174">Los índices espaciales no se pueden especificar en vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="ff933-174">Spatial indexes cannot be specified on indexed views.</span></span>  
  
### <a name="multiple-spatial-index-restrictions"></a><span data-ttu-id="ff933-175">Varias restricciones de los índices espaciales</span><span class="sxs-lookup"><span data-stu-id="ff933-175">Multiple Spatial Index Restrictions</span></span>  
 <span data-ttu-id="ff933-176">Puede crear hasta 249 índices espaciales en cualquiera de las columnas espaciales de una tabla admitida.</span><span class="sxs-lookup"><span data-stu-id="ff933-176">You can create up to 249 spatial indexes on any of the spatial columns in a supported table.</span></span> <span data-ttu-id="ff933-177">Crear más de un índice espacial en la misma columna espacial puede ser útil, por ejemplo, para indizar parámetros de teselación diferentes en una única columna.</span><span class="sxs-lookup"><span data-stu-id="ff933-177">Creating more than one spatial index on the same spatial column can be useful, for example, to index different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="ff933-178">Solo puede crear un índice espacial al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ff933-178">You can create only one spatial index at a time.</span></span>  
  
### <a name="spatial-indexes-and-process-parallelism"></a><span data-ttu-id="ff933-179">Índices espaciales y paralelismo del proceso</span><span class="sxs-lookup"><span data-stu-id="ff933-179">Spatial Indexes and Process Parallelism</span></span>  
 <span data-ttu-id="ff933-180">Una generación de índices puede usar el paralelismo de procesos disponible.</span><span class="sxs-lookup"><span data-stu-id="ff933-180">An index build can use available process parallelism.</span></span>  
  
### <a name="version-restrictions"></a><span data-ttu-id="ff933-181">Restricciones de versión</span><span class="sxs-lookup"><span data-stu-id="ff933-181">Version Restrictions</span></span>  
 <span data-ttu-id="ff933-182">Las teselaciones espaciales incluidas en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] no se pueden replicar en [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ni en [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff933-182">Spatial tessellations introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] cannot be replicated to [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="ff933-183">Debe usar las teselaciones espaciales de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] para los índices espaciales cuando la compatibilidad con versiones anteriores con las bases de datos de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] sea un requisito.</span><span class="sxs-lookup"><span data-stu-id="ff933-183">You must use [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] spatial tessellations for spatial indexes when backward compatibility with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] databases is a requirement.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="ff933-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff933-184">See Also</span></span>  
 [<span data-ttu-id="ff933-185">Información general sobre los índices espaciales</span><span class="sxs-lookup"><span data-stu-id="ff933-185">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
  
  
