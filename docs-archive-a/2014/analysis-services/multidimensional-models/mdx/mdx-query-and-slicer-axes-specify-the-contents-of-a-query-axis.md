---
title: Especificar el contenido de un eje de consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cellsets [MDX]
- query axis [MDX]
ms.assetid: c745ade0-738e-4a98-a3f0-3eabfd3eeba2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 28fd867b8f8caaf74e4dd704753c354368da2e89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747203"
---
# <a name="specifying-the-contents-of-a-query-axis-mdx"></a><span data-ttu-id="b2fc5-102">Especificar el contenido de un eje de consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="b2fc5-102">Specifying the Contents of a Query Axis (MDX)</span></span>
  <span data-ttu-id="b2fc5-103">Los ejes de consulta especifican los límites de un conjunto de celdas devuelto por una instrucción SELECT de Expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="b2fc5-103">Query axes specify the edges of a cellset returned by a Multidimensional Expressions (MDX) SELECT statement.</span></span> <span data-ttu-id="b2fc5-104">Al especificar los límites de un conjunto de celdas puede restringir los datos devueltos que son visibles para el cliente.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-104">Specifying the edges of a cellset lets you restrict the returned data that is visible to the client.</span></span>  
  
 <span data-ttu-id="b2fc5-105">Para especificar ejes de consulta, utilice `<SELECT query axis clause>` para asignar un conjunto a un eje de consulta determinado.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-105">To specify query axes, you use the `<SELECT query axis clause>` to assign a set to a particular query axis.</span></span> <span data-ttu-id="b2fc5-106">Cada valor `<SELECT query axis clause>` define un eje de consulta.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-106">Each `<SELECT query axis clause>` value defines one query axis.</span></span> <span data-ttu-id="b2fc5-107">El número de ejes de un conjunto de datos es igual al número de valores `<SELECT query axis clause>` de la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-107">The number of axes in the dataset is equal to the number of `<SELECT query axis clause>` values in the SELECT statement.</span></span>  
  
## <a name="query-axis-syntax"></a><span data-ttu-id="b2fc5-108">Sintaxis del eje de consulta</span><span class="sxs-lookup"><span data-stu-id="b2fc5-108">Query Axis Syntax</span></span>  
 <span data-ttu-id="b2fc5-109">A continuación se muestra la sintaxis para `<SELECT query axis clause>`:</span><span class="sxs-lookup"><span data-stu-id="b2fc5-109">The following syntax shows the syntax for the `<SELECT query axis clause>`:</span></span>  
  
```  
  
<SELECT query axis clause> ::=  
   [ NON EMPTY ] Set_Expression [ <SELECT dimension property list clause> ] [<HAVING clause>]  
   ON {  
      Integer_Expression |   
      AXIS( Integer_Expression ) |   
      {COLUMNS | ROWS | PAGES | SECTIONS | CHAPTERS}     
      }  
  
```  
  
 <span data-ttu-id="b2fc5-110">Cada eje de consulta tiene un número: cero (0) para el eje X, 1 para el eje Y, 2 para el eje Z, etc.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-110">Each query axis has a number: zero (0) for the x-axis, 1 for the y-axis, 2 for the z-axis, and so on.</span></span> <span data-ttu-id="b2fc5-111">En la sintaxis de `<SELECT query axis clause>`, el valor `Integer_Expression` especifica el número de eje.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-111">In the syntax for the `<SELECT query axis clause>`, the `Integer_Expression` value specifies the axis number.</span></span> <span data-ttu-id="b2fc5-112">Una consulta de MDX puede admitir hasta 128 ejes especificados, pero muy pocas consultas MDX utilizarán más de cinco ejes.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-112">An MDX query can support up to 128 specified axes, but very few MDX queries will use more than 5 axes.</span></span> <span data-ttu-id="b2fc5-113">En los primeros cinco ejes, pueden utilizarse los alias COLUMNS, ROWS, PAGES, SECTIONS y CHAPTERS en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-113">For the first 5 axes, the aliases COLUMNS, ROWS, PAGES, SECTIONS, and CHAPTERS can instead be used.</span></span>  
  
 <span data-ttu-id="b2fc5-114">Una consulta de MDX no puede ignorar los ejes de consulta.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-114">An MDX query cannot skip query axes.</span></span> <span data-ttu-id="b2fc5-115">Es decir, una consulta que incluye uno o más ejes de consulta no debe excluir los ejes con números más bajos o intermedios.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-115">That is, a query that includes one or more query axes must not exclude lower-numbered or intermediate axes.</span></span> <span data-ttu-id="b2fc5-116">Por ejemplo, una consulta no puede tener un eje ROWS sin un eje COLUMNS, o los ejes COLUMNS y PAGES sin un eje ROWS.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-116">For example, a query cannot have a ROWS axis without a COLUMNS axis, or have COLUMNS and PAGES axes without a ROWS axis.</span></span>  
  
 <span data-ttu-id="b2fc5-117">Sin embargo, puede especificar una cláusula SELECT sin ejes (es decir, una cláusula SELECT vacía).</span><span class="sxs-lookup"><span data-stu-id="b2fc5-117">However, you can specify a SELECT clause without any axes (that is, an empty SELECT clause).</span></span> <span data-ttu-id="b2fc5-118">En este caso, todas las dimensiones son dimensiones de segmentador y la consulta de MDX selecciona una celda.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-118">In this case, all dimensions are slicer dimensions, and the MDX query selects one cell.</span></span>  
  
 <span data-ttu-id="b2fc5-119">En la sintaxis del eje de consulta mostrado más arriba, cada valor `Set_Expression` especifica el conjunto que define el contenido del eje de consulta.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-119">In the query axis syntax previously shown, each `Set_Expression` value specifies the set that defines the contents of the query axis.</span></span> <span data-ttu-id="b2fc5-120">Para obtener más información sobre los conjuntos, vea [Trabajar con miembros, tuplas y conjuntos &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="b2fc5-120">For more information about sets, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b2fc5-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b2fc5-121">Examples</span></span>  
 <span data-ttu-id="b2fc5-122">La instrucción SELECT simple siguiente devuelve la medida Internet Sales Amount en el eje de columnas y utiliza funciones MDX MEMBERS para devolver todos los miembros de la jerarquía Calendar de la dimensión Date en el eje de filas:</span><span class="sxs-lookup"><span data-stu-id="b2fc5-122">The following simple SELECT statement returns the measure Internet Sales Amount on the Columns axis, and uses the MDX MEMBERS function to return all the members from the Calendar hierarchy on the Date dimension on the Rows axis:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="b2fc5-123">Las dos consultas de siguientes devuelven exactamente los mismos resultados pero muestran el uso de números de eje en lugar de alias:</span><span class="sxs-lookup"><span data-stu-id="b2fc5-123">The two following queries return exactly the same results but demonstrate the use of axis numbers rather than aliases:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON 0,  
{[Date].[Calendar].MEMBERS} ON 1  
FROM [Adventure Works]  
  
SELECT {[Measures].[Internet Sales Amount]} ON AXIS(0),  
{[Date].[Calendar].MEMBERS} ON AXIS(1)  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="b2fc5-124">La palabra clave NON EMPTY, utilizada antes de la definición específica, es una forma sencilla de quitar todas las tuplas vacías de un eje.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-124">The NON EMPTY keyword, used before the set definition, is an easy way to remove all empty tuples from an axis.</span></span> <span data-ttu-id="b2fc5-125">Por ejemplo, en los ejemplos que hemos visto hasta ahora no hay datos en el cubo de agosto de 2004 en adelante.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-125">For example, in the examples we've seen so far there is no data in the cube from August 2004 onwards.</span></span> <span data-ttu-id="b2fc5-126">Para quitar todas las filas del conjunto que no tienen ningún dato en ninguna columna, agregue simplemente NON EMPTY antes del conjunto en la definición del eje de filas como sigue:</span><span class="sxs-lookup"><span data-stu-id="b2fc5-126">To remove all rows from the cellset that have no data in any column, simply add NON EMPTY before the set on the Rows axis definition as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="b2fc5-127">NON EMPTY se puede utilizar en todos los ejes de una consulta.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-127">NON EMPTY can be used on all axes in a query.</span></span> <span data-ttu-id="b2fc5-128">Compare los resultados de las dos consultas siguientes; la primera no utiliza NON EMPTY y la segunda lo usa en ambos ejes:</span><span class="sxs-lookup"><span data-stu-id="b2fc5-128">Compare the results of the following two queries, the first of which does not use NON EMPTY and the second of which does on both axes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
SELECT NON EMPTY {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
```  
  
 <span data-ttu-id="b2fc5-129">La cláusula HAVING se puede usar para filtrar el contenido de un eje basándose en criterios concretos; es menos flexible que otros métodos que pueden lograr los mismos resultados, como la función FILTER, pero es más sencillo utilizar.</span><span class="sxs-lookup"><span data-stu-id="b2fc5-129">The HAVING clause can be used to filter the contents of an axis based on a specific criteria; it is less flexible than other methods that can achieve the same results, such as the FILTER function, but it is simpler to use.</span></span> <span data-ttu-id="b2fc5-130">A continuación se muestra un ejemplo que solo devuelve las fechas donde Internet Sales Amount es mayor que $15.000:</span><span class="sxs-lookup"><span data-stu-id="b2fc5-130">Here is an example that returns only those dates where Internet Sales Amount is greater than $15,000:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Date].MEMBERS}   
HAVING [Measures].[Internet Sales Amount]>15000  
ON ROWS  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2fc5-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2fc5-131">See Also</span></span>  
 [<span data-ttu-id="b2fc5-132">Especificar el contenido de un eje de división en sectores &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b2fc5-132">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
