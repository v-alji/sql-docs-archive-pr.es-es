---
title: Script MDX básico (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default MDX scripts
- statements [MDX]
- expressions [MDX], scripts
- scripts [MDX], about scripts
ms.assetid: 83d9afda-7d34-42b5-8f28-20172a905f23
author: minewiskan
ms.author: owend
ms.openlocfilehash: de0d2fea002beda0eca480bd27140bdd202fcb83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748331"
---
# <a name="the-basic-mdx-script-mdx"></a><span data-ttu-id="86ede-102">Script MDX básico (MDX)</span><span class="sxs-lookup"><span data-stu-id="86ede-102">The Basic MDX Script (MDX)</span></span>
  <span data-ttu-id="86ede-103">Un script de expresiones multidimensionales (MDX) define el proceso de cálculo de un cubo en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86ede-103">A Multidimensional Expressions (MDX) script defines the calculation process for a cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="86ede-104">Hay dos tipos de scripts MDX:</span><span class="sxs-lookup"><span data-stu-id="86ede-104">There are two types of MDX scripts:</span></span>  
  
 <span data-ttu-id="86ede-105">**Script MDX predeterminado**</span><span class="sxs-lookup"><span data-stu-id="86ede-105">**The default MDX script**</span></span>  
 <span data-ttu-id="86ede-106">Al crear un cubo, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] crea un script MDX predeterminado para el cubo.</span><span class="sxs-lookup"><span data-stu-id="86ede-106">At the time that you create a cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates a default MDX script for that cube.</span></span> <span data-ttu-id="86ede-107">Este script define un paso de cálculo para todo el cubo.</span><span class="sxs-lookup"><span data-stu-id="86ede-107">This script defines a calculation pass for the whole cube.</span></span>  
  
 <span data-ttu-id="86ede-108">**Script MDX definido por el usuario**</span><span class="sxs-lookup"><span data-stu-id="86ede-108">**User-defined MDX script**</span></span>  
 <span data-ttu-id="86ede-109">Después de crear el cubo, se pueden agregar scripts MDX definidos por el usuario que amplían las capacidades de cálculo del cubo.</span><span class="sxs-lookup"><span data-stu-id="86ede-109">After you have created a cube, you can add user-defined MDX scripts that extend the calculation capabilities of the cube.</span></span>  
  
## <a name="the-default-mdx-script"></a><span data-ttu-id="86ede-110">Script MDX predeterminado</span><span class="sxs-lookup"><span data-stu-id="86ede-110">The Default MDX Script</span></span>  
 <span data-ttu-id="86ede-111">El script MDX predeterminado que crea [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] al definir un cubo contiene una sola instrucción CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="86ede-111">The default MDX script that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates when you define a cube contains a single CALCULATE statement.</span></span> <span data-ttu-id="86ede-112">Esta única instrucción CALCULATE se ubica al comienzo del script MDX predeterminado e indica que todo el cubo debe calcularse durante el primer paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="86ede-112">This single CALCULATE statement is at the beginning of the default MDX script, and indicates that the entire cube should be calculated during the first calculation pass.</span></span>  
  
 <span data-ttu-id="86ede-113">El script MDX predeterminado también incluye los comandos que crean conjuntos con nombre, asignaciones y miembros calculados creados en el Diseñador de cubos:</span><span class="sxs-lookup"><span data-stu-id="86ede-113">The default MDX script also contains the script commands that create named sets, assignments, and calculated members created in Cube Designer:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="86ede-114">agrega directamente comandos de script al script MDX predeterminado.</span><span class="sxs-lookup"><span data-stu-id="86ede-114">directly adds script commands to the default MDX script.</span></span>  
  
-   <span data-ttu-id="86ede-115">Para cada conjunto con nombre del cubo existe una instrucción CREATE SET correspondiente en el script MDX predeterminado.</span><span class="sxs-lookup"><span data-stu-id="86ede-115">For each named set in the cube, a corresponding CREATE SET statement exists in the default MDX script.</span></span>  
  
-   <span data-ttu-id="86ede-116">Para cada miembro calculado definido en el cubo existe una instrucción CREATE MEMBER correspondiente en el script MDX predeterminado.</span><span class="sxs-lookup"><span data-stu-id="86ede-116">For each calculated member defined in the cube, a corresponding CREATE MEMBER statement exists in the default MDX script.</span></span>  
  
 <span data-ttu-id="86ede-117">Para controlar el orden de los comandos de script, conjuntos con nombre y miembros calculados del script MDX predeterminado puede utilizar la pestaña **Cálculos** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="86ede-117">You can control the order of script commands, named sets, and calculated members in the default MDX script by using the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="86ede-118">Para más información sobre cómo definir los cálculos almacenados en el script MDX predeterminado, vea [Cálculos en modelos multidimensionales](../calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="86ede-118">For more information on defining calculations stored in the default MDX script, see [Calculations in Multidimensional Models](../calculations-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="86ede-119">Si no se asocia ningún script MDX a un cubo, éste asume el script MDX predeterminado.</span><span class="sxs-lookup"><span data-stu-id="86ede-119">If there is no MDX script associated with a cube, the cube assumes the default MDX script.</span></span> <span data-ttu-id="86ede-120">Es necesario asociar los cubos a un script MDX como mínimo, ya que los cubos se basan en estos scripts para determinar el comportamiento del cálculo.</span><span class="sxs-lookup"><span data-stu-id="86ede-120">A cube needs to be associated with at least one MDX script because a cube relies on the MDX script to determine calculation behavior.</span></span> <span data-ttu-id="86ede-121">Es decir, un cubo que no se haya asociado a ningún script MDX o que se haya asociado a un script MDX vacío no podría calcular ninguna celda.</span><span class="sxs-lookup"><span data-stu-id="86ede-121">In other words, a cube that was not associated with an MDX script or was associated with an empty MDX script could not and would not be able to calculate any cells.</span></span> <span data-ttu-id="86ede-122">Si crea los cubos mediante programación, mediante comandos ASSL (Analysis Services Scripting Language) o mediante los Objetos de administración de análisis (AMO), se recomienda crear un script MDX predeterminad que contenga una única instrucción CALCULATE para el cubo.</span><span class="sxs-lookup"><span data-stu-id="86ede-122">If you programmatically create cubes, either by using Analysis Services Scripting Language (ASSL) commands or by using Analysis Management Objects (AMO), it is recommended that you create a default MDX script containing a single CALCULATE statement for the cube.</span></span>  
  
## <a name="mdx-script-content"></a><span data-ttu-id="86ede-123">Contenido del script MDX</span><span class="sxs-lookup"><span data-stu-id="86ede-123">MDX Script Content</span></span>  
 <span data-ttu-id="86ede-124">Un script MDX puede incluir las siguientes instrucciones y expresiones:</span><span class="sxs-lookup"><span data-stu-id="86ede-124">An MDX script can contain the following statements and expressions:</span></span>  
  
 <span data-ttu-id="86ede-125">Todas las instrucciones de scripting MDX</span><span class="sxs-lookup"><span data-stu-id="86ede-125">All MDX scripting statements</span></span>  
 <span data-ttu-id="86ede-126">En los scripts MDX, las instrucciones de scripting MDX controlan el contexto y el ámbito de los cálculos y administran el comportamiento de otras instrucciones del script MDX.</span><span class="sxs-lookup"><span data-stu-id="86ede-126">In MDX scripts, MDX scripting statements control the context and scope of calculations, and manage the behavior of other statements in the MDX script.</span></span> <span data-ttu-id="86ede-127">Esta categoría incluye las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="86ede-127">This category includes the following statements:</span></span>  
  
-   [<span data-ttu-id="86ede-128">Actualice</span><span class="sxs-lookup"><span data-stu-id="86ede-128">CALCULATE</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
-   [<span data-ttu-id="86ede-129">INMOVILICE</span><span class="sxs-lookup"><span data-stu-id="86ede-129">FREEZE</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
-   [<span data-ttu-id="86ede-130">ID</span><span class="sxs-lookup"><span data-stu-id="86ede-130">SCOPE</span></span>](/sql/mdx/mdx-scripting-scope)  
  
 <span data-ttu-id="86ede-131">Para más información sobre las instrucciones para scripting de MDX, vea [Instrucciones para scripting de MDX &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span><span class="sxs-lookup"><span data-stu-id="86ede-131">For more information on MDX scripting statements, see [MDX Scripting Statements &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span></span>  
  
 [<span data-ttu-id="86ede-132">CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="86ede-132">CREATE MEMBER</span></span>](/sql/mdx/mdx-data-definition-create-member)  
 <span data-ttu-id="86ede-133">La instrucción CREATE MEMBER crea miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="86ede-133">The CREATE MEMBER statement creates calculated members.</span></span> <span data-ttu-id="86ede-134">Para más información sobre cómo crear miembros calculados, vea [Generar miembros calculados en MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="86ede-134">For more information about how to create calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
 [<span data-ttu-id="86ede-135">CREATE SET</span><span class="sxs-lookup"><span data-stu-id="86ede-135">CREATE SET</span></span>](/sql/mdx/mdx-data-definition-create-set)  
 <span data-ttu-id="86ede-136">La instrucción CREATE SET crea conjuntos con nombre.</span><span class="sxs-lookup"><span data-stu-id="86ede-136">The CREATE SET statement creates named sets.</span></span> <span data-ttu-id="86ede-137">Para más información sobre cómo crear conjuntos con nombre, vea [Crear conjuntos con nombre en MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="86ede-137">For more information about how to create names sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="86ede-138">Instrucciones condicionales</span><span class="sxs-lookup"><span data-stu-id="86ede-138">Conditional statements</span></span>  
 <span data-ttu-id="86ede-139">Las instrucciones condicionales agregan lógica condicional a los scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="86ede-139">Conditional statements add conditional logic to MDX scripts.</span></span> <span data-ttu-id="86ede-140">En esta categoría se incluyen las instrucciones [CASE](/sql/mdx/case-statement-mdx) e [IF](/sql/mdx/mdx-scripting-if) .</span><span class="sxs-lookup"><span data-stu-id="86ede-140">This category includes the [CASE](/sql/mdx/case-statement-mdx) and [IF](/sql/mdx/mdx-scripting-if) statements.</span></span>  
  
 <span data-ttu-id="86ede-141">Expresiones de asignación</span><span class="sxs-lookup"><span data-stu-id="86ede-141">Assignment expressions</span></span>  
 <span data-ttu-id="86ede-142">Las expresiones de asignación asignan una expresión, como un valor, a los subcubos restringidos.</span><span class="sxs-lookup"><span data-stu-id="86ede-142">An assignment expression assigns an expression, such as a value, to a constrained subcube.</span></span> <span data-ttu-id="86ede-143">Una expresión de subcubo restringido es una colección de expresiones de conjunto restringidas que definen los "bordes" de un subcubo de un script MDX.</span><span class="sxs-lookup"><span data-stu-id="86ede-143">A constrained subcube expression is a collection of constrained set expressions that define the "edges" of a subcube within an MDX script.</span></span> <span data-ttu-id="86ede-144">En los siguientes ejemplos de código se muestra la sintaxis de una expresión de subcubo restringido:</span><span class="sxs-lookup"><span data-stu-id="86ede-144">The following codes shows the syntax for a constrained subcube expression:</span></span>  
  
```  
<Constrained subcube> ::= (   
    ( <Constrained set> [<Crossjoin operator> <Constrained set>...] |  
    <ROOT function> |  
    <TREE function> |  
    LEAVES() |  
    * ) [, <Constrained subcube>...]  
<Constrained set> ::=   
    <Natural hierarchy>.MEMBERS |   
    <Natural hierarchy>.LEVEL(<numeric expression>).MEMBERS |   
    { <Natural hierarchy member> } |   
    DESCENDANTS( <Natural hierarchy member>, <Level expression>, ( SELF | AFTER | SELF_AND_AFTER ) ) |   
    DESCENDANTS( <Natural hierarchy member>, , LEAVES )  
<Natural hierarchy> ::= <Hierarchy identifier>  
<Natural hierarchy member> ::= <Natural hierarchy>.<identifier>[.<identifier>...]  
```  
  
## <a name="see-also"></a><span data-ttu-id="86ede-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86ede-145">See Also</span></span>  
 <span data-ttu-id="86ede-146">[Referencia del lenguaje MDX &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="86ede-146">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="86ede-147">Aspectos básicos de scripting MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="86ede-147">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
