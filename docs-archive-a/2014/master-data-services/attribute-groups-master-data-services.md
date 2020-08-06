---
title: Grupos de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services]
- attribute groups [Master Data Services], about attribute groups
ms.assetid: 648b3d0b-e15a-45f9-8292-3a54a072e62c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 390b402489799639e66a44992da1e20b0d0c1bbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673757"
---
# <a name="attribute-groups-master-data-services"></a><span data-ttu-id="7a668-102">Grupos de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7a668-102">Attribute Groups (Master Data Services)</span></span>
  <span data-ttu-id="7a668-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], los grupos de atributos ayudan a organizar los atributos de una entidad.</span><span class="sxs-lookup"><span data-stu-id="7a668-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], attribute groups help organize attributes in an entity.</span></span> <span data-ttu-id="7a668-104">Cuando una entidad tiene muchos atributos, los grupos de atributos mejoran la forma en que se muestra una entidad en la aplicación web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a668-104">When an entity has lots of attributes, attribute groups improve the way an entity is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
## <a name="how-attribute-groups-change-the-display"></a><span data-ttu-id="7a668-105">Cómo cambian la presentación los grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="7a668-105">How Attribute Groups Change the Display</span></span>  
 <span data-ttu-id="7a668-106">Los grupos de atributos se muestran como pestañas encima de la cuadrícula en el área funcional **Explorador** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a668-106">Attribute groups are displayed as tabs above the grid in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="7a668-107">Cuando una entidad tiene un gran número de atributos y ve esa entidad en una cuadrícula en el **Explorador**, debe desplazar hacia la derecha para ver todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="7a668-107">When an entity has a large number of attributes and you view that entity in a grid in **Explorer**, you must scroll to the right to view all of the attributes.</span></span> <span data-ttu-id="7a668-108">Para evitar este desplazamiento, puede crear grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="7a668-108">To prevent this scrolling, you can create attribute groups.</span></span>  
  
-   <span data-ttu-id="7a668-109">Los grupos de atributos siempre incluyen los atributos Name y Code.</span><span class="sxs-lookup"><span data-stu-id="7a668-109">Attribute groups always include the Name and Code attributes.</span></span>  
  
-   <span data-ttu-id="7a668-110">Cada atributo de una entidad puede pertenecer a uno o más grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="7a668-110">Each attribute for an entity can belong to one or more attribute groups.</span></span>  
  
-   <span data-ttu-id="7a668-111">Todos los atributos se incluyen automáticamente en la pestaña **Todos los atributos** en el **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="7a668-111">All attributes are automatically included on the **All Attributes** tab in **Explorer**.</span></span>  
  
-   <span data-ttu-id="7a668-112">La pestaña **Todos los atributos** no se puede ocultar.</span><span class="sxs-lookup"><span data-stu-id="7a668-112">There is no way to hide the **All Attributes** tab.</span></span>  
  
 <span data-ttu-id="7a668-113">Los grupos de atributos se administran en el área funcional **Administración del sistema** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a668-113">Attribute groups are administered in the **System Administration** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="show-or-hide-attribute-groups"></a><span data-ttu-id="7a668-114">Mostrar u ocultar grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="7a668-114">Show or Hide Attribute Groups</span></span>  
 <span data-ttu-id="7a668-115">Cuando se crea un grupo de atributos, se oculta automáticamente para todos los usuarios excepto para la persona que lo creó.</span><span class="sxs-lookup"><span data-stu-id="7a668-115">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="7a668-116">Para obtener más información sobre cómo hacer visible el grupo, consulte [Hacer que un grupo de atributos sea visible para los usuarios &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7a668-116">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
 <span data-ttu-id="7a668-117">Si desea ocultar un atributo específico dentro de un grupo, puede asignar permisos **Denegar** al atributo.</span><span class="sxs-lookup"><span data-stu-id="7a668-117">If you want to hide a specific attribute within a group, you can assign **Deny** permission to the attribute.</span></span> <span data-ttu-id="7a668-118">Para obtener más información, consulte [Permisos de hoja &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) o [Permisos consolidados &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7a668-118">For more information, see [Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) or [Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7a668-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7a668-119">Related Tasks</span></span>  
  
|<span data-ttu-id="7a668-120">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="7a668-120">Task Description</span></span>|<span data-ttu-id="7a668-121">Tema</span><span class="sxs-lookup"><span data-stu-id="7a668-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="7a668-122">Crear un nuevo grupo de atributos y agregarle atributos.</span><span class="sxs-lookup"><span data-stu-id="7a668-122">Create a new attribute group and add attributes to it.</span></span>|[<span data-ttu-id="7a668-123">Crear un grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a668-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)|  
|<span data-ttu-id="7a668-124">Hacer que un grupo de atributos sea visible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a668-124">Make an attribute group visible to users.</span></span>|[<span data-ttu-id="7a668-125">Hacer que un grupo de atributos sea visible para los usuarios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a668-125">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)|  
|<span data-ttu-id="7a668-126">Cambiar el nombre de un grupo de atributos existente.</span><span class="sxs-lookup"><span data-stu-id="7a668-126">Change the name of an existing attribute group.</span></span>|[<span data-ttu-id="7a668-127">Cambiar el nombre de un grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a668-127">Change an Attribute Group Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)|  
|<span data-ttu-id="7a668-128">Eliminar un grupo de atributos existente.</span><span class="sxs-lookup"><span data-stu-id="7a668-128">Delete an existing attribute group.</span></span>|[<span data-ttu-id="7a668-129">Eliminar un grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a668-129">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="7a668-130">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="7a668-130">Related Content</span></span>  
  
-   [<span data-ttu-id="7a668-131">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a668-131">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
