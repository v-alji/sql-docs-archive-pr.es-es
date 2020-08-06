---
title: Copias del final del registro (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up [SQL Server], tail of log
- transaction log backups [SQL Server], tail-log backups
- NO_TRUNCATE clause
- backups [SQL Server], log backups
- tail-log backups
- backups [SQL Server], tail-log backups
ms.assetid: 313ddaf6-ec54-4a81-a104-7ffa9533ca58
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cd7c505701a4edb1f66ca516d06179b2eb1a222d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663535"
---
# <a name="tail-log-backups-sql-server"></a><span data-ttu-id="0e881-102">Copias del final del registro (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0e881-102">Tail-Log Backups (SQL Server)</span></span>
  <span data-ttu-id="0e881-103">Este tema solamente es pertinente para copias de seguridad y restauración de las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usan el modelo de recuperación optimizado para cargas masivas de registros o el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="0e881-103">This topic is relevant only for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="0e881-104">Una *copia del final del registro* captura las entradas del registro de las que todavía no se ha realizado copia de seguridad (el *final del registro*) para evitar la pérdida de trabajo y mantener intacta la cadena de registros.</span><span class="sxs-lookup"><span data-stu-id="0e881-104">A *tail-log backup* captures any log records that have not yet been backed up (the *tail of the log*) to prevent work loss and to keep the log chain intact.</span></span> <span data-ttu-id="0e881-105">Para poder recuperar una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al último momento, debe realizar una copia del final del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="0e881-105">Before you can recover a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to its latest point in time, you must back up the tail of its transaction log.</span></span> <span data-ttu-id="0e881-106">La copia del final del registro será la copia de seguridad de interés en el plan de recuperación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0e881-106">The tail-log backup will be the last backup of interest in the recovery plan for the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e881-107">No todos los escenarios de restauración requieren una copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0e881-107">Not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="0e881-108">No necesita una copia del final del registro si el punto de recuperación está incluido en una copia de seguridad de registros anterior.</span><span class="sxs-lookup"><span data-stu-id="0e881-108">You do not need a tail-log backup if the recovery point is contained in an earlier log backup.</span></span> <span data-ttu-id="0e881-109">Además, no es necesaria una copia del final del registro si va a mover o reemplazar (sobrescribir) la base de datos y no necesita restaurarla a un momento posterior de la copia de seguridad más reciente.</span><span class="sxs-lookup"><span data-stu-id="0e881-109">Also, a tail-log backup is unnecessary if you are moving or replacing (overwriting) a database and do not need to restore it to a point of time after its most recent backup.</span></span>  
  
 
  
##  <a name="scenarios-that-require-a-tail-log-backup"></a><a name="TailLogScenarios"></a> <span data-ttu-id="0e881-110">Escenarios que requieren una copia del final del registro</span><span class="sxs-lookup"><span data-stu-id="0e881-110">Scenarios That Require a Tail-Log Backup</span></span>  
 <span data-ttu-id="0e881-111">Recomendamos realizar una copia del final del registro en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="0e881-111">We recommend that you take a tail-log backup in the following scenarios:</span></span>  
  
-   <span data-ttu-id="0e881-112">Si la base de datos está en línea y planea realizar una operación de restauración en la base de datos, comience con una copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0e881-112">If the database is online and you plan to perform a restore operation on the database, begin by backing up the tail of the log.</span></span> <span data-ttu-id="0e881-113">Para evitar un error en una base de datos en línea, debe utilizar... WITH NORECOVERY de la instrucción [backup](/sql/t-sql/statements/backup-transact-sql) [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e881-113">To avoid an error for an online database, you must use the ... WITH NORECOVERY option of the [BACKUP](/sql/t-sql/statements/backup-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="0e881-114">Si una base de datos está sin conexión y no puede iniciarse y necesita restaurar la base de datos, primero haga una copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0e881-114">If a database is offline and fails to start and you need to restore the database, first back up the tail of the log.</span></span> <span data-ttu-id="0e881-115">Debido a que no pueden producirse otras transacciones en este momento, el uso de WITH NORECOVERY es opcional.</span><span class="sxs-lookup"><span data-stu-id="0e881-115">Because no transactions can occur at this time, using the WITH NORECOVERY is optional.</span></span>  
  
-   <span data-ttu-id="0e881-116">Si se daña una base de datos, intente hacer una copia del final del registro con la opción WITH CONTINUE_AFTER_ERROR de la instrucción BACKUP.</span><span class="sxs-lookup"><span data-stu-id="0e881-116">If a database is damaged, try to take a tail-log backup by using the WITH CONTINUE_AFTER_ERROR option of the BACKUP statement.</span></span>  
  
     <span data-ttu-id="0e881-117">En una base de datos dañada, la copia del final del registro se puede completar sin errores solo si los archivos de registro no están dañados, si la base de datos tiene un estado que admite copias de seguridad de registros después del error y si la base de datos no contiene cambios registrados de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="0e881-117">On a damaged database backing up the tail of the log can succeed only if the log files are undamaged, the database is in a state that supports tail-log backups, and the database does not contain any bulk-logged changes.</span></span> <span data-ttu-id="0e881-118">Si no se puede crear una copia del final del registro, se pueden las transacciones confirmadas después de la última copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="0e881-118">If a tail-log backup cannot be created, any transactions committed after the latest log backup are lost.</span></span>  
  
 <span data-ttu-id="0e881-119">En la tabla siguiente se resumen las opciones BACKUP NORECOVERY y CONTINUE_AFTER_ERROR.</span><span class="sxs-lookup"><span data-stu-id="0e881-119">The following table summarizes the BACKUP NORECOVERY and CONTINUE_AFTER_ERROR options.</span></span>  
  
|<span data-ttu-id="0e881-120">Opción BACKUP LOG</span><span class="sxs-lookup"><span data-stu-id="0e881-120">BACKUP LOG option</span></span>|<span data-ttu-id="0e881-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e881-121">Comments</span></span>|  
|-----------------------|--------------|  
|<span data-ttu-id="0e881-122">NORECOVERY</span><span class="sxs-lookup"><span data-stu-id="0e881-122">NORECOVERY</span></span>|<span data-ttu-id="0e881-123">Use NORECOVERY cada vez que desee continuar con una operación de restauración en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0e881-123">Use NORECOVERY whenever you intend to continue with a restore operation on the database.</span></span> <span data-ttu-id="0e881-124">NORECOVERY pone la base de datos en el estado de restauración.</span><span class="sxs-lookup"><span data-stu-id="0e881-124">NORECOVERY takes the database into the restoring state.</span></span> <span data-ttu-id="0e881-125">Esto garantiza que la base de datos no cambie después de realizar la copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0e881-125">This guarantees that the database does not change after the tail-log backup.</span></span>  <span data-ttu-id="0e881-126">El registro se trunca a menos que también se especifique la opción NO_TRUNCATE o COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="0e881-126">The log is truncated unless the NO_TRUNCATE option or COPY_ONLY option is also specified.</span></span><br /><br /> <span data-ttu-id="0e881-127">Importante se recomienda evitar el uso de NO_TRUNCATE, excepto cuando la base de datos esté dañada. \*\* \* \* \* \* \*\*</span><span class="sxs-lookup"><span data-stu-id="0e881-127">**\*\* Important \*\*** We recommend that you avoid using NO_TRUNCATE, except when the database is damaged.</span></span>|  
|<span data-ttu-id="0e881-128">CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="0e881-128">CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="0e881-129">Utilice CONTINUE_AFTER_ERROR solo si va a crear una copia del final de una base de datos dañada.</span><span class="sxs-lookup"><span data-stu-id="0e881-129">Use CONTINUE_AFTER_ERROR only if you are backing up the tail of a damaged database.</span></span><br /><br /> <span data-ttu-id="0e881-130">Nota: cuando se usa la copia de seguridad del final del registro en una base de datos dañada, es posible que algunos de los metadatos que se capturan normalmente en copias de seguridad de registros no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="0e881-130">Note: When you use back up the tail of the log on a damaged database, some of the metadata ordinarily captured in log backups might be unavailable.</span></span> <span data-ttu-id="0e881-131">Para obtener más información, vea [Copias del final del registro con metadatos de copia de seguridad incompletos](#IncompleteMetadata), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="0e881-131">For more information, see [Tail-Log Backups That Have Incomplete Backup Metadata](#IncompleteMetadata), later in this topic.</span></span>|  
  
##  <a name="tail-log-backups-that-have-incomplete-backup-metadata"></a><a name="IncompleteMetadata"></a><span data-ttu-id="0e881-132">Copias del final del registro con metadatos de copia de seguridad incompletos</span><span class="sxs-lookup"><span data-stu-id="0e881-132">Tail-Log Backups That Have Incomplete Backup Metadata</span></span>  
 <span data-ttu-id="0e881-133">Las copias de seguridad de registros después del error capturan el final del registro aunque falten archivos en la base de datos, o la base de datos esté sin conexión o dañada.</span><span class="sxs-lookup"><span data-stu-id="0e881-133">Tail log backups capture the tail of the log even if the database is offline, damaged, or missing data files.</span></span> <span data-ttu-id="0e881-134">Sin embargo, esto puede provocar que se obtengan metadatos incompletos de los comandos de información de restauración y **msdb**.</span><span class="sxs-lookup"><span data-stu-id="0e881-134">This might cause incomplete metadata from the restore information commands and **msdb**.</span></span> <span data-ttu-id="0e881-135">Sin embargo, solo los metadatos están incompletos. El registro capturado está completo y en condiciones de uso.</span><span class="sxs-lookup"><span data-stu-id="0e881-135">However, only the metadata is incomplete; the captured log is complete and usable.</span></span>  
  
 <span data-ttu-id="0e881-136">Si una copia del final del registro tiene metadatos incompletos, en la tabla [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) se establece **has_incomplete_metadata** en **1**.</span><span class="sxs-lookup"><span data-stu-id="0e881-136">If a tail-log backup has incomplete metadata, in the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table, **has_incomplete_metadata** is set to **1**.</span></span> <span data-ttu-id="0e881-137">Asimismo, en la salida de [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql), **HasIncompleteMetadata** se establece en **1**.</span><span class="sxs-lookup"><span data-stu-id="0e881-137">Also, in the output of [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql), **HasIncompleteMetadata** is set to **1**.</span></span>  
  
 <span data-ttu-id="0e881-138">Si los metadatos de la copia del final del registro están incompletos, a la tabla [backupfilegroup](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) le faltará la mayoría de la información sobre grupos de archivos en el momento de realizar la copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="0e881-138">If the metadata in a tail-log backup is incomplete, the [backupfilegroup](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) table will be missing most of the information about filegroups at the time of the tail-log backup.</span></span> <span data-ttu-id="0e881-139">La mayoría de las columnas de la tabla **backupfilegroup** son NULL; las únicas columnas significativas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e881-139">Most of the **backupfilegroup** table columns are NULL; the only meaningful columns are as follows:</span></span>  
  
-   <span data-ttu-id="0e881-140">**backup_set_id**</span><span class="sxs-lookup"><span data-stu-id="0e881-140">**backup_set_id**</span></span>  
  
-   <span data-ttu-id="0e881-141">**filegroup_id**</span><span class="sxs-lookup"><span data-stu-id="0e881-141">**filegroup_id**</span></span>  
  
-   <span data-ttu-id="0e881-142">**type**</span><span class="sxs-lookup"><span data-stu-id="0e881-142">**type**</span></span>  
  
-   <span data-ttu-id="0e881-143">**type_desc**</span><span class="sxs-lookup"><span data-stu-id="0e881-143">**type_desc**</span></span>  
  
-   <span data-ttu-id="0e881-144">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="0e881-144">**is_readonly**</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0e881-145">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0e881-145">Related Tasks</span></span>  
 <span data-ttu-id="0e881-146">Para crear una copia del final del registro, vea [Realizar una copia de seguridad del registro de transacciones cuando la base de datos está dañada &#40;SQL Server&#41;](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e881-146">To create a tail-log backup, see [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
 <span data-ttu-id="0e881-147">Para restaurar una copia de seguridad del registro de transacciones, vea [Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e881-147">To restore a transaction log backup, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e881-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e881-148">See Also</span></span>  
 <span data-ttu-id="0e881-149">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e881-149">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="0e881-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e881-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="0e881-151">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="0e881-151">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="0e881-152">[Copias de seguridad de solo copia &#40;SQL Server&#41;](copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e881-152">[Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="0e881-153">[Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e881-153">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="0e881-154">Aplicar copias de seguridad de registros de transacción &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e881-154">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  