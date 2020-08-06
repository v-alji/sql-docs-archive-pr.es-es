---
title: Crear conjuntos con nombre de ámbito de consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- query-scoped named sets [MDX]
- WITH keyword
ms.assetid: 78bc1e9a-1bc4-4a5a-ab0b-cf430c8fbfe1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6eccb4e20fca03079a04a0219b07f6411b80a433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745437"
---
# <a name="creating-query-scoped-named-sets-mdx"></a><span data-ttu-id="1726f-102">Crear conjuntos con nombre del ámbito de consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="1726f-102">Creating Query-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="1726f-103">Si un conjunto con nombre solo es necesario para una consulta de Expresiones multidimensionales (MDX) única, puede definir ese conjunto con nombre mediante la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="1726f-103">If a named set is only required for a single Multidimensional Expressions (MDX) query, you can define that named set by using the WITH keyword.</span></span> <span data-ttu-id="1726f-104">Un conjunto con nombre que se ha creado con la palabra clave WITH deja de existir cuando cesa la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="1726f-104">A named set that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="1726f-105">Como se trata en este tema, la sintaxis de la palabra clave WITH es bastante flexible, incluso ajustando el uso de funciones para definir el conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="1726f-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even accommodating the use of functions to define the named set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1726f-106">Para obtener más información sobre los conjuntos con nombre, vea [Crear conjuntos con nombre en MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1726f-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="1726f-107">Sintaxis de la palabra clave WITH</span><span class="sxs-lookup"><span data-stu-id="1726f-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="1726f-108">La siguiente sintaxis se utiliza para agregar la palabra clave WITH a una instrucción MDX SELECT:</span><span class="sxs-lookup"><span data-stu-id="1726f-108">Use the following syntax to add the WITH keyword to a MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
  
<SELECT WITH clause> ::=  
   ( SET Set_Identifier AS 'Set_Expression')  
  
```  
  
 <span data-ttu-id="1726f-109">En la sintaxis de la palabra clave WITH, el parámetro `Set_Identifier` contiene el alias del conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="1726f-109">In the syntax for the WITH keyword, the `Set_Identifier` parameter contains the alias for the named set.</span></span> <span data-ttu-id="1726f-110">El parámetro `Set_Expression` contiene la expresión de conjunto a la que hará referencia el alias del conjunto con nombre.</span><span class="sxs-lookup"><span data-stu-id="1726f-110">The `Set_Expression` parameter contains the set expression to which the named set alias refers.</span></span>  
  
## <a name="with-keyword-example"></a><span data-ttu-id="1726f-111">Ejemplo de la palabra clave WITH</span><span class="sxs-lookup"><span data-stu-id="1726f-111">WITH Keyword Example</span></span>  
 <span data-ttu-id="1726f-112">La siguiente consulta MDX examina las ventas por unidad de diversos vinos Chardonnay y Chablis en `FoodMart 2000`, la base de datos de ejemplo de Microsoft SQL Server 2000 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1726f-112">The following MDX query examines the unit sales of the various Chardonnay and Chablis wines in `FoodMart 2000`, the sample database for Microsoft SQL Server 2000 Analysis Services.</span></span> <span data-ttu-id="1726f-113">Esta consulta, a pesar de parecer bastante sencilla en cuanto al conjunto de resultados, resulta lenta y difícil de controlar a la hora del mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="1726f-113">This query, although fairly simple in terms of the result set, is lengthy and unwieldy when you have to maintenance such a query.</span></span>  
  
```  
SELECT  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]} ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
 <span data-ttu-id="1726f-114">Para facilitar el mantenimiento de la consulta de MDX anterior, puede crear un conjunto con nombre para la consulta mediante la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="1726f-114">To make the previous MDX query easier to maintain, you can create a named set for the query by using the WITH keyword.</span></span> <span data-ttu-id="1726f-115">El siguiente código muestra cómo utilizar la palabra clave WITH para crear un conjunto con nombre, `[ChardonnayChablis]`, y cómo el conjunto con nombre acorta la instrucción SELECT y facilita su mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="1726f-115">The following code shows how to use the WITH keyword to create a named set, `[ChardonnayChablis]`, and how the named set makes the SELECT statement shorter and easier to maintain.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]}  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
### <a name="using-functions-together-with-the-with-keyword"></a><span data-ttu-id="1726f-116">Usar funciones junto con la palabra clave WITH</span><span class="sxs-lookup"><span data-stu-id="1726f-116">Using Functions Together with the WITH Keyword</span></span>  
 <span data-ttu-id="1726f-117">Aunque puede definir explícitamente cada miembro de un conjunto definido, de este modo puede producir una instrucción larga.</span><span class="sxs-lookup"><span data-stu-id="1726f-117">Although you can explicitly define each member of a named set, this approach can produce a lengthy statement.</span></span> <span data-ttu-id="1726f-118">Para facilitar la creación y mantenimiento de un conjunto con nombre, puede utilizar funciones de MDX para definir los miembros.</span><span class="sxs-lookup"><span data-stu-id="1726f-118">To make the creation and maintenance of a named set easier, you can use MDX functions to define the members.</span></span>  
  
 <span data-ttu-id="1726f-119">Por ejemplo, el siguiente ejemplo de consulta MDX utiliza las funciones MDX [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx)y [Name](/sql/mdx/members-string-mdx) y la función InStr de VBA para crear el conjunto con nombre `[ChardonnayChablis]` .</span><span class="sxs-lookup"><span data-stu-id="1726f-119">For example, the following MDX query example uses the [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx), and [Name](/sql/mdx/members-string-mdx) MDX functions and the InStr VBA function to create the `[ChardonnayChablis]` named set.</span></span> <span data-ttu-id="1726f-120">Esta versión del conjunto con nombre `[ChardonnayChablis]` es el mismo que la versión definida explícitamente que se ha mostrado anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="1726f-120">This version of the `[ChardonnayChablis]` named set is the same as the explicitly defined version shown previously in this topic.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   'Filter([Product].Members, (InStr(1, [Product].CurrentMember.Name, "chardonnay") <> 0) OR (InStr(1, [Product].CurrentMember.Name, "chablis") <> 0))'  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="1726f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1726f-121">See Also</span></span>  
 <span data-ttu-id="1726f-122">[Instrucción SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="1726f-122">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="1726f-123">Crear conjuntos con nombre de ámbito de sesión &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="1726f-123">Creating Session-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-session-scoped-named-sets.md)  
  
  
