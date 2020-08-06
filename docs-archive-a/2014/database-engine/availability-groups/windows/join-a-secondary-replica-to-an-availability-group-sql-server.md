---
title: Combinar una réplica secundaria con un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joinreplica.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
ms.assetid: e5bd2489-097a-490e-8ea1-34fe48378ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c38c2d59a46b15fc9a1dca77ae6a67e8e59e1b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672262"
---
# <a name="join-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="c55a3-102">Combinar una réplica secundaria con un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c55a3-102">Join a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="c55a3-103">En este tema se describe cómo combinar una réplica secundaria con un grupo de disponibilidad de AlwaysOn mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c55a3-103">This topic describes how to join a secondary replica to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c55a3-104">Después de agregar una réplica secundaria a un grupo de disponibilidad de AlwaysOn, la réplica secundaria se debe combinar con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-104">After a secondary replica is added to an AlwaysOn availability group, the secondary replica must be joined to the availability group.</span></span> <span data-ttu-id="c55a3-105">La operación de combinar una réplica se debe realizar en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="c55a3-105">The join-replica operation must be performed on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting the secondary replica.</span></span>  
  
-   <span data-ttu-id="c55a3-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c55a3-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c55a3-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c55a3-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="c55a3-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c55a3-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c55a3-109">**Para preparar una base de datos secundaria, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="c55a3-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="c55a3-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c55a3-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c55a3-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c55a3-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="c55a3-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c55a3-112">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="c55a3-113">**Seguimiento:** [Configurar bases de datos secundarias](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c55a3-113">**Follow Up:** [Configure Secondary Databases](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c55a3-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c55a3-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c55a3-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c55a3-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="c55a3-116">La réplica principal del grupo de disponibilidad debe estar en línea.</span><span class="sxs-lookup"><span data-stu-id="c55a3-116">The primary replica of the availability group must currently be online.</span></span>  
  
-   <span data-ttu-id="c55a3-117">Debe estar conectado a la instancia del servidor que hospede una réplica secundaria que no se haya unido todavía al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-117">You must be connected to the server instance that hosts a secondary replica that has not yet have been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="c55a3-118">La instancia del servidor local debe poder conectarse al extremo de creación de reflejo de la base de datos de la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="c55a3-118">The local server instance must be able to connect to the database mirroring endpoint of the server instance that is hosting the primary replica.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c55a3-119">Si no se cumple ningún requisito previo, la operación de unión produce un error.</span><span class="sxs-lookup"><span data-stu-id="c55a3-119">If any prerequisite is not met, the join operation fails.</span></span> <span data-ttu-id="c55a3-120">Después de un intento de unión frustrado, puede ser necesario conectarse a la instancia de servidor que hospeda la réplica principal para quitar y volver a agregar la réplica secundaria antes de unirla al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-120">After a failed join attempt, you might need to connect to the server instance that hosts the primary replica to remove and re-add the secondary replica before you can join it to the availability group.</span></span> <span data-ttu-id="c55a3-121">Para obtener más información, vea [Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) y [Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c55a3-121">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c55a3-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c55a3-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c55a3-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="c55a3-123">Permissions</span></span>  
 <span data-ttu-id="c55a3-124">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="c55a3-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c55a3-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c55a3-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c55a3-126">**Para combinar una réplica de disponibilidad con un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="c55a3-126">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="c55a3-127">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica secundaria y haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="c55a3-127">In Object Explorer, connect to the server instance that hosts the secondary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c55a3-128">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="c55a3-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="c55a3-129">Seleccione el grupo de disponibilidad de la réplica secundaria a la que está conectado.</span><span class="sxs-lookup"><span data-stu-id="c55a3-129">Select the availability group of the secondary replica to which you are connected.</span></span>  
  
4.  <span data-ttu-id="c55a3-130">Haga clic con el botón derecho en la réplica secundaria y haga clic en **Combinar con grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="c55a3-130">Right-click the secondary replica, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="c55a3-131">Se abrirá el cuadro de diálogo **Combinar réplica con grupo de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="c55a3-131">This opens the **Join Replica to Availability Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="c55a3-132">Para combinar la réplica secundaria con el grupo de disponibilidad, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c55a3-132">To join the secondary replica to the availability group, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c55a3-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c55a3-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="c55a3-134">**Para combinar una réplica de disponibilidad con un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="c55a3-134">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="c55a3-135">Conéctese a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="c55a3-135">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="c55a3-136">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="c55a3-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="c55a3-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span><span class="sxs-lookup"><span data-stu-id="c55a3-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span></span>  
  
     <span data-ttu-id="c55a3-138">donde *group_name* es el nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-138">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="c55a3-139">En el ejemplo siguiente se une la réplica secundaria al grupo de disponibilidad `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="c55a3-139">The following example, joins the secondary replica to the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c55a3-140">Para ver esta instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] usada en contexto, vea [Crear un grupo de disponibilidad &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c55a3-140">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c55a3-141">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c55a3-141">Using PowerShell</span></span>  
 <span data-ttu-id="c55a3-142">**Para combinar una réplica de disponibilidad con un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="c55a3-142">**To join an availability replica to an availability group**</span></span>  
  
 <span data-ttu-id="c55a3-143">En el proveedor de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c55a3-143">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="c55a3-144">Cambie el directorio (`cd`) a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="c55a3-144">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="c55a3-145">Combine la réplica secundaria con el grupo de disponibilidad ejecutando el cmdlet **Join-SqlAvailabilityGroup** con el nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-145">Join the secondary replica to the availability group by executing the **Join-SqlAvailabilityGroup** cmdlet with the name of the availability group.</span></span>  
  
     <span data-ttu-id="c55a3-146">Por ejemplo, el comando siguiente une una réplica secundaria hospedada en la instancia de servidor que se encuentra en la ruta especificada al grupo de disponibilidad denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="c55a3-146">For example, the following command joins a secondary replica hosted by the server instance located at the specified path to the availability group named `MyAg`.</span></span>  <span data-ttu-id="c55a3-147">Esta instancia de servidor debe hospedar una replicación secundaria en este grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-147">This server instance must host a secondary replica in this availability group.</span></span>  
  
    ```powershell
    Join-SqlAvailabilityGroup -Path SQLSERVER:\SQL\SecondaryServer\InstanceName -Name 'MyAg'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c55a3-148">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c55a3-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="c55a3-149">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c55a3-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="c55a3-150">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c55a3-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="c55a3-151">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="c55a3-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-configure-secondary-databases"></a><a name="FollowUp"></a><span data-ttu-id="c55a3-152">Seguimiento: configurar bases de datos secundarias</span><span class="sxs-lookup"><span data-stu-id="c55a3-152">Follow Up: Configure Secondary Databases</span></span>  
 <span data-ttu-id="c55a3-153">Para cada base de datos del grupo de disponibilidad se necesita una base de datos secundaria en la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="c55a3-153">For every database in the availability group, you need a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="c55a3-154">Puede configurar las bases de datos secundarias antes o después de unir una réplica secundaria a un grupo de disponibilidad del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c55a3-154">You can configure secondary databases either before or after you join a secondary replica to an availability group, as follows:</span></span>  
  
1.  <span data-ttu-id="c55a3-155">Restaure la base de datos y las copias de seguridad de registros recientes de cada base de datos principal en la instancia del servidor que hospeda la réplica secundaria, utilizando RESTORE WITH NORECOVERY para cada operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="c55a3-155">Restore recent database and log backups of each primary database onto the server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="c55a3-156">Para obtener más información, vea [Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c55a3-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="c55a3-157">Una cada base de datos secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c55a3-157">Join each secondary database to the availability group.</span></span> <span data-ttu-id="c55a3-158">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c55a3-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55a3-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c55a3-159">See Also</span></span>  
 <span data-ttu-id="c55a3-160">[Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c55a3-160">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="c55a3-161">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c55a3-161">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="c55a3-162">Solucionar problemas de Grupos de disponibilidad AlwaysOn &#40;de configuración de SQL Server&#41;eliminado</span><span class="sxs-lookup"><span data-stu-id="c55a3-162">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
