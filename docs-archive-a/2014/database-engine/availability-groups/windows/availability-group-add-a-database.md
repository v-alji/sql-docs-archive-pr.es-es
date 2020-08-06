---
title: Agregar una base de datos a un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0907cf711cac65ad77a8948841d92705fdc1eac9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663145"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a><span data-ttu-id="1d96a-102">Agregar una base de datos a un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1d96a-102">Add a Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="1d96a-103">En este tema se describe cómo agregar una base de datos a un grupo de disponibilidad AlwaysOn utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d96a-103">This topic describes how to add a database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="1d96a-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1d96a-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1d96a-105">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="1d96a-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="1d96a-106">Permisos</span><span class="sxs-lookup"><span data-stu-id="1d96a-106">Permissions</span></span>](#Permissions)  
  
-   <span data-ttu-id="1d96a-107">**Para agregar una base de datos a un grupo de disponibilidad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="1d96a-107">**To add a database to an availability group, using:**</span></span>  
  
     [<span data-ttu-id="1d96a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d96a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1d96a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d96a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1d96a-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d96a-110">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1d96a-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1d96a-111">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="1d96a-112">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="1d96a-112">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="1d96a-113">Debe estar conectado a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="1d96a-113">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="1d96a-114">La base de datos debe residir en la instancia del servidor que hospeda la réplica principal y cumple los requisitos previos y las restricciones de las bases de datos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1d96a-114">The database must reside on the server instance that hosts the primary replica and comply with the prerequisites and restrictions for availability databases.</span></span> <span data-ttu-id="1d96a-115">Para más información, vea [Requisitos previos, restricciones y recomendaciones para grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-115">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1d96a-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1d96a-116">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1d96a-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="1d96a-117">Permissions</span></span>  
 <span data-ttu-id="1d96a-118">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="1d96a-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1d96a-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d96a-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1d96a-120">**Para agregar una base de datos a un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1d96a-120">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="1d96a-121">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="1d96a-121">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1d96a-122">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="1d96a-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="1d96a-123">Haga clic con el botón secundario en el grupo de disponibilidad y seleccione uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1d96a-123">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="1d96a-124">Para iniciar la función Agregar base de datos al Asistente para grupo de disponibilidad, seleccione el comando **Agregar base de datos** .</span><span class="sxs-lookup"><span data-stu-id="1d96a-124">To launch the Add Database to Availability Group Wizard, select the **Add Database** command.</span></span> <span data-ttu-id="1d96a-125">Para obtener más información, vea [Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-125">For more information, see [Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span></span>  
  
    -   <span data-ttu-id="1d96a-126">Para agregar una o varias bases de datos especificándolas en el cuadro de diálogo **Propiedades de grupo de disponibilidad** , seleccione el comando **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1d96a-126">To add one or more databases by specifying them in the **Availability Group Properties** dialog box, select the **Properties** command.</span></span> <span data-ttu-id="1d96a-127">Los pasos para agregar una base de datos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d96a-127">The steps for adding a database are as follows:</span></span>  
  
        1.  <span data-ttu-id="1d96a-128">En el panel **Bases de datos de disponibilidad** , haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="1d96a-128">In the **Availability Databases** pane, click the **Add** button.</span></span> <span data-ttu-id="1d96a-129">Esto crea y selecciona un campo de la base de datos en blanco.</span><span class="sxs-lookup"><span data-stu-id="1d96a-129">This creates and selects a blank database field.</span></span>  
  
        2.  <span data-ttu-id="1d96a-130">Escriba el nombre de una base de datos que cumpla los requisitos previos de las bases de datos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1d96a-130">Enter the name of a database that meets the availability-databases prerequisites.</span></span>  
  
         <span data-ttu-id="1d96a-131">Para agregar otra base de datos, repita los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1d96a-131">To add another database, repeat the preceding steps.</span></span> <span data-ttu-id="1d96a-132">Cuando haya terminado de especificar las bases de datos, haga clic en **Aceptar** para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="1d96a-132">When you are done specifying databases, click **OK** to complete the operation.</span></span>  
  
         <span data-ttu-id="1d96a-133">Después de utilizar el cuadro de diálogo **Propiedades de grupo de disponibilidad** para agregar una base de datos a un grupo de disponibilidad, debe configurar la base de datos secundaria correspondiente en cada instancia de servidor que hospeda una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="1d96a-133">After you use the **Availability Group Properties** dialog box to add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="1d96a-134">Para más información, vea [Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-134">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1d96a-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d96a-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="1d96a-136">**Para agregar una base de datos a un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1d96a-136">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="1d96a-137">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="1d96a-137">Connect to the server instance that hosts the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1d96a-138">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="1d96a-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="1d96a-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="1d96a-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span></span>  
  
     <span data-ttu-id="1d96a-140">donde *group_name* es el nombre del grupo de disponibilidad y *database_name* es el nombre de una base de datos que se va a agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="1d96a-140">where *group_name* is the name of the availability group and *database_name* is the name of a database to be added to the group.</span></span>  
  
     <span data-ttu-id="1d96a-141">En el ejemplo siguiente se agrega la base de datos *MyDb3* al grupo de disponibilidad *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="1d96a-141">The following example adds the *MyDb3* database to the *MyAG* availability group.</span></span>  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  <span data-ttu-id="1d96a-142">Después de agregar una base de datos a un grupo de disponibilidad, debe configurar la base de datos secundaria correspondiente en cada instancia de servidor que hospeda una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="1d96a-142">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="1d96a-143">Para más información, vea [Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-143">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1d96a-144">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d96a-144">Using PowerShell</span></span>  
 <span data-ttu-id="1d96a-145">**Para agregar una base de datos a un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1d96a-145">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="1d96a-146">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="1d96a-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1d96a-147">Utilice el cmdlet `Add-SqlAvailabilityDatabase`.</span><span class="sxs-lookup"><span data-stu-id="1d96a-147">Use the `Add-SqlAvailabilityDatabase` cmdlet.</span></span>  
  
     <span data-ttu-id="1d96a-148">Por ejemplo, en el comando siguiente se agrega la base de datos secundaria `MyDd` al grupo de disponibilidad `MyAG` , cuya réplica principal está hospedada en `PrimaryServer\InstanceName`.</span><span class="sxs-lookup"><span data-stu-id="1d96a-148">For example, the following command adds the secondary database `MyDd` to the `MyAG` availability group, whose primary replica is hosted by `PrimaryServer\InstanceName`.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase `   
     -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
     -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d96a-149">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d96a-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="1d96a-150">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
3.  <span data-ttu-id="1d96a-151">Después de agregar una base de datos a un grupo de disponibilidad, debe configurar la base de datos secundaria correspondiente en cada instancia de servidor que hospeda una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="1d96a-151">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="1d96a-152">Para más información, vea [Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-152">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="1d96a-153">Para configurar y usar el proveedor de SQL Server PowerShell, vea [proveedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1d96a-153">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>

 <span data-ttu-id="1d96a-154">En el ejemplo siguiente se muestra el proceso completo para preparar una base de datos secundaria de una base de datos en la instancia del servidor que hospeda la réplica principal de un grupo de disponibilidad, agregando la base de datos a un grupo de disponibilidad (como una base de datos principal) y uniendo después la base de datos secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1d96a-154">The following example shows the full process for preparing a secondary database from a database on the server instance that hosts the primary replica of an availability group, adding the database to an availability group (as a primary database), and then joining the secondary database to the availability group.</span></span> <span data-ttu-id="1d96a-155">Primero, en el ejemplo se realiza una copia de seguridad de la base de datos y del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1d96a-155">First, the example backs up the database and its transaction log.</span></span> <span data-ttu-id="1d96a-156">En el ejemplo se restauran las copias de seguridad de la base de datos y de registros a las instancias de servidor que hospeda una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="1d96a-156">Then the example restores the database and log backups to the server instances that host a secondary replica.</span></span>  
  
 <span data-ttu-id="1d96a-157">En el ejemplo se llama dos veces a `Add-SqlAvailabilityDatabase`: la primera en la réplica principal para agregar la base de datos al grupo de disponibilidad y después en la réplica secundaria para unir la base de datos secundaria de esa réplica al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1d96a-157">The example calls `Add-SqlAvailabilityDatabase` twice: first on the primary replica to add the database to the availability group, and then on the secondary replica to join the secondary database on that replica to the availability group.</span></span> <span data-ttu-id="1d96a-158">Si tiene más de una réplica secundaria, restaure y una la base de datos secundaria en cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="1d96a-158">If you have more than one secondary replica, restore and join the secondary database on each of them.</span></span>  
  
```powershell
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"
```  
  
## <a name="see-also"></a><span data-ttu-id="1d96a-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d96a-159">See Also</span></span>  
 <span data-ttu-id="1d96a-160">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1d96a-160">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1d96a-161">[Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1d96a-161">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1d96a-162">[Usar el panel de AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1d96a-162">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="1d96a-163">Supervisar grupos de disponibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1d96a-163">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
