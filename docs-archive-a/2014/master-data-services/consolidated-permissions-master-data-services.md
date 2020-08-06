---
title: Permisos consolidados (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], consolidated member attribute permissions
- consolidated members [Master Data Services], attribute permissions
- permissions [Master Data Services], consolidated members
- members [Master Data Services], consolidated member permissions
ms.assetid: 084055a3-5fd3-43f3-b620-ac6afab42a3d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4c93e74acc84d6e742139263bedc011c4028efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678233"
---
# <a name="consolidated-permissions-master-data-services"></a><span data-ttu-id="49d69-102">Permisos consolidados (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="49d69-102">Consolidated Permissions (Master Data Services)</span></span>
  <span data-ttu-id="49d69-103">Los permisos consolidados se aplican a los valores de atributo de todos los miembros consolidados de una entidad.</span><span class="sxs-lookup"><span data-stu-id="49d69-103">Consolidated permissions apply to the attribute values for all consolidated members of an entity.</span></span>  
  
 <span data-ttu-id="49d69-104">Los permisos consolidados solo se aplican a las entidades que estén habilitadas para jerarquías explícitas y colecciones.</span><span class="sxs-lookup"><span data-stu-id="49d69-104">Consolidated permissions apply only to entities that are enabled for explicit hierarchies and collections.</span></span>  
  
 <span data-ttu-id="49d69-105">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="49d69-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="49d69-106">Los permisos de hoja solo se aplican al área funcional del **Explorador** de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="49d69-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="49d69-107">Los permisos asignados a **Nombre** y a los atributos de **Código** no se aplican.</span><span class="sxs-lookup"><span data-stu-id="49d69-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="49d69-108">Permiso</span><span class="sxs-lookup"><span data-stu-id="49d69-108">Permission</span></span>|<span data-ttu-id="49d69-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="49d69-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="49d69-110">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="49d69-110">**Read-only**</span></span>|<span data-ttu-id="49d69-111">Se muestran los miembros consolidados, pero el usuario no los puede agregar, quitar o cambiar.</span><span class="sxs-lookup"><span data-stu-id="49d69-111">Consolidated members are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="49d69-112">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="49d69-112">**Update**</span></span>|<span data-ttu-id="49d69-113">Se muestran los miembros consolidados y el usuario los puede agregar, quitar y cambiar.</span><span class="sxs-lookup"><span data-stu-id="49d69-113">Consolidated members are displayed and the user can add, remove, and change them.</span></span>|  
|<span data-ttu-id="49d69-114">**Denegar**</span><span class="sxs-lookup"><span data-stu-id="49d69-114">**Deny**</span></span>|<span data-ttu-id="49d69-115">No se muestran los miembros consolidados para la entidad.</span><span class="sxs-lookup"><span data-stu-id="49d69-115">Consolidated members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="49d69-116">Permisos de atributo</span><span class="sxs-lookup"><span data-stu-id="49d69-116">Attribute Permissions</span></span>  
 <span data-ttu-id="49d69-117">Los permisos de atributo se aplican a los valores del atributo para la entidad concreta.</span><span class="sxs-lookup"><span data-stu-id="49d69-117">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="49d69-118">Los usuarios que solo tienen permisos de atributo no pueden agregar o quitar miembros.</span><span class="sxs-lookup"><span data-stu-id="49d69-118">Users with only attribute permissions cannot add or remove members.</span></span>  
  
|<span data-ttu-id="49d69-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="49d69-119">Permission</span></span>|<span data-ttu-id="49d69-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="49d69-120">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="49d69-121">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="49d69-121">**Read-only**</span></span>|<span data-ttu-id="49d69-122">Se muestra el atributo, pero el usuario no puede cambiar los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="49d69-122">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="49d69-123">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="49d69-123">**Update**</span></span>|<span data-ttu-id="49d69-124">Se muestra el atributo y el usuario puede cambiar los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="49d69-124">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="49d69-125">**Denegar**</span><span class="sxs-lookup"><span data-stu-id="49d69-125">**Deny**</span></span>|<span data-ttu-id="49d69-126">No se muestra el atributo.</span><span class="sxs-lookup"><span data-stu-id="49d69-126">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="49d69-127">Nota: No puede denegar explícitamente el acceso a los atributos Name y Code.</span><span class="sxs-lookup"><span data-stu-id="49d69-127">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49d69-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49d69-128">See Also</span></span>  
 <span data-ttu-id="49d69-129">[Asignar permisos de objeto de modelo &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="49d69-129">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="49d69-130">[Permisos de hoja &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="49d69-130">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="49d69-131">[Permisos del objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="49d69-131">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="49d69-132">[Miembros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="49d69-132">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="49d69-133">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49d69-133">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
