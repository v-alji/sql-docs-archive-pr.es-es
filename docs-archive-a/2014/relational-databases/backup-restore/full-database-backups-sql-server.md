---
title: Copias de seguridad completas de bases de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- backups [SQL Server], database
- backing up databases [SQL Server], full backups
- estimating database backup size
- backing up [SQL Server], size of backup
- database backups [SQL Server], full backups
- size [SQL Server], backups
- database backups [SQL Server], about backing up databases
ms.assetid: 4d933d19-8d21-4aa1-8153-d230cb3a3f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ee871b6cabbe6c2b2cb4f444fd1e2d42d711dfbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745837"
---
# <a name="full-database-backups-sql-server"></a><span data-ttu-id="307a7-102">Copias de seguridad completas de bases de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="307a7-102">Full Database Backups (SQL Server)</span></span>
  <span data-ttu-id="307a7-103">Una copia de seguridad completa de la base de datos crea una copia de seguridad de toda la base de datos,</span><span class="sxs-lookup"><span data-stu-id="307a7-103">A full database backup backs up the whole database.</span></span> <span data-ttu-id="307a7-104">Esto incluye la parte del registro de transacciones para poder recuperar la base de datos completa después de restaurar una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="307a7-104">This includes part of the transaction log so that the full database can be recovered after a full database backup is restored.</span></span> <span data-ttu-id="307a7-105">Las copias de seguridad completas representan la base de datos en el momento en que finalizó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="307a7-105">Full database backups represent the database at the time the backup finished.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="307a7-106">A medida que la base de datos aumenta de tamaño, las copias de seguridad completas requieren una mayor cantidad de tiempo para finalizar y espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="307a7-106">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="307a7-107">Por ello, para una base de datos grande, puede que desee complementar una copia de seguridad completa con una serie de *copias de seguridad diferenciales*.</span><span class="sxs-lookup"><span data-stu-id="307a7-107">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="307a7-108">Para obtener más información, vea [Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="307a7-108">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="307a7-109">TRUSTWORTHY se establece en OFF en una copia de seguridad de base de datos.</span><span class="sxs-lookup"><span data-stu-id="307a7-109">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="307a7-110">Para obtener información sobre cómo establecer TRUSTWORTHY en ON, vea [Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="307a7-110">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="307a7-111">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="307a7-111">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="307a7-112">Copias de seguridad de la base de datos en el modelo de recuperación simple</span><span class="sxs-lookup"><span data-stu-id="307a7-112">Database Backups Under the Simple Recovery Model</span></span>](#DbBuRMs)  
  
-   [<span data-ttu-id="307a7-113">Copias de seguridad de la base de datos en el modelo de recuperación completa</span><span class="sxs-lookup"><span data-stu-id="307a7-113">Database Backups Under the Full Recovery Model</span></span>](#DbBuRMf)  
  
-   [<span data-ttu-id="307a7-114">Usar una copia de seguridad completa de la base de datos para restaurar la base de datos</span><span class="sxs-lookup"><span data-stu-id="307a7-114">Use a Full Database Backup to Restore the Database</span></span>](#RestoreDbBu)  
  
-   [<span data-ttu-id="307a7-115">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="307a7-115">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="database-backups-under-the-simple-recovery-model"></a><a name="DbBuRMs"></a> <span data-ttu-id="307a7-116">Copias de seguridad de la base de datos en el modelo de recuperación simple</span><span class="sxs-lookup"><span data-stu-id="307a7-116">Database Backups Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="307a7-117">Con el modelo de recuperación simple, después de cada copia de seguridad, la base de datos queda expuesta a la pérdida potencial del trabajo en caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="307a7-117">Under the simple recovery model, after each backup, the database is exposed to potential work loss if a disaster were to occur.</span></span> <span data-ttu-id="307a7-118">El riesgo de pérdida del trabajo se incrementa con cada actualización hasta la siguiente copia de seguridad, cuando el riesgo de pérdida vuelve a cero y empieza un nuevo ciclo de riesgo.</span><span class="sxs-lookup"><span data-stu-id="307a7-118">The work-loss exposure increases with each update until the next backup, when the work-loss exposure returns to zero and a new cycle of work-loss exposure starts.</span></span> <span data-ttu-id="307a7-119">El riesgo de pérdida de trabajo aumenta con el tiempo entre una copia de seguridad y otra.</span><span class="sxs-lookup"><span data-stu-id="307a7-119">Work-loss exposure increases over time between backups.</span></span> <span data-ttu-id="307a7-120">La siguiente ilustración muestra el riesgo de pérdida del trabajo en una estrategia de copia de seguridad que solo usa copias de seguridad completas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="307a7-120">The following illustration shows the work-loss exposure for a backup strategy that uses only full database backups.</span></span>  
  
 <span data-ttu-id="307a7-121">![Muestra el riesgo de pérdida de trabajo entre copias de seguridad de base de datos](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Muestra el riesgo de pérdida de trabajo entre copias de seguridad de base de datos")</span><span class="sxs-lookup"><span data-stu-id="307a7-121">![Shows work-loss exposure between database backups](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Shows work-loss exposure between database backups")</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="307a7-122">Ejemplo ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="307a7-122">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="307a7-123">El siguiente ejemplo muestra cómo crear una copia de seguridad completa de la base de datos mediante WITH FORMAT para sobrescribir cualquier copia de seguridad existente y crear un nuevo conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="307a7-123">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span>  
  
```  
-- Back up the AdventureWorks2012 database to new media set.  
BACKUP DATABASE AdventureWorks2012  
    TO DISK = 'Z:\SQLServerBackups\AdventureWorksSimpleRM.bak'   
    WITH FORMAT;  
GO  
```  
  
##  <a name="database-backups-under-the-full-recovery-model"></a><a name="DbBuRMf"></a> <span data-ttu-id="307a7-124">Copias de seguridad de la base de datos en el modelo de recuperación completa</span><span class="sxs-lookup"><span data-stu-id="307a7-124">Database Backups Under the Full Recovery Model</span></span>  
 <span data-ttu-id="307a7-125">En las bases de datos que usan la recuperación completa y optimizada para cargas masivas de registros, las copias de seguridad de base de datos son necesarias pero no suficientes.</span><span class="sxs-lookup"><span data-stu-id="307a7-125">For databases that use full and bulk-logged recovery, database backups are necessary but not sufficient.</span></span> <span data-ttu-id="307a7-126">También se requieren copias de seguridad de registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="307a7-126">Transaction log backups are also required.</span></span> <span data-ttu-id="307a7-127">La siguiente ilustración muestra la estrategia de copia de seguridad menos compleja en un modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="307a7-127">The following illustration shows the least complex backup strategy that is possible under the full recovery model.</span></span>  
  
 <span data-ttu-id="307a7-128">![Series de copias de seguridad completas de bases de datos y de registros](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series de copias de seguridad completas de bases de datos y de registros")</span><span class="sxs-lookup"><span data-stu-id="307a7-128">![Series of full database backups and log backups](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series of full database backups and log backups")</span></span>  
  
 <span data-ttu-id="307a7-129">Para obtener información sobre cómo crear copias de seguridad de registros, vea [Copias de seguridad de registros de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="307a7-129">For information about how to create log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="307a7-130">Ejemplo ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="307a7-130">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="307a7-131">El siguiente ejemplo muestra cómo crear una copia de seguridad completa de la base de datos mediante WITH FORMAT para sobrescribir cualquier copia de seguridad existente y crear un nuevo conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="307a7-131">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span> <span data-ttu-id="307a7-132">A continuación, en el ejemplo se realiza una copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="307a7-132">Then, the example backs up the transaction log.</span></span> <span data-ttu-id="307a7-133">En una situación real, deberá realizar una serie de copias de seguridad de registros periódicas.</span><span class="sxs-lookup"><span data-stu-id="307a7-133">In a real-life situation, you would have to perform a series of regular log backups.</span></span> <span data-ttu-id="307a7-134">Para este ejemplo, la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] se configura para usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="307a7-134">For this example, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database is set to use the full recovery model.</span></span>  
  
```  
USE master;  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
GO  
-- Back up the AdventureWorks2012 database to new media set (backup set 1).  
BACKUP DATABASE AdventureWorks2012  
  TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak'   
  WITH FORMAT;  
GO  
--Create a routine log backup (backup set 2).  
BACKUP LOG AdventureWorks2012 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak';  
GO  
```  
  
##  <a name="use-a-full-database-backup-to-restore-the-database"></a><a name="RestoreDbBu"></a> <span data-ttu-id="307a7-135">Usar una copia de seguridad completa de la base de datos para restaurar la base de datos</span><span class="sxs-lookup"><span data-stu-id="307a7-135">Use a Full Database Backup to Restore the Database</span></span>  
 <span data-ttu-id="307a7-136">Es posible volver a crear toda la base de datos en un único paso; para ello, restaure la base de datos a partir de una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="307a7-136">You can re-create a whole database in one step by restoring the database from a full database backup to any location.</span></span> <span data-ttu-id="307a7-137">En la copia de seguridad se incluye suficiente información del registro de transacciones como para permitir la recuperación de la base de datos en el punto en que se completó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="307a7-137">Enough of the transaction log is included in the backup to let you recover the database to the time when the backup finished.</span></span> <span data-ttu-id="307a7-138">El estado de la base de datos restaurada será el mismo que el de la base de datos original en el momento en que terminó la copia de seguridad de base de datos, menos algunas transacciones no confirmadas.</span><span class="sxs-lookup"><span data-stu-id="307a7-138">The restored database matches the state of the original database when the database backup finished, minus any uncommitted transactions.</span></span> <span data-ttu-id="307a7-139">Con el modelo de recuperación completa, debe restaurar todas las copias de seguridad de registros de transacciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="307a7-139">Under the full recovery model, you should then restore all subsequent transaction log backups.</span></span> <span data-ttu-id="307a7-140">Una vez recuperada la base de datos, las transacciones no confirmadas se revierten.</span><span class="sxs-lookup"><span data-stu-id="307a7-140">When the database is recovered, uncommitted transactions are rolled back.</span></span>  
  
 <span data-ttu-id="307a7-141">Para obtener más información, vea [Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](complete-database-restores-simple-recovery-model.md) o [Restauraciones de base de datos completas &#40;modelo de recuperación completa&#41;](complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="307a7-141">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="307a7-142">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="307a7-142">Related Tasks</span></span>  
 <span data-ttu-id="307a7-143">**Para crear una copia de seguridad completa de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="307a7-143">**To create a full database backup**</span></span>  
  
-   [<span data-ttu-id="307a7-144">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="307a7-144">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   <span data-ttu-id="307a7-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="307a7-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="307a7-146">**Para programar trabajos de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="307a7-146">**To schedule backup jobs**</span></span>  
  
 [<span data-ttu-id="307a7-147">Usar el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="307a7-147">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="307a7-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="307a7-148">See Also</span></span>  
 <span data-ttu-id="307a7-149">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="307a7-149">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="307a7-150">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="307a7-150">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="307a7-151">Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="307a7-151">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
  
