---
title: Obtener acceso a la transacción actual | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- current transaction access
- Current property
- Transaction class
ms.assetid: 1a4e2ce5-f627-4c81-8960-6a9968cefda2
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b7e67d30cb9d89a02eb918fcd03651b2915955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751201"
---
# <a name="accessing-the-current-transaction"></a><span data-ttu-id="26c5f-102">Obtener acceso a la transacción actual</span><span class="sxs-lookup"><span data-stu-id="26c5f-102">Accessing the Current Transaction</span></span>
  <span data-ttu-id="26c5f-103">Si una transacción se encuentra activa en el momento en que se escribe el código de Common Language Runtime (CLR) que se ejecuta en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la transacción se expone a través de la clase `System.Transactions.Transaction`.</span><span class="sxs-lookup"><span data-stu-id="26c5f-103">If a transaction is active at the point at which common language runtime (CLR) code running on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is entered, the transaction is exposed through the `System.Transactions.Transaction` class.</span></span> <span data-ttu-id="26c5f-104">La propiedad `Transaction.Current` permite obtener acceso a la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="26c5f-104">The `Transaction.Current` property is used to access the current transaction.</span></span> <span data-ttu-id="26c5f-105">En la mayoría de los casos, no es necesario obtener acceso a la transacción de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="26c5f-105">In most cases it is not necessary to access the transaction explicitly.</span></span> <span data-ttu-id="26c5f-106">Para las conexiones de bases de datos, ADO.NET comprueba `Transaction.Current` de forma automática cuando se llama al método `Connection.Open` y da de alta la conexión en esa transacción de forma transparente (a menos que la palabra clave `Enlist` esté establecida en False en la cadena de conexión).</span><span class="sxs-lookup"><span data-stu-id="26c5f-106">For database connections, ADO.NET checks `Transaction.Current` automatically when the `Connection.Open` method is called, and transparently enlists the connection in that transaction (unless the `Enlist` keyword is set to false in the connection string).</span></span>  
  
 <span data-ttu-id="26c5f-107">Es posible que desee usar directamente el objeto `Transaction` en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="26c5f-107">You might want to use the `Transaction` object directly in the following scenarios:</span></span>  
  
-   <span data-ttu-id="26c5f-108">Si desea dar de alta un recurso que no se da de alta de manera automática o que, por alguna razón, no se haya dado de alta durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="26c5f-108">If you want to enlist a resource that does not do automatic enlistment, or that for some reason was not enlisted during initialization.</span></span>  
  
-   <span data-ttu-id="26c5f-109">Si desea dar de alta un recurso de forma explícita en la transacción.</span><span class="sxs-lookup"><span data-stu-id="26c5f-109">If you want to explicitly enlist a resource in the transaction.</span></span>  
  
-   <span data-ttu-id="26c5f-110">Si desea finalizar la transacción externa desde el interior de su función o procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="26c5f-110">If you want to terminate the external transaction from within your stored procedure or function.</span></span> <span data-ttu-id="26c5f-111">En este caso, use <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="26c5f-111">In this case, you use <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="26c5f-112">Por ejemplo, el código siguiente revertirá la transacción actual:</span><span class="sxs-lookup"><span data-stu-id="26c5f-112">For example, the following code will rollback the current transaction:</span></span>  
  
    ```  
    using(TransactionScope transactionScope = new TransactionScope(TransactionScopeOptions.Required)) { }  
    ```  
  
 <span data-ttu-id="26c5f-113">En el resto de este tema se describen otras formas de cancelar una transacción externa.</span><span class="sxs-lookup"><span data-stu-id="26c5f-113">The rest of this topic describes other ways to cancel an external transaction.</span></span>  
  
## <a name="canceling-an-external-transaction"></a><span data-ttu-id="26c5f-114">Cancelar una transacción externa</span><span class="sxs-lookup"><span data-stu-id="26c5f-114">Canceling an External Transaction</span></span>  
 <span data-ttu-id="26c5f-115">Puede cancelar las transacciones externas de una función o de un procedimiento administrado de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="26c5f-115">You can cancel external transactions from a managed procedure or function in the following ways:</span></span>  
  
-   <span data-ttu-id="26c5f-116">La función o el procedimiento administrado puede devolver un valor utilizando un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="26c5f-116">The managed procedure or function can return a value by using an output parameter.</span></span> <span data-ttu-id="26c5f-117">El procedimiento [!INCLUDE[tsql](../../includes/tsql-md.md)] de llamada puede comprobar el valor devuelto y, si procede, ejecutar `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="26c5f-117">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can check the returned value and, if appropriate, execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="26c5f-118">La función o el procedimiento administrado puede iniciar una excepción personalizada.</span><span class="sxs-lookup"><span data-stu-id="26c5f-118">The managed procedure or function can throw a custom exception.</span></span> <span data-ttu-id="26c5f-119">El [!INCLUDE[tsql](../../includes/tsql-md.md)] procedimiento de llamada puede detectar la excepción producida por el procedimiento administrado o la función en un bloque try/catch y ejecutar `ROLLBACK TRANSACTION` .</span><span class="sxs-lookup"><span data-stu-id="26c5f-119">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can catch the exception thrown by the managed procedure or function in a try/catch block and execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="26c5f-120">La función o el procedimiento administrado puede cancelar la transacción actual llamando al método `Transaction.Rollback` si se cumple una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="26c5f-120">The managed procedure or function can cancel the current transaction by calling the `Transaction.Rollback` method if a certain condition is met.</span></span>  
  
 <span data-ttu-id="26c5f-121">Cuando se llama al método `Transaction.Rollback` dentro de una función o de un procedimiento administrado, éste inicia una excepción con un mensaje de error ambiguo y puede colocarse dentro de un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="26c5f-121">When it is called within a managed procedure or function, the `Transaction.Rollback` method throws an exception with an ambiguous error message and can be wrapped in a try/catch block.</span></span> <span data-ttu-id="26c5f-122">El mensaje de error puede ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="26c5f-122">The error message thresembles similar to the following:</span></span>  
  
```  
Msg 3994, Level 16, State 1, Procedure uspRollbackFromProc, Line 0  
Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting.  
```  
  
 <span data-ttu-id="26c5f-123">Se espera esta excepción y el bloque try/catch resulta necesario para que continúe la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="26c5f-123">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="26c5f-124">Sin el bloque try/catch, la excepción se iniciará inmediatamente en el procedimiento [!INCLUDE[tsql](../../includes/tsql-md.md)] de llamada y finalizará la ejecución del código administrado.</span><span class="sxs-lookup"><span data-stu-id="26c5f-124">Without the try/catch block, the exception will be immediately thrown to the calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure and managed code execution will finish.</span></span> <span data-ttu-id="26c5f-125">Cuando finaliza la ejecución del código administrado, se inicia otra excepción:</span><span class="sxs-lookup"><span data-stu-id="26c5f-125">When the managed code finishes execution, another exception is raised:</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure uspRollbackFromProc, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate " uspRollbackFromProc " has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting. The statement has been terminated.  
```  
  
 <span data-ttu-id="26c5f-126">También se espera esta excepción y, para continuar, debe incluir un bloque try/catch alrededor de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] que realiza la acción que activa el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="26c5f-126">This exception is also expected, and for execution to continue, you must have a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger.</span></span> <span data-ttu-id="26c5f-127">A pesar de las dos excepciones iniciadas, la transacción se revierte y no se confirman los cambios.</span><span class="sxs-lookup"><span data-stu-id="26c5f-127">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed.</span></span>  
  
### <a name="example"></a><span data-ttu-id="26c5f-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26c5f-128">Example</span></span>  
 <span data-ttu-id="26c5f-129">A continuación se muestra un ejemplo de una transacción que se revierte desde un procedimiento administrado mediante el uso del método `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="26c5f-129">The following is an example of a transaction being rolled back from a managed procedure by using the `Transaction.Rollback` method.</span></span> <span data-ttu-id="26c5f-130">Observe el bloque try/catch alrededor del método `Transaction.Rollback` en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="26c5f-130">Notice the try/catch block around the `Transaction.Rollback` method in the managed code.</span></span> <span data-ttu-id="26c5f-131">El script [!INCLUDE[tsql](../../includes/tsql-md.md)] crea un ensamblado y un procedimiento almacenado administrado.</span><span class="sxs-lookup"><span data-stu-id="26c5f-131">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates an assembly and managed stored procedure.</span></span> <span data-ttu-id="26c5f-132">Tenga en cuenta que la `EXEC uspRollbackFromProc` instrucción se ajusta en un bloque try/catch, de modo que la excepción que se produce cuando se completa el procedimiento administrado finaliza la ejecución se detecta.</span><span class="sxs-lookup"><span data-stu-id="26c5f-132">Be aware that the `EXEC uspRollbackFromProc` statement is wrapped in a try/catch block, so that the exception thrown when the managed procedure completes execution is caught.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspRollbackFromProc()  
{  
   using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
   {  
      // Open the connection.  
      connection.Open();  
  
      bool successCondition = true;  
  
      // Success condition is met.  
      if (successCondition)  
      {  
         SqlContext.Pipe.Send("Success condition met in procedure.");   
         // Perform other actions here.  
      }  
  
      //  Success condition is not met, the transaction will be rolled back.  
      else  
      {  
         SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...");  
         try  
         {  
               // Get the current transaction and roll it back.  
               Transaction trans = Transaction.Current;  
               trans.Rollback();  
         }  
         catch (SqlException ex)  
         {  
            // Catch the expected exception.   
            // This allows the connection to close correctly.                      
         }    
      }  
  
      // Close the connection.  
      connection.Close();  
   }  
}  
};  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  uspRollbackFromProc ()  
   Using connection As New SqlConnection("context connection=true")  
  
   ' Open the connection.  
   connection.Open()  
  
   Dim successCondition As Boolean  
   successCondition = False  
  
   ' Success condition is met.  
   If successCondition Then  
  
      SqlContext.Pipe.Send("Success condition met in procedure.")  
  
      ' Success condition is not met, the transaction will be rolled back.  
  
   Else  
      SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...")  
      Try  
         ' Get the current transaction and roll it back.  
         Dim trans As Transaction  
         trans = Transaction.Current  
         trans.Rollback()  
  
      Catch ex As SqlException  
         ' Catch the exception instead of throwing it.    
         ' This allows the connection to close correctly.                      
      End Try  
  
   End If  
  
   ' Close the connection.  
   connection.Close()  
  
End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="26c5f-133">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="26c5f-133">**Transact-SQL**</span></span>  
  
```  
--Register assembly.  
CREATE ASSEMBLY TestProcs FROM 'C:\Programming\TestProcs.dll'   
Go  
CREATE PROCEDURE uspRollbackFromProc AS EXTERNAL NAME TestProcs.StoredProcedures.uspRollbackFromProc  
Go  
  
-- Execute procedure.  
BEGIN TRY  
BEGIN TRANSACTION   
-- Perform other actions.  
Exec uspRollbackFromProc  
-- Perform other actions.  
PRINT N'Commiting transaction...'  
COMMIT TRANSACTION  
END TRY  
  
BEGIN CATCH  
SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
PRINT N'Exception thrown, rolling back transaction.'  
ROLLBACK TRANSACTION  
PRINT N'Transaction rolled back.'   
END CATCH  
Go  
  
-- Clean up.  
DROP Procedure uspRollbackFromProc;  
Go  
DROP ASSEMBLY TestProcs;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="26c5f-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26c5f-134">See Also</span></span>  
 [<span data-ttu-id="26c5f-135">Integración CLR y transacciones</span><span class="sxs-lookup"><span data-stu-id="26c5f-135">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
