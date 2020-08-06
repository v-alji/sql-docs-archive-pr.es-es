---
title: Aplicar copias de seguridad de registros de transacción (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], log backups
- transaction log backups [SQL Server], applying backups
- online restores [SQL Server], log backups
- transaction log backups [SQL Server], quantity needed for restore sequence
- backups [SQL Server], log backups
ms.assetid: 9b12be51-5469-46f9-8e86-e938e10aa3a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54c91106f8ca6f15539b4103220860143882c3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672136"
---
# <a name="apply-transaction-log-backups-sql-server"></a><span data-ttu-id="0f4c8-102">Aplicar copias de seguridad de registros de transacción (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0f4c8-102">Apply Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="0f4c8-103">Este tema solo es relevante para el modelo de recuperación completa o para el modelo de recuperación optimizado para cargas masivas de registros.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-103">The topic is relevant only for the full recovery model or bulk-logged recovery model.</span></span>  
  
 <span data-ttu-id="0f4c8-104">En este tema se describe la aplicación de copias de seguridad del registro de transacciones como parte de la restauración de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f4c8-104">This topic describes applying transaction log backups as part of restoring a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="0f4c8-105">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="0f4c8-105">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="0f4c8-106">Requisitos para restaurar copias de seguridad de registros de transacciones</span><span class="sxs-lookup"><span data-stu-id="0f4c8-106">Requirements for Restoring Transaction Log Backups</span></span>](#Requirements)  
  
-   [<span data-ttu-id="0f4c8-107">Registros de transacciones y recuperación</span><span class="sxs-lookup"><span data-stu-id="0f4c8-107">Recovery and Transaction Logs</span></span>](#RecoveryAndTlogs)  
  
-   [<span data-ttu-id="0f4c8-108">Usar copias de seguridad de registros para restaurar hasta el momento del error</span><span class="sxs-lookup"><span data-stu-id="0f4c8-108">Using Log Backups to Restore to the Point of Failure</span></span>](#PITrestore)  
  
-   [<span data-ttu-id="0f4c8-109">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0f4c8-109">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="requirements-for-restoring-transaction-log-backups"></a><a name="Requirements"></a><span data-ttu-id="0f4c8-110">Requisitos para restaurar copias de seguridad de registros de transacciones</span><span class="sxs-lookup"><span data-stu-id="0f4c8-110">Requirements for Restoring Transaction Log Backups</span></span>  
 <span data-ttu-id="0f4c8-111">Para aplicar una copia de seguridad del registro de transacciones, deben cumplirse los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f4c8-111">To apply a transaction log backup, the following requirements must be met:</span></span>  
  
-   <span data-ttu-id="0f4c8-112">**Suficientes copias de seguridad de registros para una secuencia de restauración:** Debe tener suficientes copias de seguridad de entradas de registro para poder completar una secuencia de restauración.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-112">**Enough Log Backups for a Restore Sequence :** You must have enough log records backed up to complete a restore sequence.</span></span> <span data-ttu-id="0f4c8-113">Las copias de seguridad de registros necesarias, incluida la [copia del final del registro](tail-log-backups-sql-server.md) si es necesaria, deben estar disponibles antes de iniciar la secuencia de restauración.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-113">The necessary log backups, including the [tail-log backup](tail-log-backups-sql-server.md) where required, must be available before the start of the restore sequence.</span></span>  
  
-   <span data-ttu-id="0f4c8-114">**Orden de restauración correcto:**  Primero debe restaurarse la copia de seguridad diferencial de la base de datos o la copia de seguridad completa inmediatamente anterior de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-114">**Correct restore order:**  The immediately previous full database backup or differential database backup must be restored first.</span></span> <span data-ttu-id="0f4c8-115">A continuación, todos los registros de transacciones creados después de esa copia de seguridad completa o diferencial de la base de datos deben restaurarse en orden cronológico.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-115">Then, all transaction logs that are created after that full or differential database backup must be restored in chronological order.</span></span> <span data-ttu-id="0f4c8-116">Si se pierde o se daña una copia de seguridad del registro de transacciones en esta cadena de registros, solo puede restaurar los registros de transacciones anteriores al registro de transacciones que falta.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-116">If a transaction log backup in this log chain is lost or damaged, you can restore only transaction logs before the missing transaction log.</span></span>  
  
-   <span data-ttu-id="0f4c8-117">**La base de datos no se ha recuperado todavía:**  No se puede recuperar la base de datos hasta que se haya aplicado el registro de transacciones final.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-117">**Database not yet recovered:**  The database cannot be recovered until after the final transaction log has been applied.</span></span> <span data-ttu-id="0f4c8-118">Si recupera la base de datos después de restaurar una de las copias de seguridad intermedias del registro de transacciones, anterior al final de la cadena de registros, no podrá restaurar la base de datos más allá de ese punto sin reiniciar toda la secuencia de restauración, empezando por la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-118">If you recover the database after restoring one of the intermediate transaction log backups, that before the end of the log chain, you cannot restore the database past that point without restarting the complete restore sequence, starting with the full database backup.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="0f4c8-119">Un procedimiento recomendado consiste en restaurar todas las copias de seguridad de registros (RESTORE LOG *nombre_base_de_datos* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="0f4c8-119">A best practice is to restore all the log backups (RESTORE LOG *database_name* WITH NORECOVERY).</span></span> <span data-ttu-id="0f4c8-120">Tras restaurar la última copia de seguridad de registros, recupere la base de datos en una operación aparte (RESTORE DATABASE *nombre_base_de_datos* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="0f4c8-120">Then, after restoring the last log backup, recover the database in a separate operation (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span>  
  
##  <a name="recovery-and-transaction-logs"></a><a name="RecoveryAndTlogs"></a><span data-ttu-id="0f4c8-121">Registros de transacciones y recuperación</span><span class="sxs-lookup"><span data-stu-id="0f4c8-121">Recovery and Transaction Logs</span></span>  
 <span data-ttu-id="0f4c8-122">Cuando termina la operación de restauración y recupera la base de datos, la recuperación revierte todas las transacciones incompletas.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-122">When you finish the restore operation and recover the database, recovery rolls back all incomplete transactions.</span></span> <span data-ttu-id="0f4c8-123">Este paso se conoce como la *fase de deshacer*.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-123">This is known as the *undo phase*.</span></span> <span data-ttu-id="0f4c8-124">Revertir es necesario para restaurar la integridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-124">Rolling back is required to restore the integrity of the database.</span></span> <span data-ttu-id="0f4c8-125">Después de la reversión, la base de datos pasa a estar en línea y no se pueden aplicar más copias de seguridad del registro de transacciones a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-125">After rollback, the database goes online, and no more transaction log backups can be applied to the database.</span></span>  
  
 <span data-ttu-id="0f4c8-126">Por ejemplo, una serie de copias de seguridad del registro de transacciones contiene una transacción de larga duración.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-126">For example, a series of transaction log backups contain a long-running transaction.</span></span> <span data-ttu-id="0f4c8-127">El inicio de la transacción se registra en la primera copia de seguridad del registro de transacciones, pero el final de la transacción se registra en la segunda copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-127">The start of the transaction is recorded in the first transaction log backup, but the end of the transaction is recorded in the second transaction log backup.</span></span> <span data-ttu-id="0f4c8-128">En la primera copia de seguridad del registro de transacciones no se registra ninguna operación de confirmación o reversión.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-128">There is no record of a commit or rollback operation in the first transaction log backup.</span></span> <span data-ttu-id="0f4c8-129">Si se ejecuta una operación de recuperación cuando se aplica la primera copia de seguridad del registro de transacciones, la transacción de larga ejecución se trata como incompleta y se revierten las modificaciones de datos registradas en la primera copia de seguridad del registro de transacciones de la transacción.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-129">If a recovery operation runs when the first transaction log backup is applied, the long-running transaction is treated as incomplete, and data modifications recorded in the first transaction log backup for the transaction are rolled back.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f4c8-130">no permite la aplicación de la segunda copia de seguridad del registro de transacciones a partir de este punto.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-130">does not allow for the second transaction log backup to be applied after this point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f4c8-131">En algunas circunstancias, es posible agregar un archivo explícitamente durante la restauración del registro.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-131">In some circumstances, you can explicitly add a file during log restore.</span></span>  
  
##  <a name="using-log-backups-to-restore-to-the-point-of-failure"></a><a name="PITrestore"></a><span data-ttu-id="0f4c8-132">Usar copias de seguridad de registros para restaurar hasta el momento del error</span><span class="sxs-lookup"><span data-stu-id="0f4c8-132">Using Log Backups to Restore to the Point of Failure</span></span>  
 <span data-ttu-id="0f4c8-133">Suponga el siguiente flujo de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-133">Assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="0f4c8-134">Time</span><span class="sxs-lookup"><span data-stu-id="0f4c8-134">Time</span></span>|<span data-ttu-id="0f4c8-135">Evento</span><span class="sxs-lookup"><span data-stu-id="0f4c8-135">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="0f4c8-136">8:00 a. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-136">8:00 A.M.</span></span>|<span data-ttu-id="0f4c8-137">Copia de seguridad de la base de datos para crear una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-137">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="0f4c8-138">Mediodía</span><span class="sxs-lookup"><span data-stu-id="0f4c8-138">Noon</span></span>|<span data-ttu-id="0f4c8-139">Copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-139">Back up transaction log.</span></span>|  
|<span data-ttu-id="0f4c8-140">4:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-140">4:00 P.M.</span></span>|<span data-ttu-id="0f4c8-141">Copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-141">Back up transaction log.</span></span>|  
|<span data-ttu-id="0f4c8-142">6:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-142">6:00 P.M.</span></span>|<span data-ttu-id="0f4c8-143">Copia de seguridad de la base de datos para crear una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-143">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="0f4c8-144">8:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-144">8:00 P.M.</span></span>|<span data-ttu-id="0f4c8-145">Copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-145">Back up transaction log.</span></span>|  
|<span data-ttu-id="0f4c8-146">9:45 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-146">9:45 P.M.</span></span>|<span data-ttu-id="0f4c8-147">Se produce el error.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-147">Failure occurs.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="0f4c8-148">Para obtener una explicación de este ejemplo de secuencia de copias de seguridad, vea [Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f4c8-148">For an explanation of this example sequence of backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="0f4c8-149">Para restaurar la base de datos a su estado a las 21:45</span><span class="sxs-lookup"><span data-stu-id="0f4c8-149">To restore the database to its state at 9:45 P.M.</span></span> <span data-ttu-id="0f4c8-150">(el punto de error), se puede utilizar cualquiera de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="0f4c8-150">(the point of failure), either of the following alternative procedures can be used:</span></span>  
  
 <span data-ttu-id="0f4c8-151">**Alternativa 1: restaurar la base de datos mediante la copia de seguridad de la base de datos completa más reciente**</span><span class="sxs-lookup"><span data-stu-id="0f4c8-151">**Alternative 1: Restore the database by using the most recent full database backup**</span></span>  
  
1.  <span data-ttu-id="0f4c8-152">Cree una copia del final del registro de transacciones activo actualmente como si fuera el del momento del error.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-152">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="0f4c8-153">No restaure la</span><span class="sxs-lookup"><span data-stu-id="0f4c8-153">Do not restore the 8:00 A.M.</span></span> <span data-ttu-id="0f4c8-154">copia de seguridad completa de base de datos de las 6:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-154">full database backup.</span></span> <span data-ttu-id="0f4c8-155">En su lugar, restaure la copia de seguridad completa de la base de datos de las 6:00 p.m. más reciente</span><span class="sxs-lookup"><span data-stu-id="0f4c8-155">Instead, restore the more recent 6:00 P.M.</span></span> <span data-ttu-id="0f4c8-156">y, a continuación, aplique la copia de seguridad de registros</span><span class="sxs-lookup"><span data-stu-id="0f4c8-156">full database backup, and then apply the 8:00 P.M.</span></span> <span data-ttu-id="0f4c8-157">y la copia del final del registro de las 8:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-157">log backup and the tail-log backup.</span></span>  
  
 <span data-ttu-id="0f4c8-158">**Alternativa 2: restaurar la base de datos mediante una copia de seguridad completa de la base de datos anterior**</span><span class="sxs-lookup"><span data-stu-id="0f4c8-158">**Alternative 2: Restore the database by using an earlier full database backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f4c8-159">Este proceso alternativo resulta útil si un problema impide que se use la</span><span class="sxs-lookup"><span data-stu-id="0f4c8-159">This alternative process is useful if a problem prevents you from using the 6:00 P.M.</span></span> <span data-ttu-id="0f4c8-160">copia de seguridad completa de base de datos de las 6:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-160">full database backup.</span></span> <span data-ttu-id="0f4c8-161">Este proceso lleva más tiempo que restaurar a partir de la</span><span class="sxs-lookup"><span data-stu-id="0f4c8-161">This process takes longer than restoring from the 6:00 P.M.</span></span> <span data-ttu-id="0f4c8-162">copia de seguridad completa de base de datos de las 6:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-162">full database backup.</span></span>  
  
1.  <span data-ttu-id="0f4c8-163">Cree una copia del final del registro de transacciones activo actualmente como si fuera el del momento del error.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-163">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="0f4c8-164">Restaure la</span><span class="sxs-lookup"><span data-stu-id="0f4c8-164">Restore the 8:00 A.M.</span></span> <span data-ttu-id="0f4c8-165">copia de seguridad completa de base de datos de las 8:00 a.m. y, a continuación, restaure secuencialmente las cuatro copias de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-165">full database backup, and then restore all four transaction log backups in sequence.</span></span> <span data-ttu-id="0f4c8-166">Esta acción pone al día todas las transacciones completadas hasta las 9:45 p. m.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-166">This rolls forward all completed transactions up to 9:45 P.M.</span></span>  
  
     <span data-ttu-id="0f4c8-167">Esta alternativa señala la seguridad redundante que ofrece el mantenimiento de una cadena de copias de seguridad del registro de transacciones a través de una serie de copias de seguridad completas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-167">This alternative points out the redundant security offered by maintaining a chain of transaction log backups across a series of full database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f4c8-168">En algunos casos, también se pueden utilizar registros de transacciones para restaurar una base de datos hasta un momento específico.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-168">In some cases, you can also use transaction logs to restore a database to a specific point in time.</span></span> <span data-ttu-id="0f4c8-169">Para obtener más información, vea [Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="0f4c8-169">For more information, [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0f4c8-170">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0f4c8-170">Related Tasks</span></span>  
 <span data-ttu-id="0f4c8-171">**Para aplicar una copia de seguridad del registro de transacciones**</span><span class="sxs-lookup"><span data-stu-id="0f4c8-171">**To apply a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="0f4c8-172">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4c8-172">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="0f4c8-173">**Para restaurar hasta su punto de recuperación**</span><span class="sxs-lookup"><span data-stu-id="0f4c8-173">**To restore to your recovery point**</span></span>  
  
-   [<span data-ttu-id="0f4c8-174">Restaurar una base de datos según el punto de error en el modelo de recuperación completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4c8-174">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="0f4c8-175">Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4c8-175">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   <span data-ttu-id="0f4c8-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="0f4c8-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
-   [<span data-ttu-id="0f4c8-177">Recuperación de bases de datos relacionadas que contienen transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="0f4c8-177">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="0f4c8-178">Recuperar a un número de secuencia de registro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4c8-178">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
 <span data-ttu-id="0f4c8-179">**Para recuperar una base de datos después de restaurar las copias de seguridad mediante WITH NORECOVERY**</span><span class="sxs-lookup"><span data-stu-id="0f4c8-179">**To recover a database after restoring backups using WITH NORECOVERY**</span></span>  
  
-   [<span data-ttu-id="0f4c8-180">Recuperar una base de datos sin restaurar los datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4c8-180">Recover a Database Without Restoring Data &#40;Transact-SQL&#41;</span></span>](recover-a-database-without-restoring-data-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f4c8-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f4c8-181">See Also</span></span>  
 [<span data-ttu-id="0f4c8-182">El registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4c8-182">The Transaction Log &#40;SQL Server&#41;</span></span>](../logs/the-transaction-log-sql-server.md)  
  
  
