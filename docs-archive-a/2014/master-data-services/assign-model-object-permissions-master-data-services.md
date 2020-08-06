---
title: Asignar permisos de objeto de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 92ac8ef3ac63b7128c4cbb7e9305ee6bd56ca010
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673758"
---
# <a name="assign-model-object-permissions-master-data-services"></a><span data-ttu-id="5dfa8-102">Asignar permisos de objeto de modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5dfa8-102">Assign Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="5dfa8-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], asigne permisos a los objetos de modelo cuando necesite proporcionar a un usuario o grupo acceso a los datos en el área funcional del **Explorador** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]o cuando necesite convertir en administrador a un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign permissions to model objects when you need to give a user or group access to data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], or when you need to make a user or group an administrator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dfa8-104">Al asignar el permiso a un modelo, implícitamente se deniega el permiso a todos los otros modelos.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-104">When you assign permission to a model, permission to all other models is implicitly denied.</span></span> <span data-ttu-id="5dfa8-105">Si no asigna permisos del objeto de modelo, el usuario o grupo no pueden tener acceso a ningún dato en el **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-105">If you do not assign model object permissions, the user or group cannot access any data in **Explorer**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5dfa8-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5dfa8-106">Prerequisites</span></span>  
 <span data-ttu-id="5dfa8-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="5dfa8-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5dfa8-108">Debe disponer de permiso para tener acceso al área funcional **Permisos de usuario y de grupo** .</span><span class="sxs-lookup"><span data-stu-id="5dfa8-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="5dfa8-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-109">You must be a model administrator.</span></span> <span data-ttu-id="5dfa8-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa8-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-model-object-permissions"></a><span data-ttu-id="5dfa8-111">Asignar permisos de objeto de modelo</span><span class="sxs-lookup"><span data-stu-id="5dfa8-111">To assign model object permissions</span></span>  
  
1.  <span data-ttu-id="5dfa8-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Permisos de usuario y de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="5dfa8-113">En la página **Usuarios** o **Grupos** , seleccione la fila para el usuario o grupo que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="5dfa8-114">Haga clic en **Editar usuario seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="5dfa8-115">Haga clic en la pestaña **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="5dfa8-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="5dfa8-116">Si lo desea, seleccione un modelo en la lista desplegable **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="5dfa8-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="5dfa8-117">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="5dfa8-118">Expanda el árbol y haga clic en el objeto de modelo al que desea asignar los permisos.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-118">Expand the tree, and click the model object you want to assign permissions to.</span></span>  
  
8.  <span data-ttu-id="5dfa8-119">En el menú, seleccione **solo lectura**, **Actualizar**o **denegar**.</span><span class="sxs-lookup"><span data-stu-id="5dfa8-119">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
9. <span data-ttu-id="5dfa8-120">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="5dfa8-120">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5dfa8-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5dfa8-121">Next Steps</span></span>  
  
-   <span data-ttu-id="5dfa8-122">(Opcional) [Asignar los permisos de los miembros de una jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="5dfa8-122">(Optional) [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfa8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5dfa8-123">See Also</span></span>  
 <span data-ttu-id="5dfa8-124">[Eliminar permisos de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5dfa8-124">[Delete Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="5dfa8-125">[Permisos del objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5dfa8-125">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="5dfa8-126">Crear un administrador de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5dfa8-126">Create a Model Administrator &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  
