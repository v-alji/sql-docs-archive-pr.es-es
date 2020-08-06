---
title: Service Broker con Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da179219363422c4ec242d29be61f35dd1609823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673279"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="3cd83-102">Service Broker con grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3cd83-102">Service Broker with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="3cd83-103">Este tema contiene información acerca de la configuración de Service Broker para que funcione con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cd83-103">This topic contains information about configuring Service Broker to work with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="3cd83-104">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="3cd83-104">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="3cd83-105">Requisitos para que un servicio de un grupo de disponibilidad reciba mensajes remotos</span><span class="sxs-lookup"><span data-stu-id="3cd83-105">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>](#ReceiveRemoteMessages)  
  
-   [<span data-ttu-id="3cd83-106">Requisitos para enviar mensajes a un servicio remoto en un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3cd83-106">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>](#SendRemoteMessages)  
  
##  <a name="requirements-for-a-service-in-an-availability-group-to-receive-remote-messages"></a><a name="ReceiveRemoteMessages"></a> <span data-ttu-id="3cd83-107">Requisitos de un servicio en un grupo de disponibilidad para que reciba mensajes remotos</span><span class="sxs-lookup"><span data-stu-id="3cd83-107">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>  
  
1.  <span data-ttu-id="3cd83-108">**Asegúrese de que el grupo de disponibilidad tiene un agente de escucha.**</span><span class="sxs-lookup"><span data-stu-id="3cd83-108">**Ensure that the availability group possesses a listener.**</span></span>  
  
     <span data-ttu-id="3cd83-109">Para obtener más información, vea [Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3cd83-109">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="3cd83-110">**Asegúrese de que el extremo de Service Broker existe y está correctamente configurado.**</span><span class="sxs-lookup"><span data-stu-id="3cd83-110">**Ensure that the Service Broker endpoint exists and is correctly configured.**</span></span>  
  
     <span data-ttu-id="3cd83-111">En cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospede una réplica de disponibilidad para el grupo de disponibilidad, configure el extremo de Service Broker del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cd83-111">On every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group, configure the Service Broker endpoint, as follows:</span></span>  
  
    -   <span data-ttu-id="3cd83-112">Establezca LISTENER_IP en 'ALL'.</span><span class="sxs-lookup"><span data-stu-id="3cd83-112">Set LISTENER_IP to 'ALL'.</span></span> <span data-ttu-id="3cd83-113">Este valor permite las conexiones en cualquier dirección IP válida enlazada al agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3cd83-113">This setting enables connections on any valid IP address that is bound to the availability group listener.</span></span>  
  
    -   <span data-ttu-id="3cd83-114">Establezca el valor PORT de Service Broker en el mismo número de puerto en todas las instancias del servidor host.</span><span class="sxs-lookup"><span data-stu-id="3cd83-114">Set the Service Broker PORT to the same port number on all the host server instances.</span></span>  
  
        > [!TIP]  
        >  <span data-ttu-id="3cd83-115">Para ver el número de puerto del punto de conexión de Service Broker en una instancia de servidor determinada, consulte la columna **port** de la vista de catálogo [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) , donde **type_desc** = 'SERVICE_BROKER'.</span><span class="sxs-lookup"><span data-stu-id="3cd83-115">To view the port number of the Service Broker endpoint on a given server instance, query the **port** column of the [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog view, where **type_desc** = 'SERVICE_BROKER'.</span></span>  
  
     <span data-ttu-id="3cd83-116">En el ejemplo siguiente se crea un extremo de Service Broker autenticado por Windows que utiliza el puerto predeterminado de Service Broker (4022) y escucha en todas las direcciones IP válidas.</span><span class="sxs-lookup"><span data-stu-id="3cd83-116">The following example creates a Windows authenticated Service Broker endpoint that uses the default Service Broker port (4022) and listens to all valid IP addresses.</span></span>  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     <span data-ttu-id="3cd83-117">Para obtener más información, vea [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cd83-117">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
3.  <span data-ttu-id="3cd83-118">**Conceda el permiso CONNECT para usar el extremo.**</span><span class="sxs-lookup"><span data-stu-id="3cd83-118">**Grant CONNECT permission on the endpoint.**</span></span>  
  
     <span data-ttu-id="3cd83-119">Conceda el permiso CONNECT para usar el extremo de Service Broker a PUBLIC o a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3cd83-119">Grant CONNECT permission on the Service Broker endpoint either to PUBLIC or to a login.</span></span>  
  
     <span data-ttu-id="3cd83-120">En el siguiente ejemplo se concede la conexión para usar un extremo de Service Broker denominado `broker_endpoint` a PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="3cd83-120">The following example grants the connection on a Service Broker endpoint named `broker_endpoint` to PUBLIC.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     <span data-ttu-id="3cd83-121">Para obtener más información, vea [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cd83-121">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span>  
  
4.  <span data-ttu-id="3cd83-122">**Asegúrese de que msdb contiene una ruta AutoCreatedLocal o una ruta al servicio específico.**</span><span class="sxs-lookup"><span data-stu-id="3cd83-122">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cd83-123">De forma predeterminada, todas las bases de datos de usuario, incluida **msdb**, contienen la ruta **AutoCreatedLocal**.</span><span class="sxs-lookup"><span data-stu-id="3cd83-123">By default, each user database, including **msdb**, contains the route **AutoCreatedLocal**.</span></span> <span data-ttu-id="3cd83-124">Esta ruta coincide con cualquier nombre de servicio e instancia de agente, y especifica que el mensaje debe entregarse en la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="3cd83-124">This route matches any service name and broker instance and specifies that the message should be delivered within the current instance.</span></span> <span data-ttu-id="3cd83-125">**AutoCreatedLocal** tiene una prioridad menor que las rutas que especifican explícitamente un servicio específico que se comunica con una instancia remota.</span><span class="sxs-lookup"><span data-stu-id="3cd83-125">**AutoCreatedLocal** has lower priority than routes that explicitly specify a specific service that communicates with a remote instance.</span></span>  
  
     <span data-ttu-id="3cd83-126">Para obtener más información sobre cómo crear rutas, vea [Ejemplos de enrutamiento de Service Broker](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (en la versión de Libros en pantalla de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ) y [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cd83-126">For information about creating routes, see [Service Broker Routing Examples](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in the [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] version of Books Online) and [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
##  <a name="requirements-for-sending-messages-to-a-remote-service-in-an-availability-group"></a><a name="SendRemoteMessages"></a> <span data-ttu-id="3cd83-127">Requisitos para enviar mensajes a un servicio remoto en un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3cd83-127">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>  
  
1.  <span data-ttu-id="3cd83-128">**Cree una ruta al servicio de destino.**</span><span class="sxs-lookup"><span data-stu-id="3cd83-128">**Create a route to the target service.**</span></span>  
  
     <span data-ttu-id="3cd83-129">Configure la ruta del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cd83-129">Configure the route as follows:</span></span>  
  
    -   <span data-ttu-id="3cd83-130">Establezca ADDRESS en la dirección IP del agente de escucha del grupo de disponibilidad que hospeda la base de datos de servicio.</span><span class="sxs-lookup"><span data-stu-id="3cd83-130">Set ADDRESS to the listener IP address of availability group that hosts the service database.</span></span>  
  
    -   <span data-ttu-id="3cd83-131">Establezca PORT en el puerto especificado en el extremo de Service Broker de cada instancia de SQL Server remota.</span><span class="sxs-lookup"><span data-stu-id="3cd83-131">Set PORT to the port that you specified in the Service Broker endpoint of each of the remote SQL Server instances.</span></span>  
  
     <span data-ttu-id="3cd83-132">En el ejemplo siguiente se crea una ruta denominada `RouteToTargetService` para el servicio `ISBNLookupRequestService` .</span><span class="sxs-lookup"><span data-stu-id="3cd83-132">The following example creates a route named `RouteToTargetService` for the `ISBNLookupRequestService` service.</span></span> <span data-ttu-id="3cd83-133">La ruta tiene como destino el agente de escucha del grupo de disponibilidad, `MyAgListener`, que utiliza el puerto 4022.</span><span class="sxs-lookup"><span data-stu-id="3cd83-133">The route targets the availability group listener, `MyAgListener`, which uses port 4022.</span></span>  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     <span data-ttu-id="3cd83-134">Para obtener más información, vea [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cd83-134">For more information, see [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
2.  <span data-ttu-id="3cd83-135">**Asegúrese de que msdb contiene una ruta AutoCreatedLocal o una ruta al servicio específico.**</span><span class="sxs-lookup"><span data-stu-id="3cd83-135">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span> <span data-ttu-id="3cd83-136">(Para obtener más información, vea [Requisitos de un servicio en un grupo de disponibilidad para que reciba mensajes remotos](#ReceiveRemoteMessages), anteriormente en este tema).</span><span class="sxs-lookup"><span data-stu-id="3cd83-136">(For more information, see [Requirements for a Service in an Availability Group to Receive Remote Messages](#ReceiveRemoteMessages), earlier in this topic.)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3cd83-137">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3cd83-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3cd83-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cd83-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [<span data-ttu-id="3cd83-139">CREATE ROUTE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cd83-139">CREATE ROUTE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [<span data-ttu-id="3cd83-140">GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cd83-140">GRANT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-transact-sql)  
  
-   <span data-ttu-id="3cd83-141">[Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3cd83-141">[Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="3cd83-142">Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3cd83-142">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="3cd83-143">Configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3cd83-143">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a><span data-ttu-id="3cd83-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cd83-144">See Also</span></span>  
 <span data-ttu-id="3cd83-145">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3cd83-145">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="3cd83-146">[Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="3cd83-146">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="3cd83-147">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="3cd83-147">SQL Server Service Broker</span></span>](../../configure-windows/sql-server-service-broker.md)  
  
  
