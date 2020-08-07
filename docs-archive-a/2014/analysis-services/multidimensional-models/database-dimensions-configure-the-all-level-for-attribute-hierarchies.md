---
title: Configure el nivel (All) para las jerarquías de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- All members
- IsAggregatable property
- topmost levels [Analysis Services]
- (All) levels
- AttributeAllMemberName property
- levels [Analysis Services]
- members [Analysis Services], All
- AllMemberName property
ms.assetid: 0cb35e6f-b10f-483d-b893-78f6ca3979fd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9874a8c8a6861bc7d9e44271b089e8af3a4c0ae2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745460"
---
# <a name="configure-the-all-level-for-attribute-hierarchies"></a><span data-ttu-id="88e2a-102">Configurar el nivel (All) para las jerarquías de atributo</span><span class="sxs-lookup"><span data-stu-id="88e2a-102">Configure the (All) Level for Attribute Hierarchies</span></span>
  <span data-ttu-id="88e2a-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , el nivel (All) es un nivel opcional generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="88e2a-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the (All) level is an optional, system-generated level.</span></span> <span data-ttu-id="88e2a-104">Contiene un único miembro cuyo valor es la agregación de los valores de todos los miembros del nivel inmediatamente subordinado.</span><span class="sxs-lookup"><span data-stu-id="88e2a-104">It contains only one member whose value is the aggregation of the values of all members in the immediately subordinate level.</span></span> <span data-ttu-id="88e2a-105">Este miembro se denomina All.</span><span class="sxs-lookup"><span data-stu-id="88e2a-105">This member is called the All member.</span></span> <span data-ttu-id="88e2a-106">Se trata de un miembro generado por el sistema que no se encuentra en la tabla de dimensión.</span><span class="sxs-lookup"><span data-stu-id="88e2a-106">It is a system-generated member that is not contained in the dimension table.</span></span> <span data-ttu-id="88e2a-107">Puesto que el miembro del nivel (All) está en la parte superior de la jerarquía, el valor del miembro es la agregación consolidada de los valores de todos los miembros de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="88e2a-107">Because the member in the (All) level is at the top of the hierarchy, the member's value is the consolidated aggregation of the values of all members in the hierarchy.</span></span> <span data-ttu-id="88e2a-108">El miembro All actúa a menudo como miembro predeterminado de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="88e2a-108">The All member often serves as the default member of a hierarchy.</span></span>  
  
 <span data-ttu-id="88e2a-109">La presencia de un nivel (All) en una jerarquía de atributo depende del valor de la propiedad `IsAggregatable` para el atributo. La presencia de un nivel (All) en una jerarquía definida por el usuario depende de la propiedad `IsAggregatable` del atributo en el nivel superior de la jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="88e2a-109">The presence of an (All) level in an attribute hierarchy depends on the `IsAggregatable` property setting for the attribute and the presence of an (All) level in a user-defined hierarchy depends on the `IsAggregatable` property of the attribute at the top-most level of user-defined hierarchy.</span></span> <span data-ttu-id="88e2a-110">Si la propiedad `IsAggregatable` está establecida en `True`, existirá un nivel (All).</span><span class="sxs-lookup"><span data-stu-id="88e2a-110">If the `IsAggregatable` property is set to `True`, an (All) level will exist.</span></span> <span data-ttu-id="88e2a-111">Una jerarquía no tendrá nivel (All) si la propiedad `IsAggregatable` está establecida en `False`.</span><span class="sxs-lookup"><span data-stu-id="88e2a-111">A hierarchy has no (All) level if the `IsAggregatable` property is set to `False`.</span></span>  
  
## <a name="establishing-the-topmost-level"></a><span data-ttu-id="88e2a-112">Establecer el nivel superior</span><span class="sxs-lookup"><span data-stu-id="88e2a-112">Establishing the Topmost Level</span></span>  
 <span data-ttu-id="88e2a-113">Si la propiedad `IsAggregatable` está establecida en `False` en el atributo de origen de un nivel de la jerarquía, por encima de dicho nivel no aparecerá ningún nivel que se pueda agregar en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="88e2a-113">If the `IsAggregatable` property is set to `False` on the source attribute of a level in a hierarchy, then no aggregatable level can appear in the hierarchy above that level.</span></span> <span data-ttu-id="88e2a-114">Un nivel que no se pueda agregar debe ser el nivel superior de cualquier jerarquía o la propiedad `IsAggregatable` de los atributos de origen de los niveles situados por encima de él deben también establecerse en `False`.</span><span class="sxs-lookup"><span data-stu-id="88e2a-114">A non-aggregatable level must be the topmost level of any hierarchy or the `IsAggregatable` property of the source attributes for any levels above it must also be set to `False`.</span></span>  
  
## <a name="all-member-and-all-level"></a><span data-ttu-id="88e2a-115">Miembro All y nivel (All)</span><span class="sxs-lookup"><span data-stu-id="88e2a-115">All Member and (All) Level</span></span>  
 <span data-ttu-id="88e2a-116">El único miembro del nivel (All) se llama All.</span><span class="sxs-lookup"><span data-stu-id="88e2a-116">The single member of the (All) level is called the All member.</span></span> <span data-ttu-id="88e2a-117">La `AttributeAllMemberName` propiedad de una dimensión especifica el nombre del miembro All para los atributos de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="88e2a-117">The `AttributeAllMemberName`property on a dimension specifies the name of the All member for attributes in a dimension.</span></span> <span data-ttu-id="88e2a-118">La propiedad `AllMemberName` en una jerarquía especifica el nombre del miembro All de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="88e2a-118">The `AllMemberName` property on a hierarchy specifies the name of the All member for the hierarchy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e2a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88e2a-119">See Also</span></span>  
 [<span data-ttu-id="88e2a-120">Definir un miembro predeterminado</span><span class="sxs-lookup"><span data-stu-id="88e2a-120">Define a Default Member</span></span>](attribute-properties-define-a-default-member.md)  
  
  
