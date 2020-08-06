---
title: Página de propiedades de seguridad, elementos (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 351b8503-354f-4b1b-a7ac-f1245d978da0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 297ae2ceefad89d64c59b5da25d51d541917c894
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671364"
---
# <a name="security-properties-page-items-report-manager"></a><span data-ttu-id="0aa57-102">Página de propiedades de seguridad, elementos (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="0aa57-102">Security Properties Page, Items (Report Manager)</span></span>
  <span data-ttu-id="0aa57-103">Use la página Propiedades de seguridad para ver o modificar la configuración de seguridad que determina el acceso a carpetas, informes, modelos, recursos y orígenes de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="0aa57-103">Use the Security properties page to view or modify the security settings that determine access to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="0aa57-104">Esta página está disponible para los elementos para los que tenga permiso de protección.</span><span class="sxs-lookup"><span data-stu-id="0aa57-104">This page is available for items that you have permission to secure.</span></span>  
  
 <span data-ttu-id="0aa57-105">El acceso a los elementos se define a través de asignaciones de roles, que especifican las tareas que puede realizar un grupo o usuario.</span><span class="sxs-lookup"><span data-stu-id="0aa57-105">Access to items is defined through role assignments that specify the tasks that a group or user can perform.</span></span> <span data-ttu-id="0aa57-106">Una asignación de roles consta de un nombre de usuario o grupo y de una o varias definiciones de roles que especifican un conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="0aa57-106">A role assignment consists of one user or group name and one or more role definitions that specify a collection of tasks.</span></span>  
  
 <span data-ttu-id="0aa57-107">La configuración de seguridad se hereda de la carpeta raíz a las subcarpetas y los elementos que contienen.</span><span class="sxs-lookup"><span data-stu-id="0aa57-107">Security settings are inherited from the root folder down to subfolders and items within those folders.</span></span> <span data-ttu-id="0aa57-108">A menos que se anule explícitamente la herencia de la seguridad, las subcarpetas y los elementos heredan el contexto de seguridad de un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="0aa57-108">Unless you explicitly break inherited security, subfolders and items inherit the security context of a parent item.</span></span> <span data-ttu-id="0aa57-109">Si se redefine una directiva de seguridad para una carpeta situada en la mitad de la jerarquía, todos los elementos secundarios, incluidas las subcarpetas, adoptarán la nueva configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0aa57-109">If you redefine a security policy for a folder in the middle of the hierarchy, all its child items, including subfolders, assume the new security settings.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="0aa57-110">Navegación</span><span class="sxs-lookup"><span data-stu-id="0aa57-110">Navigation</span></span>  
 <span data-ttu-id="0aa57-111">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="0aa57-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-security-page-for-an-item"></a><span data-ttu-id="0aa57-112">Para abrir la página Seguridad de un elemento</span><span class="sxs-lookup"><span data-stu-id="0aa57-112">To open the Security page for an item</span></span>  
  
1.  <span data-ttu-id="0aa57-113">Abra el Administrador de informes y busque el elemento para el que desea establecer la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0aa57-113">Open Report Manager, and locate the item for which you want to configure security settings.</span></span>  
  
2.  <span data-ttu-id="0aa57-114">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0aa57-114">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="0aa57-115">En el menú desplegable, efectúe uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0aa57-115">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="0aa57-116">Haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0aa57-116">Click **Security**.</span></span> <span data-ttu-id="0aa57-117">Se abrirá la página de propiedades Seguridad para el elemento.</span><span class="sxs-lookup"><span data-stu-id="0aa57-117">This opens the Security properties page for the item.</span></span>  
  
    -   <span data-ttu-id="0aa57-118">Haga clic en **Administrar** para abrir la página de propiedades General del elemento.</span><span class="sxs-lookup"><span data-stu-id="0aa57-118">Click **Manage** to open the General properties page for the item.</span></span> <span data-ttu-id="0aa57-119">A continuación, seleccione la pestaña **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="0aa57-119">Then select the **Security** tab.</span></span>  
  
 <span data-ttu-id="0aa57-120">**Editar seguridad del elemento**</span><span class="sxs-lookup"><span data-stu-id="0aa57-120">**Edit Item Security**</span></span>  
 <span data-ttu-id="0aa57-121">Haga clic para cambiar la manera en la que se define la seguridad para el elemento actual.</span><span class="sxs-lookup"><span data-stu-id="0aa57-121">Click to change how security is defined for the current item.</span></span> <span data-ttu-id="0aa57-122">Si va a modificar la seguridad de una carpeta, los cambios se aplicarán al contenido de la carpeta actual y a todas sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0aa57-122">If you are editing security for a folder, your changes apply to the contents of the current folder and any subfolders.</span></span>  
  
 <span data-ttu-id="0aa57-123">Este botón no está disponible para la carpeta Inicio.</span><span class="sxs-lookup"><span data-stu-id="0aa57-123">This button is not available for the Home folder.</span></span>  
  
 <span data-ttu-id="0aa57-124">Los botones siguientes están disponibles cuando se edita la seguridad de un elemento.</span><span class="sxs-lookup"><span data-stu-id="0aa57-124">The following buttons become available when you edit item security.</span></span>  
  
 <span data-ttu-id="0aa57-125">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="0aa57-125">**Delete**</span></span>  
 <span data-ttu-id="0aa57-126">Active la casilla situada al lado del nombre de usuario o grupo que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0aa57-126">Select the check box next to the group or user name that you want to delete and click **Delete**.</span></span> <span data-ttu-id="0aa57-127">No se puede eliminar una asignación de roles si es la única que queda o si es una asignación de roles integrada, como "Built-in\Administradores", que define la línea base de la seguridad del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="0aa57-127">You cannot delete a role assignment if it is the only one remaining, or if it is a built-in role assignment (for example, "Built-in\Administrators") that defines the security baseline for the report server.</span></span> <span data-ttu-id="0aa57-128">Si se elimina una asignación de roles, no se elimina la cuenta de usuario o grupo ni las definiciones de roles.</span><span class="sxs-lookup"><span data-stu-id="0aa57-128">Deleting a role assignment does not delete a group or user account or role definitions.</span></span>  
  
 <span data-ttu-id="0aa57-129">**Nueva asignación de roles**</span><span class="sxs-lookup"><span data-stu-id="0aa57-129">**New Role Assignment**</span></span>  
 <span data-ttu-id="0aa57-130">Haga clic para abrir la página Nueva asignación de roles, que se usa para crear más asignaciones de roles para el elemento actual.</span><span class="sxs-lookup"><span data-stu-id="0aa57-130">Click to open the New Role Assignment page, which is used to create additional role assignments for the current item.</span></span> <span data-ttu-id="0aa57-131">Para obtener más información, consulte [nueva asignación de roles: página Editar asignación de roles &#40;Administrador de informes&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="0aa57-131">For more information, see [New Role Assignment: Edit Role Assignment Page &#40;Report Manager&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="0aa57-132">**Volver a la seguridad del elemento primario**</span><span class="sxs-lookup"><span data-stu-id="0aa57-132">**Revert to Parent Security**</span></span>  
 <span data-ttu-id="0aa57-133">Haga clic para restablecer la configuración de seguridad a la de la carpeta primaria inmediata.</span><span class="sxs-lookup"><span data-stu-id="0aa57-133">Click to reset the security settings to that of the immediate parent folder.</span></span> <span data-ttu-id="0aa57-134">Si la herencia permanece intacta en toda la jerarquía de carpetas del servidor de informes, se utiliza la configuración de seguridad de la carpeta de nivel superior, Inicio.</span><span class="sxs-lookup"><span data-stu-id="0aa57-134">If inheritance is unbroken throughout the report server folder hierarchy, the security settings of the top-level folder, Home, are used.</span></span>  
  
 <span data-ttu-id="0aa57-135">**Grupo o usuario**</span><span class="sxs-lookup"><span data-stu-id="0aa57-135">**Group or User**</span></span>  
 <span data-ttu-id="0aa57-136">Muestra los grupos y usuarios que forman parte de una asignación de roles existente para el elemento actual.</span><span class="sxs-lookup"><span data-stu-id="0aa57-136">Lists the groups and users that are part of an existing role assignment for the current item.</span></span> <span data-ttu-id="0aa57-137">Se han definido las asignaciones de roles existentes para la carpeta actual de los grupos y usuarios que se muestran en esta columna.</span><span class="sxs-lookup"><span data-stu-id="0aa57-137">Existing role assignments for the current folder are defined for the groups and users that appear in this column.</span></span> <span data-ttu-id="0aa57-138">Puede hacer clic en un nombre de usuario o grupo para ver o editar los detalles de las asignaciones de roles.</span><span class="sxs-lookup"><span data-stu-id="0aa57-138">You can click a group or user name to view or edit role assignment details.</span></span>  
  
 <span data-ttu-id="0aa57-139">**Roles**</span><span class="sxs-lookup"><span data-stu-id="0aa57-139">**Roles**</span></span>  
 <span data-ttu-id="0aa57-140">Muestra una o varias definiciones de roles que son parte de una asignación de roles existente.</span><span class="sxs-lookup"><span data-stu-id="0aa57-140">Lists one or more role definitions that are part of an existing role assignment.</span></span> <span data-ttu-id="0aa57-141">Si se asignan varios roles a una cuenta de usuario o grupo, ese usuario o grupo puede realizar todas las tareas que pertenecen a todos esos roles.</span><span class="sxs-lookup"><span data-stu-id="0aa57-141">If multiple roles are assigned to a group or user account, that group or user can perform all tasks that belong to those roles.</span></span> <span data-ttu-id="0aa57-142">Para ver las tareas asociadas a un rol, use SQL Server Management Studio para ver las tareas de cada definición de rol.</span><span class="sxs-lookup"><span data-stu-id="0aa57-142">To view the tasks that are associated with a role, use SQL Server Management Studio to view the tasks in each role definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa57-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0aa57-143">See Also</span></span>  
 <span data-ttu-id="0aa57-144">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0aa57-144">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="0aa57-145">[Roles predefinidos](security/role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="0aa57-145">[Predefined Roles](security/role-definitions-predefined-roles.md) </span></span>  
 <span data-ttu-id="0aa57-146">[Conceder permisos en un servidor de informes en modo nativo](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="0aa57-146">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="0aa57-147">[Asignaciones de roles](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="0aa57-147">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="0aa57-148">Definiciones de roles</span><span class="sxs-lookup"><span data-stu-id="0aa57-148">Role Definitions</span></span>](security/role-definitions.md)  
  
  
