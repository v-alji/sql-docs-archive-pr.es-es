---
title: Usar System. Transactions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TransactionScope class
- Dispose method
- System.Transactions namespace
ms.assetid: 79656ce5-ce46-4c5e-9540-cf9869bd774b
author: rothja
ms.author: jroth
ms.openlocfilehash: 277edd75ea0437dc532ed5672e3c7b8a0569af8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751182"
---
# <a name="using-systemtransactions"></a><span data-ttu-id="ac9f7-102">Utilizar System.Transactions</span><span class="sxs-lookup"><span data-stu-id="ac9f7-102">Using System.Transactions</span></span>
  <span data-ttu-id="ac9f7-103">El espacio de nombres `System.Transactions` proporciona un nuevo marco de transacciones totalmente integrado con ADO.NET y la característica de integración con Common Language Runtime (CLR) en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac9f7-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="ac9f7-104">La clase `System.Transactions.TransactionScope` crea un bloque de código transaccional dando de alta implícitamente las conexiones en una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-104">The `System.Transactions.TransactionScope` class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="ac9f7-105">Se debe llamar al método `Complete` al final del bloque de código marcado por `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-105">You must call the `Complete` method at the end of the code block marked by the `TransactionScope`.</span></span> <span data-ttu-id="ac9f7-106">Se llama al método `Dispose` cuando la ejecución de programas deja un bloque de código, lo que hace que se interrumpa la transacción si no se llama al método `Complete`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-106">The `Dispose` method is invoked when program execution leaves a code block, causing the transaction to be discontinued if the `Complete` method is not called.</span></span> <span data-ttu-id="ac9f7-107">Si se ha producido una excepción que hace que el código deje el ámbito, se considera que la transacción se ha interrumpido.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-107">If an exception has been thrown that causes the code to leave scope, the transaction is considered to be discontinued.</span></span>  
  
 <span data-ttu-id="ac9f7-108">Se recomienda emplear un bloque `using` para asegurarse de que se llama al método `Dispose` en el objeto `TransactionScope` cuando se sale del bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-108">We recommend that you employ a `using` block to ensure that the `Dispose` method is called on the `TransactionScope` object when the `using` block is exited.</span></span> <span data-ttu-id="ac9f7-109">El hecho de no confirmar o revertir las transacciones pendientes puede reducir significativamente el rendimiento, porque el tiempo de espera predeterminado para `TransactionScope` es un minuto.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-109">Failure to commit or roll back pending transactions can seriously degrade performance because the default time-out for the `TransactionScope` is one minute.</span></span> <span data-ttu-id="ac9f7-110">Si no utiliza una instrucción `using`, debe realizar todo el trabajo de un bloque `Try` y llamar explícitamente al método `Dispose` del bloque `Finally`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-110">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the `Dispose` method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="ac9f7-111">Si se produce una excepción dentro de `TransactionScope`, la transacción se marca como incoherente y se abandona.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-111">If an exception occurs within the `TransactionScope`, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="ac9f7-112">Se revierte cuando se elimina `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-112">It is rolled back when the `TransactionScope` is disposed.</span></span> <span data-ttu-id="ac9f7-113">Si no se produce ninguna excepción, las transacciones participantes se confirman.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-113">If no exception occurs, participating transactions commit.</span></span>  
  
 <span data-ttu-id="ac9f7-114">Se debe utilizar `TransactionScope` solamente cuando se tiene acceso a orígenes de datos locales y remotos o a administradores de recursos externos.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-114">`TransactionScope` should be used only when local and remote data sources or external resource managers are being accessed.</span></span> <span data-ttu-id="ac9f7-115">Esto se debe a que `TransactionScope` siempre hace que se promuevan las transacciones, aunque solo se esté utilizando dentro de una conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-115">This is because `TransactionScope` always causes transactions to promote, even if it is being used only within a context connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac9f7-116">La clase `TransactionScope` crea una transacción con `System.Transactions.Transaction.IsolationLevel` de `Serializable` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-116">The `TransactionScope` class creates a transaction with a `System.Transactions.Transaction.IsolationLevel` of `Serializable` by default.</span></span> <span data-ttu-id="ac9f7-117">Dependiendo de la aplicación, puede considerar la opción de reducir el nivel de aislamiento para evitar conflictos en ella.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-117">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac9f7-118">Se recomienda realizar solo actualizaciones, inserciones, y eliminaciones dentro de las transacciones distribuidas en servidores remotos porque consumen una gran cantidad de recursos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-118">We recommend that you perform only updates, inserts, and deletes within distributed transactions against remote servers because they consume significant database resources.</span></span> <span data-ttu-id="ac9f7-119">Si la operación se va a realizar en el servidor local, no hace falta una transacción distribuida y bastará con una transacción local.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-119">If the operation is going to be performed on the local server, a distributed transaction is not necessary and a local transaction will suffice.</span></span> <span data-ttu-id="ac9f7-120">Las instrucciones SELECT pueden bloquear innecesariamente los recursos de la base de datos y, en algunas situaciones, puede que sea necesario utilizar transacciones para las mismas.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-120">SELECT statements may lock database resources unnecessarily, and in some scenarios it may be necessary to use transactions for selects.</span></span> <span data-ttu-id="ac9f7-121">Cualquier trabajo no relacionado con la base de datos se debe llevar a cabo fuera del ámbito de la transacción, a menos que implique a otros administradores de recursos con transacciones.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-121">Any non-database work should be done outside of the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="ac9f7-122">Aunque una excepción dentro del ámbito de la transacción impide que se confirme la transacción, la clase `TransactionScope` no tiene medios para revertir los cambios que haya realizado el código fuera del ámbito de la propia transacción.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-122">Although an exception within the scope of the transaction prevents the transaction from committing, the `TransactionScope` class has no provision for rolling back any changes your code has made outside of the scope of the transaction itself.</span></span> <span data-ttu-id="ac9f7-123">Si tiene que realizar alguna acción cuando se revierte la transacción, debe escribir su propia implementación de la interfaz `System.Transactions.IEnlistmentNotification` y dar de alta explícitamente la transacción.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-123">If you need to take some action when the transaction is rolled back, you must write your own implementation of the `System.Transactions.IEnlistmentNotification` interface, and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac9f7-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac9f7-124">Example</span></span>  
 <span data-ttu-id="ac9f7-125">Para trabajar con `System.Transactions`, debe tener una referencia al archivo System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-125">To work with `System.Transactions`, you must have a reference to the System.Transactions.dll file.</span></span>  
  
 <span data-ttu-id="ac9f7-126">El código siguiente muestra cómo crear una transacción que se puede promover en dos instancias diferentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac9f7-126">The following code demonstrates how to create a transaction that can be promoted against two different instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac9f7-127">Estas instancias están representadas por dos objetos `System.Data.SqlClient.SqlConnection` diferentes, que se incluyen en un bloque `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-127">These instances are represented by two different `System.Data.SqlClient.SqlConnection` objects, which are wrapped in a `TransactionScope` block.</span></span> <span data-ttu-id="ac9f7-128">El código crea el bloque `TransactionScope` con una instrucción `using` y abre la primera conexión, que automáticamente lo da de alta en `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-128">The code creates the `TransactionScope` block with a `using` statement, and opens the first connection, which automatically enlists it in the `TransactionScope`.</span></span> <span data-ttu-id="ac9f7-129">La transacción se da de alta inicialmente como una transacción ligera, no como una transacción distribuida completa.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-129">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="ac9f7-130">El código supone la existencia de lógica condicional (que se ha omitido por razones de brevedad).</span><span class="sxs-lookup"><span data-stu-id="ac9f7-130">The code assumes the existence of conditional logic (which has been omitted for brevity).</span></span> <span data-ttu-id="ac9f7-131">Solo abre la segunda conexión si es necesario, dándola de alta en `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-131">It opens the second connection only if it is needed, enlisting it in the `TransactionScope`.</span></span> <span data-ttu-id="ac9f7-132">Cuando se abre la conexión, la transacción se promueve automáticamente a una transacción distribuida completa.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-132">When the connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="ac9f7-133">El código llama entonces a `TransactionScope.Complete`, que confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-133">The code then invokes `TransactionScope.Complete`, which commits the transaction.</span></span> <span data-ttu-id="ac9f7-134">El código elimina las dos conexiones al salir de las instrucciones `using` para las conexiones.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-134">The code disposes of the two connections when exiting the `using` statements for the connections.</span></span> <span data-ttu-id="ac9f7-135">Se llama automáticamente al método `TransactionScope.Dispose` para `TransactionScope` a la terminación del bloque `using` para `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-135">The `TransactionScope.Dispose` method for the `TransactionScope` is automatically called at the termination of the `using` block for the `TransactionScope`.</span></span> <span data-ttu-id="ac9f7-136">Si se ha producido una excepción en algún punto del bloque `TransactionScope`, no se llama a `Complete` y la transacción distribuida se revertirá cuando se elimine `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="ac9f7-136">If an exception has been thrown at any point in the `TransactionScope` block, `Complete` does not get called, and the distributed transaction will roll back when the `TransactionScope` is disposed.</span></span>  
  
 <span data-ttu-id="ac9f7-137">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac9f7-137">Visual Basic</span></span>  
  
```  
Using transScope As New TransactionScope()  
    Using connection1 As New SqlConnection(connectString1)  
        ' Opening connection1 automatically enlists it in the   
        ' TransactionScope as a lightweight transaction.  
        connection1.Open()  
  
        ' Do work in the first connection.  
  
        ' Assumes conditional logic in place where the second  
        ' connection will only be opened as needed.  
        Using connection2 As New SqlConnection(connectString2)  
            ' Open the second connection, which enlists the   
            ' second connection and promotes the transaction to  
            ' a full distributed transaction.  
            connection2.Open()  
  
            ' Do work in the second connection.  
  
        End Using  
    End Using  
  
    ' Commit the transaction.  
    transScope.Complete()  
End Using  
```  
  
 <span data-ttu-id="ac9f7-138">C#</span><span class="sxs-lookup"><span data-stu-id="ac9f7-138">C#</span></span>  
  
```  
using (TransactionScope transScope = new TransactionScope())  
{  
    using (SqlConnection connection1 = new   
       SqlConnection(connectString1))  
    {  
        // Opening connection1 automatically enlists it in the   
        // TransactionScope as a lightweight transaction.  
        connection1.Open();  
  
        // Do work in the first connection.  
  
        // Assumes conditional logic in place where the second  
        // connection will only be opened as needed.  
        using (SqlConnection connection2 = new   
            SqlConnection(connectString2))  
        {  
            // Open the second connection, which enlists the   
            // second connection and promotes the transaction to  
            // a full distributed transaction.   
            connection2.Open();  
  
            // Do work in the second connection.  
        }  
    }  
    //  The Complete method commits the transaction.  
    transScope.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac9f7-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac9f7-139">See Also</span></span>  
 [<span data-ttu-id="ac9f7-140">Integración CLR y transacciones</span><span class="sxs-lookup"><span data-stu-id="ac9f7-140">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
