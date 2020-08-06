---
title: Gráficos de áreas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 245b236d-1d55-4744-b752-80bd133502aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f401efa0abd5eac8ab39e511bc6b16a4f381ebdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746779"
---
# <a name="area-charts-report-builder-and-ssrs"></a><span data-ttu-id="a0f68-102">Gráficos de áreas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="a0f68-102">Area Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a0f68-103">Un gráfico de áreas muestra una serie como un conjunto de puntos conectados por una línea, con toda el área situada debajo de la línea rellenada.</span><span class="sxs-lookup"><span data-stu-id="a0f68-103">An area chart displays a series as a set of points connected by a line, with all the area filled in below the line.</span></span> <span data-ttu-id="a0f68-104">Para obtener más información sobre cómo agregar datos a un gráfico de áreas, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a0f68-104">For more information on how to add data to an area chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a0f68-105">En la ilustración siguiente se muestra un ejemplo de gráfico de áreas apiladas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-105">The following illustration shows an example of a stacked area chart.</span></span> <span data-ttu-id="a0f68-106">Los datos se adaptan perfectamente a un gráfico de áreas apiladas porque en él se pueden mostrar los totales para todas las series y la proporción con la que cada serie contribuye al total.</span><span class="sxs-lookup"><span data-stu-id="a0f68-106">The data is well suited for display on a stacked area chart because the chart can display totals for all series as well as the proportion that each series contributes to the total.</span></span>  
  
 <span data-ttu-id="a0f68-107">![Gráfico de áreas](../media/areachart.gif "Gráfico de áreas")</span><span class="sxs-lookup"><span data-stu-id="a0f68-107">![Area chart](../media/areachart.gif "Area chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="a0f68-108">Variaciones</span><span class="sxs-lookup"><span data-stu-id="a0f68-108">Variations</span></span>  
  
-   <span data-ttu-id="a0f68-109">**Área apilada**.</span><span class="sxs-lookup"><span data-stu-id="a0f68-109">**Stacked area**.</span></span> <span data-ttu-id="a0f68-110">Gráfico de áreas donde varias series se apilan verticalmente.</span><span class="sxs-lookup"><span data-stu-id="a0f68-110">An area chart where multiple series are stacked vertically.</span></span> <span data-ttu-id="a0f68-111">Si solo hay una serie en el gráfico, el gráfico de áreas apiladas se mostrará igual que un gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-111">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="a0f68-112">**Área 100% apilada**.</span><span class="sxs-lookup"><span data-stu-id="a0f68-112">**Percent stacked area**.</span></span> <span data-ttu-id="a0f68-113">Gráfico de áreas donde varias series se apilan verticalmente para ajustarse a la totalidad del área del gráfico.</span><span class="sxs-lookup"><span data-stu-id="a0f68-113">An area chart where multiple series are stacked vertically to fit the entire chart area.</span></span> <span data-ttu-id="a0f68-114">Si solo hay una serie en el gráfico, el gráfico de áreas apiladas se mostrará igual que un gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-114">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="a0f68-115">**Área suavizada**.</span><span class="sxs-lookup"><span data-stu-id="a0f68-115">**Smooth area**.</span></span> <span data-ttu-id="a0f68-116">Gráfico de áreas donde los puntos de datos se conectan mediante una línea suavizada en lugar de una línea normal.</span><span class="sxs-lookup"><span data-stu-id="a0f68-116">An area chart where the data points are connected by a smooth line instead of a regular line.</span></span> <span data-ttu-id="a0f68-117">Use un gráfico de área suavizada en lugar de un gráfico de áreas cuando esté más interesado en mostrar tendencias que en mostrar los valores de los puntos de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="a0f68-117">Use a smooth area chart instead of an area chart when you are more concerned with displaying trends than with displaying the values of individual data points.</span></span>  
  
## <a name="data-considerations-for-area-charts"></a><span data-ttu-id="a0f68-118">Consideraciones sobre los datos para los gráficos de áreas</span><span class="sxs-lookup"><span data-stu-id="a0f68-118">Data Considerations for Area Charts</span></span>  
  
-   <span data-ttu-id="a0f68-119">Junto con el gráfico de líneas, el gráfico de áreas es el único tipo de gráfico que muestra datos contiguos.</span><span class="sxs-lookup"><span data-stu-id="a0f68-119">Along with the line chart, the area chart is the only chart type that displays data contiguously.</span></span> <span data-ttu-id="a0f68-120">Por esta razón, el gráfico de áreas se usa normalmente para representar datos que tienen lugar durante un período continuado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a0f68-120">For this reason, an area chart is commonly used to represent data that occurs over a continuous period of time.</span></span>  
  
-   <span data-ttu-id="a0f68-121">Un gráfico de áreas apiladas en porcentaje resulta de gran utilidad para mostrar datos proporcionales que tienen lugar a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a0f68-121">A percent stacked area chart is useful for showing proportional data that occurs over time.</span></span>  
  
-   <span data-ttu-id="a0f68-122">Si solo hay una serie, el gráfico de áreas apiladas se dibujará como un gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-122">If there is only one series, a stacked area chart will be drawn as an area chart.</span></span>  
  
-   <span data-ttu-id="a0f68-123">En un gráfico de áreas sencillo, si los valores de varias series son similares, las áreas se pueden superponer y ocultar valores de puntos de datos importantes.</span><span class="sxs-lookup"><span data-stu-id="a0f68-123">In a plain area chart, if the values in multiple series are similar, the areas may overlap, obscuring important data point values.</span></span> <span data-ttu-id="a0f68-124">Para resolver este problema, cambie el tipo de gráfico por un gráfico de áreas apiladas, que ha sido diseñado para mostrar varias series en un gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-124">You can resolve this issue by changing the chart type to a stacked area chart, which is designed to show multiple series on an area chart.</span></span>  
  
-   <span data-ttu-id="a0f68-125">Si el gráfico de áreas apiladas contiene intervalos, es posible que el conjunto de datos incluya valores vacíos, que se mostrarán como una sección vacía en un gráfico de áreas apiladas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-125">If your stacked area chart contains gaps, it is possible that your dataset includes empty values, which will be shown as a vacant section on a stacked area chart.</span></span> <span data-ttu-id="a0f68-126">Si el conjunto de datos incluye valores vacíos, es posible que le interese insertar puntos vacíos en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="a0f68-126">If your dataset includes empty values, consider inserting empty points on the chart.</span></span> <span data-ttu-id="a0f68-127">Al agregar puntos vacíos, se rellenarán las áreas vacías el gráfico con un color diferente para indicar los valores NULL o valores cero.</span><span class="sxs-lookup"><span data-stu-id="a0f68-127">Adding empty points will fill in the empty areas on the chart with a different color to indicate null or zero values.</span></span> <span data-ttu-id="a0f68-128">Para obtener más información, vea [Agregar puntos vacíos al gráfico &#40;generador de informes y SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a0f68-128">For more information, see [Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="a0f68-129">Los tipos de gráfico de área son muy similares a los gráficos de columnas y de líneas en cuanto a comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a0f68-129">Area chart types are very similar to column and line charts in behavior.</span></span> <span data-ttu-id="a0f68-130">Si está realizando una comparación entre varias series, plantéese la posibilidad de usar un gráfico de columnas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-130">If you are making a comparison between multiple series, consider using a column chart instead.</span></span> <span data-ttu-id="a0f68-131">Si está analizando tendencias durante un período de tiempo, considere la posibilidad de usar un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="a0f68-131">If you are analyzing trends over a period of time, consider using a line chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f68-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0f68-132">See Also</span></span>  
 <span data-ttu-id="a0f68-133">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0f68-133">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0f68-134">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0f68-134">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0f68-135">[Gráficos de líneas &#40;Generador de informes y SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0f68-135">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0f68-136">[Cambiar un tipo de gráfico &#40;Generador de informes y SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0f68-136">[Change a Chart Type &#40;Report Builder and SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a0f68-137">Puntos de datos vacíos y nulos en los gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a0f68-137">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
