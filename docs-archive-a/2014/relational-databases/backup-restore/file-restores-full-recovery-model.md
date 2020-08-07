---
title: Restauraciones de archivos (modelo de recuperación completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- full recovery model [SQL Server], performing restores
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- file restores [SQL Server], full recovery model
- restoring files [SQL Server], full recovery model
- Transact-SQL restore sequence
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: d2236a2a-4cf1-4c3f-b542-f73f6096e15c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 488515ec900867f13d33580402e36a3f98747bb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745839"
---
# <a name="file-restores-full-recovery-model"></a><span data-ttu-id="de059-102">Restauraciones de archivos (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="de059-102">File Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="de059-103">Este tema solo es pertinente para las bases de datos que contienen varios archivos o grupos de archivos con el modelo de recuperación completa o de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="de059-103">This topic is relevant only for databases that contain multiple files or filegroups under the full or bulk-load recovery model.</span></span>  
  
 <span data-ttu-id="de059-104">El objetivo de una restauración de archivos consiste en restaurar uno o varios archivos dañados sin necesidad de restaurar la totalidad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de059-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="de059-105">Un escenario de restauración de archivos consiste en una única secuencia de restauración que copia, pone al día y recupera los datos apropiados.</span><span class="sxs-lookup"><span data-stu-id="de059-105">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data</span></span>  
  
 <span data-ttu-id="de059-106">Si el grupo de archivos que se restaura es de lectura/escritura, es necesario aplicar una cadena ininterrumpida de copias de seguridad de registros después de que se restaure la última copia de seguridad de datos o diferencial.</span><span class="sxs-lookup"><span data-stu-id="de059-106">If the filegroup that is being restored is read/write, an unbroken chain of log backups must be applied after the last data or differential backup is restored.</span></span> <span data-ttu-id="de059-107">De esta forma, el grupo de archivos se actualiza a los registros existentes en los registros activos actuales del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="de059-107">This brings the filegroup forward to the log records in the current active log records in the log file.</span></span> <span data-ttu-id="de059-108">Normalmente, el punto de recuperación está cerca del final del registro, aunque no necesariamente.</span><span class="sxs-lookup"><span data-stu-id="de059-108">The recovery point is typically near the end of log, but not necessarily.</span></span>  
  
 <span data-ttu-id="de059-109">Si el grupo de archivos que se restaura es de solo lectura, por lo general, la aplicación de las copias de seguridad de registros no es necesaria y se omitirá.</span><span class="sxs-lookup"><span data-stu-id="de059-109">If the filegroup that is being restored is read-only, usually applying log backups is unnecessary and is skipped.</span></span> <span data-ttu-id="de059-110">Si se hizo la copia de seguridad después de que el archivo pasará a ser de solo lectura, será la última copia de seguridad que se restaurará.</span><span class="sxs-lookup"><span data-stu-id="de059-110">If the backup was taken after the file became read-only, that is the last backup to restore.</span></span> <span data-ttu-id="de059-111">La puesta al día se detiene en el punto de destino.</span><span class="sxs-lookup"><span data-stu-id="de059-111">Roll forward stops at the target point.</span></span>  
  
 <span data-ttu-id="de059-112">Los escenarios de restauración de archivos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="de059-112">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="de059-113">Restauración de archivos sin conexión</span><span class="sxs-lookup"><span data-stu-id="de059-113">Offline file restore</span></span>  
  
     <span data-ttu-id="de059-114">En una *restauración de archivos sin conexión*, la base de datos permanece sin conexión mientras se restauran los archivos o grupos de archivos dañados.</span><span class="sxs-lookup"><span data-stu-id="de059-114">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="de059-115">Al final de la secuencia de restauración, la base de datos pasará a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="de059-115">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="de059-116">Todas las ediciones de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] admiten restauraciones de archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="de059-116">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="de059-117">Restauración de archivos en línea</span><span class="sxs-lookup"><span data-stu-id="de059-117">Online file restore</span></span>  
  
     <span data-ttu-id="de059-118">En *restauración de archivos en línea*, si la base de datos está en línea durante una restauración de archivos, permanecerá en línea durante la restauración de archivos.</span><span class="sxs-lookup"><span data-stu-id="de059-118">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="de059-119">Sin embargo, cada grupo de archivos en el que se restaura un archivo está sin conexión durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="de059-119">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="de059-120">Una vez recuperados todos los archivos de un grupo de archivos sin conexión, este se conecta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="de059-120">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="de059-121">Para más información sobre la restauración con conexión de archivos y páginas, vea [Características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="de059-121">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="de059-122">Para obtener más información sobre la restauración con conexión, vea [Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="de059-122">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="de059-123">Si quiere que la base de datos esté sin conexión durante una restauración de archivos, deje sin conexión la base de datos antes de iniciar la secuencia de restauración mediante la ejecución de la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) siguiente: ALTER DATABASE *nombre_base_de_datos* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="de059-123">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  
  
  
##  <a name="restoring-damaged-files-from-file-backups"></a><a name="Overview"></a> <span data-ttu-id="de059-124">Restaurar archivos dañados a partir de copias de seguridad de archivo</span><span class="sxs-lookup"><span data-stu-id="de059-124">Restoring Damaged Files from File Backups</span></span>  
  
1.  <span data-ttu-id="de059-125">Antes de restaurar uno o varios archivos dañados, intente crear una [copia del final del registro](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="de059-125">Before restoring one or more damaged files, attempt to create a [tail-log backup](tail-log-backups-sql-server.md).</span></span>  
  
     <span data-ttu-id="de059-126">Si se ha dañado el registro, no se puede crear una copia del final del registro y se debe restaurar toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de059-126">If the log has been damaged, a tail-log backup cannot be created, and you must restore the whole database.</span></span>  
  
     <span data-ttu-id="de059-127">Para obtener más información sobre cómo hacer una copia de seguridad de un registro de transacciones, vea [Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="de059-127">For information about how to back up a transaction log, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="de059-128">En restauraciones de archivos sin conexión, siempre debe realizar una copia del final de registros después del error antes de la restauración de archivos.</span><span class="sxs-lookup"><span data-stu-id="de059-128">For an offline file restore, you must always take a tail-log backup before the file restore.</span></span> <span data-ttu-id="de059-129">En restauraciones de archivos en línea, siempre debe realizar la copia de seguridad de registros después de la restauración de archivos.</span><span class="sxs-lookup"><span data-stu-id="de059-129">For an online file restore, you must always take the log backup after the file restore.</span></span> <span data-ttu-id="de059-130">Esta copia de seguridad de registros es necesaria para que el archivo pueda recuperarse a un estado coherente con el resto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de059-130">This log backup is necessary to allow for the file to be recovered to a state consistent with the rest of the database.</span></span>  
  
2.  <span data-ttu-id="de059-131">Restaure cada archivo dañado a partir de la copia de seguridad más reciente de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="de059-131">Restore each damaged file from the most recent file backup of that file.</span></span>  
  
3.  <span data-ttu-id="de059-132">Restaure la copia de seguridad diferencial de archivos más reciente, si existe, para cada archivo restaurado.</span><span class="sxs-lookup"><span data-stu-id="de059-132">Restore the most recent differential file backup, if any, for each restored file.</span></span>  
  
4.  <span data-ttu-id="de059-133">Restaure las copias de seguridad del registro de transacciones en orden, comenzando con la copia de seguridad que abarca el más antiguo de los archivos restaurados y finalizando con la copia del final del registro después del error creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="de059-133">Restore transaction log backups in sequence, starting with the backup that covers the oldest of the restored files and ending with the tail-log backup created in step 1.</span></span>  
  
     <span data-ttu-id="de059-134">Debe hacer que la base de datos sea coherente; para ello, restaure las copias de seguridad del registro de transacciones creadas después de las copias de seguridad de archivos.</span><span class="sxs-lookup"><span data-stu-id="de059-134">You must restore the transaction log backups that were created after the file backups to bring the database to a consistent state.</span></span> <span data-ttu-id="de059-135">Las copias de seguridad del registro de transacciones se pueden poner al día rápidamente, porque solo se aplican los cambios correspondientes a los archivos restaurados.</span><span class="sxs-lookup"><span data-stu-id="de059-135">The transaction log backups can be rolled forward quickly, because only the changes that apply to the restored files are applied.</span></span> <span data-ttu-id="de059-136">La restauración de archivos individuales puede ser mejor que la restauración de toda la base de datos, dado que los archivos dañados no se copian y, posteriormente, ponen al día.</span><span class="sxs-lookup"><span data-stu-id="de059-136">Restoring individual files can be better than restoring the whole database, because undamaged files are not copied and then rolled forward.</span></span> <span data-ttu-id="de059-137">Sin embargo, aún debe leerse toda la cadena de copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="de059-137">However, the whole chain of log backups still has to be read.</span></span>  
  
5.  <span data-ttu-id="de059-138">Recupere la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de059-138">Recover the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de059-139">Las copias de seguridad de archivos se pueden utilizar para restaurar la base de datos a un momento anterior.</span><span class="sxs-lookup"><span data-stu-id="de059-139">File backups can be used to restore the database to an earlier point in time.</span></span> <span data-ttu-id="de059-140">Para ello, debe restaurar un conjunto completo de copias de seguridad de archivos y, a continuación, restaurar las copias de seguridad del registro de transacciones en orden hasta llegar al momento específico establecido, que es después del final de la copia de seguridad de archivos restaurada más reciente.</span><span class="sxs-lookup"><span data-stu-id="de059-140">To do this, you must restore a complete set of file backups, and then restore transaction log backups in sequence to reach a target point that is after the end of the most recent restored file backup.</span></span> <span data-ttu-id="de059-141">Para obtener más información sobre la recuperación a un momento dado, vea [Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="de059-141">For more information about point-in-time recovery, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
## <a name="transact-sql-restore-sequence-for-an-offline-file-restore-full-recovery-model"></a><span data-ttu-id="de059-142">Secuencia de restauración de Transact-SQL para la restauración de archivos sin conexión (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="de059-142">Transact-SQL Restore Sequence for an Offline File Restore (Full Recovery Model)</span></span>  
 <span data-ttu-id="de059-143">Un escenario de restauración de archivos consiste en una única secuencia de restauración que copia, pone al día y recupera los datos apropiados.</span><span class="sxs-lookup"><span data-stu-id="de059-143">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data.</span></span>  
  
 <span data-ttu-id="de059-144">En esta sección se muestran las opciones esenciales de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para una secuencia de restauración de archivos.</span><span class="sxs-lookup"><span data-stu-id="de059-144">This section shows the essential [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a file-restore sequence.</span></span> <span data-ttu-id="de059-145">La sintaxis y los detalles no pertinentes para este propósito se omiten.</span><span class="sxs-lookup"><span data-stu-id="de059-145">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="de059-146">La secuencia de restauración de ejemplo siguiente muestra una restauración sin conexión de dos archivos secundarios, `A` y `B`, mediante WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="de059-146">The following sample restore sequence shows an offline restore of two secondary files, `A` and `B`, using WITH NORECOVERY.</span></span> <span data-ttu-id="de059-147">A continuación, se aplican dos copias de seguridad de registros con NORECOVERY y, después, la copia del final del registro después del error, recuperada con WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="de059-147">Next, two log backups are applied with NORECOVERY, followed with the tail-log backup, and this is restored using WITH RECOVERY.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de059-148">El siguiente ejemplo de secuencia de restauración se inicia tomando el archivo sin conexión y después crea una copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="de059-148">The following sample restore sequence starts by taking the file offline and then creates a tail-log backup.</span></span>  
  
```  
--Take the file offline.  
ALTER DATABASE database_name MODIFY FILE SET OFFLINE;  
-- Back up the currently active transaction log.  
BACKUP LOG database_name  
   TO <tail_log_backup>  
   WITH NORECOVERY;  
GO   
-- Restore the files.  
RESTORE DATABASE database_name FILE=name   
   FROM <file_backup_of_file_A>   
   WITH NORECOVERY;  
RESTORE DATABASE database_name FILE=<name> ......  
   FROM <file_backup_of_file_B>   
   WITH NORECOVERY;  
-- Restore the log backups.  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <tail_log_backup>   
   WITH RECOVERY;  
```  
  
## <a name="examples"></a><span data-ttu-id="de059-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="de059-149">Examples</span></span>  
  
-   [<span data-ttu-id="de059-150">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="de059-150">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="de059-151">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="de059-151">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="de059-152">Ejemplo: restauración sin conexión del grupo de archivos principal y de otro grupo de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="de059-152">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="de059-153">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="de059-153">Related Tasks</span></span>  
 <span data-ttu-id="de059-154">**Para restaurar archivos y grupos de archivos**</span><span class="sxs-lookup"><span data-stu-id="de059-154">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="de059-155">Restaurar archivos en una nueva ubicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="de059-155">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="de059-156">Restaurar archivos y grupos de archivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="de059-156">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="de059-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="de059-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="de059-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de059-158">See Also</span></span>  
 <span data-ttu-id="de059-159">[Copias de seguridad y restauración: interoperabilidad y coexistencia &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="de059-159">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="de059-160">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="de059-160">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="de059-161">[Copias de seguridad de archivos completas &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="de059-161">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="de059-162">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="de059-162">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="de059-163">[Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="de059-163">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="de059-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de059-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="de059-165">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="de059-165">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="de059-166">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="de059-166">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
