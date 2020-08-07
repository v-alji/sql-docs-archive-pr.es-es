---
title: Superponer permisos de usuario y de grupo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7044bf6260170cbc598719ec204ddb6f861f6301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745348"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a><span data-ttu-id="6f43e-102">Superponer permisos de usuario y de grupo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6f43e-102">Overlapping User and Group Permissions (Master Data Services)</span></span>
  <span data-ttu-id="6f43e-103">Los permisos de un usuario se basan en:</span><span class="sxs-lookup"><span data-stu-id="6f43e-103">A user's permissions are based on:</span></span>  
  
-   <span data-ttu-id="6f43e-104">Permisos de las pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="6f43e-104">Permissions from group memberships.</span></span>  
  
-   <span data-ttu-id="6f43e-105">Permisos asignados explícitamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="6f43e-105">Permissions assigned explicitly to the user.</span></span>  
  
 <span data-ttu-id="6f43e-106">Si un usuario es miembro de varios grupos y dichos grupos tienen acceso al Administrador de datos maestros, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="6f43e-106">If a user is a member of multiple groups, and those groups have access to Master Data Manager, the following rules apply:</span></span>  
  
-   <span data-ttu-id="6f43e-107">**Denegar** invalida al resto de permisos.</span><span class="sxs-lookup"><span data-stu-id="6f43e-107">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="6f43e-108">La **actualización** invalida las invalidaciones **de solo lectura**.</span><span class="sxs-lookup"><span data-stu-id="6f43e-108">**Update** overrides **Read-only**.</span></span>  
  
 <span data-ttu-id="6f43e-109">Estas reglas se aplican a las pestañas **Modelos** y **Miembros de la jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="6f43e-109">These rules apply to both the **Models** and **Hierarchy Members** tabs.</span></span> <span data-ttu-id="6f43e-110">Los permisos se resuelven para cada pestaña y, a continuación, se combinan.</span><span class="sxs-lookup"><span data-stu-id="6f43e-110">Permissions are resolved for each tab and then combined.</span></span> <span data-ttu-id="6f43e-111">Para obtener más información, consulte [Cómo se determinan los permisos &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f43e-111">For more information, see [How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f43e-112">Puede ver la resolución de los permisos superpuestos de usuario y de grupo en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f43e-112">You can view the resolution of user and group overlapping permissions in the user interface.</span></span> <span data-ttu-id="6f43e-113">Las pestañas **Modelos** y **Miembros de la jerarquía** tienen una lista desplegable en la que puede elegir **Vigente** para ver los permisos vigentes.</span><span class="sxs-lookup"><span data-stu-id="6f43e-113">Both the **Models** and **Hierarchy Members** tab have a drop-down list from which you can choose **Effective** to view effective permissions.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="6f43e-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="6f43e-114">Example 1</span></span>  
 <span data-ttu-id="6f43e-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span><span class="sxs-lookup"><span data-stu-id="6f43e-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span></span>  
  
 <span data-ttu-id="6f43e-116">El usuario pertenece a Grupo 1 y Grupo 2.</span><span class="sxs-lookup"><span data-stu-id="6f43e-116">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="6f43e-117">El usuario tiene permiso **de solo lectura** para la entidad product.</span><span class="sxs-lookup"><span data-stu-id="6f43e-117">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="6f43e-118">El Grupo 1 tiene el permiso **Actualizar** para la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="6f43e-118">Group 1 has **Update** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="6f43e-119">El grupo 2 tiene permiso **de solo lectura** para la entidad product.</span><span class="sxs-lookup"><span data-stu-id="6f43e-119">Group 2 has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="6f43e-120">Resultado: el permiso vigente del usuario para la entidad Product es **Actualizar** .</span><span class="sxs-lookup"><span data-stu-id="6f43e-120">Result: The user's effective permission is **Update** to the Product entity.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="6f43e-121">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="6f43e-121">Example 2</span></span>  
 <span data-ttu-id="6f43e-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span><span class="sxs-lookup"><span data-stu-id="6f43e-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span></span>  
  
 <span data-ttu-id="6f43e-123">El usuario pertenece a Grupo 1 y Grupo 2.</span><span class="sxs-lookup"><span data-stu-id="6f43e-123">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="6f43e-124">El usuario tiene permiso **de solo lectura** para la entidad product.</span><span class="sxs-lookup"><span data-stu-id="6f43e-124">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="6f43e-125">El Grupo 1 tiene el permiso **Actualizar** para la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="6f43e-125">Group 1 has **Update** permission to Product entity.</span></span>  
  
 <span data-ttu-id="6f43e-126">El Grupo 2 tiene el permiso **Denegar** para la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="6f43e-126">Group 2 has **Deny** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="6f43e-127">Resultado: el permiso vigente del usuario para la entidad Product es **Denegar** .</span><span class="sxs-lookup"><span data-stu-id="6f43e-127">Result: The user's effective permission is **Deny** to the Product entity.</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="6f43e-128">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="6f43e-128">Example 3</span></span>  
 <span data-ttu-id="6f43e-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span><span class="sxs-lookup"><span data-stu-id="6f43e-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span></span>  
  
 <span data-ttu-id="6f43e-130">El usuario pertenece a Grupo 1 y Grupo 2.</span><span class="sxs-lookup"><span data-stu-id="6f43e-130">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="6f43e-131">El usuario tiene el permiso **Actualizar** para un grupo de miembros en un nodo de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="6f43e-131">The user has **Update** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="6f43e-132">El grupo 1 tiene el permiso **solo lectura** para un grupo de miembros en un nodo de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="6f43e-132">Group 1 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="6f43e-133">El grupo 2 tiene **el permiso solo lectura** para un grupo de miembros en un nodo de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="6f43e-133">Group 2 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="6f43e-134">Resultado: el permiso vigente del usuario para los miembros es **Actualizar** .</span><span class="sxs-lookup"><span data-stu-id="6f43e-134">Result: The user's effective permission is **Update** to the members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f43e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f43e-135">See Also</span></span>  
 <span data-ttu-id="6f43e-136">[Cómo se determinan los permisos &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6f43e-136">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="6f43e-137">Superponer permisos de modelo y de miembro &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6f43e-137">Overlapping Model and Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
