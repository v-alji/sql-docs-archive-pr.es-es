---
title: Mostrar los mismos datos en una matriz y en un gráfico (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1262f283-9fc2-4bc1-9c79-457f7642abc7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7746ce1f06d4dcc67c51ddc40714f19a3ff83d51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748000"
---
# <a name="display-the-same-data-on-a-matrix-and-a-chart-report-builder"></a><span data-ttu-id="888d2-102">Mostrar los mismos datos en una matriz y en un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="888d2-102">Display the Same Data on a Matrix and a Chart (Report Builder)</span></span>
  <span data-ttu-id="888d2-103">Cuando se desea mostrar los mismos datos en una matriz y en un gráfico, se deben establecer propiedades en ambas regiones de datos para especificar el mismo conjunto de datos, y también las mismas expresiones para los filtros, los grupos, las ordenaciones y los datos.</span><span class="sxs-lookup"><span data-stu-id="888d2-103">When you want to show the same data in a matrix and a chart, you must set properties on both data regions to specify the same dataset, and also the same expressions for filters, groups, sorts, and data.</span></span>  
  
 <span data-ttu-id="888d2-104">Dado que ambas regiones de datos tendrán el mismo antecesor para los datos (el conjunto de datos de informe), puede agregar un botón de ordenación interactiva a la matriz de modo que, cuando se haga clic en él, cambie el criterio de ordenación tanto para la matriz como para el gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-104">Because both data regions will have the same ancestor for data (the report dataset), you can add an interactive sort button to the matrix that, when the user clicks it, changes the sort order for both the matrix and the chart.</span></span> <span data-ttu-id="888d2-105">Para obtener más información, vea [Agregar una ordenación interactiva a una tabla o una matriz &#40;Generador de informes y SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="888d2-105">For more information, see [Add Interactive Sort to a Table or Matrix &#40;Report Builder and SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="888d2-106">Para usar los valores de grupo de columnas de la matriz como una leyenda para el gráfico, debe especificar los colores para los datos de las series en el gráfico y, a continuación, usar los mismos colores como colores de relleno para el fondo de los cuadros de texto en la celda de la matriz que muestra los valores de grupo.</span><span class="sxs-lookup"><span data-stu-id="888d2-106">To use the matrix column group values as a legend for the chart, you must specify the colors for the series data on the chart, and then use the same colors as the fill colors for the background of the text boxes in the matrix cell that displays the group values.</span></span> <span data-ttu-id="888d2-107">Para más información, vea [Especificar colores uniformes en varios gráficos de formas &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="888d2-107">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="888d2-108">En tiempo de ejecución, su informe puede aparecer desordenado si hay demasiados valores de grupo para sus definiciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="888d2-108">At run-time, your report may appear cluttered if there are too many group values for your group definitions.</span></span> <span data-ttu-id="888d2-109">Es posible que necesite filtrar valores, combinar grupos o ajustar el umbral para que el gráfico combine los grupos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="888d2-109">You might need to filter values, combine groups, or adjust the threshold for the chart to combine groups for you.</span></span> <span data-ttu-id="888d2-110">Para obtener más información, vea [Vincular varias regiones de datos al mismo conjunto de datos &#40;Generador de informes y SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="888d2-110">For more information, see [Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-matrix-and-chart-to-display-the-same-data"></a><span data-ttu-id="888d2-111">Para agregar una matriz y un gráfico que muestren los mismos datos</span><span class="sxs-lookup"><span data-stu-id="888d2-111">To add a matrix and chart to display the same data</span></span>  
  
1.  <span data-ttu-id="888d2-112">Abra un informe en la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="888d2-112">Open a report in design view.</span></span>  
  
2.  <span data-ttu-id="888d2-113">En la pestaña **Insertar** , en el grupo **Regiones de datos** , haga clic en **Matriz**y, a continuación, haga clic en el cuerpo del informe o en un rectángulo en el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="888d2-113">From the **Insert** tab, in the **Data Regions** group, click **Matrix**, and then click the report body or in a rectangle in the report body.</span></span> <span data-ttu-id="888d2-114">Se agregará una matriz al informe.</span><span class="sxs-lookup"><span data-stu-id="888d2-114">A matrix is added to the report.</span></span>  
  
3.  <span data-ttu-id="888d2-115">En la pestaña **Insertar** , en el grupo **Regiones de datos** , haga clic en **Gráfico**y, a continuación, seleccione el tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-115">From the **Insert** tab, in the **Data Regions** group, click **Chart**, and then select the chart type.</span></span> <span data-ttu-id="888d2-116">Se agregará un gráfico al informe.</span><span class="sxs-lookup"><span data-stu-id="888d2-116">A chart is added to the report.</span></span>  
  
4.  <span data-ttu-id="888d2-117">(Opcional) En la pestaña **Insertar** , en el grupo **Elementos de informe** , haga clic en **Rectángulo**y, después, haga clic en el informe.</span><span class="sxs-lookup"><span data-stu-id="888d2-117">(Optional) From the **Insert** tab, in the **Report Items** group, click **Rectangle**, and then click the report.</span></span> <span data-ttu-id="888d2-118">Se agregará un rectángulo al informe.</span><span class="sxs-lookup"><span data-stu-id="888d2-118">A rectangle is added to the report.</span></span> <span data-ttu-id="888d2-119">Arrastre la matriz y el gráfico de los pasos 2 y 3 hasta el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="888d2-119">Drag the matrix and chart from steps 2 and 3 into the rectangle.</span></span>  
  
     <span data-ttu-id="888d2-120">Colocando varias regiones de datos en el contenedor de rectángulo, ayudará a controlar cómo se representan la matriz y el gráfico al visualizar el informe.</span><span class="sxs-lookup"><span data-stu-id="888d2-120">By placing multiple data regions in the rectangle container, you help control how the matrix and chart render when you view the report.</span></span>  
  
     <span data-ttu-id="888d2-121">En los siguientes pasos, elegirá el campo de conjunto de datos que va a mostrarse tanto en la matriz como en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-121">In the next few steps, you will choose the same dataset field to display in the matrix and to display in the chart.</span></span>  
  
5.  <span data-ttu-id="888d2-122">En el panel Datos de informe, arrastre un campo de conjunto de datos numérico hasta la celda de datos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="888d2-122">From the Report Data pane, drag a numeric dataset field to the Data cell in the matrix.</span></span>  
  
     <span data-ttu-id="888d2-123">De forma predeterminada, se usa la función de agregado Sum para calcular el valor de grupo.</span><span class="sxs-lookup"><span data-stu-id="888d2-123">By default, the aggregate function Sum is used for calculating the group value.</span></span> <span data-ttu-id="888d2-124">Si cambia la función de agregado en la matriz, también debe cambiarla en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-124">If you change the aggregate function in the matrix, you must change in the chart also.</span></span>  
  
6.  <span data-ttu-id="888d2-125">En la matriz, haga clic con el botón derecho en la celda con datos, haga clic en **Propiedades de cuadro de texto**y, después, haga clic en **Número**.</span><span class="sxs-lookup"><span data-stu-id="888d2-125">In the matrix, right-click the cell with data, click **Text Box Properties**, and then click **Number**.</span></span> <span data-ttu-id="888d2-126">Elija un formato adecuado para el valor de campo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="888d2-126">Choose an appropriate format for the dataset field value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="888d2-127">Arrastre el mismo campo de conjunto de datos que eligió en el paso 3 hasta el área **Valores** del gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-127">Drag the same dataset field you chose in step 3 to the **Values** area on the chart.</span></span>  
  
9. <span data-ttu-id="888d2-128">En el gráfico, haga clic con el botón derecho en el eje Y, haga clic en **Propiedades del eje**y, después, haga clic en **Número**.</span><span class="sxs-lookup"><span data-stu-id="888d2-128">In the chart, right-click the Y axis, click **Axis Properties**, and then click **Number**.</span></span> <span data-ttu-id="888d2-129">Elija el mismo formato para los datos que eligió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="888d2-129">Choose the same format for the data that you chose in step 4.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="888d2-130">En los siguientes pasos, establecerá el grupo de filas de la matriz y el grupo de series del gráfico en la misma expresión, así como el criterio de ordenación para el grupo de series del gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-130">In the next few steps, you will set the matrix row group and the chart series group to the same expression, and also set the sort order for the chart series group.</span></span>  
  
11. <span data-ttu-id="888d2-131">En el panel Datos de informe, arrastre el campo de conjunto de datos por el que desea agrupar las filas de la matriz al panel Grupos de filas.</span><span class="sxs-lookup"><span data-stu-id="888d2-131">From the Report Data pane, drag the dataset field that you want to group by for matrix rows to the Row Groups pane.</span></span>  
  
     <span data-ttu-id="888d2-132">De forma predeterminada, el grupo de filas de la matriz agrega una expresión de ordenación que es igual que la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="888d2-132">By default, the matrix row group adds a sort expression that is the same as the group expression.</span></span>  
  
12. <span data-ttu-id="888d2-133">Arrastre el mismo campo de conjunto de datos que usó en el paso 9 al área **Grupos de la serie** del gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-133">Drag the same dataset field that you used in step 9 to the **Series Groups** area for the chart.</span></span>  
  
13. <span data-ttu-id="888d2-134">Haga clic con el botón derecho en el grupo en el área **Grupos de la serie** y, después, haga clic en **Propiedades del grupo de series**.</span><span class="sxs-lookup"><span data-stu-id="888d2-134">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
14. <span data-ttu-id="888d2-135">Haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="888d2-135">Click **Sorting**.</span></span>  
  
15. <span data-ttu-id="888d2-136">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="888d2-136">Click **Add**.</span></span> <span data-ttu-id="888d2-137">Aparecerá una nueva fila en la cuadrícula de expresiones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="888d2-137">A new row appears in the sort expressions grid.</span></span>  
  
16. <span data-ttu-id="888d2-138">En **Ordenar por**, en la lista desplegable, elija el campo de conjunto de datos por el que eligió realizar la agrupación en el paso 9.</span><span class="sxs-lookup"><span data-stu-id="888d2-138">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 9.</span></span>  
  
17. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="888d2-139">En los siguientes pasos, establecerá el grupo de columnas de la matriz y el grupo de categorías del gráfico en la misma expresión, así como el criterio de ordenación para el grupo de categorías del gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-139">In the next few steps, you will set the matrix column group and the chart category group to the same expression, and also set the sort order for the chart category group.</span></span>  
  
18. <span data-ttu-id="888d2-140">En el panel Datos de informe, arrastre el campo de conjunto de datos por el que desea agrupar las columnas de la matriz al panel Grupos de columnas.</span><span class="sxs-lookup"><span data-stu-id="888d2-140">From the Report Data pane, drag the dataset field that you want to group by for matrix columns to the Column Groups pane.</span></span>  
  
     <span data-ttu-id="888d2-141">De forma predeterminada, el grupo de columnas de la matriz agrega una expresión de ordenación que es igual que la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="888d2-141">By default, the matrix column group adds a sort expression that is the same as the group expression.</span></span>  
  
19. <span data-ttu-id="888d2-142">Arrastre el mismo campo de conjunto de datos que usó en el paso 16 al área **Grupos de categorías** del gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-142">Drag the same dataset field that you used in step 16 to the **Category Groups** area for the chart.</span></span>  
  
20. <span data-ttu-id="888d2-143">Haga clic con el botón derecho en el área **Grupos de categorías** y, después, en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="888d2-143">Right-click the group in the **CategoryGroups** area, and then click **Category Group Properties**.</span></span>  
  
21. <span data-ttu-id="888d2-144">Haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="888d2-144">Click **Sorting**.</span></span>  
  
22. <span data-ttu-id="888d2-145">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="888d2-145">Click **Add**.</span></span> <span data-ttu-id="888d2-146">Aparecerá una nueva fila en la cuadrícula de expresiones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="888d2-146">A new row appears in the sort expressions grid.</span></span>  
  
23. <span data-ttu-id="888d2-147">En **Ordenar por**, en la lista desplegable, elija el campo de conjunto de datos por el que eligió realizar la agrupación en el paso 16.</span><span class="sxs-lookup"><span data-stu-id="888d2-147">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 16.</span></span>  
  
24. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
25. <span data-ttu-id="888d2-148">Obtenga una vista previa del resultado.</span><span class="sxs-lookup"><span data-stu-id="888d2-148">Preview the result.</span></span> <span data-ttu-id="888d2-149">Los grupos de filas y de columnas de la matriz muestran los mismos datos que los grupos de series y de categorías del gráfico.</span><span class="sxs-lookup"><span data-stu-id="888d2-149">The matrix row and column groups display the same data as the chart series and category groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888d2-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="888d2-150">See Also</span></span>  
 <span data-ttu-id="888d2-151">[Vincular varias regiones de datos al mismo conjunto de datos &#40;Generador de informes y SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="888d2-151">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="888d2-152">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="888d2-152">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="888d2-153">[Enumera &#40;Generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="888d2-153">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="888d2-154">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="888d2-154">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
