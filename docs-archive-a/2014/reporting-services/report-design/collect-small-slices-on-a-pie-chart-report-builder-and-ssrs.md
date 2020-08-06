---
title: Recopilar segmentos pequeños en un gráfico circular (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673495"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="0b950-102">Recopilar segmentos pequeños en un gráfico circular (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0b950-102">Collect Small Slices on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0b950-103">Si los gráficos circulares muestran demasiados puntos de datos, pueden parecer desordenados.</span><span class="sxs-lookup"><span data-stu-id="0b950-103">When pie charts display too many points of data, they begin to look cluttered.</span></span> <span data-ttu-id="0b950-104">Para resolver este problema, puede mostrar como un único sector en el gráfico circular todos los datos que estén por debajo de un determinado valor.</span><span class="sxs-lookup"><span data-stu-id="0b950-104">To resolve this issue, you can show all data that falls beneath a certain value as one slice on the pie chart.</span></span>  
  
 <span data-ttu-id="0b950-105">Para recopilar sectores pequeños en un solo sector, en primer lugar debe decidir si el umbral de recopilación de sectores pequeños será un porcentaje del gráfico circular o un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="0b950-105">To collect small slices into one slice, first decide whether your threshold for collecting small slices is measured as a percentage of the pie chart or as a fixed value.</span></span> <span data-ttu-id="0b950-106">A continuación, establezca las propiedades CollectedThreshold y CollectedThresholdUsePercent. Establezca la propiedad CollectedThreshold como el porcentaje del gráfico de un valor que debe quedarse por debajo para que se realice la recopilación o el valor de datos del umbral real de la colección.</span><span class="sxs-lookup"><span data-stu-id="0b950-106">Then set the CollectedThreshold and CollectedThresholdUsePercent properties.Set the CollectedThreshold property to either the percentage of the chart that a value must fall below to be collected, or the actual threshold data value for collection.</span></span> <span data-ttu-id="0b950-107">Establezca la propiedad CollectedThresholdUsePercent en `True` para utilizar un porcentaje o `False` para usar un valor real.</span><span class="sxs-lookup"><span data-stu-id="0b950-107">Set the CollectedThresholdUsePercent property to `True` to use a percentage or `False` to use an actual value.</span></span>  
  
 <span data-ttu-id="0b950-108">También puede recopilar sectores pequeños en un segundo gráfico circular al que se llamará desde un sector recopilado del primer gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="0b950-108">You can also collect small slices into a second pie chart that is called out from a collected slice of the first pie chart.</span></span> <span data-ttu-id="0b950-109">El segundo gráfico circular se dibuja a la derecha del gráfico circular original.</span><span class="sxs-lookup"><span data-stu-id="0b950-109">The second pie chart is drawn to the right of the original pie chart.</span></span>  
  
 <span data-ttu-id="0b950-110">En los gráficos de embudo y en los piramidales, no es posible combinar varios sectores en uno solo.</span><span class="sxs-lookup"><span data-stu-id="0b950-110">You cannot combine slices of funnel or pyramid charts into one slice.</span></span>  
  
 <span data-ttu-id="0b950-111">Un ejemplo de este gráfico está disponible como informe de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0b950-111">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="0b950-112">Para más información acerca de cómo descargar este y otros informes de ejemplo, consulte el tema sobre [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][informes de ejemplo del Generador de informes y el Diseñador de informes](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="0b950-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a><span data-ttu-id="0b950-113">Para recopilar sectores pequeños en un solo sector de un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="0b950-113">To collect small slices into a single slice on a pie chart</span></span>  
  
1.  <span data-ttu-id="0b950-114">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b950-114">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="0b950-115">En la superficie de diseño, haga clic en cualquier sector del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="0b950-115">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="0b950-116">Las propiedades de la serie se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b950-116">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="0b950-117">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="0b950-117">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="0b950-118">Establezca la propiedad CollectedStyle en **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="0b950-118">Set the CollectedStyle property to **SingleSlice**.</span></span>  
  
5.  <span data-ttu-id="0b950-119">Establezca el valor del umbral de recopilación y el tipo de umbral.</span><span class="sxs-lookup"><span data-stu-id="0b950-119">Set the collected threshold value and type of threshold.</span></span> <span data-ttu-id="0b950-120">En los ejemplos siguientes se muestran formas habituales de establecer umbrales de recopilación.</span><span class="sxs-lookup"><span data-stu-id="0b950-120">The following examples are common ways of setting collected thresholds.</span></span>  
  
    -   <span data-ttu-id="0b950-121">**Por porcentaje.**</span><span class="sxs-lookup"><span data-stu-id="0b950-121">**By percentage.**</span></span> <span data-ttu-id="0b950-122">Por ejemplo, para recopilar en un solo sector cualquier sector del gráfico circular que esté por debajo del 10%:</span><span class="sxs-lookup"><span data-stu-id="0b950-122">For example, to collect any slice on your pie chart that is less than 10% into a single slice:</span></span>  
  
         <span data-ttu-id="0b950-123">Establezca la propiedad CollectedThresholdUsePercent en `True` .</span><span class="sxs-lookup"><span data-stu-id="0b950-123">Set the CollectedThresholdUsePercent property to `True`.</span></span>  
  
         <span data-ttu-id="0b950-124">Establezca la propiedad CollectedThreshold en **10**.</span><span class="sxs-lookup"><span data-stu-id="0b950-124">Set the CollectedThreshold property to **10**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0b950-125">Si establece CollectedStyle en **SingleSlice**, CollectedThreshold en un valor mayor que **100**y CollectedThresholdUsePercent es `True` , el gráfico producirá una excepción porque no puede calcular un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="0b950-125">If you set CollectedStyle to **SingleSlice**, CollectedThreshold to a value greater than **100**, and CollectedThresholdUsePercent is `True`, the chart will throw an exception because it cannot calculate a percentage.</span></span> <span data-ttu-id="0b950-126">Para resolver este problema, establezca CollectedThreshold en un valor menor que **100**.</span><span class="sxs-lookup"><span data-stu-id="0b950-126">To resolve this issue, set the CollectedThreshold to a value less than **100**.</span></span>  
  
    -   <span data-ttu-id="0b950-127">**Por valor de datos.**</span><span class="sxs-lookup"><span data-stu-id="0b950-127">**By data value.**</span></span> <span data-ttu-id="0b950-128">Por ejemplo, para recopilar en un solo sector cualquier sector del gráfico circular que esté por debajo de 5000:</span><span class="sxs-lookup"><span data-stu-id="0b950-128">For example, to collect any slice on your pie chart that is less than 5000 into a single slice:</span></span>  
  
         <span data-ttu-id="0b950-129">Establezca la propiedad CollectedThresholdUsePercent en `False` .</span><span class="sxs-lookup"><span data-stu-id="0b950-129">Set the CollectedThresholdUsePercent property to `False`.</span></span>  
  
         <span data-ttu-id="0b950-130">Establezca la propiedad CollectedThreshold en **5000**.</span><span class="sxs-lookup"><span data-stu-id="0b950-130">Set the CollectedThreshold property to **5000**.</span></span>  
  
6.  <span data-ttu-id="0b950-131">Establezca la propiedad CollectedLabel en una cadena que represente la etiqueta de texto que se mostrará en el sector recopilado.</span><span class="sxs-lookup"><span data-stu-id="0b950-131">Set the CollectedLabel property to a string that represents the text label that will be shown on the collected slice.</span></span>  
  
7.  <span data-ttu-id="0b950-132">(Opcional) Establezca las propiedades CollectedSliceExploded, CollectedColor, CollectedLegendText y CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="0b950-132">(Optional) Set the CollectedSliceExploded, CollectedColor, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="0b950-133">Estas propiedades cambian el aspecto, el color, el texto de la etiqueta, el texto de la leyenda y la información sobre herramientas del sector simple.</span><span class="sxs-lookup"><span data-stu-id="0b950-133">These properties change the appearance, color, label text, legend text and tooltip aspects of the single slice.</span></span>  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a><span data-ttu-id="0b950-134">Para recopilar sectores pequeños en un gráfico circular secundario con llamada</span><span class="sxs-lookup"><span data-stu-id="0b950-134">To collect small slices into a secondary, callout pie chart</span></span>  
  
1.  <span data-ttu-id="0b950-135">Siga los pasos 1 a 3 descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0b950-135">Follow Steps 1-3 from above.</span></span>  
  
2.  <span data-ttu-id="0b950-136">Establezca la propiedad CollectedStyle en **CollectedPie**.</span><span class="sxs-lookup"><span data-stu-id="0b950-136">Set the CollectedStyle property to **CollectedPie**.</span></span>  
  
3.  <span data-ttu-id="0b950-137">Establezca la propiedad CollectedThreshold en un valor que represente el umbral de recopilación de los sectores pequeños en un solo sector.</span><span class="sxs-lookup"><span data-stu-id="0b950-137">Set the CollectedThresholdproperty to a value that represents the threshold at which small slices will be collected into one slice.</span></span> <span data-ttu-id="0b950-138">Cuando la propiedad CollectedStyle se establece en **CollectedPie**, CollectedThresholdUsePercentproperty siempre se establece en `True` y el umbral recopilado siempre se mide en porcentaje.</span><span class="sxs-lookup"><span data-stu-id="0b950-138">When the CollectedStyle property is set to **CollectedPie**, the CollectedThresholdUsePercentproperty is always set to `True`, and the collected threshold is always measured in percent.</span></span>  
  
4.  <span data-ttu-id="0b950-139">(Opcional) Establezca las propiedades CollectedColor, CollectedLabel, CollectedLegendText y CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="0b950-139">(Optional) Set the CollectedColor, CollectedLabel, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="0b950-140">El resto de las propiedades denominadas "Collected" no se aplican al gráfico circular recopilado.</span><span class="sxs-lookup"><span data-stu-id="0b950-140">All other properties named "Collected" do not apply to the collected pie.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b950-141">El gráfico circular secundario se calcula en función de los sectores pequeños existentes en los datos, por lo que solo se ve en Vista previa.</span><span class="sxs-lookup"><span data-stu-id="0b950-141">The secondary pie chart is calculated based on the small slices in your data so it will only appear in Preview.</span></span> <span data-ttu-id="0b950-142">No aparece en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="0b950-142">It does not appear on the design surface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b950-143">No puede dar formato al gráfico circular secundario.</span><span class="sxs-lookup"><span data-stu-id="0b950-143">You cannot format the secondary pie chart.</span></span> <span data-ttu-id="0b950-144">Por esta razón, a la hora de recopilar sectores del gráfico circular se recomienda el uso del primer enfoque.</span><span class="sxs-lookup"><span data-stu-id="0b950-144">For this reason, it is strongly recommended to use the first approach when collecting pie slices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b950-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b950-145">See Also</span></span>  
 <span data-ttu-id="0b950-146">[Gráficos circulares &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0b950-146">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0b950-147">[Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0b950-147">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0b950-148">[Mostrar las etiquetas de los puntos de datos fuera de un gráfico circular &#40;Generador de informes y SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0b950-148">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0b950-149">[Mostrar valores de porcentaje en un gráfico circular &#40;Generador de informes y SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0b950-149">[Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0b950-150">Agregar efectos 3D a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0b950-150">Add 3D Effects to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-3d-effects-report-builder.md)  
  
  
