---
title: Configurar el acceso de solo lectura en una réplica de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- Availability Groups [SQL Server], read-only routing
- Availability Groups [SQL Server], client connectivity
ms.assetid: 22387419-22c4-43fa-851c-5fecec4b049b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab13081396aff46d193c1b0449d6b93042ee60d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744874"
---
# <a name="configure-read-only-access-on-an-availability-replica-sql-server"></a><span data-ttu-id="00974-102">Configurar el acceso de solo lectura en una réplica de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="00974-102">Configure Read-Only Access on an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="00974-103">De forma predeterminada, tanto el acceso de lectura y escritura como de intento de lectura se permiten en la réplica principal. No se permiten conexiones en las réplicas secundarias de un grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="00974-103">By default both read-write and read-intent access are allowed to the primary replica and no connections are allowed to secondary replicas of an AlwaysOn availability group.</span></span> <span data-ttu-id="00974-104">En este tema se describe cómo se configura el acceso de conexión de una réplica de disponibilidad de un grupo de disponibilidad AlwaysOn en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00974-104">This topic describes how to configure connection access on an availability replica of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="00974-105">Para más información sobre las implicaciones de habilitar el acceso de solo lectura en una réplica secundaria y una introducción al acceso de conexión, vea [Acerca del acceso de conexión de cliente a réplicas de disponibilidad &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) y [Secundarias activas: réplicas secundarias legibles &#40;grupos de disponibilidad AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="00974-105">For information about the implications of enabling read-only access for a secondary replica and for an introduction to connection access, see [About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) and [Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="00974-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="00974-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="00974-107">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="00974-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="00974-108">Para configurar otro acceso de conexión, debe estar conectado a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-108">To configure different connection access, you must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="00974-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="00974-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="00974-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="00974-110">Permissions</span></span>  
  
|<span data-ttu-id="00974-111">Tarea</span><span class="sxs-lookup"><span data-stu-id="00974-111">Task</span></span>|<span data-ttu-id="00974-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="00974-112">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="00974-113">Para configurar réplicas al crear un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="00974-113">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="00974-114">Se requiere la pertenencia al rol fijo de servidor **sysadmin** y el permiso de servidor CREATE AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="00974-114">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="00974-115">Para modificar una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="00974-115">To modify an availability replica</span></span>|<span data-ttu-id="00974-116">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="00974-116">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="00974-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00974-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="00974-118">**Para configurar el acceso en una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="00974-118">**To configure access on an availability replica**</span></span>  
  
1.  <span data-ttu-id="00974-119">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="00974-119">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="00974-120">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="00974-120">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="00974-121">Haga clic en el grupo de disponibilidad cuya réplica desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="00974-121">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="00974-122">Haga clic con el botón derecho en la réplica de disponibilidad y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="00974-122">Right-click the availability replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="00974-123">En el cuadro de diálogo **Propiedades de réplica de disponibilidad** , puede cambiar el acceso de conexión para el rol principal y para el secundario, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="00974-123">In the **Availability Replica Properties** dialog box, you can change the connection access for the primary role and for the secondary role, as follows:</span></span>  
  
    -   <span data-ttu-id="00974-124">Para el rol secundario, seleccione un nuevo valor en la lista desplegable **Secundario legible** , del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="00974-124">For the secondary role, select a new value from the **Readable secondary** drop list, as follows:</span></span>  
  
         <span data-ttu-id="00974-125">**No**</span><span class="sxs-lookup"><span data-stu-id="00974-125">**No**</span></span>  
         <span data-ttu-id="00974-126">No se permiten conexiones de usuario a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="00974-126">No user connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="00974-127">No están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-127">They are not available for read access.</span></span> <span data-ttu-id="00974-128">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00974-128">This is the default setting.</span></span>  
  
         <span data-ttu-id="00974-129">**Solo intento de lectura**</span><span class="sxs-lookup"><span data-stu-id="00974-129">**Read-intent only**</span></span>  
         <span data-ttu-id="00974-130">Únicamente se permiten conexiones de solo lectura a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="00974-130">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="00974-131">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-131">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="00974-132">**Sí**</span><span class="sxs-lookup"><span data-stu-id="00974-132">**Yes**</span></span>  
         <span data-ttu-id="00974-133">Se permiten todas las conexiones a las bases de datos secundarias de esta réplica, pero solo para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-133">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="00974-134">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-134">The secondary database(s) are all available for read access.</span></span>  
  
    -   <span data-ttu-id="00974-135">Para el rol principal, seleccione un nuevo valor en la lista desplegable **Conexiones de rol principal** , del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="00974-135">For the primary role, select a new value from the **Connections in primary role** drop list, as follows:</span></span>  
  
         <span data-ttu-id="00974-136">**Permitir todas las conexiones**</span><span class="sxs-lookup"><span data-stu-id="00974-136">**Allow all connections**</span></span>  
         <span data-ttu-id="00974-137">Se permiten todas las conexiones con las bases de datos de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-137">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="00974-138">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00974-138">This is the default setting.</span></span>  
  
         <span data-ttu-id="00974-139">**Permitir conexiones de lectura o escritura**</span><span class="sxs-lookup"><span data-stu-id="00974-139">**Allow read/write connections**</span></span>  
         <span data-ttu-id="00974-140">Cuando la propiedad Application Intent está establecida en **ReadWrite** o no tiene ningún valor, se permite la conexión.</span><span class="sxs-lookup"><span data-stu-id="00974-140">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="00974-141">No se permiten las conexiones en las que la propiedad de conexión Application Intent esté establecida en **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="00974-141">Connections where the Application Intent connection property is set to **ReadOnly** are not allowed.</span></span> <span data-ttu-id="00974-142">Esto puede ayudar a evitar que los clientes conecten por equivocación una carga de trabajo de intención de lectura a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-142">This can help prevent customers from connecting a read-intent work load to the primary replica by mistake.</span></span> <span data-ttu-id="00974-143">Para obtener más información sobre propiedad de conexión Application Intent, vea [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="00974-143">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="00974-144">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00974-144">Using Transact-SQL</span></span>  
 <span data-ttu-id="00974-145">**Para configurar el acceso en una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="00974-145">**To configure access on an availability replica**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00974-146">Para ver un ejemplo de este procedimiento, vea [Ejemplo (Transact-SQL)](#TsqlExample)más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="00974-146">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="00974-147">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-147">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="00974-148">Si va a especificar una réplica para un nuevo grupo de disponibilidad, use la instrucción [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00974-148">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="00974-149">Si va a agregar o modificar una réplica de un grupo de disponibilidad existente, use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00974-149">If you are adding or modifying a replica of an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="00974-150">Para configurar el acceso de conexión para el rol secundario, en la cláusula ADD REPLICA o MODIFY REPLICA WITH, especifique la opción SECONDARY_ROLE, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="00974-150">To configure connection access for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="00974-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="00974-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span></span>  
  
         <span data-ttu-id="00974-152">donde,</span><span class="sxs-lookup"><span data-stu-id="00974-152">where,</span></span>  
  
         <span data-ttu-id="00974-153">No</span><span class="sxs-lookup"><span data-stu-id="00974-153">NO</span></span>  
         <span data-ttu-id="00974-154">No se permiten conexiones directas a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="00974-154">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="00974-155">No están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-155">They are not available for read access.</span></span> <span data-ttu-id="00974-156">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00974-156">This is the default setting.</span></span>  
  
         <span data-ttu-id="00974-157">READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="00974-157">READ_ONLY</span></span>  
         <span data-ttu-id="00974-158">Únicamente se permiten conexiones de solo lectura a las bases de datos secundarias de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="00974-158">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="00974-159">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-159">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="00974-160">ALL</span><span class="sxs-lookup"><span data-stu-id="00974-160">ALL</span></span>  
         <span data-ttu-id="00974-161">Se permiten todas las conexiones a las bases de datos secundarias de esta réplica, pero solo para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-161">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="00974-162">Todas las bases de datos secundarias están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-162">The secondary database(s) are all available for read access.</span></span>  
  
3.  <span data-ttu-id="00974-163">Para configurar el acceso de conexión para el rol principal, en la cláusula ADD REPLICA o MODIFY REPLICA WITH, especifique la opción PRIMARY_ROLE, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="00974-163">To configure connection access for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
     <span data-ttu-id="00974-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="00974-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span></span>  
  
     <span data-ttu-id="00974-165">donde,</span><span class="sxs-lookup"><span data-stu-id="00974-165">where,</span></span>  
  
     <span data-ttu-id="00974-166">READ_WRITE</span><span class="sxs-lookup"><span data-stu-id="00974-166">READ_WRITE</span></span>  
     <span data-ttu-id="00974-167">No se permiten las conexiones en las que la propiedad de conexión Application Intent esté establecida en **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="00974-167">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span>  <span data-ttu-id="00974-168">Cuando la propiedad Application Intent está establecida en **ReadWrite** o no tiene ningún valor, se permite la conexión.</span><span class="sxs-lookup"><span data-stu-id="00974-168">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="00974-169">Para obtener más información sobre propiedad de conexión Application Intent, vea [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="00974-169">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
     <span data-ttu-id="00974-170">ALL</span><span class="sxs-lookup"><span data-stu-id="00974-170">ALL</span></span>  
     <span data-ttu-id="00974-171">Se permiten todas las conexiones con las bases de datos de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-171">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="00974-172">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00974-172">This is the default setting.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="00974-173">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="00974-173">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="00974-174">En el siguiente ejemplo se agrega una réplica secundaria a un grupo de disponibilidad denominado *AG2*.</span><span class="sxs-lookup"><span data-stu-id="00974-174">The following example adds a secondary replica to an availability group named *AG2*.</span></span> <span data-ttu-id="00974-175">Se especifica una instancia de servidor independiente, *COMPUTER03\HADR_INSTANCE*, para hospedar la nueva réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="00974-175">A stand-alone server instance, *COMPUTER03\HADR_INSTANCE*, is specified to host the new availability replica.</span></span> <span data-ttu-id="00974-176">Esta réplica configurada para permitir las conexiones de solo lectura-escritura para el rol principal y permitir las conexiones de solo intención de lectura para el rol secundario.</span><span class="sxs-lookup"><span data-stu-id="00974-176">This replica configured to allow only read-write connections for the primary role and to allow only read-intent connections for secondary role.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AG2   
   ADD REPLICA ON   
      'COMPUTER03\HADR_INSTANCE' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03:7022',  
         PRIMARY_ROLE ( ALLOW_CONNECTIONS = READ_WRITE ),  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY )  
         );   
GO  
```  
  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="00974-177">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="00974-177">Using PowerShell</span></span>  

### <a name="to-configure-access-on-an-availability-replica"></a><span data-ttu-id="00974-178">Para configurar el acceso en una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="00974-178">To configure access on an availability replica</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="00974-179">Para obtener un ejemplo de código, vea los ejemplos de PowerShell más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="00974-179">For a code example, see the PowerShell examples later in this section.</span></span>  
  
1.  <span data-ttu-id="00974-180">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-180">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="00974-181">Para agregar una réplica de disponibilidad a un grupo de disponibilidad, use el cmdlet `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="00974-181">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="00974-182">Para modificar una réplica de disponibilidad existente, use el cmdlet `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="00974-182">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="00974-183">Los parámetros pertinentes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="00974-183">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="00974-184">Para configurar el acceso de conexión para el rol secundario, especifique el `ConnectionModeInSecondaryRole` parámetro *secondary_role_keyword* , donde *secondary_role_keyword* es igual a uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="00974-184">To configure connection access for the secondary role, specify the `ConnectionModeInSecondaryRole`*secondary_role_keyword* parameter, where *secondary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowNoConnections`  
         <span data-ttu-id="00974-185">No se permiten conexiones directas con las bases de datos de la réplica secundaria y las bases de datos no están disponibles para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-185">No direct connections are allowed to the databases in the secondary replica and the databases are not available for read access.</span></span> <span data-ttu-id="00974-186">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00974-186">This is the default setting.</span></span>  
  
         `AllowReadIntentConnectionsOnly`  
         <span data-ttu-id="00974-187">Solo se permiten conexiones con las bases de datos de la réplica secundaria en las que la propiedad Application Intent está establecida en **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="00974-187">Connections are allowed only to the databases in the secondary replica where the Application Intent property is set to **ReadOnly**.</span></span> <span data-ttu-id="00974-188">Para obtener más información acerca de esta propiedad, vea [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="00974-188">For more information about this property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="00974-189">Se permiten todas las conexiones con las bases de datos de la réplica secundaria para acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="00974-189">All connections are allowed to the databases in the secondary replica for read-only access.</span></span>  
  
    -   <span data-ttu-id="00974-190">Para configurar el acceso de conexión para el rol principal, especifique `ConnectionModeInPrimaryRole` *primary_role_keyword*, donde *primary_role_keyword* es igual a uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="00974-190">To configure connection access for the primary role, specify `ConnectionModeInPrimaryRole`*primary_role_keyword*, where *primary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowReadWriteConnections`  
         <span data-ttu-id="00974-191">No se permiten las conexiones en las que la propiedad de conexión Application Intent esté establecida en ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="00974-191">Connections where the Application Intent connection property is set to ReadOnly are disallowed.</span></span> <span data-ttu-id="00974-192">Cuando la propiedad Application Intent está establecida en ReadWrite o no tiene ningún valor, se permite la conexión.</span><span class="sxs-lookup"><span data-stu-id="00974-192">When the Application Intent property is set to ReadWrite or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="00974-193">Para obtener más información sobre propiedad de conexión Application Intent, vea [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="00974-193">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="00974-194">Se permiten todas las conexiones con las bases de datos de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="00974-194">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="00974-195">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00974-195">This is the default setting.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00974-196">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00974-196">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="00974-197">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="00974-197">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="00974-198">Para configurar y usar el proveedor de SQL Server PowerShell, vea [proveedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="00974-198">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
<span data-ttu-id="00974-199">En el siguiente ejemplo, los parámetros `ConnectionModeInSecondaryRole` y `ConnectionModeInPrimaryRole` se establecen en `AllowAllConnections`.</span><span class="sxs-lookup"><span data-stu-id="00974-199">The following example, sets the both the `ConnectionModeInSecondaryRole` and `ConnectionModeInPrimaryRole` parameters to `AllowAllConnections`.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  

Set-SqlAvailabilityReplica -ConnectionModeInSecondaryRole "AllowAllConnections" `
 -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ConnectionModeInPrimaryRole "AllowAllConnections" `
-InputObject $primaryReplica
```  

##  <a name="follow-up-after-configuring-read-only-access-for-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="00974-200">Seguimiento: después de configurar el acceso de solo lectura para una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="00974-200">Follow Up: After Configuring Read-Only Access for an Availability Replica</span></span>  
 <span data-ttu-id="00974-201">**Acceso de solo lectura a una réplica secundaria legible**</span><span class="sxs-lookup"><span data-stu-id="00974-201">**Read-only access to a readable secondary replica**</span></span>  
  
-   <span data-ttu-id="00974-202">Cuando se usa la [utilidad BCP](../../../tools/bcp-utility.md) o la [utilidad SQLCMD](../../../tools/sqlcmd-utility.md), se puede especificar el acceso de solo lectura a cualquier réplica secundaria que esté habilitada para el acceso de solo lectura especificando el `-K ReadOnly` modificador.</span><span class="sxs-lookup"><span data-stu-id="00974-202">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
-   <span data-ttu-id="00974-203">Para habilitar las aplicaciones cliente para conectarse a réplicas secundarias legibles:</span><span class="sxs-lookup"><span data-stu-id="00974-203">To enable client applications to connect to readable secondary replicas:</span></span>  
  
    ||<span data-ttu-id="00974-204">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="00974-204">Prerequisite</span></span>|<span data-ttu-id="00974-205">Vínculo</span><span class="sxs-lookup"><span data-stu-id="00974-205">Link</span></span>|  
    |-|------------------|----------|  
    |<span data-ttu-id="00974-206">![Casilla de verificación](../../media/checkboxemptycenterxtraspacetopandright.gif "Casilla de verificación")</span><span class="sxs-lookup"><span data-stu-id="00974-206">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="00974-207">Asegúrese de que el grupo de disponibilidad tiene un agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="00974-207">Ensure that the availability group has a listener.</span></span>|[<span data-ttu-id="00974-208">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00974-208">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)|  
    |<span data-ttu-id="00974-209">![Casilla de verificación](../../media/checkboxemptycenterxtraspacetopandright.gif "Casilla de verificación")</span><span class="sxs-lookup"><span data-stu-id="00974-209">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="00974-210">Configure el enrutamiento de solo lectura en un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="00974-210">Configure read-only routing for the availability group.</span></span>|[<span data-ttu-id="00974-211">Configurar el enrutamiento de solo lectura para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00974-211">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)|  
  
 <span data-ttu-id="00974-212">**Factores que podrían afectar a los desencadenadores y trabajos tras la conmutación por error**</span><span class="sxs-lookup"><span data-stu-id="00974-212">**Factors that might affect triggers and jobs after a failover**</span></span>  
  
 <span data-ttu-id="00974-213">Si tiene desencadenadores y trabajos que darán error al ejecutarse en una base de datos secundarias no legible o en una base de datos secundaria legible, tiene que escribir los desencadenadores y los trabajos para controlar una réplica dad y determinar si la base de datos es una base de datos principal o si es una base de datos secundaria legible.</span><span class="sxs-lookup"><span data-stu-id="00974-213">If you have triggers and jobs that will fail when running on a non-readable secondary database or on a readable secondary database, you need to script the triggers and jobs to check on a given replica to determine whether the database is a primary database or is a readable secondary database.</span></span> <span data-ttu-id="00974-214">Para obtener esta información, use la función [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) para devolver la propiedad **Updatability** de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="00974-214">To obtain this information, use the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **Updatability** property of the database.</span></span> <span data-ttu-id="00974-215">Para identificar una base de datos de solo lectura, especifique READ_ONLY como el valor, según se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="00974-215">To identify a read-only database, specify READ_ONLY as the value, as follows:</span></span>  
  
```  
DATABASEPROPERTYEX([db name],'Updatability') = N'READ_ONLY'  
```  
  
 <span data-ttu-id="00974-216">Para identificar una base de datos de solo escritura, especifique READ_WRITE como el valor.</span><span class="sxs-lookup"><span data-stu-id="00974-216">To identify a read-write database, specify READ_WRITE as the value.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="00974-217">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="00974-217">Related Tasks</span></span>  
  
-   [<span data-ttu-id="00974-218">Configurar el enrutamiento de solo lectura para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00974-218">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="00974-219">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00974-219">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="00974-220">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="00974-220">Related Content</span></span>  
  
-   [<span data-ttu-id="00974-221">Always On: propuesta de valor de secundaria legible</span><span class="sxs-lookup"><span data-stu-id="00974-221">Always On: Value Proposition of Readable Secondary</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-value-proposition-of-readable-secondary)  
  
-   [<span data-ttu-id="00974-222">Always On: ¿por qué hay dos opciones para habilitar una réplica secundaria para la carga de trabajo de lectura?</span><span class="sxs-lookup"><span data-stu-id="00974-222">Always On: Why there are two options to enable a secondary replica for read workload?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-why-there-are-two-options-to-enable-a-secondary-replica-for-read-workload)  
  
-   [<span data-ttu-id="00974-223">Always On: configuración de una réplica secundaria legible</span><span class="sxs-lookup"><span data-stu-id="00974-223">Always On: Setting up Readable Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-setting-up-readable-seconary-replica)  
  
-   [<span data-ttu-id="00974-224">Always On: acabo de habilitar una secundaria legible pero mi consulta está bloqueada</span><span class="sxs-lookup"><span data-stu-id="00974-224">Always On: I just enabled Readable Secondary but my query is blocked?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-i-just-enabled-readable-secondary-but-my-query-is-blocked)  
  
-   [<span data-ttu-id="00974-225">Always On: ofrecer las estadísticas más recientes de la secundaria legible, la base de datos de solo lectura y la instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="00974-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-making-latest-statistics-available-on-readable-secondary-read-only-database-and-database-snapshot)  
  
-   [<span data-ttu-id="00974-226">Always On: desafíos de las estadísticas de la base de datos de solo lectura, la instantánea de base de datos y la réplica secundaria</span><span class="sxs-lookup"><span data-stu-id="00974-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-challenges-with-statistics-on-readonly-database-database-snapshot-and-secondary-replica)  
  
-   [<span data-ttu-id="00974-227">Always On: impacto sobre la carga de trabajo principal al ejecutar la carga de trabajo de informes en la réplica secundaria</span><span class="sxs-lookup"><span data-stu-id="00974-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-on-the-primary-workload-when-you-run-reporting-workload-on-the-secondary-replica)  
  
-   [<span data-ttu-id="00974-228">Always On: efectos de asignar la carga de trabajo de informes de la secundaria legible al aislamiento de instantánea</span><span class="sxs-lookup"><span data-stu-id="00974-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-of-mapping-reporting-workload-on-readable-secondary-to-snapshot-isolation)  
  
-   [<span data-ttu-id="00974-229">Always On: minimizar el bloqueo de subprocesos REDO al ejecutar la carga de trabajo de informes en la réplica secundaria</span><span class="sxs-lookup"><span data-stu-id="00974-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-minimizing-blocking-of-redo-thread-when-running-reporting-workload-on-secondary-replica)  
  
-   [<span data-ttu-id="00974-230">Always On: secundaria legible y latencia de datos</span><span class="sxs-lookup"><span data-stu-id="00974-230">Always On: Readable Secondary and data latency</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-readable-secondary-and-data-latency)  
  
## <a name="see-also"></a><span data-ttu-id="00974-231">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00974-231">See Also</span></span>  
 <span data-ttu-id="00974-232">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00974-232">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="00974-233">Secundarias activas: réplicas secundarias legibles &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="00974-233">Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  
 [<span data-ttu-id="00974-234">Acerca del acceso de conexión de cliente a réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00974-234">About Client Connection Access to Availability Replicas &#40;SQL Server&#41;</span></span>](about-client-connection-access-to-availability-replicas-sql-server.md)  
