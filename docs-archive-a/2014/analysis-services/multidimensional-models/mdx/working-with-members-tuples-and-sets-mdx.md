---
title: Trabajar con miembros, tuplas y conjuntos (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], tuples
- member keys [MDX]
- MDX [Analysis Services], sets
- calculated members [MDX]
- members [MDX]
- Multidimensional Expressions [Analysis Services], members
- named sets [MDX]
- Multidimensional Expressions [Analysis Services], tuples
- member functions [MDX]
- sets [MDX]
- MDX [Analysis Services], members
- member names [MDX]
- Multidimensional Expressions [Analysis Services], sets
- tuple functions
- tuples
- set functions [MDX]
ms.assetid: b6ec2439-caef-46d3-9fd7-5f4526cee334
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ce3bf2d5ad7df2b1cd74897b3b49c7cef97e8ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663148"
---
# <a name="working-with-members-tuples-and-sets-mdx"></a><span data-ttu-id="fdb20-102">Trabajar con miembros, tuplas y conjuntos (MDX)</span><span class="sxs-lookup"><span data-stu-id="fdb20-102">Working with Members, Tuples, and Sets (MDX)</span></span>
  <span data-ttu-id="fdb20-103">MDX proporciona varias funciones que devuelven uno o más miembros, tuplas o conjuntos; o que actúan sobre un miembro, tupla o conjunto.</span><span class="sxs-lookup"><span data-stu-id="fdb20-103">MDX provides numerous functions that return one or more members, tuples, or sets; or that act upon a member, tuple, or set.</span></span>  
  
## <a name="member-functions"></a><span data-ttu-id="fdb20-104">Funciones de miembro</span><span class="sxs-lookup"><span data-stu-id="fdb20-104">Member Functions</span></span>  
 <span data-ttu-id="fdb20-105">MDX proporciona varias funciones para recuperar miembros de otras entidades MDX, por ejemplo desde dimensiones, niveles, conjuntos o tuplas.</span><span class="sxs-lookup"><span data-stu-id="fdb20-105">MDX provides several functions for retrieving members from other MDX entities, such as from dimensions, levels, sets, or tuples.</span></span> <span data-ttu-id="fdb20-106">Por ejemplo, [FirstChild](/sql/mdx/firstchild-mdx) es una función que actúa sobre un miembro y devuelve un miembro.</span><span class="sxs-lookup"><span data-stu-id="fdb20-106">For example, the [FirstChild](/sql/mdx/firstchild-mdx) function is a function that acts upon a member and returns a member.</span></span>  
  
 <span data-ttu-id="fdb20-107">Para obtener el primer miembro secundario de la dimensión Time, se debe indicar explícitamente el miembro, como en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fdb20-107">To obtain the first child member of the Time dimension, you can explicitly state the member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].[CY 2001] on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="fdb20-108">También se puede utilizar la función `FirstChild` para devolver el mismo miembro, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fdb20-108">You can also use the `FirstChild` function to return the same member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].FirstChild on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="fdb20-109">Para obtener más información sobre las funciones de miembro de MDX, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-109">For more information about MDX member functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="tuple-functions"></a><span data-ttu-id="fdb20-110">funciones de tupla</span><span class="sxs-lookup"><span data-stu-id="fdb20-110">Tuple Functions</span></span>  
 <span data-ttu-id="fdb20-111">MDX proporciona varias funciones que devuelven tuplas y que se pueden utilizar en cualquier ubicación en la que se acepte una tupla.</span><span class="sxs-lookup"><span data-stu-id="fdb20-111">MDX provides several functions that return tuples, and they can be used anywhere that a tuple is accepted.</span></span> <span data-ttu-id="fdb20-112">Por ejemplo, la función [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) puede usarse para extraer la primera tupla de un conjunto, lo que resulta muy útil cuando se sabe que un conjunto está compuesto por una sola tupla y se quiere proporcionar esa tupla a una función que requiere una.</span><span class="sxs-lookup"><span data-stu-id="fdb20-112">For example, the [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) function can be used to extract the first tuple from set, which is very useful when you know that a set is composed of a single tuple and you want to supply that tuple to a function that requires a tuple.</span></span>  
  
 <span data-ttu-id="fdb20-113">El ejemplo siguiente devuelve la primera tupla desde el conjunto de tuplas en el eje de columna.</span><span class="sxs-lookup"><span data-stu-id="fdb20-113">The following example returns the first tuple from within the set of tuples on the column axis.</span></span>  
  
```  
SELECT {  
   ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2003]  
   )  
, ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2004]  
   )  
}.Item(0)  
ON COLUMNS   
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="fdb20-114">Para obtener más información sobre las funciones de tupla, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-114">For more information about tuple functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="set-functions"></a><span data-ttu-id="fdb20-115">Funciones de conjunto</span><span class="sxs-lookup"><span data-stu-id="fdb20-115">Set Functions</span></span>  
 <span data-ttu-id="fdb20-116">MDX proporciona varias funciones que devuelven conjuntos.</span><span class="sxs-lookup"><span data-stu-id="fdb20-116">MDX provides several functions that return sets.</span></span> <span data-ttu-id="fdb20-117">Escribir tuplas explícitamente y encerrarlas entre llaves no es la única manera de recuperar un conjunto.</span><span class="sxs-lookup"><span data-stu-id="fdb20-117">Explicitly typing tuples and enclosing them in braces is not the only way to retrieve a set.</span></span> <span data-ttu-id="fdb20-118">Para obtener más información sobre la función de miembros para devolver un conjunto, vea [Conceptos clave de MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="fdb20-118">For more information about the members function to return a set, see [Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span></span> <span data-ttu-id="fdb20-119">Hay muchas más funciones de conjunto.</span><span class="sxs-lookup"><span data-stu-id="fdb20-119">There are many additional set functions.</span></span>  
  
 <span data-ttu-id="fdb20-120">El operador dos puntos (:) permite utilizar el orden natural de los miembros para crear un conjunto.</span><span class="sxs-lookup"><span data-stu-id="fdb20-120">The colon operator lets you use the natural order of members to create a set.</span></span> <span data-ttu-id="fdb20-121">Por ejemplo, el conjunto que se muestra en el siguiente ejemplo incluye tuplas del primer al cuarto trimestre del año 2002.</span><span class="sxs-lookup"><span data-stu-id="fdb20-121">For example, the set shown in the following example contains tuples for the 1st through the 4th quarter of calendar year 2002.</span></span>  
  
```  
SELECT   
   {[Calendar Quarter].[Q1 CY 2002]:[Calendar Quarter].[Q4 CY 2002]}   
ON 0  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="fdb20-122">Si no utiliza el operador dos puntos para crear el conjunto, puede crear el mismo conjunto de miembros al especificar las tuplas en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdb20-122">If you do not use the colon operator to create the set, you can create the same set of members by specifying the tuples in the following example.</span></span>  
  
```  
SELECT {  
   [Calendar Quarter].[Q1 CY 2002],   
   [Calendar Quarter].[Q2 CY 2002],   
   [Calendar Quarter].[Q3 CY 2002],   
   [Calendar Quarter].[Q4 CY 2002]  
   } ON 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="fdb20-123">El operador dos puntos es una función inclusiva.</span><span class="sxs-lookup"><span data-stu-id="fdb20-123">The colon operator is an inclusive function.</span></span> <span data-ttu-id="fdb20-124">Los miembros ubicados a ambos lados del operador dos puntos se incluyen en el conjunto resultante.</span><span class="sxs-lookup"><span data-stu-id="fdb20-124">The members on both sides of the colon operator are included in the resulting set.</span></span>  
  
 <span data-ttu-id="fdb20-125">Para obtener más información sobre las funciones de conjuntos, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-125">For more information about set functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="array-functions"></a><span data-ttu-id="fdb20-126">Funciones de matriz</span><span class="sxs-lookup"><span data-stu-id="fdb20-126">Array Functions</span></span>  
 <span data-ttu-id="fdb20-127">Una función de matriz actúa sobre un conjunto y devuelve una matriz.</span><span class="sxs-lookup"><span data-stu-id="fdb20-127">An array function acts upon a set and returns an array.</span></span> <span data-ttu-id="fdb20-128">Para obtener más información sobre las funciones de matriz, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-128">For more information about array functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="hierarchy-functions"></a><span data-ttu-id="fdb20-129">Funciones de jerarquía</span><span class="sxs-lookup"><span data-stu-id="fdb20-129">Hierarchy Functions</span></span>  
 <span data-ttu-id="fdb20-130">Una función de jerarquía devuelve una jerarquía al actuar sobre un miembro, un nivel, una jerarquía o una cadena.</span><span class="sxs-lookup"><span data-stu-id="fdb20-130">A hierarchy function returns a hierarchy by acting upon a member, level, hierarchy, or string.</span></span> <span data-ttu-id="fdb20-131">Para obtener más información sobre las funciones de jerarquía, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-131">For more information about hierarchy functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="level-functions"></a><span data-ttu-id="fdb20-132">Funciones de nivel</span><span class="sxs-lookup"><span data-stu-id="fdb20-132">Level Functions</span></span>  
 <span data-ttu-id="fdb20-133">Una función de nivel devuelve un nivel al actuar sobre un miembro, un nivel o una cadena.</span><span class="sxs-lookup"><span data-stu-id="fdb20-133">A level function returns a level by acting upon a member, level, or string.</span></span> <span data-ttu-id="fdb20-134">Para obtener más información sobre las funciones de nivel, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-134">For more information about level functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="logical-functions"></a><span data-ttu-id="fdb20-135">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="fdb20-135">Logical Functions</span></span>  
 <span data-ttu-id="fdb20-136">Una función lógica actúa sobre una expresión MDX para devolver información acerca de las tuplas, miembros o conjuntos de la expresión.</span><span class="sxs-lookup"><span data-stu-id="fdb20-136">A logical function acts upon a MDX expression to return information about the tuples, members, or sets in the expression.</span></span> <span data-ttu-id="fdb20-137">Por ejemplo, la función [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) evalúa si una expresión ha devuelto un valor de celda vacía.</span><span class="sxs-lookup"><span data-stu-id="fdb20-137">For example, the [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) function evaluates whether an expression has returned an empty cell value.</span></span> <span data-ttu-id="fdb20-138">Para obtener más información sobre las funciones lógicas, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-138">For more information about logical functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="numeric-functions"></a><span data-ttu-id="fdb20-139">Funciones numéricas</span><span class="sxs-lookup"><span data-stu-id="fdb20-139">Numeric Functions</span></span>  
 <span data-ttu-id="fdb20-140">Una función numérica actúa sobre una expresión MDX para devolver un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="fdb20-140">A numeric function acts upon a MDX expression to return a scalar value.</span></span> <span data-ttu-id="fdb20-141">Por ejemplo, la función [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) devuelve un valor escalar que se calcula al agregar medidas sobre las tuplas de un conjunto especificado.</span><span class="sxs-lookup"><span data-stu-id="fdb20-141">For example, the [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) function returns a scalar value calculated by aggregating measures over the tuples in a specified set.</span></span> <span data-ttu-id="fdb20-142">Para obtener más información sobre las funciones numéricas, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-142">For more information about numeric functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="string-functions"></a><span data-ttu-id="fdb20-143">Funciones de cadena</span><span class="sxs-lookup"><span data-stu-id="fdb20-143">String Functions</span></span>  
 <span data-ttu-id="fdb20-144">Una función de cadena actúa sobre una expresión MDX para devolver una cadena.</span><span class="sxs-lookup"><span data-stu-id="fdb20-144">A string function acts upon a MDX expression to return a string.</span></span> <span data-ttu-id="fdb20-145">Por ejemplo, la función [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) devuelve un valor de cadena que contiene el nombre único de una dimensión, jerarquía, nivel o miembro.</span><span class="sxs-lookup"><span data-stu-id="fdb20-145">For example, the [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) function returns a string value containing the unique name of a dimension, hierarchy, level, or member.</span></span> <span data-ttu-id="fdb20-146">Para obtener más información sobre las funciones de cadena, vea [Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="fdb20-146">For more information about string functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb20-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdb20-147">See Also</span></span>  
 <span data-ttu-id="fdb20-148">[Conceptos clave de &#40;MDX Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="fdb20-148">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="fdb20-149">[Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="fdb20-149">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="fdb20-150">Referencia de funciones MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="fdb20-150">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
