---
title: Crear celdas calculadas de ámbito de sesión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 199de07778a153cd1bc40b5033d364e5e0055bd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671734"
---
# <a name="creating-session-scoped-calculated-cells"></a><span data-ttu-id="a80f2-102">Crear celdas calculadas de ámbito de sesión</span><span class="sxs-lookup"><span data-stu-id="a80f2-102">Creating Session-Scoped Calculated Cells</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="a80f2-103">Esta sintaxis ya no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a80f2-103">This syntax has been deprecated.</span></span> <span data-ttu-id="a80f2-104">En su lugar debería utilizar asignaciones MDX.</span><span class="sxs-lookup"><span data-stu-id="a80f2-104">You should use MDX assignments should instead.</span></span> <span data-ttu-id="a80f2-105">Para más información sobre asignaciones, vea [Script MDX básico &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a80f2-105">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="a80f2-106">Para crear celdas calculadas disponibles para todas las consultas realizadas en la misma sesión, se pueden utilizar las instrucciones [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) o [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) .</span><span class="sxs-lookup"><span data-stu-id="a80f2-106">To create calculated cells that are available to all queries in the same session, you can use either the [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) statement or the [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) statement.</span></span> <span data-ttu-id="a80f2-107">Ambas devuelven el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="a80f2-107">Both statements have the same result.</span></span>  
  
## <a name="create-cell-calculation-syntax"></a><span data-ttu-id="a80f2-108">Sintaxis de CREATE CELL CALCULATION</span><span class="sxs-lookup"><span data-stu-id="a80f2-108">CREATE CELL CALCULATION Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a80f2-109">Esta sintaxis ya no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a80f2-109">This syntax has been deprecated.</span></span> <span data-ttu-id="a80f2-110">En su lugar debería utilizar asignaciones MDX.</span><span class="sxs-lookup"><span data-stu-id="a80f2-110">You should use MDX assignments should instead.</span></span> <span data-ttu-id="a80f2-111">Para más información sobre asignaciones, vea [Script MDX básico &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a80f2-111">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="a80f2-112">Utilice la siguiente sintaxis si desea definir una celda calculada de ámbito de sesión mediante la instrucción CREATE CELL CALCULATION:</span><span class="sxs-lookup"><span data-stu-id="a80f2-112">Use the following syntax to use the CREATE CELL CALCULATION statement to define a session-scoped calculated cell:</span></span>  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a><span data-ttu-id="a80f2-113">Sintaxis de ALTER CUBE</span><span class="sxs-lookup"><span data-stu-id="a80f2-113">ALTER CUBE Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a80f2-114">Esta sintaxis ya no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a80f2-114">This syntax has been deprecated.</span></span> <span data-ttu-id="a80f2-115">En su lugar debería utilizar asignaciones MDX.</span><span class="sxs-lookup"><span data-stu-id="a80f2-115">You should use MDX assignments should instead.</span></span> <span data-ttu-id="a80f2-116">Para más información sobre asignaciones, vea [Script MDX básico &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a80f2-116">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="a80f2-117">Utilice la siguiente sintaxis si desea definir una celda calculada de ámbito de sesión mediante la instrucción ALTER CUBE:</span><span class="sxs-lookup"><span data-stu-id="a80f2-117">Use the following syntax to use the ALTER CUBE statement to define a session-scoped calculated cell:</span></span>  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 <span data-ttu-id="a80f2-118">El valor `String_Expression` contiene una lista de expresiones de conjunto MDX ortogonales de una sola dimensión, cada una de las cuales debe resolverse en alguna de las siguientes categorías de conjuntos que se indican en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="a80f2-118">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions, each of which must resolve to one of the categories of sets that are listed in the following table.</span></span>  
  
|<span data-ttu-id="a80f2-119">Category</span><span class="sxs-lookup"><span data-stu-id="a80f2-119">Category</span></span>|<span data-ttu-id="a80f2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="a80f2-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a80f2-121">Conjunto vacío</span><span class="sxs-lookup"><span data-stu-id="a80f2-121">Empty set</span></span>|<span data-ttu-id="a80f2-122">Una expresión de conjunto MDX que se resuelve en un conjunto vacío.</span><span class="sxs-lookup"><span data-stu-id="a80f2-122">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="a80f2-123">En este caso, el ámbito de la celda calculada es todo el cubo.</span><span class="sxs-lookup"><span data-stu-id="a80f2-123">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="a80f2-124">Conjunto de un solo miembro</span><span class="sxs-lookup"><span data-stu-id="a80f2-124">Single member set</span></span>|<span data-ttu-id="a80f2-125">Una expresión de conjunto MDX que se resuelve en un solo miembro.</span><span class="sxs-lookup"><span data-stu-id="a80f2-125">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="a80f2-126">Conjunto de miembros de nivel</span><span class="sxs-lookup"><span data-stu-id="a80f2-126">Set of level members</span></span>|<span data-ttu-id="a80f2-127">Una expresión de conjunto MDX que se resuelve en miembros de un solo nivel.</span><span class="sxs-lookup"><span data-stu-id="a80f2-127">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="a80f2-128">Un ejemplo de esto es el *Level_Expression*.`Members`</span><span class="sxs-lookup"><span data-stu-id="a80f2-128">An example of this is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="a80f2-129">Función MDX.</span><span class="sxs-lookup"><span data-stu-id="a80f2-129">MDX function.</span></span> <span data-ttu-id="a80f2-130">Para incluir miembros calculados, use el *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="a80f2-130">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="a80f2-131">Función MDX.</span><span class="sxs-lookup"><span data-stu-id="a80f2-131">MDX function.</span></span><br /><br /> <span data-ttu-id="a80f2-132">Para más información, vea [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="a80f2-132">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="a80f2-133">Conjunto de descendientes</span><span class="sxs-lookup"><span data-stu-id="a80f2-133">Set of descendants</span></span>|<span data-ttu-id="a80f2-134">Una expresión de conjunto MDX que se resuelve en los descendientes de un miembro determinado.</span><span class="sxs-lookup"><span data-stu-id="a80f2-134">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="a80f2-135">Un ejemplo de esto es la `Descendants` función MDX (*Member_Expression*, *Level_Expression*, *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="a80f2-135">An example of this is the `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*) MDX function.</span></span><br /><br /> <span data-ttu-id="a80f2-136">Para más información, vea [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="a80f2-136">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a80f2-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a80f2-137">See Also</span></span>  
 [<span data-ttu-id="a80f2-138">Generar cálculos de celdas en MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a80f2-138">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
