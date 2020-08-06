---
title: Crear cálculos de celda de ámbito de consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped cell calculations [MDX]
ms.assetid: 45987daa-4400-41e9-add7-2428fd75709b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a9c9d529bfeb26b959b2521e4ce3c3d7f10d082
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750290"
---
# <a name="creating-query-scoped-cell-calculations-mdx"></a><span data-ttu-id="a91b0-102">Crear cálculos de celdas del ámbito de consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="a91b0-102">Creating Query-Scoped Cell Calculations (MDX)</span></span>
  <span data-ttu-id="a91b0-103">La palabra clave `WITH` en las expresiones multidimensionales (MDX) se usa para describir las celdas calculadas en el contexto de una consulta.</span><span class="sxs-lookup"><span data-stu-id="a91b0-103">You use the `WITH` keyword in Multidimensional Expressions (MDX) to describe calculated cells within the context of a query.</span></span> <span data-ttu-id="a91b0-104">La palabra clave `WITH` tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a91b0-104">The `WITH` keyword has the following syntax:</span></span>  
  
```  
WITH CELL CALCULATION Cube_Name.CellCalc_Identifier  String_Expression  
```  
  
 <span data-ttu-id="a91b0-105">El valor `CellCalc_Identifier` es el nombre de las celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="a91b0-105">The `CellCalc_Identifier` value is the name of the calculated cells.</span></span> <span data-ttu-id="a91b0-106">El valor `String_Expression` contiene una lista de expresiones de conjunto MDX ortogonales de una sola dimensión.</span><span class="sxs-lookup"><span data-stu-id="a91b0-106">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions.</span></span> <span data-ttu-id="a91b0-107">Cada una de estas expresiones de conjunto debe dar como resultado una de las categorías que figuran en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="a91b0-107">Each of these set expressions must resolve to one of the categories listed in the following table.</span></span>  
  
|<span data-ttu-id="a91b0-108">Category</span><span class="sxs-lookup"><span data-stu-id="a91b0-108">Category</span></span>|<span data-ttu-id="a91b0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a91b0-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a91b0-110">Conjunto vacío</span><span class="sxs-lookup"><span data-stu-id="a91b0-110">Empty set</span></span>|<span data-ttu-id="a91b0-111">Una expresión de conjunto MDX que se resuelve en un conjunto vacío.</span><span class="sxs-lookup"><span data-stu-id="a91b0-111">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="a91b0-112">En este caso, el ámbito de la celda calculada es todo el cubo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-112">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="a91b0-113">Conjunto de un solo miembro</span><span class="sxs-lookup"><span data-stu-id="a91b0-113">Single member set</span></span>|<span data-ttu-id="a91b0-114">Una expresión de conjunto MDX que se resuelve en un solo miembro.</span><span class="sxs-lookup"><span data-stu-id="a91b0-114">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="a91b0-115">Conjunto de miembros de nivel</span><span class="sxs-lookup"><span data-stu-id="a91b0-115">Set of level members</span></span>|<span data-ttu-id="a91b0-116">Una expresión de conjunto MDX que se resuelve en miembros de un solo nivel.</span><span class="sxs-lookup"><span data-stu-id="a91b0-116">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="a91b0-117">Un ejemplo de este tipo de expresión de conjunto es el *Level_Expression*.`Members`</span><span class="sxs-lookup"><span data-stu-id="a91b0-117">An example of such a set expression is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="a91b0-118">Función MDX.</span><span class="sxs-lookup"><span data-stu-id="a91b0-118">MDX function.</span></span> <span data-ttu-id="a91b0-119">Para incluir miembros calculados, use el *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="a91b0-119">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="a91b0-120">Función MDX.</span><span class="sxs-lookup"><span data-stu-id="a91b0-120">MDX function.</span></span> <span data-ttu-id="a91b0-121">Para más información, vea [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="a91b0-121">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="a91b0-122">Conjunto de descendientes</span><span class="sxs-lookup"><span data-stu-id="a91b0-122">Set of descendants</span></span>|<span data-ttu-id="a91b0-123">Una expresión de conjunto MDX que se resuelve en los descendientes de un miembro determinado.</span><span class="sxs-lookup"><span data-stu-id="a91b0-123">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="a91b0-124">Un ejemplo de este tipo de expresión de conjunto es la `Descendants` función MDX (*Member_Expression*, *Level_Expresion*, *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="a91b0-124">An example of such a set expression is the `Descendants`(*Member_Expression*, *Level_Expresion*, *Desc_Flag*) MDX function.</span></span> <span data-ttu-id="a91b0-125">Para más información, vea [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="a91b0-125">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
 <span data-ttu-id="a91b0-126">Si el argumento `String_Expression` no describe ninguna dimensión, MDX considera que se han incluido todos los miembros para generar el subcubo de cálculo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-126">If the `String_Expression` argument does not describe a dimension, MDX assumes that all members are included for the purposes of constructing the calculation subcube.</span></span> <span data-ttu-id="a91b0-127">Por lo tanto, si el argumento `String_Expression` tiene el valor NULL, la definición de las celdas calculadas se aplica a todo el cubo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-127">Therefore, if the `String_Expression` argument is NULL, the calculated cells definition applies to the whole cube.</span></span>  
  
 <span data-ttu-id="a91b0-128">El argumento `MDX_Expression` contiene una expresión MDX que se evalúa como un valor de celda para todas las celdas definidas en el argumento `String_Expression` .</span><span class="sxs-lookup"><span data-stu-id="a91b0-128">The `MDX_Expression` argument contains an MDX expression that evaluates to a cell value for all the cells defined in the `String_Expression` argument.</span></span>  
  
## <a name="additional-considerations"></a><span data-ttu-id="a91b0-129">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="a91b0-129">Additional Considerations</span></span>  
 <span data-ttu-id="a91b0-130">MDX procesa la condición de cálculo, especificada por la propiedad `CONDITION` solamente una vez.</span><span class="sxs-lookup"><span data-stu-id="a91b0-130">MDX processes the calculation condition, specified by the `CONDITION` property, only once.</span></span> <span data-ttu-id="a91b0-131">Este único procesamiento proporciona mayor rendimiento para la evaluación de varias definiciones de celdas calculadas, sobre todo con celdas calculadas superpuestas a través de pasos de cubo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-131">This single processing provides increased performance for the evaluation of multiple calculated cells definitions, especially with overlapping calculated cells across cube passes.</span></span>  
  
 <span data-ttu-id="a91b0-132">Este único procesamiento se lleva a cabo dependiendo del ámbito de creación establecido en la definición de las celdas calculadas:</span><span class="sxs-lookup"><span data-stu-id="a91b0-132">When this single processing occurs depends on the creation scope of the calculated cells definition:</span></span>  
  
-   <span data-ttu-id="a91b0-133">Si se crea en un ámbito global, como parte de un cubo, MDX procesa la condición de cálculo al mismo tiempo que el cubo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-133">If created at global scope, as part of a cube, MDX process the calculation condition when the cube is processed.</span></span> <span data-ttu-id="a91b0-134">Si se modifican de alguna manera las celdas del cubo y se incluyen en el subcubo de cálculo de una definición de celdas calculadas, la condición de cálculo puede no ser precisa hasta que el cubo vuelva a procesarse.</span><span class="sxs-lookup"><span data-stu-id="a91b0-134">If cells are modified in the cube in any way, and the cells are included in the calculation subcube of a calculated cells definition, the calculation condition may not be accurate until the cube is reprocessed.</span></span> <span data-ttu-id="a91b0-135">La modificación de las celdas puede producirse a partir de reescrituras, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-135">Cell modification can occur from writebacks, for example.</span></span> <span data-ttu-id="a91b0-136">La condición de cálculo se vuelve a procesar en el mismo momento que el cubo.</span><span class="sxs-lookup"><span data-stu-id="a91b0-136">The calculation condition is reprocessed when the cube is reprocessed.</span></span>  
  
-   <span data-ttu-id="a91b0-137">Si se creó en un ámbito de sesión, MDX procesa la condición de cálculo cuando la instrucción se emite durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="a91b0-137">If created at session scope, MDX process the calculation condition when the statement is issued during the session.</span></span> <span data-ttu-id="a91b0-138">Como en definiciones de celdas calculadas creadas globalmente, si se modifican las celdas, la condición de cálculo puede no ser precisa para la definición de celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="a91b0-138">As with calculated cells definitions created globally, if the cells are modified, the calculation condition may not be accurate for the calculated cells definition.</span></span>  
  
-   <span data-ttu-id="a91b0-139">Si se creó en un ámbito de consulta, MDX procesa la condición de cálculo cuando se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="a91b0-139">If created at query scope, MDX processes the calculation condition when the query runs.</span></span> <span data-ttu-id="a91b0-140">Aquí también se aplica el tema de modificación de las celdas, aunque las cuestiones de latencia de datos son mínimas debido al bajo tiempo de proceso de la ejecución de la consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="a91b0-140">The cell modification issue applies here, also, although data latency issues are minimal because of the low processing time of MDX query execution.</span></span>  
  
 <span data-ttu-id="a91b0-141">Por otro lado, MDX procesa la fórmula de cálculo siempre que se emite una consulta MDX en el cubo y ésta implica celdas incluidas en la definición de celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="a91b0-141">On the other hand, MDX processes the calculation formula whenever an MDX query is issued against the cube involving cells included in the calculated cells definition.</span></span> <span data-ttu-id="a91b0-142">Este procesamiento se lleva a cabo independientemente del ámbito de creación.</span><span class="sxs-lookup"><span data-stu-id="a91b0-142">This processing occurs regardless of the creation scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a91b0-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a91b0-143">See Also</span></span>  
 [<span data-ttu-id="a91b0-144">CREATE CELL CALCULATION &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a91b0-144">CREATE CELL CALCULATION Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
  