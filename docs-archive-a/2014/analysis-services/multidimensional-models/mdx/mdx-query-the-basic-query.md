---
title: Consulta MDX básica (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], SELECT statement
- queries [MDX], about queries
- cellsets [MDX]
- SELECT statement [MDX]
- cubes [Analysis Services], SELECT statement
ms.assetid: 4fa5a95a-fec9-4584-875c-dbf030c53e82
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6b1a70753abe8e477bd1e522a37f4513cc12a52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675608"
---
# <a name="the-basic-mdx-query-mdx"></a><span data-ttu-id="4e223-102">Consulta de MDX básica (MDX)</span><span class="sxs-lookup"><span data-stu-id="4e223-102">The Basic MDX Query (MDX)</span></span>
  <span data-ttu-id="4e223-103">La consulta de expresiones multidimensionales (MDX) básica es la instrucción SELECT: la consulta utilizada con más frecuencia en MDX.</span><span class="sxs-lookup"><span data-stu-id="4e223-103">The basic Multidimensional Expressions (MDX) query is the SELECT statement-the most frequently used query in MDX.</span></span> <span data-ttu-id="4e223-104">Si comprende cómo una instrucción MDX SELECT debe especificar un conjunto de resultados, en qué consiste la sintaxis de la instrucción SELECT y cómo crear una consulta simple mediante la instrucción SELECT, tendrá un conocimiento sólido de cómo utilizar MDX para realizar consultas de datos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="4e223-104">By understanding how an MDX SELECT statement must specify a result set, what the syntax of the SELECT statement is, and how to create a simple query using the SELECT statement, you will have a solid understanding of how to use MDX to query multidimensional data.</span></span>  
  
## <a name="specifying-a-result-set"></a><span data-ttu-id="4e223-105">Especificar un conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="4e223-105">Specifying a Result Set</span></span>  
 <span data-ttu-id="4e223-106">En MDX, la instrucción SELECT especifica un conjunto de resultados que contiene un subconjunto de datos multidimensionales que se han devuelto desde un cubo.</span><span class="sxs-lookup"><span data-stu-id="4e223-106">In MDX, the SELECT statement specifies a result set that contains a subset of multidimensional data that has been returned from a cube.</span></span> <span data-ttu-id="4e223-107">Para especificar un conjunto de resultados, una consulta MDX debe contener la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4e223-107">To specify a result set, an MDX query must contain the following information:</span></span>  
  
-   <span data-ttu-id="4e223-108">El número de ejes que desea que el conjunto de resultados contenga.</span><span class="sxs-lookup"><span data-stu-id="4e223-108">The number of axes that you want the result set to contain.</span></span> <span data-ttu-id="4e223-109">Puede especificar hasta 128 ejes en una consulta de MDX.</span><span class="sxs-lookup"><span data-stu-id="4e223-109">You can specify up to 128 axes in an MDX query.</span></span>  
  
-   <span data-ttu-id="4e223-110">El conjunto de miembros o tuplas que se incluyen en cada eje de la consulta de MDX.</span><span class="sxs-lookup"><span data-stu-id="4e223-110">The set of members or tuples to include on each axis of the MDX query.</span></span>  
  
-   <span data-ttu-id="4e223-111">El nombre del cubo que define el contexto de la consulta de MDX.</span><span class="sxs-lookup"><span data-stu-id="4e223-111">The name of the cube that sets the context of the MDX query.</span></span>  
  
-   <span data-ttu-id="4e223-112">El conjunto de miembros o tuplas que se incluyen en el eje segmentador.</span><span class="sxs-lookup"><span data-stu-id="4e223-112">The set of members or tuples to include on the slicer axis.</span></span> <span data-ttu-id="4e223-113">Para obtener más información sobre los ejes de consulta y segmentador, vea [Restringir la consulta con ejes de consulta y segmentador &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span><span class="sxs-lookup"><span data-stu-id="4e223-113">For more information about slicer and query axes, see[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span></span>  
  
 <span data-ttu-id="4e223-114">Para identificar los ejes de consulta, el cubo que se consultará y el eje segmentador, la instrucción MDX SELECT utiliza las cláusulas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e223-114">To identify the query axes, the cube that will be queried, and the slicer axis, the MDX SELECT statement uses the following clauses:</span></span>  
  
-   <span data-ttu-id="4e223-115">Una cláusula SELECT que determina los ejes de consulta de una instrucción MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="4e223-115">A SELECT clause that determines the query axes of an MDX SELECT statement.</span></span> <span data-ttu-id="4e223-116">Para obtener más información sobre la construcción de los ejes de consulta en una cláusula SELECT, vea [Especificar el contenido de un eje de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="4e223-116">For more information about the construction of query axes in a SELECT clause, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="4e223-117">Una cláusula FROM que determina qué cubo se consultará.</span><span class="sxs-lookup"><span data-stu-id="4e223-117">A FROM clause that determines which cube will be queried.</span></span> <span data-ttu-id="4e223-118">Para obtener más información sobre la cláusula FROM, vea [SELECT &#40;Instrucción, MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="4e223-118">For more information about the FROM clause, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
-   <span data-ttu-id="4e223-119">Una cláusula WHERE opcional que determina qué miembros o tuplas se utilizarán en el eje segmentador para restringir los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="4e223-119">An optional WHERE clause that determines which members or tuples to use on the slicer axis to restrict the data returned.</span></span> <span data-ttu-id="4e223-120">Para obtener más información sobre la construcción de un eje segmentador en una cláusula WHERE, vea [Especificar el contenido de un eje de división en sectores &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="4e223-120">For more information about the construction of a slicer axis in a WHERE clause, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e223-121">Para obtener más información detallada sobre las distintas cláusulas de la instrucción SELECT, vea [SELECT &#40;Instrucción, MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="4e223-121">For more detailed information about the various clauses of the SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="select-statement-syntax"></a><span data-ttu-id="4e223-122">Sintaxis de la instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="4e223-122">SELECT Statement Syntax</span></span>  
 <span data-ttu-id="4e223-123">En la sintaxis siguiente se muestra una instrucción SELECT básica que incluye el uso de las cláusulas SELECT, FROM y WHERE:</span><span class="sxs-lookup"><span data-stu-id="4e223-123">The following syntax shows a basic SELECT statement that includes the use of the SELECT, FROM, and WHERE clauses:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause>   
    [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
```  
  
 <span data-ttu-id="4e223-124">La instrucción MDX SELECT admite una sintaxis opcional, como la palabra clave WITH, el uso de funciones de MDX para crear miembros calculados incluyéndolos en un eje o en un eje segmentador, y la capacidad de devolver los valores de propiedades específicas de celda como parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4e223-124">The MDX SELECT statement supports optional syntax, such as the WITH keyword, the use of MDX functions to create calculated members for inclusion in an axis or slicer axis, and the ability to return the values of specific cell properties as part of the query.</span></span> <span data-ttu-id="4e223-125">Para obtener más información sobre la instrucción MDX SELECT, vea [SELECT &#40;Instrucción, MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="4e223-125">For more information about the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
### <a name="comparing-the-syntax-of-the-mdx-select-statement-to-sql"></a><span data-ttu-id="4e223-126">Comparar la sintaxis de la instrucción MDX SELECT con SQL</span><span class="sxs-lookup"><span data-stu-id="4e223-126">Comparing the Syntax of the MDX SELECT Statement to SQL</span></span>  
 <span data-ttu-id="4e223-127">El formato de la sintaxis de la instrucción MDX SELECT es similar al de la sintaxis de SQL.</span><span class="sxs-lookup"><span data-stu-id="4e223-127">The syntax format for the MDX SELECT statement is similar to that of SQL syntax.</span></span> <span data-ttu-id="4e223-128">Sin embargo, hay varias diferencias fundamentales:</span><span class="sxs-lookup"><span data-stu-id="4e223-128">However, there are several fundamental differences:</span></span>  
  
-   <span data-ttu-id="4e223-129">La sintaxis de MDX distingue los conjuntos circundando tuplas o miembros con llaves (los caracteres {y}). Para obtener más información sobre la sintaxis de miembros, tuplas y [conjuntos, vea trabajar con miembros, tuplas y conjuntos &#40;&#41;MDX ](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="4e223-129">MDX syntax distinguishes sets by surrounding tuples or members with braces (the { and } characters.) For more information about member, tuple, and set syntax, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
-   <span data-ttu-id="4e223-130">Las consultas de MDX pueden tener 0, 1, 2 ó hasta 128 ejes de consulta en la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="4e223-130">MDX queries can have 0, 1, 2 or up to 128 query axes in the SELECT statement.</span></span> <span data-ttu-id="4e223-131">Cada eje se comporta exactamente de la misma manera, a diferencia de en SQL, donde hay diferencias significativas entre el modo en que se comportan las filas y las columnas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="4e223-131">Each axis behaves in exactly the same way, unlike SQL where there are significant differences between how the rows and the columns of a query behave.</span></span>  
  
-   <span data-ttu-id="4e223-132">Al igual que con una consulta de SQL, la cláusula FROM da nombre al origen de los datos de la consulta de MDX.</span><span class="sxs-lookup"><span data-stu-id="4e223-132">As with an SQL query, the FROM clause names the source of the data for the MDX query.</span></span> <span data-ttu-id="4e223-133">Sin embargo, la cláusula MDX FROM está restringida a un solo cubo.</span><span class="sxs-lookup"><span data-stu-id="4e223-133">However, the MDX FROM clause is restricted to a single cube.</span></span> <span data-ttu-id="4e223-134">Se puede recuperar información de otros cubos, utilizando la función LookupCube valor por valor.</span><span class="sxs-lookup"><span data-stu-id="4e223-134">Information from other cubes can be retrieved on a value-by-value basis by using the LookupCube function.</span></span>  
  
-   <span data-ttu-id="4e223-135">La cláusula WHERE describe el eje segmentador de una consulta de MDX.</span><span class="sxs-lookup"><span data-stu-id="4e223-135">The WHERE clause describes the slicer axis in an MDX query.</span></span> <span data-ttu-id="4e223-136">Actúa como un eje invisible, un eje adicional en la consulta, dividiendo los valores que aparecen en las celdas del conjunto de resultados; a diferencia de la cláusula WHERE de SQL, que no afecta directamente a lo que aparece en el eje de las filas de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4e223-136">It acts as something like an invisible, extra axis in the query, slicing the values that appear in the cells in the result set; unlike the SQL WHERE clause it does not directly affect what appears on the rows axis of the query.</span></span> <span data-ttu-id="4e223-137">La funcionalidad de la cláusula WHERE de SQL está disponible a través de otras funciones de MDX como FILTER.</span><span class="sxs-lookup"><span data-stu-id="4e223-137">The functionality of the SQL WHERE clause is available through other MDX functions such as the FILTER function.</span></span>  
  
## <a name="select-statement-example"></a><span data-ttu-id="4e223-138">Ejemplo de instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="4e223-138">SELECT Statement Example</span></span>  
 <span data-ttu-id="4e223-139">En el siguiente ejemplo se muestra una consulta de MDX básica que utiliza la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="4e223-139">The following example shows a basic MDX query that uses the SELECT statement.</span></span> <span data-ttu-id="4e223-140">Esta consulta devuelve un conjunto de resultados que contiene las cifras de ventas e impuestos de 2002 y 2003 de la zona de ventas sudoeste.</span><span class="sxs-lookup"><span data-stu-id="4e223-140">This query returns a result set that contains the 2002 and 2003 sales and tax amounts for the Southwest sales territories.</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON COLUMNS,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON ROWS  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="4e223-141">En este ejemplo, la consulta define la siguiente información del conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="4e223-141">In this example, the query defines the following result set information:</span></span>  
  
-   <span data-ttu-id="4e223-142">La cláusula SELECT establece los ejes de la consulta en los miembros Sales Amount y Tax Amount de la dimensión Measures, y los miembros 2002 y 2003 de la dimensión Date.</span><span class="sxs-lookup"><span data-stu-id="4e223-142">The SELECT clause sets the query axes as the Sales Amount and Tax Amount members of the Measures dimension, and the 2002 and 2003 members of the Date dimension.</span></span>  
  
-   <span data-ttu-id="4e223-143">La cláusula FROM indica que el origen de datos es el cubo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="4e223-143">The FROM clause indicates that the data source is the Adventure Works cube.</span></span>  
  
-   <span data-ttu-id="4e223-144">La cláusula WHERE define el eje segmentador como el miembro Southwest de la dimensión Sales Territory.</span><span class="sxs-lookup"><span data-stu-id="4e223-144">The WHERE clause defines the slicer axis as the Southwest member of the Sales Territory dimension.</span></span>  
  
 <span data-ttu-id="4e223-145">Observe que el ejemplo de consulta utiliza también los alias de los ejes COLUMNS y ROWS.</span><span class="sxs-lookup"><span data-stu-id="4e223-145">Notice that the query example also uses the COLUMNS and ROWS axis aliases.</span></span> <span data-ttu-id="4e223-146">Las posiciones ordinales para estos ejes también podrían haberse utilizado.</span><span class="sxs-lookup"><span data-stu-id="4e223-146">The ordinal positions for these axes could also have been used.</span></span> <span data-ttu-id="4e223-147">En el siguiente ejemplo se muestra cómo podría haberse escrito la consulta de MDX para que utilizara la posición ordinal de cada eje:</span><span class="sxs-lookup"><span data-stu-id="4e223-147">The following example shows how the MDX query could have been written to use the ordinal position of each axis:</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON 0,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON 1  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="4e223-148">Para obtener ejemplos detallados, vea [Especificar el contenido de un eje de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) y [Especificar el contenido de un eje de división en sectores &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="4e223-148">For more detailed examples, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)and [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e223-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e223-149">See Also</span></span>  
 <span data-ttu-id="4e223-150">[Conceptos clave de &#40;MDX Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4e223-150">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 [<span data-ttu-id="4e223-151">SELECT &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4e223-151">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
