---
title: Preparar manualmente una base de datos secundaria para un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.configsecondarydbs.f1
- sql12.swb.availabilitygroup.preparedbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 9f2feb3c-ea9b-4992-8202-2aeed4f9a6dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3da3f7332bdabce65785b2844157dd4639389254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671183"
---
# <a name="manually-prepare-a-secondary-database-for-an-availability-group-sql-server"></a><span data-ttu-id="e70fb-102">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e70fb-102">Manually Prepare a Secondary Database for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="e70fb-103">En este tema se describe cómo preparar una base de datos secundaria de un grupo de disponibilidad AlwaysOn en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e70fb-103">This topic describes how to prepare a secondary database for an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="e70fb-104">La preparación de una base de datos secundaria requiere dos pasos: (1) restaurar una copia de seguridad reciente de la base de datos principal y las copias de seguridad del registro subsiguientes en cada instancia del servidor que hospeda la réplica secundaria utilizando RESTORE WITH NORECOVERY, y (2) unir la base de datos restaurada al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70fb-104">Preparing a secondary database requires two steps: (1) restoring a recent database backup of the primary database and subsequent log backups onto each server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY, and (2) joining the restored database to the availability group.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="e70fb-105">Si no tiene una configuración de trasvase de registros, es posible que pueda convertir la base de datos principal de trasvase de registros junto con una o varias de sus bases de datos secundarias en una base de datos principal AlwaysOn y una o varias bases de datos secundarias AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e70fb-105">If you have an existing log shipping configuration, you might be able to convert the log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and one or more AlwaysOn secondary databases.</span></span> <span data-ttu-id="e70fb-106">Para obtener más información, consulte [requisitos previos para migrar desde el trasvase de registros a Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-106">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="e70fb-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e70fb-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e70fb-108">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="e70fb-108">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="e70fb-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="e70fb-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e70fb-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e70fb-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e70fb-111">**Para preparar una base de datos secundaria, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="e70fb-111">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="e70fb-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e70fb-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e70fb-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e70fb-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="e70fb-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e70fb-114">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="e70fb-115">Tareas de copia de seguridad y restauración relacionadas</span><span class="sxs-lookup"><span data-stu-id="e70fb-115">Related Backup and Restore Tasks</span></span>](#RelatedTasks)  
  
-   <span data-ttu-id="e70fb-116">**Seguimiento:** [Después de preparar una base de datos secundaria](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e70fb-116">**Follow Up:** [After Preparing a Secondary Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e70fb-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e70fb-117">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="e70fb-118">Requisitos previos y restricciones</span><span class="sxs-lookup"><span data-stu-id="e70fb-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="e70fb-119">Asegúrese de que el sistema en donde piensa colocar la base de datos posee una unidad de disco con espacio suficiente para las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="e70fb-119">Make sure that the system where you plan to place database possesses a disk drive with sufficient space for the secondary databases.</span></span>  
  
-   <span data-ttu-id="e70fb-120">La base de datos secundaria debe tener el mismo nombre que la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="e70fb-120">The name of the secondary database must be the same as the name of the primary database.</span></span>  
  
-   <span data-ttu-id="e70fb-121">Use RESTORE WITH NORECOVERY para cada operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="e70fb-121">Use RESTORE WITH NORECOVERY for every restore operation.</span></span>  
  
-   <span data-ttu-id="e70fb-122">Si la base de datos secundaria debe residir en una ruta de acceso de archivo diferente (incluida la letra de unidad) de la de la base de datos principal, el comando de restauración debe utilizar la opción WITH MOVE para cada uno de los archivos de base de datos para especificarlos a la ruta de acceso de la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="e70fb-122">If the secondary database needs to reside on a different file path (including the drive letter) than the primary database, the restore command must also use the WITH MOVE option for each of the database files to specify them to the path of the secondary database.</span></span>  
  
-   <span data-ttu-id="e70fb-123">Si restaura la base de datos grupo de archivos por grupo de archivos, asegúrese de restaurar la base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="e70fb-123">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
-   <span data-ttu-id="e70fb-124">Después de restaurar la base de datos, debe restaurar (WITH NORECOVERY) cada copia de seguridad del registro creada desde la última copia de seguridad de datos restaurada.</span><span class="sxs-lookup"><span data-stu-id="e70fb-124">After restoring the database, you must restore (WITH NORECOVERY) every log backup created since the last restored data backup.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e70fb-125">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="e70fb-125">Recommendations</span></span>  
  
-   <span data-ttu-id="e70fb-126">En las instancias independientes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]se recomienda que, si es posible, la ruta de acceso de archivo (incluida la letra de unidad) de una base de datos secundaria determinada sea idéntica a la de la base de datos principal correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e70fb-126">On stand-alone instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], we recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span> <span data-ttu-id="e70fb-127">Esto se debe a que si se mueven los archivos de base de datos al crear una base de datos secundaria, una operación posterior de agregar archivo podría producir un error en la base de datos secundaria y hacer que esta se suspenda.</span><span class="sxs-lookup"><span data-stu-id="e70fb-127">This is because if you move the database files when creating a secondary database, a later add-file operation might fail on the secondary database and cause the secondary database to be suspended.</span></span>  
  
-   <span data-ttu-id="e70fb-128">Antes de preparar las bases de datos secundarias, se recomienda encarecidamente suspender las copias de seguridad del registro programadas en las bases de datos del grupo de disponibilidad hasta que la inicialización de las réplicas secundarias se haya completado.</span><span class="sxs-lookup"><span data-stu-id="e70fb-128">Before preparing your secondary databases, we strongly recommend that you suspend scheduled log backups on the databases in the availability group until the initialization of secondary replicas has completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e70fb-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e70fb-129">Security</span></span>  
 <span data-ttu-id="e70fb-130">Cuando se realiza una copia de seguridad de una base de datos, la [propiedad de base de datos TRUSTWORTHY](../../../relational-databases/security/trustworthy-database-property.md) se establece en OFF.</span><span class="sxs-lookup"><span data-stu-id="e70fb-130">When a database is backed up, the [TRUSTWORTHY database property](../../../relational-databases/security/trustworthy-database-property.md) is set to OFF.</span></span> <span data-ttu-id="e70fb-131">Por lo tanto, TRUSTWORTHY está siempre en OFF en una base de datos que se acaba de restaurar.</span><span class="sxs-lookup"><span data-stu-id="e70fb-131">Therefore, TRUSTWORTHY is always OFF on a newly restored database.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e70fb-132">Permisos</span><span class="sxs-lookup"><span data-stu-id="e70fb-132">Permissions</span></span>  
 <span data-ttu-id="e70fb-133">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="e70fb-133">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span> <span data-ttu-id="e70fb-134">Para obtener más información, vea [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e70fb-134">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="e70fb-135">Cuando la base de datos que se va a restaurar no existe en la instancia de servidor, la instrucción RESTORE requiere permisos CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e70fb-135">When the database being restored does not exist on the server instance, the RESTORE statement requires CREATE DATABASE permissions.</span></span> <span data-ttu-id="e70fb-136">Para obtener más información, vea [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e70fb-136">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e70fb-137">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e70fb-137">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70fb-138"> Si las rutas de acceso de archivos de copia de seguridad y restauración son idénticas entre la instancia de servidor que hospeda la réplica principal y cada instancia que hospeda la réplica secundaria, debe poder crear bases de datos secundarias con el [Asistente para nuevo grupo de disponibilidad](use-the-availability-group-wizard-sql-server-management-studio.md), [Asistente para agregar una réplica al grupo de disponibilidad](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)o el [Asistente para agregar una base de datos al grupo de disponibilidad](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-138">If the backup and restore file paths are identical between the server instance that hosts the primary replica and every instance that hosts a secondary replica, you should be able create secondary databases by using [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md).</span></span>  
  
 <span data-ttu-id="e70fb-139">**Para preparar una base de datos secundaria**</span><span class="sxs-lookup"><span data-stu-id="e70fb-139">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="e70fb-140">A menos que ya tenga una copia de seguridad reciente de la base de datos principal, cree una nueva copia de seguridad de base de datos completa o diferencial.</span><span class="sxs-lookup"><span data-stu-id="e70fb-140">Unless you already have a recent database backup of the primary database, create a new full or differential database backup.</span></span> <span data-ttu-id="e70fb-141">Como práctica recomendada, coloque esta copia de seguridad y las copias de seguridad del registro subsiguientes en el recurso compartido de red recomendado.</span><span class="sxs-lookup"><span data-stu-id="e70fb-141">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="e70fb-142">Cree al menos una nueva copia de seguridad del registro de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="e70fb-142">Create at least one new log backup of the primary database.</span></span>  
  
3.  <span data-ttu-id="e70fb-143">En la instancia del servidor que hospeda la réplica secundaria, restaure la copia de seguridad completa de la base de datos principal (y opcionalmente una copia de seguridad diferencial) seguida de las copias de seguridad del registro subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="e70fb-143">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by any subsequent log backups.</span></span>  
  
     <span data-ttu-id="e70fb-144">En la página **Opciones de RESTORE DATABASE** , seleccione **Dejar la base de datos no operativa y no revertir transacciones no confirmadas. Pueden restaurarse registros de transacciones adicionales. (RESTORE WITH NORECOVERY)**.</span><span class="sxs-lookup"><span data-stu-id="e70fb-144">On the **RESTORE DATABASEOptions** page, select **Leave the database non-operational, and do not roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**.</span></span>  
  
     <span data-ttu-id="e70fb-145">Si las rutas de acceso de archivos de la base de datos principal y la base de datos secundaria difieren, por ejemplo, si la base de datos principal se encuentra en la unidad "F:" pero la instancia de servidor que hospeda la réplica secundaria no tiene unidad "F:", incluya la opción MOVE en la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="e70fb-145">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
4.  <span data-ttu-id="e70fb-146">Para completar la configuración de la base de datos secundaria, debe unirla al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70fb-146">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="e70fb-147">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-147">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70fb-148">Para obtener información sobre cómo realizar estas operaciones de copia de seguridad y restauración, vea [Tareas de copia de seguridad y restauración relacionadas](#RelatedTasks), más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e70fb-148">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this section.</span></span>  
  
###  <a name="related-backup-and-restore-tasks"></a><a name="RelatedTasks"></a><span data-ttu-id="e70fb-149">Tareas de copia de seguridad y restauración relacionadas</span><span class="sxs-lookup"><span data-stu-id="e70fb-149">Related Backup and Restore Tasks</span></span>  
 <span data-ttu-id="e70fb-150">**Para crear una copia de seguridad de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="e70fb-150">**To create a database backup**</span></span>  
  
-   [<span data-ttu-id="e70fb-151">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-151">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="e70fb-152">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-152">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="e70fb-153">**Para crear una copia de seguridad del registro**</span><span class="sxs-lookup"><span data-stu-id="e70fb-153">**To create a log backup**</span></span>  
  
-   [<span data-ttu-id="e70fb-154">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-154">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
 <span data-ttu-id="e70fb-155">**Para restaurar copias de seguridad**</span><span class="sxs-lookup"><span data-stu-id="e70fb-155">**To restore backups**</span></span>  
  
-   [<span data-ttu-id="e70fb-156">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-156">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="e70fb-157">Restaurar una copia de seguridad diferencial de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-157">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="e70fb-158">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-158">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="e70fb-159">Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-159">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e70fb-160">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e70fb-160">Using Transact-SQL</span></span>  
 <span data-ttu-id="e70fb-161">**Para preparar una base de datos secundaria**</span><span class="sxs-lookup"><span data-stu-id="e70fb-161">**To prepare a secondary database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70fb-162">Para obtener un ejemplo de este procedimiento, vea [Ejemplo (Transact-SQL)](#ExampleTsql), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="e70fb-162">For an example of this procedure, see [Example (Transact-SQL)](#ExampleTsql), earlier in this topic.</span></span>  
  
1.  <span data-ttu-id="e70fb-163">A menos que tenga una copia de seguridad completa reciente de la base de datos principal, conéctese a la instancia del servidor que hospeda la réplica principal y cree una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e70fb-163">Unless you have a recent full backup of the primary database, connect to the server instance that hosts the primary replica and create a full database backup.</span></span> <span data-ttu-id="e70fb-164">Como práctica recomendada, coloque esta copia de seguridad y las copias de seguridad del registro subsiguientes en el recurso compartido de red recomendado.</span><span class="sxs-lookup"><span data-stu-id="e70fb-164">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="e70fb-165">En la instancia del servidor que hospeda la réplica secundaria, restaure la copia de seguridad completa de la base de datos principal (y opcionalmente una copia de seguridad diferencial) seguida de todas las copias de seguridad del registro subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="e70fb-165">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by all subsequent log backups.</span></span> <span data-ttu-id="e70fb-166">Use WITH NORECOVERY para cada operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="e70fb-166">Use WITH NORECOVERY for every restore operation.</span></span>  
  
     <span data-ttu-id="e70fb-167">Si las rutas de acceso de archivos de la base de datos principal y la base de datos secundaria difieren, por ejemplo, si la base de datos principal se encuentra en la unidad "F:" pero la instancia de servidor que hospeda la réplica secundaria no tiene unidad "F:", incluya la opción MOVE en la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="e70fb-167">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
3.  <span data-ttu-id="e70fb-168">Si se han realizado copias de seguridad del registro de la base de datos principal desde que se realizó la copia de seguridad del registro obligatoria, deben copiarse también en la instancia de servidor que hospeda la réplica secundaria y aplicar cada una de ellas a la base de datos secundaria, empezando con la más antigua y utilizando siempre RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="e70fb-168">If any log backups have been taken on the primary database since the required log backup, you must also copy these to the server instance that hosts the secondary replica and apply each of those log backups to the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e70fb-169">Ni existiría una copia de seguridad del registro si la base de datos principal se ha creado recientemente y no se ha hecho todavía ninguna copia de seguridad del registro, o si el modelo de recuperación ha cambiado recientemente de SIMPLE a FULL.</span><span class="sxs-lookup"><span data-stu-id="e70fb-169">A log backup would not exist if the primary database has just been created and no log backup has been taken yet or if the recovery model has just been changed from simple to full.</span></span>  
  
4.  <span data-ttu-id="e70fb-170">Para completar la configuración de la base de datos secundaria, debe unirla al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70fb-170">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="e70fb-171">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-171">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70fb-172">Para obtener información sobre cómo realizar estas operaciones de copia de seguridad y restauración, vea [Tareas de copia de seguridad y restauración relacionadas](#RelatedTasks), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e70fb-172">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this topic.</span></span>  
  
###  <a name="transact-sql-example"></a><a name="ExampleTsql"></a><span data-ttu-id="e70fb-173">Ejemplo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e70fb-173">Transact-SQL Example</span></span>  
 <span data-ttu-id="e70fb-174">En el siguiente ejemplo se prepara una base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="e70fb-174">The following example prepares a secondary database.</span></span> <span data-ttu-id="e70fb-175">En este ejemplo se utiliza la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , que usa de forma predeterminada un modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="e70fb-175">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="e70fb-176">Para utilizar la base de datos [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , modifíquela para que utilice el modelo de recuperación completa:</span><span class="sxs-lookup"><span data-stu-id="e70fb-176">To use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```sql
    USE master;  
    GO  
    ALTER DATABASE MyDB1   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="e70fb-177">Después de modificar el modelo de recuperación de la base de datos de SIMPLE a FULL, cree una copia de seguridad completa, que puede usarse para crear la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="e70fb-177">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the secondary database.</span></span> <span data-ttu-id="e70fb-178">Puesto que se ha cambiado recientemente el modelo de recuperación, se especifica la opción WITH FORMAT para crear un conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="e70fb-178">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="e70fb-179">Esto es útil para separar las copias de seguridad con el modelo de recuperación completa a partir de cualquier copia de seguridad anterior realizada con el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="e70fb-179">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="e70fb-180">Para este ejemplo, el archivo de copia de seguridad (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) se crea en la misma unidad que la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e70fb-180">For the purpose of this example, the backup file (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e70fb-181">Para una base de datos de producción, siempre se debe realizar la copia de seguridad en un dispositivo independiente.</span><span class="sxs-lookup"><span data-stu-id="e70fb-181">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="e70fb-182">En la instancia del servidor que hospeda la réplica principal (`INSTANCE01`), cree una copia de seguridad completa de la base de datos principal del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e70fb-182">On the server instance that hosts the primary replica (`INSTANCE01`), create a full backup of the primary database as follows:</span></span>  
  
    ```sql
    BACKUP DATABASE MyDB1   
        TO DISK = 'C:\MyDB1.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="e70fb-183">Copie la copia de seguridad completa en la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="e70fb-183">Copy the full backup to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="e70fb-184">Restaure la copia de seguridad completa en la instancia del servidor que hospeda la réplica secundaria utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="e70fb-184">Restore the full backup, using RESTORE WITH NORECOVERY, onto the server instance that hosts the secondary replica.</span></span> <span data-ttu-id="e70fb-185">El comando de restauración depende de si las rutas de acceso de las bases de datos principal y secundaria son idénticas.</span><span class="sxs-lookup"><span data-stu-id="e70fb-185">The restore command depends on whether the paths of primary and secondary databases are identical.</span></span>  
  
    -   <span data-ttu-id="e70fb-186">**Si las rutas de acceso son idénticas:**</span><span class="sxs-lookup"><span data-stu-id="e70fb-186">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="e70fb-187">En el equipo que hospeda la réplica secundaria, restaure la copia de seguridad completa del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="e70fb-187">On the computer that hosts the secondary replica, restore the full backup as follows:</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1   
            FROM DISK = 'C:\MyDB1.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="e70fb-188">**Si las rutas de acceso son distintas:**</span><span class="sxs-lookup"><span data-stu-id="e70fb-188">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="e70fb-189">Si la ruta de acceso de la base de datos secundaria difiere de la de la base de datos principal (por ejemplo, letras de unidad diferentes), la creación de la base de datos secundaria requiere que la operación de restauración incluya una cláusula MOVE.</span><span class="sxs-lookup"><span data-stu-id="e70fb-189">If the path of the secondary database differs from the path of the primary database (for instance, their drive letters differ), creating the secondary database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="e70fb-190">Si los nombres de las rutas de acceso de las bases de datos principal y secundaria son distintos, no se puede agregar ningún archivo.</span><span class="sxs-lookup"><span data-stu-id="e70fb-190">If the path names of the primary and secondary databases differ, you cannot add a file.</span></span> <span data-ttu-id="e70fb-191">Esto es debido a que al recibir el registro para la operación de agregar un archivo, la instancia del servidor de la réplica secundaria intenta colocar el nuevo archivo en la misma ruta de acceso utilizada por la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="e70fb-191">This is because on receiving the log for the add file operation, the server instance of the secondary replica attempts to place the new file in the same path as used by the primary database.</span></span>  
  
         <span data-ttu-id="e70fb-192">Por ejemplo, el siguiente comando restaura una copia de seguridad de una base de datos principal que reside en el directorio de datos de la instancia predeterminada de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="e70fb-192">For example, the following command restores a backup of a primary database that resides in the data directory of the default instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span></span> <span data-ttu-id="e70fb-193">La operación de restauración de base de datos debe mover la base de datos al directorio de datos de una instancia remota de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] denominada (*AlwaysOn1*), que hospeda la réplica secundaria en otro nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="e70fb-193">The restore database operation must move the database to the data directory of a remote instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named  (*AlwaysOn1*), which hosts the secondary replica on another cluster node.</span></span> <span data-ttu-id="e70fb-194">Allí, los archivos de registro y datos se restauran en el directorio *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* .</span><span class="sxs-lookup"><span data-stu-id="e70fb-194">There, the data and log files are restored to the *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* directory .</span></span> <span data-ttu-id="e70fb-195">La operación de restauración usa WITH NORECOVERY para la base de datos secundaria en la base de datos de restauración.</span><span class="sxs-lookup"><span data-stu-id="e70fb-195">The restore operation uses WITH NORECOVERY, to leave the secondary database in the restoring database.</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1  
          FROM DISK='C:\MyDB1.bak'  
         WITH NORECOVERY,   
            MOVE 'MyDB1_Data' TO   
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.mdf',   
            MOVE 'MyDB1_Log' TO  
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="e70fb-196">Una vez restaurada la copia de seguridad completa, debe crearse una copia de seguridad del registro en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="e70fb-196">After you restore the full backup, you must create a log backup on the primary database.</span></span> <span data-ttu-id="e70fb-197">Por ejemplo, la siguiente instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] realiza una copia de seguridad del registro en un archivo de copia de seguridad denominado *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="e70fb-197">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement backs up the log to the a backup file named *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    BACKUP LOG MyDB1   
      TO DISK = 'E:\MyDB1_log.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="e70fb-198">Para poder unir la base de datos a la réplica secundaria, se debe aplicar la copia de seguridad de registros obligatoria (y las copias de seguridad de registros subsiguientes).</span><span class="sxs-lookup"><span data-stu-id="e70fb-198">Before you can join the database to the secondary replica, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="e70fb-199">Por ejemplo, la siguiente instrucción de [!INCLUDE[tsql](../../../includes/tsql-md.md)] restaura el primer registro de *C:\MyDB1.bak*:</span><span class="sxs-lookup"><span data-stu-id="e70fb-199">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores the first log from *C:\MyDB1.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="e70fb-200">Si las copias de seguridad del registro adicionales se producen antes de que la base de datos se una a la réplica secundaria, también debe restaurar todas las copias de seguridad del registro, de forma secuencial, a la instancia del servidor que hospeda la réplica secundaria mediante RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="e70fb-200">If any additional log backups occur before the database joins the secondary replica, you must also restore all of those log backups, in sequence, to the server instance that hosts the secondary replica using RESTORE WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="e70fb-201">Por ejemplo, la siguiente instrucción de [!INCLUDE[tsql](../../../includes/tsql-md.md)] restaura dos registros adicionales de *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="e70fb-201">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores two additional logs from *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="e70fb-202">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e70fb-202">Using PowerShell</span></span>  
 <span data-ttu-id="e70fb-203">**Para preparar una base de datos secundaria**</span><span class="sxs-lookup"><span data-stu-id="e70fb-203">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="e70fb-204">Si necesita crear una copia de seguridad reciente de la base de datos principal, cambie el directorio (`cd`) a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e70fb-204">If you need to create a recent backup of the primary database, change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="e70fb-205">Utilice el cmdlet `Backup-SqlDatabase` para crear cada una de las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e70fb-205">Use the `Backup-SqlDatabase` cmdlet to create each of the backups.</span></span>  
  
3.  <span data-ttu-id="e70fb-206">Cambie el directorio (`cd`) a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="e70fb-206">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="e70fb-207">Para restaurar las copias de seguridad de base de datos y del registro de cada base de datos principal, utilice el cmdlet `restore-SqlDatabase`, especificando el parámetro de restauración `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="e70fb-207">To restore the database and log backups of each primary database, use the `restore-SqlDatabase` cmdlet, specifying the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="e70fb-208">Si las rutas de acceso de archivo difieren entre equipos que hospedan la réplica principal y la réplica secundaria de destino, utilice también el parámetro de restauración `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="e70fb-208">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e70fb-209">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e70fb-209">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="e70fb-210">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-210">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
5.  <span data-ttu-id="e70fb-211">Para completar la configuración de la base de datos secundaria, debe unirla al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70fb-211">To complete configuration of the secondary database, you need to join it to the availability group.</span></span> <span data-ttu-id="e70fb-212">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-212">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="e70fb-213">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e70fb-213">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="e70fb-214">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="e70fb-214">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="sample-backup-and-restore-script-and-command"></a><a name="ExamplePSscript"></a><span data-ttu-id="e70fb-215">Ejemplo de script y comando de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="e70fb-215">Sample Backup and Restore Script and Command</span></span>  
 <span data-ttu-id="e70fb-216">Los siguientes comandos de PowerShell realizan una copia de seguridad del registro de transacciones y una copia de seguridad completa de la base de datos en un recurso compartido de red y restauran las copias de seguridad de ese recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="e70fb-216">The following PowerShell commands back up a full database backup and transaction log to a network share and restore those backups from that share.</span></span> <span data-ttu-id="e70fb-217">En este ejemplo se supone que la ruta de acceso de archivo en que se restaura la base de datos es la misma que la ruta de acceso de archivo en que se creo la copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e70fb-217">This example assumes that the file path to which the database is restored is the same as the file path on which the database was backed up.</span></span>  
  
```powershell
# Create database backup  
Backup-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -ServerInstance "SourceMachine\Instance"  
# Create log backup  
Backup-SqlDatabase -Database "MyDB1" -BackupAction "Log" -BackupFile "\\share\backups\MyDB1.trn" -ServerInstance "SourceMachine\Instance"  
# Restore database backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -NoRecovery -ServerInstance "DestinationMachine\Instance"  
# Restore log backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.trn" -RestoreAction "Log" -NoRecovery -ServerInstance "DestinationMachine\Instance"
```  
  
##  <a name="follow-up-after-preparing-a-secondary-database"></a><a name="FollowUp"></a><span data-ttu-id="e70fb-218">Seguimiento: después de preparar una base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="e70fb-218">Follow Up: After Preparing a Secondary Database</span></span>  
 <span data-ttu-id="e70fb-219">Para completar la configuración de la base de datos secundaria, debe unir la base de datos que se acaba de restaurar al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70fb-219">To complete configuration of the secondary database, join the newly restored database to the availability group.</span></span> <span data-ttu-id="e70fb-220">Para obtener más información, vea [Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e70fb-220">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70fb-221">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e70fb-221">See Also</span></span>  
 <span data-ttu-id="e70fb-222">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e70fb-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="e70fb-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e70fb-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="e70fb-224">[Argumentos RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e70fb-224">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="e70fb-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e70fb-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="e70fb-226">Solucionar problemas de una operación Add-File &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="e70fb-226">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
