---
title: Modo asincrónico y SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- asynchronous operations [SQL Server Native Client]
- SQLCancel function
- SQLSetConnectAttr function
- SQL Server Native Client, asynchronous operations
- ODBC functions
- ODBC applications, asynchronous operations
- SQL Server Native Client ODBC driver, asynchronous mode
ms.assetid: f31702a2-df76-4589-ac3b-da5412c03dc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 9071c6821e6edeb577b639223e42899d2927bced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675295"
---
# <a name="asynchronous-mode-and-sqlcancel"></a><span data-ttu-id="8ff83-102">Modo asincrónico y SQLCancel</span><span class="sxs-lookup"><span data-stu-id="8ff83-102">Asynchronous Mode and SQLCancel</span></span>
  <span data-ttu-id="8ff83-103">Algunas funciones ODBC pueden operar de forma sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="8ff83-103">Some ODBC functions can operate either synchronously or asynchronously.</span></span> <span data-ttu-id="8ff83-104">La aplicación puede habilitar las operaciones asincrónicas para un identificador de instrucción o un identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ff83-104">The application can enable asynchronous operations for either a statement handle or a connection handle.</span></span> <span data-ttu-id="8ff83-105">Si la opción está establecida para un identificador de conexión, afectará a todos los identificadores de instrucción del identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ff83-105">If the option is set for a connection handle, it affects all statement handles on the connection handle.</span></span> <span data-ttu-id="8ff83-106">La aplicación utiliza las instrucciones siguientes para habilitar o deshabilitar las operaciones asincrónicas:</span><span class="sxs-lookup"><span data-stu-id="8ff83-106">The application uses the following statements to enable or disable asynchronous operations:</span></span>  
  
```  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="8ff83-107">Cuando una aplicación llama a una función ODBC en modo sincrónico, el controlador no devuelve el control a la aplicación hasta que se notifique que el servidor ha completado el comando.</span><span class="sxs-lookup"><span data-stu-id="8ff83-107">When an application calls an ODBC function in synchronous mode, the driver does not return control to the application until it is notified that the server has completed the command.</span></span>  
  
 <span data-ttu-id="8ff83-108">Cuando funciona en modo asincrónico, el controlador devuelve inmediatamente el control a la aplicación, incluso antes de enviar el comando al servidor.</span><span class="sxs-lookup"><span data-stu-id="8ff83-108">When operating asynchronously, the driver immediately returns control to the application, even before sending the command to the server.</span></span> <span data-ttu-id="8ff83-109">El controlador establece el código de retorno en SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="8ff83-109">The driver sets the return code to SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="8ff83-110">A continuación, la aplicación realiza las demás tareas.</span><span class="sxs-lookup"><span data-stu-id="8ff83-110">The application can then perform other work.</span></span>  
  
 <span data-ttu-id="8ff83-111">Cuando la aplicación comprueba que el comando ha finalizado, realiza la misma llamada de función con los mismos parámetros al controlador.</span><span class="sxs-lookup"><span data-stu-id="8ff83-111">When the application tests for completion of the command, it makes the same function call with the same parameters to the driver.</span></span> <span data-ttu-id="8ff83-112">Si el controlador aún no ha recibido una respuesta del servidor, devolverá de nuevo SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="8ff83-112">If the driver has not yet received an answer from the server, it will again return SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="8ff83-113">La aplicación debe comprobar periódicamente el comando hasta que el código de retorno sea distinto de SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="8ff83-113">The application must test the command periodically until the return code is something other than SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="8ff83-114">Cuando la aplicación obtiene otro código de retorno, incluso SQL_ERROR, puede determinar que el comando ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="8ff83-114">When the application gets some other return code, even SQL_ERROR, it can determine that the command has completed.</span></span>  
  
 <span data-ttu-id="8ff83-115">A veces un comando tarda mucho tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="8ff83-115">Sometimes a command is outstanding for a long time.</span></span> <span data-ttu-id="8ff83-116">Si la aplicación necesita cancelar el comando sin esperar una respuesta, puede hacerlo mediante una llamada a **SQLCancel** con el mismo identificador de instrucción que el comando pendiente.</span><span class="sxs-lookup"><span data-stu-id="8ff83-116">If the application needs to cancel the command without waiting for a reply, it can do so by calling **SQLCancel** with the same statement handle as the outstanding command.</span></span> <span data-ttu-id="8ff83-117">Esta es la única vez que se debe usar **SQLCancel** .</span><span class="sxs-lookup"><span data-stu-id="8ff83-117">This is the only time **SQLCancel** should be used.</span></span> <span data-ttu-id="8ff83-118">Algunos programadores usan **SQLCancel** cuando se han procesado de forma parcial a través de un conjunto de resultados y desean cancelar el resto del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="8ff83-118">Some programmers use **SQLCancel** when they have processed part way through a result set and want to cancel the rest of the result set.</span></span> <span data-ttu-id="8ff83-119">Se debe usar [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) o [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) para cancelar el resto de un conjunto de resultados pendiente, no **SQLCancel**.</span><span class="sxs-lookup"><span data-stu-id="8ff83-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) should be used to cancel the remainder of an outstanding result set, not **SQLCancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff83-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ff83-120">See Also</span></span>  
 [<span data-ttu-id="8ff83-121">Crear una aplicación de controlador ODBC de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8ff83-121">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
