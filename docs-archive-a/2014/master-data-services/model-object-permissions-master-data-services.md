---
title: Permisos de objeto de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], model objects
- models [Master Data Services], object permissions
ms.assetid: fab6335b-4cae-47de-ae7c-6c4743e0680f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4cc64d753b680cfabc3707a29c6d9de631708c20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676538"
---
# <a name="model-object-permissions-master-data-services"></a><span data-ttu-id="11ea5-102">Permisos de objeto del modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="11ea5-102">Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="11ea5-103">Los permisos del objeto de modelo son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11ea5-103">Model object permissions are mandatory.</span></span> <span data-ttu-id="11ea5-104">Determinan los atributos a los que un usuario puede tener acceso en el área funcional del **Explorador** de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="11ea5-104">They determine the attributes a user can access in the **Explorer** functional area of the UI.</span></span>  
  
 <span data-ttu-id="11ea5-105">Por ejemplo, si asigna a un usuario el permiso **Actualizar** para la entidad Product, el usuario puede actualizar todos los atributos de la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="11ea5-105">For example, if you assign a user **Update** permission to the Product entity, the user can update all of the attributes of the Product entity.</span></span> <span data-ttu-id="11ea5-106">Si asigna el permiso **Actualizar** a un único atributo, el usuario solo podrá actualizar el atributo.</span><span class="sxs-lookup"><span data-stu-id="11ea5-106">If you assign **Update** permission to a single attribute, the user can update that attribute only.</span></span>  
  
 <span data-ttu-id="11ea5-107">Para determinar la seguridad asignada en cada valor de atributo individual, los permisos de objeto de modelo se combinan con los permisos de miembros de jerarquía, que determinan los miembros a los que un usuario puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="11ea5-107">To determine security assigned on each individual attribute value, model object permissions are combined with hierarchy member permissions, which determine the members a user can access.</span></span>  
  
 <span data-ttu-id="11ea5-108">Para conceder a un usuario acceso a un área funcional que no sea el **Explorador**, el usuario debe ser un administrador del modelo, lo que implica también la asignación de permisos de objeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="11ea5-108">To give a user access to a functional area other than **Explorer**, the user must be a model administrator, which also involves assigning model object permissions.</span></span> <span data-ttu-id="11ea5-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="11ea5-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="11ea5-110">Los permisos del objeto de modelo se asignan en la [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] interfaz de usuario (UI), en el área funcional **permisos de usuario y de grupo** de la pestaña **modelos** . En esta pestaña, el modelo se representa como una estructura de árbol.</span><span class="sxs-lookup"><span data-stu-id="11ea5-110">Model object permissions are assigned in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), in the **User and Group Permissions** functional area on the **Models** tab. On this tab, the model is represented as a tree structure.</span></span> <span data-ttu-id="11ea5-111">Cuando asigne un permiso a un objeto en el árbol, todos los objetos subordinados heredan ese permiso.</span><span class="sxs-lookup"><span data-stu-id="11ea5-111">When you assign permission to an object in the tree, all objects below inherit that permission.</span></span> <span data-ttu-id="11ea5-112">Para invalidar esa herencia asignando el permiso a objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="11ea5-112">You can override that inheritance by assigning permission to individual objects.</span></span>  
  
 <span data-ttu-id="11ea5-113">Puede asignar el permiso de **solo lectura**, **Actualizar**o **denegar** a los objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="11ea5-113">You can assign **Read-only**, **Update**, or **Deny** permission to model objects.</span></span> <span data-ttu-id="11ea5-114">Si no asigna permisos en la pestaña **Modelos** , el usuario no podrá ver ningún modelo ni ningún dato en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11ea5-114">If you do not assign any permissions on the **Models** tab, the user cannot view any models or data in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="11ea5-115">Procedimiento recomendado</span><span class="sxs-lookup"><span data-stu-id="11ea5-115">Best Practice</span></span>  
 <span data-ttu-id="11ea5-116">En general, debe asignar el permiso **Actualizar** al objeto de modelo y, a continuación, asignar explícitamente el permiso a los objetos situados debajo de.</span><span class="sxs-lookup"><span data-stu-id="11ea5-116">In general, you should assign **Update** permission to the model object, and then explicitly assign permission to objects underneath.</span></span> <span data-ttu-id="11ea5-117">Si no asigna permisos en objetos subordinados, los permisos se heredan y el usuario es un administrador.</span><span class="sxs-lookup"><span data-stu-id="11ea5-117">If you do not assign permission to objects underneath, the permissions are inherited and the user is an administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ea5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11ea5-118">See Also</span></span>  
 <span data-ttu-id="11ea5-119">[Asignar permisos de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11ea5-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="11ea5-120">[Permisos de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11ea5-120">[Model Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="11ea5-121">[&#40;Master Data Services permisos de área funcional&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11ea5-121">[Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="11ea5-122">[Permisos de miembros de la jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11ea5-122">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="11ea5-123">Cómo se determinan los permisos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="11ea5-123">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
