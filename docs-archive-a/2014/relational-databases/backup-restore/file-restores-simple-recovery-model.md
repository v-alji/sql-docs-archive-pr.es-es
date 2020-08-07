---
title: Restauraciones de archivos (modelo de recuperación simple) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- simple recovery model [SQL Server]
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- Transact-SQL restore sequence
- restoring files [SQL Server], simple recovery model
- file restores [SQL Server], simple recovery model
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: b6d07386-7c6f-4cc6-be32-93289adbd3d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ed48f48f531e727de5d6e1403ef47f5399f874d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745838"
---
# <a name="file-restores-simple-recovery-model"></a><span data-ttu-id="38711-102">Restauraciones de archivos (modelo de recuperación simple)</span><span class="sxs-lookup"><span data-stu-id="38711-102">File Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="38711-103">Este tema solo es relevante para las bases de datos de modelo simple que incluyen como mínimo un grupo de archivos secundario de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="38711-103">This topic is relevant only for simple-model databases that contain at least one read-only secondary filegroup.</span></span>  
  
 <span data-ttu-id="38711-104">El objetivo de una restauración de archivos consiste en restaurar uno o varios archivos dañados sin necesidad de restaurar la totalidad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="38711-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="38711-105">En el modelo de recuperación simple, las copias de seguridad de archivos se admiten únicamente para los archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="38711-105">Under the simple recovery model, file backups are supported only for read-only files.</span></span> <span data-ttu-id="38711-106">El grupo de archivos primario y los grupos de archivos secundarios de lectura/escritura se restauran siempre juntos, mediante la restauración de una base de datos o de una copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="38711-106">The primary filegroup and read/write secondary filegroups are always restored together, by restoring a database or partial backup.</span></span>  
  
 <span data-ttu-id="38711-107">Los escenarios de restauración de archivos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="38711-107">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="38711-108">Restauración de archivos sin conexión</span><span class="sxs-lookup"><span data-stu-id="38711-108">Offline file restore</span></span>  
  
     <span data-ttu-id="38711-109">En una *restauración de archivos sin conexión*, la base de datos permanece sin conexión mientras se restauran los archivos o grupos de archivos dañados.</span><span class="sxs-lookup"><span data-stu-id="38711-109">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="38711-110">Al final de la secuencia de restauración, la base de datos pasará a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="38711-110">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="38711-111">Todas las ediciones de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] admiten restauraciones de archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="38711-111">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="38711-112">Restauración de archivos en línea</span><span class="sxs-lookup"><span data-stu-id="38711-112">Online file restore</span></span>  
  
     <span data-ttu-id="38711-113">En *restauración de archivos en línea*, si la base de datos está en línea durante una restauración de archivos, permanecerá en línea durante la restauración de archivos.</span><span class="sxs-lookup"><span data-stu-id="38711-113">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="38711-114">Sin embargo, cada grupo de archivos en el que se restaura un archivo está sin conexión durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="38711-114">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="38711-115">Una vez recuperados todos los archivos de un grupo de archivos sin conexión, este se conecta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="38711-115">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="38711-116">Para más información sobre la restauración con conexión de archivos y páginas, vea [Características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="38711-116">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="38711-117">Para obtener más información sobre la restauración con conexión, vea [Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="38711-117">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="38711-118">Si quiere que la base de datos esté sin conexión durante una restauración de archivos, deje sin conexión la base de datos antes de iniciar la secuencia de restauración mediante la ejecución de la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) siguiente: ALTER DATABASE *nombre_base_de_datos* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="38711-118">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  

  
##  <a name="overview-of-file-and-filegroup-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="38711-119">Información general acerca de la restauración de archivos y grupos de archivos con el modelo de recuperación simple</span><span class="sxs-lookup"><span data-stu-id="38711-119">Overview of File and Filegroup Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="38711-120">Un escenario de restauración de archivos está formado por una única secuencia de restauración que copia, pone al día y recupera los datos apropiados de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="38711-120">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data as follows:</span></span>  
  
1.  <span data-ttu-id="38711-121">Restaure cada archivo dañado a partir de su copia de seguridad de archivo más reciente.</span><span class="sxs-lookup"><span data-stu-id="38711-121">Restore each damaged file from its most recent file backup.</span></span>  
  
2.  <span data-ttu-id="38711-122">Restaure la copia de seguridad diferencial de archivos más reciente para cada archivo restaurado y recupere la base de datos.</span><span class="sxs-lookup"><span data-stu-id="38711-122">Restore the most recent differential file backup for each restored file and recover the database.</span></span>  
  
### <a name="transact-sql-steps-for-file-restore-sequence-simple-recovery-model"></a><span data-ttu-id="38711-123">Secuencia de restauración de Transact-SQL para la restauración de archivos (modelo de recuperación simple)</span><span class="sxs-lookup"><span data-stu-id="38711-123">Transact-SQL Steps for File Restore Sequence (Simple Recovery Model)</span></span>  
 <span data-ttu-id="38711-124">Esta sección muestra las opciones fundamentales de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) de [!INCLUDE[tsql](../../../includes/tsql-md.md)] de una secuencia de restauración de archivos simple.</span><span class="sxs-lookup"><span data-stu-id="38711-124">This section shows the essential [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a simple file-restore sequence.</span></span> <span data-ttu-id="38711-125">La sintaxis y los detalles no pertinentes para este propósito se omiten.</span><span class="sxs-lookup"><span data-stu-id="38711-125">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="38711-126">La secuencia de restauración solo contiene dos instrucciones de [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38711-126">The restore sequence contains only two [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="38711-127">La primera instrucción restaura un archivo secundario, el archivo `A`, que se restaura usando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="38711-127">The first statement restores a secondary file, file `A`, which is restored using WITH NORECOVERY.</span></span> <span data-ttu-id="38711-128">La segunda operación restaura otros dos archivos, `B` y `C` , que se restauran usando WITH RECOVERY desde un dispositivo de copia de seguridad diferente:</span><span class="sxs-lookup"><span data-stu-id="38711-128">The second operation restores two other files, `B` and `C` which are restored using WITH RECOVERY from a different backup device:</span></span>  
  
1.  <span data-ttu-id="38711-129">RESTORE DATABASE *base_de_datos* FILE **=** _nombre_de_archivo_A_</span><span class="sxs-lookup"><span data-stu-id="38711-129">RESTORE DATABASE *database* FILE **=**_name_of_file_A_</span></span>  
  
     <span data-ttu-id="38711-130">FROM *copia_de_seguridad_de_archivo_A*</span><span class="sxs-lookup"><span data-stu-id="38711-130">FROM *file_backup_of_file_A*</span></span>  
  
     <span data-ttu-id="38711-131">WITH NORECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="38711-131">WITH NORECOVERY **;**</span></span>  
  
2.  <span data-ttu-id="38711-132">RESTORE DATABASE *base_de_datos* FILE **=** _nombre_de_archivo_B_ **,** _nombre_de_archivo_C_</span><span class="sxs-lookup"><span data-stu-id="38711-132">RESTORE DATABASE *database* FILE **=**_name_of_file_B_**,**_name_of_file_C_</span></span>  
  
     <span data-ttu-id="38711-133">FROM *copia_de_seguridad_de_archivos_B_y_C*</span><span class="sxs-lookup"><span data-stu-id="38711-133">FROM *file_backup_of_files_B_and_C*</span></span>  
  
     <span data-ttu-id="38711-134">WITH RECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="38711-134">WITH RECOVERY **;**</span></span>  
  
### <a name="examples"></a><span data-ttu-id="38711-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="38711-135">Examples</span></span>  
  
-   [<span data-ttu-id="38711-136">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="38711-136">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="38711-137">Ejemplo: restauración sin conexión del grupo de archivos principal y de otro grupo de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="38711-137">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="38711-138">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="38711-138">Related Tasks</span></span>  
 <span data-ttu-id="38711-139">**Para restaurar archivos y grupos de archivos**</span><span class="sxs-lookup"><span data-stu-id="38711-139">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="38711-140">Restaurar archivos y grupos de archivos en archivos existentes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="38711-140">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="38711-141">Restaurar archivos y grupos de archivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="38711-141">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="38711-142">Restaurar archivos y grupos de archivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="38711-142">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="38711-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="38711-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="38711-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38711-144">See Also</span></span>  
 <span data-ttu-id="38711-145">[Copias de seguridad y restauración: interoperabilidad y coexistencia &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38711-145">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="38711-146">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38711-146">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="38711-147">[Copias de seguridad de archivos completas &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38711-147">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="38711-148">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38711-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="38711-149">[Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38711-149">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="38711-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38711-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="38711-151">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="38711-151">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="38711-152">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="38711-152">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
