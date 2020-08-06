---
title: Propiedades de rol de usuario (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f79953abdf5e3d1cdb03de8c5feeb6b2de34ab7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746116"
---
# <a name="user-role-properties-management-studio"></a><span data-ttu-id="e5063-102">Propiedades de rol de usuario (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e5063-102">User Role Properties (Management Studio)</span></span>
  <span data-ttu-id="e5063-103">Use esta página para ver qué tareas se incluyen en una definición de roles de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="e5063-103">Use this page to view which tasks are included in an item-level role definition.</span></span> <span data-ttu-id="e5063-104">También puede usar esta página para cambiar la lista de tareas o modificar una descripción de roles.</span><span class="sxs-lookup"><span data-stu-id="e5063-104">You can also use this page to change the task list or modify a role description.</span></span>  
  
 <span data-ttu-id="e5063-105">Una definición de roles de nivel de elemento es una colección con nombre de las tareas que realizan los usuarios respecto a un elemento determinado, es decir, una carpeta, un informe, un recurso o un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="e5063-105">An item-level role definition is a named collection of tasks that users perform relative to a specific item (that is, a folder, report, resource, or shared data source).</span></span> <span data-ttu-id="e5063-106">Las definiciones de roles se asignan a un usuario o grupo para crear una asignación de roles en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="e5063-106">Role definitions are assigned to a user or group to create a role assignment in Report Manager.</span></span> <span data-ttu-id="e5063-107">Las tareas de la definición de roles describen lo que puede hacer el usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="e5063-107">The tasks in the role definition describe what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e5063-108">incluye varias definiciones de roles de nivel de elemento predeterminadas con las que podrá trabajar.</span><span class="sxs-lookup"><span data-stu-id="e5063-108">includes a number of predefined item-level role definitions that you can work with.</span></span> <span data-ttu-id="e5063-109">Puede modificar las definiciones de roles cambiando la lista de tareas de cada una.</span><span class="sxs-lookup"><span data-stu-id="e5063-109">You can modify the role definitions by changing the task list of each one.</span></span> <span data-ttu-id="e5063-110">Al editar una definición de roles, todas las asignaciones de roles que la incluyan se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="e5063-110">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5063-111">Las asignaciones de roles de usuario solo se usan en un servidor de informes que se ejecuta en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="e5063-111">User role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="e5063-112">Si el servidor de informes se configura para la integración con SharePoint, esta página muestra la información de solo lectura sobre los roles y los niveles de permisos que se definen en el sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e5063-112">If the report server is configured for SharePoint integration, this page displays read-only information about the roles and permission levels that are defined on the SharePoint site.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5063-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="e5063-113">Options</span></span>  
 <span data-ttu-id="e5063-114">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e5063-114">**Name**</span></span>  
 <span data-ttu-id="e5063-115">Especifica el nombre de la definición de roles.</span><span class="sxs-lookup"><span data-stu-id="e5063-115">Specifies the name of the role definition.</span></span>  
  
 <span data-ttu-id="e5063-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e5063-116">**Description**</span></span>  
 <span data-ttu-id="e5063-117">Muestra una descripción de la definición de roles.</span><span class="sxs-lookup"><span data-stu-id="e5063-117">Shows a description of the role definition.</span></span> <span data-ttu-id="e5063-118">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], esta descripción solo resulta visible en esta página.</span><span class="sxs-lookup"><span data-stu-id="e5063-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="e5063-119">En el Administrador de informes, esta descripción ayuda a los usuarios a decidir si desean usar el rol en una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="e5063-119">In Report Manager, this description helps users decide whether to use the role in a role assignment.</span></span>  
  
 <span data-ttu-id="e5063-120">**Task**</span><span class="sxs-lookup"><span data-stu-id="e5063-120">**Task**</span></span>  
 <span data-ttu-id="e5063-121">Muestra todas las tareas de nivel de elemento que pueden seleccionarse para esta definición de roles.</span><span class="sxs-lookup"><span data-stu-id="e5063-121">Lists all item-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="e5063-122">Puede agregar o quitar elementos de la lista de tareas predefinidas para definir el modo en que los usuarios tienen acceso a un elemento dado a través de ese rol.</span><span class="sxs-lookup"><span data-stu-id="e5063-122">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="e5063-123">No puede crear nuevas tareas y no puede modificar tareas existentes.</span><span class="sxs-lookup"><span data-stu-id="e5063-123">You cannot create new tasks, and you cannot modify existing tasks.</span></span> <span data-ttu-id="e5063-124">La lista de tareas de una definición de roles solo aparece en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5063-124">The task list of a role definition appears only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e5063-125">**Descripción de la tarea**</span><span class="sxs-lookup"><span data-stu-id="e5063-125">**Task Description**</span></span>  
 <span data-ttu-id="e5063-126">Proporciona información sobre cada tarea.</span><span class="sxs-lookup"><span data-stu-id="e5063-126">Provides information about each task.</span></span> <span data-ttu-id="e5063-127">No puede modificar descripciones de tareas.</span><span class="sxs-lookup"><span data-stu-id="e5063-127">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5063-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5063-128">See Also</span></span>  
 <span data-ttu-id="e5063-129">[Tareas de nivel de elemento](../security/tasks-and-permissions-item-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e5063-129">[Item-Level Tasks](../security/tasks-and-permissions-item-level-tasks.md) </span></span>  
 <span data-ttu-id="e5063-130">[Definiciones de roles](../security/role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="e5063-130">[Role Definitions](../security/role-definitions.md) </span></span>  
 <span data-ttu-id="e5063-131">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e5063-131">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="e5063-132">[Tareas y permisos](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="e5063-132">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="e5063-133">Roles predefinidos</span><span class="sxs-lookup"><span data-stu-id="e5063-133">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
