---
title: Cómo se determinan los permisos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], determining permissions
ms.assetid: 1dc0b43a-d023-4e7d-b027-8b1459fd058c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea3306b772224bc8602659c7e17e8dc1634f0d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674173"
---
# <a name="how-permissions-are-determined-master-data-services"></a><span data-ttu-id="64626-102">Cómo se determinan los permisos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="64626-102">How Permissions Are Determined (Master Data Services)</span></span>
  <span data-ttu-id="64626-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], la manera más sencilla de configurar la seguridad es asignar permisos del objeto de modelo a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="64626-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], the simplest way to configure security is to assign model object permissions to a group that the user is a member of.</span></span>

 <span data-ttu-id="64626-104">La seguridad se hace más compleja cuando:</span><span class="sxs-lookup"><span data-stu-id="64626-104">Security becomes more complex when:</span></span>

-   <span data-ttu-id="64626-105">Se asignan permisos del objeto de modelo y permisos de los miembros de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64626-105">Both model object and hierarchy member permissions are assigned.</span></span>

-   <span data-ttu-id="64626-106">El usuario pertenece a grupos y el permiso se asigna al usuario y los grupos.</span><span class="sxs-lookup"><span data-stu-id="64626-106">The user belongs to groups and permission is assigned to both the user and groups.</span></span>

-   <span data-ttu-id="64626-107">El usuario pertenece a grupos y el permiso se asigna a varios grupos.</span><span class="sxs-lookup"><span data-stu-id="64626-107">The user belongs to groups and permission is assigned to multiple groups.</span></span>

## <a name="permissions-assigned-to-a-single-group-or-user"></a><span data-ttu-id="64626-108">Permisos asignados a un solo grupo o usuario</span><span class="sxs-lookup"><span data-stu-id="64626-108">Permissions assigned to a single group or user</span></span>
 <span data-ttu-id="64626-109">Si asigna permisos a un solo grupo o usuario, los permisos se determinan en función del siguiente flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="64626-109">If you assign permissions to a single group or user, permissions are determined based on the following workflow.</span></span>

 <span data-ttu-id="64626-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span><span class="sxs-lookup"><span data-stu-id="64626-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span></span>

### <a name="step-1-effective-attribute-permissions-are-determined"></a><span data-ttu-id="64626-111">Paso 1: se determinan los permisos de atributo efectivos.</span><span class="sxs-lookup"><span data-stu-id="64626-111">Step 1: Effective attribute permissions are determined.</span></span>
 <span data-ttu-id="64626-112">En la siguiente lista se describe cómo se determinan los permisos de atributo efectivos:</span><span class="sxs-lookup"><span data-stu-id="64626-112">The following list describes how effective attribute permissions are determined:</span></span>

-   <span data-ttu-id="64626-113">Los permisos asignados a objetos de modelo determinan a qué atributos puede tener acceso un usuario.</span><span class="sxs-lookup"><span data-stu-id="64626-113">Permissions assigned to model objects determine which attributes a user can access.</span></span>

-   <span data-ttu-id="64626-114">Todos los objetos de modelo heredan automáticamente el permiso del objeto más cercano en un nivel superior de la estructura del modelo.</span><span class="sxs-lookup"><span data-stu-id="64626-114">All model objects automatically inherit permission from the closest object at a higher level in the model structure.</span></span>

-   <span data-ttu-id="64626-115">Todos los objetos del mismo nivel que la entidad se deniegan implícitamente.</span><span class="sxs-lookup"><span data-stu-id="64626-115">Any objects at the same level as the entity are implicitly denied.</span></span>

-   <span data-ttu-id="64626-116">Todos los objetos de un nivel superior reciben acceso de navegación.</span><span class="sxs-lookup"><span data-stu-id="64626-116">Any objects at a higher level are given navigational access.</span></span> <span data-ttu-id="64626-117">Para obtener más información sobre el acceso de navegación, consulte [&#40;de acceso de navegación Master Data Services&#41;](navigational-access-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64626-117">For more information about navigational access, see [Navigational Access &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span></span>

 <span data-ttu-id="64626-118">En este ejemplo, el permiso **de solo lectura** se asigna a una entidad y el permiso se hereda mediante su atributo, que está en un nivel inferior de la estructura del modelo.</span><span class="sxs-lookup"><span data-stu-id="64626-118">In this example, **Read-only** permission is assigned to an entity and that permission is inherited by its attribute, which is at a lower level in the model structure.</span></span> <span data-ttu-id="64626-119">El modelo proporciona acceso de navegación a esta entidad y su atributo.</span><span class="sxs-lookup"><span data-stu-id="64626-119">The model provides navigational access to this entity and its attribute.</span></span> <span data-ttu-id="64626-120">La otra entidad del modelo no tiene ningún permiso explícito asignado y no hereda ningún permiso, de modo que se deniega implícitamente.</span><span class="sxs-lookup"><span data-stu-id="64626-120">The other entity in the model has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="64626-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="64626-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>

### <a name="step-2-if-hierarchy-member-permissions-are-assigned-effective-member-permissions-are-determined"></a><span data-ttu-id="64626-122">Paso 2: si se asignan los permisos de los miembros de una jerarquía, se determinan los permisos de miembros efectivos.</span><span class="sxs-lookup"><span data-stu-id="64626-122">Step 2: If hierarchy member permissions are assigned, effective member permissions are determined.</span></span>
 <span data-ttu-id="64626-123">En la siguiente lista se describe cómo se determinan los permisos de los miembros de una jerarquía efectivos:</span><span class="sxs-lookup"><span data-stu-id="64626-123">The following list describes how effective hierarchy member permissions are determined:</span></span>

-   <span data-ttu-id="64626-124">Los permisos asignados a los nodos de la jerarquía determinan a qué miembros puede tener acceso un usuario.</span><span class="sxs-lookup"><span data-stu-id="64626-124">Permissions assigned to hierarchy nodes determine which members a user can access.</span></span>

-   <span data-ttu-id="64626-125">Todos los nodos de una jerarquía heredan automáticamente el permiso del objeto más cercano en un nivel superior en la estructura de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64626-125">All nodes in a hierarchy automatically inherit permission from the closest object at a higher level in the hierarchy structure.</span></span>

-   <span data-ttu-id="64626-126">Todos los nodos del mismo nivel se deniegan implícitamente.</span><span class="sxs-lookup"><span data-stu-id="64626-126">Any nodes at the same level are implicitly denied.</span></span>

-   <span data-ttu-id="64626-127">Todos los nodos de niveles superiores a los que no se asignan los permisos se deniegan implícitamente.</span><span class="sxs-lookup"><span data-stu-id="64626-127">Any nodes at higher levels that do not have permissions assigned are implicitly denied.</span></span>

 <span data-ttu-id="64626-128">En este ejemplo, el permiso de **solo lectura** se asigna a un nodo de la jerarquía y el permiso lo hereda un nodo de un nivel inferior en la estructura de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64626-128">In this example, **Read-only** permission is assigned to one node of the hierarchy and that permission is inherited by a node at a lower level in the hierarchy structure.</span></span> <span data-ttu-id="64626-129">La raíz no tiene ningún permiso asignado, de modo que se deniega implícitamente.</span><span class="sxs-lookup"><span data-stu-id="64626-129">The root has no permission assigned, so it is implicitly denied.</span></span> <span data-ttu-id="64626-130">El otro nodo de la estructura de la jerarquía no tiene ningún permiso explícito asignado y no hereda ningún permiso, de modo que se deniega implícitamente.</span><span class="sxs-lookup"><span data-stu-id="64626-130">The other node in the hierarchy structure has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="64626-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="64626-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span></span>

### <a name="step-3-the-intersection-of-attribute-and-member-permissions-is-determined"></a><span data-ttu-id="64626-132">Paso 3: se determina la intersección los permisos de atributo y de miembro.</span><span class="sxs-lookup"><span data-stu-id="64626-132">Step 3: The intersection of attribute and member permissions is determined.</span></span>
 <span data-ttu-id="64626-133">Si los permisos de atributo efectivos son diferentes que los permisos de miembro efectivos, los permisos se deben determinar para cada valor de atributo individual.</span><span class="sxs-lookup"><span data-stu-id="64626-133">If the effective attribute permissions are different than the effective member permissions, permissions must be determined for each individual attribute value.</span></span> <span data-ttu-id="64626-134">Para obtener más información, consulte [Superponer permisos de modelo y de miembro &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64626-134">For more information, see [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span></span>

## <a name="permissions-assigned-to-multiple-groups"></a><span data-ttu-id="64626-135">Permisos asignados a varios grupos</span><span class="sxs-lookup"><span data-stu-id="64626-135">Permissions assigned to multiple groups</span></span>
 <span data-ttu-id="64626-136">Si un usuario pertenece a uno o más grupos y se asignan permisos al usuario y a los grupos, el flujo de trabajo se vuelve más complejo.</span><span class="sxs-lookup"><span data-stu-id="64626-136">If a user belongs to one or more groups and permissions are assigned to both the user and the groups, the workflow becomes more complex.</span></span>

 <span data-ttu-id="64626-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span><span class="sxs-lookup"><span data-stu-id="64626-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span></span>

 <span data-ttu-id="64626-138">En este caso, los permisos de usuario y de grupo que se superpongan se deben resolver para poder comparar los permisos del objeto de modelo y del miembro de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64626-138">In this case, overlapping user and group permissions must be resolved before model object and hierarchy member permissions can be compared.</span></span> <span data-ttu-id="64626-139">Para obtener más información, consulte [Superponer permisos de usuario y de grupo &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64626-139">For more information, see [Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="64626-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64626-140">See Also</span></span>
 <span data-ttu-id="64626-141">[Los permisos de usuario y de grupo superpuestos &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [los permisos de miembros y modelos superpuestos &#40;Master Data Services](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="64626-141">[Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span></span>


