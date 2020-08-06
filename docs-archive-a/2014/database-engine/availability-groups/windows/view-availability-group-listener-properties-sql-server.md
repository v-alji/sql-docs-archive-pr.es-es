---
title: Ver las propiedades del agente de escucha del grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistenerproperties.general.f1
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
ms.assetid: aca0d016-3228-40b8-bdc3-285ed6d9b280
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7fe316394a030350ceb12a0d1b8e2d48ee1d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663121"
---
# <a name="view-availability-group-listener-properties-sql-server"></a><span data-ttu-id="fe19a-102">Ver las propiedades del agente de escucha del grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe19a-102">View Availability Group Listener Properties (SQL Server)</span></span>
  <span data-ttu-id="fe19a-103">En este tema se describe cómo ver las propiedades de un *agente de escucha del grupo de disponibilidad* AlwaysOn mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe19a-103">This topic describes how to view the properties of an AlwaysOn *availability group listener* by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="fe19a-104">**Para ver las propiedades del agente de escucha, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="fe19a-104">**To view listener properties, using:**</span></span>  
  
     [<span data-ttu-id="fe19a-105">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe19a-105">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fe19a-106">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe19a-106">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fe19a-107">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe19a-107">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fe19a-108">**Para ver las propiedades del agente de escucha**</span><span class="sxs-lookup"><span data-stu-id="fe19a-108">**To view listener properties**</span></span>  
  
1.  <span data-ttu-id="fe19a-109">En el Explorador de objetos, conéctese a una instancia del servidor que hospeda una réplica de disponibilidad del grupo disponibilidad cuyo agente de escucha desea ver.</span><span class="sxs-lookup"><span data-stu-id="fe19a-109">In Object Explorer, connect to a server instance that hosts any availability replica of the availability group whose listener you want to view.</span></span> <span data-ttu-id="fe19a-110">Haga clic en el nombre del servidor para expandir el árbol.</span><span class="sxs-lookup"><span data-stu-id="fe19a-110">Click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="fe19a-111">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="fe19a-111">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="fe19a-112">Expanda el nodo del grupo de disponibilidad y expanda el nodo **Agentes de escucha de grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="fe19a-112">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="fe19a-113">Haga clic con el botón derecho en el agente de escucha que quiere ver y seleccione el comando **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="fe19a-113">Right-click the listener that you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="fe19a-114">Se abrirá el cuadro de diálogo de **Propiedades del agente de escucha del grupo de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="fe19a-114">This opens the **Availability Group Listener Properties** dialog box.</span></span> <span data-ttu-id="fe19a-115">Para obtener más información, vea [Propiedades del agente de escucha de grupo de disponibilidad (cuadro de diálogo)](#AgListenerPropertiesDialog), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="fe19a-115">For more information, see [Availability Group Listener Properties (Dialog Box)](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="availability-group-listener-properties-dialog-box"></a><a name="AgListenerPropertiesDialog"></a> <span data-ttu-id="fe19a-116">Propiedades del agente de escucha de grupo de disponibilidad (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="fe19a-116">Availability Group Listener Properties (Dialog Box)</span></span>  
 <span data-ttu-id="fe19a-117">**Nombre DNS del agente de escucha**</span><span class="sxs-lookup"><span data-stu-id="fe19a-117">**Listener DNS Name**</span></span>  
 <span data-ttu-id="fe19a-118">El nombre de red del agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe19a-118">The network name of the availability group listener.</span></span>  
  
 <span data-ttu-id="fe19a-119">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="fe19a-119">**Port**</span></span>  
 <span data-ttu-id="fe19a-120">El puerto TCP usado por este agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fe19a-120">The TCP port used by this listener.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe19a-121">Si está conectado a la réplica principal, puede utilizar este campo para modificar el número de puerto del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fe19a-121">If you are connected the primary replica, you can use this field to modify the port number of the listener.</span></span> <span data-ttu-id="fe19a-122">Esto requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="fe19a-122">This requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
 <span data-ttu-id="fe19a-123">**Modo de red**</span><span class="sxs-lookup"><span data-stu-id="fe19a-123">**Network Mode**</span></span>  
 <span data-ttu-id="fe19a-124">Indica el protocolo TCP utilizado por el agente de escucha; puede ser:</span><span class="sxs-lookup"><span data-stu-id="fe19a-124">Indicates the TCP protocol used by the listener, one of:</span></span>  
  
 <span data-ttu-id="fe19a-125">**DHCP**</span><span class="sxs-lookup"><span data-stu-id="fe19a-125">**DHCP**</span></span>  
 <span data-ttu-id="fe19a-126">El agente de escucha utiliza una dirección IP dinámica asignada por un servidor que ejecute el protocolo DHCP (Protocolo de configuración dinámica de host).</span><span class="sxs-lookup"><span data-stu-id="fe19a-126">The listener uses an dynamic IP address that is assigned by a server running the Dynamic Host Configuration Protocol (DHCP).</span></span>  
  
 <span data-ttu-id="fe19a-127">**Dirección IP estática**</span><span class="sxs-lookup"><span data-stu-id="fe19a-127">**Static IP**</span></span>  
 <span data-ttu-id="fe19a-128">El agente de utiliza una o más direcciones IP estáticas.</span><span class="sxs-lookup"><span data-stu-id="fe19a-128">The listener uses one or more Static IP addresses.</span></span> <span data-ttu-id="fe19a-129">Para tener acceso a las diferentes subredes, un agente de escucha del grupo de disponibilidad debe utilizar direcciones IP estáticas.</span><span class="sxs-lookup"><span data-stu-id="fe19a-129">To access the different subnets, an availability group listener must use static IP addresses.</span></span>  
  
 <span data-ttu-id="fe19a-130">La cuadrícula muestra cada una de las subredes en que el agente de escucha escucha y la dirección IP asociada a esa subred.</span><span class="sxs-lookup"><span data-stu-id="fe19a-130">The grid displays each of the subnets on which the listener listens and the IP address associated with that subnet.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fe19a-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe19a-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="fe19a-132">**Para ver las propiedades del agente de escucha**</span><span class="sxs-lookup"><span data-stu-id="fe19a-132">**To view listener properties**</span></span>  
  
 <span data-ttu-id="fe19a-133">Para supervisar los agentes de escucha del grupo de disponibilidad, utilice las vistas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe19a-133">To monitor the availability group listeners, use the following views:</span></span>  
  
 [<span data-ttu-id="fe19a-134">sys.availability_group_listener_ip_addresses</span><span class="sxs-lookup"><span data-stu-id="fe19a-134">sys.availability_group_listener_ip_addresses</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listener-ip-addresses-transact-sql)  
 <span data-ttu-id="fe19a-135">Devuelve una fila para cada dirección IP virtual conforme que está actualmente en línea para un agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe19a-135">Returns a row for every conformant virtual IP address that is currently online for an availability group listener.</span></span>  
  
 <span data-ttu-id="fe19a-136">**Nombres de columna:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span><span class="sxs-lookup"><span data-stu-id="fe19a-136">**Column names:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span></span>  
  
 [<span data-ttu-id="fe19a-137">sys.availability_group_listeners</span><span class="sxs-lookup"><span data-stu-id="fe19a-137">sys.availability_group_listeners</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listeners-transact-sql)  
 <span data-ttu-id="fe19a-138">Para un grupo de disponibilidad determinado, devuelve cero filas que indican que no hay ningún nombre de red asociado al grupo de disponibilidad o devuelve una fila por cada configuración de agente de escucha del grupo de disponibilidad del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="fe19a-138">For a given availability group, returns either zero rows indicating that no network name is associated with the availability group, or returns a row for each availability-group listener configuration in the WSFC cluster.</span></span>  
  
 <span data-ttu-id="fe19a-139">**Nombres de columna:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span><span class="sxs-lookup"><span data-stu-id="fe19a-139">**Column names:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span></span>  
  
 [<span data-ttu-id="fe19a-140">sys.dm_tcp_listener_states</span><span class="sxs-lookup"><span data-stu-id="fe19a-140">sys.dm_tcp_listener_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql)  
 <span data-ttu-id="fe19a-141">Devuelve una fila que contiene la información de estado dinámico para cada agente de escucha TCP.</span><span class="sxs-lookup"><span data-stu-id="fe19a-141">Returns a row containing dynamic-state information for each TCP listener.</span></span>  
  
 <span data-ttu-id="fe19a-142">**Nombres de columna:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span><span class="sxs-lookup"><span data-stu-id="fe19a-142">**Column names:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe19a-143">Para obtener más información sobre cómo usar [!INCLUDE[tsql](../../../includes/tsql-md.md)] para supervisar el entorno de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , vea [Supervisar grupos de disponibilidad &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fe19a-143">For more information about using [!INCLUDE[tsql](../../../includes/tsql-md.md)] to monitor your [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] environment, see [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fe19a-144">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fe19a-144">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fe19a-145">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe19a-145">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="fe19a-146">Quitar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe19a-146">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe19a-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe19a-147">See Also</span></span>  
 <span data-ttu-id="fe19a-148">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe19a-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="fe19a-149">[Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="fe19a-149">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="fe19a-150">Supervisar grupos de disponibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fe19a-150">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
