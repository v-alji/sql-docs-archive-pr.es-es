---
title: Crear miembros calculados de ámbito de consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped calculated members [MDX]
ms.assetid: c4507149-e67b-4e5d-9192-cc911acd9adc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c0b3e7184f3cc6abd189344bbce1b6e1f948ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671733"
---
# <a name="creating-query-scoped-calculated-members-mdx"></a><span data-ttu-id="5c587-102">Crear miembros calculados en el ámbito de consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="5c587-102">Creating Query-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="5c587-103">Si un miembro calculado solamente es necesario para una consulta de Expresiones multidimensionales (MDX) única, puede definir ese miembro calculado mediante la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="5c587-103">If a calculated member is only required for a single Multidimensional Expressions (MDX) query, you can define that calculated member by using the WITH keyword.</span></span> <span data-ttu-id="5c587-104">Un miembro calculado que se ha creado con la palabra clave WITH deja de existir cuando cesa la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5c587-104">A calculated member that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="5c587-105">Como se trata en este tema, la sintaxis de la palabra clave WITH es bastante flexible, incluso permitiendo que un miembro calculado se base en otro miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="5c587-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even allowing a calculated member to be based on another calculated member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c587-106">Para más información sobre los miembros calculados, vea [Generar miembros calculados en MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="5c587-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="5c587-107">Sintaxis de la palabra clave WITH</span><span class="sxs-lookup"><span data-stu-id="5c587-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="5c587-108">La siguiente sintaxis se utiliza para agregar la palabra clave WITH a una instrucción MDX SELECT:</span><span class="sxs-lookup"><span data-stu-id="5c587-108">Use the following syntax to add the WITH keyword to an MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ] SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]FROM <SELECT subcube clause> [ <SELECT slicer axis clause> ][ <SELECT cell property list clause> ]  
<SELECT WITH clause> ::=  
   ( [ CALCULATED ] MEMBER <CREATE MEMBER body clause>) | <CREATE MEMBER body clause> ::= Member_Identifier AS 'MDX_Expression'  
   [ <CREATE MEMBER property clause> [ , <CREATE MEMBER property clause> ... ] ]  
<CREATE MEMBER property clause> ::=  
   ( MemberProperty_Identifier = Scalar_Expression )  
  
```  
  
 <span data-ttu-id="5c587-109">En la sintaxis de la palabra clave WITH, el valor `Member_Identifier` es el nombre completo del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="5c587-109">In the syntax for the WITH keyword, the `Member_Identifier` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="5c587-110">El nombre completo incluye la dimensión o el nivel al que se asocia el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="5c587-110">This fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="5c587-111">El valor `MDX_Expression` devuelve el valor del miembro calculado una vez que el valor de la expresión se ha evaluado.</span><span class="sxs-lookup"><span data-stu-id="5c587-111">The `MDX_Expression` value returns the value of the calculated member after the expression value has been evaluated.</span></span> <span data-ttu-id="5c587-112">Los valores de las propiedades de celda intrínsecas para un miembro calculado se pueden especificar también proporcionando el nombre de la propiedad de celda en el valor `MemberProperty_Identifier` y el valor de la propiedad de celda en el valor `Scalar_Expression` .</span><span class="sxs-lookup"><span data-stu-id="5c587-112">The values of intrinsic cell properties for a calculated member can be optionally specified by supplying the name of the cell property in the `MemberProperty_Identifier` value and the value of the cell property in the `Scalar_Expression` value.</span></span>  
  
## <a name="with-keyword-examples"></a><span data-ttu-id="5c587-113">Ejemplos de la palabra clave WITH</span><span class="sxs-lookup"><span data-stu-id="5c587-113">WITH Keyword Examples</span></span>  
 <span data-ttu-id="5c587-114">La siguiente consulta MDX define un miembro calculado, `[Measures].[Special Discount]`y calcula un descuento especial basado en la cantidad de descuento original.</span><span class="sxs-lookup"><span data-stu-id="5c587-114">The following MDX query defines a calculated member, `[Measures].[Special Discount]`, calculating a special discount based on the original discount amount.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Amount] * 1.5  
SELECT   
   [Measures].[Special Discount] on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 <span data-ttu-id="5c587-115">También puede crear miembros calculados en cualquier punto de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="5c587-115">You can also create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="5c587-116">Por ejemplo, la siguiente consulta MDX define el miembro calculado `[BigSeller]` para un cubo Sales hipotético.</span><span class="sxs-lookup"><span data-stu-id="5c587-116">For example, the following MDX query defines the `[BigSeller]` calculated member for a hypothetical Sales cube.</span></span> <span data-ttu-id="5c587-117">Este miembro calculado determina si un establecimiento especificado tiene al menos 100,00 en ventas de unidades de cerveza y vino.</span><span class="sxs-lookup"><span data-stu-id="5c587-117">This calculated member determines whether a specified store has at least 100.00 in unit sales for beer and wine.</span></span> <span data-ttu-id="5c587-118">Sin embargo, la consulta crea el miembro calculado `[BigSeller]` no como un miembro secundario de la dimensión `[Product]` , sino más bien como un miembro secundario del miembro `[Beer and Wine]` .</span><span class="sxs-lookup"><span data-stu-id="5c587-118">However, the query creates the `[BigSeller]` calculated member not as a child member of the `[Product]` dimension, but instead as a child member of the `[Beer and Wine]` member.</span></span>  
  
```  
WITH   
   MEMBER [Product].[Beer and Wine].[BigSeller] AS  
  IIf([Product].[Beer and Wine] > 100, "Yes","No")  
SELECT  
   {[Product].[BigSeller]} ON COLUMNS,  
   Store.[Store Name].Members ON ROWS  
FROM Sales  
  
```  
  
 <span data-ttu-id="5c587-119">Los miembros calculados no tienen que depender solo de los miembros existentes en un cubo.</span><span class="sxs-lookup"><span data-stu-id="5c587-119">Calculated members do not have to depend only on existing members in a cube.</span></span> <span data-ttu-id="5c587-120">El miembro calculado también puede basarse en otro miembro calculado definido en la misma expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="5c587-120">Calculated member can also be based on other calculated members defined in the same MDX expression.</span></span> <span data-ttu-id="5c587-121">Por ejemplo, la siguiente consulta MDX utiliza el valor creado en el primer miembro calculado, `[Measures].[Special Discount]`, para generar el valor del segundo miembro calculado, `[Measures].[Special Discounted Amount]`.</span><span class="sxs-lookup"><span data-stu-id="5c587-121">For example, the following MDX query uses the value created in the first calculated member, `[Measures].[Special Discount]`, to generate the value of the second calculated member, `[Measures].[Special Discounted Amount]`.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Percentage] * 1.5,   
   FORMAT_STRING = 'Percent'  
  
   MEMBER [Measures].[Special Discounted Amount] AS  
   [Measures].[Reseller Average Unit Price] * [Measures].[Special Discount],   
   FORMAT_STRING = 'Currency'  
  
SELECT   
   {[Measures].[Special Discount], [Measures].[Special Discounted Amount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c587-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c587-122">See Also</span></span>  
 <span data-ttu-id="5c587-123">[Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="5c587-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 <span data-ttu-id="5c587-124">[Instrucción SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="5c587-124">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="5c587-125">Crear miembros calculados de ámbito de sesión &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="5c587-125">Creating Session-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-session-scoped-calculated-members.md)  
  
  
