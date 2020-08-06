---
title: Establecer el contexto de cubo en una consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], MDX
- MDX [Analysis Services], cube context
- SELECT statement [MDX]
- Multidimensional Expressions [Analysis Services], cube context
- queries [MDX], cube context
ms.assetid: 79d6a1e8-2825-4eb9-97df-5071aecae8f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72ae6e19f879651feb47841d70b444e9f845c74e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743655"
---
# <a name="establishing-cube-context-in-a-query-mdx"></a><span data-ttu-id="bf58c-102">Establecer el contexto de cubo en una consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="bf58c-102">Establishing Cube Context in a Query (MDX)</span></span>
  <span data-ttu-id="bf58c-103">Las consultas de MDX se ejecutan en un contexto de cubo especificado.</span><span class="sxs-lookup"><span data-stu-id="bf58c-103">Every MDX query runs within a specified cube context.</span></span> <span data-ttu-id="bf58c-104">En este contexto se definen los miembros que se evalúan mediante las expresiones contenidas en la consulta.</span><span class="sxs-lookup"><span data-stu-id="bf58c-104">This context defines the members that are evaluated by the expressions within the query.</span></span>  
  
 <span data-ttu-id="bf58c-105">En la instrucción SELECT, la cláusula FROM determina el contexto de cubo.</span><span class="sxs-lookup"><span data-stu-id="bf58c-105">In the SELECT statement, the FROM clause determines the cube context.</span></span> <span data-ttu-id="bf58c-106">Este contexto puede ser todo el cubo o simplemente un subcubo de ese cubo.</span><span class="sxs-lookup"><span data-stu-id="bf58c-106">This context can be the whole cube or just a subcube from that cube.</span></span> <span data-ttu-id="bf58c-107">Al especificar el contexto de cubo mediante la cláusula FROM, puede utilizar funciones adicionales para expandir o restringir ese contexto.</span><span class="sxs-lookup"><span data-stu-id="bf58c-107">Having specified cube context through the FROM clause, you can use additional functions to expand or restrict that context.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf58c-108">Las instrucciones SCOPE y CALCULATE también le permiten gestionar el contexto de cubo desde un script de MDX.</span><span class="sxs-lookup"><span data-stu-id="bf58c-108">The SCOPE and CALCULATE statements also let you manage cube context from within an MDX script.</span></span> <span data-ttu-id="bf58c-109">Para más información, vea [Aspectos básicos de scripting MDX &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf58c-109">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
## <a name="from-clause-syntax"></a><span data-ttu-id="bf58c-110">Sintaxis de la cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="bf58c-110">FROM Clause Syntax</span></span>  
 <span data-ttu-id="bf58c-111">La siguiente sintaxis describe la cláusula FROM:</span><span class="sxs-lookup"><span data-stu-id="bf58c-111">The following syntax describes the FROM clause:</span></span>  
  
```  
<SELECT subcube clause> ::=  
   Cube_Identifier |   
   (SELECT [  
      * |   
      ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]   
   FROM <SELECT subcube clause> <SELECT slicer axis clause> )  
```  
  
 <span data-ttu-id="bf58c-112">En esta sintaxis, observe que es la cláusula `<SELECT subcube clause>` la que describe el cubo o el subcubo en el que se ejecuta la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="bf58c-112">In this syntax, notice that it is the `<SELECT subcube clause>` clause that describes the cube or subcube on which the SELECT statement is executed.</span></span>  
  
 <span data-ttu-id="bf58c-113">Un sencillo ejemplo de una cláusula FROM sería una que se ejecutase contra la totalidad del cubo de ejemplo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="bf58c-113">A simple example of a FROM clause would be one that runs against the entire Adventure Works sample cube.</span></span> <span data-ttu-id="bf58c-114">Esa cláusula FROM tendría el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf58c-114">Such a FROM clause would have the following format:</span></span>  
  
```  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="bf58c-115">Para más información sobre la cláusula FROM de la instrucción MDX SELECT, vea [SELECT &#40;Instrucción, MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="bf58c-115">For more information about the FROM clause in the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="refining-the-context"></a><span data-ttu-id="bf58c-116">Refinar el contexto</span><span class="sxs-lookup"><span data-stu-id="bf58c-116">Refining the Context</span></span>  
 <span data-ttu-id="bf58c-117">Aunque la cláusula FROM especifica el contexto de cubo para un solo cubo, esto no debe limitarle a la hora de trabajar con datos de más de un cubo de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="bf58c-117">Although the FROM clause specifies the cube context as within a single cube, this does not have to limit you from working with data from more than one cube at a time.</span></span>  
  
 <span data-ttu-id="bf58c-118">Puede utilizar la función de MDX [LookupCube](/sql/mdx/lookupcube-mdx) para recuperar datos de cubos que se encuentren fuera del contexto de cubo.</span><span class="sxs-lookup"><span data-stu-id="bf58c-118">You can use the MDX [LookupCube](/sql/mdx/lookupcube-mdx) function to retrieve data from cubes outside the cube context.</span></span> <span data-ttu-id="bf58c-119">Además, funciones como [Filter](/sql/mdx/filter-mdx) están disponibles para permitir la restricción temporal del contexto mientras se evalúa la consulta.</span><span class="sxs-lookup"><span data-stu-id="bf58c-119">Additionally, functions such as the [Filter](/sql/mdx/filter-mdx) function, are available that allow temporary restriction of the context while evaluating the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf58c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf58c-120">See Also</span></span>  
 [<span data-ttu-id="bf58c-121">Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf58c-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
