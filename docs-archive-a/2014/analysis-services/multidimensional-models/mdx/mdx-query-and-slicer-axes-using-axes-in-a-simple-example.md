---
title: Usar los ejes de consulta y segmentador en un ejemplo simple (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 324f082fd6659592e56af65680bd4aa623c625d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675022"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a><span data-ttu-id="8b641-102">Usar los ejes de consulta y segmentador en un ejemplo simple (MDX)</span><span class="sxs-lookup"><span data-stu-id="8b641-102">Using Query and Slicer Axes in a Simple Example (MDX)</span></span>
  <span data-ttu-id="8b641-103">En este sencillo ejemplo se ilustran los conceptos en los que se basa la especificación y el uso de los ejes de consulta y segmentador.</span><span class="sxs-lookup"><span data-stu-id="8b641-103">The simple example presented in this topic illustrates the basics of specifying and using query and slicer axes.</span></span>  
  
## <a name="the-cube"></a><span data-ttu-id="8b641-104">Cubo</span><span class="sxs-lookup"><span data-stu-id="8b641-104">The Cube</span></span>  
 <span data-ttu-id="8b641-105">Un cubo, denominado TestCube, tiene dos dimensiones simples: Route y Time.</span><span class="sxs-lookup"><span data-stu-id="8b641-105">A cube, named TestCube, has two simple dimensions named Route and Time.</span></span> <span data-ttu-id="8b641-106">Cada dimensión solo tiene una jerarquía de usuario, denominadas Route y Time respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8b641-106">Each dimension has only one user hierarchy, named Route and Time respectively.</span></span> <span data-ttu-id="8b641-107">Puesto que las medidas del cubo son parte de la dimensión Measures, este cubo tiene tres dimensiones en total.</span><span class="sxs-lookup"><span data-stu-id="8b641-107">Because the measures of the cube are part of the Measures dimension, this cube has three dimensions in all.</span></span>  
  
## <a name="the-query"></a><span data-ttu-id="8b641-108">Consulta</span><span class="sxs-lookup"><span data-stu-id="8b641-108">The Query</span></span>  
 <span data-ttu-id="8b641-109">La consulta va a proporcionar una matriz en la que la medida Packages se puede comparar con rutas (routes) y tiempos (times).</span><span class="sxs-lookup"><span data-stu-id="8b641-109">The query is to provide a matrix in which the Packages measure can be compared across routes and times.</span></span>  
  
 <span data-ttu-id="8b641-110">En la siguiente consulta MDX de ejemplo, las jerarquías Route y Time se utilizan como ejes de la consulta y la dimensión Measures como eje segmentador.</span><span class="sxs-lookup"><span data-stu-id="8b641-110">In the following MDX query example, the Route and Time hierarchies are the query axes, and the Measures dimension is the slicer axis.</span></span> <span data-ttu-id="8b641-111">La función [Members](/sql/mdx/members-set-mdx) indica que MDX usará los miembros de la jerarquía o el nivel para generar un conjunto.</span><span class="sxs-lookup"><span data-stu-id="8b641-111">The [Members](/sql/mdx/members-set-mdx) function indicates that MDX will use the members of the hierarchy or level to construct a set.</span></span> <span data-ttu-id="8b641-112">El uso de la función `Members` implica que no es necesario especificar explícitamente cada miembro de una jerarquía o un nivel específicos de una consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="8b641-112">The use of the `Members` function means that you do not have to explicitly state each member of a specific hierarchy or level in an MDX query.</span></span>  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a><span data-ttu-id="8b641-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="8b641-113">The Results</span></span>  
 <span data-ttu-id="8b641-114">El resultado es una cuadrícula que identifica el valor de la medida Packages en cada intersección de las dimensiones de eje COLUMNS y ROWS.</span><span class="sxs-lookup"><span data-stu-id="8b641-114">The result is a grid that identifies the value of the Packages measure at each intersection of the COLUMNS and ROWS axis dimensions.</span></span> <span data-ttu-id="8b641-115">En la tabla siguiente se muestra el aspecto que tendría la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8b641-115">The following table shows how this grid would look.</span></span>  
  
||<span data-ttu-id="8b641-116">post-</span><span class="sxs-lookup"><span data-stu-id="8b641-116">air</span></span>|<span data-ttu-id="8b641-117">sea</span><span class="sxs-lookup"><span data-stu-id="8b641-117">sea</span></span>|  
|-|---------|---------|  
|<span data-ttu-id="8b641-118">1st quarter</span><span class="sxs-lookup"><span data-stu-id="8b641-118">1st quarter</span></span>|<span data-ttu-id="8b641-119">60</span><span class="sxs-lookup"><span data-stu-id="8b641-119">60</span></span>|<span data-ttu-id="8b641-120">50</span><span class="sxs-lookup"><span data-stu-id="8b641-120">50</span></span>|  
|<span data-ttu-id="8b641-121">2nd quarter</span><span class="sxs-lookup"><span data-stu-id="8b641-121">2nd quarter</span></span>|<span data-ttu-id="8b641-122">45</span><span class="sxs-lookup"><span data-stu-id="8b641-122">45</span></span>|<span data-ttu-id="8b641-123">45</span><span class="sxs-lookup"><span data-stu-id="8b641-123">45</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b641-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b641-124">See Also</span></span>  
 <span data-ttu-id="8b641-125">[Especificar el contenido de un eje de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span><span class="sxs-lookup"><span data-stu-id="8b641-125">[Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span></span>  
 [<span data-ttu-id="8b641-126">Especificar el contenido de un eje de división en sectores &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8b641-126">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
