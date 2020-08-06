---
title: Restauraciones de base de datos completas (modelo de recuperación completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- restoring [SQL Server], database
- full recovery model [SQL Server], performing restores
- log backups [SQL Server[
ms.assetid: 5b4c471c-b972-498e-aba9-92cf7a0ea881
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea6ec9f196acd0a64a0b785024bd6426cd6a5381
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677719"
---
# <a name="complete-database-restores-full-recovery-model"></a><span data-ttu-id="0ce50-102">Restauraciones de base de datos completas (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="0ce50-102">Complete Database Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="0ce50-103">El objetivo de una restauración completa de la base de datos es restaurar toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ce50-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="0ce50-104">Durante el proceso de restauración, la base de datos completa se encuentra sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0ce50-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="0ce50-105">Antes de que ninguna parte de la base de datos esté en línea, se recuperan todos los datos a un punto coherente en el que todas las partes de la base de datos se encuentran en el mismo momento y en el que no existe ninguna transacción sin confirmar.</span><span class="sxs-lookup"><span data-stu-id="0ce50-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="0ce50-106">En el modelo de recuperación completa, después de restaurar la copia o copias de seguridad de los datos, debe restaurar todas las copias de seguridad de registros de transacciones posteriores y, a continuación, recuperar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ce50-106">Under the full recovery model, after you restore your data backup or backups, you must restore all subsequent transaction log backups and then recover the database.</span></span> <span data-ttu-id="0ce50-107">Puede restaurar una base de datos a un *punto de recuperación* específico en una de estas copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="0ce50-107">You can restore a database to a specific *recovery point* within one of these log backups.</span></span> <span data-ttu-id="0ce50-108">El punto de recuperación puede ser una fecha y hora específicas, una transacción marcada o un número de secuencia de registro (LSN).</span><span class="sxs-lookup"><span data-stu-id="0ce50-108">The recovery point can be a specific date and time, a marked transaction, or a log sequence number (LSN).</span></span>  
  
 <span data-ttu-id="0ce50-109">Al restaurar una base de datos, especialmente en el modelo de recuperación completa o el modelo de recuperación optimizado para cargas masivas de registros, debe usar una única secuencia de restauración.</span><span class="sxs-lookup"><span data-stu-id="0ce50-109">When restoring a database, particularly under the full recovery model or bulk-logged recovery model, you should use a single restore sequence.</span></span> <span data-ttu-id="0ce50-110">Una *secuencia de restauración* consta de dos o más operaciones de restauración que mueven datos en una o varias fases de restauración.</span><span class="sxs-lookup"><span data-stu-id="0ce50-110">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ce50-111">Se recomienda no adjuntar ni restaurar bases de datos de orígenes desconocidos o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="0ce50-111">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="0ce50-112">Estas bases de datos pueden contener código malintencionado que podría ejecutar código [!INCLUDE[tsql](../../includes/tsql-md.md)] inesperado o provocar errores debido a la modificación del esquema o de la estructura de la base de datos física.</span><span class="sxs-lookup"><span data-stu-id="0ce50-112">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="0ce50-113">Para usar una base de datos desde un origen desconocido o que no sea de confianza, ejecute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) en la base de datos de un servidor que no sea de producción y examine también el código, como procedimientos almacenados u otro código definido por el usuario, en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ce50-113">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
 <span data-ttu-id="0ce50-114">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="0ce50-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="0ce50-115">Restaurar una base de datos hasta el momento del error</span><span class="sxs-lookup"><span data-stu-id="0ce50-115">Restoring a Database to the Point of Failure</span></span>](#PointOfFailure)  
  
-   [<span data-ttu-id="0ce50-116">Restaurar una base de datos a un punto dentro de una copia de seguridad de registros</span><span class="sxs-lookup"><span data-stu-id="0ce50-116">Restoring a Database to a Point Within a Log Backup</span></span>](#PointWithinBackup)  
  
-   [<span data-ttu-id="0ce50-117">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0ce50-117">Related Tasks</span></span>](#RelatedTasks)  
  
> [!NOTE]  
>  <span data-ttu-id="0ce50-118">Para obtener más información sobre la compatibilidad con las copias de seguridad de versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea la sección "Soporte de compatibilidad" de [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0ce50-118">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="restoring-a-database-to-the-point-of-failure"></a><a name="PointOfFailure"></a> <span data-ttu-id="0ce50-119">Restaurar una base de datos hasta el momento del error</span><span class="sxs-lookup"><span data-stu-id="0ce50-119">Restoring a Database to the Point of Failure</span></span>  
 <span data-ttu-id="0ce50-120">En general, la recuperación de una base de datos hasta el momento del error incluye los siguientes pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="0ce50-120">Typically, recovering a database to the point of failure involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="0ce50-121">Realizar una copia de seguridad del registro de transacciones activo (denominado el final del registro).</span><span class="sxs-lookup"><span data-stu-id="0ce50-121">Back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="0ce50-122">De esta forma se crea una copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0ce50-122">This creates a tail-log backup.</span></span> <span data-ttu-id="0ce50-123">Si el registro de transacciones activo no está disponible, todas las transacciones de esa parte del registro se pierden.</span><span class="sxs-lookup"><span data-stu-id="0ce50-123">If the active transaction log is unavailable, all transactions in that part of the log are lost.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0ce50-124">En el modelo de recuperación optimizado para cargas masivas de registros, realizar la copia de seguridad de un registro que contiene operaciones de registro masivo requiere acceso a todos los archivos de datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ce50-124">Under the bulk-logged recovery model, backing up any log that contains bulk-logged operations requires access to all data files in the database.</span></span> <span data-ttu-id="0ce50-125">Si no se puede tener acceso a los archivos de datos, no se puede realizar una copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="0ce50-125">If the data files cannot be accessed, the transaction log cannot be backed up.</span></span> <span data-ttu-id="0ce50-126">En ese caso, debe repetir manualmente todos los cambios realizados desde la copia de seguridad de registros más reciente.</span><span class="sxs-lookup"><span data-stu-id="0ce50-126">In that case, you have to manually redo all changes that were made since the most recent log backup.</span></span>  
  
     <span data-ttu-id="0ce50-127">Para obtener más información, vea [Copias del final del registro &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0ce50-127">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="0ce50-128">Restaurar la copia de seguridad completa más reciente sin recuperar la base de datos (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="0ce50-128">Restore the most recent full database backup without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
3.  <span data-ttu-id="0ce50-129">Si existen copias de seguridad diferenciales, restaurar la más reciente sin recuperar la base de datos (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="0ce50-129">If differential backups exist, restore the most recent one without recovering the database (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span></span>  
  
     <span data-ttu-id="0ce50-130">Al restaurar la copia de seguridad diferencial más reciente se reduce el número de copias de seguridad de registros que se deben restaurar.</span><span class="sxs-lookup"><span data-stu-id="0ce50-130">Restoring the most recent differential backup reduces the number of log backups that must be restored.</span></span>  
  
4.  <span data-ttu-id="0ce50-131">Restaurar los registros secuencialmente con la opción NORECOVERY, comenzando por la primera copia de seguridad de registros de transacciones creada después de la copia de seguridad que se acaba de restaurar.</span><span class="sxs-lookup"><span data-stu-id="0ce50-131">Starting with the first transaction log backup that was created after the backup you just restored, restore the logs in sequence with NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="0ce50-132">Recuperar la base de datos (RESTORE DATABASE *database_name* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="0ce50-132">Recover the database (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span> <span data-ttu-id="0ce50-133">Como alternativa, este paso se puede combinar con la restauración de la última copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="0ce50-133">Alternatively, this step can be combined with restoring the last log backup.</span></span>  
  
 <span data-ttu-id="0ce50-134">En la siguiente ilustración se muestra esta secuencia de restauración.</span><span class="sxs-lookup"><span data-stu-id="0ce50-134">The following illustration shows this restore sequence.</span></span> <span data-ttu-id="0ce50-135">Después de que se produzca un error (1), se crea una copia del final del registro (2).</span><span class="sxs-lookup"><span data-stu-id="0ce50-135">After a failure occurs (1), a tail-log backup is created (2).</span></span> <span data-ttu-id="0ce50-136">A continuación, la base de datos se restaura al punto del error.</span><span class="sxs-lookup"><span data-stu-id="0ce50-136">Next, the database is restored to the point of the failure.</span></span> <span data-ttu-id="0ce50-137">Esto implica la restauración de una copia de seguridad de la base de datos, de una copia de seguridad diferencial subsiguiente, y de cada copia de seguridad de registros realizada después de la copia de seguridad diferencial, incluida la copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0ce50-137">This involves restoring a database backup, a subsequent differential backup, and every log backup taken after the differential backup, including the tail-log backup.</span></span>  
  
 <span data-ttu-id="0ce50-138">![Completar la restauración de una base de datos hasta que se produjo un error](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Completar la restauración de una base de datos hasta que se produjo un error")</span><span class="sxs-lookup"><span data-stu-id="0ce50-138">![Complete database restore to the time of a failure](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Complete database restore to the time of a failure")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ce50-139">Cuando restaura una copia de seguridad de la base de datos en una instancia de servidor distinta, vea [Copiar bases de datos con Copias de seguridad y restauración](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="0ce50-139">When you restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="0ce50-140">Sintaxis RESTORE de Transact-SQL básica</span><span class="sxs-lookup"><span data-stu-id="0ce50-140">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="0ce50-141">La sintaxis [de](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] básica para la secuencia de restauración en la ilustración anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ce50-141">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for the restore sequence in the preceding illustration is as follows:</span></span>  
  
1.  <span data-ttu-id="0ce50-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="0ce50-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span></span>  
  
2.  <span data-ttu-id="0ce50-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="0ce50-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span></span>  
  
3.  <span data-ttu-id="0ce50-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="0ce50-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span></span>  
  
     <span data-ttu-id="0ce50-145">Repita este paso de restauración del registro para cada copia de seguridad de registros adicional.</span><span class="sxs-lookup"><span data-stu-id="0ce50-145">Repeat this restore-log step for each additional log backup.</span></span>  
  
4.  <span data-ttu-id="0ce50-146">RESTORE DATABASE *database* WITH RECOVERY;</span><span class="sxs-lookup"><span data-stu-id="0ce50-146">RESTORE DATABASE *database* WITH RECOVERY;</span></span>  
  
###  <a name="example-recovering-to-the-point-of-failure-transact-sql"></a><a name="ExampleToPoFTsql"></a> <span data-ttu-id="0ce50-147">Ejemplo: recuperación hasta el momento del error (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0ce50-147">Example: Recovering to the Point of Failure (Transact-SQL)</span></span>  
 <span data-ttu-id="0ce50-148">En el siguiente ejemplo de [!INCLUDE[tsql](../../includes/tsql-md.md)] se muestran las opciones fundamentales en una secuencia de restauración que restaura la base de datos hasta el momento del error.</span><span class="sxs-lookup"><span data-stu-id="0ce50-148">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] example shows the essential options in a restore sequence that restores the database to the point of failure.</span></span> <span data-ttu-id="0ce50-149">En el ejemplo se crea una copia del final del registro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ce50-149">The example creates a tail-log backup of the database.</span></span> <span data-ttu-id="0ce50-150">A continuación, en el ejemplo se restaura una copia de seguridad completa de la base de datos y una copia de seguridad de registros; a continuación; se restaura la copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0ce50-150">Next, the example restores a full database backup and log backup and then restores the tail-log backup.</span></span> <span data-ttu-id="0ce50-151">En el ejemplo, se recupera la base de datos en un último paso independiente.</span><span class="sxs-lookup"><span data-stu-id="0ce50-151">The example recovers the database in a separate, final step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ce50-152">En este ejemplo se usa una copia de seguridad de base de datos y una copia de seguridad de registros que se crea en la sección "Copias de seguridad de la base de datos en el modelo de recuperación completa" de [Copias de seguridad completas de bases de datos &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0ce50-152">This example uses a database backup and log backup that is created in the "Using Database Backups Under the Full Recovery Model" section in [Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span></span> <span data-ttu-id="0ce50-153">Antes de la copia de seguridad de la base de datos, la base de datos de ejemplo de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] se ha configurado para usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="0ce50-153">Before the database backup, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database was set to use the full recovery model.</span></span>  
  
```  
USE master;  
--Create tail-log backup.  
BACKUP LOG AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'    
   WITH NORECOVERY;   
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=1,   
    NORECOVERY;  
  
--Restore the regular log backup (from backup set 2).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=2,   
    NORECOVERY;  
  
--Restore the tail-log backup (from backup set 3).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'  
  WITH FILE=3,   
    NORECOVERY;  
GO  
--recover the database:  
RESTORE DATABASE AdventureWorks2012 WITH RECOVERY;  
GO  
```  
  
##  <a name="restoring-a-database-to-a-point-within-a-log-backup"></a><a name="PointWithinBackup"></a> <span data-ttu-id="0ce50-154">Restaurar bases de datos a un punto de una copia de seguridad de registros</span><span class="sxs-lookup"><span data-stu-id="0ce50-154">Restoring a Database to a Point Within a Log Backup</span></span>  
 <span data-ttu-id="0ce50-155">En el modelo de recuperación completa, una restauración completa de la base de datos se puede recuperar normalmente hasta un momento en el tiempo, una transacción marcada o un LSN de la copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="0ce50-155">Under the full recovery model, a complete database restore can usually be recovered to a point of time, a marked transaction, or an LSN within a log backup.</span></span> <span data-ttu-id="0ce50-156">Sin embargo, en el modelo de recuperación optimizado para cargas masivas de registros, si la copia de seguridad de registros contiene cambios de registros de operaciones masivas, no es posible la recuperación a un momento dado.</span><span class="sxs-lookup"><span data-stu-id="0ce50-156">However, under the bulk-logged recovery model, if the log backup contains bulk-logged changes, point-in-time recovery is not possible.</span></span>  
  
### <a name="sample-point-in-time-restore-scenarios"></a><span data-ttu-id="0ce50-157">Escenarios de ejemplo de restauración en un momento concreto</span><span class="sxs-lookup"><span data-stu-id="0ce50-157">Sample Point-in-Time Restore Scenarios</span></span>  
 <span data-ttu-id="0ce50-158">En este siguiente ejemplo se presupone que usa un sistema de base de datos de gran importancia para el que se crea una copia de seguridad completa diariamente cada medianoche, una copia de seguridad diferencial de la base de datos cada hora, de lunes a sábado, y copias de seguridad del registro de transacciones cada 10 minutos durante el día.</span><span class="sxs-lookup"><span data-stu-id="0ce50-158">The following example assumes a mission-critical database system for which a full database backup is created daily at midnight, a differential database backup is created on the hour, Monday through Saturday, and transaction log backups are created every 10 minutes throughout the day.</span></span> <span data-ttu-id="0ce50-159">Para restaurar la base de datos al estado en que estaba a las 5:19 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-159">To restore the database to the state is was in at 5:19 A.M.</span></span> <span data-ttu-id="0ce50-160">del miércoles, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ce50-160">Wednesday, do the following:</span></span>  
  
1.  <span data-ttu-id="0ce50-161">Restaure la copia de seguridad de la base de datos completa creada la medianoche del martes.</span><span class="sxs-lookup"><span data-stu-id="0ce50-161">Restore the full database backup that was created Tuesday at midnight.</span></span>  
  
2.  <span data-ttu-id="0ce50-162">Restaure la copia de seguridad diferencial de la base de datos que se ha creado a las 5:00.</span><span class="sxs-lookup"><span data-stu-id="0ce50-162">Restore the differential database backup that was created at 5:00 A.M.</span></span> <span data-ttu-id="0ce50-163">del miércoles.</span><span class="sxs-lookup"><span data-stu-id="0ce50-163">on Wednesday.</span></span>  
  
3.  <span data-ttu-id="0ce50-164">Aplique la copia de seguridad del registro de transacciones que se ha creado a las 5:10.</span><span class="sxs-lookup"><span data-stu-id="0ce50-164">Apply the transaction log backup that was created at 5:10 A.M.</span></span> <span data-ttu-id="0ce50-165">del miércoles.</span><span class="sxs-lookup"><span data-stu-id="0ce50-165">on Wednesday.</span></span>  
  
4.  <span data-ttu-id="0ce50-166">Aplique la copia de seguridad del registro de transacciones creada a las 5:20 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-166">Apply the transaction log backup that was created 5:20 A.M.</span></span> <span data-ttu-id="0ce50-167">del miércoles y especifique que el proceso de recuperación solo se aplique a las transacciones realizadas antes de las 5:19 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-167">on Wednesday, specifying that the recovery process applies only to transactions that occurred before 5:19 A.M.</span></span>  
  
 <span data-ttu-id="0ce50-168">O bien, si la base de datos tiene que restaurarse a su estado de las 3:04 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-168">Alternatively, if the database needs to be restored to its state at 3:04 A.M.</span></span> <span data-ttu-id="0ce50-169">del jueves, pero la copia de seguridad diferencial de la base de datos que se creó el jueves a las 3:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-169">Thursday, but the differential database backup that was created at 3:00 A.M.</span></span> <span data-ttu-id="0ce50-170">no está disponible, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ce50-170">Thursday is unavailable, do the following:</span></span>  
  
1.  <span data-ttu-id="0ce50-171">Restaure la copia de seguridad de la base de datos creada la medianoche del miércoles.</span><span class="sxs-lookup"><span data-stu-id="0ce50-171">Restore the database backup that was created Wednesday at midnight.</span></span>  
  
2.  <span data-ttu-id="0ce50-172">Restaure la copia de seguridad diferencial de la base de datos creada a las 2:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-172">Restore the differential database backup that was created at 2:00 A.M.</span></span> <span data-ttu-id="0ce50-173">del jueves.</span><span class="sxs-lookup"><span data-stu-id="0ce50-173">on Thursday.</span></span>  
  
3.  <span data-ttu-id="0ce50-174">Aplique todas las copias de seguridad del registro de transacciones creadas desde las 2:10 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-174">Apply all the transaction log backups created from 2:10 A.M.</span></span> <span data-ttu-id="0ce50-175">a las 3:00.</span><span class="sxs-lookup"><span data-stu-id="0ce50-175">to 3:00 A.M.</span></span> <span data-ttu-id="0ce50-176">del jueves.</span><span class="sxs-lookup"><span data-stu-id="0ce50-176">on Thursday.</span></span>  
  
4.  <span data-ttu-id="0ce50-177">Aplique la copia de seguridad del registro de transacciones creada a las 3:10 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-177">Apply the transaction log backup that was created at 3:10 A.M.</span></span> <span data-ttu-id="0ce50-178">del jueves y detenga el proceso de recuperación a las 3:04 a.m.</span><span class="sxs-lookup"><span data-stu-id="0ce50-178">on Thursday, stopping the recovery process at 3:04 A.M.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ce50-179">Para obtener un ejemplo de una restauración a un momento dado, vea [Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="0ce50-179">For an example of a point-in-time restore, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0ce50-180">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0ce50-180">Related Tasks</span></span>  
 <span data-ttu-id="0ce50-181">**Para restaurar una copia de seguridad completa de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="0ce50-181">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="0ce50-182">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-182">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="0ce50-183">Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-183">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="0ce50-184">**Para restaurar una copia de seguridad diferencial de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="0ce50-184">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="0ce50-185">Restaurar una copia de seguridad diferencial de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-185">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="0ce50-186">**Para restaurar una copia de seguridad del registro de transacciones**</span><span class="sxs-lookup"><span data-stu-id="0ce50-186">**To restore a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="0ce50-187">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-187">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="0ce50-188">**Para restaurar una copia de seguridad mediante los objetos de administración de SQL Server (SMO)**</span><span class="sxs-lookup"><span data-stu-id="0ce50-188">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
 <span data-ttu-id="0ce50-189">**Para restaurar bases de datos a un punto de una copia de seguridad de registros**</span><span class="sxs-lookup"><span data-stu-id="0ce50-189">**To restore a database to a point within a log backup**</span></span>  
  
-   [<span data-ttu-id="0ce50-190">Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-190">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="0ce50-191">Recuperación de bases de datos relacionadas que contienen transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="0ce50-191">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="0ce50-192">Recuperar a un número de secuencia de registro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-192">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ce50-193">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ce50-193">See Also</span></span>  
 <span data-ttu-id="0ce50-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ce50-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="0ce50-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ce50-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="0ce50-196">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ce50-196">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="0ce50-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ce50-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="0ce50-198">[Copias de seguridad completas de bases de datos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ce50-198">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="0ce50-199">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ce50-199">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="0ce50-200">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ce50-200">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="0ce50-201">Información general sobre restauración y recuperación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce50-201">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
