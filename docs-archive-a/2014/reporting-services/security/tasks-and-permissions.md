---
title: Tareas y permisos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], tasks
- role-based security [Reporting Services], permissions
- security [Reporting Services], tasks
- security [Reporting Services], permissions
- role-based security [Reporting Services], tasks
- predefined tasks [Reporting Services]
- tasks [Reporting Services]
ms.assetid: d7ff90b5-b976-4270-b9ad-9d7b801d8263
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01cbf00850c5dd57e7ca1575a1a0cb826c009714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749045"
---
# <a name="tasks-and-permissions"></a><span data-ttu-id="629c3-102">Tareas y permisos</span><span class="sxs-lookup"><span data-stu-id="629c3-102">Tasks and Permissions</span></span>
  <span data-ttu-id="629c3-103">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], *tareas* son las acciones que un usuario o administrador puede llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="629c3-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], *tasks* are actions that a user or administrator can perform.</span></span> <span data-ttu-id="629c3-104">Las tareas están predefinidas.</span><span class="sxs-lookup"><span data-stu-id="629c3-104">Tasks are predefined.</span></span> <span data-ttu-id="629c3-105">No se puede crear tareas personalizadas ni modificar las que se proporcionan ni mediante programación ni con una herramienta.</span><span class="sxs-lookup"><span data-stu-id="629c3-105">You cannot create custom tasks or modify the ones provided either programmatically or through a tool.</span></span> <span data-ttu-id="629c3-106">En total, hay veinticinco tareas.</span><span class="sxs-lookup"><span data-stu-id="629c3-106">There are twenty-five tasks in all.</span></span> <span data-ttu-id="629c3-107">Estas tareas comprenden todo el conjunto de operaciones que están disponibles en la seguridad basada en roles.</span><span class="sxs-lookup"><span data-stu-id="629c3-107">These tasks comprise the entire set of operations that are available in role-based security.</span></span> <span data-ttu-id="629c3-108">Algunos ejemplos de tareas son "Ver informes", "Administrar informes" y "Administrar propiedades del servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="629c3-108">Some examples of tasks include "View reports," "Manage reports," and "Manage report server properties."</span></span>  
  
 <span data-ttu-id="629c3-109">Cada tarea se compone de un conjunto de permisos, también predefinidos.</span><span class="sxs-lookup"><span data-stu-id="629c3-109">Each task consists of a set of permissions, which are also predefined.</span></span> <span data-ttu-id="629c3-110">Por ejemplo, la tarea "Administrar carpetas" contiene los permisos necesarios para crear y eliminar carpetas, así como para ver y actualizar propiedades de carpetas.</span><span class="sxs-lookup"><span data-stu-id="629c3-110">For example, the "Manage folders" task contains permissions to create and delete folders and view and update folder properties.</span></span> <span data-ttu-id="629c3-111">Los permisos de cada tarea están documentos para proporcionar una descripción más exacta de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="629c3-111">Permissions for each task are documented to provide a more exact description of each task.</span></span> <span data-ttu-id="629c3-112">No es posible interactuar con permisos directamente ni especificarlos en las asignaciones de roles.</span><span class="sxs-lookup"><span data-stu-id="629c3-112">It is not possible to interact with permissions directly or to specify them in role assignments.</span></span> <span data-ttu-id="629c3-113">Los permisos se conceden a los usuarios indirectamente mediante las tareas que se incluyen en las definiciones de rol.</span><span class="sxs-lookup"><span data-stu-id="629c3-113">Users are granted permissions indirectly through the tasks that are included in role definitions.</span></span>  
  
 <span data-ttu-id="629c3-114">Las tareas solo se pueden llevar a cabo si forman parte de un rol y dicho rol se incluye en una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="629c3-114">Tasks can be performed only if they are part of a role and that role is included in a role assignment.</span></span> <span data-ttu-id="629c3-115">Por lo tanto, si la tarea Ver modelos no está incluida en un rol, o ese rol no está incluido en una asignación de roles, los usuarios no podrán ver los modelos de informes.</span><span class="sxs-lookup"><span data-stu-id="629c3-115">Thus, if the View Models task is not included in a role, or that role is not included in a role assignment, users cannot view report models.</span></span> <span data-ttu-id="629c3-116">El siguiente diagrama muestra cómo los permisos se combinan para crear tareas y éstas se combinan para crear roles que se pueden utilizar para asignaciones de roles específicas.</span><span class="sxs-lookup"><span data-stu-id="629c3-116">The following diagram shows how permissions are combined into tasks, and how tasks are combined into roles that can be used for specific role assignments.</span></span>  
  
 <span data-ttu-id="629c3-117">![Diagrama de tareas y permisos](../media/report-securityobjects.gif "Diagrama de tareas y permisos")</span><span class="sxs-lookup"><span data-stu-id="629c3-117">![Permissions and task diagram](../media/report-securityobjects.gif "Permissions and task diagram")</span></span>  
<span data-ttu-id="629c3-118">Diagrama de tareas y permisos</span><span class="sxs-lookup"><span data-stu-id="629c3-118">Permissions and task diagram</span></span>  
  
## <a name="system-and-item-level-tasks"></a><span data-ttu-id="629c3-119">Tareas de nivel de sistema y de elemento</span><span class="sxs-lookup"><span data-stu-id="629c3-119">System and Item Level Tasks</span></span>  
 <span data-ttu-id="629c3-120">Las tareas se clasifican en dos categorías: nivel de sistema y nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="629c3-120">Tasks fall into two categories: system level and item level.</span></span> <span data-ttu-id="629c3-121">Un rol puede incluir tareas solo de una categoría.</span><span class="sxs-lookup"><span data-stu-id="629c3-121">A role can include tasks only from a single category.</span></span> <span data-ttu-id="629c3-122">La siguiente tabla describe cada categoría de tareas.</span><span class="sxs-lookup"><span data-stu-id="629c3-122">The following table describes each category of tasks.</span></span>  
  
|<span data-ttu-id="629c3-123">Category</span><span class="sxs-lookup"><span data-stu-id="629c3-123">Category</span></span>|<span data-ttu-id="629c3-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="629c3-124">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="629c3-125">Tareas de nivel de elemento</span><span class="sxs-lookup"><span data-stu-id="629c3-125">Item-Level Tasks</span></span>](tasks-and-permissions-item-level-tasks.md)|<span data-ttu-id="629c3-126">Acciones que se realizan con elementos administrados por un servidor de informes, como carpetas, informes, modelos de informe y recursos.</span><span class="sxs-lookup"><span data-stu-id="629c3-126">Actions that are performed on items managed by a report server, such as folders, reports, report models, and resources.</span></span><br /><br /> <span data-ttu-id="629c3-127">Las tareas de nivel de elemento se centran en el espacio de nombres de las carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="629c3-127">Item-level tasks are scoped to the report server folder namespace.</span></span> <span data-ttu-id="629c3-128">Todos los elementos a los que tiene acceso mediante las carpetas en un servidor de informes o mediante una dirección URL están protegidos por las asignaciones de roles que incluyen tareas de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="629c3-128">All items that you access through the folders on a report server or through URL access are secured by role assignments that include item-level tasks.</span></span>|  
|[<span data-ttu-id="629c3-129">Tareas de nivel de sistema</span><span class="sxs-lookup"><span data-stu-id="629c3-129">System-Level Tasks</span></span>](tasks-and-permissions-system-level-tasks.md)|<span data-ttu-id="629c3-130">Acciones que se realizan en el nivel de sistema, como administrar trabajos o programaciones compartidas que se pueden utilizar con muchos elementos.</span><span class="sxs-lookup"><span data-stu-id="629c3-130">Actions that are performed at the system level, such as managing jobs or shared schedules that can be used with many items.</span></span> <span data-ttu-id="629c3-131">Las tareas de nivel de sistema se centran fuera del espacio de nombres de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="629c3-131">System-level tasks are scoped outside of the report server folder namespace.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="629c3-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="629c3-132">See Also</span></span>  
 <span data-ttu-id="629c3-133">[Definiciones de roles](role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="629c3-133">[Role Definitions](role-definitions.md) </span></span>  
 <span data-ttu-id="629c3-134">[Roles predefinidos](role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="629c3-134">[Predefined Roles](role-definitions-predefined-roles.md) </span></span>  
 [<span data-ttu-id="629c3-135">Concesión de permisos en un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="629c3-135">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  