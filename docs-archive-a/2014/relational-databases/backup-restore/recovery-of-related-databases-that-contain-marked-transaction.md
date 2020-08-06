---
title: Recuperación de bases de datos relacionadas que contienen transacciones marcadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], marks
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- transactions [SQL Server], recovering to a mark
- database recovery [SQL Server]
- marked transactions [SQL Server], restoring
- database restores [SQL Server], point in time
ms.assetid: 77a0d9c0-978a-4891-8b0d-a4256c81c3f8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b968322f92c7a135adb5fd0733b5774e7562bc39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748142"
---
# <a name="recovery-of-related--databases-that-contain-marked-transaction"></a><span data-ttu-id="ba172-102">Recuperación de bases de datos relacionadas que contienen transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="ba172-102">Recovery of Related  Databases That Contain Marked Transaction</span></span>
  <span data-ttu-id="ba172-103">Este tema solo es pertinente para las bases de datos que contienen transacciones marcadas y utilizan los modelos de recuperación completa u optimizado para cargas masivas de registros.</span><span class="sxs-lookup"><span data-stu-id="ba172-103">This topic is relevant only for databases that contain marked transactions and that use the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="ba172-104">Para obtener información sobre los requisitos para la restauración a un punto de recuperación específico, vea [Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="ba172-104">For information about the requirements for restoring to a specific recovery point, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba172-105">permite insertar marcas con nombre en el registro de transacciones para recuperar hasta esa marca específica.</span><span class="sxs-lookup"><span data-stu-id="ba172-105">supports inserting named marks into the transaction log to allow recovery to that specific mark.</span></span> <span data-ttu-id="ba172-106">Las marcas del registro son específicas de la transacción y se insertan solo si se confirman sus transacciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="ba172-106">Log marks are transaction specific and are inserted only if their associated transaction commits.</span></span> <span data-ttu-id="ba172-107">Como resultado, las marcas se pueden asociar a un trabajo específico y se podrá recuperar hasta un punto que incluya o excluya ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba172-107">As a result, marks can be tied to specific work, and you can recover to a point that includes or excludes this work.</span></span>  
  
 <span data-ttu-id="ba172-108">Antes de insertar marcas con nombre en el registro de transacciones, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba172-108">Before you insert named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="ba172-109">Debido a que las marcas de transacción consumen espacio del registro, utilícelas solo para aquellas transacciones que desempeñen un rol importante en la estrategia de recuperación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-109">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="ba172-110">Después de la confirmación de una transacción marcada, se inserta una fila en la tabla [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) de **msdb**.</span><span class="sxs-lookup"><span data-stu-id="ba172-110">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="ba172-111">Si la transacción marcada abarca varias bases de datos del mismo servidor de base de datos o de diferentes servidores, las marcas se registran en los registros de todas las bases de datos afectadas.</span><span class="sxs-lookup"><span data-stu-id="ba172-111">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span> <span data-ttu-id="ba172-112">Para obtener más información, vea [Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente &#40;modelo de recuperación completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="ba172-112">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba172-113">Para obtener información sobre cómo marcar transacciones, vea [Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente &#40;modelo de recuperación completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="ba172-113">For information about how to mark transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-inserting-named-marks-into-a-transaction-log"></a><span data-ttu-id="ba172-114">Sintaxis de Transact-SQL para insertar marcas con nombre en un registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="ba172-114">Transact-SQL Syntax for Inserting Named Marks into a Transaction Log</span></span>  
 <span data-ttu-id="ba172-115">Para insertar marcas en los registros de transacciones, use la instrucción [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) y la cláusula WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="ba172-115">To insert marks into the transaction logs, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="ba172-116">La marca recibe el mismo nombre que la transacción.</span><span class="sxs-lookup"><span data-stu-id="ba172-116">The mark is named the same as the transaction.</span></span> <span data-ttu-id="ba172-117">La descripción ( *description* ) es opcional y es un texto descriptivo de la marca, no su nombre.</span><span class="sxs-lookup"><span data-stu-id="ba172-117">The optional *description* is a textual description of the mark, not the mark name.</span></span> <span data-ttu-id="ba172-118">Por ejemplo, el nombre de la transacción y de la marca que se crea en la siguiente instrucción `BEGIN TRANSACTION` es `Tx1`:</span><span class="sxs-lookup"><span data-stu-id="ba172-118">For example, the name of both the transaction and the mark that is created in the following `BEGIN TRANSACTION` statement is `Tx1`:</span></span>  
  
```wmimof  
BEGIN TRANSACTION Tx1 WITH MARK 'not the mark name, just a description'    
```  
  
 <span data-ttu-id="ba172-119">El registro de transacciones registra el nombre de la marca (nombre de la transacción), su descripción, la base de datos, el usuario, la información de `datetime` y el número de flujo de registro (LSN).</span><span class="sxs-lookup"><span data-stu-id="ba172-119">The transaction log records the mark name (transaction name), description, database, user, `datetime` information, and the log sequence number (LSN).</span></span> <span data-ttu-id="ba172-120">La información de `datetime` se utiliza con el nombre de la marca para identificar la marca de forma única.</span><span class="sxs-lookup"><span data-stu-id="ba172-120">The `datetime` information is used with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="ba172-121">Para obtener información sobre cómo insertar una marca en una transacción que abarca varias bases de datos, vea [Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente &#40;modelo de recuperación completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="ba172-121">For information about how to insert a mark into a transaction that spans multiple databases, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-recovering-to-a-mark"></a><span data-ttu-id="ba172-122">Sintaxis de Transact-SQL para recuperar hasta una marca</span><span class="sxs-lookup"><span data-stu-id="ba172-122">Transact-SQL Syntax for Recovering to a Mark</span></span>  
 <span data-ttu-id="ba172-123">Si el destino es una transacción marcada con la instrucción[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql), puede usar una de las cláusulas siguientes para detenerse en la marca o inmediatamente antes:</span><span class="sxs-lookup"><span data-stu-id="ba172-123">When you target a marked transaction by using a[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)statement, you can use one the following clauses to stop at or immediately before the mark:</span></span>  
  
-   <span data-ttu-id="ba172-124">Use la cláusula with STOPATMARK = **' *`<mark_name>`* '** para especificar que la transacción marcada es el punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="ba172-124">Use the WITH STOPATMARK = **'*`<mark_name>`*'** clause to specify that the marked transaction is the recovery point.</span></span>  
  
     <span data-ttu-id="ba172-125">STOPATMARK pone al día hasta la marca e incluye la transacción marcada en la puesta al día.</span><span class="sxs-lookup"><span data-stu-id="ba172-125">STOPATMARK rolls forward to the mark and includes the marked transaction in the roll forward.</span></span>  
  
-   <span data-ttu-id="ba172-126">Use la cláusula with STOPBEFOREMARK = **' *`<mark_name>`* '** para especificar que la entrada de registro que está inmediatamente antes de la marca es el punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="ba172-126">Use the WITH STOPBEFOREMARK = **'*`<mark_name>`*'** clause to specify that the log record that is immediately before the mark is the recovery point.</span></span>  
  
     <span data-ttu-id="ba172-127">STOPBEFOREMARK pone al día hasta la marca y excluye la transacción marcada de la puesta al día.</span><span class="sxs-lookup"><span data-stu-id="ba172-127">STOPBEFOREMARK rolls forward to the mark and excludes marked the transaction from the roll forward.</span></span>  
  
 <span data-ttu-id="ba172-128">Las opciones STOPATMARK y STOPBEFOREMARK admiten una cláusula AFTER *datetime* opcional.</span><span class="sxs-lookup"><span data-stu-id="ba172-128">The STOPATMARK and STOPBEFOREMARK options both support an optional AFTER *datetime* clause.</span></span> <span data-ttu-id="ba172-129">Cuando se utiliza *datetime* , no es necesario que los nombres de marca sean únicos.</span><span class="sxs-lookup"><span data-stu-id="ba172-129">When *datetime* is used, mark names do not have to be unique.</span></span>  
  
 <span data-ttu-id="ba172-130">Si se omite AFTER *datetime* , la puesta al día se detiene en la primera marca que tenga el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ba172-130">If AFTER *datetime* is omitted, roll forward stops at the first mark that has the specified name.</span></span> <span data-ttu-id="ba172-131">Si se especifica AFTER *datetime* , la puesta al día se detiene en la primera marca que tenga el nombre especificado, ya sea en *datetime*o después.</span><span class="sxs-lookup"><span data-stu-id="ba172-131">If AFTER *datetime* is specified, roll forward stops at the first mark that has the specified name, exactly at or after *datetime*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba172-132">Al igual que en las operaciones de restauración a un momento dado, la recuperación hasta una marca no está permitida cuando la base de datos está realizando operaciones de registro masivo.</span><span class="sxs-lookup"><span data-stu-id="ba172-132">As in all point-in-time restore operations, recovering to a mark is disallowed when the database is undergoing operations that are bulk-logged.</span></span>  
  
 <span data-ttu-id="ba172-133">**Para restaurar una transacción marcada**</span><span class="sxs-lookup"><span data-stu-id="ba172-133">**To restore to a marked transaction**</span></span>  
  
 [<span data-ttu-id="ba172-134">Restaurar una base de datos en una transacción marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ba172-134">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
 [<span data-ttu-id="ba172-135">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba172-135">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
### <a name="preparing-the-log-backups"></a><span data-ttu-id="ba172-136">Preparar las copias de seguridad de registros</span><span class="sxs-lookup"><span data-stu-id="ba172-136">Preparing the Log Backups</span></span>  
 <span data-ttu-id="ba172-137">En este ejemplo, una estrategia correcta de copia de seguridad para estas bases de datos relacionadas sería:</span><span class="sxs-lookup"><span data-stu-id="ba172-137">For this example, an appropriate backup strategy for these related databases would be the following:</span></span>  
  
1.  <span data-ttu-id="ba172-138">Utilizar el modelo de recuperación completa para ambas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-138">Use the full recovery model for both databases.</span></span>  
  
2.  <span data-ttu-id="ba172-139">Crear una copia de seguridad completa de cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-139">Create a full backup of each database.</span></span>  
  
     <span data-ttu-id="ba172-140">La copia de seguridad de las bases de datos se puede realizar de forma secuencial o simultánea.</span><span class="sxs-lookup"><span data-stu-id="ba172-140">The databases can be backed up sequentially or simultaneously.</span></span>  
  
3.  <span data-ttu-id="ba172-141">Antes de realizar la copia de seguridad del registro de transacciones, marque una transacción que se ejecute en todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-141">Before backing up the transaction log, mark a transaction that executes in all databases.</span></span> <span data-ttu-id="ba172-142">Para obtener información sobre cómo crear transacciones marcadas, vea [Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente &#40;modelo de recuperación completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="ba172-142">For information about how to create the marked transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
4.  <span data-ttu-id="ba172-143">Realizar una copia de seguridad del registro de transacciones en ambas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-143">Back up the transaction log on each database.</span></span>  
  
### <a name="recovering-the-database-to-a-marked-transaction"></a><span data-ttu-id="ba172-144">Recuperar la base de datos a una transacción marcada</span><span class="sxs-lookup"><span data-stu-id="ba172-144">Recovering the Database to a Marked Transaction</span></span>  
 <span data-ttu-id="ba172-145">**Para restaurar la copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="ba172-145">**To restore the backup**</span></span>  
  
1.  <span data-ttu-id="ba172-146">Cree [copias de seguridad del final del registro](tail-log-backups-sql-server.md) de las bases de datos no dañadas, si es posible.</span><span class="sxs-lookup"><span data-stu-id="ba172-146">Create [tail-log backups](tail-log-backups-sql-server.md) of the undamaged databases, if possible.</span></span>  
  
2.  <span data-ttu-id="ba172-147">Restaure la copia de seguridad completa de base de datos más reciente de cada una de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-147">Restore the most recent full database backup of each database.</span></span>  
  
3.  <span data-ttu-id="ba172-148">Identifique la transacción marcada más reciente que esté disponible en todas las copias de seguridad de los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="ba172-148">Identify the most recent marked transaction that is available in all of the transaction log backups.</span></span> <span data-ttu-id="ba172-149">Esta información se almacena en la tabla **logmarkhistory** de la base de datos **msdb** de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="ba172-149">This information is stored in the **logmarkhistory** table in the **msdb** database on each server.</span></span>  
  
4.  <span data-ttu-id="ba172-150">Identifique qué copias de seguridad de registros de todas las bases de datos relacionadas contienen esta marca.</span><span class="sxs-lookup"><span data-stu-id="ba172-150">Identify the log backups for all related databases that contain this mark.</span></span>  
  
5.  <span data-ttu-id="ba172-151">Restaure cada una de las copias de seguridad de registros y deténgase en la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="ba172-151">Restore each log backup, stopping at the marked transaction.</span></span>  
  
6.  <span data-ttu-id="ba172-152">Recupere cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba172-152">Recover each database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba172-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba172-153">See Also</span></span>  
 <span data-ttu-id="ba172-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba172-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="ba172-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba172-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="ba172-156">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba172-156">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ba172-157">[Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente &#40;modelo de recuperación completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span><span class="sxs-lookup"><span data-stu-id="ba172-157">[Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span></span>  
 <span data-ttu-id="ba172-158">[Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba172-158">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="ba172-159">[Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="ba172-159">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="ba172-160">Planear y realizar secuencias de restauración &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ba172-160">Plan and Perform Restore Sequences &#40;Full Recovery Model&#41;</span></span>](plan-and-perform-restore-sequences-full-recovery-model.md)  
  
  
