---
title: Gráficos de dispersión (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2520ae24-0609-4890-807d-3267018aba8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 93f9b31089eb8399c7fdfd201d3c799608f2e91e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746768"
---
# <a name="scatter-charts-report-builder-and-ssrs"></a><span data-ttu-id="4d94d-102">Gráficos de dispersión (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="4d94d-102">Scatter Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4d94d-103">Un gráfico de dispersión muestra una serie como un conjunto de puntos.</span><span class="sxs-lookup"><span data-stu-id="4d94d-103">A scatter chart displays a series as a set of points.</span></span> <span data-ttu-id="4d94d-104">Los valores se representan mediante la posición de los puntos en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="4d94d-104">Values are represented by the position of the points on the chart.</span></span> <span data-ttu-id="4d94d-105">Las categorías se representan mediante distintos marcadores en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="4d94d-105">Categories are represented by different markers on the chart.</span></span> <span data-ttu-id="4d94d-106">Los gráficos de dispersión suelen usarse para comparar datos agregados de las categorías.</span><span class="sxs-lookup"><span data-stu-id="4d94d-106">Scatter charts are typically used to compare aggregated data across categories.</span></span> <span data-ttu-id="4d94d-107">Para más información sobre cómo agregar datos a un gráfico de dispersión, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="4d94d-107">For more information on how to add data to a scatter chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="4d94d-108">En la ilustración siguiente se muestra un ejemplo de gráfico de dispersión.</span><span class="sxs-lookup"><span data-stu-id="4d94d-108">The following illustration shows an example of a scatter chart.</span></span>  
  
 <span data-ttu-id="4d94d-109">![Gráfico de dispersión](../media/rs-scatterchart.gif "Gráfico de dispersión")</span><span class="sxs-lookup"><span data-stu-id="4d94d-109">![Scatter chart](../media/rs-scatterchart.gif "Scatter chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="4d94d-110">Variaciones</span><span class="sxs-lookup"><span data-stu-id="4d94d-110">Variations</span></span>  
  
-   <span data-ttu-id="4d94d-111">**Burbuja.**</span><span class="sxs-lookup"><span data-stu-id="4d94d-111">**Bubble.**</span></span> <span data-ttu-id="4d94d-112">Los gráficos de burbujas muestran la diferencia entre dos valores de un punto de datos basándose en el tamaño de la burbuja.</span><span class="sxs-lookup"><span data-stu-id="4d94d-112">Bubble charts display the difference between two values of a data point based on the size of the bubble.</span></span> <span data-ttu-id="4d94d-113">Cuanto mayor sea la burbuja, mayor será la diferencia entre los dos valores.</span><span class="sxs-lookup"><span data-stu-id="4d94d-113">The larger the bubble, the larger the difference between the two values.</span></span>  
  
-   <span data-ttu-id="4d94d-114">**Burbuja 3D**.</span><span class="sxs-lookup"><span data-stu-id="4d94d-114">**3-D Bubble**.</span></span> <span data-ttu-id="4d94d-115">Gráfico de burbujas mostrado en tres dimensiones.</span><span class="sxs-lookup"><span data-stu-id="4d94d-115">A bubble chart displayed in 3-D.</span></span>  
  
## <a name="data-considerations-for-a-scatter-chart"></a><span data-ttu-id="4d94d-116">Consideraciones sobre los datos para los gráficos de dispersión</span><span class="sxs-lookup"><span data-stu-id="4d94d-116">Data Considerations for a Scatter Chart</span></span>  
  
-   <span data-ttu-id="4d94d-117">Los gráficos de dispersión se usan normalmente para mostrar y comparar valores numéricos, como datos científicos, estadísticos y de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="4d94d-117">Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical, and engineering data.</span></span>  
  
-   <span data-ttu-id="4d94d-118">Use el gráfico de dispersión cuando desee comparar grandes cantidades de puntos de datos sin tener en cuenta el tiempo.</span><span class="sxs-lookup"><span data-stu-id="4d94d-118">Use the scatter chart when you want to compare large numbers of data points without regard to time.</span></span> <span data-ttu-id="4d94d-119">Cuantos más datos incluya en un gráfico de dispersión, mejores comparaciones podrá realizar.</span><span class="sxs-lookup"><span data-stu-id="4d94d-119">The more data that you include in a scatter chart, the better the comparisons that you can make.</span></span>  
  
-   <span data-ttu-id="4d94d-120">El gráfico de burbujas requiere dos valores (superior e inferior) por cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="4d94d-120">The bubble chart requires two values (top and bottom) per data point.</span></span>  
  
-   <span data-ttu-id="4d94d-121">Los gráficos de dispersión son ideales para controlar la distribución de los valores y los clústeres de los puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="4d94d-121">Scatter charts are ideal for handling the distribution of values and clusters of data points.</span></span> <span data-ttu-id="4d94d-122">Éste es el mejor tipo de gráfico si el conjunto de datos contiene muchos puntos (por ejemplo, varios miles).</span><span class="sxs-lookup"><span data-stu-id="4d94d-122">This is the best chart type if your dataset contains many points (for example, several thousand points).</span></span> <span data-ttu-id="4d94d-123">Se debe evitar mostrar varias series en un gráfico de puntos porque visualmente puede resultar confuso.</span><span class="sxs-lookup"><span data-stu-id="4d94d-123">Displaying multiple series on a point chart is visually distracting and should be avoided.</span></span> <span data-ttu-id="4d94d-124">En este escenario, puede resultar más factible usar un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="4d94d-124">In this scenario, consider using a line chart.</span></span>  
  
-   <span data-ttu-id="4d94d-125">De forma predeterminada, los gráficos de dispersión muestran los puntos de datos como círculos.</span><span class="sxs-lookup"><span data-stu-id="4d94d-125">By default, scatter charts display data points as circles.</span></span> <span data-ttu-id="4d94d-126">Si tiene varias series en un gráfico de dispersión, plantéese la posibilidad de cambiar la forma del marcador de cada punto por un cuadrado, un triángulo, un rombo o cualquier otra forma.</span><span class="sxs-lookup"><span data-stu-id="4d94d-126">If you have multiple series on a scatter chart, consider changing the marker shape of each point to be square, triangle, diamond, or another shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d94d-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d94d-127">See Also</span></span>  
 <span data-ttu-id="4d94d-128">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d94d-128">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4d94d-129">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d94d-129">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4d94d-130">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d94d-130">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4d94d-131">Gráficos de líneas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4d94d-131">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)  
  
  
