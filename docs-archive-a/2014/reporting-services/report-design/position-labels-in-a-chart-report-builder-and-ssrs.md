---
title: Colocar etiquetas en un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5db74e0b-8be8-4b47-b386-faab56dffa9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e90cbf04e0282454658e6324f0ba6600a99cb718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743922"
---
# <a name="position-labels-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="3573e-102">Colocar etiquetas en un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="3573e-102">Position Labels in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3573e-103">Dado que cada tipo de gráfico tiene una forma diferente, las etiquetas de punto de datos se colocan en una ubicación óptima para no interferir en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3573e-103">Because each chart type has a different shape, data point labels are placed in an optimal location so as not to interfere on the chart.</span></span> <span data-ttu-id="3573e-104">La posición predeterminada de las etiquetas depende del tipo de gráfico:</span><span class="sxs-lookup"><span data-stu-id="3573e-104">The default position of the labels depends varies with the chart type:</span></span>  
  
-   <span data-ttu-id="3573e-105">En los gráficos apilados, las etiquetas solo se pueden colocar dentro de la serie.</span><span class="sxs-lookup"><span data-stu-id="3573e-105">On stacked charts, labels can only be positioned inside the series.</span></span>  
  
-   <span data-ttu-id="3573e-106">En los gráficos de embudo o piramidales, las etiquetas se colocan fuera de una columna.</span><span class="sxs-lookup"><span data-stu-id="3573e-106">On funnel or pyramid charts, labels are placed on the outside in a column.</span></span>  
  
-   <span data-ttu-id="3573e-107">En los gráficos circulares, las etiquetas se colocan dentro de los sectores.</span><span class="sxs-lookup"><span data-stu-id="3573e-107">On pie charts, labels are placed inside the individual slices on a pie chart.</span></span>  
  
-   <span data-ttu-id="3573e-108">En los gráficos de barras, las etiquetas se colocan fuera de las barras que representan los puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="3573e-108">On bar charts, labels are placed outside of the bars that represent data points.</span></span>  
  
-   <span data-ttu-id="3573e-109">En los gráficos polares, las etiquetas se colocan fuera del área circular que representa los puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="3573e-109">On polar charts, labels are placed outside of the circular area that represents data points.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-position-of-point-labels-in-a-pie-chart"></a><span data-ttu-id="3573e-110">Para cambiar la posición de las etiquetas de punto de datos de un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="3573e-110">To change the position of point labels in a Pie chart</span></span>  
  
1.  <span data-ttu-id="3573e-111">Cree un gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="3573e-111">Create a pie chart.</span></span>  
  
2.  <span data-ttu-id="3573e-112">En la superficie de diseño, haga clic con el botón derecho en el gráfico y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="3573e-112">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="3573e-113">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-113">Open the Properties pane.</span></span> <span data-ttu-id="3573e-114">En la pestaña **Ver** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3573e-114">On the **View** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3573e-115">En la superficie de diseño, haga clic en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3573e-115">On the design surface, click the chart.</span></span> <span data-ttu-id="3573e-116">Las propiedades del gráfico se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-116">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="3573e-117">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="3573e-117">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="3573e-118">Se muestra una lista de atributos para el gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="3573e-118">A list of attributes for the pie chart is displayed.</span></span>  
  
6.  <span data-ttu-id="3573e-119">Seleccione un valor para la propiedad PieLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="3573e-119">Select a value for the PieLabelStyle property.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-funnel-or-pyramid-chart"></a><span data-ttu-id="3573e-120">Para cambiar la posición de las etiquetas de punto de datos en un gráfico de embudo o piramidal</span><span class="sxs-lookup"><span data-stu-id="3573e-120">To change the position of point labels in a Funnel or Pyramid chart</span></span>  
  
1.  <span data-ttu-id="3573e-121">Cree un gráfico de embudo o piramidal.</span><span class="sxs-lookup"><span data-stu-id="3573e-121">Create a funnel or pyramid chart.</span></span>  
  
2.  <span data-ttu-id="3573e-122">En la superficie de diseño, haga clic con el botón derecho en el gráfico y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="3573e-122">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="3573e-123">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-123">Open the Properties pane.</span></span> <span data-ttu-id="3573e-124">En la pestaña **Ver** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3573e-124">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="3573e-125">En la superficie de diseño, haga clic en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3573e-125">On the design surface, click the chart.</span></span> <span data-ttu-id="3573e-126">Las propiedades del gráfico se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-126">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="3573e-127">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="3573e-127">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="3573e-128">Se muestra una lista de atributos para el gráfico de embudo.</span><span class="sxs-lookup"><span data-stu-id="3573e-128">A list of attributes for the funnel chart is displayed.</span></span>  
  
6.  <span data-ttu-id="3573e-129">Si se trata de un gráfico de embudo, seleccione un valor para la propiedad FunnelLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="3573e-129">For a funnel chart, select a value for the FunnelLabelStyle property.</span></span> <span data-ttu-id="3573e-130">Si se trata de un gráfico piramidal, seleccione un valor para la propiedad PyramidLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="3573e-130">For a pyramid chart, select a value for the PyramidLabelStyle property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3573e-131">Cuando esta propiedad se establece en un valor `OutsideInColumn`, las etiquetas se representan en una columna vertical.</span><span class="sxs-lookup"><span data-stu-id="3573e-131">When this property is set to a value `OutsideInColumn`, the labels are drawn in a vertical column.</span></span> <span data-ttu-id="3573e-132">No hay ninguna manera de cambiar la posición de la columna.</span><span class="sxs-lookup"><span data-stu-id="3573e-132">There is no way to change the position of the column.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-bar-chart"></a><span data-ttu-id="3573e-133">Para cambiar la posición de las etiquetas de punto de datos de un gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="3573e-133">To change the position of point labels in a Bar chart</span></span>  
  
1.  <span data-ttu-id="3573e-134">Cree un gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="3573e-134">Create a bar chart.</span></span>  
  
2.  <span data-ttu-id="3573e-135">En la superficie de diseño, haga clic con el botón derecho en el gráfico y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="3573e-135">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="3573e-136">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-136">Open the Properties pane.</span></span> <span data-ttu-id="3573e-137">En la pestaña **Ver** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3573e-137">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="3573e-138">En la superficie de diseño, haga clic en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3573e-138">On the design surface, click the chart.</span></span> <span data-ttu-id="3573e-139">Las propiedades del gráfico se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-139">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="3573e-140">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="3573e-140">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="3573e-141">Se muestra una lista de atributos para el gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="3573e-141">A list of attributes for the bar chart is displayed.</span></span>  
  
6.  <span data-ttu-id="3573e-142">Seleccione un valor para la propiedad BarLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="3573e-142">Select a value for the BarLabelStyle property.</span></span>  
  
 <span data-ttu-id="3573e-143">Si el estilo de la etiqueta de la barra se establece en `Outside`, la etiqueta se colocará fuera de la barra, siempre y cuando quepa en el área del gráfico.</span><span class="sxs-lookup"><span data-stu-id="3573e-143">When the bar label style is set to `Outside`, the labels will be placed outside of the bar, as long as it fits in the chart area.</span></span> <span data-ttu-id="3573e-144">Si la etiqueta no se puede colocar fuera de la barra, pero sí dentro del área del gráfico, la etiqueta se situará dentro de la barra en la posición más próxima al extremo de la misma.</span><span class="sxs-lookup"><span data-stu-id="3573e-144">If the label cannot be placed outside of the bar but inside of the chart area, the label is placed inside the bar at the position closest to the end of the bar.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-an-area-column-line-or-scatter-chart"></a><span data-ttu-id="3573e-145">Para cambiar la posición de las etiquetas de punto de datos en una gráfico de áreas, de columnas, de líneas o de dispersión</span><span class="sxs-lookup"><span data-stu-id="3573e-145">To change the position of point labels in an Area, Column, Line or Scatter chart</span></span>  
  
1.  <span data-ttu-id="3573e-146">Cree un gráfico de áreas, de columnas, de líneas o de dispersión.</span><span class="sxs-lookup"><span data-stu-id="3573e-146">Create an Area, Column, Line or Scatter chart.</span></span>  
  
2.  <span data-ttu-id="3573e-147">En la superficie de diseño, haga clic con el botón derecho en el gráfico y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="3573e-147">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="3573e-148">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-148">Open the Properties pane.</span></span> <span data-ttu-id="3573e-149">En la pestaña **Ver** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3573e-149">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="3573e-150">En la superficie de diseño, haga clic en la serie.</span><span class="sxs-lookup"><span data-stu-id="3573e-150">On the design surface, click the series.</span></span> <span data-ttu-id="3573e-151">Las propiedades de la serie se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3573e-151">The properties for the series are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="3573e-152">En la sección **Datos** , expanda el nodo **DataPoint** y, a continuación, expanda el nodo **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="3573e-152">In the **Data** section, expand the **DataPoint** node, then expand the **Label**node.</span></span>  
  
6.  <span data-ttu-id="3573e-153">Seleccione un valor para la propiedad Position.</span><span class="sxs-lookup"><span data-stu-id="3573e-153">Select a value for the Position property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3573e-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3573e-154">See Also</span></span>  
 <span data-ttu-id="3573e-155">[Gráficos circulares &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3573e-155">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3573e-156">[Gráficos de barras &#40;Generador de informes y SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3573e-156">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3573e-157">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3573e-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3573e-158">[Aplicar formato de fecha o de moneda a las etiquetas de los ejes &#40;Generador de informes y SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3573e-158">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3573e-159">[Mostrar las etiquetas de los puntos de datos fuera de un gráfico circular &#40;Generador de informes y SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3573e-159">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3573e-160">Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3573e-160">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
  
  
