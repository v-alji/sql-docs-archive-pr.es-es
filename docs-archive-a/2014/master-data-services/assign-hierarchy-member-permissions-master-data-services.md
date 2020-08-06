---
title: Asignar los permisos de los miembros de una jerarquía (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4a1602f9fe351f826b63d4447f90dcf02a10f49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673774"
---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="b62d0-102">Asignar los permisos de los miembros de una jerarquía (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b62d0-102">Assign Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="b62d0-103">Asigne los permisos a los miembros de la jerarquía para proporcionar a los usuarios o grupos acceso para ver los datos en el área funcional del **Explorador** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b62d0-103">Assign permissions to hierarchy members to give users or groups access to view data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="b62d0-104">Los permisos de los miembros de la jerarquía son opcionales.</span><span class="sxs-lookup"><span data-stu-id="b62d0-104">Hierarchy member permissions are optional.</span></span> <span data-ttu-id="b62d0-105">Proporcionan una granularidad agregada para los permisos de objetos de modelo, que son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b62d0-105">They provide added granularity to model object permissions, which are required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b62d0-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b62d0-106">Prerequisites</span></span>  
 <span data-ttu-id="b62d0-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b62d0-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b62d0-108">Debe disponer de permiso para tener acceso al área funcional **Permisos de usuario y de grupo** .</span><span class="sxs-lookup"><span data-stu-id="b62d0-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="b62d0-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="b62d0-109">You must be a model administrator.</span></span> <span data-ttu-id="b62d0-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b62d0-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-hierarchy-member-permissions"></a><span data-ttu-id="b62d0-111">Asignar los permisos de los miembros de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="b62d0-111">To assign hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="b62d0-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Permisos de usuario y de grupo**.</span><span class="sxs-lookup"><span data-stu-id="b62d0-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="b62d0-113">En la página **Usuarios** o **Grupos** , seleccione la fila para el usuario o grupo que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="b62d0-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="b62d0-114">Haga clic en **Editar usuario seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="b62d0-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="b62d0-115">Haga clic en la pestaña **Miembros de la jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="b62d0-115">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="b62d0-116">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="b62d0-116">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="b62d0-117">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="b62d0-117">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="b62d0-118">En la lista **Jerarquía** , seleccione una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="b62d0-118">From the **Hierarchy** list, select a hierarchy.</span></span>  
  
8.  <span data-ttu-id="b62d0-119">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b62d0-119">Click **Edit**.</span></span>  
  
9. <span data-ttu-id="b62d0-120">Expanda el árbol y haga clic en el nodo de la jerarquía al que desea asignar los permisos.</span><span class="sxs-lookup"><span data-stu-id="b62d0-120">Expand the tree, and click the hierarchy node you want to assign permissions to.</span></span>  
  
10. <span data-ttu-id="b62d0-121">En el menú, seleccione **solo lectura**, **Actualizar**o **denegar**.</span><span class="sxs-lookup"><span data-stu-id="b62d0-121">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
11. <span data-ttu-id="b62d0-122">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="b62d0-122">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b62d0-123">Los permisos de los miembros de la jerarquía no surten efecto inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="b62d0-123">Hierarchy member permissions do not take effect immediately.</span></span> <span data-ttu-id="b62d0-124">Consulte [Aplicar inmediatamente los permisos de los miembros &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b62d0-124">See [Immediately Apply Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62d0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b62d0-125">See Also</span></span>  
 <span data-ttu-id="b62d0-126">[Eliminar permisos de miembros de jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b62d0-126">[Delete Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="b62d0-127">[Asignar permisos de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b62d0-127">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="b62d0-128">Permisos de miembros de la jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b62d0-128">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
