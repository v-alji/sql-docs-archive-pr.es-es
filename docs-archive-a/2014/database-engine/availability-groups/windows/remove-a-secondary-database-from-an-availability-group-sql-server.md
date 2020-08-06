---
title: Quitar una base de datos secundaria de un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c3de0afd73b46ae5594d26d1763f5bd78483efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670598"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="1f0e9-102">Quitar una base de datos secundaria de un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1f0e9-102">Remove a Secondary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="1f0e9-103">En este tema se describe cómo quitar una base de datos secundaria de un grupo de disponibilidad AlwaysOn utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0e9-103">This topic describes how to remove a secondary database from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="1f0e9-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1f0e9-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1f0e9-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1f0e9-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="1f0e9-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1f0e9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1f0e9-107">**Para quitar una base de datos secundaria, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="1f0e9-107">**To remove a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="1f0e9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f0e9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1f0e9-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1f0e9-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1f0e9-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f0e9-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="1f0e9-111">**Seguimiento:**  [después de quitar una base de datos secundaria de un grupo de disponibilidad](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1f0e9-111">**Follow Up:**  [After Removing a Secondary Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1f0e9-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1f0e9-112">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>   
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="1f0e9-113">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="1f0e9-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="1f0e9-114">Esta tarea solo se admite en las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-114">This task is supported only on secondary replicas.</span></span> <span data-ttu-id="1f0e9-115">Debe estar conectado a la instancia del servidor que hospeda la réplica secundaria de la que se va a quitar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-115">You must be connected to the server instance that hosts the secondary replica from which the database is to be removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1f0e9-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1f0e9-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1f0e9-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="1f0e9-117">Permissions</span></span>  
 <span data-ttu-id="1f0e9-118">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1f0e9-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f0e9-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1f0e9-120">**Para quitar una base de datos secundaria de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1f0e9-120">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="1f0e9-121">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica secundaria de la que desea quitar una o varias bases de datos secundarias y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-121">In Object Explorer, connect to the server instance that hosts the secondary replica from which you want to remove one or more secondary databases, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1f0e9-122">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="1f0e9-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="1f0e9-123">Seleccione el grupo de disponibilidad y expanda el nodo **Bases de datos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="1f0e9-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="1f0e9-124">Este paso depende de si desea quitar varios grupos de bases de datos o solo una base de datos, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="1f0e9-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="1f0e9-125">Para quitar varias bases de datos, use el panel **Detalles del Explorador de objetos** para ver y seleccionar todas las bases de datos que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="1f0e9-126">Para obtener más información, vea [Usar los detalles del Explorador de objetos para supervisar los grupos de disponibilidad &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e9-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="1f0e9-127">Para quitar una sola base de datos, selecciónela en el panel **Explorador de objetos** o el panel **Detalles del Explorador de objetos** .</span><span class="sxs-lookup"><span data-stu-id="1f0e9-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="1f0e9-128">Haga clic con el botón derecho en la base de datos o las bases de datos seleccionadas y seleccione **Quitar base de datos secundaria** en el menú de comandos.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-128">Right-click the selected database or databases, and select **Remove Secondary Database** in the command menu.</span></span>  
  
6.  <span data-ttu-id="1f0e9-129">En el cuadro de diálogo **Quitar base de datos del grupo de disponibilidad** , para quitar todas las bases de datos enumeradas, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-129">In the **Remove Database from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="1f0e9-130">Si no desea quitar todas las bases de datos enumeradas, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-130">If you do not want to remove all the listed databases, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1f0e9-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1f0e9-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="1f0e9-132">**Para quitar una base de datos secundaria de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1f0e9-132">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="1f0e9-133">Conéctese a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-133">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="1f0e9-134">Utilice la cláusula [SET HADR de la instrucción ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="1f0e9-134">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="1f0e9-135">ALTER DATABASE *database_name* SET HADR OFF</span><span class="sxs-lookup"><span data-stu-id="1f0e9-135">ALTER DATABASE *database_name* SET HADR OFF</span></span>  
  
     <span data-ttu-id="1f0e9-136">donde *database_name* es el nombre de una base de datos secundaria que se va a quitar del grupo de disponibilidad al que pertenece.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-136">where *database_name* is the name of a secondary database to be removed from the availability group to which it belongs.</span></span>  
  
     <span data-ttu-id="1f0e9-137">En el ejemplo siguiente se quita la base de datos secundaria local *MyDb2* de su grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-137">The following example removes the local secondary database *MyDb2* from its availability group.</span></span>  
  
    ```sql
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1f0e9-138">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f0e9-138">Using PowerShell</span></span>  
 <span data-ttu-id="1f0e9-139">**Para quitar una base de datos secundaria de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1f0e9-139">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="1f0e9-140">Cambie el directorio (`cd`) a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-140">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="1f0e9-141">Use el cmdlet **Remove-SqlAvailabilityDatabase** , y especifique el nombre de la base de datos de disponibilidad que se va a quitar del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-141">Use the **Remove-SqlAvailabilityDatabase** cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="1f0e9-142">Cuando esté conectado a una instancia de servidor que hospeda una réplica secundaria, solo la base de datos secundaria local se quita del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-142">When you are connected to a server instance that hosts a secondary replica, only the local secondary database is removed from the availability group.</span></span>  
  
     <span data-ttu-id="1f0e9-143">Por ejemplo, el comando siguiente quita la base de datos secundaria `MyDb8` de la réplica secundaria hospedada por la instancia de servidor denominada `SecondaryComputer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-143">For example, the following command removes the secondary database `MyDb8` from the secondary replica hosted by the server instance named `SecondaryComputer\Instance`.</span></span> <span data-ttu-id="1f0e9-144">La sincronización de datos cesa en las bases de datos secundarias quitadas.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-144">Data synchronization to the removed secondary databases ceases.</span></span> <span data-ttu-id="1f0e9-145">Este comando no afecta a la base de datos principal ni a ninguna otra base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-145">This command does not affect the primary database or any other secondary databases.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="1f0e9-146">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="1f0e9-147">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e9-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="1f0e9-148">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1f0e9-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="1f0e9-149">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="1f0e9-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-database-from-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="1f0e9-150">Seguimiento: después de quitar una base de datos secundaria de un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="1f0e9-150">Follow Up: After Removing a Secondary Database from an Availability Group</span></span>  
 <span data-ttu-id="1f0e9-151">Cuando se quita una base de datos secundaria, deja de estar unida al grupo de disponibilidad y este descartará toda la información acerca de la base de datos secundaria quitada.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-151">When a secondary database is removed, it is no longer joined to the availability group and all information about the removed secondary database is discarded by the availability group.</span></span> <span data-ttu-id="1f0e9-152">La base de datos secundaria quitada se pone en estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-152">The removed secondary database is placed in the RESTORING state.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="1f0e9-153">Durante un breve período de tiempo después de quitar una base de datos secundaria, es posible que pueda reiniciar la sincronización de datos de AlwaysOn en la base de datos volviéndola a unir al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-153">For a short time after removing a secondary database, you might be able to restart AlwaysOn data synchronization on the database by re-joining it to the availability group.</span></span> <span data-ttu-id="1f0e9-154">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e9-154">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="1f0e9-155">En este momento hay formas alternativas de tratar una base de datos secundaria quitada:</span><span class="sxs-lookup"><span data-stu-id="1f0e9-155">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="1f0e9-156">Si ya no necesita la base de datos secundaria, puede quitarla.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-156">If you no longer need the secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="1f0e9-157">Para obtener más información, vea [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) o [Eliminar una base de datos](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e9-157">For more information, see [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) or [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="1f0e9-158">Si desea obtener acceso a una base de datos secundaria quitada después de haberse quitado del grupo de disponibilidad, puede recuperar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-158">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="1f0e9-159">Sin embargo, si recupera una base de datos secundaria quitada, dos bases de datos independientes divergentes que tienen el mismo nombre estarán en línea.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-159">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="1f0e9-160">Debe asegurarse de que los clientes puedan tener acceso solo a la base de datos principal actual.</span><span class="sxs-lookup"><span data-stu-id="1f0e9-160">You must make sure that clients can access only the current primary database.</span></span>  
  
     <span data-ttu-id="1f0e9-161">Para obtener más información, vea [Recuperar una base de datos sin restaurar los datos &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e9-161">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0e9-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f0e9-162">See Also</span></span>  
 <span data-ttu-id="1f0e9-163">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1f0e9-163">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="1f0e9-164">Quitar una base de datos principal de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1f0e9-164">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
