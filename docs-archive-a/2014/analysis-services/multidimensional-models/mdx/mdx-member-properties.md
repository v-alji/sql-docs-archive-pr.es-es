---
title: Usar las propiedades de miembro (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745435"
---
# <a name="using-member-properties-mdx"></a><span data-ttu-id="a6c03-102">Usar las propiedades de miembro (MDX)</span><span class="sxs-lookup"><span data-stu-id="a6c03-102">Using Member Properties (MDX)</span></span>
  <span data-ttu-id="a6c03-103">Las propiedades de miembro cubren la información básica de todos los miembros de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="a6c03-103">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="a6c03-104">Esta información básica incluye el nombre del miembro, el nivel primario, el número de secundarios, etc.</span><span class="sxs-lookup"><span data-stu-id="a6c03-104">This basic information includes the member name, parent level, the number of children, and so on.</span></span> <span data-ttu-id="a6c03-105">Las propiedades de miembro están disponibles para todos los miembros de un determinado nivel.</span><span class="sxs-lookup"><span data-stu-id="a6c03-105">Member properties are available for all members at a given level.</span></span> <span data-ttu-id="a6c03-106">En términos de organización, las propiedades de miembro se tratan como datos organizados dimensionalmente, almacenados en una sola dimensión.</span><span class="sxs-lookup"><span data-stu-id="a6c03-106">In terms of organization, member properties are treated as dimensionally organized data, stored on a single dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6c03-107">En [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], las propiedades de miembro se conocen como relaciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="a6c03-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], member properties are know as attribute relationships.</span></span> <span data-ttu-id="a6c03-108">Para obtener más información, vea [Relaciones de atributo](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="a6c03-108">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
 <span data-ttu-id="a6c03-109">Las propiedades de miembro pueden ser *intrínsecas* o *personalizadas*:</span><span class="sxs-lookup"><span data-stu-id="a6c03-109">Member properties are either *intrinsic* or *custom*:</span></span>  
  
 <span data-ttu-id="a6c03-110">Propiedades de miembro intrínsecas</span><span class="sxs-lookup"><span data-stu-id="a6c03-110">Intrinsic member properties</span></span>  
 <span data-ttu-id="a6c03-111">Todos los miembros admiten propiedades de miembro intrínsecas, como el valor con formato de un miembro, mientras que las dimensiones y los niveles proporcionan propiedades de miembro intrínsecas adicionales de nivel y dimensión, como el Id. de un miembro.</span><span class="sxs-lookup"><span data-stu-id="a6c03-111">All members support intrinsic member properties, such as the formatted value of a member, while dimensions and levels supply additional intrinsic dimension and level member properties, such as the ID of a member.</span></span>  
  
 <span data-ttu-id="a6c03-112">Para obtener más información, vea [Propiedades de miembro intrínsecas &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a6c03-112">For more information, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
 <span data-ttu-id="a6c03-113">Propiedades de miembro definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="a6c03-113">User-defined member properties</span></span>  
 <span data-ttu-id="a6c03-114">Los miembros suelen tener propiedades adicionales asociadas.</span><span class="sxs-lookup"><span data-stu-id="a6c03-114">Members often have additional properties associated with them.</span></span> <span data-ttu-id="a6c03-115">Por ejemplo, el nivel Products puede ofrecer las propiedades SKU, SRP, Weight y Volume para cada producto.</span><span class="sxs-lookup"><span data-stu-id="a6c03-115">For example, the Products level may offer the SKU, SRP, Weight, and Volume properties for each product.</span></span> <span data-ttu-id="a6c03-116">Estas propiedades no son miembros, pero contienen información adicional sobre los miembros del nivel Products.</span><span class="sxs-lookup"><span data-stu-id="a6c03-116">These properties are not members, but contain additional information about members at the Products level.</span></span>  
  
 <span data-ttu-id="a6c03-117">Para obtener más información, vea [Propiedades de miembro definidas por el usuario &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a6c03-117">For more information, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
 <span data-ttu-id="a6c03-118">Las propiedades de miembro intrínsecas y definidas por el usuario se pueden recuperar mediante el uso de la `PROPERTIES` palabra clave o la función [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="a6c03-118">Both intrinsic and user-defined member properties can be retrieved through the use of the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
## <a name="using-the-properties-keyword"></a><span data-ttu-id="a6c03-119">Usar la palabra clave PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="a6c03-119">Using the PROPERTIES Keyword</span></span>  
 <span data-ttu-id="a6c03-120">La palabra clave `PROPERTIES` especifica las propiedades de miembro que deben utilizarse para una dimensión de eje determinada.</span><span class="sxs-lookup"><span data-stu-id="a6c03-120">The `PROPERTIES` keyword specifies the member properties that are to be used for a given axis dimension.</span></span> <span data-ttu-id="a6c03-121">La `PROPERTIES` palabra clave está incluida en la `<axis specification>` cláusula de la instrucción MDX [Select](/sql/mdx/mdx-data-manipulation-select) :</span><span class="sxs-lookup"><span data-stu-id="a6c03-121">The `PROPERTIES` keyword is buried within the `<axis specification>` clause of the MDX [SELECT](/sql/mdx/mdx-data-manipulation-select) statement:</span></span>  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 <span data-ttu-id="a6c03-122">La cláusula `<axis_specification>` incluye una cláusula `<dim_props>` opcional, como se ilustra en la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a6c03-122">The `<axis_specification>` clause includes an optional `<dim_props>` clause, as shown in the following syntax:</span></span>  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="a6c03-123">Para obtener más información sobre los valores `<set>` y `<axis_name>`, vea [Especificar el contenido de un eje de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="a6c03-123">For more information about the `<set>` and `<axis_name>` values, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
 <span data-ttu-id="a6c03-124">La cláusula `<dim_props>` permite realizar consultas sobre propiedades de dimensiones, niveles y miembros mediante la palabra clave `PROPERTIES`.</span><span class="sxs-lookup"><span data-stu-id="a6c03-124">The `<dim_props>` clause lets you query dimension, level, and member properties using the `PROPERTIES` keyword.</span></span> <span data-ttu-id="a6c03-125">En la siguiente sintaxis se muestra el formato de la cláusula `<dim_props>` :</span><span class="sxs-lookup"><span data-stu-id="a6c03-125">The following syntax shows the formatting of the `<dim_props>` clause:</span></span>  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 <span data-ttu-id="a6c03-126">El análisis detallado de la sintaxis `<property>` varía según la propiedad sobre la que se efectúe la consulta:</span><span class="sxs-lookup"><span data-stu-id="a6c03-126">The breakdown of the `<property>` syntax varies depending on the property that you are querying:</span></span>  
  
-   <span data-ttu-id="a6c03-127">Las propiedades de miembro intrínsecas contextuales deben ir precedidas del nombre de la dimensión o el nivel.</span><span class="sxs-lookup"><span data-stu-id="a6c03-127">Context sensitive intrinsic member properties must be preceded with the name of the dimension or level.</span></span> <span data-ttu-id="a6c03-128">Sin embargo, el nombre de las propiedades de miembro intrínsecas no contextuales no puede completarse con el de la dimensión o el nivel.</span><span class="sxs-lookup"><span data-stu-id="a6c03-128">However, non-context sensitive intrinsic member properties cannot be qualified by the dimension or level name.</span></span> <span data-ttu-id="a6c03-129">Para obtener más información sobre cómo usar la `PROPERTIES` palabra clave con las propiedades de miembro intrínsecas, vea [propiedades de miembro intrínsecas &#40;&#41;MDX ](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a6c03-129">For more information about how to use the `PROPERTIES` keyword with intrinsic member properties, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
-   <span data-ttu-id="a6c03-130">Las propiedades de miembro definidas por el usuario deben ir precedidas por el nombre del nivel en el que residen.</span><span class="sxs-lookup"><span data-stu-id="a6c03-130">User-defined member properties should be preceded by the name of the level in which they reside.</span></span> <span data-ttu-id="a6c03-131">Para obtener más información sobre cómo usar la `PROPERTIES` palabra clave con las propiedades de miembro definidas por el usuario, vea [propiedades de miembro definidas por el usuario &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a6c03-131">For more information about how to use the `PROPERTIES` keyword with user-defined member properties, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c03-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6c03-132">See Also</span></span>  
 [<span data-ttu-id="a6c03-133">Crear y usar los valores de propiedad &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a6c03-133">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)  
  
  
