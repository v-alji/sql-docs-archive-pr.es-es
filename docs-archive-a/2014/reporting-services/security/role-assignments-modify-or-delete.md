---
title: Modificar o eliminar una asignación de roles (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d67c5cdb7647d50008f72890e4ac3e3c7eed456e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746154"
---
# <a name="modify-or-delete-a-role-assignment-report-manager"></a><span data-ttu-id="276e6-102">Modificar o eliminar una asignación de roles (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="276e6-102">Modify or Delete a Role Assignment (Report Manager)</span></span>
  <span data-ttu-id="276e6-103">Una asignación de roles asigna un grupo o cuenta de usuario a una definición de roles predefinida que incluye tareas que se pueden realizar.</span><span class="sxs-lookup"><span data-stu-id="276e6-103">A role assignment maps a group or user account to a predefined role definition that includes tasks that can be performed.</span></span> <span data-ttu-id="276e6-104">Determina los tipos de operaciones que un usuario puede realizar con relación a una carpeta, informe, modelo u otro tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="276e6-104">It determines the types of operations that a user can perform relative to a folder, report, model, or other content type.</span></span> <span data-ttu-id="276e6-105">Para crear, modificar o eliminar asignaciones de roles, use el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="276e6-105">To create, modify, or delete role assignments, you use Report Manager.</span></span> <span data-ttu-id="276e6-106">Después de crear una asignación de roles para un grupo o usuario concreto, puede modificarla posteriormente seleccionando un rol diferente.</span><span class="sxs-lookup"><span data-stu-id="276e6-106">After you create a role assignment for a particular user or group, you can modify it later by selecting a different role.</span></span> <span data-ttu-id="276e6-107">Si desea revocar los permisos a un servidor de informes, puede eliminar una asignación de roles del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="276e6-107">If you want to revoke permissions to a report server, you can delete a role assignment from the report server.</span></span>  
  
 <span data-ttu-id="276e6-108">Dependiendo de su objetivo, los enfoques alternativos podrían ser más adecuados.</span><span class="sxs-lookup"><span data-stu-id="276e6-108">Depending on your objective, alternative approaches might be more appropriate.</span></span> <span data-ttu-id="276e6-109">Entre los ejemplos se incluyen la personalización o la creación de una nueva definición de roles, o la modificación de la pertenencia de una cuenta de grupo en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="276e6-109">Examples include customizing or creating a new role definition, or modifying the membership of a group account in Active Directory.</span></span>  
  
 <span data-ttu-id="276e6-110">Por ejemplo, supongamos que tiene un grupo de usuarios que necesitan administrar su contenido totalmente, pero que no deberían tener el conjunto completo de permisos asociado al Administrador de contenido.</span><span class="sxs-lookup"><span data-stu-id="276e6-110">For example, suppose you have a group of users who need to fully manage their content, but should not have the full set of permissions associated with Content Manager.</span></span> <span data-ttu-id="276e6-111">En este caso, podría crear una nueva definición de roles denominada Administrador de contenido del departamento que incluye todas las tareas en Administrador de contenido excepto **Establecer directivas de seguridad para elementos**.</span><span class="sxs-lookup"><span data-stu-id="276e6-111">In this case, you could create a new role definition called Department Content Manager that includes all of the tasks in Content Manager except **Set security policies for items**.</span></span>  
  
 <span data-ttu-id="276e6-112">Del mismo modo, si es un administrador de red o del sistema, y es más sencillo para usted administrar las cuentas de grupo de Active Directory que las asignaciones de roles en el Administrador de informes, podría reducir la sobrecarga de administrar asignaciones de roles creando una asignación de roles única para una cuenta de grupo y ajustar a continuación la pertenencia a grupo cuando los usuarios ya no requieren el acceso a los informes.</span><span class="sxs-lookup"><span data-stu-id="276e6-112">Similarly, if you are a system or network administrator and it is easier for you to manage Active Directory group accounts than role assignments in Report Manager, you could reduce the overhead of managing role assignments by creating a single role assignment for a group account, and then adjust group membership when users no longer require access to reports.</span></span>  
  
 <span data-ttu-id="276e6-113">Si determina que el mejor enfoque es la modificación o la eliminación de una asignación de roles, recuerde comprobar las asignaciones de roles del sistema y las asignaciones de roles del elemento.</span><span class="sxs-lookup"><span data-stu-id="276e6-113">If you determine that modifying or deleting a role assignment is the best approach, remember to check for both system role assignments and item role assignments.</span></span> <span data-ttu-id="276e6-114">Cada tipo de asignación de roles se configura a través de páginas diferentes del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="276e6-114">Each type of role assignment is configured through different pages in Report Manager.</span></span>  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a><span data-ttu-id="276e6-115">Para modificar o eliminar una asignación de roles del sistema</span><span class="sxs-lookup"><span data-stu-id="276e6-115">To modify or delete a system role assignment</span></span>  
  
1.  <span data-ttu-id="276e6-116">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="276e6-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="276e6-117">Haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="276e6-117">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="276e6-118">Haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="276e6-118">Click **Security**.</span></span> <span data-ttu-id="276e6-119">Todas las asignaciones de roles del nivel de sistema definidas actualmente para el servidor o la implementación escalada aparecen enumeradas por nombre de cuenta.</span><span class="sxs-lookup"><span data-stu-id="276e6-119">All system-level role assignments currently defined for the server or scale-out deployment are listed by account name.</span></span>  
  
4.  <span data-ttu-id="276e6-120">Busque la asignación de rol que desea modificar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="276e6-120">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="276e6-121">Para agregar o quitar el rol para un usuario o grupo determinado, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="276e6-121">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="276e6-122">Para eliminar una asignación de rol, active la casilla situada junto al nombre de usuario o grupo y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="276e6-122">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a><span data-ttu-id="276e6-123">Para modificar o eliminar una asignación de roles de elemento</span><span class="sxs-lookup"><span data-stu-id="276e6-123">To modify or delete an item role assignment</span></span>  
  
1.  <span data-ttu-id="276e6-124">Inicie el **Administrador de informes** y busque el elemento para el que desea modificar o eliminar una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="276e6-124">Start **Report Manager** and locate the item for which you want to edit or delete a role assignment.</span></span>  
  
2.  <span data-ttu-id="276e6-125">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="276e6-125">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="276e6-126">En el menú desplegable, haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="276e6-126">In the drop-down menu, click **Security**.</span></span>  
  
4.  <span data-ttu-id="276e6-127">Busque la asignación de rol que desea modificar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="276e6-127">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="276e6-128">Para agregar o quitar el rol para un usuario o grupo determinado, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="276e6-128">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="276e6-129">Para eliminar una asignación de rol, active la casilla situada junto al nombre de usuario o grupo y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="276e6-129">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276e6-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="276e6-130">See Also</span></span>  
 <span data-ttu-id="276e6-131">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="276e6-131">(create-and-manage-role-assignments.md)</span></span>   
 <span data-ttu-id="276e6-132">[Asignaciones de roles](role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="276e6-132">[Role Assignments](role-assignments.md) </span></span>  
 <span data-ttu-id="276e6-133">[&#40;Administrador de informes página Configuración del sitio&#41;](../site-settings-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="276e6-133">[Site Settings Page &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span></span>  
 [<span data-ttu-id="276e6-134">Nueva asignación de roles del sistema y Editar asignaciones de roles del sistema &#40;páginas del Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="276e6-134">New System Role Assignments: Edit System Role Assignments Page &#40;Report Manager&#41;</span></span>](../new-system-role-assignments-edit-system-role-assignments-page-report-manager.md)  
  
  
