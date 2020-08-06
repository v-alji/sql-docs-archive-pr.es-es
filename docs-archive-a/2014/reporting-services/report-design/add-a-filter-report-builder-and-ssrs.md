---
title: Agregar un filtro (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61a5444c437027d92a9f054e74cbcac6af5cc776
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751729"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a><span data-ttu-id="98ca1-102">Agregar un filtro (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="98ca1-102">Add a Filter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="98ca1-103">Agregue un filtro a un conjunto de datos, una región de datos o un grupo cuando desee incluir o excluir valores específicos para la realización de cálculos o la visualización.</span><span class="sxs-lookup"><span data-stu-id="98ca1-103">Add a filter to a dataset, data region, or group when you want to include or exclude specific values for calculations or display.</span></span> <span data-ttu-id="98ca1-104">Los filtros se aplican en tiempo de ejecución y en este orden: primero en el conjunto de datos, a continuación, en la región de datos y, por último, en el grupo; en las jerarquías de grupo, se aplican en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="98ca1-104">Filters are applied at run time first on the dataset, and then on the data region, and then on the group, in top-down order for group hierarchies.</span></span> <span data-ttu-id="98ca1-105">En una tabla, matriz o lista, los filtros de los grupos de filas, los grupos de columnas y los grupos adyacentes se aplican de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="98ca1-105">In a table, matrix, or list, filters for row groups, column groups, and adjacent groups are applied independently.</span></span> <span data-ttu-id="98ca1-106">En un gráfico, también se aplican de forma independiente los filtros de los grupos de categorías y los grupos de series.</span><span class="sxs-lookup"><span data-stu-id="98ca1-106">In a chart, filters for category groups and series groups are applied independently.</span></span>  
  
 <span data-ttu-id="98ca1-107">Para agregar un filtro, debe especificar una o varias ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="98ca1-107">To add a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="98ca1-108">Una ecuación de filtro se compone de una expresión que identifica los datos que se van a filtrar, un operador y el valor con el que se va a llevar a cabo la comparación.</span><span class="sxs-lookup"><span data-stu-id="98ca1-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="98ca1-109">Los tipos de datos de los datos filtrados y el valor deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="98ca1-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="98ca1-110">No está permitido el filtrado por valores agregados para un conjunto de datos o una región de datos.</span><span class="sxs-lookup"><span data-stu-id="98ca1-110">Filtering on aggregate values for a dataset or data region is not supported.</span></span>  
  
 <span data-ttu-id="98ca1-111">Para filtrar los puntos de datos de un gráfico, puede establecer un filtro en un grupo de categorías o en un grupo de series.</span><span class="sxs-lookup"><span data-stu-id="98ca1-111">To filter data points in a chart, you can set a filter on a category group or a series group.</span></span> <span data-ttu-id="98ca1-112">De manera predeterminada, el gráfico usa la función integrada SUM para agregar valores que pertenecen al mismo grupo en un punto de datos individual de la serie.</span><span class="sxs-lookup"><span data-stu-id="98ca1-112">By default, the chart uses the built-in function Sum to aggregate values that belong to the same group into an individual data point in the series.</span></span> <span data-ttu-id="98ca1-113">Si cambia la función de agregado de una serie, deberá cambiar la función de agregado en la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="98ca1-113">If you change the aggregate function of a series, you must change the aggregate function in the filter expression.</span></span>  
  
 <span data-ttu-id="98ca1-114">Para más información sobre cómo filtrar conjuntos de datos insertados y compartidos, vea [Agregar un filtro a un conjunto de datos &#40;Generador de informes y SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98ca1-114">For more information about filtering embedded and shared datasets, see [Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a><span data-ttu-id="98ca1-115">Para establecer un filtro en una región de datos</span><span class="sxs-lookup"><span data-stu-id="98ca1-115">To set a filter on a data region</span></span>  
  
1.  <span data-ttu-id="98ca1-116">Abra un informe en la vista **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-116">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="98ca1-117">Seleccione la región de datos en la superficie de diseño y, a continuación, haga clic con el botón derecho en _\<data region>_ **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-117">Select the data region on the design surface, and then right-click _\<data region>_**Properties**.</span></span> <span data-ttu-id="98ca1-118">Si se trata de un medidor, seleccione **Propiedades del panel de medidores**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-118">For a gauge, select **Gauge Panel Properties**.</span></span> <span data-ttu-id="98ca1-119">_\<data region>_ Se abrirá el cuadro de diálogo **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-119">The _\<data region>_**Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="98ca1-120">En una región de datos Tablix, haga clic con el botón derecho en la celda de la esquina o en un identificador de fila o columna y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-120">On a Tablix data region, right-click the corner cell or a row or column handle, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="98ca1-121">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-121">Click **Filters**.</span></span> <span data-ttu-id="98ca1-122">Aparece la lista actual de ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="98ca1-122">This displays the current list of filter equations.</span></span> <span data-ttu-id="98ca1-123">La lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98ca1-123">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="98ca1-124">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-124">Click **Add**.</span></span> <span data-ttu-id="98ca1-125">Aparece una nueva ecuación de filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="98ca1-125">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="98ca1-126">En **Expresión**, escriba o seleccione la expresión para el campo que va a filtrar.</span><span class="sxs-lookup"><span data-stu-id="98ca1-126">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="98ca1-127">Para editar la expresión, haga clic en el botón de expresión (*fx*).</span><span class="sxs-lookup"><span data-stu-id="98ca1-127">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="98ca1-128">En la lista desplegable, seleccione el tipo de datos que coincide con el tipo de datos de la expresión que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="98ca1-128">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="98ca1-129">En el cuadro **Operador** , seleccione el operador que deberá usar el filtro para comparar los valores de los cuadros **Expresión** y **Valor** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-129">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="98ca1-130">El operador que elija determinará el número de valores que se usarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ca1-130">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="98ca1-131">En el cuadro **Valor** , escriba la expresión o el valor que deberá usar el filtro para evaluar el valor de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-131">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="98ca1-132">Para obtener ejemplos de ecuaciones de filtro, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98ca1-132">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a><span data-ttu-id="98ca1-133">Para establecer un filtro en un grupo de filas o de columnas de un Tablix</span><span class="sxs-lookup"><span data-stu-id="98ca1-133">To set a filter on a Tablix row or column group</span></span>  
  
1.  <span data-ttu-id="98ca1-134">Abra un informe en la vista **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-134">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="98ca1-135">Haga clic con el botón secundario en la tabla, matriz o región de datos de lista de la superficie de diseño para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="98ca1-135">Right-click the table, matrix, or list data region on the design surface to select it.</span></span> <span data-ttu-id="98ca1-136">El panel de agrupación muestra los grupos para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="98ca1-136">The Grouping pane displays the groups for the selected item.</span></span>  
  
3.  <span data-ttu-id="98ca1-137">En el panel de agrupación, haga clic con el botón derecho en el grupo y, después, haga clic en **Editar grupo**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-137">In the Grouping pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="98ca1-138">Se abre el cuadro de diálogo **Grupo de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-138">The **Tablix Group** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="98ca1-139">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-139">Click **Filters**.</span></span> <span data-ttu-id="98ca1-140">Aparece la lista actual de ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="98ca1-140">This displays the current list of filter equations.</span></span> <span data-ttu-id="98ca1-141">La lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98ca1-141">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="98ca1-142">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-142">Click **Add**.</span></span> <span data-ttu-id="98ca1-143">Aparece una nueva ecuación de filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="98ca1-143">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="98ca1-144">En **Expresión**, escriba o seleccione la expresión para el campo que va a filtrar.</span><span class="sxs-lookup"><span data-stu-id="98ca1-144">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="98ca1-145">Para editar la expresión, haga clic en el botón de expresión (*fx*).</span><span class="sxs-lookup"><span data-stu-id="98ca1-145">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="98ca1-146">En la lista desplegable, seleccione el tipo de datos que coincide con el tipo de datos de la expresión que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="98ca1-146">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="98ca1-147">En el cuadro **Operador** , seleccione el operador que deberá usar el filtro para comparar los valores de los cuadros **Expresión** y **Valor** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-147">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="98ca1-148">El operador que elija determinará el número de valores que se usarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ca1-148">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="98ca1-149">En el cuadro **Valor** , escriba la expresión o el valor que deberá usar el filtro para evaluar el valor de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-149">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="98ca1-150">Para obtener ejemplos de ecuaciones de filtro, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98ca1-150">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a><span data-ttu-id="98ca1-151">Para establecer un filtro en un grupo de categorías de gráfico</span><span class="sxs-lookup"><span data-stu-id="98ca1-151">To set a filter on a Chart category group</span></span>  
  
1.  <span data-ttu-id="98ca1-152">Abra un informe en la vista **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-152">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="98ca1-153">En la superficie de diseño, haga clic dos veces en el gráfico para que aparezcan las zonas de colocación de campos de datos, de serie y de categoría.</span><span class="sxs-lookup"><span data-stu-id="98ca1-153">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="98ca1-154">Haga clic con el botón derecho en un campo de la zona de colocación de campos de categoría y seleccione **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-154">Right-click on a field contained in the category field drop zone and select **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="98ca1-155">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-155">Click **Filters**.</span></span> <span data-ttu-id="98ca1-156">Aparece la lista actual de ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="98ca1-156">This displays the current list of filter equations.</span></span> <span data-ttu-id="98ca1-157">La lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98ca1-157">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="98ca1-158">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-158">Click **Add**.</span></span> <span data-ttu-id="98ca1-159">Aparece una nueva ecuación de filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="98ca1-159">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="98ca1-160">En **Expresión**, escriba o seleccione la expresión para el campo que va a filtrar.</span><span class="sxs-lookup"><span data-stu-id="98ca1-160">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="98ca1-161">Para editar la expresión, haga clic en el botón de expresión (*fx*).</span><span class="sxs-lookup"><span data-stu-id="98ca1-161">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="98ca1-162">En la lista desplegable, seleccione el tipo de datos que coincide con el tipo de datos de la expresión que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="98ca1-162">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="98ca1-163">En el cuadro **Operador** , seleccione el operador que deberá usar el filtro para comparar los valores de los cuadros **Expresión** y **Valor** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-163">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="98ca1-164">El operador que elija determinará el número de valores que se usarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ca1-164">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="98ca1-165">En el cuadro **Valor** , escriba la expresión o el valor que deberá usar el filtro para evaluar el valor de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-165">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="98ca1-166">Para obtener ejemplos de ecuaciones de filtro, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98ca1-166">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a><span data-ttu-id="98ca1-167">Para establecer un filtro en un grupo de series de gráfico</span><span class="sxs-lookup"><span data-stu-id="98ca1-167">To set a filter on a Chart series group</span></span>  
  
1.  <span data-ttu-id="98ca1-168">Abra un informe en la vista **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-168">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="98ca1-169">En la superficie de diseño, haga clic dos veces en el gráfico para que aparezcan las zonas de colocación de campos de datos, de serie y de categoría.</span><span class="sxs-lookup"><span data-stu-id="98ca1-169">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="98ca1-170">Haga clic con el botón derecho en un campo de la zona de colocación de campos de serie y seleccione **Propiedades del grupo de series**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-170">Right-click on a field contained in the series field drop zone and select **Series Group Properties**.</span></span>  
  
4.  <span data-ttu-id="98ca1-171">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-171">Click **Filters**.</span></span> <span data-ttu-id="98ca1-172">Aparece la lista actual de ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="98ca1-172">This displays the current list of filter equations.</span></span> <span data-ttu-id="98ca1-173">La lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98ca1-173">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="98ca1-174">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-174">Click **Add**.</span></span> <span data-ttu-id="98ca1-175">Aparece una nueva ecuación de filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="98ca1-175">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="98ca1-176">En **Expresión**, escriba o seleccione la expresión para el campo que va a filtrar.</span><span class="sxs-lookup"><span data-stu-id="98ca1-176">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="98ca1-177">Para editar la expresión, haga clic en el botón de expresión (*fx*).</span><span class="sxs-lookup"><span data-stu-id="98ca1-177">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="98ca1-178">En la lista desplegable, seleccione el tipo de datos que coincide con el tipo de datos de la expresión que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="98ca1-178">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="98ca1-179">En el cuadro **Operador** , seleccione el operador que deberá usar el filtro para comparar los valores de los cuadros **Expresión** y **Valor** .</span><span class="sxs-lookup"><span data-stu-id="98ca1-179">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="98ca1-180">El operador que elija determinará el número de valores que se usarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="98ca1-180">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="98ca1-181">En el cuadro **Valor** , escriba la expresión o el valor que deberá usar el filtro para evaluar el valor de **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="98ca1-181">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="98ca1-182">Para obtener ejemplos de ecuaciones de filtro, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="98ca1-182">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98ca1-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98ca1-183">See Also</span></span>  
 <span data-ttu-id="98ca1-184">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="98ca1-184">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="98ca1-185">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ca1-185">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="98ca1-186">[Medidores &#40;Generador de informes y SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ca1-186">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="98ca1-187">[Enumera &#40;Generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="98ca1-187">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="98ca1-188">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="98ca1-188">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
