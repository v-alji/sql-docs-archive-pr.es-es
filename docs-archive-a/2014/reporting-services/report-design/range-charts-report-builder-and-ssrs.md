---
title: Rangos de intervalos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48e351d3-ac5b-4eda-a4bd-32a0de206a30
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 76a9723bc55030da59d22c945a40ce4418b84ab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746767"
---
# <a name="range-charts-report-builder-and-ssrs"></a><span data-ttu-id="6d7f0-102">Rangos de intervalos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6d7f0-102">Range Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6d7f0-103">Un tipo de gráfico de intervalos muestra un conjunto de puntos de datos en el que cada uno de ellos se define mediante varios valores para la misma categoría.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-103">A range chart type displays a set of data points that are each defined by multiple values for the same category.</span></span> <span data-ttu-id="6d7f0-104">Los valores se representan mediante el alto de los marcadores con relación al eje de valores.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-104">Values are represented by the height of the marker as measured by the value axis.</span></span> <span data-ttu-id="6d7f0-105">Las etiquetas de las categorías se muestran en el eje de categorías.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-105">Category labels are displayed on the category axis.</span></span> <span data-ttu-id="6d7f0-106">El gráfico de intervalos sencillo rellena el área situada entre el valor superior y el valor inferior de cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-106">The plain range chart fills in the area between the top and bottom value for each data point.</span></span>  
  
 <span data-ttu-id="6d7f0-107">En la ilustración siguiente se muestra un gráfico de intervalos sencillo con tres series.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-107">The following illustration shows a plain range chart with three series.</span></span>  
  
 <span data-ttu-id="6d7f0-108">![Gráfico de intervalos](../media/rs-rangechart.gif "Gráfico de intervalos")</span><span class="sxs-lookup"><span data-stu-id="6d7f0-108">![Range chart](../media/rs-rangechart.gif "Range chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="6d7f0-109">Variaciones</span><span class="sxs-lookup"><span data-stu-id="6d7f0-109">Variations</span></span>  
  
-   <span data-ttu-id="6d7f0-110">**Intervalo suavizado**.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-110">**Smooth range**.</span></span> <span data-ttu-id="6d7f0-111">Un gráfico de intervalos suavizados muestra las líneas curvas en lugar de rectas.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-111">A smooth range chart displays curved lines rather than straight.</span></span>  
  
-   <span data-ttu-id="6d7f0-112">**Intervalo de columnas**.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-112">**Column range**.</span></span> <span data-ttu-id="6d7f0-113">Un gráfico de intervalos de columnas usa columnas en lugar de áreas para mostrar los intervalos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-113">A column range chart uses columns instead of areas to display the ranges.</span></span>  
  
-   <span data-ttu-id="6d7f0-114">**Intervalo de barras**.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-114">**Bar range**.</span></span> <span data-ttu-id="6d7f0-115">Un gráfico de intervalos de barras usa barras en lugar de áreas para mostrar los intervalos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-115">A bar range chart uses bars instead of areas to display the ranges.</span></span>  
  
## <a name="data-considerations-for-range-charts"></a><span data-ttu-id="6d7f0-116">Consideraciones sobre los datos para los gráficos de intervalos</span><span class="sxs-lookup"><span data-stu-id="6d7f0-116">Data Considerations for Range Charts</span></span>  
  
-   <span data-ttu-id="6d7f0-117">Los tipos de gráficos de intervalos requieren dos valores para cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-117">Range chart types require two values per data point.</span></span> <span data-ttu-id="6d7f0-118">Estos valores se corresponden con un valor alto y un valor bajo que definen el intervalo para cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-118">These values correspond with a high value and a low value that defines the range for each data point.</span></span>  
  
-   <span data-ttu-id="6d7f0-119">Los gráficos de intervalos son útiles para realizar análisis solo si los valores superiores son siempre más altos que los inferiores.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-119">Range charts are useful for analysis only if the top values are always higher than the bottom values.</span></span> <span data-ttu-id="6d7f0-120">Si este no es el caso, considere la posibilidad de usar un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-120">If this is not the case, consider using a line chart.</span></span> <span data-ttu-id="6d7f0-121">Si el valor alto es más bajo que el valor bajo, el gráfico de intervalos mostrará el valor absoluto de la diferencia entre estos valores.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-121">If the high value is lower the low value, the range chart will display the absolute value of the difference between these values.</span></span>  
  
-   <span data-ttu-id="6d7f0-122">Si se especifica solo un valor, el gráfico de intervalos se mostrará como si se tratara de un gráfico de áreas normal, con un valor por cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-122">If only one value is specified, the range chart will display as if it were a regular area chart, with one value per data point.</span></span>  
  
-   <span data-ttu-id="6d7f0-123">Los gráficos de intervalos se suelen usar para representar gráficamente datos que contienen valores mínimos y máximos para cada grupo de categorías del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-123">Range charts are often used to graph data that contains minimum and maximum values for each category group in the dataset.</span></span>  
  
-   <span data-ttu-id="6d7f0-124">En un gráfico de intervalos no es posible mostrar marcadores en cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-124">Displaying markers on each data point is not supported on the range chart.</span></span>  
  
-   <span data-ttu-id="6d7f0-125">Al igual que en un gráfico de áreas, si en un gráfico de intervalos sencillo los valores de varias series son similares, las series se superpondrán.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-125">Like the area chart, in a plain range chart, if the values in multiple series are similar, the series will overlap.</span></span> <span data-ttu-id="6d7f0-126">En este escenario, es posible que prefiera usar un gráfico de intervalos de columnas o un gráfico de intervalos de barras en lugar de un gráfico de intervalos sencillo.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-126">In this scenario, you may want to use a column range or bar range chart instead of a plain range chart.</span></span>  
  
-   <span data-ttu-id="6d7f0-127">Se pueden crear diagramas de Gantt usando un gráfico de intervalos de barras.</span><span class="sxs-lookup"><span data-stu-id="6d7f0-127">Gantt charts can be created using a range bar chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d7f0-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d7f0-128">See Also</span></span>  
 <span data-ttu-id="6d7f0-129">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d7f0-129">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6d7f0-130">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6d7f0-130">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6d7f0-131">Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6d7f0-131">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
