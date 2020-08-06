---
title: Tareas de nivel de sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98f9390664064cd293b80d094d65c903869bc709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749049"
---
# <a name="system-level-tasks"></a><span data-ttu-id="db272-102">Tareas de nivel de sistema</span><span class="sxs-lookup"><span data-stu-id="db272-102">System-Level Tasks</span></span>
  <span data-ttu-id="db272-103">Una tarea de nivel de sistema es una colección de permisos relativos a las operaciones correspondientes al sitio del servidor de informes en general.</span><span class="sxs-lookup"><span data-stu-id="db272-103">A system-level task is a collection of permissions that relate to operations that apply to the report server site as a whole.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="db272-104">también incluye tareas de nivel de elemento que corresponden a elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="db272-104">also includes item-level tasks that apply to specific items.</span></span> <span data-ttu-id="db272-105">Para obtener más información, vea [Tareas de nivel de elemento](tasks-and-permissions-item-level-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="db272-105">For more information, see [Item-Level Tasks](tasks-and-permissions-item-level-tasks.md).</span></span> <span data-ttu-id="db272-106">Para obtener más información acerca de tareas y permisos en general, vea [Tasks and Permissions](tasks-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="db272-106">For more information about tasks and permissions in general, see [Tasks and Permissions](tasks-and-permissions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db272-107">Si trabaja con estas tareas mediante programación, debe utilizar métodos que admitan tareas de nivel de sistema.</span><span class="sxs-lookup"><span data-stu-id="db272-107">If you are working with these tasks programmatically, you must use methods that support system-level tasks.</span></span> <span data-ttu-id="db272-108">Para más información, vea <xref:ReportService2010.ReportingService2010.ListTasks%2A> y <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="db272-108">For more information, see <xref:ReportService2010.ReportingService2010.ListTasks%2A> and <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span></span>  
  
## <a name="permissions-in-system-level-tasks"></a><span data-ttu-id="db272-109">Permisos en tareas de nivel de sistema</span><span class="sxs-lookup"><span data-stu-id="db272-109">Permissions in System-Level Tasks</span></span>  
 <span data-ttu-id="db272-110">La siguiente tabla identifica la colección de permisos para cada tarea del sistema.</span><span class="sxs-lookup"><span data-stu-id="db272-110">The following table identifies the collection of permissions for each system task.</span></span> <span data-ttu-id="db272-111">Los permisos se incluyen con fin informativo únicamente, para proporcionar una descripción más exacta de la funcionalidad disponible con cada tarea.</span><span class="sxs-lookup"><span data-stu-id="db272-111">Permissions are listed for informational purposes only, to provide a more exact description of the functionality available through each task.</span></span>  
  
|<span data-ttu-id="db272-112">Tarea</span><span class="sxs-lookup"><span data-stu-id="db272-112">Task</span></span>|<span data-ttu-id="db272-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="db272-113">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="db272-114">Ejecutar definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="db272-114">Execute report definitions</span></span>|<span data-ttu-id="db272-115">Ejecutar definiciones de informe (el nombre del permiso y la tarea es el mismo)</span><span class="sxs-lookup"><span data-stu-id="db272-115">Execute Report Definitions (the permission and task name are the same)</span></span>|  
|<span data-ttu-id="db272-116">Generación de eventos</span><span class="sxs-lookup"><span data-stu-id="db272-116">Generate events</span></span>|<span data-ttu-id="db272-117">Generar eventos</span><span class="sxs-lookup"><span data-stu-id="db272-117">Generate Events</span></span>|  
|<span data-ttu-id="db272-118">Trabajos de administración</span><span class="sxs-lookup"><span data-stu-id="db272-118">Manage jobs</span></span>|<span data-ttu-id="db272-119">Leer propiedades del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-119">Read System Properties</span></span><br /><br /> <span data-ttu-id="db272-120">Actualizar propiedades del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-120">Update System Properties</span></span>|  
|<span data-ttu-id="db272-121">Administrar propiedades del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="db272-121">Manage report server properties</span></span>|<span data-ttu-id="db272-122">Leer propiedades del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-122">Read System Properties</span></span><br /><br /> <span data-ttu-id="db272-123">Actualizar propiedades del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-123">Update System Properties</span></span>|  
|<span data-ttu-id="db272-124">Administrar roles</span><span class="sxs-lookup"><span data-stu-id="db272-124">Manage roles</span></span>|<span data-ttu-id="db272-125">Crear roles</span><span class="sxs-lookup"><span data-stu-id="db272-125">Create Roles</span></span><br /><br /> <span data-ttu-id="db272-126">Eliminar roles</span><span class="sxs-lookup"><span data-stu-id="db272-126">Delete Roles</span></span><br /><br /> <span data-ttu-id="db272-127">Leer propiedades de roles</span><span class="sxs-lookup"><span data-stu-id="db272-127">Read Role Properties</span></span><br /><br /> <span data-ttu-id="db272-128">Actualizar propiedades de roles</span><span class="sxs-lookup"><span data-stu-id="db272-128">Update Role Properties</span></span>|  
|<span data-ttu-id="db272-129">Administrar programaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="db272-129">Manage shared schedules</span></span>|<span data-ttu-id="db272-130">Crear programaciones</span><span class="sxs-lookup"><span data-stu-id="db272-130">Create Schedules</span></span>|  
|<span data-ttu-id="db272-131">Administrar la seguridad del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="db272-131">Manage report server security</span></span>|<span data-ttu-id="db272-132">Leer directivas de seguridad del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-132">Read System Security Policies</span></span><br /><br /> <span data-ttu-id="db272-133">Actualizar directivas de seguridad del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-133">Update System Security Policies</span></span>|  
|<span data-ttu-id="db272-134">Ver propiedades del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="db272-134">View report server properties</span></span>|<span data-ttu-id="db272-135">Leer propiedades del sistema</span><span class="sxs-lookup"><span data-stu-id="db272-135">Read System Properties</span></span>|  
|<span data-ttu-id="db272-136">Ver programaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="db272-136">View shared schedules</span></span>|<span data-ttu-id="db272-137">Leer programaciones</span><span class="sxs-lookup"><span data-stu-id="db272-137">Read Schedules</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db272-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db272-138">See Also</span></span>  
 [<span data-ttu-id="db272-139">Concesión de permisos en un servidor de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="db272-139">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
