---
title: Aplicar formato a un gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10214"
- sql12.rtp.rptdesigner.calculatedseriesproperties.fill.f1
- sql12.rtp.rptdesigner.serieslabelproperties.fill.f1
- sql12.rtp.rptdesigner.legendproperties.fill.f1
- "10149"
- sql12.rtp.rptdesigner.seriesproperties.shadow.f1
- sql12.rtp.rptdesigner.seriesproperties.markers.f1
- "10255"
- sql12.rtp.rptdesigner.charttitleproperties.fill.f1
- "10154"
- "10170"
- "10173"
- sql12.rtp.rptdesigner.seriesproperties.fill.f1
- "10169"
- "10158"
- sql12.rtp.rptdesigner.chartareaproperties.fill.f1
- sql12.rtp.rptdesigner.charttitleproperties.shadow.f1
- "10246"
- "10150"
- sql12.rtp.rptdesigner.calculatedseriesproperties.borders.f1
- sql12.rtp.rptdesigner.chartproperties.fill.f1
- "10159"
- sql12.rtp.rptdesigner.majorgridlineproperties.gridlineoptions.f1
- "10160"
- sql12.rtp.rptdesigner.serieslabelproperties.font.f1
- "10182"
- "10163"
- "10164"
- "10253"
- "10216"
- "10171"
- "10257"
- sql12.rtp.rptdesigner.chartareaproperties.border.f1
- sql12.rtp.rptdesigner.calculatedseriesproperties.shadow.f1
- sql12.rtp.rptdesigner.chartproperties.border.f1
- sql12.rtp.rptdesigner.minorgridlineproperties.gridlineoptions.f1
- sql12.rtp.rptdesigner.chartareaproperties.shadow.f1
- sql12.rtp.rptdesigner.charttitleproperties.borders.f1
- sql12.rtp.rptdesigner.charttitleproperties.font.f1
- "10247"
ms.assetid: d3984300-c766-42f8-b7c4-863123d67c99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af164d4db9b6439f0634d113652b95939827b0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671379"
---
# <a name="formatting-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="1e299-102">Aplicar formato a un gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="1e299-102">Formatting a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1e299-103">Después de definir los datos para el gráfico y su aspecto, puede aplicar formato para mejorar su aspecto general y resaltar los puntos de datos clave.</span><span class="sxs-lookup"><span data-stu-id="1e299-103">After you have defined the data for your chart and it is appearing the way you want, you can add formatting to improve the overall appearance and highlight key data points.</span></span> <span data-ttu-id="1e299-104">Las opciones de formato más comunes se pueden modificar desde el cuadro de diálogo de propiedades; estas opciones se muestran al hacer clic con el botón secundario en un elemento de gráfico para ver su menú contextual.</span><span class="sxs-lookup"><span data-stu-id="1e299-104">The most common formatting options can be modified from the Properties dialog box that are found when you right-click a chart element to display its shortcut menu.</span></span> <span data-ttu-id="1e299-105">Cada elemento de gráfico dispone de su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1e299-105">Each chart element has its own dialog box.</span></span> <span data-ttu-id="1e299-106">Para más información sobre los elementos de gráfico, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1e299-106">For more information about chart elements, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="1e299-107">Aunque todas las propiedades relacionadas con el gráfico se encuentran en el panel de propiedades, muchas de estas propiedades también se pueden establecer desde un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1e299-107">All properties that relate to the chart are located in the Properties pane, but many of these properties can also be set from a dialog box.</span></span> <span data-ttu-id="1e299-108">Mientras da formato a la serie, puede usar atributos personalizados para especificar propiedades específicas de la serie (estos atributos solo se encuentran en la categoría de propiedades **CustomAttributes** , situada en el panel de propiedades).</span><span class="sxs-lookup"><span data-stu-id="1e299-108">If you are formatting the series, you can specify series-specific properties using custom attributes, which can only be found in the **CustomAttributes** category of properties, located in the Properties pane.</span></span>  
  
 <span data-ttu-id="1e299-109">Para dar formato al gráfico de forma eficaz con el menor número posible de pasos, cambie el estilo de borde, la paleta y el estilo de dibujo predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1e299-109">To effectively format the chart using a minimal number of steps, change the default border style, palette and drawing style.</span></span> <span data-ttu-id="1e299-110">Estas tres características son las que posibilitan el cambio visual más notable en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="1e299-110">These three features produce the largest visible change on the chart.</span></span> <span data-ttu-id="1e299-111">Los estilos de dibujo solo se pueden aplicar a los gráficos circulares, de anillos, de barras y de columnas.</span><span class="sxs-lookup"><span data-stu-id="1e299-111">Drawing styles are only applicable to pie, doughnut, bar and column charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="1e299-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1e299-112">In This Section</span></span>  
 [<span data-ttu-id="1e299-113">Aplicar formato a los colores de serie de un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-113">Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="1e299-114">Describe cómo se definen los colores con una paleta, cómo puede definir su propia paleta de colores, y cómo se definen los colores basándose en una expresión.</span><span class="sxs-lookup"><span data-stu-id="1e299-114">Discusses how colors are defined using a palette, how you can define your own color palette, and how to define colors based on an expression.</span></span>  
  
 [<span data-ttu-id="1e299-115">Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-115">Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="1e299-116">Describe cómo mostrar líneas de cuadrícula, marcas de graduación y títulos, y cómo dar formato a los números y a las fechas de la escala del eje.</span><span class="sxs-lookup"><span data-stu-id="1e299-116">Discusses how to display gridlines, tick marks, and titles, and how to format numbers and dates on the axis scale.</span></span>  
  
 [<span data-ttu-id="1e299-117">Aplicar formato a la leyenda de un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-117">Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-formatting-report-builder.md)  
 <span data-ttu-id="1e299-118">Describe cómo volver a ordenar y a dar formato a los elementos de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="1e299-118">Discusses how to re-order and format items in the chart legend.</span></span>  
  
 [<span data-ttu-id="1e299-119">Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-119">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="1e299-120">Describe cómo situar etiquetas de puntos de datos y cómo dar formato a los marcadores de los puntos de datos para cada serie del gráfico.</span><span class="sxs-lookup"><span data-stu-id="1e299-120">Discusses how to position data point labels and format data point markers for every series on the chart.</span></span>  
  
 [<span data-ttu-id="1e299-121">Aplicar 3D, bisel y otros efectos a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-121">3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-3d-bevel-and-other-report-builder.md)  
 <span data-ttu-id="1e299-122">Describe varios efectos 3D que puede aplicar a un gráfico.</span><span class="sxs-lookup"><span data-stu-id="1e299-122">Discusses various 3D effects that you can apply to a chart.</span></span>  
  
 [<span data-ttu-id="1e299-123">Agregar un marco de borde a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-123">Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="1e299-124">Explica cómo agregar un marco de borde a un gráfico.</span><span class="sxs-lookup"><span data-stu-id="1e299-124">Explains how to add a border frame to a chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e299-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e299-125">See Also</span></span>  
 <span data-ttu-id="1e299-126">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1e299-126">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1e299-127">[Agregar un marco de borde a un gráfico &#40;Generador de informes y SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1e299-127">[Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1e299-128">[Definir los colores de un gráfico mediante una paleta &#40;Generador de informes y SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1e299-128">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1e299-129">Agregar estilos con bisel, relieve y textura a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e299-129">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
