---
title: Eliminar permisos de objeto de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting model object permissions [Master Data Services]
- permissions [Master Data Services], deleting model object permissions
- models [Master Data Services], deleting object permissions
ms.assetid: 859c5952-f600-4940-8064-1afd13f7f6dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 98da869476e597d76a83b0b86cc9e6e4274a25e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745879"
---
# <a name="delete-model-object-permissions-master-data-services"></a><span data-ttu-id="94091-102">Eliminar permisos de objeto de modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="94091-102">Delete Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="94091-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine los permisos del objeto de modelo para quitar las asignaciones que se hayan realizado.</span><span class="sxs-lookup"><span data-stu-id="94091-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94091-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="94091-104">Prerequisites</span></span>  
 <span data-ttu-id="94091-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="94091-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="94091-106">Debe disponer de permiso para tener acceso al área funcional **Permisos de usuario y de grupo** .</span><span class="sxs-lookup"><span data-stu-id="94091-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="94091-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="94091-107">You must be a model administrator.</span></span> <span data-ttu-id="94091-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="94091-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-model-object-permissions"></a><span data-ttu-id="94091-109">Eliminar permisos de objeto de modelo</span><span class="sxs-lookup"><span data-stu-id="94091-109">To delete model object permissions</span></span>  
  
1.  <span data-ttu-id="94091-110">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Permisos de usuario y de grupo**.</span><span class="sxs-lookup"><span data-stu-id="94091-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="94091-111">En la página **Usuarios** o **Grupos** , seleccione la fila para el usuario o grupo que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="94091-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="94091-112">Haga clic en **Editar usuario seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="94091-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="94091-113">Haga clic en la pestaña **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="94091-113">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="94091-114">Si lo desea, seleccione un modelo en la lista desplegable **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="94091-114">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="94091-115">En el panel **Resumen de permisos de modelo** , seleccione la fila correspondiente al permiso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="94091-115">In the **Model Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
7.  <span data-ttu-id="94091-116">Haga clic en **eliminar permiso seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="94091-116">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94091-117">No puede quitar un permiso de un usuario si se hereda de un grupo.</span><span class="sxs-lookup"><span data-stu-id="94091-117">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="94091-118">En su lugar debe quitar el permiso del grupo.</span><span class="sxs-lookup"><span data-stu-id="94091-118">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94091-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94091-119">See Also</span></span>  
 <span data-ttu-id="94091-120">[Permisos del objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="94091-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="94091-121">Asignar permisos de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="94091-121">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
  
