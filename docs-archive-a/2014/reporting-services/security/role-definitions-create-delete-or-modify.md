---
title: Crear, eliminar o modificar un rol (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- deleting roles
- removing roles
- roles [Reporting Services], definitions
- modifying roles
- roles [Reporting Services], deleting
- roles [Reporting Services], modifying
ms.assetid: 3d1d56e6-a283-44a7-8417-36cb4d2c74d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 543bddda88e41af39d3200df4728716d46b3ae8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747966"
---
# <a name="create-delete-or-modify-a-role-management-studio"></a><span data-ttu-id="eae2d-102">Crear, eliminar o modificar un rol (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eae2d-102">Create, Delete, or Modify a Role (Management Studio)</span></span>
  <span data-ttu-id="eae2d-103">Reporting Services proporciona roles predefinidos que definen un nivel de acceso a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="eae2d-103">Reporting Services provides predefined roles that define a level of access to a report server.</span></span> <span data-ttu-id="eae2d-104">Cada usuario o grupo que requiere acceso al servidor de informes lo hace a través de un rol que describe las tareas que se pueden realizar.</span><span class="sxs-lookup"><span data-stu-id="eae2d-104">Each user or group who requires access to report server does so through a role that describes the tasks that can be performed.</span></span> <span data-ttu-id="eae2d-105">Los roles se definen para el servidor de informes como un conjunto.</span><span class="sxs-lookup"><span data-stu-id="eae2d-105">Roles are defined for the report server as a whole.</span></span> <span data-ttu-id="eae2d-106">No puede variar una definición de roles para partes concretas del servidor de informes ni especificar que se use un rol de manera diferente dependiendo de las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="eae2d-106">You cannot vary a role definition for specific parts of the report server, or specify that a role be used differently depending on the circumstances.</span></span>  
  
 <span data-ttu-id="eae2d-107">Para crear, modificar o eliminar roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eae2d-107">To create, modify, or delete roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="eae2d-108">Solo puede eliminar roles que no se usan.</span><span class="sxs-lookup"><span data-stu-id="eae2d-108">You can only delete roles that are not used.</span></span>  
  
 <span data-ttu-id="eae2d-109">Para asignar usuarios y grupos a los roles que crea, use el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="eae2d-109">To assign users and groups to the roles that you create, use Report Manager.</span></span> <span data-ttu-id="eae2d-110">Para obtener más información, vea [conceder a un usuario acceso a un servidor de informes &#40;Administrador de informes&#41;](grant-user-access-to-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="eae2d-110">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eae2d-111">Si el servidor de informes se configura para el modo integrado de SharePoint, y se conectó al sitio de SharePoint con el que se integra el servidor de informes, puede ver y modificar los niveles de permisos que controlan el acceso a las operaciones y el contenido del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="eae2d-111">If the report server is configured for SharePoint integrated mode, and you connected to the SharePoint site that the report server is integrated with, you can view and modify the permission levels that control access to report server content and operations.</span></span>  
  
### <a name="to-create-a-role-definition"></a><span data-ttu-id="eae2d-112">Para crear una definición de roles</span><span class="sxs-lookup"><span data-stu-id="eae2d-112">To create a role definition</span></span>  
  
1.  <span data-ttu-id="eae2d-113">En el Explorador de objetos, expanda un nodo de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="eae2d-113">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="eae2d-114">Expanda la carpeta Seguridad.</span><span class="sxs-lookup"><span data-stu-id="eae2d-114">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="eae2d-115">Si está creando una definición de roles de nivel de elemento, haga clic con el botón derecho en **Roles**y seleccione **Nuevo rol**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-115">If you are creating an item-level role definition, right-click **Roles**, and point to **New Role**.</span></span>  
  
     <span data-ttu-id="eae2d-116">O bien, si está creando una definición de roles de nivel de sistema, haga clic con el botón derecho en **Roles del sistema**y seleccione **Nuevo rol del sistema**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-116">Or, if you are creating a system-level role definition, right-click **System Roles**, and point to **New System Role**.</span></span>  
  
4.  <span data-ttu-id="eae2d-117">Escriba un nombre único para el rol.</span><span class="sxs-lookup"><span data-stu-id="eae2d-117">Type a unique name for the role.</span></span> <span data-ttu-id="eae2d-118">El nombre debe incluir al menos un carácter.</span><span class="sxs-lookup"><span data-stu-id="eae2d-118">A name must contain at least one character.</span></span> <span data-ttu-id="eae2d-119">También puede incluir espacios y determinados símbolos, pero no los caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="eae2d-119">It can also include spaces and certain symbols, but not the characters ; ?</span></span> <span data-ttu-id="eae2d-120">: \@ & = +, $/\* \< > | "o/.</span><span class="sxs-lookup"><span data-stu-id="eae2d-120">: \@ & = + , $ / \* \< > | " or /.</span></span>  
  
5.  <span data-ttu-id="eae2d-121">Si lo desea, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="eae2d-121">Optionally type a description.</span></span> <span data-ttu-id="eae2d-122">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , esta descripción solo resulta visible en esta página.</span><span class="sxs-lookup"><span data-stu-id="eae2d-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] this description is visible only on this page.</span></span> <span data-ttu-id="eae2d-123">Los usuarios que ven este elemento a través del Administrador de informes pueden ver esta descripción en esa herramienta.</span><span class="sxs-lookup"><span data-stu-id="eae2d-123">Users who view this item through Report Manager can see this description in that tool.</span></span>  
  
6.  <span data-ttu-id="eae2d-124">Seleccione las tareas que pueden realizar los miembros de este rol.</span><span class="sxs-lookup"><span data-stu-id="eae2d-124">Select the tasks that members of this role can perform.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-or-modify-a-role-definition"></a><span data-ttu-id="eae2d-125">Para eliminar o modificar una definición de roles</span><span class="sxs-lookup"><span data-stu-id="eae2d-125">To delete or modify a role definition</span></span>  
  
1.  <span data-ttu-id="eae2d-126">En el Explorador de objetos, expanda un nodo de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="eae2d-126">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="eae2d-127">Expanda la carpeta Seguridad.</span><span class="sxs-lookup"><span data-stu-id="eae2d-127">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="eae2d-128">Para eliminar o modificar una definición de roles de nivel de elemento, expanda la carpeta Roles.</span><span class="sxs-lookup"><span data-stu-id="eae2d-128">To delete or modify an item-level role definition, expand the Roles folder.</span></span> <span data-ttu-id="eae2d-129">Realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="eae2d-129">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="eae2d-130">Para eliminar una definición de roles, haga clic con el botón derecho en el elemento y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-130">To delete a role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="eae2d-131">Aparece el cuadro de diálogo **Eliminar objeto** .</span><span class="sxs-lookup"><span data-stu-id="eae2d-131">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="eae2d-132">Para modificar una definición de roles, haga clic con el botón derecho en el elemento y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-132">To modify a role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="eae2d-133">De este modo se muestra la página General del cuadro de diálogo **Propiedades de rol de usuario** .</span><span class="sxs-lookup"><span data-stu-id="eae2d-133">The General page of the **User Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="eae2d-134">Seleccione las tareas que pueden realizar los miembros de este rol y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-134">Select the tasks that members of this role can perform, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="eae2d-135">Para eliminar o modificar una definición de roles de nivel de sistema, expanda la carpeta **Roles del sistema** .</span><span class="sxs-lookup"><span data-stu-id="eae2d-135">To delete or modify a system-level role definition, expand the **System Roles** folder.</span></span> <span data-ttu-id="eae2d-136">Realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="eae2d-136">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="eae2d-137">Para eliminar una definición de roles de sistema, haga clic con el botón derecho en el elemento y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-137">To delete a system role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="eae2d-138">Aparece el cuadro de diálogo **Eliminar objeto** .</span><span class="sxs-lookup"><span data-stu-id="eae2d-138">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="eae2d-139">Para modificar una definición de rol de sistema, haga clic con el botón derecho en el elemento y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eae2d-139">To modify a system role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="eae2d-140">De este modo se muestra la página General del cuadro de diálogo **Propiedades de rol del sistema** .</span><span class="sxs-lookup"><span data-stu-id="eae2d-140">The General page of the **System Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="eae2d-141">Seleccione las tareas que pueden realizar los miembros de este rol y haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="eae2d-141">Select the tasks that members of this role can perform, and click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae2d-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eae2d-142">See Also</span></span>  
 <span data-ttu-id="eae2d-143">[Conectarse a un servidor de informes en Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="eae2d-143">[Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="eae2d-144">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="eae2d-144">(create-and-manage-role-assignments.md)</span></span>   
 [<span data-ttu-id="eae2d-145">Reporting Services en SQL Server Management Studio &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eae2d-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span></span>](../tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
  
