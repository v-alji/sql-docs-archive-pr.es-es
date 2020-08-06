---
title: Distribuciones de columnas (minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
author: minewiskan
ms.author: owend
ms.openlocfilehash: 29aad33535c4cc4d9baf4c453249ce3b51595e78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677963"
---
# <a name="column-distributions-data-mining"></a><span data-ttu-id="334c3-102">Distribuciones de columnas (minería de datos)</span><span class="sxs-lookup"><span data-stu-id="334c3-102">Column Distributions (Data Mining)</span></span>
  <span data-ttu-id="334c3-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puede definir distribuciones de columnas en una estructura de minería de datos, para que los algoritmos puedan procesar los datos de esas columnas cuando se crean modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="334c3-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can define column distributions in a mining structure, to affect how algorithms process the data in those columns when you create mining models.</span></span> <span data-ttu-id="334c3-104">Para algunos algoritmos, resulta útil definir la distribución de las columnas continuas antes de procesar el modelo, si se sabe que las columnas contienen distribuciones de valores comunes.</span><span class="sxs-lookup"><span data-stu-id="334c3-104">For some algorithms, it is useful to define the distribution of any continuous columns before you process the model, if the columns are known to contain common distributions of values.</span></span> <span data-ttu-id="334c3-105">Si no define las distribuciones, los modelos de minería de datos resultantes podrían generar predicciones menos precisas que si se definieran las distribuciones porque los algoritmos disponen de menos información con la que interpretar los datos.</span><span class="sxs-lookup"><span data-stu-id="334c3-105">If you do not define the distributions, the resulting mining models may produce less accurate predictions than if the distributions were defined, because the algorithms will have less information from which to interpret the data.</span></span>

 <span data-ttu-id="334c3-106">Los algoritmos que están disponibles en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] admiten los siguientes tipos de distribución:</span><span class="sxs-lookup"><span data-stu-id="334c3-106">The algorithms that are available in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support the following distribution types:</span></span>

 <span data-ttu-id="334c3-107">`Normal`Los valores de la columna continua forman un histograma con una distribución normal.</span><span class="sxs-lookup"><span data-stu-id="334c3-107">`Normal` The values for the continuous column form a histogram with a normal distribution.</span></span>

 <span data-ttu-id="334c3-108">![Histograma con distribución normal](../media/normal-distribution.gif "Histograma con distribución normal")</span><span class="sxs-lookup"><span data-stu-id="334c3-108">![Histogram with normal distribution](../media/normal-distribution.gif "Histogram with normal distribution")</span></span>

 <span data-ttu-id="334c3-109">`Log Normal`Los valores de la columna continua forman un histograma, donde la curva se alarga en el extremo superior y se sesga hacia el extremo inferior.</span><span class="sxs-lookup"><span data-stu-id="334c3-109">`Log Normal` The values for the continuous column form a histogram, where the curve is elongated at the upper end and is skewed toward the lower end.</span></span>

 <span data-ttu-id="334c3-110">![Histograma con distribución normal del registro](../media/log-normal-distribution.gif "Histograma con distribución normal del registro")</span><span class="sxs-lookup"><span data-stu-id="334c3-110">![Histogram with log normal distribution](../media/log-normal-distribution.gif "Histogram with log normal distribution")</span></span>

 <span data-ttu-id="334c3-111">`Uniform`Los valores de la columna continua forman una curva plana, en la que todos los valores son igualmente probables.</span><span class="sxs-lookup"><span data-stu-id="334c3-111">`Uniform` The values for the continuous column form a flat curve, in which all values are equally likely.</span></span>

 <span data-ttu-id="334c3-112">![Histograma con distribución uniforme](../media/uniform-distribution.gif "Histograma con distribución uniforme")</span><span class="sxs-lookup"><span data-stu-id="334c3-112">![Histogram with uniform distribution](../media/uniform-distribution.gif "Histogram with uniform distribution")</span></span>

 <span data-ttu-id="334c3-113">Para más información sobre los algoritmos que proporciona [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vea [Algoritmos de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="334c3-113">For more information about the algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="334c3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="334c3-114">See Also</span></span>
 <span data-ttu-id="334c3-115">[Tipos de contenido &#40;](content-types-data-mining.md) [estructuras de minería de datos&#41;de minería de datos &#40;Analysis Services-minería de datos&#41;métodos de](mining-structures-analysis-services-data-mining.md) [discretización &#40;](discretization-methods-data-mining.md) [distribuciones](/sql/dmx/distributions-dmx)&#41;de minería de datos &#40;DMX&#41;columnas de la [estructura de minería](mining-structure-columns.md) de datos</span><span class="sxs-lookup"><span data-stu-id="334c3-115">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) [Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [Discretization Methods &#40;Data Mining&#41;](discretization-methods-data-mining.md) [Distributions &#40;DMX&#41;](/sql/dmx/distributions-dmx) [Mining Structure Columns](mining-structure-columns.md)</span></span>


