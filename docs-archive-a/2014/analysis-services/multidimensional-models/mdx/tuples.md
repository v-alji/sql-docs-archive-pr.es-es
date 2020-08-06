---
title: Tuplas | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 35b629ae-b1ef-44b1-b556-96956aeb56e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: c39d03d60cb66f3b2e26b2e660bd85f4e5e9d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748328"
---
# <a name="tuples"></a><span data-ttu-id="66ac1-102">Tuplas</span><span class="sxs-lookup"><span data-stu-id="66ac1-102">Tuples</span></span>
  <span data-ttu-id="66ac1-103">Una tupla identifica de forma inequívoca un segmento de datos de un cubo.</span><span class="sxs-lookup"><span data-stu-id="66ac1-103">A tuple uniquely identifies a slice of data from a cube.</span></span> <span data-ttu-id="66ac1-104">Una combinación de miembros de dimensión forma la tupla, siempre que no haya dos o más miembros que pertenecen a la misma jerarquía.</span><span class="sxs-lookup"><span data-stu-id="66ac1-104">The tuple is formed by a combination of dimension members, as long as there are no two or more members that belong to the same hierarchy.</span></span>  
  
## <a name="implicit-or-default-attribute-members-in-a-tuple"></a><span data-ttu-id="66ac1-105">Miembros de atributo implícitos o predeterminados en una tupla</span><span class="sxs-lookup"><span data-stu-id="66ac1-105">Implicit or default attribute members in a tuple</span></span>  
 <span data-ttu-id="66ac1-106">Al definir una tupla en una consulta o expresión MDX, no es necesario incluir explícitamente el miembro de atributo de cada jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="66ac1-106">When defining a tuple in an MDX query or expression, you do not need to explicitly include the attribute member from every attribute hierarchy.</span></span> <span data-ttu-id="66ac1-107">Si no se incluye de manera explicita un miembro de una jerarquía de atributo en una consulta o expresión, el miembro predeterminado de esa jerarquía de atributo es el miembro de atributo implícitamente incluido en la tupla.</span><span class="sxs-lookup"><span data-stu-id="66ac1-107">If a member from an attribute hierarchy is not explicitly included in a query or an expression, the default member for that attribute hierarchy is the attribute member implicitly included in the tuple.</span></span> <span data-ttu-id="66ac1-108">A menos que se lo defina explícitamente de otra manera en un cubo, el miembro predeterminado de cada jerarquía de atributo es el miembro (All), si existe.</span><span class="sxs-lookup"><span data-stu-id="66ac1-108">Unless otherwise explicitly defined in a cube, the default member for every attribute hierarchy is the (All) member, if an (All) member exists.</span></span> <span data-ttu-id="66ac1-109">Si no existe un miembro (All) dentro de una jerarquía de atributo, el miembro predeterminado es un miembro del nivel superior de la jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="66ac1-109">If an (All) member does not exist within an attribute hierarchy, the default member is a member of the attribute hierarchy's top level.</span></span> <span data-ttu-id="66ac1-110">La medida predeterminada es la primera medida especificada en el cubo, a menos que se defina explícitamente una medida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="66ac1-110">The default measure is the first measure specified in the cube, unless a default measure is explicitly defined.</span></span> <span data-ttu-id="66ac1-111">Para más información, vea [Definir un miembro predeterminado](../attribute-properties-define-a-default-member.md) y [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span><span class="sxs-lookup"><span data-stu-id="66ac1-111">For more information, see [Define a Default Member](../attribute-properties-define-a-default-member.md) and [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span></span>  
  
 <span data-ttu-id="66ac1-112">Por ejemplo, la siguiente tupla identifica a una celda única de la base de datos Adventure Works al definir explícitamente un solo miembro de la dimensión de medidas.</span><span class="sxs-lookup"><span data-stu-id="66ac1-112">For example, the following tuple identifies a single cell in the Adventure Works database by explicitly defining only a single member of the Measures dimension.</span></span>  
  
```  
(Measures.[Reseller Sales Amount])  
```  
  
 <span data-ttu-id="66ac1-113">El ejemplo anterior identifica de forma exclusiva la celda que consta del miembro Reseller Sales Amount de la dimensión de medidas y el miembro predeterminado de cada jerarquía de atributo del cubo.</span><span class="sxs-lookup"><span data-stu-id="66ac1-113">The previous example uniquely identifies the cell consisting of the Reseller Sales Amount member from the Measures dimension and the default member from every attribute hierarchy in the cube.</span></span> <span data-ttu-id="66ac1-114">El miembro predeterminado es el miembro (All) de cada jerarquía de atributo que no sea la jerarquía de atributo Destination Currency.</span><span class="sxs-lookup"><span data-stu-id="66ac1-114">The default member is the (All) member for every attribute hierarchy other than the Destination Currency attribute hierarchy.</span></span> <span data-ttu-id="66ac1-115">El miembro predeterminado de la jerarquía Destination Currency es US Dollar (este miembro predeterminado se define en el script MDX del cubo Adventure Works).</span><span class="sxs-lookup"><span data-stu-id="66ac1-115">The default member for the Destination Currency hierarchy is the US Dollar member (this default member is defined in the MDX script for the Adventure Works cube).</span></span>  
  
 <span data-ttu-id="66ac1-116">La consulta siguiente devuelve el valor de la celda a la que se hace referencia en la tupla especificada en el ejemplo anterior ($80.450,596,98).</span><span class="sxs-lookup"><span data-stu-id="66ac1-116">The following query returns the value for the cell referenced by the tuple specified in the previous example, ($80,450.596.98).</span></span>  
  
```  
SELECT   
Measures.[Reseller Sales Amount] ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="66ac1-117">Al especificar un eje para un conjunto (en este caso compuesto por una sola tupla) de una consulta, debe comenzar por especificar un conjunto para el eje de columna antes de especificar un conjunto para el eje de fila.</span><span class="sxs-lookup"><span data-stu-id="66ac1-117">When you specify an axis for a set (in this case composed of a single tuple) in a query, you must begin by specifying a set for the column axis before specifying a set for the row axis.</span></span> <span data-ttu-id="66ac1-118">También se puede hacer referencia al eje de columna como *eje(0)* o sencillamente *0*.</span><span class="sxs-lookup"><span data-stu-id="66ac1-118">The column axis can also be referred to as *axis(0)* or simply *0*.</span></span> <span data-ttu-id="66ac1-119">Para más información sobre las consultas MDX, vea [Consulta de MDX básica &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="66ac1-119">For more information about MDX queries, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
### <a name="tuples-as-values-or-member-references"></a><span data-ttu-id="66ac1-120">Tuplas como valores o referencias de miembro</span><span class="sxs-lookup"><span data-stu-id="66ac1-120">Tuples as values or member references</span></span>  
 <span data-ttu-id="66ac1-121">Puede utilizar una tupla de una consulta para devolver el valor de la celda a la que se hace referencia en la tupla, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="66ac1-121">You can use a tuple in a query to return the value in the cell that is referenced by the tuple, as in the previous example.</span></span> <span data-ttu-id="66ac1-122">De lo contrario, puede utilizar una tupla en una expresión para hacer referencia de forma explícita a los miembros especificados en la tupla.</span><span class="sxs-lookup"><span data-stu-id="66ac1-122">Or you can use a tuple in an expression to explicitly refer to the members specified in the tuple.</span></span> <span data-ttu-id="66ac1-123">La consulta o la expresión pueden utilizar funciones que devuelvan o consuman tuplas.</span><span class="sxs-lookup"><span data-stu-id="66ac1-123">The query or the expression can utilize functions that either return or consume tuples.</span></span> <span data-ttu-id="66ac1-124">Una tupla puede utilizarse para hacer referencia al valor de la celda que especifica la tupla o para especificar una combinación de miembros cuando se utilicen en una función.</span><span class="sxs-lookup"><span data-stu-id="66ac1-124">A tuple can be used to either refer to the value of the cell that the tuple specifies, or to specify a combination of members when utilized in a function.</span></span>  
  
### <a name="tuple-dimensionality"></a><span data-ttu-id="66ac1-125">Dimensionalidad de tuplas</span><span class="sxs-lookup"><span data-stu-id="66ac1-125">Tuple dimensionality</span></span>  
 <span data-ttu-id="66ac1-126">La *dimensionalidad* de una tupla hace referencia a la secuencia o el orden de los miembros de la tupla.</span><span class="sxs-lookup"><span data-stu-id="66ac1-126">The *dimensionality* of a tuple refers to the sequence or order of the members in the tuple.</span></span> <span data-ttu-id="66ac1-127">Debido a que los miembros implícitos siempre aparecen en el mismo orden, se piensa en la dimensionalidad generalmente en relación con los miembros explícitamente definidos de la tupla.</span><span class="sxs-lookup"><span data-stu-id="66ac1-127">Since the implicit members always occur in the same order, dimensionality is most often thought of in terms of the explicitly defined members of the tuple.</span></span> <span data-ttu-id="66ac1-128">El orden de los miembros de la tupla es importante al definir un conjunto de tuplas.</span><span class="sxs-lookup"><span data-stu-id="66ac1-128">The ordering of the members of the tuple is important when you define a set of tuples.</span></span> <span data-ttu-id="66ac1-129">El ejemplo siguiente incluye dos miembros de una tupla en el eje de columna.</span><span class="sxs-lookup"><span data-stu-id="66ac1-129">The following example includes two members in a tuple on the column axis.</span></span>  
  
```  
SELECT   
([Measures].[Reseller Sales Amount],[Date].[Calendar Year].[CY 2004]) ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="66ac1-130">Al especificar explícitamente un miembro de una tupla de más de una dimensión, debe incluir toda la tupla entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="66ac1-130">When you explicitly specify a member in a tuple from more than one dimension, you must include the entire tuple in parentheses.</span></span> <span data-ttu-id="66ac1-131">Cuando solo se especifica un miembro de una tupla, los paréntesis son opcionales.</span><span class="sxs-lookup"><span data-stu-id="66ac1-131">When only specifying a single member in a tuple, parentheses are optional.</span></span>  
  
 <span data-ttu-id="66ac1-132">La tupla de la consulta del ejemplo anterior especifica la devolución de la celda del cubo en la intersección de la medida Reseller Sales Amount de la dimensión de medidas y el miembro CY 2004 de la jerarquía de atributo Calendar Year de la dimensión Date.</span><span class="sxs-lookup"><span data-stu-id="66ac1-132">The tuple in the query in the previous example specifies the return of the cube cell at the intersection of the Reseller Sales Amount Measure of the Measures dimension and the CY 2004 member of the Calendar Year attribute hierarchy in the Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66ac1-133">Se puede hacer referencia a un miembro de atributo por su nombre de miembro o su clave de miembro.</span><span class="sxs-lookup"><span data-stu-id="66ac1-133">An attribute member can be referred by either its member name or its member key.</span></span> <span data-ttu-id="66ac1-134">En el ejemplo anterior, se podía reemplazar la referencia a [CY 2004] con &[2004].</span><span class="sxs-lookup"><span data-stu-id="66ac1-134">In the previous example, you could replace the reference to [CY 2004] with &[2004].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ac1-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66ac1-135">See Also</span></span>  
 <span data-ttu-id="66ac1-136">[Conceptos clave de &#40;MDX Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="66ac1-136">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="66ac1-137">[Espacio de cubo](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="66ac1-137">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="66ac1-138">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="66ac1-138">[Autoexists](autoexists.md) </span></span>  
 [<span data-ttu-id="66ac1-139">Trabajar con miembros, tuplas y conjuntos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="66ac1-139">Working with Members, Tuples, and Sets &#40;MDX&#41;</span></span>](working-with-members-tuples-and-sets-mdx.md)  
  
  
