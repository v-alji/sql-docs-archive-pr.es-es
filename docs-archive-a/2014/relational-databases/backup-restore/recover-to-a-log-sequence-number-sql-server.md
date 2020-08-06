---
title: Recuperación a un número de secuencia de registro (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log sequence numbers [SQL Server]
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- LSNs
- database recovery [SQL Server]
- database restores [SQL Server], point in time
ms.assetid: f7b3de5b-198d-448d-8c71-1cdd9239676c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4df55c3468fc009d86cffd58a837d6935f5ce14b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675467"
---
# <a name="recover-to-a-log-sequence-number-sql-server"></a><span data-ttu-id="2daa0-102">Recuperar a un número de secuencia de registro (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2daa0-102">Recover to a Log Sequence Number (SQL Server)</span></span>
  <span data-ttu-id="2daa0-103">Este tema solamente es aplicable a las bases de datos que utilizan el modelo de recuperación optimizado para cargas masivas de registros o el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="2daa0-103">This topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="2daa0-104">Puede usar un número de secuencia de registro (LSN) para definir el punto de recuperación de una operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="2daa0-104">You can use a log sequence number (LSN) to define the recovery point for a restore operation.</span></span> <span data-ttu-id="2daa0-105">Sin embargo, esta es una característica especializada dirigida a los proveedores de herramientas y no es probable que tenga una utilidad general.</span><span class="sxs-lookup"><span data-stu-id="2daa0-105">However, this is a specialized feature that is intended for tools vendors and is unlikely to be generally useful.</span></span>  
  
##  <a name="overview-of-log-sequence-numbers"></a><a name="LSNs"></a> <span data-ttu-id="2daa0-106">Información general de los números de secuencia de registro</span><span class="sxs-lookup"><span data-stu-id="2daa0-106">Overview of Log Sequence Numbers</span></span>  
 <span data-ttu-id="2daa0-107">Los LSN se utilizan internamente durante una secuencia RESTORE para realizar el seguimiento del momento dado al que se restauran los datos.</span><span class="sxs-lookup"><span data-stu-id="2daa0-107">LSNs are used internally during a RESTORE sequence to track the point in time to which data has been restored.</span></span> <span data-ttu-id="2daa0-108">Al restaurar una copia de seguridad, los datos se restauran al LSN correspondiente al momento dado en que se efectuó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2daa0-108">When a backup is restored, the data is restored to the LSN corresponding to the point in time at which the backup was taken.</span></span> <span data-ttu-id="2daa0-109">Las copias de seguridad diferenciales y del registro posponen la base de datos restaurada a un momento posterior, correspondiente a un LSN superior.</span><span class="sxs-lookup"><span data-stu-id="2daa0-109">Differential and log backups advance the restored database to a later time, which corresponds to a higher LSN.</span></span>  
  
 <span data-ttu-id="2daa0-110">Cada entrada del registro de transacción se identifica de forma exclusiva mediante un número de secuencia de registro (LSN).</span><span class="sxs-lookup"><span data-stu-id="2daa0-110">Every record in the transaction log is uniquely identified by a log sequence number (LSN).</span></span> <span data-ttu-id="2daa0-111">Los números LSN se ordenan de manera que si LSN2 es mayor que LSN1, el cambio descrito por la entrada de registro a la que hace referencia LSN2 se produce después del cambio descrito por la entrada de registro LSN.</span><span class="sxs-lookup"><span data-stu-id="2daa0-111">LSNs are ordered such that if LSN2 is greater than LSN1, the change described by the log record referred to by LSN2 occurred after the change described by the log record LSN.</span></span>  
  
 <span data-ttu-id="2daa0-112">El LSN de una entrada de registro en la que se haya producido un evento importante puede resultar útil para generar secuencias de restauración válidas.</span><span class="sxs-lookup"><span data-stu-id="2daa0-112">The LSN of a log record at which a significant event occurred can be useful for constructing correct restore sequences.</span></span> <span data-ttu-id="2daa0-113">Dado que LSN se ordenan, se pueden comparar la igualdad y la desigualdad (es decir,, **\<**, **>** **=** , **\<=**, **>=** ).</span><span class="sxs-lookup"><span data-stu-id="2daa0-113">Because LSNs are ordered, they can be compared for equality and inequality (that is, **\<**, **>**, **=**, **\<=**, **>=**).</span></span> <span data-ttu-id="2daa0-114">Estas comparaciones son útiles para generar secuencias de restauración.</span><span class="sxs-lookup"><span data-stu-id="2daa0-114">Such comparisons are useful when constructing restore sequences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2daa0-115">Los números LSN son valores con tipos de datos `numeric`(25,0).</span><span class="sxs-lookup"><span data-stu-id="2daa0-115">LSNs are values of data type `numeric`(25,0).</span></span> <span data-ttu-id="2daa0-116">Las operaciones aritméticas (por ejemplo, la suma o la resta) carecen de importancia y no deben utilizarse con los LSN.</span><span class="sxs-lookup"><span data-stu-id="2daa0-116">Arithmetic operations (for example, addition or subtraction) are not meaningful and must not be used with LSNs.</span></span>  
  

  
## <a name="viewing-lsns-used-by-backup-and-restore"></a><span data-ttu-id="2daa0-117">Ver LSN utilizados por las copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="2daa0-117">Viewing LSNs Used by Backup and Restore</span></span>  
 <span data-ttu-id="2daa0-118">El LSN de una entrada de registro en la que se produce un determinado evento de copias de seguridad y restauración puede visualizarse mediante uno o más de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="2daa0-118">The LSN of a log record at which a given backup and restore event occurred is viewable using one or more of the following:</span></span>  
  
-   [<span data-ttu-id="2daa0-119">backupset</span><span class="sxs-lookup"><span data-stu-id="2daa0-119">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
-   [<span data-ttu-id="2daa0-120">backupfile</span><span class="sxs-lookup"><span data-stu-id="2daa0-120">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)  
  
-   <span data-ttu-id="2daa0-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2daa0-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span></span>  
  
-   [<span data-ttu-id="2daa0-122">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="2daa0-122">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="2daa0-123">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="2daa0-123">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="2daa0-124">Los LSN también aparecen en algunos textos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2daa0-124">LSNs also appear in some message texts.</span></span>  
  
## <a name="transact-sql-syntax-for-restoring-to-an-lsn"></a><span data-ttu-id="2daa0-125">Sintaxis de Transact-SQL para restaurar hasta un LSN</span><span class="sxs-lookup"><span data-stu-id="2daa0-125">Transact-SQL Syntax for Restoring to an LSN</span></span>  
 <span data-ttu-id="2daa0-126">Con la instrucción [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , puede detenerse en el LSN o inmediatamente antes, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2daa0-126">By using a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, you can stop at or immediately before the LSN, as follows:</span></span>  
  
-   <span data-ttu-id="2daa0-127">Use la cláusula WITH STOPATMARK **="** lsn: _<número_lsn_>_ **"** , donde lsn: *\<lsnNumber>* es una cadena que especifica que la entrada de registro que contiene el LSN especificado es el punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="2daa0-127">Use the WITH STOPATMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record that contains the specified LSN is the recovery point.</span></span>  
  
     <span data-ttu-id="2daa0-128">STOPATMARK realiza una puesta al día hasta el LSN e incluye esa entrada de registro en la puesta al día.</span><span class="sxs-lookup"><span data-stu-id="2daa0-128">STOPATMARK roll forwards to the LSN and includes that log record in the roll forward.</span></span>  
  
-   <span data-ttu-id="2daa0-129">Use la cláusula WITH STOPBEFOREMARK **="** lsn: _<número_lsn_>_ **"** , donde lsn: *\<lsnNumber>* es una cadena que especifica que la entrada de registro inmediatamente anterior a la que contiene el número LSN especificado es el punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="2daa0-129">Use the WITH STOPBEFOREMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record immediately before the log record that contains the specified LSN number is the recovery point.</span></span>  
  
     <span data-ttu-id="2daa0-130">STOPBEFOREMARK realiza una puesta al día al LSN y excluye esa entrada de registro de la puesta al día.</span><span class="sxs-lookup"><span data-stu-id="2daa0-130">STOPBEFOREMARK rolls forward to the LSN and excludes that log record from the roll forward.</span></span>  
  
 <span data-ttu-id="2daa0-131">Normalmente, se selecciona una transacción específica para incluirla o excluirla.</span><span class="sxs-lookup"><span data-stu-id="2daa0-131">Typically, a specific transaction is selected to be included or excluded.</span></span> <span data-ttu-id="2daa0-132">Aunque no es necesario, en la práctica, la entrada de registro especificada es una entrada de confirmación de transacción.</span><span class="sxs-lookup"><span data-stu-id="2daa0-132">Although not required, in practice, the specified log record is a transaction-commit record.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2daa0-133">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2daa0-133">Examples</span></span>  
 <span data-ttu-id="2daa0-134">En el ejemplo siguiente se da por supuesto que se ha modificado la base de datos `AdventureWorks` para usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="2daa0-134">The following example assumes that the `AdventureWorks` database has been changed to use the full recovery model.</span></span>  
  
```  
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2daa0-135">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2daa0-135">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2daa0-136">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-136">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="2daa0-137">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-137">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="2daa0-138">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-138">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="2daa0-139">Restaurar una base de datos según el punto de error en el modelo de recuperación completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-139">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="2daa0-140">Restaurar una base de datos en una transacción marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-140">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2daa0-141">Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-141">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="2daa0-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2daa0-142">See Also</span></span>  
 <span data-ttu-id="2daa0-143">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2daa0-143">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="2daa0-144">[El registro de transacciones &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2daa0-144">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="2daa0-145">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2daa0-145">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
