---
title: Cambiar el modo de conmutación por error de una réplica de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover modes [SQL Server]
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover modes
- Availability Groups [SQL Server], configuring
ms.assetid: 619a826f-8e65-48eb-8c34-39497d238279
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d946440e2950192299c42652babb4082790dbd03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750217"
---
# <a name="change-the-failover-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="3386d-102">Cambiar el modo de conmutación por error de una réplica de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3386d-102">Change the Failover Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="3386d-103">En este tema se describe cómo cambiar el modo de conmutación por error de una réplica de disponibilidad de un grupo de disponibilidad AlwaysOn en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3386d-103">This topic describes how to change the failover mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="3386d-104">El modo de conmutación por error es una propiedad de réplica que determina el modo de conmutación por error para las réplicas que se ejecutan en modo de disponibilidad de confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="3386d-104">The failover mode is a replica property that determines the failover mode for replicas that run under synchronous-commit availability mode.</span></span> <span data-ttu-id="3386d-105">Para más información, vea [Conmutación por error y modos de conmutación por error &#40;grupos de disponibilidad AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) y [Modos de disponibilidad &#40;grupos de disponibilidad AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3386d-105">For more information, see [Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) and [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3386d-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3386d-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="3386d-107">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="3386d-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="3386d-108">Esta tarea solo se admite en las réplicas principales.</span><span class="sxs-lookup"><span data-stu-id="3386d-108">This task is supported only on primary replicas.</span></span> <span data-ttu-id="3386d-109">Debe estar conectado a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3386d-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="3386d-110">Las instancias de clúster de conmutación por error (FCI) de SQL Server no admiten la conmutación automática por error de grupos de disponibilidad, por lo tanto, todas las réplicas de disponibilidad hospedadas por un FCI solo se pueden configurar para la conmutación por error manual.</span><span class="sxs-lookup"><span data-stu-id="3386d-110">SQL Server Failover Cluster Instances (FCIs) do not support automatic failover by availability groups, so any availability replica that is hosted by an FCI can only be configured for manual failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3386d-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3386d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3386d-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="3386d-112">Permissions</span></span>  
 <span data-ttu-id="3386d-113">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3386d-113">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3386d-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3386d-114">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3386d-115">**Para cambiar el modo de conmutación por error de una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3386d-115">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="3386d-116">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="3386d-116">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3386d-117">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="3386d-117">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="3386d-118">Haga clic en el grupo de disponibilidad cuya réplica desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="3386d-118">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="3386d-119">Haga clic con el botón derecho en la réplica y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3386d-119">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3386d-120">En el cuadro de diálogo **Propiedades de réplica de disponibilidad** , use la lista desplegable **Modo de conmutación por error** para cambiar el modo de conmutación por error de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="3386d-120">In the **Availability Replica Properties** dialog box, use the **Failover mode** drop list to change the failover mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3386d-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3386d-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="3386d-122">**Para cambiar el modo de conmutación por error de una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="3386d-122">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="3386d-123">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3386d-123">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3386d-124">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="3386d-124">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="3386d-125">ALTER AVAILABILITY GROUP *nombre_grupo* MODIFY REPLICA ON '*nombre_servidor*'</span><span class="sxs-lookup"><span data-stu-id="3386d-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="3386d-126">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="3386d-126">WITH ( {</span></span>  
  
     <span data-ttu-id="3386d-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="3386d-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="3386d-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="3386d-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="3386d-129">}  )</span><span class="sxs-lookup"><span data-stu-id="3386d-129">}  )</span></span>  
  
     <span data-ttu-id="3386d-130">, donde</span><span class="sxs-lookup"><span data-stu-id="3386d-130">where</span></span>  
  
    -   <span data-ttu-id="3386d-131">*nombre_grupo* es el nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="3386d-131">*group_name* is the name of the availability group.</span></span>  
  
    -   <span data-ttu-id="3386d-132">{ '*nombre_sistema*[\\*nombre_instancia*]' | '*nombre_red_FCI*[\\*nombre_instancia*]' }</span><span class="sxs-lookup"><span data-stu-id="3386d-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span></span>  
  
         <span data-ttu-id="3386d-133">Especifica la dirección de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda la réplica de disponibilidad que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="3386d-133">Specifies the address of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica to be altered.</span></span> <span data-ttu-id="3386d-134">Los componentes de esta dirección son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3386d-134">The components of this address are as follows:</span></span>  
  
         <span data-ttu-id="3386d-135">*nombre_sistema*</span><span class="sxs-lookup"><span data-stu-id="3386d-135">*system_name*</span></span>  
         <span data-ttu-id="3386d-136">Es el nombre de NetBIOS del sistema informático en el que reside una instancia del servidor independiente.</span><span class="sxs-lookup"><span data-stu-id="3386d-136">Is the NetBIOS name of the computer system on which a stand-alone server instance resides.</span></span>  
  
         <span data-ttu-id="3386d-137">*nombre_red_FCI*</span><span class="sxs-lookup"><span data-stu-id="3386d-137">*FCI_network_name*</span></span>  
         <span data-ttu-id="3386d-138">Es el nombre de red que se utiliza para tener acceso a un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en el que una instancia del servidor de destino es un asociado de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (un FCI).</span><span class="sxs-lookup"><span data-stu-id="3386d-138">Is the network name that is used to access a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster in which a target server instance is a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover partner (an FCI).</span></span>  
  
         <span data-ttu-id="3386d-139">*instance_name*</span><span class="sxs-lookup"><span data-stu-id="3386d-139">*instance_name*</span></span>  
         <span data-ttu-id="3386d-140">Es el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda la réplica de disponibilidad de destino.</span><span class="sxs-lookup"><span data-stu-id="3386d-140">Is the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the target availability replica.</span></span> <span data-ttu-id="3386d-141">En el caso de una instancia del servidor predeterminada, *nombre_instancia* es opcional.</span><span class="sxs-lookup"><span data-stu-id="3386d-141">For a default server instance, *instance_name* is optional.</span></span>  
  
     <span data-ttu-id="3386d-142">Para obtener más información sobre estos parámetros, vea [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3386d-142">For more information about these parameters, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="3386d-143">En el ejemplo siguiente, escrito en la réplica principal del grupo de disponibilidad *MyAG* , se cambia el modo de conmutación por error a conmutación automática por error en la réplica de disponibilidad que se encuentra en la instancia del servidor predeterminada en un equipo denominado *COMPUTER01*.</span><span class="sxs-lookup"><span data-stu-id="3386d-143">The following example, entered on the primary replica of the *MyAG* availability group, changes the failover mode to automatic failover on the availability replica that is located on the default server instance on a computer named *COMPUTER01*.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP MyAG MODIFY REPLICA ON 'COMPUTER01' WITH  
       (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3386d-144">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3386d-144">Using PowerShell</span></span>  

### <a name="to-change-the-failover-mode-of-an-availability-replica"></a><span data-ttu-id="3386d-145">Para cambiar el modo de conmutación por error de una réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="3386d-145">To change the failover mode of an availability replica</span></span>
  
1.  <span data-ttu-id="3386d-146">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3386d-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3386d-147">Utilice el cmdlet `Set-SqlAvailabilityReplica` con el parámetro `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="3386d-147">Use the `Set-SqlAvailabilityReplica` cmdlet with the `FailoverMode` parameter.</span></span> <span data-ttu-id="3386d-148">Cuando se establece una réplica en conmutación automática por error, puede que sea necesario usar el parámetro `AvailabilityMode` para cambiar la réplica al modo de disponibilidad de confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="3386d-148">When setting a replica to automatic failover, you might need to use the `AvailabilityMode` parameter to change the replica to synchronous-commit availability mode.</span></span>  
  
     <span data-ttu-id="3386d-149">Por ejemplo, el comando siguiente modifica la réplica `MyReplica` en el grupo de disponibilidad `MyAg` para utilizar el modo de disponibilidad de confirmación sincrónica y admitir la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="3386d-149">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\Replicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3386d-150">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3386d-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="3386d-151">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3386d-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="3386d-152">Para configurar y usar el proveedor de SQL Server PowerShell, vea [proveedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3386d-152">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3386d-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3386d-153">See Also</span></span>  
 [<span data-ttu-id="3386d-154">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3386d-154">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="3386d-155">[Modos de disponibilidad &#40;Grupos de disponibilidad AlwaysOn&#41;](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="3386d-155">[Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="3386d-156">Conmutación por error y modos de conmutación por error &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="3386d-156">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md) 
