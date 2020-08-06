---
title: Administrar el ámbito y el contexto (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], context
- scope [MDX]
- CALCULATE statement
- This function [MDX]
- SCOPE statement
- scripts [MDX], scope
ms.assetid: 631e7c20-8be9-4c35-8609-76516aef19d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7cf1e6cea8df00b632e114a5a8756373738ca6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671736"
---
# <a name="managing-scope-and-context-mdx"></a><span data-ttu-id="66021-102">Administrar el ámbito y el contexto (MDX)</span><span class="sxs-lookup"><span data-stu-id="66021-102">Managing Scope and Context (MDX)</span></span>
  <span data-ttu-id="66021-103">En [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , un script de expresiones multidimensionales (MDX) se puede aplicar a todo el cubo, o a partes concretas del cubo, en puntos específicos de la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="66021-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script can apply to the entire cube, or to specific portions of the cube, at specific points within the execution of the script.</span></span> <span data-ttu-id="66021-104">El script MDX puede adoptar un enfoque en capas de los cálculos del cubo mediante el uso de pasos de cálculo.</span><span class="sxs-lookup"><span data-stu-id="66021-104">The MDX script can take a layered approach to calculations within a cube through the use of calculation passes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66021-105">Para obtener más información sobre el impacto que tienen los pasos de cálculo, vea [Descripción de orden de paso y orden de resolución &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="66021-105">For more information on how calculation passes can affect calculations, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="66021-106">Para controlar el paso de cálculo, el ámbito y el contexto de un script MDX, se pueden usar específicamente la instrucción CACULATE, la función `This` y la instrucción SCOPE.</span><span class="sxs-lookup"><span data-stu-id="66021-106">To control the calculation pass, scope, and context within an MDX script, you specifically use the CACULATE statement, the `This` function, and the SCOPE statement.</span></span>  
  
## <a name="using-the-calculate-statement"></a><span data-ttu-id="66021-107">Usar la instrucción CALCULATE</span><span class="sxs-lookup"><span data-stu-id="66021-107">Using the CALCULATE Statement</span></span>  
 <span data-ttu-id="66021-108">La instrucción CALCULATE rellena cada celda del cubo con datos agregados.</span><span class="sxs-lookup"><span data-stu-id="66021-108">The CALCULATE statement populates each cell in the cube with aggregated data.</span></span> <span data-ttu-id="66021-109">Por ejemplo, el script MDX predeterminado tiene una única instrucción CALCULATE al principio del script.</span><span class="sxs-lookup"><span data-stu-id="66021-109">For example, the default MDX script has a single CALCULATE statement at the beginning of the script.</span></span>  
  
 <span data-ttu-id="66021-110">Para obtener más información sobre la sintaxis de la instrucción CALCULATE, vea [CALCULATE &#40;instrucciónMDX&#41;](/sql/mdx/mdx-scripting-calculate).</span><span class="sxs-lookup"><span data-stu-id="66021-110">For more information on the syntax of the CALCULATE statement, see [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66021-111">Si el script contiene una instrucción SCOPE que incluya una instrucción CALCULATE, MDX evalúa la instrucción CALCULATE en el contexto del subcubo definido por la instrucción SCOPE, no en relación a todo el cubo.</span><span class="sxs-lookup"><span data-stu-id="66021-111">If the script contains a SCOPE statement that contains a CALCULATE statement, MDX evaluates the CALCULATE statement within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
## <a name="using-the-this-function"></a><span data-ttu-id="66021-112">Usar la función This</span><span class="sxs-lookup"><span data-stu-id="66021-112">Using the This Function</span></span>  
 <span data-ttu-id="66021-113">La función `This` permite recuperar el subcubo actual en un script MDX.</span><span class="sxs-lookup"><span data-stu-id="66021-113">The `This` function lets you retrieve the current subcube within an MDX script.</span></span> <span data-ttu-id="66021-114">La función `This` también se puede usar para establecer con rapidez los valores de las celdas del subcubo actual en una expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="66021-114">You can use the `This` function to quickly set the value of cells within the current subcube to an MDX expression.</span></span> <span data-ttu-id="66021-115">Por lo general, la función `This` se usa en combinación con la instrucción SCOPE para cambiar el contenido de un subcubo específico durante un paso de cálculo determinado.</span><span class="sxs-lookup"><span data-stu-id="66021-115">You often use the `This` function in conjunction with the SCOPE statement to change the contents of a specific subcube during a specific calculation pass.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66021-116">Si el script contiene una instrucción SCOPE que incluya una función `This`, MDX evalúa la función `This` en el contexto del subcubo definido por la instrucción SCOPE, no en relación a todo el cubo.</span><span class="sxs-lookup"><span data-stu-id="66021-116">If the script contains a SCOPE statement that contains a `This` function, MDX evaluates the `This` function within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
### <a name="this-function-example"></a><span data-ttu-id="66021-117">Ejemplo de la función This</span><span class="sxs-lookup"><span data-stu-id="66021-117">This Function Example</span></span>  
 <span data-ttu-id="66021-118">En el siguiente ejemplo de un comando de script MDX, se utiliza la función `This` para aumentar el valor de la medida Amount (en el grupo de medida Finance del cubo de ejemplo de [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)]) en un 10% para los elementos secundarios del miembro Redmond de la dimensión Customer:</span><span class="sxs-lookup"><span data-stu-id="66021-118">The following MDX script command example uses the `This` function to increase the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension:</span></span>  
  
```  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="66021-119">Para obtener más información sobre la sintaxis de la `This` función, vea [esta &#40;MDX&#41;](/sql/mdx/this-mdx).</span><span class="sxs-lookup"><span data-stu-id="66021-119">For more information on the syntax of the `This` function, see [This &#40;MDX&#41;](/sql/mdx/this-mdx).</span></span>  
  
## <a name="using-the-scope-statement"></a><span data-ttu-id="66021-120">Usar la instrucción SCOPE</span><span class="sxs-lookup"><span data-stu-id="66021-120">Using the SCOPE Statement</span></span>  
 <span data-ttu-id="66021-121">La instrucción SCOPE define el subcubo actual que contiene otras expresiones e instrucciones MDX en el script MDX y especifica su ámbito.</span><span class="sxs-lookup"><span data-stu-id="66021-121">The SCOPE statement defines the current subcube that contains, and specifies the scope of, other MDX expressions and statements within an MDX script.</span></span> <span data-ttu-id="66021-122">MDX evalúa estas otras expresiones e instrucciones MDX, incluida la función `This` y la instrucción CALCULATE, en el contexto del subcubo.</span><span class="sxs-lookup"><span data-stu-id="66021-122">MDX evaluates this other MDX expressions and statements, including the `This` function and the CALCULATE statement, within the context of the subcube.</span></span>  
  
 <span data-ttu-id="66021-123">Las instrucciones SCOPE son dinámicas, pero no iterativas por naturaleza.</span><span class="sxs-lookup"><span data-stu-id="66021-123">A SCOPE statement is dynamic, but not iterative in nature.</span></span> <span data-ttu-id="66021-124">Las instrucciones incluidas en una instrucción SCOPE se ejecutan una sola vez, pero el subcubo en sí puede determinarse dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="66021-124">The statements contained within a SCOPE statement run once, but the subcube itself can be dynamically determined.</span></span> <span data-ttu-id="66021-125">Por ejemplo, suponga que tiene un cubo denominado SampleCube.</span><span class="sxs-lookup"><span data-stu-id="66021-125">For example, you have a cube named SampleCube.</span></span> <span data-ttu-id="66021-126">A continuación aplica la siguiente instrucción SCOPE al cubo SampleCube para definir un subcubo que defina a su vez el contexto como ALLMEMBERS en la dimensión Measures:</span><span class="sxs-lookup"><span data-stu-id="66021-126">Against the SampleCube cube, you apply the following SCOPE statement to define a subcube the defines the context as the ALLMEMBERS within the Measures dimension:</span></span>  
  
 `SCOPE([Measures].ALLMEMBERS);`  
  
 `THIS = [Measures].ALLMEMBERS.COUNT;`  
  
 `END SCOPE;`  
  
 <span data-ttu-id="66021-127">Las instrucciones y expresiones de esta instrucción SCOPE se ejecutan una vez.</span><span class="sxs-lookup"><span data-stu-id="66021-127">The statements and expressions within this SCOPE statement run once.</span></span>  
  
 <span data-ttu-id="66021-128">A continuación, un usuario del negocio ejecuta la siguiente consulta MDX que incluye una medida, denominada ExistingMeasure, en el cubo SampleCube:</span><span class="sxs-lookup"><span data-stu-id="66021-128">Now, a business user runs the following MDX query that contains one measure, named ExistingMeasure, against the SampleCube cube:</span></span>  
  
 `WITH MEMBER [Measures].[NewMeasure] AS '1'`  
  
 `SELECT`  
  
 `[Measures].ALLMEMBERS ON COLUMNS,`  
  
 `[Customer].DEFAULTMEMBER ON ROWS`  
  
 `FROM`  
  
 `[SampleCube]`  
  
 <span data-ttu-id="66021-129">El conjunto de celdas que devuelve la consulta se parece al resultado que se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="66021-129">The cellset returned from the query resembles the output shown in the following table.</span></span>  
  
||<span data-ttu-id="66021-130">[ExistingMeasure]</span><span class="sxs-lookup"><span data-stu-id="66021-130">[ExistingMeasure]</span></span>|<span data-ttu-id="66021-131">[NewMeasure]</span><span class="sxs-lookup"><span data-stu-id="66021-131">[NewMeasure]</span></span>|  
|-|-------------------------|--------------------|  
|<span data-ttu-id="66021-132">[Customer].[All]</span><span class="sxs-lookup"><span data-stu-id="66021-132">[Customer].[All]</span></span>|<span data-ttu-id="66021-133">2</span><span class="sxs-lookup"><span data-stu-id="66021-133">2</span></span>|<span data-ttu-id="66021-134">2</span><span class="sxs-lookup"><span data-stu-id="66021-134">2</span></span>|  
  
 <span data-ttu-id="66021-135">Si examinamos el conjunto de celdas devuelto, veremos que el valor ExistingMeasure, incluido en la instrucción SCOPE del script MDX, se actualiza dinámicamente después de definir la medida NewMeasure.</span><span class="sxs-lookup"><span data-stu-id="66021-135">Looking at the returned cellset, notice how the ExistingMeasure value, included in the SCOPE statement within the MDX script, is dynamically updated after the measure NewMeasure was defined.</span></span>  
  
 <span data-ttu-id="66021-136">Las instrucciones SCOPE pueden anidarse en otras instrucciones SCOPE.</span><span class="sxs-lookup"><span data-stu-id="66021-136">A SCOPE statement can be nested within another SCOPE statement.</span></span> <span data-ttu-id="66021-137">Sin embargo, dado que las instrucciones SCOPE no son iterativas, el objetivo principal de anidar este tipo de instrucciones radica en la posibilidad de subdividir todavía más un subcubo para tratamientos especiales.</span><span class="sxs-lookup"><span data-stu-id="66021-137">However, as the SCOPE statement is not iterative, the primary purpose for nesting SCOPE statements is to further subdivide a subcube for special treatment.</span></span>  
  
### <a name="scope-statement-example"></a><span data-ttu-id="66021-138">Ejemplo de la instrucción SCOPE</span><span class="sxs-lookup"><span data-stu-id="66021-138">SCOPE Statement Example</span></span>  
 <span data-ttu-id="66021-139">En el siguiente ejemplo de script MDX se utiliza la instrucción SCOPE para aumentar el valor de la medida Amount (en el grupo de medida Finance del cubo de ejemplo de [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] ) en un 10% para los elementos secundarios del miembro Redmond de la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="66021-139">The following MDX script example uses a SCOPE statement to sets the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension.</span></span> <span data-ttu-id="66021-140">No obstante, otra instrucción SCOPE cambia el subcubo de forma que incluya la medida Amount para los elementos secundarios del año 2002.</span><span class="sxs-lookup"><span data-stu-id="66021-140">However, another SCOPE statement changes the subcube to include the Amount measure for the children of the 2002 calendar year.</span></span> <span data-ttu-id="66021-141">Por último, la medida Amount se agrega solo a dicho subcubo, sin modificar los valores agregados de la medida Amount correspondientes a otros años.</span><span class="sxs-lookup"><span data-stu-id="66021-141">Finally, the Amount measure is then aggregated only for that subcube, leaving the aggregated values for the Amount measure in other calendar years unchanged.</span></span>  
  
```  
/* Calculate the entire cube first. */  
CALCULATE;  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="66021-142">Para obtener más información sobre la sintaxis de la instrucción SCOPE, vea [SCOPE &#40;Instrucción,MDX&#41;](/sql/mdx/mdx-scripting-scope).</span><span class="sxs-lookup"><span data-stu-id="66021-142">For more information on the syntax of the SCOPE statement, see [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66021-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66021-143">See Also</span></span>  
 <span data-ttu-id="66021-144">[Referencia del lenguaje MDX &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="66021-144">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 <span data-ttu-id="66021-145">[Script MDX básico &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="66021-145">[The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span></span>  
 [<span data-ttu-id="66021-146">Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="66021-146">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
