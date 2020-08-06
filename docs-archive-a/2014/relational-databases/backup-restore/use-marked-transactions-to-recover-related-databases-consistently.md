---
title: Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente (modelo de recuperación completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction marks [SQL Server]
- marked transactions [SQL Server]
- database restores [SQL Server], inserting transaction marks for
- recovery [SQL Server], related databases
- restoring databases [SQL Server], related database recovery
- database restores [SQL Server], related databases
- marked transactions [SQL Server], creating
- BEGIN TRAN...WITH MARK statement
- two-phase commit
ms.assetid: 50a73574-1a69-448e-83dd-9abcc7cb7e1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8dd368ad14f6e521fb8d504bdea774e3088c2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748137"
---
# <a name="use-marked-transactions-to-recover-related-databases-consistently-full-recovery-model"></a><span data-ttu-id="5a6a8-102">Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="5a6a8-102">Use Marked Transactions to Recover Related Databases Consistently (Full Recovery Model)</span></span>
  <span data-ttu-id="5a6a8-103">Este tema solamente es aplicable a las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usan el modelo de recuperación optimizado para cargas masivas de registros o el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="5a6a8-104">Al realizar actualizaciones relacionadas en dos o más bases de datos, *bases de datos relacionadas*, puede usar marcas de transacción para recuperarlas a un punto con coherencia lógica.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-104">When you make related updates to two or more databases, *related databases*, you can use transaction marks to recover them to a logically consistent point.</span></span> <span data-ttu-id="5a6a8-105">Sin embargo, en esta recuperación se pierden todas las transacciones que se confirmaron después de la marca utilizada como punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-105">However, this recovery loses any transaction that is committed after the mark that was used as the recovery point.</span></span> <span data-ttu-id="5a6a8-106">Las marcas de transacciones solo son adecuadas cuando se están probando bases de datos relacionadas o cuando se está dispuesto a perder las últimas transacciones confirmadas.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-106">Marking transactions is suitable only when you are testing related databases or when you are willing to lose recently committed transactions.</span></span>  
  
 <span data-ttu-id="5a6a8-107">Si se marcan periódicamente las transacciones relacionadas en todas las bases de datos relacionadas, se establece una serie de puntos de recuperación común en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-107">Routinely marking related transactions in every related database establishes a series of common recovery points in the databases.</span></span> <span data-ttu-id="5a6a8-108">Las marcas de transacción se graban en el registro de transacciones y se incluyen en las copias de seguridad de los registros.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-108">The transaction marks are recorded in the transaction log and included in log backups.</span></span> <span data-ttu-id="5a6a8-109">Si se produce un desastre, puede restaurar cada una de las bases de datos a la misma marca de transacción para recuperarlas a un punto coherente.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-109">In the event of a disaster, you can restore each of the databases to the same transaction mark to recover them to a consistent point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a6a8-110">Las copias de seguridad de registros de las distintas bases de datos se pueden crear por separado y no tienen que ser simultáneos.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-110">Log backups on the different databases can be created independently of each other and do not have to be simultaneous.</span></span>  
  
 <span data-ttu-id="5a6a8-111">La recuperación de bases de datos relacionadas en los escenarios siguientes requiere que ya se hayan marcado las transacciones de todas las bases de datos relacionadas:</span><span class="sxs-lookup"><span data-stu-id="5a6a8-111">Recovering related databases in the following scenarios requires that you have already marked transactions in every related database:</span></span>  
  
-   <span data-ttu-id="5a6a8-112">Uno o más registros de transacciones se destruyen.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-112">One or more transaction logs are destroyed.</span></span> <span data-ttu-id="5a6a8-113">Tiene que restaurar el conjunto de bases de datos a un estado coherente en el momento de la última copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-113">You have to restore the set of databases to a consistent state at the time of your last log backup.</span></span>  
  
-   <span data-ttu-id="5a6a8-114">Tiene que restaurar todo el conjunto de bases de datos a un estado coherente entre sí en algún momento anterior.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-114">You have to restore the entire set of databases to a mutually consistent state at some earlier point in time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5a6a8-115">Las bases de datos relacionadas solo se pueden recuperar hasta una transacción marcada, no hasta un momento específico.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-115">You can recover related databases only to a marked transaction, not to a specific point in time.</span></span>  
  
 <span data-ttu-id="5a6a8-116">Para obtener más información sobre cómo crear transacciones marcadas, vea "Crear las transacciones marcadas" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-116">For information about how to create marking transactions, see "Creating the Marked Transactions," later in this topic.</span></span>  
  
## <a name="typical-scenario-for-using-marked-transactions"></a><span data-ttu-id="5a6a8-117">Escenario habitual para utilizar transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="5a6a8-117">Typical Scenario for Using Marked Transactions</span></span>  
 <span data-ttu-id="5a6a8-118">Un escenario habitual para usar transacciones marcadas consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5a6a8-118">A typical scenario for using marked transactions includes the following steps:</span></span>  
  
1.  <span data-ttu-id="5a6a8-119">Crear una copia de seguridad completa o diferencial de cada una de las bases de datos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-119">Create a full or differential database backup of each of the related databases.</span></span>  
  
2.  <span data-ttu-id="5a6a8-120">Marcar un bloque de transacciones en todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-120">Mark a transaction block in all the databases.</span></span>  
  
3.  <span data-ttu-id="5a6a8-121">Realizar una copia de seguridad del registro de transacciones de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-121">Back up the transaction log for all the databases.</span></span>  
  
4.  <span data-ttu-id="5a6a8-122">Restaurar las copias de seguridad de las bases de datos con WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-122">Restore database backups WITH NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="5a6a8-123">Restaurar los registros con WITH STOPATMARK.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-123">Restore logs WITH STOPATMARK.</span></span>  
  
## <a name="considerations-for-using-marked-transactions"></a><span data-ttu-id="5a6a8-124">Consideraciones para el uso de transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="5a6a8-124">Considerations for Using Marked Transactions</span></span>  
 <span data-ttu-id="5a6a8-125">Antes de insertar marcas con nombre en el registro de transacciones, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a6a8-125">Before inserting named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="5a6a8-126">Debido a que las marcas de transacción consumen espacio del registro, utilícelas solo para aquellas transacciones que desempeñen un rol importante en la estrategia de recuperación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-126">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="5a6a8-127">Después de la confirmación de una transacción marcada, se inserta una fila en la tabla [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) de **msdb**.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-127">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="5a6a8-128">Si la transacción marcada abarca varias bases de datos del mismo servidor de base de datos o de diferentes servidores, las marcas se registran en los registros de todas las bases de datos afectadas.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-128">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span>  
  
## <a name="creating-the-marked-transactions"></a><span data-ttu-id="5a6a8-129">Crear las transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="5a6a8-129">Creating the Marked Transactions</span></span>  
 <span data-ttu-id="5a6a8-130">Para crear una transacción marcada, use la instrucción [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) y la cláusula WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="5a6a8-130">To create a marked transaction, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="5a6a8-131">La descripción ( *description* ) es opcional y es un texto descriptivo de la marca.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-131">The optional *description* is a textual description of the mark.</span></span> <span data-ttu-id="5a6a8-132">Es necesario un nombre de marca para la transacción.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-132">A mark name for the transaction is required.</span></span> <span data-ttu-id="5a6a8-133">Puede volver a usarse un nombre de marca.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-133">A mark name can be reused.</span></span> <span data-ttu-id="5a6a8-134">El registro de transacciones registra el nombre de la marca, su descripción, la base de datos, el usuario, la información de fecha y hora y el número de secuencia de registro (LSN).</span><span class="sxs-lookup"><span data-stu-id="5a6a8-134">The transaction log records the mark name, description, database, user, datetime information, and the log sequence number (LSN).</span></span> <span data-ttu-id="5a6a8-135">La información de fecha y hora se utiliza con el nombre de la marca para identificar la marca de forma única.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-135">The datetime information is used along with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="5a6a8-136">**Para crear transacciones marcadas en un conjunto de bases de datos:**</span><span class="sxs-lookup"><span data-stu-id="5a6a8-136">**To create marked transactions in a set of databases:**</span></span>  
  
1.  <span data-ttu-id="5a6a8-137">Asigne un nombre a la transacción en la instrucción BEGIN TRAN y use la cláusula WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-137">Name the transaction in the BEGIN TRAN statement and use the WITH MARK clause</span></span>  
  
     <span data-ttu-id="5a6a8-138">Puede anidar la instrucción BEGIN TRAN *new_mark_name* WITH MARK en una transacción existente.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-138">You can nest the statement BEGIN TRAN *new_mark_name* WITH MARK within an existing transaction.</span></span> <span data-ttu-id="5a6a8-139">El valor de *new_mark_name* es el nombre de marca de la transacción, aunque la transacción tenga un nombre de transacción.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-139">The value of *new_mark_name* is the mark name for the transaction, even if the transaction possesses a transaction name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5a6a8-140">Si ejecuta una segunda instrucción anidada BEGIN TRAN...WITH MARK, dicha instrucción se omite pero genera un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-140">If you issue a second nested BEGIN TRAN...WITH MARK, that statement is skipped but causes a warning message.</span></span>  
  
2.  <span data-ttu-id="5a6a8-141">Ejecute una actualización en todas las bases de datos del conjunto.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-141">Run an update against all of the databases in the set.</span></span>  
  
     <span data-ttu-id="5a6a8-142">La marca de una transacción concreta se inserta en los registros de transacciones solo en la instancia de servidor en que se ejecuta la instrucción BEGIN TRAN...WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-142">The mark for a specific transaction is inserted into transaction logs only on the server instance where the BEGIN TRAN...WITH MARK statement is executed.</span></span> <span data-ttu-id="5a6a8-143">La marca de transacción se coloca en el registro de transacciones de todas las bases de datos actualizadas por la transacción marcada en esa instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-143">The transaction mark is placed in the transaction log of every database updated by the marked transaction on that server instance.</span></span> <span data-ttu-id="5a6a8-144">Si las bases de datos se encuentran en distintas instancias de servidor, se deben crear marcas idénticas en cada una de dichas instancias.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-144">If the databases reside on different server instances, identical marks must be created on each of the server instances.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="5a6a8-145">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5a6a8-145">Examples</span></span>  
 <span data-ttu-id="5a6a8-146">En el ejemplo siguiente se restaura el registro de transacciones hasta la marca de la transacción marcada denominada `ListPriceUpdate`.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-146">The following example restores the transaction log to the mark in the marked transaction named `ListPriceUpdate`.</span></span>  
  
```sql  
USE AdventureWorks  
GO  
BEGIN TRANSACTION ListPriceUpdate  
   WITH MARK 'UPDATE Product list prices';  
GO  
  
UPDATE Production.Product  
   SET ListPrice = ListPrice * 1.10  
   WHERE ProductNumber LIKE 'BK-%';  
GO  
  
COMMIT TRANSACTION ListPriceUpdate;  
GO  
  
-- Time passes. Regular database   
-- and log backups are taken.  
-- An error occurs in the database.  
USE master  
GO  
  
RESTORE DATABASE AdventureWorks  
FROM AdventureWorksBackups  
WITH FILE = 3, NORECOVERY;  
GO  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups   
   WITH FILE = 4,  
   RECOVERY,   
   STOPATMARK = 'ListPriceUpdate';  
```  
  
## <a name="forcing-a-mark-to-spread-to-other-servers"></a><span data-ttu-id="5a6a8-147">Forzar que una marca se distribuya a otros servidores</span><span class="sxs-lookup"><span data-stu-id="5a6a8-147">Forcing a Mark to Spread to Other Servers</span></span>  
 <span data-ttu-id="5a6a8-148">Un nombre de marca de transacción no se distribuye automáticamente a otro servidor cuando se distribuye la transacción.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-148">A transaction mark name is not automatically distributed to another server as the transaction spreads there.</span></span> <span data-ttu-id="5a6a8-149">Para forzar que la marca se distribuya a los otros servidores, es necesario escribir un procedimiento almacenado que contenga una instrucción BEGIN TRAN *name* WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-149">To force the mark to spread to the other servers, a stored procedure must be written that contains a BEGIN TRAN *name* WITH MARK statement.</span></span> <span data-ttu-id="5a6a8-150">Ese procedimiento almacenado se debe ejecutar en el servidor remoto en el ámbito de la transacción del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-150">That stored procedure must then be executed on the remote server under the scope of the transaction in the originating server.</span></span>  
  
 <span data-ttu-id="5a6a8-151">Por ejemplo, suponga que hay una base de datos con particiones en varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a6a8-151">For example, consider a partitioned database that exists on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a6a8-152">En cada instancia hay una base de datos cuyo nombre es `coyote`.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-152">On each instance is a database named `coyote`.</span></span> <span data-ttu-id="5a6a8-153">Primero, cree un procedimiento almacenado, por ejemplo `sp_SetMark`, en todas las bases de datos:</span><span class="sxs-lookup"><span data-stu-id="5a6a8-153">First, in every database, create a stored procedure, for example, `sp_SetMark`.</span></span>  
  
```sql  
CREATE PROCEDURE sp_SetMark  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION @name WITH MARK  
UPDATE coyote.dbo.Marks SET one = 1  
COMMIT TRANSACTION;  
GO  
```  
  
 <span data-ttu-id="5a6a8-154">A continuación, cree el procedimiento almacenado `sp_MarkAll` que contenga una transacción que coloque una marca en cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-154">Next, create stored procedure `sp_MarkAll` containing a transaction that places a mark in every database.</span></span> <span data-ttu-id="5a6a8-155">`sp_MarkAll` se puede ejecutar desde cualquiera de las instancias.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-155">`sp_MarkAll` can be run from any of the instances.</span></span>  
  
```sql  
CREATE PROCEDURE sp_MarkAll  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION  
EXEC instance0.coyote.dbo.sp_SetMark @name  
EXEC instance1.coyote.dbo.sp_SetMark @name  
EXEC instance2.coyote.dbo.sp_SetMark @name  
COMMIT TRANSACTION;  
GO  
```  
  
### <a name="two-phase-commit"></a><span data-ttu-id="5a6a8-156">confirmación en dos fases</span><span class="sxs-lookup"><span data-stu-id="5a6a8-156">Two-Phase Commit</span></span>  
 <span data-ttu-id="5a6a8-157">La confirmación de una transacción distribuida tiene lugar en dos fases: preparación y confirmación.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-157">Committing a distributed transaction occurs in two phases: prepare and commit.</span></span> <span data-ttu-id="5a6a8-158">Cuando se confirma una transacción marcada, la entrada de registro de confirmación de cada base de datos de la transacción marcada se coloca en el registro en un punto en que no hay transacciones dudosas en ninguno de los registros.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-158">When a marked transaction is committed, the commit log record for each database in the marked transaction is placed in the log at a point where there are no in-doubt transactions in any of the logs.</span></span> <span data-ttu-id="5a6a8-159">En este momento, es seguro que ninguna transacción aparecerá como confirmada en un registro pero no en otro.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-159">At this point, it is guaranteed that there are no transactions that appear as committed in one log, but not committed in another log.</span></span>  
  
 <span data-ttu-id="5a6a8-160">Con los siguientes pasos se realiza esta tarea durante la confirmación de una transacción marcada:</span><span class="sxs-lookup"><span data-stu-id="5a6a8-160">The following steps accomplish this during the commit of a marked transaction:</span></span>  
  
1.  <span data-ttu-id="5a6a8-161">La fase de preparación del marcado de una transacción pausa las nuevas operaciones de preparación y confirmación.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-161">Prepare phase of a marking transaction stalls all new prepares and commits.</span></span>  
  
2.  <span data-ttu-id="5a6a8-162">Solo podrán continuar las confirmaciones de las transacciones ya preparadas.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-162">Only commits of already prepared transactions are allowed to continue.</span></span>  
  
3.  <span data-ttu-id="5a6a8-163">A continuación, el marcado de la transacción espera a que terminen todas las transacciones preparadas (con un tiempo de espera).</span><span class="sxs-lookup"><span data-stu-id="5a6a8-163">Marking transaction then waits for all prepared transactions to drain (with time-out).</span></span>  
  
4.  <span data-ttu-id="5a6a8-164">Se prepara y se confirma la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-164">Marked transaction is prepared and committed.</span></span>  
  
5.  <span data-ttu-id="5a6a8-165">Se quita la pausa de las nuevas preparaciones y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-165">The stall of new prepares and commits is removed.</span></span>  
  
 <span data-ttu-id="5a6a8-166">Las pausas generadas por las transacciones marcadas que abarcan varias bases de datos pueden disminuir el rendimiento del procesamiento de las transacciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-166">The stalls generated by marked transactions that span multiple databases can reduce the transaction processing performance of the server.</span></span>  
  
 <span data-ttu-id="5a6a8-167">Se recomienda no ejecutar transacciones marcadas a la vez.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-167">We recommend that you do not run concurrent marked transactions.</span></span> <span data-ttu-id="5a6a8-168">Aunque es poco frecuente, la confirmación de una transacción marcada distribuida podría interbloquear otras transacciones marcadas distribuidas que se estén confirmando simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-168">It is rare but possible for the commit of a distributed marked transaction to deadlock with other distributed marked transactions that are committing at the same time.</span></span> <span data-ttu-id="5a6a8-169">Si esto sucede, se elegirá el marcado de la transacción como víctima del interbloqueo y se revertirá la operación.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-169">When this happens, the marking transaction is chosen as the deadlock victim and is rolled back.</span></span> <span data-ttu-id="5a6a8-170">Cuando se produce este error, la aplicación puede volver a intentar la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-170">When this error occurs, the application can retry the marked transaction.</span></span> <span data-ttu-id="5a6a8-171">Si se intenta confirmar varias transacciones marcadas simultáneamente, la probabilidad de interbloqueo es mayor.</span><span class="sxs-lookup"><span data-stu-id="5a6a8-171">When multiple marked transactions try to commit concurrently, there is a higher probability of deadlock.</span></span>  
  
## <a name="recovering-to-a-marked-transaction"></a><span data-ttu-id="5a6a8-172">Recuperar a una transacción marcada</span><span class="sxs-lookup"><span data-stu-id="5a6a8-172">Recovering to a Marked Transaction</span></span>  
 <span data-ttu-id="5a6a8-173">Para obtener información sobre cómo recuperar una base de datos con transacciones marcadas a una marca concreta o inmediatamente antes, vea [Recuperación de bases de datos relacionadas que contienen transacciones marcadas](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="5a6a8-173">For information about how to recover a database that contains marked transactions to or just before a particular mark, see [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6a8-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a6a8-174">See Also</span></span>  
 <span data-ttu-id="5a6a8-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a6a8-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span></span>  
 <span data-ttu-id="5a6a8-176">[Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5a6a8-176">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="5a6a8-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a6a8-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="5a6a8-178">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5a6a8-178">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="5a6a8-179">[Copias de seguridad completas de bases de datos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5a6a8-179">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="5a6a8-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a6a8-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="5a6a8-181">Recuperación de bases de datos relacionadas que contienen transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="5a6a8-181">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
  
