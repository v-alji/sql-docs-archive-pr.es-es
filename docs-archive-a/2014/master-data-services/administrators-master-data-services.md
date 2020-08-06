---
title: Administradores (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], about administrators
- administrators [Master Data Services]
- models [Master Data Services], administrators
ms.assetid: d330aa4e-6ade-4b09-b376-1b15d6c78f7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 52e16d4e77acc0a6b50b87e00184918cb9ce64b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747078"
---
# <a name="administrators-master-data-services"></a><span data-ttu-id="d5cc9-102">Administradores (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d5cc9-102">Administrators (Master Data Services)</span></span>
  <span data-ttu-id="d5cc9-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hay dos tipos de administradores: los administradores de modelo y el administrador del sistema de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5cc9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], there are two types of administrators: model administrators, and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
## <a name="model-administrators"></a><span data-ttu-id="d5cc9-104">Administradores de modelos</span><span class="sxs-lookup"><span data-stu-id="d5cc9-104">Model Administrators</span></span>  
 <span data-ttu-id="d5cc9-105">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , un administrador de modelo es un usuario que tiene el permiso **Actualizar** asignado al objeto de modelo de nivel superior en la pestaña **objetos de modelo** y ningún otro permiso asignado.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-105">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a model administrator is a user who has **Update** permission assigned to the top-level model object on the **Model Objects** tab and no other assigned permissions.</span></span>  
  
-   <span data-ttu-id="d5cc9-106">Si el usuario tiene acceso al área funcional del **Explorador** , podrá agregar, eliminar y actualizar todos los datos maestros de esta área.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-106">If the user has access to the **Explorer** functional area, the user can add, delete, and update all master data in this area.</span></span>  
  
-   <span data-ttu-id="d5cc9-107">Si el usuario tiene acceso a otras áreas funcionales, puede realizar todas las tareas administrativas disponibles en el área funcional.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-107">If the user has access to other functional areas, the user can perform all administrative tasks available in the functional area.</span></span>  
  
 <span data-ttu-id="d5cc9-108">Cada modelo puede tener varios administradores.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-108">Each model can have multiple administrators.</span></span> <span data-ttu-id="d5cc9-109">Cada usuario puede ser administrador de modelo para uno, varios o todos los modelos de la implementación de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5cc9-109">Each user can be a model administrator for one, several, or all models in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span>  
  
 <span data-ttu-id="d5cc9-110">Un usuario se puede configurar como administrador de modelo en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-110">A user can be configured as a model administrator either in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] or programmatically.</span></span> <span data-ttu-id="d5cc9-111">Para obtener más información, consulte [Crear un administrador de modelo &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5cc9-111">For more information, see [Create a Model Administrator &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md).</span></span>  
  
## <a name="master-data-services-system-administrator"></a><span data-ttu-id="d5cc9-112">Administrador del sistema de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="d5cc9-112">Master Data Services System Administrator</span></span>  
 <span data-ttu-id="d5cc9-113">Solo hay un administrador del sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5cc9-113">There is only one [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span> <span data-ttu-id="d5cc9-114">El administrador del sistema es el usuario especificado para la **cuenta de administrador** al crear la base de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-114">The system administrator is the user specified for the **Administrator Account** when you create the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
 <span data-ttu-id="d5cc9-115">El administrador del sistema de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d5cc9-115">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator:</span></span>  
  
-   <span data-ttu-id="d5cc9-116">Tiene acceso a todas las áreas funcionales automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-116">Automatically has access to all functional areas.</span></span>  
  
-   <span data-ttu-id="d5cc9-117">Puede Agregar, eliminar y actualizar todos los datos maestros de todos los modelos en el área funcional del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="d5cc9-117">Can add, delete, and update all master data for all models in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="d5cc9-118">Puede cambiar el usuario que está asignado como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-118">You can change the user who is assigned as the system administrator.</span></span> <span data-ttu-id="d5cc9-119">Para obtener más información, vea [cambiar la cuenta de administrador del sistema &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5cc9-119">For more information, see [Change the System Administrator Account &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md).</span></span>  
  
## <a name="comparing-administrator-types"></a><span data-ttu-id="d5cc9-120">Comparar los tipos de administradores</span><span class="sxs-lookup"><span data-stu-id="d5cc9-120">Comparing Administrator Types</span></span>  
  
|<span data-ttu-id="d5cc9-121">Tipo de administrador</span><span class="sxs-lookup"><span data-stu-id="d5cc9-121">Administrator Type</span></span>|<span data-ttu-id="d5cc9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5cc9-122">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="d5cc9-123">Administrador del sistema de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5cc9-123">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator</span></span>|<span data-ttu-id="d5cc9-124">Los permisos asignados en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] no tienen ningún efecto sobre el acceso del administrador.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-124">Permissions assigned in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] have no effect on the administrator's access.</span></span><br /><br /> <span data-ttu-id="d5cc9-125">Tiene automáticamente el permiso **Actualizar** para todos los modelos.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-125">Automatically has **Update** permission to all models.</span></span><br /><br /> <span data-ttu-id="d5cc9-126">Tiene acceso a todas las áreas funcionales automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-126">Automatically has access to all functional areas.</span></span><br /><br /> <span data-ttu-id="d5cc9-127">En MDM. tblUser, el valor de la columna **ID** es **1**.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-127">In mdm.tblUser, the value in the **ID** column is **1**.</span></span>|  
|<span data-ttu-id="d5cc9-128">Administrador de modelo</span><span class="sxs-lookup"><span data-stu-id="d5cc9-128">Model administrator</span></span>|<span data-ttu-id="d5cc9-129">Los permisos asignados en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] determinan si el usuario es o no un administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-129">Permissions assigned in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] determine whether or not the user is a model administrator.</span></span><br /><br /> <span data-ttu-id="d5cc9-130">Puede ser administrador de modelo según los permisos que se le asignen explícitamente o los permisos heredados de un grupo.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-130">Can be a model administrator based on permissions assigned explicitly or permissions inherited from a group.</span></span><br /><br /> <span data-ttu-id="d5cc9-131">Es un administrador solo para los modelos que tienen el permiso **Actualizar** asignado al objeto de modelo de nivel superior y ningún otro permiso.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-131">Is an administrator only for models that have **Update** permission assigned to top-level model object, and no other permissions.</span></span><br /><br /> <span data-ttu-id="d5cc9-132">Solo tiene acceso a áreas funcionales a las que se permita el acceso.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-132">Has access only to functional areas that access is granted to.</span></span><br /><br /> <span data-ttu-id="d5cc9-133">En MDM. tblUser, el valor de la columna **ID** no es **1**.</span><span class="sxs-lookup"><span data-stu-id="d5cc9-133">In mdm.tblUser, the value in the **ID** column is not **1**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5cc9-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5cc9-134">See Also</span></span>  
 <span data-ttu-id="d5cc9-135">[Cree un administrador de modelos &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5cc9-135">[Create a Model Administrator &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md) </span></span>  
 <span data-ttu-id="d5cc9-136">[Cambie la cuenta de administrador del sistema &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5cc9-136">[Change the System Administrator Account &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md) </span></span>  
 <span data-ttu-id="d5cc9-137">[Crear una base de datos de Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="d5cc9-137">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 [<span data-ttu-id="d5cc9-138">Notificaciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5cc9-138">Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/notifications-master-data-services.md)  
  
  
