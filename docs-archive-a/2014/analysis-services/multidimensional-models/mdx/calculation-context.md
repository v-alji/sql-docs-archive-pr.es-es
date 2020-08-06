---
title: Contexto de cálculo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aec8aa98-b77d-4f8f-9684-2618b1d8e970
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6d14df51c6ec37fb96520af7acf207227ae4ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746564"
---
# <a name="calculation-context"></a><span data-ttu-id="a7067-102">Contexto de cálculo</span><span class="sxs-lookup"><span data-stu-id="a7067-102">Calculation Context</span></span>
  <span data-ttu-id="a7067-103">El contexto de cálculo es el subespacio conocido del cubo donde se evalúa una expresión y todas las coordenadas se conocen explícitamente o se pueden derivar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="a7067-103">The calculation context is the known subspace of the cube where an expression is evaluated and all coordinates are either explicitly known or can be derived from the expression.</span></span>  
  
## <a name="determining-the-calculation-context"></a><span data-ttu-id="a7067-104">Determinar el contexto del cálculo</span><span class="sxs-lookup"><span data-stu-id="a7067-104">Determining the calculation context</span></span>  
 <span data-ttu-id="a7067-105">Cada conjunto, miembro, tupla o función numérica se ejecuta en el contexto de toda la expresión o instrucción MDX.</span><span class="sxs-lookup"><span data-stu-id="a7067-105">Every set, member, tuple, or numeric function executes in the context of the entire MDX expression or statement.</span></span> <span data-ttu-id="a7067-106">Cuando se pasa un argumento, como una tupla, a una función, solo se proporcionan explícitamente algunas coordenadas del espacio de cubo.</span><span class="sxs-lookup"><span data-stu-id="a7067-106">When an argument, such as a tuple, is passed to a function, only some of the coordinates in the cube space are explicitly provided.</span></span> <span data-ttu-id="a7067-107">Las otras coordenadas se obtienen según el contexto de cálculo actual.</span><span class="sxs-lookup"><span data-stu-id="a7067-107">The other coordinates are obtained based on the current calculation context.</span></span>  
  
 <span data-ttu-id="a7067-108">El contexto de cálculo de las coordenadas de celda y los miembros de atributo que no se han especificado se determina en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="a7067-108">The calculation context for unspecified cell coordinates and attribute members is determined in the following order:</span></span>  
  
1.  <span data-ttu-id="a7067-109">La cláusula FROM (si corresponde): esta cláusula puede especificar un cubo entero o un subcubo en forma de una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="a7067-109">The FROM clause (if applicable) - this clause can either specify an entire cube or can specify a subcube in the form of a SELECT statement.</span></span>  
  
2.  <span data-ttu-id="a7067-110">La cláusula WHERE (si corresponde): esta cláusula, que también se conoce como el *eje segmentador*, en la que se especifica un conjunto, tupla o miembro que limita el número de miembros devuelto en el eje de columna y de fila por una consulta.</span><span class="sxs-lookup"><span data-stu-id="a7067-110">The WHERE clause (if applicable) - this clause, which is also known as the *slicer axis*, on which you specify a set, tuple, or member that restricts the members returned on the column and row axis by a query.</span></span> <span data-ttu-id="a7067-111">Conceptualmente, el miembro predeterminado de cada jerarquía de atributo que no se especifica explícitamente en el eje de columna o de fila es parte del eje segmentador.</span><span class="sxs-lookup"><span data-stu-id="a7067-111">Conceptually, the default member of every attribute hierarchy that is not explicitly specified on column or row axis is part of the slicer axis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7067-112">Cuando se especifican las coordenadas de celda de un atributo en particular en el eje segmentador y en otro eje, las coordenadas especificadas en la función pueden tener prioridad al determinar los miembros del conjunto en el eje.</span><span class="sxs-lookup"><span data-stu-id="a7067-112">When cell coordinates for a particular attribute are specified on both the slicer axis and on another axis, the coordinates specified in the function may take precedence in determining the members of the set on the axis.</span></span> <span data-ttu-id="a7067-113">Las funciones [Filter (MDX)](/sql/mdx/filter-mdx) y [Order (MDX)](/sql/mdx/order-mdx) son ejemplos de esas funciones. Se puede filtrar u ordenar un resultado por miembros de atributo que se excluyen del contexto de cálculo con la cláusula WHERE o mediante una instrucción SELECT de la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="a7067-113">The [Filter (MDX)](/sql/mdx/filter-mdx) and [Order (MDX)](/sql/mdx/order-mdx) functions are examples of such functions - you can filter or order a result by attribute members that are excluded from the calculation context by the WHERE clause, or by a SELECT statement in the FROM clause.</span></span>  
  
3.  <span data-ttu-id="a7067-114">Los conjuntos con nombre y los miembros calculados definidos en la consulta o expresión.</span><span class="sxs-lookup"><span data-stu-id="a7067-114">The named sets and calculated members defined in the query or expression.</span></span>  
  
4.  <span data-ttu-id="a7067-115">Las tuplas y conjuntos especificados en los ejes de columna y fila, mediante el miembro predeterminado de los atributos que no aparecen en el eje de fila, de columna o segmentador.</span><span class="sxs-lookup"><span data-stu-id="a7067-115">The tuples and sets specified on the row and column axes, utilizing the default member for attributes that do not appear on the row, column, or slicer axis.</span></span>  
  
5.  <span data-ttu-id="a7067-116">Las celdas de cubo o subcubo en cada eje, lo que elimina las tuplas vacías del eje y aplica la cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="a7067-116">The cube or subcube cells on each axis, eliminating empty tuples on the axis and applying the HAVING clause.</span></span>  
  
6.  <span data-ttu-id="a7067-117">Para más información, vea [Establecer el contexto de cubo en una consulta &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a7067-117">For more information, see [Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span></span>  
  
 <span data-ttu-id="a7067-118">En la siguiente consulta, el contexto de cálculo del eje de fila está limitado por el miembro de atributo Country y el miembro de atributo Calendar Year especificados en la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="a7067-118">In the following query, the calculation context for the row axis is restricted by the Country attribute member and the Calendar Year attribute member that are specified in the WHERE clause.</span></span>  
  
```  
SELECT Customer.City.City.Members ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France, [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="a7067-119">Sin embargo, si modifica esta consulta al especificar la función `FILTER` en el eje de fila y utiliza un miembro de jerarquía de atributo Calendar Year en la función `FILTER`, entonces se puede modificar el miembro de atributo de la jerarquía de atributo Calendar Year que se utiliza para proporcionar el contexto de cálculo para los miembros del conjunto en el eje de columna.</span><span class="sxs-lookup"><span data-stu-id="a7067-119">However, if you modify this query by specifying the `FILTER` function on the row axis, and utilize a Calendar Year attribute hierarchy member in the `FILTER` function, then the attribute member from the Calendar Year attribute hierarchy that is used to provide the calculation context for the members of the set on the column axis can be modified.</span></span>  
  
```  
SELECT FILTER  
   (  
      Customer.City.City.Members,   
         ([Date].[Calendar].[Calendar Year].[CY 2003],  
            Measures.[Internet Order Quantity]) > 75   
   ) ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France,  
   [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="a7067-120">En la consulta anterior, el contexto de cálculo para las celdas de las tuplas que aparecen en el eje de columna está filtrado por el miembro CY 2003 de la jerarquía de atributo Calendar Year, a pesar de que el contexto de cálculo nominal para la jerarquía de atributo Calendar Year es CY 2004.</span><span class="sxs-lookup"><span data-stu-id="a7067-120">In the previous query, the calculation context for the cells in the tuples that appear on the column axis is filtered by the CY 2003 member of the Calendar Year attribute hierarchy, even though the nominal calculation context for the Calendar Year attribute hierarchy is CY 2004.</span></span> <span data-ttu-id="a7067-121">Además, está filtrado por la medida Internet Order Quantity.</span><span class="sxs-lookup"><span data-stu-id="a7067-121">Furthermore, it is filtered by the Internet Order Quantity measure.</span></span> <span data-ttu-id="a7067-122">Sin embargo, una vez que se establecen los miembros del conjunto en el eje de columna, el contexto de cálculo de los valores para los miembros que aparecen en el eje se determina nuevamente mediante la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="a7067-122">However, once the members of the set on the column axis is set, the calculation context for the values for the members that appear on the axis is again determined by the WHERE clause.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7067-123">Para aumentar el rendimiento de la consulta, debe eliminar los miembros y las tuplas lo más pronto posible en el proceso de resolución.</span><span class="sxs-lookup"><span data-stu-id="a7067-123">To increase query performance, you should eliminate members and tuples as early in the resolution process as possible.</span></span> <span data-ttu-id="a7067-124">De esta manera, los cálculos de tiempo de consulta complejos en el conjunto final de miembros operan en la menor cantidad de celdas posible.</span><span class="sxs-lookup"><span data-stu-id="a7067-124">In this manner, complex query time calculations on the final set of members operate on the fewest cells possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7067-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7067-125">See Also</span></span>  
 <span data-ttu-id="a7067-126">[Establecer el contexto de cubo en una consulta &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="a7067-126">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 <span data-ttu-id="a7067-127">[Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a7067-127">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="a7067-128">Conceptos clave de MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a7067-128">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)  
  
  
