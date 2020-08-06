---
title: Mostrar la información sobre herramientas en una serie (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9113ec843b3b9255f380b17ee1ab6b360fa1f60d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676340"
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a><span data-ttu-id="0d09e-102">Mostrar la información sobre herramientas en una serie (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d09e-102">Show ToolTips on a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0d09e-103">Puede agregar una información sobre herramientas a cada uno de los puntos de datos de la serie de un gráfico para mostrar información relacionada con el punto de datos, como el nombre del grupo, el valor del punto de datos o el porcentaje del punto de datos en relación con el total de la serie, cuando los usuarios mantienen el mouse sobre el punto de datos en un informe representado.</span><span class="sxs-lookup"><span data-stu-id="0d09e-103">You can add a ToolTip to each data point on the series of a chart to display information related to the data point, such as the group name, the value of the data point, or the percentage of the data point relative to the series total when users hover over the data point in a rendered report.</span></span>  
  
 <span data-ttu-id="0d09e-104">No se puede agregar una información sobre herramientas a una serie calculada.</span><span class="sxs-lookup"><span data-stu-id="0d09e-104">You cannot add a ToolTip to a calculated series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-tooltip-on-each-data-point"></a><span data-ttu-id="0d09e-105">Para especificar una información sobre herramientas en cada punto de datos</span><span class="sxs-lookup"><span data-stu-id="0d09e-105">To specify a ToolTip on each data point</span></span>  
  
1.  <span data-ttu-id="0d09e-106">Haga clic con el botón derecho en la serie o en el campo del área **Valores** y seleccione **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="0d09e-106">Right-click on the series or right-click on the field in the **Values** area, and click **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="0d09e-107">Haga clic en **Datos de las series** y, para la propiedad **ToolTip** , escriba una cadena o una expresión.</span><span class="sxs-lookup"><span data-stu-id="0d09e-107">Click **Series Data** and, for the **ToolTip** property, type in a string or expression.</span></span> <span data-ttu-id="0d09e-108">Puede usar cualquier palabra clave específica del gráfico para representar otro elemento del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0d09e-108">You can use any chart-specific keyword to represent another element on the chart.</span></span> <span data-ttu-id="0d09e-109">Para más información, vea [Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0d09e-109">For more information, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d09e-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d09e-110">See Also</span></span>  
 <span data-ttu-id="0d09e-111">[Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d09e-111">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d09e-112">[Cambiar el texto de un elemento de leyenda &#40;Generador de informes y SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="0d09e-112">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="0d09e-113">[Aplicar formato a los colores de serie de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d09e-113">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0d09e-114">Agregar una acción de obtención de detalles en un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0d09e-114">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
