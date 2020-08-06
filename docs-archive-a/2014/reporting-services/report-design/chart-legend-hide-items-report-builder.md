---
title: Ocultar elementos de leyenda en el gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92256240-0cd5-4be4-8904-d1e3b93cb6b3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20444432f580ffaf1c5f4de1320b06319f973a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676353"
---
# <a name="hide-legend-items-on-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="0593e-102">Ocultar elementos de leyenda en el gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0593e-102">Hide Legend Items on the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0593e-103">De forma predeterminada, cualquier serie que se agregue a un gráfico que no sea un gráfico de formas se agregará como elemento en la leyenda.</span><span class="sxs-lookup"><span data-stu-id="0593e-103">By default, any series added to a non-Shape chart will be added as an item in the legend.</span></span> <span data-ttu-id="0593e-104">En los gráficos circulares, de anillos, de embudo y piramidales, cualquier serie que se agregue al gráfico agregará puntos de datos individuales a la leyenda.</span><span class="sxs-lookup"><span data-stu-id="0593e-104">For pie, doughnut, funnel, and pyramid charts, any series added to the chart will add individual data points in the legend.</span></span>  
  
 <span data-ttu-id="0593e-105">Puede ocultar cualquier elemento de la leyenda.</span><span class="sxs-lookup"><span data-stu-id="0593e-105">You can hide any item on the legend.</span></span> <span data-ttu-id="0593e-106">Aunque oculte un elemento de leyenda, este seguirá apareciendo en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="0593e-106">When you hide a legend item, it will still appear in the chart.</span></span> <span data-ttu-id="0593e-107">Esto resulta de gran utilidad en situaciones donde no se desea mostrar más información sobre una serie agregada al gráfico.</span><span class="sxs-lookup"><span data-stu-id="0593e-107">This is useful in situations where you do not want to show more information for a series that is added to the chart.</span></span> <span data-ttu-id="0593e-108">Por ejemplo, si ha agregado al gráfico una serie calculada, como una media móvil, puede ser que le interese ocultar esta entrada en la leyenda para que solo se muestre más información sobre la serie original.</span><span class="sxs-lookup"><span data-stu-id="0593e-108">For example, if you have added a calculated series like a moving average to the chart, you may want to hide this entry in the legend so that more information is only shown for the original series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-an-item-from-display-in-the-legend"></a><span data-ttu-id="0593e-109">Para ocultar un elemento en la leyenda</span><span class="sxs-lookup"><span data-stu-id="0593e-109">To hide an item from display in the legend</span></span>  
  
1.  <span data-ttu-id="0593e-110">Haga clic con el botón derecho en la serie que quiere ocultar y seleccione **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="0593e-110">Right-click on the series you want to hide and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="0593e-111">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="0593e-111">Click **Legend**.</span></span> <span data-ttu-id="0593e-112">Seleccione la opción **No mostrar esta serie en una leyenda** .</span><span class="sxs-lookup"><span data-stu-id="0593e-112">Select the **Do not show this series in a legend** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0593e-113">No puede ocultar una serie para un grupo y dejarla visible para los demás.</span><span class="sxs-lookup"><span data-stu-id="0593e-113">You cannot hide a series for one group and not for the others.</span></span> <span data-ttu-id="0593e-114">Si ha agregado un campo al área **Grupos de series** , se ocultarán todas las series que pertenecen a este grupo.</span><span class="sxs-lookup"><span data-stu-id="0593e-114">If you have added a field to the **Series Groups** area, all series belonging to this group will be hidden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0593e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0593e-115">See Also</span></span>  
 <span data-ttu-id="0593e-116">[Aplicar formato a la leyenda de un gráfico &#40;Generador de informes y SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="0593e-116">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="0593e-117">[Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0593e-117">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0593e-118">[Cambiar el texto de un elemento de leyenda &#40;Generador de informes y SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="0593e-118">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="0593e-119">[Agregar una media móvil a un gráfico &#40;Generador de informes y SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0593e-119">[Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0593e-120">Cuadro de diálogo de Propiedades de la leyenda, General &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0593e-120">Legend Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../legend-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
