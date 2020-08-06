---
title: Especificar el contenido de un eje segmentador (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- filtering data [MDX]
ms.assetid: c56b0a70-cdec-427f-990e-425290344e7d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8620c54970ea14a2ac01c85262a372d2b3db0d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744397"
---
# <a name="specifying-the-contents-of-a-slicer-axis-mdx"></a><span data-ttu-id="657e7-102">Especificar el contenido de un eje de división en sectores (MDX)</span><span class="sxs-lookup"><span data-stu-id="657e7-102">Specifying the Contents of a Slicer Axis (MDX)</span></span>
  <span data-ttu-id="657e7-103">El eje segmentador filtra los datos devueltos por la instrucción SELECT de Expresiones multidimensionales (MDX) y restringe los datos devueltos de forma que solamente se devuelvan los datos de intersección entre los miembros especificados.</span><span class="sxs-lookup"><span data-stu-id="657e7-103">The slicer axis filters the data returned by the Multidimensional Expressions (MDX) SELECT statement, restricting the returned data so that only data intersecting with the specified members will be returned.</span></span> <span data-ttu-id="657e7-104">Puede considerarse como eje adicional no visible en una consulta.</span><span class="sxs-lookup"><span data-stu-id="657e7-104">It can be thought of as an invisible extra axis in a query.</span></span> <span data-ttu-id="657e7-105">El eje segmentador se define en la cláusula WHERE de la instrucción SELECT de MDX.</span><span class="sxs-lookup"><span data-stu-id="657e7-105">The slicer axis is defined in the WHERE clause of the SELECT statement in MDX.</span></span>  
  
## <a name="slicer-axis-syntax"></a><span data-ttu-id="657e7-106">Sintaxis del eje segmentador</span><span class="sxs-lookup"><span data-stu-id="657e7-106">Slicer Axis Syntax</span></span>  
 <span data-ttu-id="657e7-107">Para especificar explícitamente un eje segmentador, debe utilizar `<SELECT slicer axis clause>` en MDX, según se describe en la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="657e7-107">To explicitly specify a slicer axis, you  using the `<SELECT slicer axis clause>` in MDX, as described in the following syntax:</span></span>  
  
```  
<SELECT slicer axis clause> ::=  WHERE Set_Expression  
```  
  
 <span data-ttu-id="657e7-108">En la sintaxis del eje segmentador que se muestra, `Set_Expression` puede tomar una expresión de tupla, que se trata como un conjunto en cuanto a la evaluación de la cláusula, o como una expresión de conjunto.</span><span class="sxs-lookup"><span data-stu-id="657e7-108">In the slicer axis syntax shown, `Set_Expression` can take either a tuple expression, which is treated as a set for the purposes of evaluating the clause, or a set expression.</span></span> <span data-ttu-id="657e7-109">Si se especifica una expresión de conjunto, MDX intentará evaluar el conjunto, sumando las celdas de resultado en cada tupla del conjunto.</span><span class="sxs-lookup"><span data-stu-id="657e7-109">If a set expression is specified, MDX will try to evaluate the set, aggregating the result cells in every tuple along the set.</span></span> <span data-ttu-id="657e7-110">En otras palabras, MDX intentará utilizar la función [Aggregate](/sql/mdx/aggregate-mdx) en el conjunto, agregando cada medida por su función de agregación asociada.</span><span class="sxs-lookup"><span data-stu-id="657e7-110">In other words, MDX will try to use the [Aggregate](/sql/mdx/aggregate-mdx) function on the set, aggregating each measure by its associated aggregation function.</span></span> <span data-ttu-id="657e7-111">Asimismo, si la expresión de conjunto no puede expresarse como un cruce de miembros de la jerarquía de atributos, MDX trata las celdas que quedan fuera de la expresión de conjunto para el segmentador como valores nulos (NULL) para fines de evaluación.</span><span class="sxs-lookup"><span data-stu-id="657e7-111">Also, if the set expression cannot be expressed as a crossjoin of attribute hierarchy members, MDX treats cells that fall outside of the set expression for the slicer as null for evaluation purposes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="657e7-112">A diferencia de la cláusula WHERE de SQL, la cláusula WHERE de una instrucción MDX SELECT no filtra nunca directamente lo que se devuelve en el eje de filas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="657e7-112">Unlike the WHERE clause in SQL, the WHERE clause of an MDX SELECT statement never directly filters what is returned on the Rows axis of a query.</span></span> <span data-ttu-id="657e7-113">Para filtrar qué aparece en el eje de filas o columnas de una consulta, puede utilizar una variedad de funciones MDX, como FILTER, NON EMPTY y TOPCOUNT.</span><span class="sxs-lookup"><span data-stu-id="657e7-113">To filter what appears on the Rows or Columns axis of a query, you can use a variety of MDX functions, for example FILTER, NONEMPTY and TOPCOUNT.</span></span>  
  
### <a name="implicit-slicer-axis"></a><span data-ttu-id="657e7-114">Eje segmentador implícito</span><span class="sxs-lookup"><span data-stu-id="657e7-114">Implicit Slicer Axis</span></span>  
 <span data-ttu-id="657e7-115">Si un miembro de una jerarquía del cubo no está explícitamente incluido en un eje de consulta, el miembro predeterminado de esa jerarquía se incluye implícitamente en el eje segmentador.</span><span class="sxs-lookup"><span data-stu-id="657e7-115">If a member from a hierarchy within the cube is not explicitly included in a query axis, the default member from that hierarchy is implicitly included in the slicer axis.</span></span> <span data-ttu-id="657e7-116">Para más información sobre los miembros predeterminados, vea [Definir un miembro predeterminado](../attribute-properties-define-a-default-member.md).</span><span class="sxs-lookup"><span data-stu-id="657e7-116">For more information about default members, see [Define a Default Member](../attribute-properties-define-a-default-member.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="657e7-117">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="657e7-117">Examples</span></span>  
 <span data-ttu-id="657e7-118">La consulta siguiente no incluye la cláusula WHERE y devuelve el valor de la medida Internet Sales Amount para todos los años naturales:</span><span class="sxs-lookup"><span data-stu-id="657e7-118">The following query does not include a WHERE clause, and returns the value of the Internet Sales Amount measure for all Calendar Years:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="657e7-119">Agregar una cláusula WHERE, como sigue:</span><span class="sxs-lookup"><span data-stu-id="657e7-119">Adding a WHERE clause, as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States])  
  
```  
  
 <span data-ttu-id="657e7-120">no cambia lo que se devuelve en las filas o columnas de la consulta; cambia los valores devueltos para cada celda.</span><span class="sxs-lookup"><span data-stu-id="657e7-120">does not change what is returned on Rows or Columns in the query; it changes the values returned for each cell.</span></span> <span data-ttu-id="657e7-121">En este ejemplo, se crean sectores de la consulta para que devuelva el valor de Internet Sales Amount para todos los años naturales, pero solo para los clientes que viven en los Estados Unidos. Varios miembros de diferentes jerarquías pueden agregarse a la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="657e7-121">In this example, the query is sliced so that it returns the value of Internet Sales Amount for all Calendar Years but only for Customers who live in the United States.Multiple members from different hierarchies can be added to the WHERE clause.</span></span> <span data-ttu-id="657e7-122">La consulta siguiente muestra el valor de Internet Sales Amount para todos los años naturales para los clientes que viven en Estados Unidos y que compraron productos de la categoría bicicletas:</span><span class="sxs-lookup"><span data-stu-id="657e7-122">The following query shows the value of Internet Sales Amount for all Calendar Years for Customers who live in the United States and who bought Products in the Category Bikes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States], [Product].[Category].&[1])  
```  
  
 <span data-ttu-id="657e7-123">Si desea utilizar varios miembros de la misma jerarquía, debe incluir un conjunto en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="657e7-123">If you want to use multiple members from the same hierarchy, you need to include a set in the WHERE clause.</span></span> <span data-ttu-id="657e7-124">Por ejemplo, la siguiente consulta muestra el valor de Internet Sales Amount para todos los años naturales para los clientes que compraron productos de la categoría bicicletas y viven en Estados Unidos o Reino Unido:</span><span class="sxs-lookup"><span data-stu-id="657e7-124">For example, the following query shows the value of Internet Sales Amount for all Calendar Years for Customers who bought Products in the Category Bikes and live in either the United States or the United Kingdom:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE(  
{[Customer].[Customer Geography].[Country].&[United States]  
, [Customer].[Customer Geography].[Country].&[United Kingdom]}  
, [Product].[Category].&[1])  
  
```  
  
 <span data-ttu-id="657e7-125">Como se mencionó anteriormente, con un conjunto en la cláusula WHERE agregará implícitamente los valores de todos los miembros del conjunto.</span><span class="sxs-lookup"><span data-stu-id="657e7-125">As mentioned above, using a set in the WHERE clause will implicitly aggregate values for all members in the set.</span></span> <span data-ttu-id="657e7-126">En este caso, la consulta muestra los valores agregados para Estados Unidos y Reino Unido en cada celda.</span><span class="sxs-lookup"><span data-stu-id="657e7-126">In this case, the query shows aggregated values for the United States and the United Kingdom in each cell.</span></span>  
  
  
