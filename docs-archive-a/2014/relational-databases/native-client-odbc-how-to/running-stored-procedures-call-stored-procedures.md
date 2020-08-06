---
title: Llamar a procedimientos almacenados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: rothja
ms.author: jroth
ms.openlocfilehash: d98d623dbbb4701bb59c95df502d0063d528d0d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672931"
---
# <a name="call-stored-procedures-odbc"></a><span data-ttu-id="937a6-102">Llamar a procedimientos almacenados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="937a6-102">Call Stored Procedures (ODBC)</span></span>
  <span data-ttu-id="937a6-103">Cuando una instrucción SQL llama a un procedimiento almacenado mediante la cláusula de escape ODBC CALL, el controlador Microsoft SQL Server envía el procedimiento a SQL Server mediante el mecanismo de llamada a procedimiento almacenado remoto (RPC).</span><span class="sxs-lookup"><span data-stu-id="937a6-103">When a SQL statement calls a stored procedure using the ODBC CALL escape clause, the Microsoft SQL Server driver sends the procedure to SQL Server using the remote stored procedure call (RPC) mechanism.</span></span> <span data-ttu-id="937a6-104">Las solicitudes de RPC omiten gran parte del análisis de la instrucción y del procesamiento del parámetro en SQL Server, y es más rápido que usar la instrucción Transact-SQL EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="937a6-104">RPC requests bypass much of the statement parsing and parameter processing in SQL Server and are faster than using the Transact-SQL EXECUTE statement.</span></span>  
  
 <span data-ttu-id="937a6-105">Para obtener una aplicación de ejemplo que muestra esta característica, vea [procesar códigos de retorno y parámetros de salida &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="937a6-105">For a sample application that demonstrates this feature, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
### <a name="to-run-a-procedure-as-an-rpc"></a><span data-ttu-id="937a6-106">Para ejecutar un procedimiento como una RPC</span><span class="sxs-lookup"><span data-stu-id="937a6-106">To run a procedure as an RPC</span></span>  
  
1.  <span data-ttu-id="937a6-107">Cree una instrucción SQL que use la secuencia de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="937a6-107">Construct a SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="937a6-108">La instrucción usa marcadores de parámetros para cada parámetro de entrada, de entrada/salida y de salida, así como para el valor devuelto por el procedimiento (si existe):</span><span class="sxs-lookup"><span data-stu-id="937a6-108">The statement uses parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any):</span></span>  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  <span data-ttu-id="937a6-109">Llame a [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) para cada parámetro de entrada, de entrada/salida y de salida, así como para el valor devuelto por el procedimiento (si existe).</span><span class="sxs-lookup"><span data-stu-id="937a6-109">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="937a6-110">Ejecute la instrucción con [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="937a6-110">Execute the statement with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="937a6-111">Si una aplicación envía un procedimiento con la sintaxis de Transact-SQL EXECUTE (en contraposición al flujo de escape ODBC CALL), el controlador ODBC de SQL Server pasa la llamada al procedimiento a SQL Server como una instrucción SQL en lugar de como una RPC.</span><span class="sxs-lookup"><span data-stu-id="937a6-111">If an application submits a procedure using the Transact-SQL EXECUTE syntax (as opposed to the ODBC CALL escape sequence), the SQL Server ODBC driver passes the procedure call to SQL Server as a SQL statement rather than as an RPC.</span></span> <span data-ttu-id="937a6-112">Además, los parámetros de salida no se devuelven si se usa la instrucción Transact-SQL EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="937a6-112">Also, output parameters are not returned if the Transact-SQL EXECUTE statement is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937a6-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="937a6-113">See Also</span></span>  
 <span data-ttu-id="937a6-114">[Temas de procedimientos de ejecución de procedimientos almacenados &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="937a6-114">[Running Stored Procedures How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="937a6-115">[Procesar por lotes las llamadas a procedimientos almacenados](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span><span class="sxs-lookup"><span data-stu-id="937a6-115">[Batching Stored Procedure Calls](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span></span>  
 <span data-ttu-id="937a6-116">[Ejecutar procedimientos almacenados](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="937a6-116">[Running Stored Procedures](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span></span>  
 <span data-ttu-id="937a6-117">[Llamar a un procedimiento almacenado](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="937a6-117">[Calling a Stored Procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="937a6-118">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="937a6-118">Procedures</span></span>](../native-client-odbc-queries/executing-statements/procedures.md)  
  
  
