---
title: Información general del Monitor de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlservermonitor.main.f1
helpviewer_keywords:
- SQL Server Monitor [SQL Server]
ms.assetid: 048ae16d-31c3-489a-9f1e-1400a3bacd39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab90186ed493e616e672cfacf881fd61be166f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663099"
---
# <a name="sql-server-monitor-overview"></a><span data-ttu-id="651d8-102">Información general del Monitor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="651d8-102">SQL Server Monitor Overview</span></span>
  <span data-ttu-id="651d8-103">Monitor de SQL Server no realiza funciones de supervisión, sino que hospeda módulos que sí lo hacen.</span><span class="sxs-lookup"><span data-stu-id="651d8-103">SQL Server Monitor does not perform monitoring functions, but it hosts modules that do.</span></span> <span data-ttu-id="651d8-104">Los módulos del Monitor de SQL Server incluyen el Monitor de replicación y el Monitor de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="651d8-104">The SQL Server Monitor modules include Replication Monitor and Database Mirroring Monitor.</span></span>  
  
 <span data-ttu-id="651d8-105">Para utilizar uno de estos módulos, selecciónelo en el menú **Ir** .</span><span class="sxs-lookup"><span data-stu-id="651d8-105">To use one of these modules, select that module on the **Go** menu.</span></span> <span data-ttu-id="651d8-106">El módulo seleccionado actualmente posee el contenido de los paneles de navegación y de detalles, la interacción con el usuario en los paneles de detalles y las consultas de contenido y estado.</span><span class="sxs-lookup"><span data-stu-id="651d8-106">The currently selected module owns the content of the navigation and detail panes, user interaction in the detail panes, and the queries for content and status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="651d8-107">Para obtener más información sobre estos monitores, vea [Supervisar la replicación](../../relational-databases/replication/monitoring-replication.md) y [Supervisar la creación de reflejo de la base de datos &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="651d8-107">For more information about these monitors, see [Monitoring Replication](../../relational-databases/replication/monitoring-replication.md) and [Monitoring Database Mirroring &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="651d8-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="651d8-108">Permissions</span></span>  
  
-   <span data-ttu-id="651d8-109">Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="651d8-109">Replication Monitor</span></span>  
  
     <span data-ttu-id="651d8-110">Para supervisar la replicación, debe ser miembro del rol fijo de servidor **sysadmin** en el distribuidor o miembro del rol fijo de base de datos **replmonitor** en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="651d8-110">To monitor replication, you must be a member of the **sysadmin** fixed server role at the Distributor or a member of the **replmonitor** fixed database role in the distribution database.</span></span> <span data-ttu-id="651d8-111">Un administrador del sistema puede agregar cualquier usuario al rol **replmonitor** , que permite a un usuario ver la actividad de replicación en el Monitor de replicación; sin embargo, el usuario no puede administrar la replicación.</span><span class="sxs-lookup"><span data-stu-id="651d8-111">A system administrator can add any user to the **replmonitor** role, which allows that user to view replication activity in Replication Monitor; however, the user cannot administer replication.</span></span>  
  
-   <span data-ttu-id="651d8-112">Monitor de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="651d8-112">Database Mirroring Monitor</span></span>  
  
     <span data-ttu-id="651d8-113">Para supervisar la creación de reflejo de la base de datos, debe ser miembro del rol fijo de servidor **sysadmin** o del rol fijo de base de datos **dbm_monitor** en la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="651d8-113">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role on the server instance.</span></span> <span data-ttu-id="651d8-114">Si solo es miembro de **sysadmin** o **dbm_monitor** en una de las instancias del servidor asociado, el monitor únicamente puede conectarse a dicho asociado; no puede recuperar información del otro asociado.</span><span class="sxs-lookup"><span data-stu-id="651d8-114">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span> <span data-ttu-id="651d8-115">Para más información, consulte [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="651d8-115">For more information, see [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="menu-options"></a><span data-ttu-id="651d8-116">Opciones de menú</span><span class="sxs-lookup"><span data-stu-id="651d8-116">Menu Options</span></span>  
 <span data-ttu-id="651d8-117">El Monitor de SQL Server tiene un menú que incluye comandos relacionados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="651d8-117">SQL Server Monitor has a menu that contains commands that pertain to SQL Server Monitor.</span></span> <span data-ttu-id="651d8-118">Este menú también contiene comandos del módulo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="651d8-118">This menu may also contain commands from the selected module.</span></span>  
  
 <span data-ttu-id="651d8-119">Las siguientes opciones de menú pertenecen al Monitor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="651d8-119">The following menu options pertain to SQL Server Monitor.</span></span>  
  
 <span data-ttu-id="651d8-120">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="651d8-120">**File**</span></span>  
 <span data-ttu-id="651d8-121">Este menú contiene el comando **Salir** .</span><span class="sxs-lookup"><span data-stu-id="651d8-121">This menu contains the **Exit** command.</span></span>  
  
 <span data-ttu-id="651d8-122">**Acción**</span><span class="sxs-lookup"><span data-stu-id="651d8-122">**Action**</span></span>  
 <span data-ttu-id="651d8-123">Contiene el menú contextual del nodo seleccionado en el árbol de navegación.</span><span class="sxs-lookup"><span data-stu-id="651d8-123">Contains the context menu of the node selected in the navigation tree.</span></span>  
  
 <span data-ttu-id="651d8-124">**Go**</span><span class="sxs-lookup"><span data-stu-id="651d8-124">**Go**</span></span>  
 <span data-ttu-id="651d8-125">Contiene una lista de componentes de supervisión</span><span class="sxs-lookup"><span data-stu-id="651d8-125">Contains a list of monitoring components:</span></span>  
  
-   <span data-ttu-id="651d8-126">Creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="651d8-126">Database Mirroring</span></span>  
  
-   <span data-ttu-id="651d8-127">Replicación</span><span class="sxs-lookup"><span data-stu-id="651d8-127">Replication</span></span>  
  
 <span data-ttu-id="651d8-128">**Para utilizar SQL Server Management Studio a fin de supervisar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="651d8-128">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="651d8-129">Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="651d8-129">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="651d8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="651d8-130">See Also</span></span>  
 [<span data-ttu-id="651d8-131">Supervisar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="651d8-131">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-sql-server.md)  
  
  
