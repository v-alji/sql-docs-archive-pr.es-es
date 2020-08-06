---
title: Restringir la consulta con ejes de consulta y segmentador (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], axes
- queries [MDX], axes
- axes [MDX]
- MDX [Analysis Services], axes
ms.assetid: a64b8172-cd73-42f9-8847-52e967b9697a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ed4d50aa40d2915c60f887e64cdc3ef8a6d52c5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747201"
---
# <a name="restricting-the-query-with-query-and-slicer-axes-mdx"></a><span data-ttu-id="3400d-102">Restringir la consulta con ejes de consulta y segmentador (MDX)</span><span class="sxs-lookup"><span data-stu-id="3400d-102">Restricting the Query with Query and Slicer Axes (MDX)</span></span>
  <span data-ttu-id="3400d-103">Cuando se formula una instrucción SELECT de Expresiones multidimensionales (MDX), una aplicación normalmente examina un cubo y divide el conjunto de jerarquías en dos subconjuntos:</span><span class="sxs-lookup"><span data-stu-id="3400d-103">When formulating a Multidimensional Expressions (MDX) SELECT statement, an application typically examines a cube and divides the set of hierarchies into two subsets:</span></span>  
  
-   <span data-ttu-id="3400d-104">**Ejes de consulta**: conjunto de jerarquías a partir del cual se recuperan los datos de varios miembros.</span><span class="sxs-lookup"><span data-stu-id="3400d-104">**Query axes**-the set of hierarchies from which data is retrieved for multiple members.</span></span> <span data-ttu-id="3400d-105">Para obtener más información sobre los ejes de consulta, vea [Especificar el contenido de un eje de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="3400d-105">For more information about query axes, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="3400d-106">**Eje segmentador**: conjunto de jerarquías a partir del cual se recuperan los datos para un solo miembro.</span><span class="sxs-lookup"><span data-stu-id="3400d-106">**Slicer axis**-the set of hierarchies from which data is retrieved for a single member.</span></span> <span data-ttu-id="3400d-107">Para obtener más información sobre el eje segmentador, vea [Especificar el contenido de un eje de división en sectores &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="3400d-107">For more information about the slicer axis, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
 <span data-ttu-id="3400d-108">Como los ejes de consulta y segmentador pueden construirse a partir de varias jerarquías del cubo que se va a consultar, estos términos se utilizan para diferenciar las jerarquías que emplea el cubo que se va a consultar de las jerarquías creadas en el cubo que devuelve una consulta de MDX.</span><span class="sxs-lookup"><span data-stu-id="3400d-108">Because query and slicer axes can be constructed from multiple hierarchies of the cube to be queried, these terms are used to differentiate the hierarchies used by the cube that is to be queried from the hierarchies created in the cube returned by an MDX query.</span></span>  
  
 <span data-ttu-id="3400d-109">Para ver un sencillo ejemplo del uso de los ejes de consulta y segmentador, consulte [Usar los ejes de consulta y segmentador en un ejemplo simple &#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span><span class="sxs-lookup"><span data-stu-id="3400d-109">To see a simple example using query and slicer axes, see [Using Query and Slicer Axes in a Simple Example &#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3400d-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3400d-110">See Also</span></span>  
 <span data-ttu-id="3400d-111">[Trabajar con miembros, tuplas y conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="3400d-111">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 [<span data-ttu-id="3400d-112">Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3400d-112">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
