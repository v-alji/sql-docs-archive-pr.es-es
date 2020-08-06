---
title: Configurar el enrutamiento de solo lectura para un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- read-only routing
- Availability Groups [SQL Server], readable secondary replicas
- Availability Groups [SQL Server], read-only routing
- readable secondary replicas
- Availability Groups [SQL Server], client connectivity
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 7bd89ddd-0403-4930-a5eb-3c78718533d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d51d1db75caa29814a01fc1f49bfdd49b403c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674994"
---
# <a name="configure-read-only-routing-for-an-availability-group-sql-server"></a><span data-ttu-id="f325f-102">Configurar el enrutamiento de solo lectura para un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f325f-102">Configure Read-Only Routing for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="f325f-103">Para configurar el grupo de disponibilidad AlwaysOn para admitir el enrutamiento de solo lectura en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], puede utilizar [!INCLUDE[tsql](../../../includes/tsql-md.md)] o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f325f-103">To configure an AlwaysOn availability group to support read-only routing in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can use either [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell.</span></span> <span data-ttu-id="f325f-104">El*enrutamiento de solo lectura* hace referencia a la capacidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de enrutar las solicitudes de conexión de solo lectura a una [réplica secundaria legible](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) AlwaysOn disponible (es decir, una réplica configurada para permitir cargas de trabajo de solo lectura al ejecutarse en un rol secundario).</span><span class="sxs-lookup"><span data-stu-id="f325f-104">*Read-only routing* refers to the ability of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to route qualifying read-only connection requests to an available AlwaysOn [readable secondary replica](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) (that is, a replica that is configured to allow read-only workloads when running under the secondary role).</span></span> <span data-ttu-id="f325f-105">Para admitir el enrutamiento de solo lectura, el grupo de disponibilidad debe poseer un [agente de escucha de grupo de disponibilidad](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-105">To support read-only routing, the availability group must possess an [availability group listener](../../listeners-client-connectivity-application-failover.md).</span></span> <span data-ttu-id="f325f-106">Los clientes de solo lectura deben dirigir sus solicitudes de conexión a este agente de escucha y las cadenas de conexión del cliente deben especificar el intento de aplicación como de “solo lectura”.</span><span class="sxs-lookup"><span data-stu-id="f325f-106">Read-only clients must direct their connection requests to this listener, and the client's connection strings must specify the application intent as "read-only."</span></span> <span data-ttu-id="f325f-107">Es decir, deben ser *solicitudes de conexión de intento de lectura*.</span><span class="sxs-lookup"><span data-stu-id="f325f-107">That is, they must be *read-intent connection requests*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f325f-108">Para obtener información sobre cómo configurar una réplica secundaria legible, vea [Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-108">For information about how to configure a readable secondary replica, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="f325f-109">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]no admite la configuración del enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-109">Configuring read-only routing is not supported by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f325f-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f325f-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f325f-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f325f-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="f325f-112">El grupo de disponibilidad debe poseer un agente de escucha de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f325f-112">The availability group must possess an availability group listener.</span></span> <span data-ttu-id="f325f-113">Para obtener más información, vea [Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-113">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   <span data-ttu-id="f325f-114">Una o varias réplicas de disponibilidad deben estar configuradas para aceptar solo lectura en el rol secundario (es decir, para ser [réplicas secundarias legibles](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn% 20Availability% 20Groups \) . MD)).</span><span class="sxs-lookup"><span data-stu-id="f325f-114">One or more availability replicas must be configured to accept read-only in the secondary role (that is, to be [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn%20Availability%20Groups\).md)).</span></span> <span data-ttu-id="f325f-115">Para obtener más información, vea [Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-115">For more information, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>  
  
-   <span data-ttu-id="f325f-116">Debe estar conectado a la instancia del servidor que hospeda la réplica principal actual.</span><span class="sxs-lookup"><span data-stu-id="f325f-116">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
###  <a name="what-replica-properties-do-you-need-to-configure-to-support-read-only-routing"></a><a name="RORReplicaProperties"></a><span data-ttu-id="f325f-117">¿Qué propiedades de réplica debe configurar para admitir el enrutamiento de solo lectura?</span><span class="sxs-lookup"><span data-stu-id="f325f-117">What Replica Properties Do you Need to Configure to Support Read-Only Routing?</span></span>  
  
-   <span data-ttu-id="f325f-118">Para cada réplica secundaria legible que vaya a admitir el enrutamiento de solo lectura, debe especificar una *dirección URL de enrutamiento de solo lectura*.</span><span class="sxs-lookup"><span data-stu-id="f325f-118">For each readable secondary replica that is to support read-only routing, you need to specify a *read-only routing URL*.</span></span> <span data-ttu-id="f325f-119">Esta dirección URL tiene efecto cuando la réplica local se ejecuta en el rol secundario.</span><span class="sxs-lookup"><span data-stu-id="f325f-119">This URL takes effect only when the local replica is running under the secondary role.</span></span> <span data-ttu-id="f325f-120">La dirección URL de enrutamiento de solo lectura debe especificarse réplica a réplica, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f325f-120">The read-only routing URL must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="f325f-121">Cada dirección URL de solo lectura se usa para enrutar las solicitudes de conexión de intento de lectura a una réplica secundaria legible específica.</span><span class="sxs-lookup"><span data-stu-id="f325f-121">Each read-only routing URL is used for routing read-intent connection requests to a specific readable secondary replica.</span></span> <span data-ttu-id="f325f-122">Normalmente, cada réplica secundaria legible se asigna a una dirección URL de enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-122">Typically, every readable secondary replica is assigned a read-only routing URL.</span></span>  
  
     <span data-ttu-id="f325f-123">Para obtener información sobre cómo calcular la dirección URL de enrutamiento de solo lectura para una réplica de disponibilidad, vea [Calcular Read_only_routing_url para AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="f325f-123">For information about calculating the read-only routing URL for an availability replica, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
-   <span data-ttu-id="f325f-124">Para cada réplica de disponibilidad que quiera que admita el enrutamiento de solo lectura cuando sea la réplica principal, debe especificar una *lista de enrutamiento de solo lectura*.</span><span class="sxs-lookup"><span data-stu-id="f325f-124">For each availability replica that you want to support read-only routing when it is the primary replica, you need to specify a *read-only routing list*.</span></span> <span data-ttu-id="f325f-125">Una lista de enrutamiento de solo lectura dada solo tiene efecto cuando la réplica local se ejecuta en el rol principal.</span><span class="sxs-lookup"><span data-stu-id="f325f-125">A given read-only routing list takes effect only when the local replica is running under the primary role.</span></span> <span data-ttu-id="f325f-126">Esta lista se debe especificar réplica a réplica, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f325f-126">This list must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="f325f-127">Normalmente, cada lista de enrutamiento de solo lectura contendría cada dirección URL de enrutamiento de solo lectura con la dirección URL de la réplica local al final de la lista.</span><span class="sxs-lookup"><span data-stu-id="f325f-127">Typically, each read-only routing list would contain every read-only routing URL, with the URL of the local replica at the end of the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f325f-128">Las solicitudes de conexión de intento de lectura se enrutan al primer elemento secundario legible disponible en la lista de enrutamiento de solo lectura de la réplica principal actual.</span><span class="sxs-lookup"><span data-stu-id="f325f-128">Read-intent connection requests are routed to the first available readable secondary on the read-only routing list of the current primary replica.</span></span> <span data-ttu-id="f325f-129">No hay equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="f325f-129">There is no load balancing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f325f-130">Para obtener información sobre los agentes de escucha de grupo de disponibilidad y obtener más información sobre el enrutamiento de solo lectura, vea [Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-130">For information about availability group listeners and more information about read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f325f-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f325f-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f325f-132">Permisos</span><span class="sxs-lookup"><span data-stu-id="f325f-132">Permissions</span></span>  
  
|<span data-ttu-id="f325f-133">Tarea</span><span class="sxs-lookup"><span data-stu-id="f325f-133">Task</span></span>|<span data-ttu-id="f325f-134">Permisos</span><span class="sxs-lookup"><span data-stu-id="f325f-134">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f325f-135">Para configurar réplicas al crear un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="f325f-135">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="f325f-136">Se requiere la pertenencia al rol fijo de servidor **sysadmin** y el permiso de servidor CREATE AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f325f-136">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="f325f-137">Para modificar una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="f325f-137">To modify an availability replica</span></span>|<span data-ttu-id="f325f-138">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f325f-138">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f325f-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f325f-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="f325f-140">**Para configurar el enrutamiento de solo lectura**</span><span class="sxs-lookup"><span data-stu-id="f325f-140">**To Configure read-only routing**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f325f-141">Para obtener un ejemplo de código, vea [Ejemplo (Transact-SQL)](#TsqlExample), más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f325f-141">For a code example, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="f325f-142">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f325f-142">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="f325f-143">Si va a especificar una réplica para un nuevo grupo de disponibilidad, use la instrucción [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f325f-143">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="f325f-144">Si va a agregar o modificar una réplica para un grupo de disponibilidad existente, use la instrucción [ALTER Availability Group](/sql/t-sql/statements/alter-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f325f-144">If you are adding or modifying a replica for an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="f325f-145">Para configurar el acceso de solo lectura para el rol secundario, en la cláusula ADD REPLICA o MODIFY REPLICA WITH, especifique la opción SECONDARY_ROLE, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="f325f-145">To configure read-only routing for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="f325f-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **= '** TCP **:// *`system-address`* : *`port`* ')**</span><span class="sxs-lookup"><span data-stu-id="f325f-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **://*`system-address`*:*`port`*')**</span></span>  
  
         <span data-ttu-id="f325f-147">Los parámetros de la dirección URL de enrutamiento de solo lectura son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f325f-147">The parameters of the read-only routing URL are as follows:</span></span>  
  
         <span data-ttu-id="f325f-148">*system-address*</span><span class="sxs-lookup"><span data-stu-id="f325f-148">*system-address*</span></span>  
         <span data-ttu-id="f325f-149">Es una cadena, como un nombre de sistema, un nombre de dominio completo o una dirección IP, que identifica sin ambigüedad el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f325f-149">Is a string, such as a system name, a fully qualified domain name, or an IP address, that unambiguously identifies the destination computer system.</span></span>  
  
         <span data-ttu-id="f325f-150">*port*</span><span class="sxs-lookup"><span data-stu-id="f325f-150">*port*</span></span>  
         <span data-ttu-id="f325f-151">Es un número de puerto que usa el motor de base de datos de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f325f-151">Is a port number that is used by the Database Engine of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="f325f-152">Por ejemplo:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span><span class="sxs-lookup"><span data-stu-id="f325f-152">For example:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span></span>  
  
         <span data-ttu-id="f325f-153">En una cláusula MODIFY REPLICA el ALLOW_CONNECTIONS es opcional si la réplica ya está configurada para permitir conexiones de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-153">In a MODIFY REPLICA clause the ALLOW_CONNECTIONS is optional if the replica is already configured to allow read-only connections.</span></span>  
  
         <span data-ttu-id="f325f-154">Para obtener más información, vea [Calcular read_only_routing_url para AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="f325f-154">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="f325f-155">Para configurar el enrutamiento de solo lectura para el rol principal, en la cláusula ADD REPLICA o MODIFY REPLICA WITH, especifique la opción PRIMARY_ROLE, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="f325f-155">To configure read-only routing for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="f325f-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **= (' *`server`* '** [ **,**... *n* ]) **)**</span><span class="sxs-lookup"><span data-stu-id="f325f-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **=('*`server`*'** [ **,**...*n* ] **))**</span></span>  
  
         <span data-ttu-id="f325f-157">donde *server* identifica una instancia del servidor que hospeda una réplica secundaria de solo lectura en el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f325f-157">where, *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span>  
  
         <span data-ttu-id="f325f-158">Por ejemplo:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span><span class="sxs-lookup"><span data-stu-id="f325f-158">For example:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f325f-159">Debe establecer la dirección URL de enrutamiento de solo lectura antes de configurar la lista de enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-159">You must set the read-only routing URL before configuring the read-only routing list.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="f325f-160">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f325f-160">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="f325f-161">En el ejemplo siguiente se modifica la disponibilidad de las dos réplicas de un grupo de disponibilidad existente, `AG1` para admitir el enrutamiento de solo lectura, si una de las réplicas posee actualmente el rol principal.</span><span class="sxs-lookup"><span data-stu-id="f325f-161">The following example modifies two availability replicas of an existing availability group, `AG1` to support read-only routing if one of these replicas currently owns the primary role.</span></span> <span data-ttu-id="f325f-162">Para identificar las instancias de servidor que hospedan la réplica de disponibilidad, este ejemplo especifica los nombres de instancia `COMPUTER01` y `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="f325f-162">To identify the server instances that host the availability replica, this example specifies the instance names-`COMPUTER01` and `COMPUTER02`.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER02.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER02','COMPUTER01')));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER01','COMPUTER02')));  
GO
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="f325f-163">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f325f-163">Using PowerShell</span></span>  

### <a name="to-configure-read-only-routing"></a><span data-ttu-id="f325f-164">Para configurar el enrutamiento de solo lectura</span><span class="sxs-lookup"><span data-stu-id="f325f-164">To Configure read-only routing</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="f325f-165">Para obtener un ejemplo de código, vea [Ejemplo (PowerShell)](#PSExample), más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f325f-165">For a code example, see [Example (PowerShell)](#PSExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="f325f-166">Establezca el valor predeterminado (`cd`) en la instancia del servidor que hospeda la réplica de disponibilidad principal.</span><span class="sxs-lookup"><span data-stu-id="f325f-166">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="f325f-167">Para agregar una réplica de disponibilidad a un grupo de disponibilidad, use el cmdlet `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="f325f-167">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="f325f-168">Para modificar una réplica de disponibilidad existente, use el cmdlet `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="f325f-168">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="f325f-169">Los parámetros pertinentes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f325f-169">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="f325f-170">Para configurar el enrutamiento de solo lectura para el rol secundario, especifique el parámetro **parámetro readonlyroutingconnectionurl " *`url`* "** .</span><span class="sxs-lookup"><span data-stu-id="f325f-170">To configure read-only routing for the secondary role, specify the **ReadonlyRoutingConnectionUrl"*`url`*"** parameter.</span></span>  
  
         <span data-ttu-id="f325f-171">donde, *url* es el nombre de dominio completo (FQDN) y puerto que se usa para el enrutamiento de la réplica para las conexiones de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-171">where, *url* is the connectivity fully-qualified domain name (FQDN) and port to use when routing to the replica for read-only connections.</span></span> <span data-ttu-id="f325f-172">Por ejemplo: `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span><span class="sxs-lookup"><span data-stu-id="f325f-172">For example:  `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span></span>  
  
         <span data-ttu-id="f325f-173">Para obtener más información, vea [Calcular read_only_routing_url para AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="f325f-173">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="f325f-174">Para configurar el acceso de conexión para el rol principal, especifique **ReadonlyRoutingList " *`server`* "** [ **,**... *n* ], donde *Server* identifica una instancia del servidor que hospeda una réplica secundaria de solo lectura en el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f325f-174">To configure connection access for the primary role, specify **ReadonlyRoutingList"*`server`*"** [ **,**...*n* ], where *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span> <span data-ttu-id="f325f-175">Por ejemplo: `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span><span class="sxs-lookup"><span data-stu-id="f325f-175">For example:  `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f325f-176">Debe establecer la dirección URL de enrutamiento de solo lectura de la réplica antes de configurar su lista de enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-176">You must set the read-only routing URL of a replica before configuring its read-only routing list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f325f-177">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f325f-177">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f325f-178">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-178">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="f325f-179">Para configurar y usar el proveedor de SQL Server PowerShell, vea [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) y [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-179">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) and [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>
  
###  <a name="example-powershell"></a><a name="PSExample"></a> <span data-ttu-id="f325f-180">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f325f-180">Example (PowerShell)</span></span>  
 <span data-ttu-id="f325f-181">En el ejemplo siguiente se configura la réplica principal y una réplica secundaria en un grupo de disponibilidad para el enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-181">The following example configures the primary replica and one secondary replica in an availability group for read-only routing.</span></span> <span data-ttu-id="f325f-182">Primero, en el el ejemplo se asigna una dirección URL de solo lectura de enrutamiento a cada réplica.</span><span class="sxs-lookup"><span data-stu-id="f325f-182">First, the example assigns a read-only routing URL to each replica.</span></span> <span data-ttu-id="f325f-183">Después, establece la lista de enrutamiento de solo lectura en la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f325f-183">Then it sets the read-only routing list on the primary replica.</span></span> <span data-ttu-id="f325f-184">Las conexiones con la propiedad "ReadOnly" establecida en la cadena de conexión se redirigirán a la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="f325f-184">Connections with the "ReadOnly" property set in the connection string will be redirected to the secondary replica.</span></span> <span data-ttu-id="f325f-185">Si esta réplica secundaria no es legible (según lo determinado por la opción de configuración `ConnectionModeInSecondaryRole`), la conexión se dirigirá de nuevo a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f325f-185">If this secondary replica is not readable (as determined by the `ConnectionModeInSecondaryRole` setting), the connection will be directed back to the primary replica.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  
$secondaryReplica = Get-Item "AvailabilityReplicas\SecondaryServer"  
  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://PrimaryServer.domain.com:1433" -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://SecondaryServer.domain.com:1433" -InputObject $secondaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingList "SecondaryServer","PrimaryServer" -InputObject $primaryReplica  
```  
  
##  <a name="follow-up-after-configuring-read-only-routing"></a><a name="FollowUp"></a> <span data-ttu-id="f325f-186">Seguimiento: después de configurar el enrutamiento de solo lectura</span><span class="sxs-lookup"><span data-stu-id="f325f-186">Follow Up: After Configuring Read-Only Routing</span></span>  
 <span data-ttu-id="f325f-187">Una vez que la réplica principal actual y las réplicas secundarias legibles están configuradas para admitir el enrutamiento de solo lectura en ambos roles, las réplicas secundarias legibles pueden recibir solicitudes de intentos de conexión de lectura de los clientes que se conectan mediante el agente de escucha de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f325f-187">Once the current primary replica and the readable secondary replicas are configured to support read-only routing in both roles, the readable secondary replicas can receive read read-intent connection requests from clients that connect via the availability group listener.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="f325f-188">Cuando se usa la [utilidad BCP](../../../tools/bcp-utility.md) o la [utilidad SQLCMD](../../../tools/sqlcmd-utility.md), se puede especificar el acceso de solo lectura a cualquier réplica secundaria que esté habilitada para el acceso de solo lectura especificando el `-K ReadOnly` modificador.</span><span class="sxs-lookup"><span data-stu-id="f325f-188">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
###  <a name="requirements-and-recommendations-for-client-connection-strings"></a><a name="ConnStringReqsRecs"></a> <span data-ttu-id="f325f-189">Requisitos y recomendaciones para las cadenas de conexión de cliente</span><span class="sxs-lookup"><span data-stu-id="f325f-189">Requirements and Recommendations for Client Connection-Strings</span></span>  
 <span data-ttu-id="f325f-190">Para que una aplicación cliente use el enrutamiento de solo lectura, la cadena de conexión debe cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f325f-190">For a client application to use read-only routing, its connection string must satisfy the following requirements:</span></span>  
  
-   <span data-ttu-id="f325f-191">Usar el protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="f325f-191">Use the TCP protocol.</span></span>  
  
-   <span data-ttu-id="f325f-192">Establecer el atributo o propiedad para el intento de aplicaciones de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-192">Set the application intent attribute/property to readonly.</span></span>  
  
-   <span data-ttu-id="f325f-193">Hacer referencia al agente de escucha de un grupo de disponibilidad que se configura para admitir el enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-193">Reference the listener of an availability group that is configured to support read-only routing.</span></span>  
  
-   <span data-ttu-id="f325f-194">Hacer referencia a una base de datos en ese grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f325f-194">Reference a database in that availability group.</span></span>  
  
 <span data-ttu-id="f325f-195">Además, se recomienda que las cadenas de conexión habiliten la conmutación por error de múltiples subredes, que admite un subproceso de cliente paralelo para cada réplica en cada subred.</span><span class="sxs-lookup"><span data-stu-id="f325f-195">In addition, we recommend that connection strings enable multi-subnet failover, which supports a parallel client thread for each replica on each subnet.</span></span> <span data-ttu-id="f325f-196">Esto reduce el tiempo de reconexión de cliente después de una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f325f-196">This minimizes client reconnection time after a failover.</span></span>  
  
 <span data-ttu-id="f325f-197">La sintaxis para una cadena de conexión depende del proveedor de SQL Server que una aplicación está utilizando.</span><span class="sxs-lookup"><span data-stu-id="f325f-197">The syntax for a connection string depends on the SQL Server provider an application is using.</span></span> <span data-ttu-id="f325f-198">El siguiente ejemplo de cadena de conexión para el proveedor de datos de .NET Framework 4.0.2 para SQL Server, muestra las partes de una cadena de conexión necesarias y que se recomiendan para que funcionen con el enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f325f-198">The following example connection string for the .NET Framework Data Provider 4.0.2 for SQL Server illustrates the parts of a connection string that are required and recommended to work for read-only routing.</span></span>  
  
```  
Server=tcp:MyAgListener,1433;Database=Db1;IntegratedSecurity=SSPI;ApplicationIntent=ReadOnly;MultiSubnetFailover=True  
```  
  
 <span data-ttu-id="f325f-199">Para obtener más información sobre el intento de aplicación de solo lectura y el enrutamiento de solo lectura, vea [Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-199">For more information about read-only application intent and read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
### <a name="if-read-only-routing-is-not-working-correctly"></a><span data-ttu-id="f325f-200">Si el enrutamiento de solo lectura no funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="f325f-200">If Read-Only Routing is Not Working Correctly</span></span>  
 <span data-ttu-id="f325f-201">Para obtener información sobre la solución de problemas de una configuración de enrutamiento de solo lectura, vea [El enrutamiento de solo lectura no funciona correctamente](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f325f-201">For information about troubleshooting a read-only routing configuration, see [Read-Only Routing is Not Working Correctly](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f325f-202">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f325f-202">Related Tasks</span></span>  

### <a name="to-view-read-only-routing-configurations"></a><span data-ttu-id="f325f-203">Para ver las configuraciones del enrutamiento de solo lectura</span><span class="sxs-lookup"><span data-stu-id="f325f-203">To view read-only routing configurations</span></span>
  
-   [<span data-ttu-id="f325f-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f325f-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
  
-   <span data-ttu-id="f325f-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (columna **read_only_routing_url**)</span><span class="sxs-lookup"><span data-stu-id="f325f-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url** column)</span></span>  
  
### <a name="to-configure-client-connection-access"></a><span data-ttu-id="f325f-206">Para configurar el acceso de la conexión de cliente</span><span class="sxs-lookup"><span data-stu-id="f325f-206">To configure client connection access</span></span>
  
-   [<span data-ttu-id="f325f-207">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f325f-207">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f325f-208">Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f325f-208">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
### <a name="to-use-connection-strings-in-applications"></a><span data-ttu-id="f325f-209">Para usar las cadenas de conexión en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f325f-209">To use connection strings in applications</span></span>
  
-   [<span data-ttu-id="f325f-210">Compatibilidad de SQL Server Native Client para la alta disponibilidad con recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="f325f-210">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](../../../relational-databases/native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
  
-   [<span data-ttu-id="f325f-211">Usar palabras clave de cadena de conexión con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f325f-211">Using Connection String Keywords with SQL Server Native Client</span></span>](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f325f-212">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f325f-212">Related Content</span></span>  
  
-   <span data-ttu-id="f325f-213">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="f325f-213">**Blogs:**</span></span>  
  
     [<span data-ttu-id="f325f-214">Calcular Read_only_routing_url para AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f325f-214">Calculating read_only_routing_url for AlwaysOn</span></span>](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson)  
  
     [<span data-ttu-id="f325f-215">Blogs del equipo de AlwaysOn de SQL Server: el blog oficial del equipo de AlwaysOn de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f325f-215">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="f325f-216">Blogs de los ingenieros de SQL Server de CSS</span><span class="sxs-lookup"><span data-stu-id="f325f-216">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="f325f-217">**Notas del producto:**</span><span class="sxs-lookup"><span data-stu-id="f325f-217">**White papers:**</span></span>  
  
     [<span data-ttu-id="f325f-218">Notas del producto de Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="f325f-218">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="f325f-219">Notas del producto del equipo de asesoramiento al cliente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f325f-219">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="f325f-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f325f-220">See Also</span></span>  
 <span data-ttu-id="f325f-221">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f325f-221">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="f325f-222">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f325f-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="f325f-223">[Secundarias activas: réplicas secundarias legibles (Grupos de disponibilidad AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="f325f-223">[Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 <span data-ttu-id="f325f-224">[Acerca del acceso de conexión de cliente a réplicas de disponibilidad &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f325f-224">[About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span></span>  
 [<span data-ttu-id="f325f-225">Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f325f-225">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
