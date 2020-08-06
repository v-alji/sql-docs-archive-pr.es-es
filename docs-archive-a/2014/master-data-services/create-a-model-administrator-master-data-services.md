---
title: Crear un administrador de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 24efc3961e6ed5b9f41b2321dfcc4fbf16632270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677749"
---
# <a name="create-a-model-administrator-master-data-services"></a><span data-ttu-id="a4ccf-102">Crear un administrador de modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a4ccf-102">Create a Model Administrator (Master Data Services)</span></span>
  <span data-ttu-id="a4ccf-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , cree un administrador de modelo cuando desee que un grupo o usuario tenga el permiso **Actualizar** para todos los objetos de uno o varios modelos.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model administrator when you want a group or user to have **Update** permission to all objects in one or more models.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a4ccf-104">Para simplificar la administración, cree un grupo local o de Windows y configúrelo como administrador del modelo.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-104">To simplify administration, create a Windows or local group and configure it as a model administrator.</span></span> <span data-ttu-id="a4ccf-105">Puede agregar usuarios al grupo y quitarlos a continuación sin tener acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4ccf-105">You can then add and remove users from the group without accessing [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4ccf-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a4ccf-106">Prerequisites</span></span>  
 <span data-ttu-id="a4ccf-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="a4ccf-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a4ccf-108">Debe disponer de permiso para tener acceso al área funcional **Permisos de usuario y de grupo** .</span><span class="sxs-lookup"><span data-stu-id="a4ccf-108">You must have permission to access the **User and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="a4ccf-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-109">You must be a model administrator.</span></span> <span data-ttu-id="a4ccf-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4ccf-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-administrator"></a><span data-ttu-id="a4ccf-111">Para crear un administrador de modelo</span><span class="sxs-lookup"><span data-stu-id="a4ccf-111">To create a model administrator</span></span>  
  
1.  <span data-ttu-id="a4ccf-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Permisos de usuario y de grupo**.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="a4ccf-113">En la página **Usuarios** o **Grupos** , seleccione la fila para el usuario o grupo que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="a4ccf-114">Haga clic en **Editar usuario seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="a4ccf-115">Haga clic en la pestaña **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="a4ccf-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="a4ccf-116">Si lo desea, seleccione un modelo en la lista desplegable **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="a4ccf-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="a4ccf-117">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="a4ccf-118">Haga clic en el modelo al que desea conceder el permiso.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-118">Click the model you want to grant permission to.</span></span>  
  
8.  <span data-ttu-id="a4ccf-119">En el menú, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-119">From the menu, select **Update**.</span></span>  
  
9. <span data-ttu-id="a4ccf-120">Complete los pasos 7 y 8 con cada modelo para el que desee que administren el grupo o el usuario.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-120">Complete steps 7 and 8 for each model you want the group or user to be an administrator for.</span></span>  
  
10. <span data-ttu-id="a4ccf-121">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="a4ccf-121">Click **Save**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4ccf-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a4ccf-122">Remarks</span></span>  
 <span data-ttu-id="a4ccf-123">No asigne ningún otro permiso para los objetos de modelo o los miembros de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-123">Do not assign any other permissions to model objects or hierarchy members.</span></span> <span data-ttu-id="a4ccf-124">Si lo hace, el usuario ya no es un administrador y no puede ver el modelo en ningún área funcional que no sea el **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-124">If you do, the user is no longer an administrator and cannot view the model in any functional area other than **Explorer**.</span></span>  
  
 <span data-ttu-id="a4ccf-125">Existe una excepción: Si el usuario tiene el permiso **Actualizar** asignado a una **raíz** de jerarquía en la pestaña miembros de la **jerarquía** , el usuario se considera un administrador del modelo.</span><span class="sxs-lookup"><span data-stu-id="a4ccf-125">There is one exception: if the user has **Update** permission assigned to a hierarchy **Root** on the **Hierarchy Members** tab, the user is still considered a model administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ccf-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4ccf-126">See Also</span></span>  
 <span data-ttu-id="a4ccf-127">[Administradores &#40;Master Data Services&#41;](administrators-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a4ccf-127">[Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md) </span></span>  
 <span data-ttu-id="a4ccf-128">[Asignar permisos de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a4ccf-128">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="a4ccf-129">[Asignar permisos de miembro de jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a4ccf-129">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="a4ccf-130">[Permisos del objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a4ccf-130">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="a4ccf-131">Permisos de miembros de la jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a4ccf-131">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
