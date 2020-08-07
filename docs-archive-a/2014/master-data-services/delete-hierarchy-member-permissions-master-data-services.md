---
title: Eliminar los permisos de los miembros de una jerarquía (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting member permissions [Master Data Services]
- members [Master Data Services], deleting permissions
- permissions [Master Data Services], deleting member permissions
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8b6e7fbfc4379733d5cb809ce4d46d2c12d05a48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745880"
---
# <a name="delete-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="04314-102">Eliminar los permisos de los miembros de una jerarquía (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="04314-102">Delete Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="04314-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine los permisos del objeto de modelo para quitar las asignaciones que se hayan realizado.</span><span class="sxs-lookup"><span data-stu-id="04314-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04314-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="04314-104">Prerequisites</span></span>  
 <span data-ttu-id="04314-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="04314-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="04314-106">Debe disponer de permiso para tener acceso al área funcional **Permisos de usuario y de grupo** .</span><span class="sxs-lookup"><span data-stu-id="04314-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="04314-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="04314-107">You must be a model administrator.</span></span> <span data-ttu-id="04314-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="04314-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-hierarchy-member-permissions"></a><span data-ttu-id="04314-109">Eliminar los permisos de los miembros de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="04314-109">To delete hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="04314-110">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Permisos de usuario y de grupo**.</span><span class="sxs-lookup"><span data-stu-id="04314-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="04314-111">En la página **Usuarios** o **Grupos** , seleccione la fila para el usuario o grupo que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="04314-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="04314-112">Haga clic en **Editar usuario seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="04314-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="04314-113">Haga clic en la pestaña **Miembros de la jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="04314-113">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="04314-114">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="04314-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="04314-115">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="04314-115">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="04314-116">En el panel **Resumen de permisos de miembros** de la jerarquía, seleccione la fila correspondiente al permiso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="04314-116">In the **Hierarchy Member Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
8.  <span data-ttu-id="04314-117">Haga clic en **eliminar permiso seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="04314-117">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04314-118">No puede quitar un permiso de un usuario si se hereda de un grupo.</span><span class="sxs-lookup"><span data-stu-id="04314-118">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="04314-119">En su lugar debe quitar el permiso del grupo.</span><span class="sxs-lookup"><span data-stu-id="04314-119">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04314-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04314-120">See Also</span></span>  
 <span data-ttu-id="04314-121">[Permisos de miembros de la jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="04314-121">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="04314-122">Asignar los permisos de los miembros de una jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="04314-122">Assign Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  
