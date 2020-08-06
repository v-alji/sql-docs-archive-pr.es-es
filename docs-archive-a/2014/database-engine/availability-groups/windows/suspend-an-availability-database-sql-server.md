---
title: Suspender una base de datos de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.suspenddatamove.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], suspending a database
- Availability Groups [SQL Server], databases
ms.assetid: 86858982-6af1-4e80-9a93-87451f0d7ee9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49afe868a509f84160fc1ad154135e8e67f6900a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750186"
---
# <a name="suspend-an-availability-database-sql-server"></a><span data-ttu-id="a87dc-102">Suspender una base de datos de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a87dc-102">Suspend an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="a87dc-103">Puede suspender una base de datos de disponibilidad en [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a87dc-103">You can suspend an availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a87dc-104">Observe que un comando de suspender tiene que emitirse en la instancia de servidor que hospeda la base de datos que se va a suspender o a reanudar.</span><span class="sxs-lookup"><span data-stu-id="a87dc-104">Note that a suspend command needs to be issued on the server instance that hosts the database to be suspended or resumed.</span></span>  
  
 <span data-ttu-id="a87dc-105">El efecto de un comando de suspensión depende de si suspende una base de datos secundaria o una base de datos principal, según se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a87dc-105">The effect of a suspend command depends on whether you suspend a secondary database or a primary database, as follows:</span></span>  
  
|<span data-ttu-id="a87dc-106">Base de datos suspendida</span><span class="sxs-lookup"><span data-stu-id="a87dc-106">Suspended Database</span></span>|<span data-ttu-id="a87dc-107">Efecto del comando de suspensión</span><span class="sxs-lookup"><span data-stu-id="a87dc-107">Effect of Suspend Command</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="a87dc-108">Base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="a87dc-108">Secondary database</span></span>|<span data-ttu-id="a87dc-109">Solo la base de datos secundaria local se suspende y su estado de sincronización se pasa a NOT SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="a87dc-109">Only the local secondary database is suspended and its synchronization state becomes NOT SYNCHRONIZING.</span></span> <span data-ttu-id="a87dc-110">Otras bases de datos secundarias no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="a87dc-110">Other secondary databases are not affected.</span></span> <span data-ttu-id="a87dc-111">La base de datos suspendida deja de recibir y aplicar datos (registros) y comienza a quedar rezagada respecto de la principal base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-111">The suspended database stops receiving and applying data (log records) and begins to fall behind the primary database.</span></span> <span data-ttu-id="a87dc-112">Las conexiones existentes en la secundaria legible siguen estando utilizables.</span><span class="sxs-lookup"><span data-stu-id="a87dc-112">Existing connections on the readable secondary remain usable.</span></span> <span data-ttu-id="a87dc-113">Las nuevas conexiones a la base de datos suspendida en la secundaria legible no se permiten hasta que se reanude el movimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="a87dc-113">New connections to the suspended database on the readable secondary are not allowed until data movement is resumed.</span></span><br /><br /> <span data-ttu-id="a87dc-114">La base de datos principal sigue estando disponible.</span><span class="sxs-lookup"><span data-stu-id="a87dc-114">The primary database remains available.</span></span> <span data-ttu-id="a87dc-115">Si suspende cada una de las bases de datos secundarias correspondientes, la base de datos principal se queda expuesta.</span><span class="sxs-lookup"><span data-stu-id="a87dc-115">If you suspend each of the corresponding secondary databases, the primary database runs exposed.</span></span><br /><br /> <span data-ttu-id="a87dc-116">**\*\* Importante \*\*** Mientras se suspende una base de datos secundaria, la cola de envío de la base de datos principal correspondiente acumulará registros de transacciones sin enviar.</span><span class="sxs-lookup"><span data-stu-id="a87dc-116">**\*\* Important \*\*** While a secondary database is suspended, the send queue of the corresponding primary database will accumulate unsent transaction log records.</span></span> <span data-ttu-id="a87dc-117">Las conexiones a la réplica secundaria devuelven los datos que estaban disponibles en el momento en que suspendió el movimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="a87dc-117">Connections to the secondary replica return data that was available at the time the data movement was suspended.</span></span>|  
|<span data-ttu-id="a87dc-118">Base de datos principal</span><span class="sxs-lookup"><span data-stu-id="a87dc-118">Primary database</span></span>|<span data-ttu-id="a87dc-119">La base de datos principal detiene el movimiento de datos a cada base de datos secundaria conectada.</span><span class="sxs-lookup"><span data-stu-id="a87dc-119">The primary database stops data movement to every connected secondary database.</span></span> <span data-ttu-id="a87dc-120">La base de datos principal continúa ejecutándose en un modo expuesto.</span><span class="sxs-lookup"><span data-stu-id="a87dc-120">The primary database continues running, in an exposed mode.</span></span> <span data-ttu-id="a87dc-121">La base de datos principal sigue disponible para los clientes y las conexiones existentes en una base de datos secundaria legible permanecen utilizables y se pueden establecer nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="a87dc-121">The primary database remains available to clients, and existing connections on a readable secondary remain usable and new connections can be made.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="a87dc-122">Suspender una base de datos secundaria de AlwaysOn no afecta directamente a la disponibilidad de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-122">Suspending an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="a87dc-123">Sin embargo, suspender una base de datos secundaria puede afectar a las capacidades de la redundancia y de conmutación por error para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-123">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database.</span></span> <span data-ttu-id="a87dc-124">Esto se diferencia del reflejo de base de datos, en el que el estado de reflejo se suspende tanto en la base de datos reflejada como en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-124">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database.</span></span> <span data-ttu-id="a87dc-125">Al suspender una base de datos principal AlwaysOn, se suspende el movimiento de datos en todas las bases de datos secundarias y las capacidades de conmutación por error y redundancia cesan para esa base de datos hasta que la base de datos principal se reanuda.</span><span class="sxs-lookup"><span data-stu-id="a87dc-125">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="a87dc-126">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a87dc-126">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a87dc-127">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a87dc-127">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a87dc-128">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a87dc-128">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a87dc-129">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="a87dc-129">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a87dc-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a87dc-130">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a87dc-131">**Para suspender una base de datos con:**</span><span class="sxs-lookup"><span data-stu-id="a87dc-131">**To suspend a database, using:**</span></span>  
  
-   [<span data-ttu-id="a87dc-132">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a87dc-132">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a87dc-133">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a87dc-133">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a87dc-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a87dc-134">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="a87dc-135">**Seguimiento:** [Evitar un registro de transacciones lleno](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a87dc-135">**Follow up:** [Avoiding a Full Transaction Log](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="a87dc-136">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a87dc-136">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a87dc-137">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a87dc-137">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a87dc-138">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a87dc-138">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a87dc-139">Un comando SUSPEND realiza la devolución en cuanto haya sido aceptado por la réplica que hospeda la base de datos de destino, pero la suspensión real de la base de datos se produce de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a87dc-139">A SUSPEND command returns as soon as it has been accepted by the replica that hosts the target database, but actually suspending the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a87dc-140">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a87dc-140">Prerequisites</span></span>  
 <span data-ttu-id="a87dc-141">Debe estar conectado a la instancia de servidor que hospeda la base de datos que desea suspender.</span><span class="sxs-lookup"><span data-stu-id="a87dc-141">You must be connected to the server instance that hosts the database that you want to suspend.</span></span> <span data-ttu-id="a87dc-142">Para suspender una base de datos principal y las bases de datos secundarias correspondientes, conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-142">To suspend a primary database and the corresponding secondary databases, connect to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="a87dc-143">Para suspender una base de datos secundaria dejando disponible la base de datos principal, conéctese a la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="a87dc-143">To suspend a secondary database while leaving the primary database available, connect to the secondary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a87dc-144">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="a87dc-144">Recommendations</span></span>  
 <span data-ttu-id="a87dc-145">Durante los cuellos de botella, la suspensión breve de una o varias bases de datos secundarias puede ser útil para mejorar temporalmente el rendimiento de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-145">During bottlenecks, suspending one or more secondary databases briefly might be useful to improve performance temporarily on the primary replica.</span></span> <span data-ttu-id="a87dc-146">Mientras una base de datos secundaria permanece suspendida, el registro de transacciones de la base de datos principal correspondiente no puede truncarse.</span><span class="sxs-lookup"><span data-stu-id="a87dc-146">As long as a secondary database remains suspended, the transaction log of the corresponding primary database cannot be truncated.</span></span> <span data-ttu-id="a87dc-147">Esto hace que las entradas de registro se acumulen en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-147">This causes log records to accumulate on the primary database.</span></span> <span data-ttu-id="a87dc-148">Por tanto, se recomienda reanudar o quitar rápidamente una base de datos secundaria suspendida.</span><span class="sxs-lookup"><span data-stu-id="a87dc-148">Therefore, we recommend that you resume, or remove, a suspended secondary database quickly.</span></span> <span data-ttu-id="a87dc-149">Para más información, vea [Seguimiento: Evitar un registro de transacciones lleno](#FollowUp) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a87dc-149">For more information, see [Follow up: Avoiding a Full Transaction Log](#FollowUp), later in this topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a87dc-150">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a87dc-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a87dc-151">Permisos</span><span class="sxs-lookup"><span data-stu-id="a87dc-151">Permissions</span></span>  
 <span data-ttu-id="a87dc-152">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a87dc-152">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="a87dc-153">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a87dc-153">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a87dc-154">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a87dc-154">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a87dc-155">**Para suspender una base de datos**</span><span class="sxs-lookup"><span data-stu-id="a87dc-155">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="a87dc-156">En el Explorador de objetos, conéctese a la instancia de servidor que hospeda la réplica de disponibilidad en la que desea suspender una base de datos y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="a87dc-156">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to suspend a database, and expand the server tree.</span></span> <span data-ttu-id="a87dc-157">Para obtener más información, vea [Requisitos previos](#Prerequisites), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a87dc-157">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a87dc-158">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="a87dc-158">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a87dc-159">Expanda el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a87dc-159">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="a87dc-160">Expanda el nodo **Bases de datos de disponibilidad** , haga clic con el botón derecho en la base de datos y haga clic en **Suspender movimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="a87dc-160">Expand the **Availability Databases** node, right-click the database, and click **Suspend Data Movement**.</span></span>  
  
5.  <span data-ttu-id="a87dc-161">En el cuadro de diálogo **Suspender movimiento de datos** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a87dc-161">In the **Suspend Data Movement** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="a87dc-162">El Explorador de objetos indica que la base de datos está suspendida mediante el cambio del icono de la base de datos para mostrar un indicador de detención.</span><span class="sxs-lookup"><span data-stu-id="a87dc-162">Object Explorer indicates that the database is suspended by changing  the database icon to display a pause indicator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a87dc-163">Para suspender bases de datos adicionales en esta ubicación de réplica, repita los pasos 4 y 5 para cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="a87dc-163">To suspend additional databases on this replica location, repeat steps 4 and 5  for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a87dc-164">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a87dc-164">Using Transact-SQL</span></span>  
 <span data-ttu-id="a87dc-165">**Para suspender una base de datos**</span><span class="sxs-lookup"><span data-stu-id="a87dc-165">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="a87dc-166">Conéctese a la instancia del servidor que hospeda la réplica cuya base de datos desea suspender.</span><span class="sxs-lookup"><span data-stu-id="a87dc-166">Connect to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="a87dc-167">Para obtener más información, vea [Requisitos previos](#Prerequisites), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a87dc-167">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a87dc-168">Suspenda la base de datos mediante la siguiente instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr):</span><span class="sxs-lookup"><span data-stu-id="a87dc-168">Suspend the database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="a87dc-169">ALTER DATABASE *database_name* Set HADR Suspend</span><span class="sxs-lookup"><span data-stu-id="a87dc-169">ALTER DATABASE *database_name* SET HADR SUSPEND</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a87dc-170">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="a87dc-170">Using PowerShell</span></span>  
 <span data-ttu-id="a87dc-171">**Para suspender una base de datos**</span><span class="sxs-lookup"><span data-stu-id="a87dc-171">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="a87dc-172">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica cuya base de datos desea suspender.</span><span class="sxs-lookup"><span data-stu-id="a87dc-172">Change directory (`cd`) to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="a87dc-173">Para obtener más información, vea [Requisitos previos](#Prerequisites), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a87dc-173">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a87dc-174">Utilice el cmdlet `Suspend-SqlAvailabilityDatabase` para suspender el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a87dc-174">Use the `Suspend-SqlAvailabilityDatabase` cmdlet to suspend the availability group.</span></span>  
  
     <span data-ttu-id="a87dc-175">Por ejemplo, el siguiente comando suspende la sincronización de datos para la base de datos de disponibilidad `MyDb3` en el grupo de disponibilidad `MyAg` en la instancia del servidor denominada `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="a87dc-175">For example, the following command suspends data synchronization for the availability database `MyDb3` in the availability group `MyAg` on the server instance named `Computer\Instance`.</span></span>  
  
    ```powershell
    Suspend-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a87dc-176">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a87dc-176">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a87dc-177">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a87dc-177">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a87dc-178">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a87dc-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a87dc-179">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="a87dc-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-avoiding-a-full-transaction-log"></a><a name="FollowUp"></a> <span data-ttu-id="a87dc-180">Seguimiento: Evitar un registro de transacciones lleno</span><span class="sxs-lookup"><span data-stu-id="a87dc-180">Follow Up: Avoiding a Full Transaction Log</span></span>  
 <span data-ttu-id="a87dc-181">Normalmente, cuando se lleva a cabo un punto de comprobación automático en una base de datos, su registro de transacciones se trunca en dicho punto de comprobación después de la siguiente copia de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="a87dc-181">Normally, when an automatic checkpoint is performed on a database, its transaction log is truncated to that checkpoint after the next log backup.</span></span> <span data-ttu-id="a87dc-182">Sin embargo, mientras una base de datos secundaria está suspendida, todas las entradas de registro actuales permanecen activas en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-182">However, while a secondary database is suspended, all of the current log records remain active on the primary database.</span></span> <span data-ttu-id="a87dc-183">Si el registro de transacciones se llena (bien porque alcanza su tamaño máximo o porque la instancia del servidor se queda sin espacio), la base de datos no puede realizar más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a87dc-183">If the transaction log fills up (either because it reaches its maximum size or the server instance runs out of space), the database cannot perform any more updates.</span></span>  
  
 <span data-ttu-id="a87dc-184">Para evitar este problema, debe realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a87dc-184">To avoid this problem, you should do one of the following:</span></span>  
  
-   <span data-ttu-id="a87dc-185">Agregar más espacio del registro para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a87dc-185">Add more log space for the primary database.</span></span>  
  
-   <span data-ttu-id="a87dc-186">Reanudar la base de datos secundaria antes de que el registro se llene.</span><span class="sxs-lookup"><span data-stu-id="a87dc-186">Resume the secondary database before the log fills up.</span></span> <span data-ttu-id="a87dc-187">Para obtener más información, vea [Reanudar una base de datos de disponibilidad &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a87dc-187">For more information, see [Resume an Availability Database &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span></span>  
  
-   <span data-ttu-id="a87dc-188">Quitar la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="a87dc-188">Remove the secondary database.</span></span> <span data-ttu-id="a87dc-189">Para obtener más información, vea [Quitar una base de datos secundaria de un grupo de disponibilidad &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a87dc-189">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="a87dc-190">**Para solucionar problemas en un registro de transacciones lleno**</span><span class="sxs-lookup"><span data-stu-id="a87dc-190">**To troubleshoot a full transaction log**</span></span>  
  
-   [<span data-ttu-id="a87dc-191">Solucionar problemas de un registro de transacciones lleno &#40;Error 9002 de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a87dc-191">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../../../relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a87dc-192">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a87dc-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a87dc-193">Reanudar una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a87dc-193">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a87dc-194">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a87dc-194">See Also</span></span>  
 <span data-ttu-id="a87dc-195">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a87dc-195">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a87dc-196">Reanudar una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a87dc-196">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
