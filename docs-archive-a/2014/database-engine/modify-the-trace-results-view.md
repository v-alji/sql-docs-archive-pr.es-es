---
title: Modificar la vista de resultados de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 860a80dc-bac0-4ef0-bf7f-7a9b430d7aa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 050c8f179742cf3cef6473b03f062390caf195f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663654"
---
# <a name="modify-the-trace-results-view"></a><span data-ttu-id="0e325-102">Modificar la vista de resultados del seguimiento</span><span class="sxs-lookup"><span data-stu-id="0e325-102">Modify the Trace Results View</span></span>
  <span data-ttu-id="0e325-103">En este tema se describe cómo modificar la vista de resultados de seguimiento de una sesión de eventos extendidos en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] realizando las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="0e325-103">This topic describes how to modify the trace results view of an Extended Events session in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] by performing the following tasks.</span></span>  
  
1.  [<span data-ttu-id="0e325-104">Agregar o quitar columnas</span><span class="sxs-lookup"><span data-stu-id="0e325-104">Add or Remove Columns</span></span>](#AddRemoveColumns)  
  
2.  [<span data-ttu-id="0e325-105">Crear, modificar o eliminar columnas combinadas</span><span class="sxs-lookup"><span data-stu-id="0e325-105">Create, Edit, or Delete Merged Columns</span></span>](#ChangeColumns)  
  
3.  [<span data-ttu-id="0e325-106">Ordenar los resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-106">Sort the Results</span></span>](#SortResults)  
  
4.  [<span data-ttu-id="0e325-107">Agrupar los resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-107">Group the Results</span></span>](#GroupResults)  
  
5.  [<span data-ttu-id="0e325-108">Agregar los resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-108">Aggregate the Results</span></span>](#AggregateResults)  
  
6.  [<span data-ttu-id="0e325-109">Filtrar los resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-109">Filter the Results</span></span>](#Filter)  
  
7.  [<span data-ttu-id="0e325-110">Buscar texto en columnas</span><span class="sxs-lookup"><span data-stu-id="0e325-110">Search for Text in Columns</span></span>](#Search)  
  
8.  [<span data-ttu-id="0e325-111">Cambiar la configuración de presentación</span><span class="sxs-lookup"><span data-stu-id="0e325-111">Change the Display Settings</span></span>](#ChangeDisplay)  
  
##  <a name="add-or-remove-columns"></a><a name="AddRemoveColumns"></a><span data-ttu-id="0e325-112">Agregar o quitar columnas</span><span class="sxs-lookup"><span data-stu-id="0e325-112">Add or Remove Columns</span></span>  
  
1.  <span data-ttu-id="0e325-113">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-113">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-114"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-114">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-115">En la ventana de resultados de seguimiento, haga clic con el botón secundario del mouse en el encabezado de columna y, a continuación, seleccione **Elegir columnas**.</span><span class="sxs-lookup"><span data-stu-id="0e325-115">In the trace results window, right-click the column header, and then select **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="0e325-116">En el cuadro de diálogo **Elegir columnas** , en la sección **Columnas disponibles** , seleccione los nombres de columna que desea agregar y, a continuación, haga clic en la flecha derecha.</span><span class="sxs-lookup"><span data-stu-id="0e325-116">In the **Choose Columns** dialog box, in the **Available columns** section, select the column names you want to add, and then click the right arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-117">De forma predeterminada, las columnas se organizan por nombre.</span><span class="sxs-lookup"><span data-stu-id="0e325-117">By default, the columns are arranged by name.</span></span> <span data-ttu-id="0e325-118">Para mostrar las columnas por evento, haga clic en **Organizar por evento**.</span><span class="sxs-lookup"><span data-stu-id="0e325-118">To display the columns by event, click **Arrange by event**.</span></span>  
  
     <span data-ttu-id="0e325-119">Para quitar las columnas, en la sección **Columnas seleccionadas** , seleccione las columnas que desea quitar, y haga clic en la flecha izquierda.</span><span class="sxs-lookup"><span data-stu-id="0e325-119">To remove columns, in the **Selected columns** section, select the columns you want to remove, and click the left arrow.</span></span>  
  
4.  <span data-ttu-id="0e325-120">En la sección **Columnas seleccionadas** , para cambiar la presentación del orden de columnas, haga clic en **Subir** o **Bajar** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0e325-120">In the **Selected columns** section, to change the column order display, click **Move Up** or **Move Down** respectively.</span></span> <span data-ttu-id="0e325-121">No puede mover varias filas.</span><span class="sxs-lookup"><span data-stu-id="0e325-121">You cannot move multiple rows.</span></span>  
  
5.  <span data-ttu-id="0e325-122">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e325-122">Click **OK**.</span></span>  
  
##  <a name="create-edit-or-delete-merged-columns"></a><a name="ChangeColumns"></a><span data-ttu-id="0e325-123">Crear, editar o eliminar columnas combinadas</span><span class="sxs-lookup"><span data-stu-id="0e325-123">Create, Edit, or Delete Merged Columns</span></span>  
  
#### <a name="to-create-merged-columns"></a><span data-ttu-id="0e325-124">Para crear columnas combinadas</span><span class="sxs-lookup"><span data-stu-id="0e325-124">To create merged columns</span></span>  
  
1.  <span data-ttu-id="0e325-125">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-125">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-126"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-126">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-127">En la ventana de resultados de seguimiento, haga clic con el botón secundario en el encabezado de columna y, a continuación, haga clic en **Elegir columnas**.</span><span class="sxs-lookup"><span data-stu-id="0e325-127">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="0e325-128">En el cuadro de diálogo **Elegir columnas** , haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="0e325-128">In the **Choose Columns** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="0e325-129">En el cuadro de diálogo **Nueva columna combinada** , en el cuadro **Nombre de columna combinada** , escriba un nombre para las columnas combinadas.</span><span class="sxs-lookup"><span data-stu-id="0e325-129">In the **New Merged Column** dialog box, in the **Merged column name** box, enter a name for the merged columns.</span></span>  
  
5.  <span data-ttu-id="0e325-130">En el cuadro **Columnas originales para combinar** , seleccione dos o más columnas para combinar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-130">In the **Original columns to merge** box, select two or more columns to merge from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-131">Los eventos extendidos solo permiten combinar hasta cinco columnas.</span><span class="sxs-lookup"><span data-stu-id="0e325-131">Extended Events only supports merging up to five columns.</span></span>  
  
6.  <span data-ttu-id="0e325-132">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e325-132">Click **OK**.</span></span>  
  
#### <a name="to-edit-merged-columns"></a><span data-ttu-id="0e325-133">Para editar columnas combinadas</span><span class="sxs-lookup"><span data-stu-id="0e325-133">To edit merged columns</span></span>  
  
1.  <span data-ttu-id="0e325-134">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-134">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-135"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-135">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-136">En la ventana de resultados de seguimiento, haga clic con el botón secundario en el encabezado de columna y, a continuación, haga clic en **Elegir columnas**.</span><span class="sxs-lookup"><span data-stu-id="0e325-136">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="0e325-137">En el cuadro de diálogo **Elegir columnas** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0e325-137">In the **Choose Columns** dialog box, click **Edit**.</span></span>  
  
4.  <span data-ttu-id="0e325-138">Para cambiar el nombre de la columna combinada, en el cuadro de diálogo **Nueva columna combinada** , en el cuadro **Nombre de columna combinada** , escriba el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="0e325-138">To change the name of the merged column, in the **New Merged Column** dialog box, in the **Merged column name** box, enter the new name.</span></span>  
  
     <span data-ttu-id="0e325-139">Para cambiar las columnas que desea combinar, en el cuadro **Columnas originales para combinar** , seleccione las columnas que desee combinar en la lista desplegable, y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e325-139">To change the columns you want to merge, in the **Original columns to merge** box, select the columns you want to merge from the drop-down list, and then click **OK**.</span></span>  
  
#### <a name="to-delete-merged-columns"></a><span data-ttu-id="0e325-140">Para eliminar columnas combinadas</span><span class="sxs-lookup"><span data-stu-id="0e325-140">To delete merged columns</span></span>  
  
1.  <span data-ttu-id="0e325-141">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-141">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-142"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-142">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-143">En la ventana de resultados de seguimiento, haga clic con el botón secundario en el encabezado de columna y, a continuación, haga clic en **Elegir columnas**.</span><span class="sxs-lookup"><span data-stu-id="0e325-143">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="0e325-144">En el cuadro de diálogo **Elegir columnas** , seleccione el nombre de la columna combinada que desee eliminar y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0e325-144">In the **Choose Columns** dialog box, select the name of the merged column you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="sort-the-results"></a><a name="SortResults"></a><span data-ttu-id="0e325-145">Ordenar los resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-145">Sort the Results</span></span>  
  
#### <a name="to-sort-the-results-in-ascending-or-descending-order"></a><span data-ttu-id="0e325-146">Para ordenar los resultados en orden ascendente o descendente</span><span class="sxs-lookup"><span data-stu-id="0e325-146">To sort the results in ascending or descending order</span></span>  
  
-   <span data-ttu-id="0e325-147">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-147">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-148"> También puede hacer clic con el botón secundario del mouse en el nombre de la sesión, seleccionar **Observar datos en directo**y, a continuación, hacer clic en el botón **Detener fuente de distribución de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="0e325-148">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
-   <span data-ttu-id="0e325-149">En la ventana de resultados de seguimiento, haga clic con el botón secundario del mouse en el encabezado de columna que desea ordenar.</span><span class="sxs-lookup"><span data-stu-id="0e325-149">In the trace results window, right-click the column heading you want to sort.</span></span> <span data-ttu-id="0e325-150">Haga clic **Orden ascendente** o en **Orden descendente** para ordenar la columna en orden ascendente o descendente respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0e325-150">Click **Sort Ascending** or **Sort Descending** to sort the column in ascending or descending order respectively.</span></span>  
  
     <span data-ttu-id="0e325-151">Si ha agrupado las columnas, al ordenar la columna, solo se ordenarán los datos que contiene el grupo.</span><span class="sxs-lookup"><span data-stu-id="0e325-151">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
##  <a name="group-results"></a><a name="GroupResults"></a><span data-ttu-id="0e325-152">Agrupar resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-152">Group Results</span></span>  
  
#### <a name="to-group-the-results-by-a-single-column"></a><span data-ttu-id="0e325-153">Para agrupar los resultados por una única columna</span><span class="sxs-lookup"><span data-stu-id="0e325-153">To group the results by a single column</span></span>  
  
1.  <span data-ttu-id="0e325-154">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-154">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-155"> También puede hacer clic con el botón secundario del mouse en el nombre de la sesión, seleccionar **Observar datos en directo**y, a continuación, hacer clic en el botón **Detener fuente de distribución de datos** de la barra de herramientas de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="0e325-155">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the Extended Events toolbar.</span></span>  
  
2.  <span data-ttu-id="0e325-156">En la ventana de resultados de seguimiento, haga clic con el botón secundario del mouse en el encabezado de columna que desea agrupar, y, a continuación, haga clic en **Agrupar por esta columna**.</span><span class="sxs-lookup"><span data-stu-id="0e325-156">In the trace results window, right-click the column header you want to group, and then click **Group By This Column**.</span></span>  
  
#### <a name="to-group-the-results-by-multiple-columns"></a><span data-ttu-id="0e325-157">Para agrupar los resultados por varias columnas</span><span class="sxs-lookup"><span data-stu-id="0e325-157">To group the results by multiple columns</span></span>  
  
1.  <span data-ttu-id="0e325-158">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-158">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-159"> También puede hacer clic con el botón secundario del mouse en el nombre de la sesión, seleccionar **Observar datos en directo**y, a continuación, hacer clic en el botón **Detener fuente de distribución de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="0e325-159">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
2.  <span data-ttu-id="0e325-160">Haga clic en el botón **Agrupación** en la barra de herramientas de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="0e325-160">Click the **Grouping** button on the Extended Events toolbar.</span></span>  
  
3.  <span data-ttu-id="0e325-161">En el cuadro de diálogo **Agrupación** , en el cuadro **Columnas disponibles** , seleccione las columnas que desee agrupar y, a continuación, haga clic en la flecha derecha.</span><span class="sxs-lookup"><span data-stu-id="0e325-161">In the **Grouping** dialog box, in the **Available columns** box, select the columns you want to group, and then click the right arrow.</span></span>  
  
     <span data-ttu-id="0e325-162">Para cambiar el orden de agrupación, en la sección **Columnas agrupadas en** , haga clic en las flechas arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="0e325-162">To change the grouping order, in the **Columns grouped on** section, click the up or down arrows.</span></span>  
  
     <span data-ttu-id="0e325-163">Para quitar las columnas de la agrupación, en el cuadro **Columnas agrupadas en** , seleccione las columnas que desea quitar y, a continuación, haga clic en la flecha izquierda.</span><span class="sxs-lookup"><span data-stu-id="0e325-163">To remove columns from the grouping, in the **Columns grouped on** box, select the columns you want to remove and then click the left arrow.</span></span>  
  
4.  <span data-ttu-id="0e325-164">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e325-164">Click **OK**.</span></span>  
  
##  <a name="aggregate-results"></a><a name="AggregateResults"></a><span data-ttu-id="0e325-165">Resultados agregados</span><span class="sxs-lookup"><span data-stu-id="0e325-165">Aggregate Results</span></span>  
 <span data-ttu-id="0e325-166">Los eventos extendidos admiten cinco funciones de agregación:</span><span class="sxs-lookup"><span data-stu-id="0e325-166">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="0e325-167">Sum</span><span class="sxs-lookup"><span data-stu-id="0e325-167">Sum</span></span>  
  
-   <span data-ttu-id="0e325-168">Min</span><span class="sxs-lookup"><span data-stu-id="0e325-168">Min</span></span>  
  
-   <span data-ttu-id="0e325-169">Max</span><span class="sxs-lookup"><span data-stu-id="0e325-169">Max</span></span>  
  
-   <span data-ttu-id="0e325-170">Average</span><span class="sxs-lookup"><span data-stu-id="0e325-170">Average</span></span>  
  
-   <span data-ttu-id="0e325-171">Count</span><span class="sxs-lookup"><span data-stu-id="0e325-171">Count</span></span>  
  
 <span data-ttu-id="0e325-172">Sum, Min, Max y Average solo se pueden usar con las columnas numéricas disponibles.</span><span class="sxs-lookup"><span data-stu-id="0e325-172">Sum, Min,  Max, and Average can only be used with available numeric columns.</span></span> <span data-ttu-id="0e325-173">Count es el número de valores distintos de null que existen para la columna seleccionada del grupo.</span><span class="sxs-lookup"><span data-stu-id="0e325-173">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
#### <a name="to-aggregate-results"></a><span data-ttu-id="0e325-174">Para agregar los resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-174">To aggregate results</span></span>  
  
1.  <span data-ttu-id="0e325-175">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-175">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-176"> También puede hacer clic con el botón secundario del mouse en el nombre de la sesión, seleccionar **Observar datos en directo**y, a continuación, hacer clic en el botón **Detener fuente de distribución de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="0e325-176">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-177">La agregación se ejecuta en un grupo, de modo que debe agrupar los resultados para realizar la agregación.</span><span class="sxs-lookup"><span data-stu-id="0e325-177">Aggregation is run against a group, so you must group the results before you can perform the aggregation.</span></span>  
  
2.  <span data-ttu-id="0e325-178">En la barra de herramientas de Eventos extendidos, haga clic en el botón **Agregado** .</span><span class="sxs-lookup"><span data-stu-id="0e325-178">On the Extended Events toolbar, click the **Aggregate** button.</span></span>  
  
     <span data-ttu-id="0e325-179">El cuadro de diálogo **Agregación** aparece mostrando las columnas disponibles para la agregación.</span><span class="sxs-lookup"><span data-stu-id="0e325-179">The **Aggregation** dialog box appears displaying the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="0e325-180">En **Tipo de agregación**, seleccione cómo desea agregar la columna correspondiente en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-180">Under **Aggregation Type**, select how you want to aggregate the corresponding column from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="0e325-181">En el cuadro **Ordenar agregación por** , seleccione la columna por la que desea ordenar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-181">In the **Sort aggregation by** box, select the column you want to sort by from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="0e325-182">Seleccione la opción **En orden ascendente** para clasificar el resultado de la agregación en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="0e325-182">Select the **In ascending order** option to sort the aggregation result in ascending order.</span></span>  
  
6.  <span data-ttu-id="0e325-183">Seleccione la opción **En orden descendente** para clasificar el resultado de la agregación en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="0e325-183">Select the **In descending order** option to sort the aggregation result in descending order.</span></span>  
  
7.  <span data-ttu-id="0e325-184">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e325-184">Click **OK**.</span></span>  
  
##  <a name="filter-results"></a><a name="Filter"></a><span data-ttu-id="0e325-185">Filtrar resultados</span><span class="sxs-lookup"><span data-stu-id="0e325-185">Filter Results</span></span>  
 <span data-ttu-id="0e325-186">Puede aplicar filtros para reducir los resultados de seguimiento que se muestran en la ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-186">You can apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="0e325-187">El filtro de visualización incluye un filtro horario y un filtro avanzado.</span><span class="sxs-lookup"><span data-stu-id="0e325-187">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="0e325-188">Puede utilizar el filtro horario para filtrar el resultado de seguimiento por la marca de tiempo del evento y utilizar el filtro avanzado para crear condiciones de filtro mediante los campos de evento y las acciones.</span><span class="sxs-lookup"><span data-stu-id="0e325-188">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="0e325-189">Hay una relación de AND lógico entre el filtro horario y el filtro avanzado.</span><span class="sxs-lookup"><span data-stu-id="0e325-189">There is an logical AND relationship between the Time and Advanced Filters.</span></span>  
  
#### <a name="to-create-a-filter"></a><span data-ttu-id="0e325-190">Para crear un filtro</span><span class="sxs-lookup"><span data-stu-id="0e325-190">To create a filter</span></span>  
  
1.  <span data-ttu-id="0e325-191">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-191">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-192"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-192">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-193">En la ventana de resultados de seguimiento, seleccione los resultados que desee filtrar, y a continuación, en la barra de herramientas Eventos extendidos, haga clic en el botón **Filtros** .</span><span class="sxs-lookup"><span data-stu-id="0e325-193">In the trace results window, select the results you want to filter, and then on the Extended Events toolbar, click the **Filters** button.</span></span>  
  
3.  <span data-ttu-id="0e325-194">En el cuadro de diálogo **Filtros** , seleccione **Establecer filtro de tiempo** para establecer el filtro horario arrastrando las barras deslizantes para establecer la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="0e325-194">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars to set the timeline.</span></span> <span data-ttu-id="0e325-195">Tenga en cuenta que al mover las barras deslizantes, el cuadro horario muestra el valor de tiempo en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="0e325-195">Note that when you move the slider bars, the time box displays the time value accordingly.</span></span> <span data-ttu-id="0e325-196">También puede especificar el tiempo en los cuadros horarios o seleccionarlo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-196">You can also enter the time in the time boxes, or you select it from the drop-down list.</span></span> <span data-ttu-id="0e325-197">Tenga en cuenta que al especificar el tiempo, el control deslizante horario de la izquierda se moverá en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="0e325-197">Note that when you enter the time, the left time slider will move accordingly.</span></span>  
  
4.  <span data-ttu-id="0e325-198">En la sección **filtros adicionales** , aplique los criterios de filtro y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0e325-198">In the **Additional Filters** section, apply your filter criteria, and then click **Apply**.</span></span> <span data-ttu-id="0e325-199">Cuando acabe de crear el filtro, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e325-199">When your finished created the filter, click **OK**.</span></span>  
  
 <span data-ttu-id="0e325-200">Un caso especial es cuando un campo de evento tiene el mismo nombre que una acción.</span><span class="sxs-lookup"><span data-stu-id="0e325-200">A special situation is when an event field has the same name as an action.</span></span> <span data-ttu-id="0e325-201">Por ejemplo, session_id.</span><span class="sxs-lookup"><span data-stu-id="0e325-201">An example of this would be session_id.</span></span> <span data-ttu-id="0e325-202">Hay varios eventos que contienen un campo session_id y, además, podría agregarse la acción session_id.</span><span class="sxs-lookup"><span data-stu-id="0e325-202">There are several events that include a session_id field and you could also add the session_id action.</span></span> <span data-ttu-id="0e325-203">Estos dos fragmentos de información se recopilan, pero la cuadrícula de presentación del generador de perfiles Eventos extendidos usa la lógica siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e325-203">Both pieces of information are collected, but the Extended Events profiler display grid uses the following logic.</span></span>  
  
-   <span data-ttu-id="0e325-204">En la ventana de la cuadrícula solo se muestra una copia de la columna (session_id en este caso).</span><span class="sxs-lookup"><span data-stu-id="0e325-204">Only one copy of the column (session_id in this case) is shown in the grid display.</span></span>  
  
-   <span data-ttu-id="0e325-205">Si existen dos campos y una acción en los datos, se muestra el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="0e325-205">If both fields and action exist in the data, the field value is shown.</span></span>  
  
-   <span data-ttu-id="0e325-206">Si solo existe el campo o la acción en los datos, se muestra el campo o la acción.</span><span class="sxs-lookup"><span data-stu-id="0e325-206">If only field or action is exists in the data, the field or action is displayed.</span></span>  
  
-   <span data-ttu-id="0e325-207">Si no existe ni la acción ni el campo, se muestra NULL.</span><span class="sxs-lookup"><span data-stu-id="0e325-207">If neither action nor field exists, display NULL.</span></span>  
  
##  <a name="search-for-text-in-columns"></a><a name="Search"></a><span data-ttu-id="0e325-208">Buscar texto en columnas</span><span class="sxs-lookup"><span data-stu-id="0e325-208">Search for Text in Columns</span></span>  
  
1.  <span data-ttu-id="0e325-209">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-209">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-210"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-210">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-211">En la barra de herramientas de eventos extendidos, haga clic en el botón **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="0e325-211">On the Extended Events toolbar, click the **Find** button.</span></span>  
  
3.  <span data-ttu-id="0e325-212">En el cuadro de diálogo **Buscar en eventos extendidos** , en el cuadro **Buscar** , escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="0e325-212">In the **Find in Extended Events** dialog box, in the **Find what** box, enter the text you want to search for.</span></span>  
  
     <span data-ttu-id="0e325-213">Puede seleccionar una de sus últimas 20 cadenas de búsqueda en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-213">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="0e325-214">En el cuadro **Buscar en** , seleccione la ubicación en la que desea buscar el texto especificado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-214">In the **Look in** box, select the location in which to search for the specified text from the drop-down list.</span></span> <span data-ttu-id="0e325-215">Utilice las siguientes opciones para buscar:</span><span class="sxs-lookup"><span data-stu-id="0e325-215">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="0e325-216">**Columnas**de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0e325-216">**Table Columns**.</span></span> <span data-ttu-id="0e325-217">Utilice esta opción para buscar en todas las columnas visibles en la ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-217">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="0e325-218">**Detalles**.</span><span class="sxs-lookup"><span data-stu-id="0e325-218">**Details**.</span></span> <span data-ttu-id="0e325-219">Utilice esta opción para buscar en todas las columnas (promocionadas y no promocionadas) en la ventana de seguimiento que se seleccionaron antes de abrir el cuadro **de diálogo Buscar en eventos extendidos** .</span><span class="sxs-lookup"><span data-stu-id="0e325-219">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="0e325-220">**\<Event column name>**.</span><span class="sxs-lookup"><span data-stu-id="0e325-220">**\<Event column name>**.</span></span> <span data-ttu-id="0e325-221">Utilice esta opción para buscar en una columna de evento concreta de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e325-221">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="0e325-222">Utilice las siguientes opciones para especificar cómo desea definir la búsqueda:</span><span class="sxs-lookup"><span data-stu-id="0e325-222">Use the following options to specify how you want to define the search:</span></span>  
  
    1.  <span data-ttu-id="0e325-223">**Coincidencia de mayúsculas y minúsculas**.</span><span class="sxs-lookup"><span data-stu-id="0e325-223">**Match case**.</span></span> <span data-ttu-id="0e325-224">Utilice esta opción para mostrar los resultados de la búsqueda del texto que escribió en el cuadro **Buscar** y que coincidan tanto con el contenido como con el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0e325-224">Use this option to display the search results for the text you entered in the **Find what** box that are matched both by content and by case.</span></span>  
  
    2.  <span data-ttu-id="0e325-225">Solo **palabras completas**.</span><span class="sxs-lookup"><span data-stu-id="0e325-225">**Match whole word**.</span></span> <span data-ttu-id="0e325-226">Utilice esta opción para mostrar solo los resultados de búsqueda del texto especificado cuyas palabras completas coincidan.</span><span class="sxs-lookup"><span data-stu-id="0e325-226">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    3.  <span data-ttu-id="0e325-227">**Buscar hacia atrás**.</span><span class="sxs-lookup"><span data-stu-id="0e325-227">**Search up**.</span></span> <span data-ttu-id="0e325-228">Utilice esta opción para buscar desde la ubicación del cursor hasta el principio de los resultados.</span><span class="sxs-lookup"><span data-stu-id="0e325-228">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    4.  <span data-ttu-id="0e325-229">**Use**.</span><span class="sxs-lookup"><span data-stu-id="0e325-229">**Use**.</span></span> <span data-ttu-id="0e325-230">Utilice esta opción para interpretar los caracteres especiales y las expresiones regulares que escribió en el cuadro **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="0e325-230">Use this option to interpret the special characters and the regular expressions you entered in the **Find what** box.</span></span> <span data-ttu-id="0e325-231">Los caracteres especiales incluyen los caracteres comodín (\*) y (?) para representar uno o más caracteres.</span><span class="sxs-lookup"><span data-stu-id="0e325-231">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="0e325-232">Las expresiones regulares son notaciones especiales utilizadas para definir patrones de texto de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0e325-232">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
6.  <span data-ttu-id="0e325-233">Haga clic en **Buscar siguiente** para buscar siguiente el texto que escribió en el cuadro **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="0e325-233">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
##  <a name="change-the-display-settings"></a><a name="ChangeDisplay"></a><span data-ttu-id="0e325-234">Cambiar la configuración de pantalla</span><span class="sxs-lookup"><span data-stu-id="0e325-234">Change the Display Settings</span></span>  
 <span data-ttu-id="0e325-235">Puede guardar la información de columna (orden de columna, columna de combinación y ancho de columna) y la información de filtro de un resultado de seguimiento en un archivo de configuración de presentación de eventos extendidos (archivo .viewsetting).</span><span class="sxs-lookup"><span data-stu-id="0e325-235">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="0e325-236">Después de guardar el archivo, puede aplicarlo a los resultados de seguimiento para cambiar la vista.</span><span class="sxs-lookup"><span data-stu-id="0e325-236">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
#### <a name="to-change-the-display-settings"></a><span data-ttu-id="0e325-237">Para cambiar la configuración de presentación</span><span class="sxs-lookup"><span data-stu-id="0e325-237">To change the display settings</span></span>  
  
1.  <span data-ttu-id="0e325-238">Abra un archivo .XEL para ver los resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0e325-238">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e325-239"> También puede hacer clic con el botón secundario en el nombre de la sesión, y seleccionar **Observar datos en directo**.</span><span class="sxs-lookup"><span data-stu-id="0e325-239">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="0e325-240">En la ventana de resultados de seguimiento, en la barra de herramientas o el menú de eventos extendidos, seleccione **Opciones de presentación**.</span><span class="sxs-lookup"><span data-stu-id="0e325-240">In the trace results window, on the Extended Events toolbar or menu, select **Display Settings**.</span></span>  
  
3.  <span data-ttu-id="0e325-241">En la lista desplegable, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e325-241">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="0e325-242">**Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="0e325-242">**Save as**.</span></span> <span data-ttu-id="0e325-243">Guarde la información de filtro y columnas del resultado de un seguimiento en un archivo .viewsetting.</span><span class="sxs-lookup"><span data-stu-id="0e325-243">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="0e325-244">**Abra**.</span><span class="sxs-lookup"><span data-stu-id="0e325-244">**Open**.</span></span> <span data-ttu-id="0e325-245">Abra un archivo .viewsetting existente.</span><span class="sxs-lookup"><span data-stu-id="0e325-245">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="0e325-246">**Abrir recientes**.</span><span class="sxs-lookup"><span data-stu-id="0e325-246">**Open recent**.</span></span> <span data-ttu-id="0e325-247">Abra un archivo .viewsetting guardado recientemente.</span><span class="sxs-lookup"><span data-stu-id="0e325-247">Open a recently saved .viewsetting file.</span></span>  
  
  
