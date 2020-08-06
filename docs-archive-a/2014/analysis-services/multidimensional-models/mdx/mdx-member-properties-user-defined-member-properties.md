---
title: Propiedades de miembro definidas por el usuario (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
author: minewiskan
ms.author: owend
ms.openlocfilehash: 75e5df5a0677ee205b5517f4c7ca89a390426971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745436"
---
# <a name="user-defined-member-properties-mdx"></a><span data-ttu-id="167e8-102">Propiedades de miembro definidas por el usuario (MDX)</span><span class="sxs-lookup"><span data-stu-id="167e8-102">User-Defined Member Properties (MDX)</span></span>
  <span data-ttu-id="167e8-103">Las propiedades de miembro definidas por el usuario se pueden agregar a un nivel con nombre específico de una dimensión como relaciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="167e8-103">User-defined member properties can be added to a specific named level in a dimension as attribute relationships.</span></span> <span data-ttu-id="167e8-104">Las propiedades de miembro definidas por el usuario no se pueden agregar al nivel `(All)` de una jerarquía ni a la propia jerarquía.</span><span class="sxs-lookup"><span data-stu-id="167e8-104">User-defined member properties cannot be added to the `(All)` level of a hierarchy, or to the hierarchy itself.</span></span>  
  
## <a name="creating-user-defined-member-properties"></a><span data-ttu-id="167e8-105">Crear propiedades de miembro definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="167e8-105">Creating User-Defined Member Properties</span></span>  
 <span data-ttu-id="167e8-106">Las propiedades de miembro definidas por el usuario pueden agregarse a las dimensiones basadas en servidor o a los cubos mediante la interfaz de usuario o mediante programación:</span><span class="sxs-lookup"><span data-stu-id="167e8-106">User-defined member properties can be added to server-based dimensions or cubes either through the user interface or programmatically:</span></span>  
  
-   <span data-ttu-id="167e8-107">Para agregar propiedades de miembro definidas por el usuario en la interfaz de usuario, se usa el Diseñador de dimensiones de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="167e8-107">To add user-defined member properties through the user interface, you use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="167e8-108">Para obtener más información, vea [Definir relaciones de atributo](../attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="167e8-108">For more information, see [Define Attribute Relationships](../attribute-relationships-define.md).</span></span>  
  
-   <span data-ttu-id="167e8-109">Para agregar propiedades de miembro definidas por el usuario mediante programación, la aplicación puede utilizar objetos Analysis Manager Objects (AMO) o una combinación de XML for Analysis (XMLA) y Analysis Services Scripting Language (ASSL).</span><span class="sxs-lookup"><span data-stu-id="167e8-109">To add user-defined member properties programmatically, your application can use either Analysis Manager Objects (AMO) or a combination of XML for Analysis (XMLA) and Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="167e8-110">Para obtener más información, vea [Relaciones de atributo](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="167e8-110">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
## <a name="retrieving-user-defined-member-properties"></a><span data-ttu-id="167e8-111">Recuperar propiedades de miembro definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="167e8-111">Retrieving User-Defined Member Properties</span></span>  
 <span data-ttu-id="167e8-112">Puede recuperar las propiedades de miembro definidas por el usuario mediante la `PROPERTIES` palabra clave o la función [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="167e8-112">You can retrieve user-defined member properties using either the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="167e8-113">Usar la palabra clave PROPERTIES para recuperar propiedades de miembro definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="167e8-113">Using the PROPERTIES Keyword to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="167e8-114">La sintaxis para recuperar propiedades de miembro definidas por el usuario es similar a la utilizada para recuperar propiedades de miembro de nivel intrínsecas, como se muestra en el siguiente ejemplo de sintaxis:</span><span class="sxs-lookup"><span data-stu-id="167e8-114">The syntax that retrieves user-defined member properties is similar to that used to retrieve intrinsic level member properties, as shown in the following syntax:</span></span>  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 <span data-ttu-id="167e8-115">La palabra clave `PROPERTIES` aparece después de la expresión de conjuntos de la especificación del eje.</span><span class="sxs-lookup"><span data-stu-id="167e8-115">The `PROPERTIES` keyword appears after the set expression of the axis specification.</span></span> <span data-ttu-id="167e8-116">Por ejemplo, en la siguiente consulta MDX, la palabra clave `PROPERTIES` recupera las propiedades de miembro definidas por el usuario `List Price` y `Dealer Price` y aparece después de la expresión de conjunto que identifica los productos vendidos en el mes de enero:</span><span class="sxs-lookup"><span data-stu-id="167e8-116">For example, the following MDX query the `PROPERTIES` keyword retrieves the `List Price` and `Dealer Price` user-defined member properties and appears after the set expression that identifies the products sold in January:</span></span>  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="167e8-117">Usar la función Properties para recuperar propiedades de miembro definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="167e8-117">Using the Properties Function to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="167e8-118">También puede obtener acceso a las propiedades de miembro personalizado con la función `Properties`.</span><span class="sxs-lookup"><span data-stu-id="167e8-118">Alternatively, you can access custom member properties with the `Properties` function.</span></span> <span data-ttu-id="167e8-119">Por ejemplo, la siguiente consulta MDX utiliza la palabra clave `WITH` para crear un miembro calculado que contiene la propiedad de miembro `List Price`:</span><span class="sxs-lookup"><span data-stu-id="167e8-119">For example, the following MDX query uses the `WITH` keyword to create a calculated member consisting of the `List Price` member property:</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="167e8-120">Para obtener más información sobre la creación de miembros calculados, vea [Generar miembros calculados en MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="167e8-120">For more information about building calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="167e8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="167e8-121">See Also</span></span>  
 <span data-ttu-id="167e8-122">[Usar las propiedades de miembro &#40;&#41;MDX](mdx-member-properties.md) </span><span class="sxs-lookup"><span data-stu-id="167e8-122">[Using Member Properties &#40;MDX&#41;](mdx-member-properties.md) </span></span>  
 [<span data-ttu-id="167e8-123">Properties &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="167e8-123">Properties &#40;MDX&#41;</span></span>](/sql/mdx/properties-mdx)  
  
  
