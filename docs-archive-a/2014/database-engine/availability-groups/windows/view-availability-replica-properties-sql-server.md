---
title: Ver las propiedades de una réplica de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- ', policies'
ms.assetid: 14fed3c4-8ecc-4e1c-931d-a7ec1e9f9e90
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ca7b0508907b4d86c9ee627438a3f18e1b01fdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746532"
---
# <a name="view-availability-replica-properties-sql-server"></a><span data-ttu-id="1ef1c-102">Ver las propiedades de una réplica de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1ef1c-102">View Availability Replica Properties (SQL Server)</span></span>
  <span data-ttu-id="1ef1c-103">En este tema se describe cómo pueden verse las propiedades de una réplica de un grupo disponibilidad AlwaysOn con [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ef1c-103">This topic describes how to view the properties of an availability replica for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1ef1c-104">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ef1c-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1ef1c-105">**Para ver y cambiar las propiedades de una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1ef1c-105">**To view and change properties an availability replica**</span></span>  
  
1.  <span data-ttu-id="1ef1c-106">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1ef1c-107">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="1ef1c-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="1ef1c-108">Expanda el grupo de disponibilidad al que la pertenece la réplica de disponibilidad y expanda el nodo **Réplicas de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="1ef1c-108">Expand the availability group to which the availability replica belongs, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="1ef1c-109">Haga clic con el botón derecho en la réplica de disponibilidad cuyas propiedades quiera ver y seleccione el comando **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1ef1c-109">Right-click the availability replica whose properties you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="1ef1c-110">En el cuadro de diálogo **Propiedades de réplica de disponibilidad** , utilice la página **General** para ver las propiedades de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-110">In the **Availability Replica Properties** dialog box, use the **General** page to view the properties of this replica.</span></span> <span data-ttu-id="1ef1c-111">Si está conectado a la réplica principal, puede cambiar las propiedades siguientes: modo de disponibilidad, modo de conmutación por error, acceso de conexión para el rol principal, acceso de lectura para el rol secundario (legible-secundario), y el valor de tiempo de espera de la sesión.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-111">If you are connected to the primary replica, you can change the following properties: availability mode, failover mode, connection access for the primary role, read-access for the secondary role (readable-secondary), and the session-timeout value.</span></span> <span data-ttu-id="1ef1c-112">Para obtener más información, vea propiedades de la [réplica de disponibilidad &#40;página General&#41;](availability-replica-properties-general-page.md).</span><span class="sxs-lookup"><span data-stu-id="1ef1c-112">For more information, see  [Availability Replica Properties &#40;General Page&#41;](availability-replica-properties-general-page.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1ef1c-113">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1ef1c-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="1ef1c-114">**Para ver las propiedades y estados de las réplicas de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1ef1c-114">**To view properties and states of availability replicas**</span></span>  
  
 <span data-ttu-id="1ef1c-115">Para ver las propiedades y estados de las réplicas de disponibilidad, utilice las siguientes vistas y la función del sistema:</span><span class="sxs-lookup"><span data-stu-id="1ef1c-115">To view the properties and states of availability replicas, use the following views and system function:</span></span>  
  
 [<span data-ttu-id="1ef1c-116">sys.availability_replicas</span><span class="sxs-lookup"><span data-stu-id="1ef1c-116">sys.availability_replicas</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql)  
 <span data-ttu-id="1ef1c-117">Devuelve una fila para cada una de las réplicas de disponibilidad en cada grupo de disponibilidad para el que la instancia local de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hospeda una réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-117">Returns a row for every availability replica in each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span>  
  
 <span data-ttu-id="1ef1c-118">**Nombres de columna:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span><span class="sxs-lookup"><span data-stu-id="1ef1c-118">**Column names:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span></span>  
  
 [<span data-ttu-id="1ef1c-119">sys.availability_read_only_routing_lists</span><span class="sxs-lookup"><span data-stu-id="1ef1c-119">sys.availability_read_only_routing_lists</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
 <span data-ttu-id="1ef1c-120">Devuelve una fila para la lista de enrutamiento de solo lectura de cada réplica de disponibilidad en un grupo de disponibilidad AlwaysOn en el clúster de conmutación por error de WSFC.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-120">Returns a row for the read only routing list of each availability replica in an AlwaysOn availability group in the WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="1ef1c-121">**Nombres de columna:** replica_id, routing_priority, read_only_replica_id</span><span class="sxs-lookup"><span data-stu-id="1ef1c-121">**Column names:** replica_id, routing_priority, read_only_replica_id</span></span>  
  
 [<span data-ttu-id="1ef1c-122">sys.dm_hadr_availability_replica_cluster_nodes</span><span class="sxs-lookup"><span data-stu-id="1ef1c-122">sys.dm_hadr_availability_replica_cluster_nodes</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-nodes-transact-sql)  
 <span data-ttu-id="1ef1c-123">Devuelve una fila para cada réplica de disponibilidad (independientemente del estado de unión) de los grupos de disponibilidad AlwaysOn del clúster de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="1ef1c-123">Returns a row for every availability replica (regardless of join state) of the AlwaysOn availability groups in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="1ef1c-124">**Nombres de columna:** group_name, replica_server_name, node_name</span><span class="sxs-lookup"><span data-stu-id="1ef1c-124">**Column names:** group_name, replica_server_name, node_name</span></span>  
  
 [<span data-ttu-id="1ef1c-125">sys.dm_hadr_availability_replica_cluster_states</span><span class="sxs-lookup"><span data-stu-id="1ef1c-125">sys.dm_hadr_availability_replica_cluster_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-states-transact-sql)  
 <span data-ttu-id="1ef1c-126">Devuelve una fila para cada réplica (independientemente del estado de unión) de todos los grupos de disponibilidad AlwaysOn (independientemente de la ubicación de la réplica) del clúster de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="1ef1c-126">Returns a row for each replica (regardless of join state) of all AlwaysOn availability groups (regardless of replica location) in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="1ef1c-127">**Nombres de columna:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span><span class="sxs-lookup"><span data-stu-id="1ef1c-127">**Column names:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span></span>  
  
 [<span data-ttu-id="1ef1c-128">sys.dm_hadr_availability_replica_states</span><span class="sxs-lookup"><span data-stu-id="1ef1c-128">sys.dm_hadr_availability_replica_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql)  
 <span data-ttu-id="1ef1c-129">Devuelve una fila que muestra el estado de cada réplica de disponibilidad local y una fila para cada réplica de disponibilidad remota en el mismo grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-129">Returns a row showing the state of each local availability replica and a row for each remote availability replica in the same availability group.</span></span>  
  
 <span data-ttu-id="1ef1c-130">**Nombres de columna:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description y last_connect_error_timestamp</span><span class="sxs-lookup"><span data-stu-id="1ef1c-130">**Column names:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description, and last_connect_error_timestamp</span></span>  
  
 [<span data-ttu-id="1ef1c-131">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="1ef1c-131">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
 <span data-ttu-id="1ef1c-132">Determina si la réplica actual es la réplica de copia de seguridad preferida.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-132">Determines whether the current replica is the preferred backup replica.</span></span> <span data-ttu-id="1ef1c-133">Devuelve 1 si la base de datos de la instancia de servidor actual es la réplica preferida.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-133">Returns 1 if the database on the current server instance is the preferred replica.</span></span> <span data-ttu-id="1ef1c-134">De lo contrario, devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="1ef1c-134">Otherwise, it returns 0.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ef1c-135">Para obtener más información sobre los contadores de rendimiento para réplicas de disponibilidad (el objeto de rendimiento **SQLServer:Availability Replica**  ), vea [SQL Server, réplica de disponibilidad](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="1ef1c-135">For information about performance counters for availability replicas (the **SQLServer:Availability Replica**  performance object), see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1ef1c-136">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="1ef1c-136">Related Tasks</span></span>  
 <span data-ttu-id="1ef1c-137">**Para obtener más información acerca de los grupos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1ef1c-137">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="1ef1c-138">Ver las propiedades del grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-138">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-139">Ver las propiedades del agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-139">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-140">Directivas de AlwaysOn para problemas operativos con Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-140">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="1ef1c-141">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1ef1c-142">Supervisar grupos de disponibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-142">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="1ef1c-143">**Para administrar las réplicas de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1ef1c-143">**To manage availability replicas**</span></span>  
  
-   [<span data-ttu-id="1ef1c-144">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-144">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-145">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-145">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-146">Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-146">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-147">Cambiar el modo de disponibilidad de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-147">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-148">Cambiar el modo de conmutación por error de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-148">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-149">Cambiar el tiempo de espera de la sesión en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-149">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-150">Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-150">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="1ef1c-151">**Para administrar una base de datos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1ef1c-151">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="1ef1c-152">Agregar una base de datos a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-152">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="1ef1c-153">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-153">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-154">Suspender una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-154">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-155">Reanudar una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-155">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-156">Quitar una base de datos secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-156">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1ef1c-157">Quitar una base de datos principal de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-157">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="1ef1c-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ef1c-158">See Also</span></span>  
 <span data-ttu-id="1ef1c-159">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1ef1c-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1ef1c-160">[Supervisar grupos de disponibilidad &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="1ef1c-160">[Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span></span>  
 <span data-ttu-id="1ef1c-161">[Directivas de AlwaysOn para problemas operativos con Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="1ef1c-161">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 [<span data-ttu-id="1ef1c-162">Administración de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef1c-162">Administration of an Availability Group &#40;SQL Server&#41;</span></span>](administration-of-an-availability-group-sql-server.md)  
  
  
