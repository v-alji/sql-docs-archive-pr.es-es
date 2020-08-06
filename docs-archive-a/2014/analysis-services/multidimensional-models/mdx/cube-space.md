---
title: Espacio del cubo | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c3a012b4-9ca0-4fb8-9c26-5ecc0e2e2b2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6a6da73815f06aa5ab80f6ad5a9d06227ed842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671737"
---
# <a name="cube-space"></a><span data-ttu-id="7937e-102">Espacio de cubo</span><span class="sxs-lookup"><span data-stu-id="7937e-102">Cube Space</span></span>
  <span data-ttu-id="7937e-103">El espacio de cubo es el producto de los miembros de las jerarquías de atributo de un cubo con las medidas de un cubo.</span><span class="sxs-lookup"><span data-stu-id="7937e-103">Cube space is the product of the members of a cube's attribute hierarchies with the cube's measures.</span></span> <span data-ttu-id="7937e-104">Por consiguiente, el espacio del cubo se determina con el producto combinatorio de todos los miembros de jerarquía de atributo en el cubo y las medidas del cubo, y define el tamaño máximo del cubo.</span><span class="sxs-lookup"><span data-stu-id="7937e-104">Therefore, the cube space is determined by the combinatorial product of all attribute hierarchy members in the cube and the cube's measures and defines the maximum size of the cube.</span></span> <span data-ttu-id="7937e-105">Es importante tener en cuenta que este espacio incluye todas las posibles combinaciones de miembros de la jerarquía de atributos, incluso las que podrían ser consideradas como imposibles en el mundo real, es decir, aquellas en las que la ciudad es París y los países son Gran Bretaña, España, Japón, India, etc.</span><span class="sxs-lookup"><span data-stu-id="7937e-105">It is important to note that this space includes all possible combinations of attribute hierarchy members; even combinations that might be deem as impossible in the real world i.e. combinations where the city is Paris and the countries are England or Spain or Japan or India or elsewhere.</span></span>  
  
## <a name="autoexists-and-cube-space"></a><span data-ttu-id="7937e-106">Espacio de cubo y Autoexist</span><span class="sxs-lookup"><span data-stu-id="7937e-106">Autoexists and cube space</span></span>  
 <span data-ttu-id="7937e-107">El concepto de *autoexist* limita este espacio de cubo a aquellas celdas que realmente existen.</span><span class="sxs-lookup"><span data-stu-id="7937e-107">The concept of *autoexists* limits this cube space to those cells that actually exist.</span></span> <span data-ttu-id="7937e-108">Los miembros de una jerarquía de atributo de una dimensión pueden no existir con los miembros de otra jerarquía de atributo de la misma dimensión.</span><span class="sxs-lookup"><span data-stu-id="7937e-108">Members of an attribute hierarchy in a dimension may not exist with members of another attribute hierarchy in the same dimension.</span></span>  
  
 <span data-ttu-id="7937e-109">Por ejemplo, si tiene un cubo con una jerarquía de atributo City, una jerarquía de atributo Country y una medida Internet Sales Amount, el espacio de este cubo solamente incluye a los miembros que existen entre sí.</span><span class="sxs-lookup"><span data-stu-id="7937e-109">For example, if you have a cube that has a City attribute hierarchy, a Country attribute hierarchy, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="7937e-110">Por ejemplo, si la jerarquía de atributo City incluye las ciudades de Nueva York, Londres, París, Tokio y Melbourne; y la jerarquía de atributo Country incluye los países Estados Unidos, Reino Unido, Francia, Japón y Australia; entonces el espacio del cubo no incluye el espacio (celda) en la intersección de París y Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="7937e-110">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="7937e-111">Al consultar las celdas que no existen, las celdas no existentes devuelven valores nulos; es decir, no pueden contener cálculos y no se puede definir un cálculo que escriba en este espacio.</span><span class="sxs-lookup"><span data-stu-id="7937e-111">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="7937e-112">Por ejemplo, la siguiente instrucción incluye celdas que no existen.</span><span class="sxs-lookup"><span data-stu-id="7937e-112">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="7937e-113">Esta consulta usa la función [Members (Set) (MDX)](/sql/mdx/members-set-mdx) para devolver el conjunto de miembros de la jerarquía de atributo Gender en el eje de columnas y cruza este conjunto con el conjunto especificado de miembros de la jerarquía de atributo Customer en el eje de filas.</span><span class="sxs-lookup"><span data-stu-id="7937e-113">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="7937e-114">Cuando se ejecuta la consulta anterior, la celda en la intersección de Aaron A. Allen y Female muestra un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="7937e-114">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="7937e-115">De igual manera, la celda en la intersección de Abigail Clark y Male muestra un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="7937e-115">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="7937e-116">Estas celdas no existen y no pueden contener un valor, pero las celdas que no existen pueden aparecer en el resultado devuelto por una consulta.</span><span class="sxs-lookup"><span data-stu-id="7937e-116">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="7937e-117">Al usar la función [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) para devolver el producto cruzado de los miembros de la jerarquía de atributo de las jerarquías de atributo de la misma dimensión, auto-exists limita las tuplas devueltas al conjunto de tuplas que realmente existen, en lugar de devolver un producto cartesiano completo.</span><span class="sxs-lookup"><span data-stu-id="7937e-117">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="7937e-118">Por ejemplo, ejecute y examine los resultados de la ejecución de la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="7937e-118">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="7937e-119">Observe que 0 se utiliza para designar al eje de columna, que es una abreviatura para el eje(0), que es el eje de columna.</span><span class="sxs-lookup"><span data-stu-id="7937e-119">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="7937e-120">La consulta anterior solo devuelve celdas para los miembros de cada jerarquía de atributo de la consulta que existen entre sí.</span><span class="sxs-lookup"><span data-stu-id="7937e-120">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="7937e-121">La consulta anterior también se puede escribir con la nueva \* variante de la función [ \* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="7937e-121">The previous query can also be written using the new \* variant of the [\* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="7937e-122">La consulta anterior también se podría escribir de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7937e-122">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="7937e-123">Los valores de celda devueltos serán idénticos, aunque los metadatos del conjunto de resultados serán diferentes.</span><span class="sxs-lookup"><span data-stu-id="7937e-123">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="7937e-124">Por ejemplo, con la consulta anterior, la jerarquía Country se movió al eje segmentador (en la cláusula WHERE), por lo que no aparece explícitamente en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7937e-124">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="7937e-125">Cada una de estas tres consultas anteriores muestra el efecto del comportamiento de autoexists en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7937e-125">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="user-defined-hierarchies-and-cube-space"></a><span data-ttu-id="7937e-126">Jerarquías definidas por el usuario y espacio de cubo</span><span class="sxs-lookup"><span data-stu-id="7937e-126">User-Defined Hierarchies and Cube Space</span></span>  
 <span data-ttu-id="7937e-127">Los ejemplos anteriores de este tema definen posiciones en el espacio de cubo mediante jerarquías de atributo.</span><span class="sxs-lookup"><span data-stu-id="7937e-127">The previous examples in this topic define positions in cube space by using attribute hierarchies.</span></span> <span data-ttu-id="7937e-128">Sin embargo, también se puede definir una posición en un espacio de cubo mediante jerarquías definidas por el usuario que se han definido en base a las jerarquías de atributo de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="7937e-128">However, you can also define a position in cube space by using user-defined hierarchies that have been defined based on attribute hierarchies in a dimension.</span></span> <span data-ttu-id="7937e-129">Una jerarquía definida por el usuario es una jerarquía de jerarquías de atributo diseñadas para facilitar la exploración del cubo por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7937e-129">A user-defined hierarchy is a hierarchy of attribute hierarchies designed to facilitate browsing of cube data by users.</span></span>  
  
 <span data-ttu-id="7937e-130">Por ejemplo, la consulta `CROSSJOIN` de la sección anterior también pudo haber sido escrita de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7937e-130">For example, the `CROSSJOIN` query in the previous section could also have been written as follows:</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[Customer Geography].[State-Province].Members  
   )   
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="7937e-131">En la consulta anterior, la jerarquía definida por el usuario Customer Geography de la dimensión Customer se utiliza para definir la posición en el espacio de cubo que se definió anteriormente mediante una jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="7937e-131">In the previous query, the Customer Geography user-defined hierarchy within the Customer dimension is used to define the position in cube space that was previously defined by using an attribute hierarchy.</span></span> <span data-ttu-id="7937e-132">La posición idéntica en el espacio de cubo puede definirse mediante jerarquías de atributo o jerarquías definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7937e-132">The identical position in cube space can be defined by using either attribute hierarchies or user-defined hierarchies.</span></span>  
  
##  <a name="attribute-relationships-and-cube-space"></a><a name="AttribRelationships"></a><span data-ttu-id="7937e-133">Relaciones de atributo y espacio de cubo</span><span class="sxs-lookup"><span data-stu-id="7937e-133">Attribute Relationships and Cube Space</span></span>  
 <span data-ttu-id="7937e-134">El definir relaciones de atributo entre atributos relacionados mejora el rendimiento de las consultas (al facilitar la creación de agregaciones apropiadas) y afecta al miembro de una jerarquía de atributo relacionada que aparece con un miembro de jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="7937e-134">Defining attribute relationships between related attributes improves query performance (by facilitating the creation of appropriate aggregations) and affects the member of a related attribute hierarchy that appears with an attribute hierarchy member.</span></span> <span data-ttu-id="7937e-135">Por ejemplo, cuando define una tupla que incluye a un miembro de la jerarquía de atributo City y la tupla no define explícitamente al miembro de la jerarquía de atributo Country, se puede esperar que el miembro de la jerarquía de atributo predeterminada Country sea el miembro relacionado de la jerarquía de atributo Country.</span><span class="sxs-lookup"><span data-stu-id="7937e-135">For example, when you define a tuple that includes a member from the City attribute hierarchy and the tuple does not explicitly define the Country attribute hierarchy member, you might expect that the default Country attribute hierarchy member would be the related member of the Country attribute hierarchy.</span></span> <span data-ttu-id="7937e-136">Sin embargo, esto es cierto solo si se define una relación de atributo entre la jerarquía de atributo City y la jerarquía de atributo Country.</span><span class="sxs-lookup"><span data-stu-id="7937e-136">However, this is only true if an attribute relationship is defined between the City attribute hierarchy and the Country attribute hierarchy.</span></span>  
  
 <span data-ttu-id="7937e-137">El ejemplo siguiente devuelve el miembro de una jerarquía de atributo relacionada que no está incluida explícitamente en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7937e-137">The following example returns the member of a related attribute hierarchy that is not included explicitly in the query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Country.CurrentMember.Name  
SELECT Measures.x ON 0,  
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="7937e-138">Observe que la `WITH` palabra clave se usa con las funciones [CURRENTMEMBER (MDX)](/sql/mdx/current-mdx) y [Name (MDX)](/sql/mdx/members-string-mdx) para crear un miembro calculado para su uso en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7937e-138">Notice that the `WITH` keyword is used with the [CurrentMember (MDX)](/sql/mdx/current-mdx) and [Name (MDX)](/sql/mdx/members-string-mdx) functions to create a calculated member for use in the query.</span></span> <span data-ttu-id="7937e-139">Para más información, vea [Consulta de MDX básica &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="7937e-139">For more information, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
 <span data-ttu-id="7937e-140">En la consulta anterior, se devuelve el nombre del miembro de la jerarquía de atributo Country asociado con cada miembro de la jerarquía de atributo State.</span><span class="sxs-lookup"><span data-stu-id="7937e-140">In the previous query, the name of the member of the Country attribute hierarchy that is associated with each member of the State attribute hierarchy is returned.</span></span> <span data-ttu-id="7937e-141">Aparece el miembro Country esperado (debido a que hay una relación de atributo definida entre los atributos City y Country).</span><span class="sxs-lookup"><span data-stu-id="7937e-141">The expected Country member appears (because an attribute relationship is defined between the City and Country attributes).</span></span> <span data-ttu-id="7937e-142">Sin embargo, si no se define una relación de atributo entre las jerarquías de atributo de la misma dimensión, se devuelve el miembro (All), como se muestra en la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="7937e-142">However, if no attribute relationship were defined between attribute hierarchies in the same dimension, the (All) member would be returned, as illustrated in the following query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Education.Currentmember.Name  
SELECT Measures.x  ON 0,   
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="7937e-143">En la consulta anterior, se devuelve el miembro (All) ("All Customers"), debido a que no hay una relación entre Education y City.</span><span class="sxs-lookup"><span data-stu-id="7937e-143">In the previous query, the (All) member ("All Customers") is returned, because there is no relationship between Education and City.</span></span> <span data-ttu-id="7937e-144">Por lo tanto, el miembro (All) de la jerarquía de atributo Education sería el miembro predeterminado de la jerarquía de atributo Education utilizada en cualquier tupla en la que interviniera la jerarquía de atributo City y no se proporcionara explícitamente un miembro Education.</span><span class="sxs-lookup"><span data-stu-id="7937e-144">Therefore, the (All) member of the Education attribute hierarchy would be the default member of the Education attribute hierarchy used in any tuple involving the City attribute hierarchy where an Education member is not explicitly provided.</span></span>  
  
## <a name="calculation-context"></a><span data-ttu-id="7937e-145">Contexto de cálculo</span><span class="sxs-lookup"><span data-stu-id="7937e-145">Calculation Context</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7937e-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7937e-146">See Also</span></span>  
 <span data-ttu-id="7937e-147">[Conceptos clave de &#40;MDX Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="7937e-147">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="7937e-148">[Tuplas](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="7937e-148">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="7937e-149">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="7937e-149">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="7937e-150">[Trabajar con miembros, tuplas y conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="7937e-150">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="7937e-151">[Totales visuales y totales no visuales](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="7937e-151">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="7937e-152">[Referencia del lenguaje MDX &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="7937e-152">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="7937e-153">Referencia de expresiones multidimensionales &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="7937e-153">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
