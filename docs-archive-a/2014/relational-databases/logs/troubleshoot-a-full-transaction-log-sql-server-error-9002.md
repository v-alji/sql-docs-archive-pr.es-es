---
title: Solucionar problemas de un registro de transacciones lleno (Error 9002 de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], full
- troubleshooting [SQL Server], full transaction log
- 9002 (Database Engine error)
- transaction logs [SQL Server], truncation
- backing up transaction logs [SQL Server], full logs
- transaction logs [SQL Server], full log
- full transaction logs [SQL Server]
ms.assetid: 0f23aa84-475d-40df-bed3-c923f8c1b520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d03e259bd0aff8fce02558dbe08efb56748493c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662901"
---
# <a name="troubleshoot-a-full-transaction-log-sql-server-error-9002"></a><span data-ttu-id="ed584-102">Solucionar problemas de un registro de transacciones lleno (Error 9002 de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ed584-102">Troubleshoot a Full Transaction Log (SQL Server Error 9002)</span></span>
  <span data-ttu-id="ed584-103">En este tema se tratan las posibles respuestas a un registro de transacciones lleno y se sugiere cómo evitar esta situación en el futuro.</span><span class="sxs-lookup"><span data-stu-id="ed584-103">This topic discusses possible responses to a full transaction log and suggests how to avoid it in the future.</span></span> <span data-ttu-id="ed584-104">Cuando el registro de transacciones se llena, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] genera un error 9002.</span><span class="sxs-lookup"><span data-stu-id="ed584-104">When the transaction log becomes full, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] issues a 9002 error.</span></span> <span data-ttu-id="ed584-105">El registro se puede llenar cuando la base de datos está en línea o en recuperación.</span><span class="sxs-lookup"><span data-stu-id="ed584-105">The log can fill when the database is online or in recovery.</span></span> <span data-ttu-id="ed584-106">Si el registro se llena mientras la base de datos está en línea, la base de datos permanece en línea, pero solo se puede leer, no se puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="ed584-106">If the log fills while the database is online, the database remains online but can only be read, not updated.</span></span> <span data-ttu-id="ed584-107">Si el registro se llena durante la recuperación, [!INCLUDE[ssDE](../../includes/ssde-md.md)] marca la base de datos como RESOURCE PENDING.</span><span class="sxs-lookup"><span data-stu-id="ed584-107">If the log fills during recovery, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] marks the database as RESOURCE PENDING.</span></span> <span data-ttu-id="ed584-108">En ambos casos, es necesaria la intervención del usuario para proporcionar espacio de registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-108">In either case, user action is required to make log space available.</span></span>  
  
## <a name="responding-to-a-full-transaction-log"></a><span data-ttu-id="ed584-109">Respuesta a un registro de transacciones lleno</span><span class="sxs-lookup"><span data-stu-id="ed584-109">Responding to a Full Transaction Log</span></span>  
 <span data-ttu-id="ed584-110">La respuesta apropiada a un registro de transacciones lleno depende en parte de la condición o condiciones que han causado que el registro se llene.</span><span class="sxs-lookup"><span data-stu-id="ed584-110">The appropriate response to a full transaction log depends partly on what condition or conditions caused the log to fill.</span></span> <span data-ttu-id="ed584-111">Para descubrir qué impide el truncamiento del registro en un caso determinado, use las columnas **log_reuse_wait** y **log_reuse_wait_desc** de la vista de catálogo **sys.database**.</span><span class="sxs-lookup"><span data-stu-id="ed584-111">To discover what is preventing log truncation in a given case, use the **log_reuse_wait** and **log_reuse_wait_desc** columns of the **sys.database** catalog view.</span></span> <span data-ttu-id="ed584-112">Para obtener más información, vea [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed584-112">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span> <span data-ttu-id="ed584-113">Para obtener la descripción de los factores que pueden retrasar el truncamiento del registro, vea [Registro de transacciones &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ed584-113">For descriptions of factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed584-114">Si la base de datos estaba en recuperación cuando se produjo el error 9002, una vez resuelto el problema, recupere la base de datos mediante ALTER DATABASE *nombre_de_base_de_datos* SET ONLINE.</span><span class="sxs-lookup"><span data-stu-id="ed584-114">If the database was in recovery when the 9002 error occurred, after resolving the problem, recover the database by using ALTER DATABASE *database_name* SET ONLINE.</span></span>  
  
 <span data-ttu-id="ed584-115">Las alternativas de respuesta ante un registro de transacciones lleno incluyen:</span><span class="sxs-lookup"><span data-stu-id="ed584-115">Alternatives for responding to a full transaction log include:</span></span>  
  
-   <span data-ttu-id="ed584-116">Realizar copias de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-116">Backing up the log.</span></span>  
  
-   <span data-ttu-id="ed584-117">Liberar espacio en disco para que el registro pueda crecer automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ed584-117">Freeing disk space so that the log can automatically grow.</span></span>  
  
-   <span data-ttu-id="ed584-118">Mover el archivo de registro a una unidad de disco con suficiente espacio.</span><span class="sxs-lookup"><span data-stu-id="ed584-118">Moving the log file to a disk drive with sufficient space.</span></span>  
  
-   <span data-ttu-id="ed584-119">Aumentar el tamaño de un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-119">Increasing the size of a log file.</span></span>  
  
-   <span data-ttu-id="ed584-120">Agregar un archivo de registro en un disco diferente.</span><span class="sxs-lookup"><span data-stu-id="ed584-120">Adding a log file on a different disk.</span></span>  
  
-   <span data-ttu-id="ed584-121">Terminar o eliminar una transacción de larga duración.</span><span class="sxs-lookup"><span data-stu-id="ed584-121">Completing or killing a long-running transaction.</span></span>  
  
 <span data-ttu-id="ed584-122">Estas alternativas se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ed584-122">These alternatives are discussed in the following sections.</span></span> <span data-ttu-id="ed584-123">Elija la respuesta más apropiada para la situación.</span><span class="sxs-lookup"><span data-stu-id="ed584-123">Choose a response that fits your situation best.</span></span>  
  
### <a name="backing-up-the-log"></a><span data-ttu-id="ed584-124">Realizar copias de seguridad del registro</span><span class="sxs-lookup"><span data-stu-id="ed584-124">Backing up the Log</span></span>  
 <span data-ttu-id="ed584-125">En el modelo de recuperación completa o en el optimizado para cargas masivas de registros, si no se ha realizado recientemente ninguna copia de seguridad del registro de transacciones, puede que la copia de seguridad sea la que evita el truncamiento del registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-125">Under the full recovery model or bulk-logged recovery model, if the transaction log has not been backed up recently, backup might be what is preventing log truncation.</span></span> <span data-ttu-id="ed584-126">Si nunca se ha realizado una copia de seguridad del registro, debe crear dos copias de seguridad de registros para que [!INCLUDE[ssDE](../../includes/ssde-md.md)] pueda truncar el registro en el punto de la última copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ed584-126">If the log has never been backed up, you must create two log backups to permit the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to truncate the log to the point of the last backup.</span></span> <span data-ttu-id="ed584-127">El truncamiento del registro libera espacio para nuevas entradas del registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-127">Truncating the log frees space for new log records.</span></span> <span data-ttu-id="ed584-128">Para evitar que el registro se vuelva a llenar, realice copias de seguridad con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="ed584-128">To keep the log from filling up again, take log backups frequently.</span></span>  
  
 <span data-ttu-id="ed584-129">**Para crear una copia de seguridad del registro de transacciones**</span><span class="sxs-lookup"><span data-stu-id="ed584-129">**To create a transaction log backup**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed584-130">Si la base de datos está dañada, vea [Copias del final del registro &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ed584-130">If the database is damaged, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="ed584-131">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed584-131">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="ed584-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="ed584-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
### <a name="freeing-disk-space"></a><span data-ttu-id="ed584-133">Liberar espacio en disco</span><span class="sxs-lookup"><span data-stu-id="ed584-133">Freeing Disk Space</span></span>  
 <span data-ttu-id="ed584-134">Puede liberar espacio en la unidad de disco que contiene el archivo de registro de transacciones de la base de datos eliminando o desplazando otros archivos.</span><span class="sxs-lookup"><span data-stu-id="ed584-134">You might be able to free disk space on the disk drive that contains the transaction log file for the database by deleting or moving other files.</span></span> <span data-ttu-id="ed584-135">La liberación de espacio de disco permite que el sistema de recuperación amplíe automáticamente el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-135">The freed disk space allows the recovery system to enlarge the log file automatically.</span></span>  
  
### <a name="moving-the-log-file-to-a-different-disk"></a><span data-ttu-id="ed584-136">Mover el archivo de registro a otro disco</span><span class="sxs-lookup"><span data-stu-id="ed584-136">Moving the Log File to a Different Disk</span></span>  
 <span data-ttu-id="ed584-137">Si no puede liberar suficiente espacio en la unidad de disco que contiene el archivo de registro, considere la posibilidad de desplazarlo a otra unidad con suficiente espacio.</span><span class="sxs-lookup"><span data-stu-id="ed584-137">If you cannot free enough disk space on the drive that currently contains the log file, consider moving the file to another drive with sufficient space.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed584-138">Los archivos de registro no se deben almacenar en sistemas de archivo comprimidos.</span><span class="sxs-lookup"><span data-stu-id="ed584-138">Log files should never be placed on compressed file systems.</span></span>  
  
 <span data-ttu-id="ed584-139">**Para mover un archivo de registro**</span><span class="sxs-lookup"><span data-stu-id="ed584-139">**To move a log file**</span></span>  
  
-   [<span data-ttu-id="ed584-140">Mover archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="ed584-140">Move Database Files</span></span>](../databases/move-database-files.md)  
  
### <a name="increasing-the-size-of-a-log-file"></a><span data-ttu-id="ed584-141">Aumentar el tamaño de un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="ed584-141">Increasing the Size of a Log File</span></span>  
 <span data-ttu-id="ed584-142">Si hay espacio disponible en el disco del registro, puede aumentar el tamaño del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ed584-142">If space is available on the log disk, you can increase the size of the log file.</span></span> <span data-ttu-id="ed584-143">El tamaño máximo de los archivos de registro es de dos terabytes (TB) por cada archivo.</span><span class="sxs-lookup"><span data-stu-id="ed584-143">The maximum size for log files is two terabytes (TB) per log file.</span></span>  
  
 <span data-ttu-id="ed584-144">**Para aumentar el tamaño de archivo**</span><span class="sxs-lookup"><span data-stu-id="ed584-144">**To increase the file size**</span></span>  
  
 <span data-ttu-id="ed584-145">Si el crecimiento automático está deshabilitado, la base de datos está en línea y hay suficiente espacio en el disco, puede:</span><span class="sxs-lookup"><span data-stu-id="ed584-145">If autogrow is disabled, the database is online, and sufficient space is available on the disk, either:</span></span>  
  
-   <span data-ttu-id="ed584-146">Aumentar manualmente el tamaño del archivo para producir un solo incremento de tamaño.</span><span class="sxs-lookup"><span data-stu-id="ed584-146">Manually increase the file size to produce a single growth increment.</span></span>  
  
-   <span data-ttu-id="ed584-147">Habilitar el crecimiento automático utilizando la instrucción ALTER DATABASE para establecer un incremento de tamaño distinto de cero para la opción FILEGROWTH.</span><span class="sxs-lookup"><span data-stu-id="ed584-147">Turn on autogrow by using the ALTER DATABASE statement to set a non-zero growth increment for the FILEGROWTH option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed584-148">En cualquier caso, si se ha alcanzado el límite del tamaño actual, aumente el valor MAXSIZE.</span><span class="sxs-lookup"><span data-stu-id="ed584-148">In either case, if the current size limit has been reached, increase the MAXSIZE value.</span></span>  
  
### <a name="adding-a-log-file-on-a-different-disk"></a><span data-ttu-id="ed584-149">Agregar un archivo de registro en otro disco</span><span class="sxs-lookup"><span data-stu-id="ed584-149">Adding a Log File on a Different Disk</span></span>  
 <span data-ttu-id="ed584-150">Agregue un nuevo archivo de registro a la base de datos en otro disco que tenga suficiente espacio mediante ALTER DATABASE <nombreDeBaseDeDatos> ADD LOG FILE.</span><span class="sxs-lookup"><span data-stu-id="ed584-150">Add a new log file to the database on a different disk that has sufficient space by using ALTER DATABASE <database_name> ADD LOG FILE.</span></span>  
  
 <span data-ttu-id="ed584-151">**Para agregar un archivo de registro**</span><span class="sxs-lookup"><span data-stu-id="ed584-151">**To add a log file**</span></span>  
  
-   [<span data-ttu-id="ed584-152">Agregar archivos de datos o de registro a una base de datos</span><span class="sxs-lookup"><span data-stu-id="ed584-152">Add Data or Log Files to a Database</span></span>](../databases/add-data-or-log-files-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed584-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed584-153">See Also</span></span>  
 <span data-ttu-id="ed584-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed584-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="ed584-155">[Administrar el tamaño del archivo de registro de transacciones](manage-the-size-of-the-transaction-log-file.md) </span><span class="sxs-lookup"><span data-stu-id="ed584-155">[Manage the Size of the Transaction Log File](manage-the-size-of-the-transaction-log-file.md) </span></span>  
 <span data-ttu-id="ed584-156">[Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed584-156">[Transaction Log Backups &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="ed584-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed584-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-log-file-recover-suspect-db-transact-sql)  
  
  
