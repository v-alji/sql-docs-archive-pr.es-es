---
title: Crear miembros calculados de ámbito de sesión (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8fe7a9f137d8b74eaa5bad104dbfdb471dd14588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675611"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a><span data-ttu-id="9d3de-102">Crear miembros calculados de ámbito de sesión (MDX)</span><span class="sxs-lookup"><span data-stu-id="9d3de-102">Creating Session-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="9d3de-103">Para crear un miembro calculado que esté disponible en una sesión de expresiones multidimensionales (MDX), es necesario usar la instrucción [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="9d3de-103">To create a calculated member that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span> <span data-ttu-id="9d3de-104">Un miembro calculado creado mediante la instrucción CREATE MEMBER no se eliminará hasta que se cierre la sesión MDX.</span><span class="sxs-lookup"><span data-stu-id="9d3de-104">A calculated member that is created by using the CREATE MEMBER statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="9d3de-105">Como se indica en este tema, la sintaxis de la instrucción CREATE MEMBER es muy sencilla y fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="9d3de-105">As discussed in this topic, the syntax of the CREATE MEMBER statement is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d3de-106">Para más información sobre los miembros calculados, vea [Generar miembros calculados en MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="9d3de-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="create-member-syntax"></a><span data-ttu-id="9d3de-107">Sintaxis de CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="9d3de-107">CREATE MEMBER Syntax</span></span>  
 <span data-ttu-id="9d3de-108">Utilice la siguiente sintaxis para agregar la instrucción CREATE MEMBER a la instrucción MDX:</span><span class="sxs-lookup"><span data-stu-id="9d3de-108">Use the following syntax to add the CREATE MEMBER statement to the MDX statement:</span></span>  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 <span data-ttu-id="9d3de-109">En la sintaxis de la instrucción CREATE MEMBER, el valor `fully-qualified-member-name` es el nombre completo del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="9d3de-109">In the syntax for the CREATE MEMBER statement, the `fully-qualified-member-name` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="9d3de-110">El nombre completo incluye la dimensión o el nivel al que se asocia el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="9d3de-110">The fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="9d3de-111">El valor `expression` devuelve el valor del miembro calculado después de haber evaluado el valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="9d3de-111">The `expression` value returns the value of the calculated member after the expression value has been evaluated,.</span></span>  
  
## <a name="create-member-example"></a><span data-ttu-id="9d3de-112">Ejemplo de CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="9d3de-112">CREATE MEMBER Example</span></span>  
 <span data-ttu-id="9d3de-113">En el siguiente ejemplo se utiliza la instrucción CREATE MEMBER para crear el miembro calculado `LastFourStores` .</span><span class="sxs-lookup"><span data-stu-id="9d3de-113">The following example uses the CREATE MEMBER statement to create the `LastFourStores` calculated member.</span></span> <span data-ttu-id="9d3de-114">Este miembro calculado devuelve la suma de las unidades vendidas en los cuatro últimos almacenes, y está disponible mientras dure la sesión del cubo.</span><span class="sxs-lookup"><span data-stu-id="9d3de-114">This calculated member returns the sum of units sold for the last four stores, and will be available throughout the whole session of the cube.</span></span>  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d3de-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d3de-115">See Also</span></span>  
 [<span data-ttu-id="9d3de-116">Crear miembros calculados en el ámbito de consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="9d3de-116">Creating Query-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  
