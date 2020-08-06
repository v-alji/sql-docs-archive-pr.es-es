---
title: Realizar una conmutación por error manual planeada de un grupo de disponibilidad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.manualfailover.f1
helpviewer_keywords:
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: 419f655d-3f9a-4e7d-90b9-f0bab47b3178
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c62942eaa8f4ab4472bca5c7123e5999eb069216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747194"
---
# <a name="perform-a-planned-manual-failover-of-an-availability-group-sql-server"></a><span data-ttu-id="fbe62-102">Realizar una conmutación por error manual planeada de un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fbe62-102">Perform a Planned Manual Failover of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="fbe62-103"> En este tema se describe cómo realizar una conmutación por error manual sin pérdida de datos (una *conmutación por error manual planeada*) en un grupo de disponibilidad AlwaysOn mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)] o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbe62-103">This topic describes how to perform a manual failover without data loss (a *planned manual failover*) on an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="fbe62-104">Un grupo de disponibilidad realiza la conmutación por error en el nivel de réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fbe62-104">An availability group fails over at the level of an availability replica.</span></span> <span data-ttu-id="fbe62-105">Una conmutación por error manual planeada, como cualquier conmutación por error de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , realiza la transición de una réplica secundaria al rol principal y, simultáneamente, realiza la transición de la réplica principal anterior al rol secundario.</span><span class="sxs-lookup"><span data-stu-id="fbe62-105">A planned manual failover, like any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] failover, transitions a secondary replica to primary role and, concurrently, transitions the former primary replica to the secondary role.</span></span>  
  
 <span data-ttu-id="fbe62-106">Una conmutación por error manual planeada, que solo se admite cuando la réplica principal y la réplica secundaria de destino se ejecutan en modo de confirmación sincrónica y están sincronizadas actualmente, conserva todos los datos de las bases de datos secundarias que están unidas al grupo de disponibilidad en la réplica secundaria de destino.</span><span class="sxs-lookup"><span data-stu-id="fbe62-106">A planned manual failover, which is supported only when the primary replica and the target secondary replica are running in synchronous-commit mode and are currently synchronized, preserves all the data in the secondary databases that are joined to the availability group on the target secondary replica.</span></span> <span data-ttu-id="fbe62-107">Una vez que la réplica principal anterior realiza la transición al rol secundario, sus bases de datos se convierten en bases de datos secundarias y comienzan la sincronización con las nuevas bases de datos principales.</span><span class="sxs-lookup"><span data-stu-id="fbe62-107">Once the former primary replica transitions to the secondary role, its databases become secondary databases and begin synchronizing with the new primary databases.</span></span> <span data-ttu-id="fbe62-108">Después de que todas realicen la transición al estado SYNCHRONIZED, la nueva réplica secundaria es apta para actuar como destino de una conmutación por error manual planeada futura.</span><span class="sxs-lookup"><span data-stu-id="fbe62-108">After they all transition into the SYNCHRONIZED state, the new secondary replica becomes eligible to serve as the target of a future planned manual failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbe62-109">Si las replicas principal y secundaria se configuran para el modo de conmutación automática por error, una vez que la réplica secundaria esté sincronizada, también pueden actuar como destino de una conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="fbe62-109">If the secondary and primary replicas are both configured for automatic failover mode, once the secondary replica is synchronized, it can also serve as the target for an automatic failover.</span></span> <span data-ttu-id="fbe62-110">Para más información, vea [Modos de disponibilidad &#40;Grupos de disponibilidad AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="fbe62-110">For more information, see [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fbe62-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fbe62-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fbe62-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fbe62-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fbe62-113">Un comando de conmutación por error realiza la devolución en cuanto la réplica secundaria de destino haya aceptado el comando.</span><span class="sxs-lookup"><span data-stu-id="fbe62-113">A failover command returns as soon as the target secondary replica has accepted the command.</span></span> <span data-ttu-id="fbe62-114">Sin embargo, la recuperación de la base de datos se produce de forma asincrónica cuando el grupo de disponibilidad ha terminado la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="fbe62-114">However, database recovery occurs asynchronously after the availability group has finished failing over.</span></span>  
  
-   <span data-ttu-id="fbe62-115">La coherencia entre las bases de datos de las distintas bases de datos del grupo de disponibilidad no se mantiene en la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="fbe62-115">Cross-database consistency across databases within the availability group is not maintained on failover.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fbe62-116">[!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no admite las transacciones entre bases de datos ni las transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="fbe62-116">Cross-database transactions and distributed transactions are not supported by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="fbe62-117">Para más información, vea [Transacciones entre bases de datos no compatibles para la creación de reflejo de la base de datos o grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="fbe62-117">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="fbe62-118">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="fbe62-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="fbe62-119">La réplica secundaria de destino y la réplica principal deben ejecutarse en modo de disponibilidad de confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="fbe62-119">The target secondary replica and the primary replica must both be running in synchronous-commit availability mode.</span></span>  
  
-   <span data-ttu-id="fbe62-120">La réplica secundaria de destino debe estar sincronizada actualmente con la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="fbe62-120">The target secondary replica must currently be synchronized with the primary replica.</span></span> <span data-ttu-id="fbe62-121">Esto requiere que todas las bases de datos secundarias de la réplica secundaria deben estar unidas al grupo de disponibilidad y sincronizadas con sus bases de datos principales correspondientes (es decir, las bases de datos secundarias locales deben estar en estado SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="fbe62-121">This requires that all the secondary databases on this secondary replica must have been joined to the availability group and be synchronized with their corresponding primary databases (that is, the local secondary databases must be SYNCHRONIZED).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fbe62-122">Para determinar la preparación para la conmutación por error de una réplica secundaria, consulte la columna **is_failover_ready** de la vista de administración dinámica [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) o examine la columna **Preparación para la conmutación por error** de [Panel de grupo AlwaysOn](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="fbe62-122">To determine the failover readiness of an secondary replica, query the **is_failover_ready** column in the [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) dynamic management view, or look at the **Failover Readiness** column of the [AlwaysOn Group Dashboard](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="fbe62-123">Esta tarea solo se admite en la réplica secundaria de destino.</span><span class="sxs-lookup"><span data-stu-id="fbe62-123">This task is supported only on the target secondary replica.</span></span> <span data-ttu-id="fbe62-124">Debe estar conectado a la instancia del servidor que hospeda la réplica secundaria de destino.</span><span class="sxs-lookup"><span data-stu-id="fbe62-124">You must be connected to the server instance that hosts the target secondary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fbe62-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fbe62-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fbe62-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="fbe62-126">Permissions</span></span>  
 <span data-ttu-id="fbe62-127">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="fbe62-127">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fbe62-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fbe62-128">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fbe62-129">**Para realizar la conmutación por error manual de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="fbe62-129">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="fbe62-130">En el Explorador de objetos, conéctese a una instancia de servidor que hospede una réplica secundaria del grupo de disponibilidad que necesita ser objeto de conmutación por error, y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="fbe62-130">In Object Explorer, connect to a server instance that hosts a secondary replica of the availability group that needs to be failed over, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="fbe62-131">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="fbe62-131">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="fbe62-132">Haga clic con el botón derecho en el grupo de disponibilidad que va a ser objeto de conmutación por error y seleccione el comando **Conmutación por error** .</span><span class="sxs-lookup"><span data-stu-id="fbe62-132">Right-click the availability group to be failed over, and select the **Failover** command.</span></span>  
  
4.  <span data-ttu-id="fbe62-133">Esto inicia el Asistente para conmutación por error del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fbe62-133">This launches the Failover Availability Group Wizard.</span></span> <span data-ttu-id="fbe62-134">Para obtener más información, vea [Usar el Asistente para grupo de disponibilidad de conmutación por error &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="fbe62-134">For more information, see [Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fbe62-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fbe62-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="fbe62-136">**Para realizar la conmutación por error manual de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="fbe62-136">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="fbe62-137">Conéctese a la instancia del servidor que hospeda la réplica secundaria de destino.</span><span class="sxs-lookup"><span data-stu-id="fbe62-137">Connect to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="fbe62-138">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="fbe62-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="fbe62-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span><span class="sxs-lookup"><span data-stu-id="fbe62-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span></span>  
  
     <span data-ttu-id="fbe62-140">donde *group_name* es el nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fbe62-140">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="fbe62-141">En el ejemplo siguiente se realiza manualmente una conmutación por error del grupo de disponibilidad *MyAg* a la réplica secundaria conectada.</span><span class="sxs-lookup"><span data-stu-id="fbe62-141">The following example manually fails over the *MyAg* availability group to the connected secondary replica.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAg FAILOVER;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="fbe62-142">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbe62-142">Using PowerShell</span></span>  
 <span data-ttu-id="fbe62-143">**Para realizar la conmutación por error manual de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="fbe62-143">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="fbe62-144">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica secundaria de destino.</span><span class="sxs-lookup"><span data-stu-id="fbe62-144">Change directory (`cd`) to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="fbe62-145">Utilice el cmdlet `Switch-SqlAvailabilityGroup`.</span><span class="sxs-lookup"><span data-stu-id="fbe62-145">Use the `Switch-SqlAvailabilityGroup` cmdlet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fbe62-146">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbe62-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="fbe62-147">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fbe62-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
     <span data-ttu-id="fbe62-148">En el ejemplo siguiente se realiza manualmente una conmutación por error del grupo de disponibilidad *MyAg* a la réplica secundaria con la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="fbe62-148">The following example manually fails over the *MyAg* availability group to the secondary replica with the specified path.</span></span>  
  
    ```powershell
    Switch-SqlAvailabilityGroup -Path SQLSERVER:\Sql\SecondaryServer\InstanceName\AvailabilityGroups\MyAg  
    ```  
  
 <span data-ttu-id="fbe62-149">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fbe62-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="fbe62-150">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="fbe62-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="fbe62-151">Obtener ayuda SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbe62-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="follow-up-after-manually-failing-over-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="fbe62-152">Seguimiento: después de la conmutación por error manual de un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="fbe62-152">Follow Up: After Manually Failing Over an Availability Group</span></span>  
 <span data-ttu-id="fbe62-153">Si la conmutación por error se produjo fuera del grupo de disponibilidad de [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] , ajuste los votos de quórum de los nodos de WSFC para reflejar la configuración del nuevo grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="fbe62-153">If you failed over outside of the [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] of the availability group, adjust the quorum votes of the WSFC nodes to reflect your new availability group configuration.</span></span> <span data-ttu-id="fbe62-154">Para obtener más información, consulte [clústeres de conmutación por error de Windows Server &#40;WSFC&#41; con SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fbe62-154">For more information, see [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe62-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbe62-155">See Also</span></span>  
 <span data-ttu-id="fbe62-156">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fbe62-156">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="fbe62-157">[Conmutación por error y modos de conmutación por error &#40;Grupos de disponibilidad AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="fbe62-157">[Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="fbe62-158">Realizar una conmutación por error manual forzada de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fbe62-158">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
