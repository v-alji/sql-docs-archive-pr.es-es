---
title: Propiedades de rol del sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.systemroleproperties.f1
ms.assetid: 0210fc2a-74fb-41dd-8e39-4830047ec417
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b37ebb1cb95d6628884d81156c9c1bc29bff86fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670253"
---
# <a name="system-role-properties-management-studio"></a><span data-ttu-id="7802f-102">Propiedades de rol del sistema (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7802f-102">System Role Properties (Management Studio)</span></span>
  <span data-ttu-id="7802f-103">Use la página Roles del sistema para ver las definiciones de roles del sistema actualmente definidas para el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7802f-103">Use the System Roles page to view the system role definitions that are currently defined for the report server.</span></span> <span data-ttu-id="7802f-104">Una definición de roles del sistema contiene una colección con nombre de tareas que se realizan en relación con el sitio completo, en lugar de un elemento individual.</span><span class="sxs-lookup"><span data-stu-id="7802f-104">A system role definition contains a named collection of tasks that are performed relative to the entire site, instead of an individual item.</span></span> <span data-ttu-id="7802f-105">Las definiciones de roles se asignan a un usuario o grupos para crear una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="7802f-105">Role definitions are assigned to a user or groups to create a resulting role assignment.</span></span> <span data-ttu-id="7802f-106">Las tareas de la definición de roles especifican lo que puede hacer el usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="7802f-106">The tasks in the role definition specify what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="7802f-107">tiene dos definiciones de roles del sistema predefinidos: **Administrador del sistema** y **Usuario del sistema**.</span><span class="sxs-lookup"><span data-stu-id="7802f-107">has two predefined system role definitions: **System Administrator** and **System User**.</span></span> <span data-ttu-id="7802f-108">Las definiciones de estos roles se pueden modificar cambiando la lista de tareas, o bien, se puede crear un nuevo rol del sistema que admita una combinación distinta de tareas.</span><span class="sxs-lookup"><span data-stu-id="7802f-108">You can modify these role definitions by changing the task list, or you can create a new system role that supports a different combination of tasks.</span></span> <span data-ttu-id="7802f-109">Al editar una definición de roles, todas las asignaciones de roles que la incluyan se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="7802f-109">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7802f-110">Las asignaciones de roles del sistema solamente se usan en un servidor de informes que se ejecuta en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="7802f-110">System role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="7802f-111">Si el servidor de informes está configurado para la integración con SharePoint, esta página no está disponible.</span><span class="sxs-lookup"><span data-stu-id="7802f-111">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7802f-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="7802f-112">Options</span></span>  
 <span data-ttu-id="7802f-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7802f-113">**Name**</span></span>  
 <span data-ttu-id="7802f-114">Especifica el nombre de la definición de roles del sistema.</span><span class="sxs-lookup"><span data-stu-id="7802f-114">Specifies the name of the system role definition.</span></span>  
  
 <span data-ttu-id="7802f-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7802f-115">**Description**</span></span>  
 <span data-ttu-id="7802f-116">Muestra una descripción de la definición de roles del sistema.</span><span class="sxs-lookup"><span data-stu-id="7802f-116">Shows a description of the system role definition.</span></span> <span data-ttu-id="7802f-117">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], esta descripción solo resulta visible en esta página.</span><span class="sxs-lookup"><span data-stu-id="7802f-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="7802f-118">Los usuarios que ven este elemento a través del Administrador de informes pueden ver esta descripción al examinar la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="7802f-118">Users who view this item through Report Manager may see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="7802f-119">**Task**</span><span class="sxs-lookup"><span data-stu-id="7802f-119">**Task**</span></span>  
 <span data-ttu-id="7802f-120">Muestra todas las tareas del nivel de sistema que se pueden seleccionar para esta definición de roles.</span><span class="sxs-lookup"><span data-stu-id="7802f-120">Lists all system-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="7802f-121">Puede agregar o quitar elementos de la lista de tareas predefinidas para definir el modo en que los usuarios tienen acceso a un elemento dado a través de ese rol.</span><span class="sxs-lookup"><span data-stu-id="7802f-121">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="7802f-122">No puede crear nuevas tareas y no puede modificar tareas existentes.</span><span class="sxs-lookup"><span data-stu-id="7802f-122">You cannot create new tasks, and you cannot modify existing tasks.</span></span>  
  
 <span data-ttu-id="7802f-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7802f-123">**Description**</span></span>  
 <span data-ttu-id="7802f-124">Proporciona información sobre cada tarea.</span><span class="sxs-lookup"><span data-stu-id="7802f-124">Provides information about each task.</span></span> <span data-ttu-id="7802f-125">No puede modificar descripciones de tareas.</span><span class="sxs-lookup"><span data-stu-id="7802f-125">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7802f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7802f-126">See Also</span></span>  
 <span data-ttu-id="7802f-127">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7802f-127">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="7802f-128">[Tareas de nivel de sistema](../security/tasks-and-permissions-system-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7802f-128">[System-Level Tasks](../security/tasks-and-permissions-system-level-tasks.md) </span></span>  
 <span data-ttu-id="7802f-129">[Tareas y permisos](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="7802f-129">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="7802f-130">Roles predefinidos</span><span class="sxs-lookup"><span data-stu-id="7802f-130">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
