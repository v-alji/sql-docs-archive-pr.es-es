---
title: Atributos en jerarquías de elementos primarios y secundarios | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data members [Analysis Services]
- nonleaf members
- MembersWithDataCaption property
- members [Analysis Services]
- members [Analysis Services], data
- leaf members
- parent-child dimensions [Analysis Services]
- MembersWithData property
ms.assetid: 249971cc-4bcd-44f1-8241-bdacc04d3d38
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c4a7e8ba43ac8ede0bd60409f84a6fa233ce182
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745433"
---
# <a name="attributes-in-parent-child-hierarchies"></a><span data-ttu-id="8055c-102">Atributos en las jerarquías de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="8055c-102">Attributes in Parent-Child Hierarchies</span></span>
  <span data-ttu-id="8055c-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , normalmente se realiza una suposición general sobre el contenido de los miembros de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="8055c-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a general assumption is usually made about the content of members in a dimension.</span></span> <span data-ttu-id="8055c-104">Los miembros hoja contienen datos derivados directamente de los orígenes de datos subyacentes; los miembros no hoja contienen datos derivados de agregaciones realizadas en miembros secundarios.</span><span class="sxs-lookup"><span data-stu-id="8055c-104">Leaf members contain data derived directly from underlying data sources; nonleaf members contain data derived from aggregations performed on child members.</span></span>  
  
 <span data-ttu-id="8055c-105">No obstante, en una jerarquía de elementos primarios y secundarios, algunos miembros no hoja también pueden tener datos derivados de orígenes de datos subyacentes, además de los datos agregados de miembros secundarios.</span><span class="sxs-lookup"><span data-stu-id="8055c-105">In a parent-child hierarchy, however, some nonleaf members may also have data derived from underlying data sources, in addition to data aggregated from child members.</span></span> <span data-ttu-id="8055c-106">Para estos miembros no hoja de una jerarquía de elementos primarios y secundarios, se pueden crear miembros secundarios especiales generados por el sistema que contengan los datos de la tabla de hechos subyacente.</span><span class="sxs-lookup"><span data-stu-id="8055c-106">For these nonleaf members in a parent-child hierarchy, special system-generated child members are created that contain the underlying fact table data.</span></span> <span data-ttu-id="8055c-107">Denominados *miembros de datos*, contienen un valor asociado directamente a un miembro no hoja que es independiente del valor de resumen calculado a partir de los descendientes del miembro no hoja.</span><span class="sxs-lookup"><span data-stu-id="8055c-107">Referred to as *data members*, they contain a value directly associated with a nonleaf member that is independent of the summary value calculated from the descendants of the nonleaf member.</span></span>  
  
 <span data-ttu-id="8055c-108">Los miembros de datos se encuentran disponibles solo en dimensiones con jerarquías de elementos primarios y secundarios, y solo son visibles si lo tienen permitido por su atributo primario.</span><span class="sxs-lookup"><span data-stu-id="8055c-108">Data members are available only to dimensions with parent-child hierarchies, and are visible only if allowed by the parent attribute.</span></span> <span data-ttu-id="8055c-109">Se puede utilizar el Diseñador de dimensiones para controlar la visibilidad de los miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="8055c-109">You can use Dimension Designer to control the visibility of data members.</span></span> <span data-ttu-id="8055c-110">Para exponer los miembros de datos, establezca la propiedad `MembersWithData` del atributo primario en `NonLeafDataVisible.`. Para ocultar los miembros de datos contenidos en el atributo primario, establezca la propiedad `MembersWithData` del atributo primario en `NonLeafDataHidden`.</span><span class="sxs-lookup"><span data-stu-id="8055c-110">To expose data members, set the `MembersWithData` property for the parent attribute to `NonLeafDataVisible.` To hide data members contained by the parent attribute, set the `MembersWithData` property on the parent attribute to `NonLeafDataHidden`.</span></span>  
  
 <span data-ttu-id="8055c-111">Este valor no reemplaza el comportamiento de agregación normal para los miembros no hoja; el miembro de datos siempre se incluye como miembro secundario para fines de agregación.</span><span class="sxs-lookup"><span data-stu-id="8055c-111">This setting does not override the normal aggregation behavior for nonleaf members; the data member is always included as a child member for the purposes of aggregation.</span></span> <span data-ttu-id="8055c-112">Sin embargo, se puede utilizar una fórmula de resumen personalizado para reemplazar el comportamiento normal de agregación.</span><span class="sxs-lookup"><span data-stu-id="8055c-112">However, a custom rollup formula can be used to override the normal aggregation behavior.</span></span> <span data-ttu-id="8055c-113">La función [DataMember](/sql/mdx/datamember-mdx) de expresiones multidimensionales (MDX) ofrece la posibilidad de obtener acceso al valor del miembro de datos asociado independientemente del valor de la `MembersWithData` propiedad.</span><span class="sxs-lookup"><span data-stu-id="8055c-113">The Multidimensional Expressions (MDX) [DataMember](/sql/mdx/datamember-mdx) function gives you the ability to access the value of the associated data member regardless of the value of the `MembersWithData` property.</span></span>  
  
 <span data-ttu-id="8055c-114">La propiedad `MembersWithDataCaption` del atributo primario ofrece a [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] la plantilla de nomenclatura usada para generar nombres de miembro para miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="8055c-114">The `MembersWithDataCaption` property of the parent attribute provides [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] with the naming template used to generate member names for data members.</span></span>  
  
## <a name="using-data-members"></a><span data-ttu-id="8055c-115">Usar miembros de datos</span><span class="sxs-lookup"><span data-stu-id="8055c-115">Using Data Members</span></span>  
 <span data-ttu-id="8055c-116">Los miembros de datos son de utilidad al agregar medidas a dimensiones organizativas que tienen jerarquías de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="8055c-116">Data members are useful when aggregating measures along organizational dimensions that have parent-child hierarchies.</span></span> <span data-ttu-id="8055c-117">Por ejemplo, en el diagrama siguiente se muestra una dimensión con tres niveles que representa el volumen de ventas brutas de productos.</span><span class="sxs-lookup"><span data-stu-id="8055c-117">For example, the following diagram shows a dimension that has three levels, representing the gross sales volume of products.</span></span> <span data-ttu-id="8055c-118">El primer nivel muestra el volumen de ventas brutas de todos los agentes de ventas.</span><span class="sxs-lookup"><span data-stu-id="8055c-118">The first level shows the gross sales volume for all salespersons.</span></span> <span data-ttu-id="8055c-119">El segundo nivel contiene el volumen de ventas brutas de todo el personal de ventas por director de ventas y el tercer nivel contiene el volumen de ventas brutas de todo el personal de ventas por vendedor.</span><span class="sxs-lookup"><span data-stu-id="8055c-119">The second level contains the gross sales volume for all sales staff grouped by sales manager, and the third level contains the gross sales volume for all sales staff grouped by salesperson.</span></span>  
  
 <span data-ttu-id="8055c-120">![Dimensión del volumen de ventas brutas con tres niveles](../media/agdatamember1.gif "Dimensión del volumen de ventas brutas con tres niveles")</span><span class="sxs-lookup"><span data-stu-id="8055c-120">![Gross sales volume dimension with three levels](../media/agdatamember1.gif "Gross sales volume dimension with three levels")</span></span>  
  
 <span data-ttu-id="8055c-121">Habitualmente, el valor del miembro Sales Manager 1 se deriva al agregar los valores de los miembros Salesperson 1 y Salesperson 2.</span><span class="sxs-lookup"><span data-stu-id="8055c-121">Ordinarily, the value of the Sales Manager 1 member would be derived by aggregating the values of the Salesperson 1 and Salesperson 2 members.</span></span> <span data-ttu-id="8055c-122">Sin embargo, como Sales Manager 1 también puede vender productos, este miembro también puede contener datos derivados de la tabla de hechos, ya que puede haber ventas brutas asociadas a Sales Manager 1.</span><span class="sxs-lookup"><span data-stu-id="8055c-122">However, because Sales Manager 1 also can sell products, that member may also contain data derived from the fact table, because there may be gross sales associated with Sales Manager 1.</span></span>  
  
 <span data-ttu-id="8055c-123">Además, la comisión individual de cada miembro del personal de ventas puede variar.</span><span class="sxs-lookup"><span data-stu-id="8055c-123">Moreover, the individual commissions for each sales staff member can vary.</span></span> <span data-ttu-id="8055c-124">En este caso, se utilizan dos escalas diferentes para calcular la comisión de las ventas brutas individuales de los directores de ventas, frente a las ventas brutas totales generadas por sus vendedores.</span><span class="sxs-lookup"><span data-stu-id="8055c-124">In this case, two different scales are used to compute commissions for the individual gross sales of the sales managers, as opposed to the total of gross sales generated by their salespersons.</span></span> <span data-ttu-id="8055c-125">Por lo tanto, es importante que los miembros no hoja puedan tener acceso a los datos de la tabla de hechos subyacente.</span><span class="sxs-lookup"><span data-stu-id="8055c-125">Therefore, it is important to be able to access the underlying fact table data for nonleaf members.</span></span> <span data-ttu-id="8055c-126">Se puede utilizar la función `DataMember` de MDX para recuperar el volumen de ventas brutas del miembro Sales Manager 1 y una expresión de resumen personalizado para excluir el miembro de datos del valor agregado del miembro Sales Manager 1, lo que proporciona el volumen de ventas brutas de los vendedores asociados a ese miembro.</span><span class="sxs-lookup"><span data-stu-id="8055c-126">The MDX `DataMember` function can be used to retrieve the individual gross sales volume of the Sales Manager 1 member, and a custom rollup expression can be used to exclude the data member from the aggregated value of the Sales Manager 1 member, providing the gross sales volume of the salespersons associated with that member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8055c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8055c-127">See Also</span></span>  
 <span data-ttu-id="8055c-128">[Referencia de propiedades de atributo de dimensión](dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8055c-128">[Dimension Attribute Properties Reference](dimension-attribute-properties-reference.md) </span></span>  
 [<span data-ttu-id="8055c-129">Jerarquía de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="8055c-129">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  