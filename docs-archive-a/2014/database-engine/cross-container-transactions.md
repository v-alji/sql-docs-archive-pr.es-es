---
title: Transacciones entre contenedores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5d84b51a-ec17-4c5c-b80e-9e994fc8ae80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28437f0903459616a574e713c0f138e8bb459870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673245"
---
# <a name="cross-container-transactions"></a><span data-ttu-id="b1d6f-102">Transacciones entre contenedores</span><span class="sxs-lookup"><span data-stu-id="b1d6f-102">Cross-Container Transactions</span></span>
  <span data-ttu-id="b1d6f-103">Las transacciones entre contenedores son transacciones de usuario implícitas o explícitas que incluyen llamadas a procedimientos almacenados compilados de forma nativa u operaciones en tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-103">Cross-container transactions are either implicit or explicit user transactions that include calls to natively-compiled stored procedures or operations on memory-optimized tables.</span></span>  
  
 <span data-ttu-id="b1d6f-104">En [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], las llamadas a procedimientos almacenados no inician una transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], calls to stored procedures do not initiate a transaction.</span></span> <span data-ttu-id="b1d6f-105">Las ejecuciones de procedimientos compilados de forma nativa en modo de confirmación automática (no en el contexto de una transacción de usuario) no se consideran transacciones entre contenedores.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-105">Executions of natively compiled procedures in autocommit mode (not in the context of a user transaction) are not considered cross-container transactions.</span></span>  
  
 <span data-ttu-id="b1d6f-106">Cualquier consulta interpretada que hace referencia a tablas optimizadas para memoria se considera parte de una transacción entre contenedores, tanto si se ejecuta desde una transacción explícita o implícita como si se ejecuta en modo de confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-106">Any interpreted query that references memory-optimized tables is considered a part of a cross-container transaction, whether executed from an explicit or implicit transaction or in auto-commit mode.</span></span>  
  
##  <a name="isolation-of-individual-operations"></a><a name="isolation"></a><span data-ttu-id="b1d6f-107">Aislamiento de operaciones individuales</span><span class="sxs-lookup"><span data-stu-id="b1d6f-107">Isolation of Individual Operations</span></span>  
 <span data-ttu-id="b1d6f-108">Cada transacción de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiene un nivel de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-108">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] transaction has an isolation level.</span></span> <span data-ttu-id="b1d6f-109">El nivel de aislamiento predeterminado es Lectura confirmada.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-109">The default isolation level is Read Committed.</span></span> <span data-ttu-id="b1d6f-110">Para usar un nivel de aislamiento diferente, puede establecer el nivel de aislamiento mediante [SET TRANSACTION ISOlation level &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1d6f-110">To use a different isolation level, you can set the isolation level using [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="b1d6f-111">Suele ser necesario realizar operaciones en tablas optimizadas para memoria en otro nivel de aislamiento diferente al de las operaciones en tablas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-111">It is often necessary to perform operations on memory-optimized tables at a different isolation level than operations on disk-based tables.</span></span> <span data-ttu-id="b1d6f-112">En una transacción, es posible establecer otro nivel de aislamiento diferente para una colección de instrucciones o para una operación de lectura individual.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-112">In a transaction, it is possible to set a different isolation level for a collection of statements or for an individual read operation.</span></span>  
  
### <a name="specifying-the-isolation-level-of-individual-operations"></a><span data-ttu-id="b1d6f-113">Especificar el nivel de aislamiento de operaciones individuales</span><span class="sxs-lookup"><span data-stu-id="b1d6f-113">Specifying the Isolation Level of Individual Operations</span></span>  
 <span data-ttu-id="b1d6f-114">Para establecer otro nivel de aislamiento para un conjunto de instrucciones de una transacción, puede utilizar `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-114">To set a different isolation level for a set of statements in a transaction, you can use `SET TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="b1d6f-115">En el siguiente ejemplo de una transacción se utiliza el nivel de aislamiento serializable como predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-115">The following example of a transaction uses the serializable isolation level as default.</span></span> <span data-ttu-id="b1d6f-116">Las operaciones de inserción y selección en t3, t2 y t1 se ejecutan con aislamiento de lectura repetible.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-116">The insert and select operations on t3, t2, and t1 are executed under repeatable read isolation.</span></span>  
  
```sql  
set transaction isolation level serializable  
go  
  
begin transaction  
 ......  
  set transaction isolation level repeatable read  
  
  insert t3 select * from t1 join t2 on t1.id=t2.id  
  
  set transaction isolation level serializable  
 ......  
commit  
```  
  
 <span data-ttu-id="b1d6f-117">Para establecer un nivel de aislamiento para las operaciones de lectura individuales distinto del predeterminado de la transacción, puede usar una sugerencia de tabla (por ejemplo, serializable).</span><span class="sxs-lookup"><span data-stu-id="b1d6f-117">To set an isolation level for individual read operations that is different from the transaction default, you can use a table hint (for example, serializable).</span></span> <span data-ttu-id="b1d6f-118">Cada selección corresponde a una operación de lectura y cada actualización y eliminación corresponde a una lectura, ya que la fila siempre tiene que leerse para que se pueda actualizar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-118">Every select corresponds to a read operation and every update and every delete corresponds to a read, because the row always needs to be read before it can be updated or deleted.</span></span> <span data-ttu-id="b1d6f-119">Las operaciones de inserción no tienen un nivel de aislamiento porque las lecturas se aíslan siempre en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1d6f-119">Insert operations do not have an isolation level, because writes are always isolated in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b1d6f-120">En el ejemplo siguiente, el nivel de aislamiento predeterminado para la transacción es de lectura confirmada pero se tiene acceso a la tabla t1 con un aislamiento serializable y a t2 con aislamiento de instantánea.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-120">In the following example, the default isolation level for the transaction is read committed, but table t1 is accessed under serializable and t2 under snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
 ......  
  
  insert t3 select * from t1 (serializable) join t2 (snapshot) on t1.id=t2.id  
  
  ......  
commit  
```  
  
### <a name="isolation-semantics-for-individual-operations"></a><span data-ttu-id="b1d6f-121">Semántica de aislamiento para operaciones individuales</span><span class="sxs-lookup"><span data-stu-id="b1d6f-121">Isolation Semantics for Individual Operations</span></span>  
 <span data-ttu-id="b1d6f-122">Una transacción T serializable se ejecuta en aislamiento completo.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-122">A serializable transaction T is executed in complete isolation.</span></span> <span data-ttu-id="b1d6f-123">Es como si otra transacción se ha confirmado antes de que se iniciara T o se ha iniciado después confirmarse T.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-123">It is as if every other transaction has either committed before T started, or is started after T committed.</span></span> <span data-ttu-id="b1d6f-124">Se vuelve más compleja cuando operaciones diferentes en una transacción tienen niveles de aislamiento distintos.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-124">It becomes more complex when different operations in a transaction have different isolation levels.</span></span>  
  
 <span data-ttu-id="b1d6f-125">La semántica general de los niveles de aislamiento de transacción en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , junto con las implicaciones en el bloqueo, se explica en [SET TRANSACTION ISOLATION LEVEL &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1d6f-125">The general semantics of the transaction isolation levels in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], along with the implications on locking, is explained in [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="b1d6f-126">En el caso de transacciones entre contenedores en las que diferentes operaciones pueden tener niveles de aislamiento distintos, debe comprender la semántica del aislamiento de las operaciones de lectura individuales.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-126">For cross-container transactions where different operations may have different isolation levels, you need to understand the semantics of isolation of individual read operations.</span></span> <span data-ttu-id="b1d6f-127">Las operaciones de escritura se aíslan siempre.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-127">Write operations are always isolated.</span></span> <span data-ttu-id="b1d6f-128">Las escrituras de transacciones diferentes no pueden verse afectadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-128">Writes in different transactions cannot impact each other.</span></span>  
  
 <span data-ttu-id="b1d6f-129">Una operación de lectura de datos devuelve varias filas que satisfacen una condición de filtro.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-129">A data read operation returns a number of rows that satisfy a filter condition.</span></span>  
  
 <span data-ttu-id="b1d6f-130">Las lecturas se realizan como parte de una transacción T. los niveles de aislamiento para las operaciones de lectura se pueden entender en términos de,</span><span class="sxs-lookup"><span data-stu-id="b1d6f-130">Reads are performed as part of a transaction T. Isolation levels for read operations can be understood in terms of,</span></span>  
  
 <span data-ttu-id="b1d6f-131">Estado de confirmación</span><span class="sxs-lookup"><span data-stu-id="b1d6f-131">Commit Status</span></span>  
 <span data-ttu-id="b1d6f-132">El estado de confirmación se refiere a si se garantiza que la lectura de los datos se va a confirmar.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-132">Commit status refers to whether the data read is guaranteed to be committed.</span></span>  
  
 <span data-ttu-id="b1d6f-133">Coherencia (Transaccional)</span><span class="sxs-lookup"><span data-stu-id="b1d6f-133">(Transactional) Consistency</span></span>  
 <span data-ttu-id="b1d6f-134">La coherencia transaccional para un conjunto de lecturas se refiere a si se garantiza que todas las lecturas de versiones de fila incluirán actualizaciones del mismo conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-134">Transactional consistency for a set of reads refers to whether the row versions read are all guaranteed to include updates from precisely the same set of transactions.</span></span>  
  
 <span data-ttu-id="b1d6f-135">La estabilidad garantiza que el sistema informa a la transacción T acerca de la lectura de los datos.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-135">Stability guarantees the system gives to transaction T about the data read.</span></span>  
 <span data-ttu-id="b1d6f-136">La estabilidad hace referencia a si las lecturas de la transacción son repetibles.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-136">Stability refers to whether the transaction's reads are repeatable.</span></span> <span data-ttu-id="b1d6f-137">Es decir, si las lecturas se repitieran, ¿devolverían las mismas filas y versiones de fila?</span><span class="sxs-lookup"><span data-stu-id="b1d6f-137">That is, if the reads were repeated would they return the same rows and row versions?</span></span>  
  
 <span data-ttu-id="b1d6f-138">Algunas garantías hacen referencia a la hora de finalización lógica de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-138">Certain guarantees refer to the logical end time of the transaction.</span></span> <span data-ttu-id="b1d6f-139">En general, la hora de finalización lógica es aquella en que la transacción se confirma en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-139">In general, the logical end time is the time the transaction is committed to the database.</span></span> <span data-ttu-id="b1d6f-140">Si la transacción tiene acceso a tablas optimizadas para memoria, la hora de finalización lógica es técnicamente el principio de la fase de validación.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-140">If memory-optimized tables are accessed by the transaction, the logical end time is technically the beginning of the validation phase.</span></span> <span data-ttu-id="b1d6f-141">(Para obtener más información, vea la descripción de la duración de las transacciones en las [transacciones en tablas optimizadas para memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b1d6f-141">(For more information, see the transaction lifetime discussion in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="b1d6f-142">Independientemente del nivel de aislamiento, una transacción (T) siempre ve sus propias actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="b1d6f-142">Regardless of isolation level, a transaction (T) always sees its own updates:</span></span>  
  
 <span data-ttu-id="b1d6f-143">READ UNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="b1d6f-143">READ UNCOMMITTED</span></span>  
 <span data-ttu-id="b1d6f-144">La lectura de datos no se puede confirmar, no es coherente ni es estable.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-144">The data read may neither be committed, consistent, or stable.</span></span> <span data-ttu-id="b1d6f-145">Sin embargo, incluirá las operaciones de escritura anteriores realizadas por T.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-145">However, it will include earlier write operations done by T.</span></span>  
  
 <span data-ttu-id="b1d6f-146">READ COMMITTED</span><span class="sxs-lookup"><span data-stu-id="b1d6f-146">READ COMMITTED</span></span>  
 <span data-ttu-id="b1d6f-147">La lectura de datos se confirmará.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-147">The data read will be committed.</span></span>  
  
 <span data-ttu-id="b1d6f-148">SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="b1d6f-148">SNAPSHOT</span></span>  
 <span data-ttu-id="b1d6f-149">Todas las operaciones de lectura realizadas por T con aislamiento de instantánea tienen la misma hora de lectura lógica, que es el inicio de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-149">All read operations performed by T under snapshot isolation have the same logical read time, which is the beginning of the transaction.</span></span> <span data-ttu-id="b1d6f-150">Se garantiza que la lectura de los datos se confirma y es coherente en la hora de lectura lógica.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-150">The data read is guaranteed to be committed and consistent as of the logical read time.</span></span> <span data-ttu-id="b1d6f-151">Se garantiza que si se repite una lectura tal y como está en la hora de lectura original, se devuelve el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-151">Repeating a read as of the original read time is guaranteed to return the same result.</span></span>  
  
 <span data-ttu-id="b1d6f-152">REPEATABLE READ</span><span class="sxs-lookup"><span data-stu-id="b1d6f-152">REPEATABLE READ</span></span>  
 <span data-ttu-id="b1d6f-153">Se garantiza que la lectura de datos se confirma y es estable hasta la hora de finalización lógica de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-153">The data read is guaranteed to be committed and stable up to the logical end time of the transaction.</span></span>  
  
 <span data-ttu-id="b1d6f-154">SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="b1d6f-154">SERIALIZABLE</span></span>  
 <span data-ttu-id="b1d6f-155">Todas las garantías de la prevención y la coherencia de las transacciones de lectura REPETIble y la coherencia transaccional con respecto a todas las operaciones de lectura serializable realizadas por T. la prevención ficticia significa que la operación de examen solo puede devolver filas adicionales escritas por T, pero no filas escritas por otras transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-155">All guarantees of REPEATABLE READ plus phantom avoidance and transactional consistency with respect to all serializable read operations performed by T. Phantom avoidance means that the scan operation can only return additional rows that were written by T, but no rows that were written by other transactions.</span></span>  
  
 <span data-ttu-id="b1d6f-156">Considere la transacción siguiente,</span><span class="sxs-lookup"><span data-stu-id="b1d6f-156">Consider the following transaction,</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  -- remove all rows from t3; the related read operation is performed under read committed   
  -- isolation, as this is the default for the transaction  
  delete from t3  
  
  -- copy the contents from t1 to t3; the read on t1 is performed under the serializable   
  -- isolation level  
  insert t3 select * from t1 (serializable)  
  
  -- compare t3 and t1; note: the result set may not be empty, as rows may have been added   
  -- by other transaction before this select, due to the read committed isolation level  
  select * from t3 except t1  
  
  -- compare t1 and t3; note: the result set is empty, as no rows have been added to t1   
  -- since its contents were copied to t1, due to the serializable isolation level  
  select * from t1 except t3  
commit  
```  
  
 <span data-ttu-id="b1d6f-157">Esta transacción elimina todas las filas de la tabla t3 con aislamiento de lectura confirmada, copia todas las filas de t1 a t3 con aislamiento serializable y, a continuación, compara t1 y t3.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-157">This transaction deletes all rows from t3 under read committed isolation, copies all rows from t1 to t3 under serializable isolation, and then compares t1 and t3.</span></span> <span data-ttu-id="b1d6f-158">Se pueden haber agregado a t3 algunas filas (no de t1) porque la tabla se vació.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-158">Some rows [not in t1] may have been added to t3 since the table was emptied.</span></span> <span data-ttu-id="b1d6f-159">No se agregaron filas a t1 ya que la copia era serializable.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-159">No rows were added to t1 as the copy was serializable.</span></span>  
  
 <span data-ttu-id="b1d6f-160">Aunque la lectura desde t1 al final de la transacción sea una lectura sintácticamente confirmada, es en efecto serializable, porque la misma lectura se realizó antes en la transacción bajo aislamiento serializable: la seriabilidad garantiza que, si la lectura se realiza en algún punto posterior de la transacción, se devuelven las mismas filas.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-160">Although the read from t1 at the end of the transaction is syntactically read committed, it is effectively serializable, because the same read was performed earlier in the transaction under serializable isolation: serializability guarantees that if the read is performed at any later point in the transaction, the same rows are returned.</span></span>  
  
## <a name="cross-container-transactions-and-isolation-levels"></a><span data-ttu-id="b1d6f-161">Niveles de aislamiento y transacciones entre contenedores</span><span class="sxs-lookup"><span data-stu-id="b1d6f-161">Cross-Container Transactions and Isolation Levels</span></span>  
 <span data-ttu-id="b1d6f-162">Se puede considerar que una transacción entre contenedores tiene dos caras: una cara basada en disco (para las operaciones con tablas basadas en disco) y una cara optimizada para memoria (para las operaciones en tablas optimizadas para memoria).</span><span class="sxs-lookup"><span data-stu-id="b1d6f-162">A cross-container transaction can be seen as having two sides: a disk-based side (for operations on disk-based tables) and a memory-optimized side (for operations on memory-optimized tables).</span></span> <span data-ttu-id="b1d6f-163">Estas dos caras pueden tener niveles de aislamiento diferentes.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-163">These two sides may have different isolation levels.</span></span> <span data-ttu-id="b1d6f-164">De hecho, las operaciones de lectura individuales en cada cara pueden tener distintos niveles de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-164">In fact, individual read operations on each side may have different isolation levels.</span></span>  
  
 <span data-ttu-id="b1d6f-165">La cara basada en disco de una transacción T determinada alcanza un cierto nivel de aislamiento X si se cumple una de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1d6f-165">The disk-based side of a given transaction T reaches a certain isolation level X if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="b1d6f-166">Se inicia en X. Es decir, el valor predeterminado de la sesión era X, ya sea porque se ejecutó `SET TRANSACTION ISOLATION LEVEL` o es el [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-166">It starts in X. That is, the session default was X, either because you executed `SET TRANSACTION ISOLATION LEVEL`, or it is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default.</span></span>  
  
-   <span data-ttu-id="b1d6f-167">Durante la transacción, el nivel de aislamiento predeterminado se cambia a X con `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-167">During the transaction, the default isolation level is changed to X using `SET TRANSACTION ISOLATION LEVEL`.</span></span>  
  
-   <span data-ttu-id="b1d6f-168">Una operación de lectura en una tabla basada en disco se ejecuta en el nivel de aislamiento X, utilizando la sintaxis `WITH (X)`.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-168">A read operation on a disk-based table is executed under isolation level X, using the syntax `WITH (X)`.</span></span>  
  
 <span data-ttu-id="b1d6f-169">La cara optimizada para memoria de T alcanza un nivel de aislamiento Y si durante la ejecución de T cualquier operación de lectura en una tabla optimizada para memoria o cualquier procedimiento almacenado compilado de forma nativa se ejecuta bajo el nivel de aislamiento Y.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-169">The memory-optimized side of T reaches an isolation level Y if during execution of T, any read operation on a memory-optimized table or any natively compiled stored procedure is executed under isolation level Y.</span></span>  
  
 <span data-ttu-id="b1d6f-170">Considere, por ejemplo, la siguiente transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-170">Consider the following transaction as an example.</span></span> <span data-ttu-id="b1d6f-171">Aquí, t1 y t2 son tablas basadas en disco y t3 y t4 son tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-171">Here, t1 and t2 are disk-based tables and t3 and t4 are memory-optimized tables.</span></span>  
  
 <span data-ttu-id="b1d6f-172">La cara basada en disco de la transacción alcanza el nivel de aislamiento de lectura confirmada, ya que se inició en ese nivel.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-172">The disk-based side of the transaction reaches the isolation level read committed, because it starts in that level.</span></span> <span data-ttu-id="b1d6f-173">La cara basada en disco también alcanza el nivel de lectura repetible, ya que la primera operación de lectura se ejecuta en ese nivel de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-173">The disk-based side also reaches repeatable read, because the first read operation is executed under that isolation level.</span></span> <span data-ttu-id="b1d6f-174">La eliminación al final de la transacción se ejecuta en el nivel de aislamiento de lectura confirmada y, por tanto, no presenta un nuevo nivel de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-174">The delete at the end of the transaction is executed under read committed isolation level, and so does not introduce a new isolation level.</span></span>  
  
 <span data-ttu-id="b1d6f-175">La cara optimizada para memoria de la transacción puede alcanzar uno de dos niveles: si condition1 es true, llega al nivel serializable mientras que, si es false, la cara optimizada para memoria solo alcanza el aislamiento de instantánea.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-175">The memory-optimized side of the transaction can reach one of two levels: if condition1 is true, it reaches serializable, while if it is false, the memory-optimized side reaches only snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  select * from t1 (repeatableread)  
  
  if condition1 begin  
    insert t3 select * from t4 (serializable)  
  end  
  else begin  
    insert t3 select * from t4 (snapshot)  
  end  
  
  delete from t1  
commit  
```  
  
### <a name="supported-isolation-levels-for-cross-container-transactions"></a><span data-ttu-id="b1d6f-176">Niveles de aislamiento admitidos para transacciones entre contenedores</span><span class="sxs-lookup"><span data-stu-id="b1d6f-176">Supported Isolation Levels for Cross-Container Transactions</span></span>  
 <span data-ttu-id="b1d6f-177">Hay ciertas limitaciones en cuanto a los niveles de aislamiento utilizados con las operaciones en tablas optimizadas para memoria en transacciones entre contenedores.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-177">There are limitations on the isolation levels used with operations on memory-optimized tables in cross-container transactions.</span></span>  
  
 <span data-ttu-id="b1d6f-178">Las tablas con optimización para memoria admiten los niveles de aislamiento SNAPSHOT, REPEATABLE READ y SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-178">Memory-optimized tables support the isolation levels SNAPSHOT, REPEATABLE READ, and SERIALIZABLE.</span></span> <span data-ttu-id="b1d6f-179">Para las transacciones de confirmación automática, las tablas optimizadas para memoria admiten el nivel de aislamiento READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-179">For autocommit transactions, memory-optimized tables support the isolation level READ COMMITTED.</span></span>  
  
 <span data-ttu-id="b1d6f-180">Se admiten los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1d6f-180">The following scenarios are supported:</span></span>  
  
-   <span data-ttu-id="b1d6f-181">Las transacciones entre contenedores READ UNCOMMITTED, READ COMMITTED y READ_COMMITTED_SNAPSHOT pueden tener acceso a tablas optimizadas para memoria con el aislamiento SNAPSHOT, REPEATABLE READ y SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-181">READ UNCOMMITTED, READ COMMITTED, and READ_COMMITTED_SNAPSHOT cross-container transactions can access memory-optimized tables under SNAPSHOT, REPEATABLE READ, and SERIALIZABLE isolation.</span></span> <span data-ttu-id="b1d6f-182">La garantía de READ COMMITTED se mantiene para la transacción; todas las filas leídas por la transacción se han confirmado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-182">The READ COMMITTED guarantee holds for the transaction; all rows read by the transaction have been committed to the database.</span></span>  
  
-   <span data-ttu-id="b1d6f-183">Las transacciones REPEATABLE READ y SERIALIZABLE pueden tener acceso a tablas optimizadas para memoria con aislamiento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-183">REPEATABLE READ and SERIALIZABLE transactions can access memory-optimized tables under SNAPSHOT isolation.</span></span>  
  
## <a name="read-only-cross-container-transactions"></a><span data-ttu-id="b1d6f-184">Transacciones entre contenedores de solo lectura</span><span class="sxs-lookup"><span data-stu-id="b1d6f-184">Read-only Cross-Container Transactions</span></span>  
 <span data-ttu-id="b1d6f-185">La mayoría de las transacciones de solo lectura en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se revierten en el tiempo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-185">Most read-only transactions in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are rolled back at commit time.</span></span> <span data-ttu-id="b1d6f-186">Dado que no hay ningún cambio que confirmar en la base de datos, el sistema simplemente libera los recursos utilizados por la transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-186">Because there are no changes to commit to the database, the system simply frees the resources used by the transaction.</span></span> <span data-ttu-id="b1d6f-187">Para las transacciones basadas en disco de solo lectura, todos los bloqueos adoptados por la transacción se liberan en este momento.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-187">For read-only disk-based transactions, all locks taken by the transaction are released at this time.</span></span> <span data-ttu-id="b1d6f-188">Para las transacciones optimizadas para memoria de solo lectura que abarcan una sola ejecución de procedimiento compilado de forma nativa, no se realiza ninguna validación.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-188">For read-only memory-optimized transactions that span a single natively compiled procedure execution, no validation is performed.</span></span>  
  
 <span data-ttu-id="b1d6f-189">Las transacciones de solo lectura entre contenedores en modo de confirmación automática se revierten simplemente al final de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-189">Cross-container, read-only transactions in autocommit mode are simply rolled back at the end of the transaction.</span></span> <span data-ttu-id="b1d6f-190">No se realiza ninguna validación.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-190">No validation is performed.</span></span>  
  
 <span data-ttu-id="b1d6f-191">Las transacciones explícitas o implícitas de solo lectura entre contenedores realizan la validación en tiempo de confirmación si la transacción tiene acceso a tablas optimizadas para memoria en aislamiento REPEATABLE READ o SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="b1d6f-191">Explicit or implicit cross-container, read-only transactions perform validation at commit time if the transaction accesses memory-optimized tables under REPEATABLE READ or SERIALIZABLE isolation.</span></span> <span data-ttu-id="b1d6f-192">Para obtener más información sobre la validación, vea la sección sobre detección de conflictos, validación y comprobaciones de dependencias de confirmación en [transacciones en tablas optimizadas para memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b1d6f-192">For details about validation see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d6f-193">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1d6f-193">See Also</span></span>  
 <span data-ttu-id="b1d6f-194">[Descripción de las transacciones en tablas optimizadas para memoria](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="b1d6f-194">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="b1d6f-195">[Directrices para los niveles de aislamiento de transacción con tablas con optimización para memoria](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="b1d6f-195">[Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="b1d6f-196">Instrucciones para la lógica de reintento de transacciones en tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="b1d6f-196">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
  
