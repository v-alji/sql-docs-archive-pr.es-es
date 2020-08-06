---
title: 'Nuevas asignaciones de roles del sistema: página Editar asignaciones de roles del sistema (Administrador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e04ec18b8ee27c5897156753c1e4f7991991eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669495"
---
# <a name="new-system-role-assignments-edit-system-role-assignments-page-report-manager"></a><span data-ttu-id="a742b-102">Nueva asignación de roles del sistema y Editar asignaciones de roles del sistema (páginas del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="a742b-102">New System Role Assignments: Edit System Role Assignments Page (Report Manager)</span></span>
  <span data-ttu-id="a742b-103">Use la página Nueva asignación de roles del sistema o Editar asignaciones de roles del sistema para definir la seguridad del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a742b-103">Use the New System Role Assignments or Edit System Role Assignments page to define security for the report server.</span></span> <span data-ttu-id="a742b-104">Toda la seguridad se define a través de asignaciones de roles, que asocian usuarios o grupos específicos a las tareas que pueden realizar.</span><span class="sxs-lookup"><span data-stu-id="a742b-104">All security is defined through role assignments that map specific users or groups to the tasks that they can perform.</span></span> <span data-ttu-id="a742b-105">La lista de tareas se presenta como una definición de roles que se selecciona cuando se realiza una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="a742b-105">The task list is represented as a role definition that you select when making the role assignment.</span></span>  
  
 <span data-ttu-id="a742b-106">Las asignaciones de roles que se crean o modifican en el nivel de sistema se aplican al servidor de informes como un conjunto.</span><span class="sxs-lookup"><span data-stu-id="a742b-106">At the system level, the role assignments that you create or modify apply to the report server as a whole.</span></span> <span data-ttu-id="a742b-107">Por ejemplo, la posibilidad de crear programaciones compartidas se especifica en el nivel de sistema porque estas programaciones se utilizan en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="a742b-107">For example, the ability to create shared schedules is specified at the system level because shared schedules are used throughout the system.</span></span>  
  
 <span data-ttu-id="a742b-108">De forma predeterminada, Reporting Services proporciona dos roles del nivel de sistema predefinidos:</span><span class="sxs-lookup"><span data-stu-id="a742b-108">By default, Reporting Services provides two predefined system level roles:</span></span>  
  
-   <span data-ttu-id="a742b-109">Usuario del sistema incluye tareas que permiten a los usuarios ver las propiedades del servidor de informes y las programaciones compartidas, así como ejecutar definiciones de informe con las que los usuarios pueden ver los informes click-through que se han publicado en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a742b-109">System User includes tasks that allow users to view report server properties and shared schedules, and to execute report definitions, which allows users to view clickthrough reports that have been published to the report server.</span></span> <span data-ttu-id="a742b-110">A la mayoría de los usuarios deberían asignarse este rol.</span><span class="sxs-lookup"><span data-stu-id="a742b-110">Most users should be assigned to this role.</span></span>  
  
-   <span data-ttu-id="a742b-111">El Administrador del sistema incluye tareas para crear y administrar programaciones compartidas, establecer las propiedades del servidor y crear asignaciones de roles de nivel de sistema para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="a742b-111">System Administrator includes tasks for creating and managing shared schedules, setting server properties, and creating system-level role assignments for other users.</span></span> <span data-ttu-id="a742b-112">Pocos usuarios requieren permisos en este nivel.</span><span class="sxs-lookup"><span data-stu-id="a742b-112">Few users require permissions at this level.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="a742b-113">Navegación</span><span class="sxs-lookup"><span data-stu-id="a742b-113">Navigation</span></span>  
 <span data-ttu-id="a742b-114">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="a742b-114">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-system-role-assignments-or-edit-system-role-assignments-page"></a><span data-ttu-id="a742b-115">Para abrir la página Nueva asignación de roles del sistema o Editar asignaciones de roles del sistema</span><span class="sxs-lookup"><span data-stu-id="a742b-115">To open the New System Role Assignments or Edit System Role Assignments page</span></span>  
  
1.  <span data-ttu-id="a742b-116">Abra el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a742b-116">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="a742b-117">En la esquina superior derecha, haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="a742b-117">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="a742b-118">Esto abre la página de propiedades General del sitio.</span><span class="sxs-lookup"><span data-stu-id="a742b-118">This opens the General properties page for the site.</span></span>  
  
3.  <span data-ttu-id="a742b-119">Seleccione la pestaña **seguridad** . Debe disponer de permisos de administrador de contenido y administrador del sistema para tener acceso a esta página.</span><span class="sxs-lookup"><span data-stu-id="a742b-119">Select the **Security** tab. You must have Content Manager and System Administrator permissions to access this page.</span></span>  
  
4.  <span data-ttu-id="a742b-120">Para crear una nueva asignación de roles, haga clic en **Nueva asignación de roles** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a742b-120">To create a new role assignment, click **New Role Assignment** in the toolbar.</span></span> <span data-ttu-id="a742b-121">Para editar una asignación de roles existente, haga clic en **Editar** junto a un grupo o usuario en la página de propiedades Seguridad.</span><span class="sxs-lookup"><span data-stu-id="a742b-121">To edit an existing role assignment, click **Edit** next to a group or user on the Security properties page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a742b-122">Opciones</span><span class="sxs-lookup"><span data-stu-id="a742b-122">Options</span></span>  
 <span data-ttu-id="a742b-123">**Grupo o usuario**</span><span class="sxs-lookup"><span data-stu-id="a742b-123">**Group or User**</span></span>  
 <span data-ttu-id="a742b-124">Escriba el nombre de una cuenta de usuario o grupo de su dominio.</span><span class="sxs-lookup"><span data-stu-id="a742b-124">Type the name of a group or user account in your domain.</span></span> <span data-ttu-id="a742b-125">Si el servidor de informes se ejecuta con una cuenta local, debe especificar usuarios o grupos locales.</span><span class="sxs-lookup"><span data-stu-id="a742b-125">If the report server is running under a local account, you must specify local groups or users.</span></span> <span data-ttu-id="a742b-126">Si el servidor de informes se ejecuta con una cuenta de dominio, debe especificar usuarios o grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="a742b-126">If the report server is running under a domain account, you must specify domain groups or users.</span></span> <span data-ttu-id="a742b-127">Escriba la cuenta con este formato: \<domain> \\<cuenta \> .</span><span class="sxs-lookup"><span data-stu-id="a742b-127">Enter the account in this format: \<domain>\\<account\>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a742b-128">Este cuadro solo está disponible en la página Nueva asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="a742b-128">This box is available only on the New Role Assignment page.</span></span>  
  
 <span data-ttu-id="a742b-129">**Roles**</span><span class="sxs-lookup"><span data-stu-id="a742b-129">**Roles**</span></span>  
 <span data-ttu-id="a742b-130">Proporciona una lista de roles del nivel del sistema que puede asignar a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="a742b-130">Provides a list of system-level roles that you can assign to other users.</span></span> <span data-ttu-id="a742b-131">Puede especificar varios roles para una asignación de roles única.</span><span class="sxs-lookup"><span data-stu-id="a742b-131">You can specify multiple roles for a single role assignment.</span></span>  
  
 <span data-ttu-id="a742b-132">El Administrador de informes no muestra las tareas en cada rol ni proporciona una manera de agregar o modificar las tareas.</span><span class="sxs-lookup"><span data-stu-id="a742b-132">Report Manager does not display the tasks in each role or provide a way to add or modify the tasks.</span></span> <span data-ttu-id="a742b-133">Debe usar los roles como se definen.</span><span class="sxs-lookup"><span data-stu-id="a742b-133">You must use the roles as they are defined.</span></span> <span data-ttu-id="a742b-134">Para crear, modificar o eliminar roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a742b-134">To create, modify, or delete roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="a742b-135">Para más información, consulte [Crear, eliminar o modificar un rol &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span><span class="sxs-lookup"><span data-stu-id="a742b-135">For more information, see [Create, Delete, or Modify a Role &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span></span>  
  
 <span data-ttu-id="a742b-136">Tenga en cuenta que si está usando [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] con Advanced Services, debe usar los roles predeterminados proporcionados.</span><span class="sxs-lookup"><span data-stu-id="a742b-136">Note that if you are using [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, you must use the default roles that are provided.</span></span>  
  
 <span data-ttu-id="a742b-137">**Descripciones**</span><span class="sxs-lookup"><span data-stu-id="a742b-137">**Descriptions**</span></span>  
 <span data-ttu-id="a742b-138">Muestra información adicional sobre el rol.</span><span class="sxs-lookup"><span data-stu-id="a742b-138">Shows additional information about the role.</span></span> <span data-ttu-id="a742b-139">En el caso de los roles predefinidos, como Usuario del sistema o Administrador del sistema, la descripción es un resumen de las tareas que admite cada rol.</span><span class="sxs-lookup"><span data-stu-id="a742b-139">For predefined roles such as System User or System Administrator, the description summarizes the tasks that each role supports.</span></span>  
  
 <span data-ttu-id="a742b-140">**Eliminar asignación de roles**</span><span class="sxs-lookup"><span data-stu-id="a742b-140">**Delete Role Assignment**</span></span>  
 <span data-ttu-id="a742b-141">Haga clic para eliminar una asignación de roles existente correspondiente a un usuario o a un grupo.</span><span class="sxs-lookup"><span data-stu-id="a742b-141">Click to delete an existing role assignment for a user or a group.</span></span> <span data-ttu-id="a742b-142">Una asignación de roles no se puede eliminar si es la única que queda, ya que cada elemento debe tener, como mínimo, una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="a742b-142">You cannot delete a role assignment if it is the only one left (each item must have a minimum of one role assignment).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a742b-143">Este botón solo está disponible en la página Editar asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="a742b-143">This button is available only on the Edit Role Assignment page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a742b-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a742b-144">See Also</span></span>  
 <span data-ttu-id="a742b-145">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a742b-145">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="a742b-146">[Asignaciones de roles](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="a742b-146">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="a742b-147">Definiciones de roles</span><span class="sxs-lookup"><span data-stu-id="a742b-147">Role Definitions</span></span>](security/role-definitions.md)  
  
  
