---
title: Ordenar datos en una región de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2fcb9be2-1daa-4c92-ad00-5f63cdf39f70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc1fb458066bb942a490b08c0faad876dd3d5438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749071"
---
# <a name="sort-data-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="4bd57-102">Ordenar datos en una región de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="4bd57-102">Sort Data in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4bd57-103">Para cambiar el criterio de ordenación de los datos de una región de datos cuando se ejecuta un informe por primera vez, es necesario establecer la expresión de ordenación en la región de datos o el grupo.</span><span class="sxs-lookup"><span data-stu-id="4bd57-103">To change the sort order of data in a data region when a report first runs, you must set the sort expression on the data region or group.</span></span> <span data-ttu-id="4bd57-104">De forma predeterminada, la expresión de ordenación de un grupo se establece automáticamente en el mismo valor que la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="4bd57-104">By default, the sort expression for a group is automatically set to the same value as the group expression.</span></span>  
  
-   <span data-ttu-id="4bd57-105">En una región de datos Tablix, establezca la expresión de ordenación para la región de datos o para cada grupo, incluido el grupo de detalles.</span><span class="sxs-lookup"><span data-stu-id="4bd57-105">In a tablix data region, set the sort expression for the data region or for each group, including the details group.</span></span> <span data-ttu-id="4bd57-106">Si solo tiene un grupo de detalles en una región de datos Tablix, puede definir una expresión de ordenación en la consulta, en la región de datos o en el grupo de detalles con el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="4bd57-106">If you have only one details group in a tablix data region, you can define a sort expression in the query, on the data region, or on the details group and they all have the same effect.</span></span>  
  
-   <span data-ttu-id="4bd57-107">En una región de datos de gráfico, establezca la expresión de ordenación para los grupos de categorías y de series para controlar el criterio de ordenación para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="4bd57-107">In a chart data region, set the sort expression for the Category and Series groups to control the sort order for each group.</span></span> <span data-ttu-id="4bd57-108">El orden de los colores en una leyenda de gráfico está determinado por la expresión de ordenación para los puntos de datos del grupo de categorías.</span><span class="sxs-lookup"><span data-stu-id="4bd57-108">The order for colors in a chart legend is determined by the sort expression for the data points in the Category group.</span></span>  
  
-   <span data-ttu-id="4bd57-109">Normalmente, en una región de datos de medidor, no es necesario ordenar los datos, ya que el medidor muestra un único valor relativo a un intervalo.</span><span class="sxs-lookup"><span data-stu-id="4bd57-109">In a gauge data region, you do not typically need to sort data because the gauge displays a single value relative to a range.</span></span> <span data-ttu-id="4bd57-110">Si necesita ordenar los datos de un medidor, primero debe definir un grupo y, a continuación, establecer la expresión de ordenación para el grupo.</span><span class="sxs-lookup"><span data-stu-id="4bd57-110">If you do need sort data in a gauge, you must first define a group, and then set the sort expression for the group.</span></span>  
  
 <span data-ttu-id="4bd57-111">Para obtener más información, vea [Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4bd57-111">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="4bd57-112">En una región de datos Tablix, también puede agregar un botón de ordenación interactiva a la parte superior de un encabezado de columna para permitir a los usuarios cambiar el criterio de ordenación de los grupos o las filas de detalles.</span><span class="sxs-lookup"><span data-stu-id="4bd57-112">For a tablix data region, you can also add an interactive sort button to the top of a column header to provide the user with the ability to change the sort order of groups or detail rows.</span></span> <span data-ttu-id="4bd57-113">Para obtener más información, vea [Ordenación interactiva &#40;Generador de informes y SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4bd57-113">For more information, see [Interactive Sort &#40;Report Builder and SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-sort-data-in-a-tablix-data-region"></a><span data-ttu-id="4bd57-114">Para ordenar los datos de una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="4bd57-114">To sort data in a Tablix data region</span></span>  
  
1.  <span data-ttu-id="4bd57-115">En la superficie de diseño, haga clic con el botón derecho en un identificador de fila y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-115">On the design surface, right-click a row handle, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="4bd57-116">Haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-116">Click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="4bd57-117">Para cada expresión de ordenación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4bd57-117">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4bd57-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-118">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="4bd57-119">Escriba o seleccione la expresión por la que desea ordenar los datos.</span><span class="sxs-lookup"><span data-stu-id="4bd57-119">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="4bd57-120">En la lista desplegable de la columna **Ordenar** , elija el sentido de la ordenación para cada expresión.</span><span class="sxs-lookup"><span data-stu-id="4bd57-120">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="4bd57-121">**A-Z** ordena la expresión en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-121">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="4bd57-122">**Z-A** ordena la expresión en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-122">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-values-in-a-group-including-the-details-group-for-a-tablix"></a><span data-ttu-id="4bd57-123">Para ordenar los valores de un grupo, incluido el grupo de detalles, para un Tablix</span><span class="sxs-lookup"><span data-stu-id="4bd57-123">To sort values in a group, including the details group, for a Tablix</span></span>  
  
1.  <span data-ttu-id="4bd57-124">En la superficie de diseño, haga clic en la región de datos Tablix para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="4bd57-124">On the design surface, click in the tablix data region to select it.</span></span> <span data-ttu-id="4bd57-125">El panel Agrupación muestra los grupos de filas y de columnas para la región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="4bd57-125">The Grouping pane displays the row groups and column groups for the Tablix data region.</span></span>  
  
2.  <span data-ttu-id="4bd57-126">En el panel Grupos de filas, haga clic con el botón derecho en el nombre del grupo y, después, haga clic en **Editar grupo**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-126">In the Row Groups pane, right-click the group name, and then click **Edit Group**.</span></span>  
  
3.  <span data-ttu-id="4bd57-127">En el cuadro de diálogo **Grupo de Tablix** , haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-127">In the **Tablix Group** dialog box, click **Sort**.</span></span>  
  
4.  <span data-ttu-id="4bd57-128">Para cada expresión de ordenación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4bd57-128">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4bd57-129">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-129">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="4bd57-130">Escriba o seleccione la expresión por la que desea ordenar los datos.</span><span class="sxs-lookup"><span data-stu-id="4bd57-130">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="4bd57-131">En la lista desplegable de la columna **Ordenar** , elija el sentido de la ordenación para cada expresión.</span><span class="sxs-lookup"><span data-stu-id="4bd57-131">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="4bd57-132">**A-Z** ordena la expresión en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-132">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="4bd57-133">**Z-A** ordena la expresión en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-133">**Z-A** sorts the expression in descending order.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-x-axis-labels-in-alphabetical-order-on-a-chart"></a><span data-ttu-id="4bd57-134">Para ordenar las etiquetas del eje X en orden alfabético en un gráfico</span><span class="sxs-lookup"><span data-stu-id="4bd57-134">To sort x-axis labels in alphabetical order on a chart</span></span>  
  
1.  <span data-ttu-id="4bd57-135">Haga clic con el botón derecho en la zona de colocación de campos de categorías y, después, haga clic en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-135">Right-click a field in the Category Field drop-zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="4bd57-136">En el cuadro de diálogo **Propiedades del grupo de categorías** , haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-136">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="4bd57-137">Para cada expresión de ordenación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4bd57-137">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4bd57-138">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-138">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="4bd57-139">Seleccione la expresión que coincide con el campo de agrupación.</span><span class="sxs-lookup"><span data-stu-id="4bd57-139">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="4bd57-140">Puede comprobar la expresión para el campo de agrupación haciendo clic en **Agrupación**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-140">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="4bd57-141">En la lista desplegable de la columna **Ordenar** , elija el sentido de la ordenación para cada expresión.</span><span class="sxs-lookup"><span data-stu-id="4bd57-141">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="4bd57-142">**A-Z** ordena la expresión en orden alfabético ascendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-142">**A-Z** sorts the expression in ascending alphabetical order.</span></span> <span data-ttu-id="4bd57-143">**Z-A** ordena la expresión en orden alfabético descendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-143">**Z-A** sorts the expression in descending alphabetical order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-the-data-points-in-ascending-or-descending-order-on-a-chart"></a><span data-ttu-id="4bd57-144">Para ordenar los puntos de datos de forma ascendente o descendente en un gráfico</span><span class="sxs-lookup"><span data-stu-id="4bd57-144">To sort the data points in ascending or descending order on a chart</span></span>  
  
1.  <span data-ttu-id="4bd57-145">Haga clic con el botón derecho en la zona de colocación de campos de categorías y, después, haga clic en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-145">Right-click a field in the Category Field drop zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="4bd57-146">En el cuadro de diálogo **Propiedades del grupo de categorías** , haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-146">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="4bd57-147">Para cada expresión de ordenación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4bd57-147">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4bd57-148">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-148">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="4bd57-149">Seleccione la expresión que coincide con el campo de datos.</span><span class="sxs-lookup"><span data-stu-id="4bd57-149">Select the expression that matches your data field.</span></span> <span data-ttu-id="4bd57-150">En la mayoría de los casos, es un valor agregado, como `=Sum(Fields!Quantity.Value)`.</span><span class="sxs-lookup"><span data-stu-id="4bd57-150">In most cases, this is an aggregated value, such as `=Sum(Fields!Quantity.Value)`.</span></span>  
  
    3.  <span data-ttu-id="4bd57-151">En la lista desplegable de la columna **Ordenar** , elija el sentido de la ordenación para cada expresión.</span><span class="sxs-lookup"><span data-stu-id="4bd57-151">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="4bd57-152">**A-Z** ordena la expresión en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-152">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="4bd57-153">**Z-A** ordena la expresión en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-153">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-data-in-ascending-or-descending-order-for-display-on-a-gauge"></a><span data-ttu-id="4bd57-154">Para ordenar los datos de forma ascendente o descendente para su presentación en un medidor</span><span class="sxs-lookup"><span data-stu-id="4bd57-154">To sort data in ascending or descending order for display on a gauge</span></span>  
  
1.  <span data-ttu-id="4bd57-155">Haga clic con el botón derecho en el medidor y, después, haga clic en **Agregar grupo de datos**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-155">Right-click the gauge and click **Add Data Group**.</span></span>  
  
2.  <span data-ttu-id="4bd57-156">En el cuadro de diálogo **Propiedades de grupo del panel de medidores** , haga clic en **General** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4bd57-156">In the **Gauge Panel GroupProperties** dialog box, click **General** if necessary.</span></span>  
  
3.  <span data-ttu-id="4bd57-157">En **Expresiones de grupo**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-157">In **Group expressions**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="4bd57-158">En **Agrupar por**, escriba o seleccione la expresión por la que se agruparán los datos.</span><span class="sxs-lookup"><span data-stu-id="4bd57-158">In **Group on**, type or select an expression by which to group the data.</span></span>  
  
5.  <span data-ttu-id="4bd57-159">Repita los pasos 3 y 4 hasta que haya agregado todas las expresiones de grupo que desee usar.</span><span class="sxs-lookup"><span data-stu-id="4bd57-159">Repeat steps 3 and 4 until you have added all the group expressions you want to use.</span></span>  
  
6.  <span data-ttu-id="4bd57-160">Haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-160">Click **Sorting**.</span></span>  
  
7.  <span data-ttu-id="4bd57-161">Para cada expresión de ordenación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4bd57-161">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4bd57-162">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-162">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="4bd57-163">Seleccione la expresión que coincide con el campo de agrupación.</span><span class="sxs-lookup"><span data-stu-id="4bd57-163">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="4bd57-164">Puede comprobar la expresión para el campo de agrupación haciendo clic en **Agrupación**.</span><span class="sxs-lookup"><span data-stu-id="4bd57-164">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="4bd57-165">En la lista desplegable de la columna **Ordenar** , elija el sentido de la ordenación para cada expresión.</span><span class="sxs-lookup"><span data-stu-id="4bd57-165">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="4bd57-166">**A-Z** ordena la expresión en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-166">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="4bd57-167">**Z-A** ordena la expresión en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="4bd57-167">**Z-A** sorts the expression in descending order.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="4bd57-168">Para más información sobre cómo se agrupan los datos en un medidor, vea [Medidores &#40;Generador de informes y SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4bd57-168">For more information about how data is grouped in a gauge, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd57-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bd57-169">See Also</span></span>  
 <span data-ttu-id="4bd57-170">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="4bd57-170">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="4bd57-171">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4bd57-171">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4bd57-172">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4bd57-172">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4bd57-173">Especificar colores coherentes en varios gráficos de formas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4bd57-173">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
