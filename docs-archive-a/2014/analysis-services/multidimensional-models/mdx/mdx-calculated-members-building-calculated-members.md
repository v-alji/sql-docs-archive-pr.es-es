---
title: Generar miembros calculados en MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], calculated members
- calculated members [MDX]
- Multidimensional Expressions [Analysis Services], calculated members
- queries [MDX], calculated members
ms.assetid: 9322e8b8-43e1-4e02-a7d1-e41a586a5bb8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30dc6562ec394065cf2f177608d4e5679cbd7df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671729"
---
# <a name="building-calculated-members-in-mdx-mdx"></a><span data-ttu-id="eacf6-102">Generar miembros calculados en MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="eacf6-102">Building Calculated Members in MDX (MDX)</span></span>
  <span data-ttu-id="eacf6-103">En las Expresiones multidimensionales (MDX), un miembro calculado es un miembro que se resuelve calculando una expresión MDX para devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="eacf6-103">In Multidimensional Expressions (MDX), a calculated member is a member that is resolved by calculating an MDX expression to return a value.</span></span> <span data-ttu-id="eacf6-104">Esta definición tan genérica tiene un alcance notable.</span><span class="sxs-lookup"><span data-stu-id="eacf6-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="eacf6-105">La capacidad de construir y utilizar miembros calculados en una consulta MDX proporciona una gran solución para manipular datos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="eacf6-105">The ability to construct and use calculated members in an MDX query provides a great deal of manipulation capability for multidimensional data.</span></span>  
  
 <span data-ttu-id="eacf6-106">Puede crear miembros calculados en cualquier punto de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="eacf6-106">You can create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="eacf6-107">También puede crear miembros calculados que no dependan únicamente de los miembros existentes en un cubo, sino también de otros miembros calculados definidos en la misma expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="eacf6-107">You can also create calculated members that depend not only on existing members in a cube, but also on other calculated members defined in the same MDX expression.</span></span>  
  
 <span data-ttu-id="eacf6-108">Puede definir un miembro calculado para que tenga uno de los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="eacf6-108">You can define a calculated member to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="eacf6-109">**Ámbito de consulta** Para crear un miembro calculado definido como parte de una consulta MDX, y en consecuencia con un ámbito limitado a la consulta, debe usar la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="eacf6-109">**Query-scoped** To create a calculated member that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="eacf6-110">Posteriormente puede utilizar el miembro calculado en una instrucción MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="eacf6-110">You can then use the calculated member within an MDX SELECT statement.</span></span> <span data-ttu-id="eacf6-111">De esta manera, el miembro calculado creado con la palabra clave WITH se puede cambiar sin tener que tocar la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="eacf6-111">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="eacf6-112">Para obtener más información sobre el uso de la palabra clave WITH para crear miembros calculados, vea [Crear miembros calculados en el ámbito de consulta &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="eacf6-112">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span></span>  
  
-   <span data-ttu-id="eacf6-113">**Ámbito de sesión** Para crear un miembro calculado cuyo ámbito sea más amplio que el contexto de la consulta, es decir, un ámbito que sea la duración de la sesión MDX, debe usar la instrucción CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="eacf6-113">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE MEMBER statement.</span></span> <span data-ttu-id="eacf6-114">Un miembro calculado definido por la utilización de la instrucción CREATE SET está disponible para todas las consultas de MDX de esa sesión.</span><span class="sxs-lookup"><span data-stu-id="eacf6-114">A calculated member defined by using the CREATE MEMBER statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="eacf6-115">La instrucción CREATE MEMBER tiene sentido, por ejemplo, en una aplicación cliente que reutilice el mismo conjunto de un modo coherente en varias consultas diferentes.</span><span class="sxs-lookup"><span data-stu-id="eacf6-115">The CREATE MEMBER statement makes sense, for example, in a client application that consistently reuses the same set in a variety of queries.</span></span>  
  
     <span data-ttu-id="eacf6-116">Para obtener más información sobre el uso de la instrucción CREATE MEMBER para crear miembros calculados en una sesión, vea [Crear miembros calculados de ámbito de sesión &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="eacf6-116">For more information about how to use the CREATE MEMBER statement to create calculated members in a session, see [Creating Session-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacf6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eacf6-117">See Also</span></span>  
 <span data-ttu-id="eacf6-118">[Instrucción CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="eacf6-118">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="eacf6-119">[Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="eacf6-119">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="eacf6-120">SELECT &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="eacf6-120">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
