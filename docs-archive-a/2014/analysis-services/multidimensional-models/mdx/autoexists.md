---
title: Autoexists | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 56283497-624c-45b5-8a0d-036b0e331d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd35958a364456c12d58392afe3754f6adcf97b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674414"
---
# <a name="autoexists"></a><span data-ttu-id="2cd2d-102">autoexist</span><span class="sxs-lookup"><span data-stu-id="2cd2d-102">Autoexists</span></span>
  <span data-ttu-id="2cd2d-103">El concepto de *autoexists* limita el espacio del cubo a esas celdas que realmente existen en el cubo en contraposición a aquellas que podrían existir como resultado de la creación de todas las posibles combinaciones de miembros de jerarquía de atributo a partir de la misma jerarquía.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-103">The concept of *autoexists* limits the cube space to those cells that actually exist in the cube in contraposition to those that might exist as a result of creating all possible combinations of attribute hierarchy members from the same hierarchy.</span></span> <span data-ttu-id="2cd2d-104">Esto es así porque los miembros de una jerarquía de atributo no pueden existir con los miembros de otra jerarquía de atributo de la misma dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-104">This is because members of one attribute hierarchy cannot exist with members of another attribute hierarchy in the same dimension.</span></span> <span data-ttu-id="2cd2d-105">Cuando dos o más jerarquías de atributos de la dimensión se usan en una instrucción SELECT, Analysis Services evalúa las expresiones de los atributos para asegurarse de que los miembros de dichos atributos están correctamente delimitados, a fin de cumplir los criterios de todos los demás atributos.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-105">When two or more attribute hierarchies of the same dimension are used in a SELECT statement, Analysis Services evaluates the attributes' expressions to make sure that the members of those attributes are properly confined to meet the criteria of all other attributes.</span></span>  
  
 <span data-ttu-id="2cd2d-106">Por ejemplo, supongamos que está trabajando con atributos de la dimensión Geography.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-106">For example, suppose you are working with attributes from the Geography dimension.</span></span> <span data-ttu-id="2cd2d-107">Si tiene una expresión que devuelve todos los miembros del atributo City, y otra expresión que delimita los miembros del atributo Country a todos los países de Europa, los miembros de City quedarán delimitados a aquellas ciudades que pertenezcan únicamente a países de Europa.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-107">If you have one expression that returns all members from the City attribute and another expression that confines members from the Country attribute to all countries in Europe, then this will result in the City members being confined to only those cities that belong to countries in Europe.</span></span> <span data-ttu-id="2cd2d-108">Esto es debido a la característica de autoexists de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-108">This is because of the autoexists characteristic of Analysis Services.</span></span> <span data-ttu-id="2cd2d-109">Autoexists solamente se aplica a atributos de una misma dimensión porque intenta impedir que los registros de la dimensión excluidos de una expresión de atributos se incluyan en las demás expresiones de atributos.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-109">Autoexists only applies to attributes from the same dimension because it tries to prevent the dimension records excluded in one attribute expression from being included by the other attribute expressions.</span></span> <span data-ttu-id="2cd2d-110">Autoexists también puede entenderse como la intersección resultante de las distintas expresiones de atributos de las filas de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-110">Autoexists can also be understood as the resulting intersection of the different attributes expressions over the dimension rows.</span></span>  
  
## <a name="cell-existence"></a><span data-ttu-id="2cd2d-111">Existencia de celdas</span><span class="sxs-lookup"><span data-stu-id="2cd2d-111">Cell Existence</span></span>  
 <span data-ttu-id="2cd2d-112">Las siguientes celdas siempre existen:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-112">The following cells always exist:</span></span>  
  
-   <span data-ttu-id="2cd2d-113">El miembro (All), de cada jerarquía, cuando se cruza con miembros de otras jerarquías de la misma dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-113">The (All) member, of every hierarchy, when crossed with members of other hierarchies in the same dimension.</span></span>  
  
-   <span data-ttu-id="2cd2d-114">Los miembros calculados cuando se cruzan con los elementos del mismo nivel no calculados o con los miembros primarios o descendientes de los elementos del mismo nivel no calculados.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-114">Calculated members when crossed with their non-calculated siblings, or with the parents or descendants of their non-calculated siblings.</span></span>  
  
## <a name="providing-non-existing-cells"></a><span data-ttu-id="2cd2d-115">Proporcionar celdas no existentes</span><span class="sxs-lookup"><span data-stu-id="2cd2d-115">Providing Non-existing cells</span></span>  
 <span data-ttu-id="2cd2d-116">Una celda no existente es una celda proporcionada por el sistema como respuesta a una consulta o cálculo que solicita una celda que no existe en el cubo.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-116">A non-existing cell is a cell provided by the system as a response to a query or calculation that requests a cell that does not exist in the cube.</span></span> <span data-ttu-id="2cd2d-117">Por ejemplo, si tiene un cubo con una jerarquía de atributo City y una jerarquía de atributo Country que pertenece a la dimensión Geography, y la medida Internet Sales Amount, el espacio de este cubo solamente incluye a los miembros que existen entre sí.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-117">For example, if you have a cube that has a City attribute hierarchy and a Country attribute hierarchy that belong to the Geography dimension, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="2cd2d-118">Por ejemplo, si la jerarquía de atributo City incluye las ciudades de Nueva York, Londres, París, Tokio y Melbourne; y la jerarquía de atributo Country incluye los países Estados Unidos, Reino Unido, Francia, Japón y Australia; entonces el espacio del cubo no incluye el espacio (celda) en la intersección de París y Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-118">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="2cd2d-119">Al consultar las celdas que no existen, las celdas no existentes devuelven valores nulos; es decir, no pueden contener cálculos y no se puede definir un cálculo que escriba en este espacio.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-119">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="2cd2d-120">Por ejemplo, la siguiente instrucción incluye celdas que no existen.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-120">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2cd2d-121">Esta consulta usa la función [Members (Set) (MDX)](/sql/mdx/members-set-mdx) para devolver el conjunto de miembros de la jerarquía de atributo Gender en el eje de columnas y cruza este conjunto con el conjunto especificado de miembros de la jerarquía de atributo Customer en el eje de filas.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-121">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="2cd2d-122">Cuando se ejecuta la consulta anterior, la celda en la intersección de Aaron A. Allen y Female muestra un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-122">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="2cd2d-123">De igual manera, la celda en la intersección de Abigail Clark y Male muestra un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-123">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="2cd2d-124">Estas celdas no existen y no pueden contener un valor, pero las celdas que no existen pueden aparecer en el resultado devuelto por una consulta.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-124">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="2cd2d-125">Al usar la función [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) para devolver el producto cruzado de los miembros de la jerarquía de atributo de las jerarquías de atributo de la misma dimensión, auto-exists limita las tuplas devueltas al conjunto de tuplas que realmente existen, en lugar de devolver un producto cartesiano completo.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-125">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="2cd2d-126">Por ejemplo, ejecute y examine los resultados de la ejecución de la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-126">For example, run and then examine the results from the execution of the following query.</span></span>  
  
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
>  <span data-ttu-id="2cd2d-127">Observe que 0 se utiliza para designar al eje de columna, que es una abreviatura para el eje(0), que es el eje de columna.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-127">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="2cd2d-128">La consulta anterior solo devuelve celdas para los miembros de cada jerarquía de atributo de la consulta que existen entre sí.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-128">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="2cd2d-129">La consulta anterior también puede escribirse con la nueva variante \* de la función [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="2cd2d-129">The previous query can also be written using the new \* variant of the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="2cd2d-130">La consulta anterior también se podría escribir de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-130">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="2cd2d-131">Los valores de celda devueltos serán idénticos, aunque los metadatos del conjunto de resultados serán diferentes.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-131">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="2cd2d-132">Por ejemplo, con la consulta anterior, la jerarquía Country se movió al eje segmentador (en la cláusula WHERE), por lo que no aparece explícitamente en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-132">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="2cd2d-133">Cada una de estas tres consultas anteriores muestra el efecto del comportamiento de autoexists en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cd2d-133">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="deep-and-shallow-autoexists"></a><span data-ttu-id="2cd2d-134">Deep y Shallow Autoexists</span><span class="sxs-lookup"><span data-stu-id="2cd2d-134">Deep and Shallow Autoexists</span></span>  
 <span data-ttu-id="2cd2d-135">Autoexists se puede aplicar a las expresiones como Deep y Shallow.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-135">Autoexists can be applied to the expressions as Deep or Shallow.</span></span> <span data-ttu-id="2cd2d-136">`Deep Autoexists` quiere decir que todas las expresiones se evaluarán para cumplir el espacio más profundo posible después de aplicar las expresiones de eje segmentador, expresiones de subselección en el eje, etc.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-136">`Deep Autoexists` means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span> <span data-ttu-id="2cd2d-137">`Shallow Autoexists` quiere decir que las expresiones externas se evalúan antes que la expresión actual y los resultados se pasan a la expresión actual.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-137">`Shallow Autoexists` means that external expressions are evaluated before the current expression and those results are passed to the current expression.</span></span> <span data-ttu-id="2cd2d-138">El valor predeterminado es deep autoexists.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-138">The default setting is deep autoexists.</span></span>  
  
 <span data-ttu-id="2cd2d-139">El siguiente escenario y ejemplos ayudarán a mostrar los tipos diferentes de autoexists.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-139">The following scenario and samples will help to illustrate the different types of Autoexistss.</span></span> <span data-ttu-id="2cd2d-140">En los ejemplos siguientes, se crearán dos conjuntos: uno de ellos como una expresión calculada, y el otro como una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-140">In the following examples two sets will be created: one as a calculated expression and the other as a constant expression.</span></span>  
  
 `//Obtain the Top 10 best reseller selling products by Name`  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="2cd2d-141">El conjunto de resultados obtenido es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-141">The obtained result set is:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="2cd2d-142">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-142">**Reseller Sales Amount**</span></span>|<span data-ttu-id="2cd2d-143">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-143">**Discount Amount**</span></span>|<span data-ttu-id="2cd2d-144">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-144">**PCT Discount**</span></span>|  
|<span data-ttu-id="2cd2d-145">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-145">**Mountain-200**</span></span>|<span data-ttu-id="2cd2d-146">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-146">**$14,356,699.36**</span></span>|<span data-ttu-id="2cd2d-147">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-147">**$19,012.71**</span></span>|<span data-ttu-id="2cd2d-148">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-148">**0.13%**</span></span>|  
|<span data-ttu-id="2cd2d-149">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-149">**Road-250**</span></span>|<span data-ttu-id="2cd2d-150">**$9,377,457.68**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-150">**$9,377,457.68**</span></span>|<span data-ttu-id="2cd2d-151">**$4,032.47**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-151">**$4,032.47**</span></span>|<span data-ttu-id="2cd2d-152">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-152">**0.04%**</span></span>|  
|<span data-ttu-id="2cd2d-153">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-153">**Mountain-100**</span></span>|<span data-ttu-id="2cd2d-154">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-154">**$8,568,958.27**</span></span>|<span data-ttu-id="2cd2d-155">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-155">**$139,393.27**</span></span>|<span data-ttu-id="2cd2d-156">**1,63 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-156">**1.63%**</span></span>|  
|<span data-ttu-id="2cd2d-157">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-157">**Road-650**</span></span>|<span data-ttu-id="2cd2d-158">**$7,442,141.81**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-158">**$7,442,141.81**</span></span>|<span data-ttu-id="2cd2d-159">**$39,698.30**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-159">**$39,698.30**</span></span>|<span data-ttu-id="2cd2d-160">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-160">**0.53%**</span></span>|  
|<span data-ttu-id="2cd2d-161">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-161">**Touring-1000**</span></span>|<span data-ttu-id="2cd2d-162">**$6,723,794.29**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-162">**$6,723,794.29**</span></span>|<span data-ttu-id="2cd2d-163">**$166,144.17**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-163">**$166,144.17**</span></span>|<span data-ttu-id="2cd2d-164">**2,47 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-164">**2.47%**</span></span>|  
|<span data-ttu-id="2cd2d-165">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-165">**Road-550-W**</span></span>|<span data-ttu-id="2cd2d-166">**$3,668,383.88**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-166">**$3,668,383.88**</span></span>|<span data-ttu-id="2cd2d-167">**$1,901.97**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-167">**$1,901.97**</span></span>|<span data-ttu-id="2cd2d-168">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-168">**0.05%**</span></span>|  
|<span data-ttu-id="2cd2d-169">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-169">**Road-350-W**</span></span>|<span data-ttu-id="2cd2d-170">**$3,665,932.31**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-170">**$3,665,932.31**</span></span>|<span data-ttu-id="2cd2d-171">**$20,946.50**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-171">**$20,946.50**</span></span>|<span data-ttu-id="2cd2d-172">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-172">**0.57%**</span></span>|  
|<span data-ttu-id="2cd2d-173">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-173">**HL Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-174">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-174">**$3,365,069.27**</span></span>|<span data-ttu-id="2cd2d-175">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-175">**$174.11**</span></span>|<span data-ttu-id="2cd2d-176">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-176">**0.01%**</span></span>|  
|<span data-ttu-id="2cd2d-177">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-177">**Road-150**</span></span>|<span data-ttu-id="2cd2d-178">**$2,363,805.16**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-178">**$2,363,805.16**</span></span>|<span data-ttu-id="2cd2d-179">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-179">**$0.00**</span></span>|<span data-ttu-id="2cd2d-180">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-180">**0.00%**</span></span>|  
|<span data-ttu-id="2cd2d-181">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-181">**Touring-3000**</span></span>|<span data-ttu-id="2cd2d-182">**$2,046,508.26**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-182">**$2,046,508.26**</span></span>|<span data-ttu-id="2cd2d-183">**$79,582.15**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-183">**$79,582.15**</span></span>|<span data-ttu-id="2cd2d-184">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-184">**3.89%**</span></span>|  
  
 <span data-ttu-id="2cd2d-185">El conjunto de productos obtenido parece el mismo que el de Preferred10Products; de modo que, comprobando el conjunto de Preferred10Products:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-185">The obtained set of products seems to be the same as Preferred10Products; so, verifying the Preferred10Products set:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="2cd2d-186">En lo que respecta a los siguientes resultados, ambos conjuntos (Top10SellingProducts y Preferred10Products) son iguales.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-186">As per the following results, both sets (Top10SellingProducts, Preferred10Products) are the same</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="2cd2d-187">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-187">**Reseller Sales Amount**</span></span>|<span data-ttu-id="2cd2d-188">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-188">**Discount Amount**</span></span>|<span data-ttu-id="2cd2d-189">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-189">**PCT Discount**</span></span>|  
|<span data-ttu-id="2cd2d-190">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-190">**Mountain-200**</span></span>|<span data-ttu-id="2cd2d-191">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-191">**$14,356,699.36**</span></span>|<span data-ttu-id="2cd2d-192">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-192">**$19,012.71**</span></span>|<span data-ttu-id="2cd2d-193">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-193">**0.13%**</span></span>|  
|<span data-ttu-id="2cd2d-194">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-194">**Road-250**</span></span>|<span data-ttu-id="2cd2d-195">**$9,377,457.68**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-195">**$9,377,457.68**</span></span>|<span data-ttu-id="2cd2d-196">**$4,032.47**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-196">**$4,032.47**</span></span>|<span data-ttu-id="2cd2d-197">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-197">**0.04%**</span></span>|  
|<span data-ttu-id="2cd2d-198">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-198">**Mountain-100**</span></span>|<span data-ttu-id="2cd2d-199">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-199">**$8,568,958.27**</span></span>|<span data-ttu-id="2cd2d-200">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-200">**$139,393.27**</span></span>|<span data-ttu-id="2cd2d-201">**1,63 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-201">**1.63%**</span></span>|  
|<span data-ttu-id="2cd2d-202">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-202">**Road-650**</span></span>|<span data-ttu-id="2cd2d-203">**$7,442,141.81**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-203">**$7,442,141.81**</span></span>|<span data-ttu-id="2cd2d-204">**$39,698.30**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-204">**$39,698.30**</span></span>|<span data-ttu-id="2cd2d-205">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-205">**0.53%**</span></span>|  
|<span data-ttu-id="2cd2d-206">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-206">**Touring-1000**</span></span>|<span data-ttu-id="2cd2d-207">**$6,723,794.29**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-207">**$6,723,794.29**</span></span>|<span data-ttu-id="2cd2d-208">**$166,144.17**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-208">**$166,144.17**</span></span>|<span data-ttu-id="2cd2d-209">**2,47 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-209">**2.47%**</span></span>|  
|<span data-ttu-id="2cd2d-210">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-210">**Road-550-W**</span></span>|<span data-ttu-id="2cd2d-211">**$3,668,383.88**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-211">**$3,668,383.88**</span></span>|<span data-ttu-id="2cd2d-212">**$1,901.97**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-212">**$1,901.97**</span></span>|<span data-ttu-id="2cd2d-213">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-213">**0.05%**</span></span>|  
|<span data-ttu-id="2cd2d-214">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-214">**Road-350-W**</span></span>|<span data-ttu-id="2cd2d-215">**$3,665,932.31**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-215">**$3,665,932.31**</span></span>|<span data-ttu-id="2cd2d-216">**$20,946.50**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-216">**$20,946.50**</span></span>|<span data-ttu-id="2cd2d-217">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-217">**0.57%**</span></span>|  
|<span data-ttu-id="2cd2d-218">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-218">**HL Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-219">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-219">**$3,365,069.27**</span></span>|<span data-ttu-id="2cd2d-220">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-220">**$174.11**</span></span>|<span data-ttu-id="2cd2d-221">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-221">**0.01%**</span></span>|  
|<span data-ttu-id="2cd2d-222">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-222">**Road-150**</span></span>|<span data-ttu-id="2cd2d-223">**$2,363,805.16**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-223">**$2,363,805.16**</span></span>|<span data-ttu-id="2cd2d-224">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-224">**$0.00**</span></span>|<span data-ttu-id="2cd2d-225">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-225">**0.00%**</span></span>|  
|<span data-ttu-id="2cd2d-226">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-226">**Touring-3000**</span></span>|<span data-ttu-id="2cd2d-227">**$2,046,508.26**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-227">**$2,046,508.26**</span></span>|<span data-ttu-id="2cd2d-228">**$79,582.15**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-228">**$79,582.15**</span></span>|<span data-ttu-id="2cd2d-229">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-229">**3.89%**</span></span>|  
  
 <span data-ttu-id="2cd2d-230">En el siguiente ejemplo se ilustrará el concepto de Autoexists en modo profundo.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-230">The following example will illustrate the concept of deep Autoexists.</span></span> <span data-ttu-id="2cd2d-231">En el ejemplo, Top10SellingProducts se filtra por el atributo [Product].[Product Line] para los productos del grupo [Mountain].</span><span class="sxs-lookup"><span data-stu-id="2cd2d-231">In the example we are filtering Top10SellingProducts by [Product].[Product Line] attribute for those in [Mountain] group.</span></span> <span data-ttu-id="2cd2d-232">Tenga en cuenta que ambos atributos (slicer y axis) pertenecen a la misma dimensión, [Product].</span><span class="sxs-lookup"><span data-stu-id="2cd2d-232">Note that both attributes (slicer and axis) belong to the same dimension, [Product].</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `// Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="2cd2d-233">Produce el siguiente conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-233">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="2cd2d-234">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-234">**Reseller Sales Amount**</span></span>|<span data-ttu-id="2cd2d-235">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-235">**Discount Amount**</span></span>|<span data-ttu-id="2cd2d-236">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-236">**PCT Discount**</span></span>|  
|<span data-ttu-id="2cd2d-237">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-237">**Mountain-200**</span></span>|<span data-ttu-id="2cd2d-238">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-238">**$14,356,699.36**</span></span>|<span data-ttu-id="2cd2d-239">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-239">**$19,012.71**</span></span>|<span data-ttu-id="2cd2d-240">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-240">**0.13%**</span></span>|  
|<span data-ttu-id="2cd2d-241">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-241">**Mountain-100**</span></span>|<span data-ttu-id="2cd2d-242">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-242">**$8,568,958.27**</span></span>|<span data-ttu-id="2cd2d-243">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-243">**$139,393.27**</span></span>|<span data-ttu-id="2cd2d-244">**1,63 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-244">**1.63%**</span></span>|  
|<span data-ttu-id="2cd2d-245">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-245">**HL Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-246">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-246">**$3,365,069.27**</span></span>|<span data-ttu-id="2cd2d-247">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-247">**$174.11**</span></span>|<span data-ttu-id="2cd2d-248">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-248">**0.01%**</span></span>|  
|<span data-ttu-id="2cd2d-249">**Mountain-300**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-249">**Mountain-300**</span></span>|<span data-ttu-id="2cd2d-250">**$1,907,249.38**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-250">**$1,907,249.38**</span></span>|<span data-ttu-id="2cd2d-251">**$876.95**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-251">**$876.95**</span></span>|<span data-ttu-id="2cd2d-252">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-252">**0.05%**</span></span>|  
|<span data-ttu-id="2cd2d-253">**Mountain-500**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-253">**Mountain-500**</span></span>|<span data-ttu-id="2cd2d-254">**$1,067,327.31**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-254">**$1,067,327.31**</span></span>|<span data-ttu-id="2cd2d-255">**$17,266.09**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-255">**$17,266.09**</span></span>|<span data-ttu-id="2cd2d-256">**1,62%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-256">**1.62%**</span></span>|  
|<span data-ttu-id="2cd2d-257">**Mountain-400-W**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-257">**Mountain-400-W**</span></span>|<span data-ttu-id="2cd2d-258">**$592,450.05**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-258">**$592,450.05**</span></span>|<span data-ttu-id="2cd2d-259">**$303.49**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-259">**$303.49**</span></span>|<span data-ttu-id="2cd2d-260">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-260">**0.05%**</span></span>|  
|<span data-ttu-id="2cd2d-261">**LL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-261">**LL Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-262">**$521,864.42**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-262">**$521,864.42**</span></span>|<span data-ttu-id="2cd2d-263">**$252.41**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-263">**$252.41**</span></span>|<span data-ttu-id="2cd2d-264">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-264">**0.05%**</span></span>|  
|<span data-ttu-id="2cd2d-265">**ML Mountain Frame-W**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-265">**ML Mountain Frame-W**</span></span>|<span data-ttu-id="2cd2d-266">**$482,953.16**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-266">**$482,953.16**</span></span>|<span data-ttu-id="2cd2d-267">**$206,95**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-267">**$206.95**</span></span>|<span data-ttu-id="2cd2d-268">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-268">**0.04%**</span></span>|  
|<span data-ttu-id="2cd2d-269">**ML Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-269">**ML Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-270">**$343,785.29**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-270">**$343,785.29**</span></span>|<span data-ttu-id="2cd2d-271">**$161.82**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-271">**$161.82**</span></span>|<span data-ttu-id="2cd2d-272">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-272">**0.05%**</span></span>|  
|<span data-ttu-id="2cd2d-273">**Women's Mountain Shorts**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-273">**Women's Mountain Shorts**</span></span>|<span data-ttu-id="2cd2d-274">**$260,304.09**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-274">**$260,304.09**</span></span>|<span data-ttu-id="2cd2d-275">**$6,675.56**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-275">**$6,675.56**</span></span>|<span data-ttu-id="2cd2d-276">**2,56%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-276">**2.56%**</span></span>|  
  
 <span data-ttu-id="2cd2d-277">En el conjunto de resultados anterior se muestran siete nuevas entradas en la lista Top10SellingProducts y, además, vemos que Mountain-200, Mountain-100 y HL Mountain Frame se han movido a la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-277">In the above result set we have seven newcomers to the list of Top10SellingProducts and Mountain-200, Mountain-100, and HL Mountain Frame have moved to the top of the list.</span></span> <span data-ttu-id="2cd2d-278">En el conjunto de resultados anterior, esos tres valores se intercalaban.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-278">In the previous result set those three values were interspersed.</span></span>  
  
 <span data-ttu-id="2cd2d-279">Esto es lo que se denomina Autoexists en modo profundo, porque el conjunto Top10SellingProducts se evalúa para cumplir las condiciones de segmentación de la consulta.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-279">This is called Deep Autoexists, because the Top10SellingProducts set is evaluated to meet the slicing conditions of the query.</span></span> <span data-ttu-id="2cd2d-280">El modo Deep Autoexists implica que todas las expresiones se evaluarán para cumplir el espacio más profundo posible después de aplicar las expresiones del segmentador, las expresiones de subselección del eje, etc.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-280">Deep Autoexists means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span>  
  
 <span data-ttu-id="2cd2d-281">No obstante, es posible que algún usuario desee poder realizar el análisis sobre Top10SellingProducts como equivalente de Preferred10Products, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-281">However, one might want to be able to do the analysis over the Top10SellingProducts as equivalent to Preferred10Products, as in the following example:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="2cd2d-282">Produce el siguiente conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="2cd2d-282">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="2cd2d-283">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-283">**Reseller Sales Amount**</span></span>|<span data-ttu-id="2cd2d-284">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-284">**Discount Amount**</span></span>|<span data-ttu-id="2cd2d-285">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-285">**PCT Discount**</span></span>|  
|<span data-ttu-id="2cd2d-286">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-286">**Mountain-200**</span></span>|<span data-ttu-id="2cd2d-287">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-287">**$14,356,699.36**</span></span>|<span data-ttu-id="2cd2d-288">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-288">**$19,012.71**</span></span>|<span data-ttu-id="2cd2d-289">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-289">**0.13%**</span></span>|  
|<span data-ttu-id="2cd2d-290">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-290">**Mountain-100**</span></span>|<span data-ttu-id="2cd2d-291">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-291">**$8,568,958.27**</span></span>|<span data-ttu-id="2cd2d-292">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-292">**$139,393.27**</span></span>|<span data-ttu-id="2cd2d-293">**1,63 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-293">**1.63%**</span></span>|  
|<span data-ttu-id="2cd2d-294">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-294">**HL Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-295">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-295">**$3,365,069.27**</span></span>|<span data-ttu-id="2cd2d-296">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-296">**$174.11**</span></span>|<span data-ttu-id="2cd2d-297">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-297">**0.01%**</span></span>|  
  
 <span data-ttu-id="2cd2d-298">En los resultados anteriores, la segmentación arroja un resultado que solamente incluye los productos Preferred10Products que forman parte del grupo [Mountain] de [Product].[Product Line]; es el resultado esperado, porque Preferred10Products es una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-298">In the above results, the slicing gives a result that contains only those products from Preferred10Products that are part of the [Mountain] group in [Product].[Product Line]; as expected, because Preferred10Products is a constant expression.</span></span>  
  
 <span data-ttu-id="2cd2d-299">Este conjunto de resultados también se entiende como shallow autoexists.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-299">This result set is also understood as Shallow Autoexists.</span></span> <span data-ttu-id="2cd2d-300">Esto se debe a que la expresión se evalúa antes de la cláusula de segmentación.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-300">This is because the expression is evaluated before the slicing clause.</span></span> <span data-ttu-id="2cd2d-301">En el ejemplo anterior, la expresión era una expresión constante a efectos de explicación del concepto.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-301">In the previous example, the expression was a constant expression for illustration purposes in order to introduce the concept.</span></span>  
  
 <span data-ttu-id="2cd2d-302">Es posible modificar el comportamiento de Autoexists en el nivel de sesión mediante la propiedad de cadena de conexión `Autoexists`.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-302">Autoexists behavior can be modified at the session level using the `Autoexists` connection string property.</span></span> <span data-ttu-id="2cd2d-303">En el ejemplo siguiente, para empezar se abre una nueva sesión y se agrega la propiedad *Autoexists=3* a la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-303">The following example begins by opening a new session and adding the *Autoexists=3* property to the connection string.</span></span> <span data-ttu-id="2cd2d-304">Se debe abrir una nueva conexión para llevar a cabo el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-304">You must open a new connection in order to do the example.</span></span> <span data-ttu-id="2cd2d-305">Una vez establecida la conexión con el valor de Autoexist, permanecerá en vigor hasta que finalice la conexión.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-305">Once the connection is established with the Autoexist setting it will remain in effect until that connection is finished.</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `//Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="2cd2d-306">El siguiente conjunto de resultados muestra el comportamiento superficial de Autoexists.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-306">The following result set now shows the shallow behavior of Autoexists.</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="2cd2d-307">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-307">**Reseller Sales Amount**</span></span>|<span data-ttu-id="2cd2d-308">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-308">**Discount Amount**</span></span>|<span data-ttu-id="2cd2d-309">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-309">**PCT Discount**</span></span>|  
|<span data-ttu-id="2cd2d-310">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-310">**Mountain-200**</span></span>|<span data-ttu-id="2cd2d-311">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-311">**$14,356,699.36**</span></span>|<span data-ttu-id="2cd2d-312">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-312">**$19,012.71**</span></span>|<span data-ttu-id="2cd2d-313">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-313">**0.13%**</span></span>|  
|<span data-ttu-id="2cd2d-314">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-314">**Mountain-100**</span></span>|<span data-ttu-id="2cd2d-315">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-315">**$8,568,958.27**</span></span>|<span data-ttu-id="2cd2d-316">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-316">**$139,393.27**</span></span>|<span data-ttu-id="2cd2d-317">**1,63 %**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-317">**1.63%**</span></span>|  
|<span data-ttu-id="2cd2d-318">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-318">**HL Mountain Frame**</span></span>|<span data-ttu-id="2cd2d-319">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-319">**$3,365,069.27**</span></span>|<span data-ttu-id="2cd2d-320">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-320">**$174.11**</span></span>|<span data-ttu-id="2cd2d-321">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="2cd2d-321">**0.01%**</span></span>|  
  
 <span data-ttu-id="2cd2d-322">El comportamiento de autoexists se puede modificar mediante el parámetro autoexists = [1 | 2 | 3] en la cadena de conexión; vea [las propiedades XMLA admitidas &#40;xmla&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) y <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> para el uso de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-322">Autoexists behavior can be modified by using the AUTOEXISTS=[1|2|3] parameter in the connection string; see [Supported XMLA Properties &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) and <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> for parameter usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd2d-323">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cd2d-323">See Also</span></span>  
 <span data-ttu-id="2cd2d-324">[Conceptos clave de &#40;MDX Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="2cd2d-324">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="2cd2d-325">[Espacio de cubo](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="2cd2d-325">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="2cd2d-326">[Tuplas](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="2cd2d-326">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="2cd2d-327">[Trabajar con miembros, tuplas y conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="2cd2d-327">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="2cd2d-328">[Totales visuales y totales no visuales](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="2cd2d-328">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="2cd2d-329">[Referencia del lenguaje MDX &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="2cd2d-329">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="2cd2d-330">Referencia de expresiones multidimensionales &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="2cd2d-330">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
