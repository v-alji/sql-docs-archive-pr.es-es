---
title: Instrucciones para la lógica de reintento de transacciones en tablas optimizadas para memoria | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2a35c37-4449-49ee-8bba-928028f1de66
author: stevestein
ms.author: sstein
ms.openlocfilehash: c9ffaccefb8d4e0a3044c4858a06029fd4350354
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746422"
---
# <a name="guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables"></a><span data-ttu-id="0c037-102">Instrucciones para la lógica de reintento de transacciones en tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="0c037-102">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="0c037-103">Hay varias condiciones de error que aparecen con las transacciones que tienen acceso a tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="0c037-103">There are error conditions that occur with transactions that access memory-optimized tables.</span></span>  
  
-   41302. <span data-ttu-id="0c037-104">La transacción actual intentó actualizar un registro que se ha actualizado desde que la transacción se inició.</span><span class="sxs-lookup"><span data-stu-id="0c037-104">The current transaction attempted to update a record that has been updated since the transaction started.</span></span>  
  
-   41305. <span data-ttu-id="0c037-105">La transacción actual no pudo confirmarse debido a un error repetible de validación de lectura.</span><span class="sxs-lookup"><span data-stu-id="0c037-105">The current transaction failed to commit due to a repeatable read validation failure.</span></span>  
  
-   41325. <span data-ttu-id="0c037-106">La transacción actual no pudo confirmarse debido a un error serializable de validación.</span><span class="sxs-lookup"><span data-stu-id="0c037-106">The current transaction failed to commit due to a serializable validation failure.</span></span>  
  
-   41301. <span data-ttu-id="0c037-107">Una transacción anterior a la transacción actual realizada en una dependencia se ha anulado y la transacción actual ya no puede confirmarse.</span><span class="sxs-lookup"><span data-stu-id="0c037-107">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>  
  
 <span data-ttu-id="0c037-108">Una causa común de estos errores son las interferencias entre transacciones que se ejecutan simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="0c037-108">A common cause of these errors is interference between concurrently executing transaction.</span></span> <span data-ttu-id="0c037-109">La acción correctora común es reintentar la transacción.</span><span class="sxs-lookup"><span data-stu-id="0c037-109">The common corrective action is to retry the transaction.</span></span>  
  
 <span data-ttu-id="0c037-110">Para obtener más información sobre estas condiciones de error, vea la sección sobre detección de conflictos, validación y comprobaciones de dependencias de confirmación en [transacciones en tablas optimizadas para memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0c037-110">For more information about these error conditions, see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="0c037-111">Los interbloqueos (código de error 1205) no pueden aparecer en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="0c037-111">Deadlocks (error code 1205) cannot occur for memory-optimized tables.</span></span> <span data-ttu-id="0c037-112">Los bloqueos no se utilizan en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="0c037-112">Locks are not used for memory-optimized tables.</span></span> <span data-ttu-id="0c037-113">Sin embargo, si la aplicación ya contiene lógica de reintento para los interbloqueos, la lógica existente se puede ampliar para incluir los nuevos códigos de error.</span><span class="sxs-lookup"><span data-stu-id="0c037-113">However, if the application already contains retry logic for deadlocks, the existing logic could be extended to include the new error codes.</span></span>  
  
## <a name="considerations-for-retrying"></a><span data-ttu-id="0c037-114">Consideraciones sobre el reintento</span><span class="sxs-lookup"><span data-stu-id="0c037-114">Considerations for Retrying</span></span>  
 <span data-ttu-id="0c037-115">Las aplicaciones suelen encontrar conflictos entre las transacciones y tienen que implementar lógica de reintento para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="0c037-115">Applications will typically encounter conflicts between transactions and need to implement retry logic to resolve those conflicts.</span></span> <span data-ttu-id="0c037-116">El número de conflictos encontrado depende de varios factores:</span><span class="sxs-lookup"><span data-stu-id="0c037-116">The number of conflicts encountered depends on a number of factors:</span></span>  
  
-   <span data-ttu-id="0c037-117">Contención de filas individuales.</span><span class="sxs-lookup"><span data-stu-id="0c037-117">Contention for individual rows.</span></span> <span data-ttu-id="0c037-118">La posibilidad de conflictos aumenta a medida que aumenta el número de transacciones que intentan actualizar la misma fila.</span><span class="sxs-lookup"><span data-stu-id="0c037-118">The potential for conflicts increases as the number of transactions attempting to update the same row increases.</span></span>  
  
-   <span data-ttu-id="0c037-119">Número de filas leídas por transacciones REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="0c037-119">Number of rows read by REPEATABLE READ transactions.</span></span> <span data-ttu-id="0c037-120">Cuantas más filas se lean, mayor es la probabilidad de que algunas de estas filas sean actualizadas por transacciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="0c037-120">The more rows read, the greater the chance that some of these rows are updated by concurrent transactions.</span></span> <span data-ttu-id="0c037-121">Esto causa errores de validación de lectura repetible.</span><span class="sxs-lookup"><span data-stu-id="0c037-121">This causes repeatable read validation failures.</span></span>  
  
-   <span data-ttu-id="0c037-122">Tamaño de los intervalos de examen que utilizan las transacciones SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="0c037-122">Size of the scan ranges used by SERIALIZABLE transactions.</span></span> <span data-ttu-id="0c037-123">Cuanto mayores sean los intervalos de examen, mayor es la posibilidad de que las transacciones simultáneas presenten filas fantasma, ocasionando errores en la validación serializable.</span><span class="sxs-lookup"><span data-stu-id="0c037-123">The larger the scan ranges, the higher the chance that concurrent transactions will introduce phantom rows, causing serializable validation failures.</span></span>  
  
     <span data-ttu-id="0c037-124">Es difícil para una aplicación evitar estos conflictos, que requieren lógica de reintento.</span><span class="sxs-lookup"><span data-stu-id="0c037-124">It is difficult for an application to avoid these conflicts, requiring retry logic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0c037-125">Las transacciones de lectura/escritura que tienen acceso a tablas optimizadas para memoria requieren lógica de reintento.</span><span class="sxs-lookup"><span data-stu-id="0c037-125">Read-write transactions that access memory-optimized tables require retry logic.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-natively-compiled-stored-procedures"></a><span data-ttu-id="0c037-126">Consideraciones para las transacciones de solo lectura y los procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="0c037-126">Considerations for Read-Only Transactions and Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="0c037-127">Las transacciones de solo lectura que abarcan la ejecución de un procedimiento almacenado compilado de forma nativa no requieren la validación de las transacciones REPEATABLE READ y SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="0c037-127">Read-only transactions that span a single execution of a natively compiled stored procedure do not require validation for REPEATABLE READ and SERIALIZABLE transactions.</span></span> <span data-ttu-id="0c037-128">No pueden producirse conflictos de escritura porque una transacción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0c037-128">Write conflicts cannot occur due to a transaction being read-only.</span></span>  
  
 <span data-ttu-id="0c037-129">Sin embargo, los errores de dependencia pueden seguir apareciendo.</span><span class="sxs-lookup"><span data-stu-id="0c037-129">However, dependency failures can still occur.</span></span> <span data-ttu-id="0c037-130">Los errores de dependencia son más extraños que los errores resultantes de conflictos.</span><span class="sxs-lookup"><span data-stu-id="0c037-130">Dependency failures are rarer than errors resulting from conflicts.</span></span> <span data-ttu-id="0c037-131">Por tanto, en muchos casos, no se requiere una lógica de reintento específica para las transacciones de solo lectura que abarcan ejecuciones únicas de procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="0c037-131">Therefore, in many cases, specific retry logic is not required for read-only transactions that span single executions of natively compiled stored procedures.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-cross-container-transactions"></a><span data-ttu-id="0c037-132">Consideraciones para las transacciones de solo lectura y las transacciones entre contenedores</span><span class="sxs-lookup"><span data-stu-id="0c037-132">Considerations for Read-Only Transactions and Cross-Container Transactions</span></span>  
 <span data-ttu-id="0c037-133">Las transacciones de solo lectura entre contenedores, que son las transacciones que se inician fuera del contexto de un procedimiento almacenado compilado de forma nativa, no realizan la validación si se tiene acceso a todas las tablas optimizadas para memoria bajo aislamiento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="0c037-133">Read-only cross-container transactions, which are transactions that are started outside the context of a natively compiled stored procedure, do not perform validation if the memory-optimized tables are all accessed under SNAPSHOT isolation.</span></span> <span data-ttu-id="0c037-134">Sin embargo, cuando se tiene acceso a tablas optimizadas para memoria con el aislamiento REPEATABLE READ o SERIALIZABLE, la validación se realiza en tiempo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="0c037-134">However, when memory-optimized tables are accessed under REPEATABLE READ or SERIALIZABLE isolation, validation is performed at commit time.</span></span> <span data-ttu-id="0c037-135">En este caso, puede ser necesaria lógica de reintento.</span><span class="sxs-lookup"><span data-stu-id="0c037-135">In this case, retry logic may be required.</span></span>  
  
 <span data-ttu-id="0c037-136">Para obtener más información, vea la sección sobre transacciones entre contenedores en [los niveles de aislamiento de transacción](../../2014/database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0c037-136">For more information, see the section on Cross-Container Transactions in [Transaction Isolation Levels](../../2014/database-engine/transaction-isolation-levels.md).</span></span>  
  
## <a name="implementing-retry-logic"></a><span data-ttu-id="0c037-137">Implementar lógica de reintento</span><span class="sxs-lookup"><span data-stu-id="0c037-137">Implementing Retry Logic</span></span>  
 <span data-ttu-id="0c037-138">Como ocurre con todas las transacciones que tienen acceso a tablas optimizadas para memoria, se debe considerar el uso de lógica de reintentos para controlar los posibles errores, como conflictos de escritura (código de error 41302) o errores de dependencia (código de error 41301).</span><span class="sxs-lookup"><span data-stu-id="0c037-138">As with all transactions that access memory-optimized tables, you need to consider retry logic to handle potential failures, such as write conflicts (error code 41302) or dependency failures (error code 41301).</span></span> <span data-ttu-id="0c037-139">En la mayoría de las aplicaciones la tasa de error será baja, pero sigue siendo necesario controlar los errores reintentando la transacción.</span><span class="sxs-lookup"><span data-stu-id="0c037-139">In most applications the failure rate will be low, but it is still necessary to handle failures by retrying the transaction.</span></span> <span data-ttu-id="0c037-140">He aquí dos maneras sugeridas de implementar lógica de reintentos:</span><span class="sxs-lookup"><span data-stu-id="0c037-140">Two suggested ways of implementing retry logic are:</span></span>  
  
-   <span data-ttu-id="0c037-141">Reintentos del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="0c037-141">Client-side retries.</span></span> <span data-ttu-id="0c037-142">Los intentos del lado cliente son la mejor manera de implementar lógica de reintentos en el caso general.</span><span class="sxs-lookup"><span data-stu-id="0c037-142">Client-side retries is the preferred way to implement retry logic in the general case.</span></span> <span data-ttu-id="0c037-143">La aplicación cliente detecta el error producido por la transacción y reintenta la transacción.</span><span class="sxs-lookup"><span data-stu-id="0c037-143">The client application catches the error thrown by the transaction, and retries the transaction.</span></span> <span data-ttu-id="0c037-144">Si una aplicación cliente existente tiene lógica de reintentos para controlar los interbloqueos, puede ampliar la aplicación para controlar los nuevos códigos de error.</span><span class="sxs-lookup"><span data-stu-id="0c037-144">If an existing client application has retry logic to handle deadlocks, you can extend the application to handle the new error codes.</span></span>  
  
-   <span data-ttu-id="0c037-145">Mediante un procedimiento almacenado contenedor.</span><span class="sxs-lookup"><span data-stu-id="0c037-145">Using a wrapper stored procedure.</span></span> <span data-ttu-id="0c037-146">El cliente llama a un procedimiento almacenado de [!INCLUDE[tsql](../includes/tsql-md.md)] interpretado que llama al procedimiento almacenado compilado de forma nativa o ejecuta la transacción.</span><span class="sxs-lookup"><span data-stu-id="0c037-146">The client calls an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that calls the natively compiled stored procedure or executes the transaction.</span></span> <span data-ttu-id="0c037-147">Después, el procedimiento contenedor usa lógica try/catch para detectar el error y reintentar la llamada al procedimiento si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0c037-147">The wrapper procedure then uses try/catch logic to catch the error and retry the procedure call if needed.</span></span> <span data-ttu-id="0c037-148">Es posible que se devuelvan resultados al cliente antes del error y que el cliente no sepa cómo descartarlos.</span><span class="sxs-lookup"><span data-stu-id="0c037-148">It is possible that results are returned to the client before the failure, and the client would not know to discard them.</span></span> <span data-ttu-id="0c037-149">Por tanto, para estar seguros, es mejor usar este método solo con procedimientos almacenados compilados de forma nativa que no devuelven ningún conjunto de resultados al cliente.</span><span class="sxs-lookup"><span data-stu-id="0c037-149">Therefore, to be safe, it is best to use this method only with natively compiled stored procedures that do not return any result sets to the client.</span></span>  
  
 <span data-ttu-id="0c037-150">La lógica de reintento se puede implementar en [!INCLUDE[tsql](../includes/tsql-md.md)] o en el código de aplicación en el nivel medio.</span><span class="sxs-lookup"><span data-stu-id="0c037-150">The retry logic can be implemented either in [!INCLUDE[tsql](../includes/tsql-md.md)] or in the application code in the mid-tier.</span></span>  
  
 <span data-ttu-id="0c037-151">Dos posibles razones para considerar la lógica de reintento son:</span><span class="sxs-lookup"><span data-stu-id="0c037-151">Two possible reasons to consider the retry logic are:</span></span>  
  
-   <span data-ttu-id="0c037-152">La aplicación cliente tiene lógica de reintento para otros códigos de error, como 1205, que puede ampliar.</span><span class="sxs-lookup"><span data-stu-id="0c037-152">The client application has retry logic for other error codes, such as 1205, which you can extend.</span></span>  
  
-   <span data-ttu-id="0c037-153">Los conflictos son raros y es importante reducir la latencia de un extremo a otro mediante la ejecución preparada.</span><span class="sxs-lookup"><span data-stu-id="0c037-153">Conflicts are rare, and it is important to reduce end-to-end latency by using prepared execution.</span></span> <span data-ttu-id="0c037-154">Para obtener más información sobre la ejecución directa de procedimientos almacenados compilados de forma nativa, vea [procedimientos almacenados compilados](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md)de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="0c037-154">For more information about executing natively compiled stored procedures directly, see [Natively Compiled Stored Procedures](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="0c037-155">En el siguiente ejemplo se muestra la lógica de reintento de un procedimiento almacenado de [!INCLUDE[tsql](../includes/tsql-md.md)] interpretado que contiene una llamada a un procedimiento almacenado compilado de forma nativa o a una transacción entre contenedores.</span><span class="sxs-lookup"><span data-stu-id="0c037-155">The following sample shows retry logic in an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that contains a call either to a natively compiled stored procedure or to a cross-container transaction.</span></span>  
  
```sql  
CREATE PROCEDURE usp_my_procedure @param1 type1, @param2 type2, ...  
AS  
BEGIN  
  -- number of retries - tune based on the workload  
  DECLARE @retry INT = 10  
  
  WHILE (@retry > 0)  
  BEGIN  
    BEGIN TRY  
  
      -- exec usp_my_native_proc @param1, @param2, ...  
  
      --       or  
  
      -- BEGIN TRANSACTION  
      --   ...  
      -- COMMIT TRANSACTION  
  
      SET @retry = 0  
    END TRY  
    BEGIN CATCH  
      SET @retry -= 1  
  
      -- the error number for deadlocks (1205) does not need to be included for   
      -- transactions that do not access disk-based tables  
      IF (@retry > 0 AND error_number() in (41302, 41305, 41325, 41301, 1205))  
      BEGIN  
        -- these error conditions are transaction dooming - rollback the transaction  
        -- this is not needed if the transaction spans a single native proc execution  
        --   as the native proc will simply rollback when an error is thrown   
        IF XACT_STATE() = -1  
          ROLLBACK TRANSACTION  
  
        -- use a delay if there is a high rate of write conflicts (41302)  
        --   length of delay should depend on the typical duration of conflicting transactions  
        -- WAITFOR DELAY '00:00:00.001'  
      END  
      ELSE  
      BEGIN  
        -- insert custom error handling for other error conditions here  
  
        -- throw if this is not a qualifying error condition  
        ;THROW  
      END  
    END CATCH  
  END  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c037-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c037-156">See Also</span></span>  
 <span data-ttu-id="0c037-157">[Descripción de las transacciones en tablas optimizadas para memoria](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="0c037-157">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="0c037-158">[Transacciones en tablas con optimización para memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="0c037-158">[Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="0c037-159">Instrucciones para los niveles de aislamiento de transacciones con tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="0c037-159">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md)  
  
  
