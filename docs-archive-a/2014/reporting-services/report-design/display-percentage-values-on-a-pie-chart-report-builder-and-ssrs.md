---
title: Mostrar valores de porcentaje en un gráfico circular (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672729"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="6dc8d-102">Mostrar valores de porcentaje en un gráfico circular (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6dc8d-102">Display Percentage Values on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6dc8d-103">De forma predeterminada, las categorías se muestran en la leyenda para identificar cada valor.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-103">By default, categories are shown in the legend to identify each value.</span></span> <span data-ttu-id="6dc8d-104">Si ha etiquetado el gráfico circular con etiquetas de categoría, es probable que le interese mostrar los porcentajes en la leyenda.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-104">If you have labeled the pie chart using category labels, you may want show percentages in the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="6dc8d-105">Para mostrar los valores de porcentaje como etiquetas en un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="6dc8d-105">To display percentage values as labels on a pie chart</span></span>  
  
1.  <span data-ttu-id="6dc8d-106">Agregue un gráfico circular al informe.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-106">Add a pie chart to your report.</span></span> <span data-ttu-id="6dc8d-107">Para más información, vea [Agregar un gráfico a un informe &#40;Generador de informes y SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6dc8d-107">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="6dc8d-108">En la superficie de diseño, haga clic con el botón derecho en gráfico circular y seleccione **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-108">On the design surface, right-click on the pie and select **Show Data Labels**.</span></span> <span data-ttu-id="6dc8d-109">Las etiquetas de datos aparecerán dentro de cada sector del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-109">The data labels should appear within each slice on the pie chart.</span></span>  
  
3.  <span data-ttu-id="6dc8d-110">En la superficie de diseño, haga clic con el botón secundario en las etiquetas y seleccione **Propiedades de la etiqueta de la serie**.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-110">On the design surface, right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="6dc8d-111">Aparece el cuadro de diálogo **Propiedades de la etiqueta de la serie** .</span><span class="sxs-lookup"><span data-stu-id="6dc8d-111">The **Series Label Properties** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="6dc8d-112">Escriba `#PERCENT` para la opción **datos de etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="6dc8d-112">Type `#PERCENT` for the **Label data** option.</span></span>  
  
5.  <span data-ttu-id="6dc8d-113">(Opcional) Para especificar el número de posiciones decimales que se deben mostrar en la etiqueta, escriba "#PERCENT{P*n*}", donde *n* es el número de posiciones decimales que se deben mostrar.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-113">(Optional) To specify how many decimal places the label shows, type "#PERCENT{P*n*}" where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="6dc8d-114">Por ejemplo, para no mostrar ninguna posición decimal, escriba "#PERCENT{P0}".</span><span class="sxs-lookup"><span data-stu-id="6dc8d-114">For example, to display no decimal places, type "#PERCENT{P0}".</span></span>  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a><span data-ttu-id="6dc8d-115">Para mostrar los valores de porcentaje en la leyenda de un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="6dc8d-115">To display percentage values in the legend of a pie chart</span></span>  
  
1.  <span data-ttu-id="6dc8d-116">En la superficie de diseño, haga clic con el botón secundario en el gráfico circular y seleccione **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="6dc8d-116">On the design surface, right-click on the pie chart and select **Series Properties**.</span></span> <span data-ttu-id="6dc8d-117">Aparece el cuadro de diálogo **Propiedades de la serie** .</span><span class="sxs-lookup"><span data-stu-id="6dc8d-117">The **Series Properties** dialog box displays.</span></span>  
  
2.  <span data-ttu-id="6dc8d-118">En **leyenda**, escriba `#PERCENT` para la propiedad **texto de leyenda personalizado** .</span><span class="sxs-lookup"><span data-stu-id="6dc8d-118">In **Legend**, type `#PERCENT` for the **Custom legend text** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc8d-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6dc8d-119">See Also</span></span>  
 <span data-ttu-id="6dc8d-120">[Gráficos circulares &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6dc8d-120">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6dc8d-121">[Aplicar formato a la leyenda de un gráfico &#40;Generador de informes y SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6dc8d-121">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="6dc8d-122">[Mostrar las etiquetas de los puntos de datos fuera de un gráfico circular &#40;Generador de informes y SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6dc8d-122">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6dc8d-123">Recopilar segmentos pequeños en un gráfico circular &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6dc8d-123">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
