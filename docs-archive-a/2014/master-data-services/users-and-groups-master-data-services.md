---
title: Usuarios y grupos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services]
- groups [Master Data Services]
- users [Master Data Services], about users
- groups [Master Data Services], about groups
ms.assetid: ed08dd2d-248e-4b68-91d4-e9961cb50eed
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: efad65bf273d58b4f60b98d050a8b99705cb00ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752222"
---
# <a name="users-and-groups-master-data-services"></a><span data-ttu-id="bb5a6-102">Usuarios y grupos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bb5a6-102">Users and Groups (Master Data Services)</span></span>
  <span data-ttu-id="bb5a6-103">Para tener acceso a la aplicación web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] un usuario debe tener una cuenta de dominio de Windows o una cuenta en el equipo servidor donde se instale [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb5a6-103">To access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application a user must have a Windows domain account or an account on the server computer where [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed.</span></span> <span data-ttu-id="bb5a6-104">Para conceder acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] puede:</span><span class="sxs-lookup"><span data-stu-id="bb5a6-104">To grant access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] you can either:</span></span>  
  
-   <span data-ttu-id="bb5a6-105">Agregar la cuenta de usuario a un dominio o grupo local y, a continuación, agregar el grupo a la lista de grupos de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb5a6-105">Add the user account to a domain or local group and then add the group to the list of groups in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="bb5a6-106">Agregar la cuenta de usuario a la lista de usuarios de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb5a6-106">Add the user account to the list of users in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb5a6-107">Cuando un usuario pertenece a un grupo que tiene acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], el nombre del usuario se agrega de forma automática a la lista de usuarios la primera vez que el usuario obtiene acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] o al [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)]MDS.</span><span class="sxs-lookup"><span data-stu-id="bb5a6-107">When a user belongs to a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], the user's name is automatically added to the list of users the first time the user accesses [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] or the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
 <span data-ttu-id="bb5a6-108">Para realizar una acción en el área de funcionalidad del **Explorador** de la IU, se debe asignar al grupo o usuario acceso al área funcional del **Explorador** y permiso a los objetos del modelo.</span><span class="sxs-lookup"><span data-stu-id="bb5a6-108">To take action within the **Explorer** functional area of the UI, the group or user must be assigned access to the **Explorer** functional area and assigned permission to model objects.</span></span>  
  
 <span data-ttu-id="bb5a6-109">Si un usuario o grupo necesita tener acceso a las áreas funcionales, el usuario o el grupo debe ser administrador.</span><span class="sxs-lookup"><span data-stu-id="bb5a6-109">If a user or group needs access to other functional areas, the user or group must be an administrator.</span></span> <span data-ttu-id="bb5a6-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bb5a6-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="bb5a6-111">Procedimiento recomendado</span><span class="sxs-lookup"><span data-stu-id="bb5a6-111">Best Practice</span></span>  
 <span data-ttu-id="bb5a6-112">Para simplificar la administración, cree grupos y asigne a cada uno permiso a las áreas funcionales y a los objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="bb5a6-112">To simplify administration, create groups and assign each group permission to functional areas and model objects.</span></span> <span data-ttu-id="bb5a6-113">Puede agregar usuarios a los grupos y quitarlos a continuación sin tener acceso a la interfaz de usuario de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb5a6-113">You can then add and remove users from the groups without accessing the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] UI.</span></span>  
  
 <span data-ttu-id="bb5a6-114">No asigne ningún permiso adicional a ningún usuario individual y no incluya usuarios en varios grupos que tengan acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb5a6-114">Do not assign additional permissions to an individual user, and do not include a user in multiple groups that have access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="bb5a6-115">Además, no use los permisos de miembros de la jerarquía a menos que desee que un grupo tenga limitado el acceso a miembros concretos.</span><span class="sxs-lookup"><span data-stu-id="bb5a6-115">In addition, do not use hierarchy member permissions unless you want a group to have limited access to specific members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5a6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb5a6-116">See Also</span></span>  
 <span data-ttu-id="bb5a6-117">[Agregar un usuario &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-user-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb5a6-117">[Add a User &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-user-master-data-services.md) </span></span>  
 <span data-ttu-id="bb5a6-118">[Agregar un grupo &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb5a6-118">[Add a Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-group-master-data-services.md) </span></span>  
 <span data-ttu-id="bb5a6-119">[Eliminar usuarios o grupos &#40;Master Data Services&#41;](../../2014/master-data-services/delete-users-or-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb5a6-119">[Delete Users or Groups &#40;Master Data Services&#41;](../../2014/master-data-services/delete-users-or-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="bb5a6-120">Probar los permisos de un usuario &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bb5a6-120">Test a User's Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/test-a-user-s-permissions-master-data-services.md)  
  
  
