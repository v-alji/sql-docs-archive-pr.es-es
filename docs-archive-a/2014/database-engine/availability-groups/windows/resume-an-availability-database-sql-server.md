---
title: Reanudar una base de datos de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.resumedatamove.f1
helpviewer_keywords:
- Availability Groups [SQL Server], resuming a database
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], databases
ms.assetid: 20e9147b-e985-4caa-910e-fc4b38dbf9a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a2279940c2502a310e9dac4448bd6029b6e13dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749490"
---
# <a name="resume-an-availability-database-sql-server"></a><span data-ttu-id="dab74-102">Reanudar una base de datos de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dab74-102">Resume an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="dab74-103">Puede reanudar una base de datos de disponibilidad suspendida en [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dab74-103">You can resume a suspended availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dab74-104">La reanudación de una base de datos suspendida coloca la base de datos en el estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="dab74-104">Resuming a suspended database puts the database into the SYNCHRONIZING state.</span></span> <span data-ttu-id="dab74-105">La reanudación de la base de datos principal también reanuda cualquiera de las bases de datos secundarias suspendidas como resultado de suspender la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="dab74-105">Resuming the primary database also resumes any of its secondary databases that were suspended as the result of suspending the primary database.</span></span> <span data-ttu-id="dab74-106">Si una base de datos secundaria se suspende localmente en la instancia de servidor que hospeda la réplica secundaria, esa base de datos secundaria se debe reanudar localmente.</span><span class="sxs-lookup"><span data-stu-id="dab74-106">If any secondary database was suspended locally, from the server instance that hosts the secondary replica, that secondary database must be resumed locally.</span></span> <span data-ttu-id="dab74-107">Una vez que una base de datos secundaria y la base de datos principal correspondiente están en el estado SYNCHRONIZING, se reanuda la sincronización de datos en la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="dab74-107">Once a given secondary database and the corresponding primary database are in the SYNCHRONIZING state, data synchronization resumes on the secondary database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dab74-108">Suspender y reanudar una base de datos secundaria de AlwaysOn no afecta directamente a la disponibilidad de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="dab74-108">Suspending and resuming an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="dab74-109">Sin embargo, suspender una base de datos secundaria puede afectar a las capacidades de conmutación por error y redundancia de la base de datos principal, hasta que la base de datos secundaria suspendida se reanuda.</span><span class="sxs-lookup"><span data-stu-id="dab74-109">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database, until the suspended secondary database is resumed.</span></span> <span data-ttu-id="dab74-110">Esto se diferencia del reflejo de base de datos, en el que el estado de reflejo se suspende tanto en la base de datos reflejada como en la base de datos principal hasta que el reflejo se reanuda.</span><span class="sxs-lookup"><span data-stu-id="dab74-110">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database until mirroring is resumed.</span></span> <span data-ttu-id="dab74-111">Al suspender una base de datos principal AlwaysOn, se suspende el movimiento de datos en todas las bases de datos secundarias y las capacidades de conmutación por error y redundancia cesan para esa base de datos hasta que la base de datos principal se reanuda.</span><span class="sxs-lookup"><span data-stu-id="dab74-111">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="dab74-112">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="dab74-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dab74-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="dab74-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dab74-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dab74-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="dab74-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="dab74-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dab74-116">**Para reanudar una base de datos secundaria, mediante:**</span><span class="sxs-lookup"><span data-stu-id="dab74-116">**To resume a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="dab74-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dab74-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dab74-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dab74-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="dab74-119">PowerShell</span><span class="sxs-lookup"><span data-stu-id="dab74-119">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="dab74-120">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="dab74-120">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dab74-121">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="dab74-121">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dab74-122">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="dab74-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="dab74-123">Un comando RESUME realiza la devolución en cuanto haya sido aceptado por la réplica que hospeda la base de datos de destino, pero la reanudación real de la base de datos se produce de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="dab74-123">A RESUME command returns as soon as it has been accepted by the replica that hosts the target database, but actually resuming the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="dab74-124">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dab74-124">Prerequisites</span></span>  
  
-   <span data-ttu-id="dab74-125">Debe estar conectado a la instancia de servidor que hospeda la base de datos que se va a reanudar.</span><span class="sxs-lookup"><span data-stu-id="dab74-125">You must be connected to the server instance that hosts the database to be resumed.</span></span>  
  
-   <span data-ttu-id="dab74-126">El grupo de disponibilidad debe estar en línea.</span><span class="sxs-lookup"><span data-stu-id="dab74-126">The availability group must be online.</span></span>  
  
-   <span data-ttu-id="dab74-127">La base de datos principal debe estar en línea y disponible.</span><span class="sxs-lookup"><span data-stu-id="dab74-127">The primary database must be online and available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dab74-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="dab74-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dab74-129">Permisos</span><span class="sxs-lookup"><span data-stu-id="dab74-129">Permissions</span></span>  
 <span data-ttu-id="dab74-130">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dab74-130">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="dab74-131">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="dab74-131">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dab74-132">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dab74-132">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="dab74-133">**Para reanudar una base de datos secundaria**</span><span class="sxs-lookup"><span data-stu-id="dab74-133">**To resume a secondary database**</span></span>  
  
1.  <span data-ttu-id="dab74-134">En el Explorador de objetos, conéctese a la instancia de servidor que hospeda la réplica de disponibilidad en la que desea reanudar una base de datos y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="dab74-134">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to resume a database, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="dab74-135">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="dab74-135">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="dab74-136">Expanda el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dab74-136">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="dab74-137">Expanda el nodo **Bases de datos de disponibilidad** , haga clic con el botón derecho en la base de datos y haga clic en **Reanudar movimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="dab74-137">Expand the **Availability Databases** node, right-click the database, and click **Resume Data Movement**.</span></span>  
  
5.  <span data-ttu-id="dab74-138">En el cuadro de diálogo **Reanudar movimiento de datos** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dab74-138">In the **Resume Data Movement** dialog box, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dab74-139">Para reanudar bases de datos adicionales en esta ubicación de réplica, repita los pasos 4 y 5 para cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="dab74-139">To resume additional databases on this replica location, repeat steps 4 and 5 for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dab74-140">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dab74-140">Using Transact-SQL</span></span>  
 <span data-ttu-id="dab74-141">**Para reanudar una base de datos secundaria suspendida localmente**</span><span class="sxs-lookup"><span data-stu-id="dab74-141">**To resume a secondary database that was suspended locally**</span></span>  
  
1.  <span data-ttu-id="dab74-142">Conéctese a la instancia de servidor que hospeda la réplica secundaria cuya base de datos desea reanudar.</span><span class="sxs-lookup"><span data-stu-id="dab74-142">Connect to the server instance that hosts the secondary replica whose database you want to resume.</span></span>  
  
2.  <span data-ttu-id="dab74-143">Reanude la base de datos secundaria utilizando la siguiente instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr):</span><span class="sxs-lookup"><span data-stu-id="dab74-143">Resume the secondary database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="dab74-144">ALTER DATABASE *database_name* Set HADR resume</span><span class="sxs-lookup"><span data-stu-id="dab74-144">ALTER DATABASE *database_name* SET HADR RESUME</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="dab74-145">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dab74-145">Using PowerShell</span></span>  

### <a name="to-resume-a-secondary-database"></a><span data-ttu-id="dab74-146">Para reanudar una base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="dab74-146">To resume a secondary database</span></span>
  
1.  <span data-ttu-id="dab74-147">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica cuya base de datos desea reanudar.</span><span class="sxs-lookup"><span data-stu-id="dab74-147">Change directory (`cd`) to the server instance that hosts the replica whose database you want to resume.</span></span> <span data-ttu-id="dab74-148">Para obtener más información, vea [Requisitos previos](#Prerequisites), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="dab74-148">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="dab74-149">Use el cmdlet **Resume-SqlAvailabilityDatabase** para reanudar el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dab74-149">Use the **Resume-SqlAvailabilityDatabase** cmdlet to resume the availability group.</span></span>  
  
     <span data-ttu-id="dab74-150">Por ejemplo, el comando siguiente reanuda la sincronización de datos para la base de datos de disponibilidad `MyDb3` en el grupo de disponibilidad `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="dab74-150">For example, the following command resumes data synchronization for the availability database `MyDb3` in the availability group `MyAg`.</span></span>  
  
    ```powershell
    Resume-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="dab74-151">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dab74-151">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="dab74-152">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="dab74-152">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="dab74-153">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dab74-153">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="dab74-154">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="dab74-154">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dab74-155">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="dab74-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="dab74-156">Suspender una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dab74-156">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="dab74-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dab74-157">See Also</span></span>  
 [<span data-ttu-id="dab74-158">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dab74-158">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
