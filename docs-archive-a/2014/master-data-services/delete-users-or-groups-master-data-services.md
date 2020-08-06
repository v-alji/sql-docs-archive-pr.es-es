---
title: Eliminar usuarios o grupos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: be302bc974994d0f4f17a8e61244065c76fa93ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676540"
---
# <a name="delete-users-or-groups-master-data-services"></a><span data-ttu-id="a1c66-102">Eliminar usuarios o grupos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a1c66-102">Delete Users or Groups (Master Data Services)</span></span>
  <span data-ttu-id="a1c66-103">Elimine los usuarios o los grupos que ya no desee que tengan acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c66-103">Delete users or groups when you no longer want them to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="a1c66-104">Tenga en cuenta el siguiente comportamiento al eliminar usuarios y grupos:</span><span class="sxs-lookup"><span data-stu-id="a1c66-104">Note the following behavior when deleting users and groups:</span></span>  
  
-   <span data-ttu-id="a1c66-105">Si elimina a un usuario que sea miembro de un grupo con acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], el usuario todavía puede tener acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] hasta que quite al usuario del grupo local o de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a1c66-105">If you delete a user who is a member of a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], then the user can still access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] until you remove the user from the Active Directory or local group.</span></span>  
  
-   <span data-ttu-id="a1c66-106">Si elimina un grupo, todos los usuarios del mismo que hayan obtenido acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] se mostrarán en la lista **Usuarios** hasta que los elimine.</span><span class="sxs-lookup"><span data-stu-id="a1c66-106">If you delete a group, all users from the group who have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] are displayed in the **Users** list until you delete them.</span></span>  
  
-   <span data-ttu-id="a1c66-107">Los cambios de seguridad no se propagan al sistema MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] durante 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="a1c66-107">Changes to security are not propagated to the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] for 20 minutes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1c66-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1c66-108">Prerequisites</span></span>  
 <span data-ttu-id="a1c66-109">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="a1c66-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a1c66-110">Debe disponer de permiso para tener acceso al área funcional **Permisos de usuario y de grupo** .</span><span class="sxs-lookup"><span data-stu-id="a1c66-110">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="a1c66-111">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="a1c66-111">You must be a model administrator.</span></span> <span data-ttu-id="a1c66-112">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a1c66-112">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-users-or-groups"></a><span data-ttu-id="a1c66-113">Eliminar usuarios o grupos</span><span class="sxs-lookup"><span data-stu-id="a1c66-113">To delete users or groups</span></span>  
  
1.  <span data-ttu-id="a1c66-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Permisos de usuario y de grupo**.</span><span class="sxs-lookup"><span data-stu-id="a1c66-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="a1c66-115">Para eliminar un usuario, permanezca en la página **Usuarios** .</span><span class="sxs-lookup"><span data-stu-id="a1c66-115">To delete a user, remain on the **Users** page.</span></span> <span data-ttu-id="a1c66-116">Para eliminar un grupo, en la barra de menús, haga clic en **ManageGroups.**</span><span class="sxs-lookup"><span data-stu-id="a1c66-116">To delete a group, from the menu bar, click **ManageGroups.**</span></span>  
  
3.  <span data-ttu-id="a1c66-117">En la cuadrícula, seleccione la fila del usuario o grupo que quiere eliminar.</span><span class="sxs-lookup"><span data-stu-id="a1c66-117">In the grid,select the row for the user or group that you want to delete.</span></span>  
  
4.  <span data-ttu-id="a1c66-118">Haga clic en **Eliminar usuario seleccionado** o en **Eliminar grupo seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="a1c66-118">Click **Delete selected user** or **Delete selected group**.</span></span>  
  
5.  <span data-ttu-id="a1c66-119">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1c66-119">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c66-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1c66-120">See Also</span></span>  
 [<span data-ttu-id="a1c66-121">Seguridad &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a1c66-121">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
