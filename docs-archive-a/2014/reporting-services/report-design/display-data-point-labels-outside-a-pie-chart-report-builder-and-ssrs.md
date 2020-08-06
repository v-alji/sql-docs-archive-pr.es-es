---
title: Mostrar las etiquetas de los puntos de datos fuera de un gráfico circular (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 959b7574-cf43-470b-b592-4944d8a9948f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dd4f38f24d2729acacfa3520635b93d8af2e9433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748006"
---
# <a name="display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="8f084-102">Mostrar las etiquetas de los puntos de datos fuera de un gráfico circular (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="8f084-102">Display Data Point Labels Outside a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8f084-103">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], el etiquetado de los gráficos circulares está optimizado, por lo que las etiquetas se muestran solo en varios segmentos de datos.</span><span class="sxs-lookup"><span data-stu-id="8f084-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pie chart labeling is optimized to display labels on only several slices of data.</span></span> <span data-ttu-id="8f084-104">Si el gráfico circular contiene demasiados segmentos, las etiquetas se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="8f084-104">Labels may overlap if the pie chart contains too many slices.</span></span> <span data-ttu-id="8f084-105">Una solución consiste en mostrar las etiquetas fuera del gráfico circular, lo que puede crear más espacio para las etiquetas de datos más largas.</span><span class="sxs-lookup"><span data-stu-id="8f084-105">One solution is to display the labels outside the pie chart, which may create more room for longer data labels.</span></span> <span data-ttu-id="8f084-106">Si las etiquetas siguen solapándose, habilite 3D para crear más espacio.</span><span class="sxs-lookup"><span data-stu-id="8f084-106">If you find that your labels still overlap, you can create more space for them by enabling 3D.</span></span> <span data-ttu-id="8f084-107">Esto reduce el diámetro del gráfico circular, lo que crea más espacio alrededor del gráfico.</span><span class="sxs-lookup"><span data-stu-id="8f084-107">This reduces the diameter of the pie chart, creating more space around the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-data-point-labels-inside-a-pie-chart"></a><span data-ttu-id="8f084-108">Para mostrar las etiquetas de los puntos de datos dentro de un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="8f084-108">To display data point labels inside a pie chart</span></span>  
  
1.  <span data-ttu-id="8f084-109">Agregue un gráfico circular al informe.</span><span class="sxs-lookup"><span data-stu-id="8f084-109">Add a pie chart to your report.</span></span> <span data-ttu-id="8f084-110">Para más información, vea [Agregar un gráfico a un informe &#40;Generador de informes y SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8f084-110">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="8f084-111">En la superficie de diseño, haga clic con el botón derecho en el gráfico y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="8f084-111">On the design surface, right-click on the chart and select **Show Data Labels**.</span></span>  
  
### <a name="to-display-data-point-labels-outside-a-pie-chart"></a><span data-ttu-id="8f084-112">Para mostrar las etiquetas de los puntos de datos fuera de un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="8f084-112">To display data point labels outside a pie chart</span></span>  
  
1.  <span data-ttu-id="8f084-113">Cree un gráfico circular y muestre las etiquetas de datos.</span><span class="sxs-lookup"><span data-stu-id="8f084-113">Create a pie chart and display the data labels.</span></span>  
  
2.  <span data-ttu-id="8f084-114">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8f084-114">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="8f084-115">En la superficie de diseño, haga clic en el propio gráfico para mostrar las propiedades **Category** en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8f084-115">On the design surface, click on the pie itself to display the **Category** properties in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="8f084-116">Expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="8f084-116">Expand the **CustomAttributes** node.</span></span> <span data-ttu-id="8f084-117">Se muestra una lista de atributos para el gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="8f084-117">A list of attributes for the pie chart is displayed.</span></span>  
  
5.  <span data-ttu-id="8f084-118">Establezca la propiedad **PieLabelStyle** en **Externa**.</span><span class="sxs-lookup"><span data-stu-id="8f084-118">Set the **PieLabelStyle** property to **Outside**.</span></span>  
  
6.  <span data-ttu-id="8f084-119">Establezca la `PieLineColor` propiedad en **negro**.</span><span class="sxs-lookup"><span data-stu-id="8f084-119">Set the `PieLineColor` property to **Black**.</span></span> <span data-ttu-id="8f084-120">La propiedad PieLineColor define las líneas de llamada para cada etiqueta de punto de datos.</span><span class="sxs-lookup"><span data-stu-id="8f084-120">The PieLineColor property defines callout lines for each data point label.</span></span>  
  
### <a name="to-prevent-overlapping-labels-displayed-outside-a-pie-chart"></a><span data-ttu-id="8f084-121">Para evitar que las etiquetas mostradas fuera de un gráfico circular se superpongan</span><span class="sxs-lookup"><span data-stu-id="8f084-121">To prevent overlapping labels displayed outside a pie chart</span></span>  
  
1.  <span data-ttu-id="8f084-122">Cree un gráfico circular con etiquetas externas.</span><span class="sxs-lookup"><span data-stu-id="8f084-122">Create a pie chart with external labels.</span></span>  
  
2.  <span data-ttu-id="8f084-123">En la superficie de diseño, haga clic con el botón derecho fuera del gráfico circular pero dentro de los límites del gráfico y seleccione **Propiedades del área de gráfico**. Aparecerá el cuadro de diálogo **Propiedades del área de gráfico** .</span><span class="sxs-lookup"><span data-stu-id="8f084-123">On the design surface, right-click outside the pie chart but inside the chart borders and select **Chart Area Properties**.The **Chart AreaProperties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="8f084-124">En la pestaña **Opciones 3D** , seleccione **Habilitar 3D**.</span><span class="sxs-lookup"><span data-stu-id="8f084-124">On the **3D Options** tab, select **Enable 3D**.</span></span>  
  
4.  <span data-ttu-id="8f084-125">Si quiere que el gráfico tenga más espacio para las etiquetas, pero que siga pareciendo bidimensional, establezca las propiedades **Rotation** e **Inclination** en **0**.</span><span class="sxs-lookup"><span data-stu-id="8f084-125">If you want the chart to have more room for labels but still appear two-dimensional, set the **Rotation** and **Inclination** properties to **0**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f084-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f084-126">See Also</span></span>  
 <span data-ttu-id="8f084-127">[Gráficos circulares &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f084-127">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f084-128">[Recopilar segmentos pequeños en un gráfico circular &#40;Generador de informes y SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f084-128">[Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8f084-129">Mostrar valores de porcentaje en un gráfico circular &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f084-129">Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
