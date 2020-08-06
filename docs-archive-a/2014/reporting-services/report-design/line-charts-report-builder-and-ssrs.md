---
title: Gráficos de líneas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 44e7a011186e66e6b8bdc8b5dd31939c883e320b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749086"
---
# <a name="line-charts-report-builder-and-ssrs"></a><span data-ttu-id="39195-102">Gráficos de líneas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="39195-102">Line Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="39195-103">Los gráficos de líneas muestran una serie como un conjunto de puntos conectados mediante una sola línea.</span><span class="sxs-lookup"><span data-stu-id="39195-103">A line chart displays a series as a set of points connected by a single line.</span></span> <span data-ttu-id="39195-104">Los gráficos de líneas se usan para representar grandes cantidades de datos que tienen lugar durante un período continuado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="39195-104">Line charts are used to representing large amounts of data that occur over a continuous period of time.</span></span> <span data-ttu-id="39195-105">Para obtener más información sobre cómo agregar datos a un gráfico de líneas, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39195-105">For more information about how to add data to a line chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="39195-106">La ilustración siguiente muestra un gráfico de líneas que contiene tres series.</span><span class="sxs-lookup"><span data-stu-id="39195-106">The following illustration shows a line chart that contains three series.</span></span>  
  
 <span data-ttu-id="39195-107">![Gráfico de líneas](../media/rs-linechart.gif "Gráfico de líneas")</span><span class="sxs-lookup"><span data-stu-id="39195-107">![Line chart](../media/rs-linechart.gif "Line chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="39195-108">Variaciones</span><span class="sxs-lookup"><span data-stu-id="39195-108">Variations</span></span>  
  
-   <span data-ttu-id="39195-109">**Línea suavizada**.</span><span class="sxs-lookup"><span data-stu-id="39195-109">**Smooth line**.</span></span> <span data-ttu-id="39195-110">Gráfico de líneas que usa una línea curva en lugar de una línea normal.</span><span class="sxs-lookup"><span data-stu-id="39195-110">A line chart that uses a curved line instead of a regular line.</span></span>  
  
-   <span data-ttu-id="39195-111">**Línea escalonada**.</span><span class="sxs-lookup"><span data-stu-id="39195-111">**Stepped line**.</span></span> <span data-ttu-id="39195-112">Gráfico de líneas que usa una línea escalonada en lugar de una línea normal.</span><span class="sxs-lookup"><span data-stu-id="39195-112">A line chart that uses a stepped line instead of a regular line.</span></span> <span data-ttu-id="39195-113">La línea escalonada conecta puntos mediante una línea que adopta la apariencia de los peldaños de una escalera.</span><span class="sxs-lookup"><span data-stu-id="39195-113">The stepped line connects points by using a line that makes it look like steps on a ladder or staircase.</span></span>  
  
-   <span data-ttu-id="39195-114">**Gráficos sparkline**.</span><span class="sxs-lookup"><span data-stu-id="39195-114">**Sparkline charts**.</span></span> <span data-ttu-id="39195-115">Variaciones del gráfico de líneas que muestran solo la serie de líneas en la celda de una tabla o una matriz.</span><span class="sxs-lookup"><span data-stu-id="39195-115">Variations of the line chart that show only the line series in the cell of a table or matrix.</span></span> <span data-ttu-id="39195-116">Para obtener más información, vea [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39195-116">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="data-considerations-for-line-charts"></a><span data-ttu-id="39195-117">Consideraciones sobre los datos para los gráficos de líneas</span><span class="sxs-lookup"><span data-stu-id="39195-117">Data Considerations for Line Charts</span></span>  
  
-   <span data-ttu-id="39195-118">Para mejorar el impacto visual del gráfico de líneas predeterminado, considere la posibilidad de cambiar el ancho del borde de la serie a 3 y agregar un desplazamiento de sombra de 1.</span><span class="sxs-lookup"><span data-stu-id="39195-118">To improve the visual impact of the default line chart, consider changing the width of the series border to 3, and adding a shadow offset of 1.</span></span> <span data-ttu-id="39195-119">Esto creará un gráfico de líneas mucho más oscuro.</span><span class="sxs-lookup"><span data-stu-id="39195-119">This will create a much bolder line chart.</span></span> <span data-ttu-id="39195-120">Deberá revertir estas propiedades a sus valores originales si cambia el tipo de gráfico de Línea por otro.</span><span class="sxs-lookup"><span data-stu-id="39195-120">You will need to revert these properties to their original values if you change the chart type from Line to another type.</span></span>  
  
-   <span data-ttu-id="39195-121">Si el conjunto de datos incluye valores vacíos, el gráfico de líneas agregará puntos vacíos en forma de líneas de marcador de posición para mantener la continuidad en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="39195-121">If your dataset includes empty values, the line chart will add empty points, in the form of placeholder lines, in order to maintain continuity on the chart.</span></span> <span data-ttu-id="39195-122">Si no desea ver estas líneas, considere la posibilidad de mostrar el conjunto de datos usando un tipo de gráfico no contiguo, como un gráfico de barras o de columnas.</span><span class="sxs-lookup"><span data-stu-id="39195-122">If you would rather not see these lines, consider displaying your dataset using a non-contiguous chart type such as a bar or column chart.</span></span>  
  
-   <span data-ttu-id="39195-123">Un gráfico de líneas requiere al menos dos puntos para dibujar una línea.</span><span class="sxs-lookup"><span data-stu-id="39195-123">A line chart requires at least two points to draw a line.</span></span>  <span data-ttu-id="39195-124">Si el conjunto de datos solo tiene un punto de datos, el gráfico de líneas se mostrará como un marcador de punto de datos único.</span><span class="sxs-lookup"><span data-stu-id="39195-124">If your dataset has only one data point, the line chart will display as a single data point marker.</span></span>  
  
-   <span data-ttu-id="39195-125">Una serie que se dibuja como una línea no ocupará mucho espacio dentro de un área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="39195-125">A series that is drawn as a line will not take up much space within a chart area.</span></span>  <span data-ttu-id="39195-126">Por este motivo, los gráficos de líneas se combinan con frecuencia con otros tipos de gráficos, como los gráficos de columnas.</span><span class="sxs-lookup"><span data-stu-id="39195-126">For this reason, line charts are frequently combined with other chart types such as column charts.</span></span> <span data-ttu-id="39195-127">Sin embargo, no se puede combinar un gráfico de líneas con los tipos de gráficos siguientes: Barras, Polar, Circular o de formas.</span><span class="sxs-lookup"><span data-stu-id="39195-127">However, you cannot combine a line chart with bar, polar, pie or shape chart types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39195-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39195-128">See Also</span></span>  
 <span data-ttu-id="39195-129">[Gráficos de barras &#40;Generador de informes y SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39195-129">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="39195-130">[Gráficos de columnas &#40;Generador de informes y SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39195-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="39195-131">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39195-131">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="39195-132">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39195-132">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="39195-133">[Gráficos de áreas &#40;Generador de informes y SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39195-133">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="39195-134">[Puntos de datos vacíos y nulos en los gráficos &#40;Generador de informes y SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="39195-134">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="39195-135">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="39195-135">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
