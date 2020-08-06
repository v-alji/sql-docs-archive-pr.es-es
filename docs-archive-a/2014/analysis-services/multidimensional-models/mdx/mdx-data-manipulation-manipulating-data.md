---
title: Manipular datos (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], data manipulation
- data manipulation [MDX]
- Multidimensional Expressions [Analysis Services], data manipulation
ms.assetid: 4865192e-f46b-4ce5-b51c-9e08dbad5b85
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a1de8b9a3431d79573cd916fa7273b6d8fa7f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673355"
---
# <a name="manipulating-data-mdx"></a><span data-ttu-id="edca2-102">Manipular datos (MDX)</span><span class="sxs-lookup"><span data-stu-id="edca2-102">Manipulating Data (MDX)</span></span>

<span data-ttu-id="edca2-103">Las expresiones multidimensionales (MDX) pueden utilizarse para manipular los datos de diversas maneras.</span><span class="sxs-lookup"><span data-stu-id="edca2-103">Multidimensional Expressions (MDX) can be used to manipulate the data in a variety of ways.</span></span> <span data-ttu-id="edca2-104">En el artículo que se muestra en este artículo se tratan algunos de los conceptos más avanzados sobre la manipulación de datos en el lenguaje MDX.</span><span class="sxs-lookup"><span data-stu-id="edca2-104">The article listed in this article cover some of the more advanced concepts of data manipulation in the MDX language.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="edca2-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="edca2-105">In This Section</span></span>

|<span data-ttu-id="edca2-106">Tema</span><span class="sxs-lookup"><span data-stu-id="edca2-106">Topic</span></span>|<span data-ttu-id="edca2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="edca2-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="edca2-108">Usar DRILLTHROUGH para recuperar datos de origen &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="edca2-108">Using DRILLTHROUGH to Retrieve Source Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-retrieve-source-data-using-drillthrough.md)|<span data-ttu-id="edca2-109">Trata el uso de la instrucción [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) de MDX para recuperar los conjuntos de filas de los datos de origen aplicables a una celda en un origen de datos multidimensional.</span><span class="sxs-lookup"><span data-stu-id="edca2-109">Discusses the use of the MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) statement to retrieve the rowsets of source data applicable to a cell in a multidimensional data source</span></span>|  
|[<span data-ttu-id="edca2-110">Trabajar con la función RollupChildren &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="edca2-110">Working with the RollupChildren Function &#40;MDX&#41;</span></span>](mdx-data-manipulation-rollupchildren-function.md)|<span data-ttu-id="edca2-111">Describe el impacto de la [RollupChildren](/sql/mdx/rollupchildren-mdx) de MDX</span><span class="sxs-lookup"><span data-stu-id="edca2-111">Discusses the impact of the MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span></span>
|[<span data-ttu-id="edca2-112">Descripción de orden de paso y orden de resolución &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="edca2-112">Understanding Pass Order and Solve Order &#40;MDX&#41;</span></span>](mdx-data-manipulation-understanding-pass-order-and-solve-order.md)|<span data-ttu-id="edca2-113">Proporciona información detallada sobre los conceptos del orden de resolución y cómo esta característica puede afectar a las expresiones, instrucciones y scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="edca2-113">Details the concepts of solve order, and how this feature affects MDX expressions, statements, and scripts.</span></span>|  

<!-- ??

|[Script for Search and Replace] function on the analysis of multidimensional data.|

GeneMi is removing this commented row because it is unclear what article its link meant to link to.
Also, I had to add its leading '|' character, for consistency to aid bulk automated updated to our markdown source code.

GeneMi , 2019/01/19
-->

## <a name="see-also"></a><span data-ttu-id="edca2-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edca2-114">See Also</span></span>

[<span data-ttu-id="edca2-115">Aspectos básicos de las consultas MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="edca2-115">MDX Query Fundamentals (Analysis Services)</span></span>](mdx-query-fundamentals-analysis-services.md)
