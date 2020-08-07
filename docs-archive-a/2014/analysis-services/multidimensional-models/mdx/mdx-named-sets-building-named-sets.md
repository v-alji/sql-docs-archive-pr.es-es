---
title: Crear conjuntos con nombre en MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], named sets
- named sets [MDX]
- sets [MDX]
- MDX [Analysis Services], named sets
- queries [MDX], named sets
- set expressions [MDX]
ms.assetid: 213b0035-e96d-4ba0-83f2-ded206905603
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91296f8c5d47afb15c67f0b60435c7f961734573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745444"
---
# <a name="building-named-sets-in-mdx-mdx"></a><span data-ttu-id="f1547-102">Crear conjuntos con nombre en MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="f1547-102">Building Named Sets in MDX (MDX)</span></span>
  <span data-ttu-id="f1547-103">Una expresión de conjunto puede ser una declaración extensa, compleja y, por tanto, difícil de seguir o entender.</span><span class="sxs-lookup"><span data-stu-id="f1547-103">A set expression can be a lengthy and complex declaration, and therefore be difficult to follow or understand.</span></span> <span data-ttu-id="f1547-104">O bien, una expresión de conjunto puede utilizarse con tanta frecuencia que definir repetidamente el conjunto sea fatigoso.</span><span class="sxs-lookup"><span data-stu-id="f1547-104">Or, a set expression may be used so frequently that repeatedly defining the set becomes burdensome.</span></span> <span data-ttu-id="f1547-105">Para facilitar el trabajo con una expresión larga, compleja o de uso habitual, las expresiones multidimensionales (MDX) permiten expresiones como un *conjunto con nombre*.</span><span class="sxs-lookup"><span data-stu-id="f1547-105">To help make working with a lengthy, complex or commonly used expression easier, Multidimensional Expressions (MDX) lets you such an expression as a *named set*.</span></span>  
  
 <span data-ttu-id="f1547-106">Esencialmente, un conjunto con nombre es una expresión de conjunto a la que se ha asignado un alias.</span><span class="sxs-lookup"><span data-stu-id="f1547-106">Basically, a named set is a set expression to which an alias has been assigned.</span></span> <span data-ttu-id="f1547-107">Un conjunto con nombre puede incorporar miembros o funciones que se pueden incorporar normalmente a un conjunto.</span><span class="sxs-lookup"><span data-stu-id="f1547-107">A named set can incorporate any members or functions that can ordinarily be incorporated into a set.</span></span> <span data-ttu-id="f1547-108">Como MDX trata el alias del conjunto con nombre como una expresión de conjunto, puede utilizar ese alias en cualquier lugar en que se acepte una expresión de conjunto.</span><span class="sxs-lookup"><span data-stu-id="f1547-108">Because MDX treats the named set alias as a set expression, you can use that alias anywhere a set expression is accepted.</span></span>  
  
 <span data-ttu-id="f1547-109">Puede definir un conjunto con nombre para que tenga uno de los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1547-109">You can define a named set to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="f1547-110">**Ámbito de consulta** Para crear un conjunto con nombre definido como parte de una consulta MDX (y, por lo tanto, con un ámbito limitado a la consulta) es necesario usar la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="f1547-110">**Query-scoped** To create a named set that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="f1547-111">Puede utilizar el conjunto con nombre en una instrucción MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="f1547-111">You can then use the named set within an MDX SELECT statement.</span></span> <span data-ttu-id="f1547-112">De esta manera, el conjunto con nombre creado con la palabra clave WITH se puede cambiar sin tener que tocar la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="f1547-112">Using this approach, the named set created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="f1547-113">Para más información sobre cómo usar la palabra clave WITH para crear conjuntos con nombre, vea [Crear conjuntos con nombre de ámbito de consulta &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f1547-113">For more information about how to use the WITH keyword to create named sets, see [Creating Query-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span></span>  
  
-   <span data-ttu-id="f1547-114">**Ámbito de sesión** Para crear un conjunto con nombre cuyo ámbito sea más amplio que el contexto de la consulta (es decir, un ámbito que represente el período de duración de la sesión MDX) es necesario usar la instrucción CREATE SET.</span><span class="sxs-lookup"><span data-stu-id="f1547-114">**Session-scoped** To create a named set whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE SET statement.</span></span> <span data-ttu-id="f1547-115">Un conjunto con nombre definido por la utilización de la instrucción CREATE SET está disponible para todas las consultas de MDX de esa sesión.</span><span class="sxs-lookup"><span data-stu-id="f1547-115">A named set defined by using the CREATE SET statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="f1547-116">La instrucción CREATE SET tiene sentido, por ejemplo, en una aplicación cliente que reutilice un conjunto de un modo coherente en varias consultas diferentes.</span><span class="sxs-lookup"><span data-stu-id="f1547-116">The CREATE SET statement makes sense, for example, in a client application that consistently reuses a set in a variety of queries.</span></span>  
  
     <span data-ttu-id="f1547-117">Para más información sobre cómo usar la instrucción CREATE SET para crear conjuntos de nombre en una sesión, vea [Crear conjuntos con nombre del ámbito de consulta &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f1547-117">For more information about how to use the CREATE SET statement to create named sets in a session, see [Creating Session-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1547-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1547-118">See Also</span></span>  
 <span data-ttu-id="f1547-119">[Instrucción SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="f1547-119">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 <span data-ttu-id="f1547-120">[CREATE SET &#40;instrucción MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span><span class="sxs-lookup"><span data-stu-id="f1547-120">[CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span></span>  
 [<span data-ttu-id="f1547-121">Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f1547-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  