---
title: Especificar un área de gráfico para una serie (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10157"
- sql12.rtp.rptdesigner.chartareaproperties.alignment.f1
ms.assetid: dc3c365b-c263-402a-bf6f-c2a7081db073
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483bc6d2fa4aa079c95e9dbd03e18c71d7b13abf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662537"
---
# <a name="specify-a-chart-area-for-a-series-report-builder-and-ssrs"></a><span data-ttu-id="835ac-102">Especificar un área de gráfico para una serie (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="835ac-102">Specify a Chart Area for a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="835ac-103">El gráfico es el contenedor de nivel superior que incluye el borde exterior, el título del gráfico y la leyenda.</span><span class="sxs-lookup"><span data-stu-id="835ac-103">The chart is the top-level container that includes the outer border, the chart title, and the legend.</span></span> <span data-ttu-id="835ac-104">De forma predeterminada, el gráfico contiene un área de gráfico predeterminada.</span><span class="sxs-lookup"><span data-stu-id="835ac-104">By default, the chart contains one default chart area.</span></span> <span data-ttu-id="835ac-105">El área de gráfico no está visible en la superficie del gráfico, pero puede imaginarla como un contenedor que incluye únicamente las etiquetas del eje, el título del eje y el área de trazado de una o más series.</span><span class="sxs-lookup"><span data-stu-id="835ac-105">The chart area is not visible on the chart surface, but you can think of the chart area as a container that encompasses only the axis labels, the axis title and the plotting area of one or more series.</span></span> <span data-ttu-id="835ac-106">En la ilustración siguiente se muestra el concepto de áreas de gráfico dentro de un único gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-106">The following illustration shows the concept of chart areas within a single chart.</span></span>  
  
 <span data-ttu-id="835ac-107">![Muestra un diagrama de un área de gráfico](../media/chartareasdiagram.gif "Muestra un diagrama de un área de gráfico")</span><span class="sxs-lookup"><span data-stu-id="835ac-107">![Shows a diagram of a chart area](../media/chartareasdiagram.gif "Shows a diagram of a chart area")</span></span>  
  
 <span data-ttu-id="835ac-108">De forma predeterminada, todas las series se agregan al área de gráfico predeterminada.</span><span class="sxs-lookup"><span data-stu-id="835ac-108">By default, all series are added to the default chart area.</span></span> <span data-ttu-id="835ac-109">Cuando se usan gráficos de áreas, de columnas, de líneas y de dispersión, cualquier combinación de estas series se puede mostrar en la misma área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-109">When using area, column, line, and scatter charts, any combination of these series can be displayed on the same chart area.</span></span> <span data-ttu-id="835ac-110">Si tiene varias series en la misma área de gráfico, se reducirá la legibilidad del gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-110">If you have several series in the same chart area, the readability of the chart is reduced.</span></span> <span data-ttu-id="835ac-111">Es recomendable separar los tipos de gráfico en varias áreas de gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-111">You may want to separate the chart types into multiple chart areas.</span></span> <span data-ttu-id="835ac-112">El uso de varias áreas de gráfico aumentará la legibilidad, facilitando las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="835ac-112">Using multiple chart areas will increase readability for easier comparisons.</span></span> <span data-ttu-id="835ac-113">Por ejemplo, los gráficos de cotizaciones de volumen y precios suelen tener intervalos de valores diferentes, pero se pueden realizar comparaciones entre los datos de volumen y de precio durante el mismo período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="835ac-113">For example, price-volume stock charts often have different ranges of values, but comparisons can be made between the price and volume data over the same period of time.</span></span>  
  
 <span data-ttu-id="835ac-114">Las series de tipo barras, polar o de formas solo se pueden combinar con series de los mismos tipos de gráfico en la misma área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-114">The bar, polar, or shape series can only be combined with series of the same chart types in the same chart area.</span></span> <span data-ttu-id="835ac-115">Si usa un gráfico polar o de formas, considere la posibilidad de usar una región de datos independiente para cada campo que desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="835ac-115">If you are using a Polar or Shape chart, consider using a separate chart data region for each field that you wish to show.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-series-with-a-new-chart-area"></a><span data-ttu-id="835ac-116">Para asociar una serie a una nueva área de gráfico</span><span class="sxs-lookup"><span data-stu-id="835ac-116">To associate a series with a new chart area</span></span>  
  
1.  <span data-ttu-id="835ac-117">Haga clic con el botón derecho en cualquier lugar del gráfico y seleccione **Agregar una nueva área de gráfico**.</span><span class="sxs-lookup"><span data-stu-id="835ac-117">Right-click anywhere on the chart and select **Add New Chart Area**.</span></span> <span data-ttu-id="835ac-118">Aparecerá una nueva área de gráfico en blanco en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-118">A new, blank chart area appears on the chart.</span></span>  
  
2.  <span data-ttu-id="835ac-119">Haga clic con el botón derecho en la serie del gráfico o en un campo de serie o de datos en la zona apropiada del panel Datos del gráfico y, después, haga clic en **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="835ac-119">Right-click the series on the chart or right-click a series or data field in the appropriate area in the Chart Data pane, and then click **Series Properties**.</span></span>  
  
3.  <span data-ttu-id="835ac-120">En **Ejes y área del gráfico**, seleccione el área de gráfico en la que desea mostrar la serie.</span><span class="sxs-lookup"><span data-stu-id="835ac-120">In **Axes and Chart Areas**, select the chart area that you want the series to be shown in.</span></span>  
  
4.  <span data-ttu-id="835ac-121">(Opcional) Alinee verticalmente las áreas de gráfico.</span><span class="sxs-lookup"><span data-stu-id="835ac-121">(Optional) Align the chart areas vertically.</span></span> <span data-ttu-id="835ac-122">Para ello, haga clic con el botón derecho en el gráfico y seleccione **Propiedades del área de gráfico**.</span><span class="sxs-lookup"><span data-stu-id="835ac-122">To do this, right-click the chart and select **Chart Area Properties**.</span></span> <span data-ttu-id="835ac-123">En **Alineación**, seleccione el área de gráfico con la que desea alinear el área de gráfico seleccionada.</span><span class="sxs-lookup"><span data-stu-id="835ac-123">In **Alignment**, select another chart area that you want to align the selected chart area with.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835ac-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="835ac-124">See Also</span></span>  
 <span data-ttu-id="835ac-125">[Mostrar varias series en un gráfico &#40;Generador de informes y SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="835ac-125">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="835ac-126">[Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="835ac-126">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="835ac-127">[Definir los colores de un gráfico mediante una paleta &#40;Generador de informes y SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="835ac-127">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="835ac-128">[Gráficos polares &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="835ac-128">[Polar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="835ac-129">[Gráficos de formas &#40;Generador de informes y SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="835ac-129">[Shape Charts &#40;Report Builder and SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="835ac-130">Gráficos circulares &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="835ac-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)  
  
  
