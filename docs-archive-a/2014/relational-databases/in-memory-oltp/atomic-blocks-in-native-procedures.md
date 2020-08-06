---
title: Bloques Atomic | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 40e0e749-260c-4cfc-a848-444d30c09d85
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ca8f5b4d767ef0fe836cd260f8d12dd5b40c75d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663471"
---
# <a name="atomic-blocks"></a><span data-ttu-id="a3339-102">Bloques atomic</span><span class="sxs-lookup"><span data-stu-id="a3339-102">Atomic Blocks</span></span>
  <span data-ttu-id="a3339-103">`BEGIN ATOMIC` es parte del estándar ANSI SQL.</span><span class="sxs-lookup"><span data-stu-id="a3339-103">`BEGIN ATOMIC` is part of the ANSI SQL standard.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a3339-104">admite los bloques atomic solo en el nivel superior de los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="a3339-104">supports atomic blocks only at the top-level of natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="a3339-105">Cada procedimiento almacenado compilado de forma nativa contiene exactamente un bloque de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3339-105">Every natively compiled stored procedure contains exactly one block of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a3339-106">Este es un bloque ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="a3339-106">This is an ATOMIC block.</span></span>  
  
-   <span data-ttu-id="a3339-107">Los procedimientos almacenados [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretados no nativos y los lotes ad hoc no admiten los bloques atomic.</span><span class="sxs-lookup"><span data-stu-id="a3339-107">Non-native, interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and ad hoc batches do not support atomic blocks.</span></span>  
  
 <span data-ttu-id="a3339-108">Los bloques atomic se ejecutan (atómicamente) dentro de la transacción.</span><span class="sxs-lookup"><span data-stu-id="a3339-108">Atomic blocks are executed (atomically) within the transaction.</span></span> <span data-ttu-id="a3339-109">Todas las instrucciones del bloque se ejecutan correctamente o el bloque completo se revertirá al punto de retorno que se creó al principio del bloque.</span><span class="sxs-lookup"><span data-stu-id="a3339-109">Either all statements in the block succeed or the entire block will be rolled back to the savepoint that was created at the start of the block.</span></span> <span data-ttu-id="a3339-110">Además, los parámetros de configuración de la sesión son fijos para el bloque atomic.</span><span class="sxs-lookup"><span data-stu-id="a3339-110">In addition, the session settings are fixed for the atomic block.</span></span> <span data-ttu-id="a3339-111">La ejecución del mismo bloque atomic en sesiones con diferentes parámetros producirá el mismo comportamiento, independientemente de la configuración de la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="a3339-111">Executing the same atomic block in sessions with different settings will result in the same behavior, independent of the settings of the current session.</span></span>  
  
## <a name="transactions-and-error-handling"></a><span data-ttu-id="a3339-112">Transacciones y control de errores</span><span class="sxs-lookup"><span data-stu-id="a3339-112">Transactions and Error Handling</span></span>  
 <span data-ttu-id="a3339-113">Si una transacción ya existe en una sesión (porque un lote ejecutó una instrucción `BEGIN TRANSACTION` y la transacción permanece activa), iniciar a continuación un bloque atomic creará un punto de retorno de la transacción.</span><span class="sxs-lookup"><span data-stu-id="a3339-113">If a transaction already exists on a session (because a batch executed a `BEGIN TRANSACTION` statement and the transaction remains active), then starting an atomic block will create a savepoint in the transaction.</span></span> <span data-ttu-id="a3339-114">Si el bloque sale sin una excepción, se confirma el punto de retorno que se creó para el bloque, pero la transacción no se confirmará hasta que se confirme en el nivel de sesión.</span><span class="sxs-lookup"><span data-stu-id="a3339-114">If the block exits without an exception, the savepoint that was created for the block commits, but the transaction will not commit until the transaction at the session level commits.</span></span> <span data-ttu-id="a3339-115">Si el bloque produce una excepción, los efectos del bloque se revierten pero la transacción en el nivel de sesión continuará, a menos que la excepción invalide la transacción.</span><span class="sxs-lookup"><span data-stu-id="a3339-115">If the block throws an exception, the effects of the block are rolled back but the transaction at the session level will proceed, unless the exception is transaction-dooming.</span></span> <span data-ttu-id="a3339-116">Por ejemplo, un conflicto de escritura invalida la transacción, mientras que un error de conversión no la invalida.</span><span class="sxs-lookup"><span data-stu-id="a3339-116">For example a write conflict is transaction-dooming, but not a type casting error.</span></span>  
  
 <span data-ttu-id="a3339-117">Si no hay ninguna transacción activa en una sesión, `BEGIN ATOMIC` iniciará una nueva transacción.</span><span class="sxs-lookup"><span data-stu-id="a3339-117">If there is no active transaction on a session, `BEGIN ATOMIC` will start a new transaction.</span></span> <span data-ttu-id="a3339-118">Si no se inicia una excepción fuera del ámbito del bloque, la transacción se confirmará al final del bloque.</span><span class="sxs-lookup"><span data-stu-id="a3339-118">If no exception is thrown outside the scope of the block, the transaction will be committed at the end of the block.</span></span> <span data-ttu-id="a3339-119">Si el bloque produce una excepción (es decir, la excepción no se detecta ni se controla en el bloque), la transacción se revertirá.</span><span class="sxs-lookup"><span data-stu-id="a3339-119">If the block throws an exception (that is, the exception is not caught and handled within the block), the transaction will be rolled back.</span></span> <span data-ttu-id="a3339-120">Para las transacciones que ocupan un único bloque atomic (un solo procedimiento almacenado compilado de forma nativa), no se deben escribir instrucciones `BEGIN TRANSACTION` y `COMMIT` o `ROLLBACK` explícitas.</span><span class="sxs-lookup"><span data-stu-id="a3339-120">For transactions that span a single atomic block (a single natively compiled stored procedure), you do not need to write explicit `BEGIN TRANSACTION` and `COMMIT` or `ROLLBACK` statements.</span></span>  
  
 <span data-ttu-id="a3339-121">Los procedimientos almacenados compilados de forma nativa admiten las construcciones `TRY`, `CATCH` y `THROW` para el control de errores.</span><span class="sxs-lookup"><span data-stu-id="a3339-121">Natively compiled stored procedures support the `TRY`, `CATCH`, and `THROW` constructs for error handling.</span></span> <span data-ttu-id="a3339-122">No se admite `RAISERROR`.</span><span class="sxs-lookup"><span data-stu-id="a3339-122">`RAISERROR` is not supported.</span></span>  
  
 <span data-ttu-id="a3339-123">En el ejemplo siguiente se muestra el comportamiento de control de errores con bloques atomic y procedimientos almacenados compilados de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="a3339-123">The following example illustrates the error handling behavior with atomic blocks and natively compiled stored procedures:</span></span>  
  
```sql  
-- sample table  
CREATE TABLE dbo.t1 (  
  c1 int not null primary key nonclustered  
)  
WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- sample proc that inserts 2 rows  
CREATE PROCEDURE dbo.usp_t1 @v1 bigint not null, @v2 bigint not null  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC  
WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english', DELAYED_DURABILITY = ON)  
  
  INSERT dbo.t1 VALUES (@v1)  
  INSERT dbo.t1 VALUES (@v2)  
  
END  
GO  
  
-- insert two rows  
EXEC dbo.usp_t1 1, 2  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify the rows 1 and 2 were committed  
SELECT c1 FROM dbo.t1  
GO  
  
-- execute proc with arithmetic overflow  
EXEC dbo.usp_t1 3, 4444444444444  
GO  
-- expected error message:  
-- Msg 8115, Level 16, State 0, Procedure usp_t1  
-- Arithmetic overflow error converting bigint to data type int.  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 was not committed; usp_t1 has been rolled back  
SELECT c1 FROM dbo.t1  
GO  
  
-- start a new transaction  
BEGIN TRANSACTION  
  -- insert rows 3 and 4  
  EXEC dbo.usp_t1 3, 4  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify the rows 3 and 4 were inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
  -- catch the arithmetic overflow error  
  BEGIN TRY  
    EXEC dbo.usp_t1 5, 4444444444444  
  END TRY  
  BEGIN CATCH  
    PRINT N'Error occurred: ' + error_message()  
  END CATCH  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify rows 3 and 4 are still in the table, and row 5 has not been inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
COMMIT  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 and 4 has been committed  
SELECT c1 FROM dbo.t1  
ORDER BY c1  
GO  
```  
  
 <span data-ttu-id="a3339-124">Los mensajes de error siguientes específicos de las tablas optimizadas para memoria invalidan las transacciones.</span><span class="sxs-lookup"><span data-stu-id="a3339-124">The following error messages specific to memory-optimized tables are transaction dooming.</span></span> <span data-ttu-id="a3339-125">Si aparecen en el ámbito de un bloque atomic, causarán que se anulen las transacciones: 10772, 41301, 41302, 41305, 41325, 41332 y 41333.</span><span class="sxs-lookup"><span data-stu-id="a3339-125">If they occur in the scope of an atomic block, they will cause the transaction to abort: 10772, 41301, 41302, 41305, 41325, 41332, and 41333.</span></span>  
  
## <a name="session-settings"></a><span data-ttu-id="a3339-126">Configuración de la sesión</span><span class="sxs-lookup"><span data-stu-id="a3339-126">Session Settings</span></span>  
 <span data-ttu-id="a3339-127">Los parámetros de configuración de sesión de los bloques atomic son fijos cuando se compila el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a3339-127">The session settings in atomic blocks are fixed when the stored procedure is compiled.</span></span> <span data-ttu-id="a3339-128">Algunos parámetros se pueden especificar con `BEGIN ATOMIC`, mientras que otros están fijos siempre en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="a3339-128">Some settings can be specified with `BEGIN ATOMIC` while other settings are always fixed to the same value.</span></span>  
  
 <span data-ttu-id="a3339-129">Se requieren las siguientes opciones con `BEGIN ATOMIC`:</span><span class="sxs-lookup"><span data-stu-id="a3339-129">The following options are required with `BEGIN ATOMIC`:</span></span>  
  
|<span data-ttu-id="a3339-130">Configuración necesaria</span><span class="sxs-lookup"><span data-stu-id="a3339-130">Required Setting</span></span>|<span data-ttu-id="a3339-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3339-131">Description</span></span>|  
|----------------------|-----------------|  
|`TRANSACTION ISOLATION LEVEL`|<span data-ttu-id="a3339-132">Los valores admitidos son `SNAPSHOT`, `REPEATABLEREAD` y `SERIALIZABLE`.</span><span class="sxs-lookup"><span data-stu-id="a3339-132">Supported values are `SNAPSHOT`, `REPEATABLEREAD`, and `SERIALIZABLE`.</span></span>|  
|`LANGUAGE`|<span data-ttu-id="a3339-133">Determina los formatos de fecha y hora y los mensajes del sistema.</span><span class="sxs-lookup"><span data-stu-id="a3339-133">Determines date and time formats and system messages.</span></span> <span data-ttu-id="a3339-134">Se admiten todos los lenguajes y alias de [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a3339-134">All languages and aliases in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) are supported.</span></span>|  
  
 <span data-ttu-id="a3339-135">Los siguientes parámetros de configuración son opcionales:</span><span class="sxs-lookup"><span data-stu-id="a3339-135">The following settings are optional:</span></span>  
  
|<span data-ttu-id="a3339-136">Configuración opcional</span><span class="sxs-lookup"><span data-stu-id="a3339-136">Optional Setting</span></span>|<span data-ttu-id="a3339-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3339-137">Description</span></span>|  
|----------------------|-----------------|  
|`DATEFORMAT`|<span data-ttu-id="a3339-138">Se admiten todos los formatos de fecha de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3339-138">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date formats are supported.</span></span> <span data-ttu-id="a3339-139">Cuando se especifica, `DATEFORMAT` reemplaza el formato de fecha predeterminado asociado a `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="a3339-139">When specified, `DATEFORMAT` overrides the default date format associated with `LANGUAGE`.</span></span>|  
|`DATEFIRST`|<span data-ttu-id="a3339-140">Cuando se especifica, `DATEFIRST` reemplaza el valor predeterminado asociado a `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="a3339-140">When specified, `DATEFIRST` overrides the default associated with `LANGUAGE`.</span></span>|  
|`DELAYED_DURABILITY`|<span data-ttu-id="a3339-141">Los valores admitidos son `OFF` y `ON`.</span><span class="sxs-lookup"><span data-stu-id="a3339-141">Supported values are `OFF` and `ON`.</span></span><br /><br /> <span data-ttu-id="a3339-142">Las confirmaciones de transacción de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden ser totalmente durables (el valor predeterminado) o durables diferidas. Para más información, vea [Controlar la durabilidad de las transacciones](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="a3339-142">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction commits can be either fully durable, the default, or delayed durable.For more information, see [Control Transaction Durability](../logs/control-transaction-durability.md).</span></span>|  
  
 <span data-ttu-id="a3339-143">Las opciones SET siguientes tienen el mismo valor predeterminado del sistema para todos los bloques atomic en todos los procedimientos almacenados compilados de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="a3339-143">The following SET options have the same system default value for all atomic blocks in all natively compiled stored procedures:</span></span>  
  
|<span data-ttu-id="a3339-144">Opción SET</span><span class="sxs-lookup"><span data-stu-id="a3339-144">Set Option</span></span>|<span data-ttu-id="a3339-145">Valor predeterminado del sistema para los bloques atomic</span><span class="sxs-lookup"><span data-stu-id="a3339-145">System Default for Atomic Blocks</span></span>|  
|----------------|--------------------------------------|  
|<span data-ttu-id="a3339-146">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="a3339-146">ANSI_NULLS</span></span>|<span data-ttu-id="a3339-147">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-147">ON</span></span>|  
|<span data-ttu-id="a3339-148">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="a3339-148">ANSI_PADDING</span></span>|<span data-ttu-id="a3339-149">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-149">ON</span></span>|  
|<span data-ttu-id="a3339-150">ANSI_WARNING</span><span class="sxs-lookup"><span data-stu-id="a3339-150">ANSI_WARNING</span></span>|<span data-ttu-id="a3339-151">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-151">ON</span></span>|  
|<span data-ttu-id="a3339-152">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="a3339-152">ARITHABORT</span></span>|<span data-ttu-id="a3339-153">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-153">ON</span></span>|  
|<span data-ttu-id="a3339-154">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="a3339-154">ARITHIGNORE</span></span>|<span data-ttu-id="a3339-155">Apagado</span><span class="sxs-lookup"><span data-stu-id="a3339-155">OFF</span></span>|  
|<span data-ttu-id="a3339-156">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="a3339-156">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="a3339-157">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-157">ON</span></span>|  
|<span data-ttu-id="a3339-158">IDENTITY_INSERT</span><span class="sxs-lookup"><span data-stu-id="a3339-158">IDENTITY_INSERT</span></span>|<span data-ttu-id="a3339-159">Apagado</span><span class="sxs-lookup"><span data-stu-id="a3339-159">OFF</span></span>|  
|<span data-ttu-id="a3339-160">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="a3339-160">NOCOUNT</span></span>|<span data-ttu-id="a3339-161">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-161">ON</span></span>|  
|<span data-ttu-id="a3339-162">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="a3339-162">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="a3339-163">Apagado</span><span class="sxs-lookup"><span data-stu-id="a3339-163">OFF</span></span>|  
|<span data-ttu-id="a3339-164">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="a3339-164">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="a3339-165">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="a3339-165">ON</span></span>|  
|<span data-ttu-id="a3339-166">ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="a3339-166">ROWCOUNT</span></span>|<span data-ttu-id="a3339-167">0</span><span class="sxs-lookup"><span data-stu-id="a3339-167">0</span></span>|  
|<span data-ttu-id="a3339-168">TEXTSIZE</span><span class="sxs-lookup"><span data-stu-id="a3339-168">TEXTSIZE</span></span>|<span data-ttu-id="a3339-169">0</span><span class="sxs-lookup"><span data-stu-id="a3339-169">0</span></span>|  
|<span data-ttu-id="a3339-170">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="a3339-170">XACT_ABORT</span></span>|<span data-ttu-id="a3339-171">Apagado</span><span class="sxs-lookup"><span data-stu-id="a3339-171">OFF</span></span><br /><br /> <span data-ttu-id="a3339-172">Las excepciones no detectadas hacen que se revierta el bloque atomic, pero no causan que la transacción se anule a menos que el error invalide la transacción.</span><span class="sxs-lookup"><span data-stu-id="a3339-172">Uncaught exceptions cause the atomic block to roll back, but not cause the transaction to abort unless the error is transaction dooming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3339-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3339-173">See Also</span></span>  
 [<span data-ttu-id="a3339-174">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="a3339-174">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
