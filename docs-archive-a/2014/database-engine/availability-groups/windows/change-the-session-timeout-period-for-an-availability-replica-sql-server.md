---
title: Cambiar el tiempo de espera de la sesión en una réplica de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], session timeout
- session timeout [SQL Server]
ms.assetid: e23c6e06-1cd1-4d4a-9bc2-e3e06ab2933d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 302ba4a2b0b72a70b05e563eb4085913074469eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750210"
---
# <a name="change-the-session-timeout-period-for-an-availability-replica-sql-server"></a><span data-ttu-id="3bb6c-102">Cambiar el tiempo de espera de la sesión en una réplica de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3bb6c-102">Change the Session-Timeout Period for an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="3bb6c-103">En este tema se describe cómo configurar el período de tiempo de espera de la sesión de una réplica de disponibilidad de AlwaysOn utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bb6c-103">This topic describes how to configure the session-timeout period of an AlwaysOn availability replica by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3bb6c-104">El período de tiempo de espera de la sesión es una propiedad de réplica que controla el número de segundos (en segundos) que una réplica de disponibilidad espera una respuesta de ping de una réplica conectada antes de determinar que la conexión ha sufrido un error.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-104">The session-timeout period is a replica property that controls how many seconds (in seconds) that an availability replica waits for a ping response from a connected replica before considering the connection to have failed.</span></span> <span data-ttu-id="3bb6c-105">De forma predeterminada, una réplica espera 10 segundos la respuesta de un ping.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-105">By default, a replica waits 10 seconds for a ping response.</span></span> <span data-ttu-id="3bb6c-106">Esta propiedad de réplica solamente se aplica a la conexión entre una réplica secundaria dada y la réplica principal del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-106">This replica property applies only the connection between a given secondary replica and the primary replica of the availability group.</span></span> <span data-ttu-id="3bb6c-107">Para obtener más información sobre el período de tiempo de espera de sesión, vea [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3bb6c-107">For more information about the session-timeout period, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="3bb6c-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="3bb6c-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3bb6c-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3bb6c-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="3bb6c-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3bb6c-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="3bb6c-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3bb6c-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3bb6c-112">**Para cambiar el período de tiempo de espera de la sesión, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="3bb6c-112">**To change the session-timeout period, using:**</span></span>  
  
     [<span data-ttu-id="3bb6c-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3bb6c-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3bb6c-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3bb6c-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="3bb6c-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bb6c-115">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3bb6c-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3bb6c-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3bb6c-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3bb6c-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="3bb6c-118">Debe estar conectado a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-118">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3bb6c-119">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3bb6c-119">Recommendations</span></span>  
 <span data-ttu-id="3bb6c-120">Es recomendable que mantenga el período de espera en 10 segundos o más.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-120">We recommend that you keep the time-out period at 10 seconds or greater.</span></span> <span data-ttu-id="3bb6c-121">Si establece el valor en menos de 10 segundos, existe la posibilidad de que un sistema sobrecargado no reciba los PING y declare un error falso.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-121">Setting the value to less than 10 seconds creates the possibility of a heavily loaded system missing PINGs and declaring a false failure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3bb6c-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3bb6c-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3bb6c-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="3bb6c-123">Permissions</span></span>  
 <span data-ttu-id="3bb6c-124">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3bb6c-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3bb6c-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3bb6c-126">**Para cambiar el período de tiempo de espera de la sesión para una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3bb6c-126">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="3bb6c-127">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-127">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3bb6c-128">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="3bb6c-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="3bb6c-129">Haga clic en el grupo de disponibilidad cuya réplica de disponibilidad desea configurar.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-129">Click the availability group whose availability replica you want to configure.</span></span>  
  
4.  <span data-ttu-id="3bb6c-130">Haga clic con el botón derecho en la réplica que vaya a configurar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-130">Right-click the replica to be configured, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3bb6c-131">En el cuadro de diálogo **Propiedades de réplica de disponibilidad** , use el campo **Tiempo de espera de sesión (segundos)** para cambiar el número de segundos del período de tiempo de espera de la sesión en la réplica.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-131">In the **Availability Replica Properties** dialog box, use the **Session timeout (seconds)** field to change the number of seconds for the session-timeout period on this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3bb6c-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3bb6c-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="3bb6c-133">**Para cambiar el período de tiempo de espera de la sesión para una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3bb6c-133">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="3bb6c-134">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-134">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3bb6c-135">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="3bb6c-135">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="3bb6c-136">ALTER AVAILABILITY GROUP *group_name*</span><span class="sxs-lookup"><span data-stu-id="3bb6c-136">ALTER AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="3bb6c-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span><span class="sxs-lookup"><span data-stu-id="3bb6c-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span></span>  
  
     <span data-ttu-id="3bb6c-138">donde *group_name* es el nombre del grupo de disponibilidad, *instance_name* es el nombre de la instancia del servidor que hospeda la réplica de disponibilidad que se va a modificar y *seconds* especifica el número mínimo de segundos que la réplica debe esperar antes de la aplicación del registro a las bases de datos cuando actúa como una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-138">where *group_name* is the name of the availability group, *instance_name* is the name of the server instance that hosts the availability replica to be modified, and *seconds* specifies the minimum number of seconds that the replica must wait before applying log to databases when acting as a secondary replica.</span></span> <span data-ttu-id="3bb6c-139">El valor predeterminado es 0 segundos, lo que indica que no hay ningún retraso de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-139">The default is 0 seconds, which indicates that there is no apply delay.</span></span>  
  
     <span data-ttu-id="3bb6c-140">En el ejemplo siguiente, escrito en la réplica principal del grupo de disponibilidad `AccountsAG` , se cambia el valor de tiempo de espera de la sesión a `15` segundos para la réplica que se encuentra en la instancia del servidor `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="3bb6c-140">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the session-timeout value to `15` seconds for the replica located on the `INSTANCE09` server instance.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP AccountsAG   
       MODIFY REPLICA ON 'INSTANCE09' WITH (SESSION_TIMEOUT = 15);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3bb6c-141">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bb6c-141">Using PowerShell</span></span>  

### <a name="to-change-the-session-timeout-period-for-an-availability-replica"></a><span data-ttu-id="3bb6c-142">Para cambiar el período de tiempo de espera de la sesión para una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3bb6c-142">To change the session-timeout period for an availability replica</span></span>
  
1.  <span data-ttu-id="3bb6c-143">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-143">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3bb6c-144">Utilice el cmdlet `Set-SqlAvailabilityReplica` con el parámetro `SessionTimeout` para cambiar el número de segundos del período de tiempo de espera de la sesión en una réplica de disponibilidad especificada.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-144">Use the `Set-SqlAvailabilityReplica` cmdlet with the `SessionTimeout` parameter to change the number of seconds for the session-timeout period on a specified availability replica.</span></span>  
  
     <span data-ttu-id="3bb6c-145">Por ejemplo, el comando siguiente establece el tiempo de espera de la sesión en 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-145">For example, the following command sets the session-timeout period to 15 seconds.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -SessionTimeout 15 -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3bb6c-146">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="3bb6c-147">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3bb6c-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="3bb6c-148">Para configurar y usar el proveedor de SQL Server PowerShell, vea [proveedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3bb6c-148">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bb6c-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bb6c-149">See Also</span></span>  
 [<span data-ttu-id="3bb6c-150">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3bb6c-150">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
