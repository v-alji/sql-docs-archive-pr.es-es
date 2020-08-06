---
title: Quitar una base de datos principal de un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeprimarydb.f1
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 6d4ca31e-ddf0-44bf-be5e-a5da060bf096
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6fafaf6464431d68f8cfdf9dc9d8fa844a42a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670600"
---
# <a name="remove-a-primary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="43b4b-102">Quitar una base de datos principal de un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43b4b-102">Remove a Primary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="43b4b-103">En este tema se describe cómo quitar la base de datos principal y las bases de datos secundarias correspondientes del grupo de disponibilidad AlwaysOn mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43b4b-103">This topic describes how to remove both the primary database and the corresponding secondary database(s) from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="43b4b-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="43b4b-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43b4b-105">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="43b4b-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="43b4b-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="43b4b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43b4b-107">**Para quitar una base de datos de disponibilidad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="43b4b-107">**To remove an availability database, using:**</span></span>  
  
     [<span data-ttu-id="43b4b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43b4b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43b4b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43b4b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="43b4b-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="43b4b-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="43b4b-111">**Seguimiento:**  [después de quitar una base de datos de disponibilidad de un grupo de disponibilidad](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="43b4b-111">**Follow Up:**  [After Removing an Availability Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43b4b-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="43b4b-112">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="43b4b-113">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="43b4b-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="43b4b-114">Esta tarea solo se admite en las réplicas principales.</span><span class="sxs-lookup"><span data-stu-id="43b4b-114">This task is supported only on primary replicas.</span></span> <span data-ttu-id="43b4b-115">Debe estar conectado a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="43b4b-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43b4b-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="43b4b-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43b4b-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="43b4b-117">Permissions</span></span>  
 <span data-ttu-id="43b4b-118">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="43b4b-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43b4b-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43b4b-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="43b4b-120">**Para quitar una base de datos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="43b4b-120">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="43b4b-121">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal de la base de datos o bases de datos que se van a quitar y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="43b4b-121">In Object Explorer, connect to the server instance that hosts the primary replica of the database or databases to be removed, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="43b4b-122">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="43b4b-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="43b4b-123">Seleccione el grupo de disponibilidad y expanda el nodo **Bases de datos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="43b4b-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="43b4b-124">Este paso depende de si desea quitar varios grupos de bases de datos o solo una base de datos, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="43b4b-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="43b4b-125">Para quitar varias bases de datos, use el panel **Detalles del Explorador de objetos** para ver y seleccionar todas las bases de datos que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="43b4b-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="43b4b-126">Para obtener más información, vea [Usar los detalles del Explorador de objetos para supervisar los grupos de disponibilidad &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="43b4b-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="43b4b-127">Para quitar una sola base de datos, selecciónela en el panel **Explorador de objetos** o el panel **Detalles del Explorador de objetos** .</span><span class="sxs-lookup"><span data-stu-id="43b4b-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="43b4b-128">Haga clic con el botón derecho en la base de datos o bases de datos seleccionadas y seleccione **Quitar base de datos del grupo de disponibilidad** en el menú de comandos.</span><span class="sxs-lookup"><span data-stu-id="43b4b-128">Right-click the selected database or databases, and select **Remove Database from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="43b4b-129">En el cuadro de diálogo **Quitar bases de datos del grupo de disponibilidad** , para quitar todas las bases de datos enumeradas, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="43b4b-129">In the **Remove Databases from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="43b4b-130">Si no desea quitar todos ellas, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="43b4b-130">If you do not want to remove all them, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43b4b-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43b4b-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="43b4b-132">**Para quitar una base de datos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="43b4b-132">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="43b4b-133">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="43b4b-133">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="43b4b-134">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="43b4b-134">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="43b4b-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span><span class="sxs-lookup"><span data-stu-id="43b4b-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span></span>  
  
     <span data-ttu-id="43b4b-136">donde *group_name* es el nombre del grupo de disponibilidad y *database_name* es el nombre de la base de datos que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="43b4b-136">where *group_name* is the name of the availability group and *database_name* is the name of the database to be removed.</span></span>  
  
     <span data-ttu-id="43b4b-137">En el ejemplo siguiente se quita una base de datos denominada `Db6` del grupo de disponibilidad `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="43b4b-137">The following example removes a databases named `Db6` from the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE DATABASE Db6;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="43b4b-138">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="43b4b-138">Using PowerShell</span></span>  
 <span data-ttu-id="43b4b-139">**Para quitar una base de datos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="43b4b-139">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="43b4b-140">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="43b4b-140">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="43b4b-141">Utilice el cmdlet `Remove-SqlAvailabilityDatabase`, especificando el nombre de la base de datos de disponibilidad que se va a quitar del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="43b4b-141">Use the `Remove-SqlAvailabilityDatabase` cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="43b4b-142">Cuando esté conectado a la instancia del servidor que hospeda la réplica principal, la base de datos principal y sus bases de datos secundarias correspondientes se quitarán en su totalidad del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="43b4b-142">When you are connected to the server instance that hosts the primary replica, the primary database and its corresponding secondary databases are all removed from the availability group.</span></span>  
  
     <span data-ttu-id="43b4b-143">Por ejemplo, el comando siguiente quita la base de datos de disponibilidad `MyDb9` del grupo de disponibilidad denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="43b4b-143">For example, the following command removes the availability database `MyDb9` from the availability group named `MyAg`.</span></span> <span data-ttu-id="43b4b-144">Dado que este comando se ejecuta en la instancia del servidor que hospeda la réplica principal, la base de datos principal y todas sus bases de datos secundarias correspondientes se quitarán del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="43b4b-144">Because the command is executed on the server instance that hosts the primary replica, the primary database and all its corresponding secondary databases are removed from the availability group.</span></span> <span data-ttu-id="43b4b-145">La sincronización de datos ya no se producirá para esta base de datos en ninguna réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="43b4b-145">Data synchronization will no longer occur for this database on any secondary replica.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\PrimaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb9  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="43b4b-146">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43b4b-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="43b4b-147">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="43b4b-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="43b4b-148">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="43b4b-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="43b4b-149">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="43b4b-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-an-availability-database-from-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="43b4b-150">Seguimiento: después de quitar una base de datos de disponibilidad de un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="43b4b-150">Follow Up: After Removing an Availability Database from an Availability Group</span></span>  
 <span data-ttu-id="43b4b-151">La acción de quitar una base de datos de disponibilidad de su grupo de disponibilidad finaliza la sincronización de datos entre la base de datos principal anterior y las bases de datos secundarias correspondientes.</span><span class="sxs-lookup"><span data-stu-id="43b4b-151">Removing an availability database from its availability group ends data synchronization between the former primary database and the corresponding secondary databases.</span></span> <span data-ttu-id="43b4b-152">La base de datos principal anterior permanece en línea.</span><span class="sxs-lookup"><span data-stu-id="43b4b-152">The former primary database remains online.</span></span> <span data-ttu-id="43b4b-153">Cada base de datos secundaria correspondiente se pone en estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="43b4b-153">Every corresponding secondary database is placed in the RESTORING state.</span></span>  
  
 <span data-ttu-id="43b4b-154">En este momento hay formas alternativas de tratar una base de datos secundaria quitada:</span><span class="sxs-lookup"><span data-stu-id="43b4b-154">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="43b4b-155">Si ya no necesita una base de datos secundaria, puede quitarla.</span><span class="sxs-lookup"><span data-stu-id="43b4b-155">If you no longer need a given secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="43b4b-156">Para obtener más información, vea [Eliminar una base de datos](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="43b4b-156">For more information, see [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="43b4b-157">Si desea obtener acceso a una base de datos secundaria quitada después de haberse quitado del grupo de disponibilidad, puede recuperar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43b4b-157">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="43b4b-158">Sin embargo, si recupera una base de datos secundaria quitada, dos bases de datos independientes divergentes que tienen el mismo nombre estarán en línea.</span><span class="sxs-lookup"><span data-stu-id="43b4b-158">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="43b4b-159">De asegurarse de que los clientes puedan tener acceso solo a una de ellas, generalmente la base de datos principal más reciente.</span><span class="sxs-lookup"><span data-stu-id="43b4b-159">You must make sure that clients can access only one of them, typically the most recent primary database.</span></span>  
  
     <span data-ttu-id="43b4b-160">Para obtener más información, vea [Recuperar una base de datos sin restaurar los datos &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="43b4b-160">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b4b-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43b4b-161">See Also</span></span>  
 <span data-ttu-id="43b4b-162">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43b4b-162">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="43b4b-163">Quitar una base de datos secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43b4b-163">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
