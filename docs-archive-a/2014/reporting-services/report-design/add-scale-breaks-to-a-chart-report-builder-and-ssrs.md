---
title: Agregar quiebres de escala a un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 84d66436-ed62-4967-bbbd-b457593ee787
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c081debd1e0a84158615edebdb6b84705c10e5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747470"
---
# <a name="add-scale-breaks-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="ef879-102">Agregar quiebres de escala a un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="ef879-102">Add Scale Breaks to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ef879-103">Un quiebre de escala es una franja dibujada a través del área de trazado de un gráfico para hacer ver una interrupción en la continuidad entre los valores altos y bajos de un eje de valores (habitualmente, el eje Y o eje vertical).</span><span class="sxs-lookup"><span data-stu-id="ef879-103">A scale break is a stripe drawn across the plotting area of a chart to denote a break in continuity between the high and low values on a value axis (usually the vertical, or y-axis).</span></span> <span data-ttu-id="ef879-104">Use un quiebre de escala para mostrar dos intervalos definidos dentro de la misma área del gráfico.</span><span class="sxs-lookup"><span data-stu-id="ef879-104">Use a scale break to display two distinct ranges in the same chart area.</span></span>  
  
 <span data-ttu-id="ef879-105">![Gráfico con quiebre de escala](../media/rs-multipledatarangeschart-scalebreak.gif "Gráfico con quiebre de escala")</span><span class="sxs-lookup"><span data-stu-id="ef879-105">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef879-106">No puede especificar dónde se debe colocar un quiebre de escala en un gráfico.</span><span class="sxs-lookup"><span data-stu-id="ef879-106">You cannot specify where to place a scale break on your chart.</span></span> <span data-ttu-id="ef879-107">El gráfico utiliza sus propios cálculos basados en los valores del conjunto de datos para determinar si hay separación suficiente entre los intervalos de datos para dibujar un quiebre de escala en el eje de valores (eje Y) en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ef879-107">The chart uses its own calculations based on the values in your dataset to determine whether there is sufficient separation between data ranges to draw a scale break on the value axis (y-axis) at run time.</span></span>  
  
 <span data-ttu-id="ef879-108">Un ejemplo de un gráfico con quiebres de escala está disponible como informe de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef879-108">An example of a chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="ef879-109">Para más información acerca de cómo descargar este y otros informes de ejemplo, consulte el tema sobre [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][informes de ejemplo del Generador de informes y el Diseñador de informes](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="ef879-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-scale-breaks-on-the-chart"></a><span data-ttu-id="ef879-110">Para habilitar quiebres de escala en el gráfico</span><span class="sxs-lookup"><span data-stu-id="ef879-110">To enable scale breaks on the chart</span></span>  
  
1.  <span data-ttu-id="ef879-111">Haga clic con el botón derecho en el eje vertical y, después, haga clic en **Propiedades del eje**.</span><span class="sxs-lookup"><span data-stu-id="ef879-111">Right-click the vertical axis and then click **Axis Properties**.</span></span> <span data-ttu-id="ef879-112">Se abrirá el cuadro de diálogo **Propiedades del eje vertical** .</span><span class="sxs-lookup"><span data-stu-id="ef879-112">The **VerticalAxis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="ef879-113">Active la casilla **Habilitar quiebres de escala** .</span><span class="sxs-lookup"><span data-stu-id="ef879-113">Select the **Enable scale breaks** check box.</span></span>  
  
### <a name="to-change-the-style-of-the-scale-break"></a><span data-ttu-id="ef879-114">Para cambiar el estilo del quiebre de escala</span><span class="sxs-lookup"><span data-stu-id="ef879-114">To change the style of the scale break</span></span>  
  
1.  <span data-ttu-id="ef879-115">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="ef879-115">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="ef879-116">En la superficie de diseño, haga clic con el botón secundario en el eje Y del gráfico.</span><span class="sxs-lookup"><span data-stu-id="ef879-116">On the design surface, right-click on the y-axis of the chart.</span></span> <span data-ttu-id="ef879-117">Las propiedades para el objeto del eje Y (que, de forma predeterminada, se denomina Eje del gráfico) se muestran en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="ef879-117">The properties for the y-axis object (named Chart Axis by default) are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="ef879-118">En la sección **Scale** , expanda la propiedad ScaleBreakStyle.</span><span class="sxs-lookup"><span data-stu-id="ef879-118">In the **Scale** section, expand the ScaleBreakStyle property.</span></span>  
  
4.  <span data-ttu-id="ef879-119">Cambie los valores de las propiedades de ScaleBreakStyle, como BreakLineType y Spacing.</span><span class="sxs-lookup"><span data-stu-id="ef879-119">Change the values for ScaleBreakStyle properties, such as BreakLineType and Spacing.</span></span> <span data-ttu-id="ef879-120">Para más información sobre las propiedades de quiebres de escala, vea [Mostrar una serie con varios rangos de datos en un gráfico &#40;Generador de informes y SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span><span class="sxs-lookup"><span data-stu-id="ef879-120">For more information about scale break properties, see [Displaying a Series with Multiple Data Ranges on a Chart &#40;Report Builder and SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef879-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef879-121">See Also</span></span>  
 <span data-ttu-id="ef879-122">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef879-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ef879-123">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef879-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ef879-124">Cuadro de diálogo Propiedades del eje, Opciones del eje &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ef879-124">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
