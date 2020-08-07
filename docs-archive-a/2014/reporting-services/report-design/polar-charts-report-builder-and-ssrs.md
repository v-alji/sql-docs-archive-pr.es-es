---
title: Gráficos polares (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c9402d8f-202a-4cdf-949e-50f5b1d2b885
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b8c4dd9394fab3e076c4a714375954a616e081f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743925"
---
# <a name="polar-charts-report-builder-and-ssrs"></a><span data-ttu-id="0066a-102">Gráficos polares (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="0066a-102">Polar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0066a-103">Un gráfico polar muestra una serie como un conjunto de puntos agrupados por categorías en un círculo de 360 grados.</span><span class="sxs-lookup"><span data-stu-id="0066a-103">A polar chart displays a series as a set of points that are grouped by category on a 360-degree circle.</span></span> <span data-ttu-id="0066a-104">Los valores se representan por la longitud de los puntos con relación al centro del círculo.</span><span class="sxs-lookup"><span data-stu-id="0066a-104">Values are represented by the length of the point as measured from the center of the circle.</span></span> <span data-ttu-id="0066a-105">Cuanto más lejos del centro esté el punto, mayor será su valor.</span><span class="sxs-lookup"><span data-stu-id="0066a-105">The farther the point is from the center, the greater its value.</span></span> <span data-ttu-id="0066a-106">Las etiquetas de las categorías se muestran en el perímetro del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0066a-106">Category labels are displayed on the perimeter of the chart.</span></span> <span data-ttu-id="0066a-107">Para obtener más información sobre cómo agregar datos a un gráfico polar, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0066a-107">For more information on how to add data to a polar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="0066a-108">Variaciones</span><span class="sxs-lookup"><span data-stu-id="0066a-108">Variations</span></span>  
  
-   <span data-ttu-id="0066a-109">**Gráfico radial**.</span><span class="sxs-lookup"><span data-stu-id="0066a-109">**Radar chart**.</span></span> <span data-ttu-id="0066a-110">Un gráfico radial muestra una serie como una línea o un área circular.</span><span class="sxs-lookup"><span data-stu-id="0066a-110">A radar chart displays a series as a circular line or area.</span></span> <span data-ttu-id="0066a-111">A diferencia del gráfico polar, el gráfico radial no muestra los datos en función de las coordenadas polares.</span><span class="sxs-lookup"><span data-stu-id="0066a-111">Unlike the polar chart, the radar chart does not display data in terms of polar coordinates.</span></span>  
  
## <a name="data-considerations-for-polar-charts"></a><span data-ttu-id="0066a-112">Consideraciones sobre los datos para los gráficos polares</span><span class="sxs-lookup"><span data-stu-id="0066a-112">Data Considerations for Polar Charts</span></span>  
  
-   <span data-ttu-id="0066a-113">El gráfico radial es útil para realizar comparaciones entre varias series de datos de categorías.</span><span class="sxs-lookup"><span data-stu-id="0066a-113">The radar chart is useful for comparisons between multiple series of category data.</span></span>  
  
-   <span data-ttu-id="0066a-114">Los gráficos polares se usan normalmente para representar datos polares, en los que cada punto de datos viene determinado por un ángulo y una distancia.</span><span class="sxs-lookup"><span data-stu-id="0066a-114">Polar charts are most commonly used to graph polar data, where each data point is determined by an angle and a distance.</span></span>  
  
-   <span data-ttu-id="0066a-115">Los gráficos polares no se pueden combinar con ningún otro tipo de gráfico en la misma área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="0066a-115">Polar charts cannot be combined with any other chart type in the same chart area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0066a-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0066a-116">Example</span></span>  
 <span data-ttu-id="0066a-117">En el ejemplo siguiente se muestra el uso de un gráfico radial.</span><span class="sxs-lookup"><span data-stu-id="0066a-117">The following example shows how a radar chart can be used.</span></span> <span data-ttu-id="0066a-118">La tabla siguiente proporciona los datos de ejemplo para el gráfico.</span><span class="sxs-lookup"><span data-stu-id="0066a-118">The table below provides sample data for the chart.</span></span>  
  
|<span data-ttu-id="0066a-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="0066a-119">Name</span></span>|<span data-ttu-id="0066a-120">Sales</span><span class="sxs-lookup"><span data-stu-id="0066a-120">Sales</span></span>|  
|----------|-----------|  
|<span data-ttu-id="0066a-121">Shrubs</span><span class="sxs-lookup"><span data-stu-id="0066a-121">Shrubs</span></span>|<span data-ttu-id="0066a-122">61</span><span class="sxs-lookup"><span data-stu-id="0066a-122">61</span></span>|  
|<span data-ttu-id="0066a-123">Seeds</span><span class="sxs-lookup"><span data-stu-id="0066a-123">Seeds</span></span>|<span data-ttu-id="0066a-124">78</span><span class="sxs-lookup"><span data-stu-id="0066a-124">78</span></span>|  
|<span data-ttu-id="0066a-125">Bulbs</span><span class="sxs-lookup"><span data-stu-id="0066a-125">Bulbs</span></span>|<span data-ttu-id="0066a-126">60</span><span class="sxs-lookup"><span data-stu-id="0066a-126">60</span></span>|  
|<span data-ttu-id="0066a-127">Árboles</span><span class="sxs-lookup"><span data-stu-id="0066a-127">Trees</span></span>|<span data-ttu-id="0066a-128">38</span><span class="sxs-lookup"><span data-stu-id="0066a-128">38</span></span>|  
|<span data-ttu-id="0066a-129">Flowers</span><span class="sxs-lookup"><span data-stu-id="0066a-129">Flowers</span></span>|<span data-ttu-id="0066a-130">81</span><span class="sxs-lookup"><span data-stu-id="0066a-130">81</span></span>|  
  
 <span data-ttu-id="0066a-131">En este ejemplo, el campo Nombre se sitúa en el área Grupos de categorías.</span><span class="sxs-lookup"><span data-stu-id="0066a-131">In this example, the Name field is placed in the Category Groups area.</span></span> <span data-ttu-id="0066a-132">El campo Ventas se coloca en el área Valores.</span><span class="sxs-lookup"><span data-stu-id="0066a-132">The Sales field is placed in the Values area.</span></span> <span data-ttu-id="0066a-133">El campo Sales se agrega automáticamente al gráfico al colocarlo.</span><span class="sxs-lookup"><span data-stu-id="0066a-133">The Sales field is automatically aggregated for the chart when you drop it.</span></span> <span data-ttu-id="0066a-134">El gráfico radial calcula dónde se deben situar las etiquetas basándose en el número de valores del campo Sales, que contiene cinco valores, y coloca las etiquetas en cinco puntos equidistantes en un círculo.</span><span class="sxs-lookup"><span data-stu-id="0066a-134">The radar chart calculates where to place the labels based on the number of values in the Sales field, which contains five values and places labels at five equidistant points on a circle.</span></span> <span data-ttu-id="0066a-135">Si el campo Sales incluyese tres valores, las etiquetas se colocarían en tres puntos equidistantes en un círculo.</span><span class="sxs-lookup"><span data-stu-id="0066a-135">If the Sales field contained three values, the labels would be placed at three equidistant points on a circle.</span></span>  
  
 <span data-ttu-id="0066a-136">En la ilustración siguiente se muestra un ejemplo de un gráfico radial basado en los datos presentados.</span><span class="sxs-lookup"><span data-stu-id="0066a-136">The following illustration shows an example of a radar chart based on the data presented.</span></span>  
  
 <span data-ttu-id="0066a-137">![Gráfico radial](../media/rs-radarchart.gif "Gráfico radial")</span><span class="sxs-lookup"><span data-stu-id="0066a-137">![Radar chart](../media/rs-radarchart.gif "Radar chart")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0066a-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0066a-138">See Also</span></span>  
 <span data-ttu-id="0066a-139">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0066a-139">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0066a-140">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0066a-140">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0066a-141">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0066a-141">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0066a-142">[Gráficos de líneas &#40;Generador de informes y SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0066a-142">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0066a-143">Puntos de datos vacíos y nulos en los gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0066a-143">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
