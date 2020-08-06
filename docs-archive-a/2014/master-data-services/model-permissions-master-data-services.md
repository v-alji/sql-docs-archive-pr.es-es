---
title: Permisos de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2846918b515bba16d12d48cd7058cf25863bf569
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673073"
---
# <a name="model-permissions-master-data-services"></a><span data-ttu-id="3b749-102">Permisos de modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b749-102">Model Permissions (Master Data Services)</span></span>
  <span data-ttu-id="3b749-103">Los permisos de modelo se aplican a todas las entidades, jerarquías derivadas, jerarquías explícitas y colecciones dentro del modelo.</span><span class="sxs-lookup"><span data-stu-id="3b749-103">Model permissions apply to all entities, derived hierarchies, explicit hierarchies, and collections that exist within the model.</span></span> <span data-ttu-id="3b749-104">Los permisos asignados al modelo se pueden invalidar con respecto a cualquier objeto individual.</span><span class="sxs-lookup"><span data-stu-id="3b749-104">Permissions assigned to the model can be overridden for any individual object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b749-105">Si un usuario es administrador de un modelo, el modelo se muestra en todas las áreas funcionales de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="3b749-105">If a user is a model administrator, the model is displayed in all functional areas of the user interface.</span></span> <span data-ttu-id="3b749-106">De lo contrario, el modelo solo se mostrará en el área funcional del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="3b749-106">Otherwise, the model is displayed in the **Explorer** functional area only.</span></span> <span data-ttu-id="3b749-107">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b749-107">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
|<span data-ttu-id="3b749-108">Permiso</span><span class="sxs-lookup"><span data-stu-id="3b749-108">Permission</span></span>|<span data-ttu-id="3b749-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b749-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="3b749-110">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="3b749-110">**Read-only**</span></span>|<span data-ttu-id="3b749-111">En el **Explorador**, se muestra el modelo, pero el usuario no puede Agregar o quitar miembros, y no puede actualizar los valores de atributo, pertenencias a jerarquías o pertenencias a colecciones.</span><span class="sxs-lookup"><span data-stu-id="3b749-111">In **Explorer**, the model is displayed but the user cannot add or remove members, and cannot update attribute values, hierarchy memberships, or collection memberships.</span></span>|  
|<span data-ttu-id="3b749-112">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="3b749-112">**Update**</span></span>|<span data-ttu-id="3b749-113">En el **Explorador**, se muestra el modelo y el usuario puede Agregar y quitar miembros, puede actualizar valores de atributo, pertenencias a jerarquías y pertenencias a colecciones.</span><span class="sxs-lookup"><span data-stu-id="3b749-113">In **Explorer**, the model is displayed and the user can add and remove members, can update attribute values, hierarchy memberships, and collection memberships.</span></span>|  
|<span data-ttu-id="3b749-114">**Denegar**</span><span class="sxs-lookup"><span data-stu-id="3b749-114">**Deny**</span></span>|<span data-ttu-id="3b749-115">El modelo no aparece.</span><span class="sxs-lookup"><span data-stu-id="3b749-115">The model is not displayed.</span></span>|  
  
 <span data-ttu-id="3b749-116">Cuando asigna permisos a un modelo, el usuario obtiene acceso a todas las versiones del modelo.</span><span class="sxs-lookup"><span data-stu-id="3b749-116">When you assign permission to a model, the user gets access to all versions of the model.</span></span> <span data-ttu-id="3b749-117">No puede asignar el permiso a una versión individual.</span><span class="sxs-lookup"><span data-stu-id="3b749-117">You cannot assign permission to an individual version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b749-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b749-118">See Also</span></span>  
 <span data-ttu-id="3b749-119">[Asignar permisos de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3b749-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="3b749-120">[Permisos del objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3b749-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="3b749-121">[Permisos de entidad &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3b749-121">[Entity Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="3b749-122">Permisos de colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3b749-122">Collection Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  
