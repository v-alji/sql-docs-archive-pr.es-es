---
title: Control de errores y mensajes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745290"
---
# <a name="handling-errors-and-messages"></a><span data-ttu-id="a46f0-102">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="a46f0-102">Handling Errors and Messages</span></span>
  <span data-ttu-id="a46f0-103">Cuando una aplicación llama a una función ODBC, el controlador ejecuta la función y devuelve información de diagnóstico de dos maneras: un código de retorno indica si la función ODBC se ha ejecutado o no correctamente en su totalidad, y los registros de diagnóstico proporcionan información detallada sobre la función.</span><span class="sxs-lookup"><span data-stu-id="a46f0-103">When an application calls an ODBC function, the driver executes the function and returns diagnostic information in two ways: A return code indicates the overall success or failure of an ODBC function, and diagnostic records provide detailed information about the function.</span></span> <span data-ttu-id="a46f0-104">Los registros de diagnóstico incluyen un registro de encabezado y registros de estado.</span><span class="sxs-lookup"><span data-stu-id="a46f0-104">Diagnostic records include a header record and status records.</span></span> <span data-ttu-id="a46f0-105">Por lo menos se devuelve un registro de diagnóstico, el registro de encabezado, aunque la función se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="a46f0-105">At least one diagnostic record, the header record, is returned even if the function succeeds.</span></span>  
  
 <span data-ttu-id="a46f0-106">La información de diagnóstico se usa en la fase de desarrollo para detectar errores de programación, como identificadores no válidos y errores de sintaxis en instrucciones SQL codificadas de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="a46f0-106">Diagnostic information is used at development time to catch programming errors, such as invalid handles and syntax errors in hard-coded SQL statements.</span></span> <span data-ttu-id="a46f0-107">También se utiliza en tiempo de ejecución para detectar errores y advertencias durante la ejecución, como truncamiento de datos, infracciones de reglas y errores de sintaxis en instrucciones SQL escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a46f0-107">It is also used at run time to catch run-time errors and warnings, such as data truncation, rule violations, and syntax errors in SQL statements entered by the user.</span></span> <span data-ttu-id="a46f0-108">La lógica del programa se suele basar en códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="a46f0-108">Program logic is generally based on return codes.</span></span>  
  
 <span data-ttu-id="a46f0-109">Por ejemplo, después de que una aplicación llama a **SQLFetch** para recuperar las filas de un conjunto de resultados, el código de retorno indica si se alcanzó el final del conjunto de resultados (SQL_NO_DATA), si se devolvieron mensajes informativos (SQL_SUCCESS_WITH_INFO) o si se produjo un error (SQL_ERROR).</span><span class="sxs-lookup"><span data-stu-id="a46f0-109">For example, after an application calls **SQLFetch** to retrieve the rows in a result set, the return code indicates whether the end of the result set was reached (SQL_NO_DATA), if any informational messages were returned (SQL_SUCCESS_WITH_INFO), or if an error occurred (SQL_ERROR).</span></span>  
  
 <span data-ttu-id="a46f0-110">Si el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client devuelve un valor distinto de SQL_SUCCESS, la aplicación puede llamar a **SQLGetDiagRec** para recuperar los mensajes informativos o de error.</span><span class="sxs-lookup"><span data-stu-id="a46f0-110">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns anything other than SQL_SUCCESS, the application can call **SQLGetDiagRec** to retrieve any informational or error messages.</span></span> <span data-ttu-id="a46f0-111">Use **SQLGetDiagRec** para desplazarse hacia arriba y hacia abajo por el conjunto de mensajes si hay más de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46f0-111">Use **SQLGetDiagRec** to scroll up and down the message set if there is more than one message.</span></span>  
  
 <span data-ttu-id="a46f0-112">El código de retorno SQL_INVALID_HANDLE siempre indica un error de programación y nunca debe encontrarse durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a46f0-112">The return code SQL_INVALID_HANDLE always indicates a programming error and should never be encountered at run time.</span></span> <span data-ttu-id="a46f0-113">Todos los demás códigos de retorno proporcionan información en tiempo de ejecución, aunque SQL_ERROR puede indicar un error de programación.</span><span class="sxs-lookup"><span data-stu-id="a46f0-113">All other return codes provide run-time information, although SQL_ERROR may indicate a programming error.</span></span>  
  
 <span data-ttu-id="a46f0-114">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] API nativa original, DB-Library para C, permite que una aplicación Instale funciones de control de errores y de control de mensajes de devolución de llamada que devuelven errores o mensajes.</span><span class="sxs-lookup"><span data-stu-id="a46f0-114">The original [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native API, DB-Library for C, allows an application to install callback error-handling and message-handling functions that return errors or messages.</span></span> <span data-ttu-id="a46f0-115">Algunas instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)], como PRINT, RAISERROR, DBCC y SET, devuelven sus resultados a la función de controlador de mensajes DB-Library en lugar de a un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a46f0-115">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, such as PRINT, RAISERROR, DBCC, and SET, return their results to the DB-Library message handler function instead of to a result set.</span></span> <span data-ttu-id="a46f0-116">Sin embargo, la API de ODBC no tiene ninguna capacidad de devolución de llamada semejante.</span><span class="sxs-lookup"><span data-stu-id="a46f0-116">However, the ODBC API has no such callback capability.</span></span> <span data-ttu-id="a46f0-117">Cuando el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client detecta mensajes procedentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , establece el código de retorno de odbc en SQL_SUCCESS_WITH_INFO o SQL_ERROR y devuelve el mensaje como uno o más registros de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a46f0-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver detects messages coming back from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it sets the ODBC return code to SQL_SUCCESS_WITH_INFO or SQL_ERROR and returns the message as one or more diagnostic records.</span></span> <span data-ttu-id="a46f0-118">Por lo tanto, una aplicación ODBC debe comprobar cuidadosamente estos códigos de retorno y llamar a **SQLGetDiagRec** para recuperar los datos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46f0-118">Therefore, an ODBC application must carefully test for these return codes and call **SQLGetDiagRec** to retrieve message data.</span></span>  
  
 <span data-ttu-id="a46f0-119">Para obtener información sobre cómo realizar un seguimiento de los errores, vea [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805) (Seguimiento de acceso a datos).</span><span class="sxs-lookup"><span data-stu-id="a46f0-119">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="a46f0-120">Para información sobre las mejoras en el seguimiento de errores agregadas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], consulte [Acceso a información de diagnóstico en el registro de eventos extendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="a46f0-120">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a46f0-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a46f0-121">In This Section</span></span>  
  
-   [<span data-ttu-id="a46f0-122">Procesar instrucciones que generan mensajes</span><span class="sxs-lookup"><span data-stu-id="a46f0-122">Processing Statements That Generate Messages</span></span>](processing-statements-that-generate-messages.md)  
  
-   [<span data-ttu-id="a46f0-123">Registros y campos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a46f0-123">Diagnostic Records and Fields</span></span>](diagnostic-records-and-fields.md)  
  
-   [<span data-ttu-id="a46f0-124">Números de errores nativos</span><span class="sxs-lookup"><span data-stu-id="a46f0-124">Native Error Numbers</span></span>](native-error-numbers.md)  
  
-   [<span data-ttu-id="a46f0-125">Códigos de error ODBC de &#40;SQLSTATE&#41;</span><span class="sxs-lookup"><span data-stu-id="a46f0-125">SQLSTATE &#40;ODBC Error Codes&#41;</span></span>](sqlstate-odbc-error-codes.md)  
  
-   [<span data-ttu-id="a46f0-126">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="a46f0-126">Error Messages</span></span>](error-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="a46f0-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a46f0-127">See Also</span></span>  
 [<span data-ttu-id="a46f0-128">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a46f0-128">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
