---
title: Conversiones de cursor IMPLÍCITAS (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, implicit cursor conversions
- implicit cursor conversions
- cursors [ODBC], implicit cursor conversions
ms.assetid: fe29a58d-8448-4512-9ffd-b414784ba338
author: rothja
ms.author: jroth
ms.openlocfilehash: ff8350c71a853e39ff1d35a1f3fba6e8e1944934
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675335"
---
# <a name="implicit-cursor-conversions-odbc"></a><span data-ttu-id="47468-102">Conversiones de cursor implícitas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="47468-102">Implicit Cursor Conversions (ODBC)</span></span>
  <span data-ttu-id="47468-103">Las aplicaciones pueden solicitar un tipo de cursor a través de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) y, a continuación, ejecutar una instrucción SQL que no sea compatible con los cursores de servidor del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="47468-103">Applications can request a cursor type through [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) and then execute an SQL statement that is not supported by server cursors of the type requested.</span></span> <span data-ttu-id="47468-104">Una llamada a **SQLExecute** o **SQLExecDirect** devuelve SQL_SUCCESS_WITH_INFO y **SQLGetDiagRec** devuelve:</span><span class="sxs-lookup"><span data-stu-id="47468-104">A call to **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 <span data-ttu-id="47468-105">La aplicación puede determinar qué tipo de cursor se usa ahora llamando a **SQLGetStmtOption** establecido en SQL_CURSOR_TYPE.</span><span class="sxs-lookup"><span data-stu-id="47468-105">The application can determine what type of cursor is now being used by calling **SQLGetStmtOption** set to SQL_CURSOR_TYPE.</span></span> <span data-ttu-id="47468-106">La conversión del tipo de cursor solamente se aplica a una instrucción.</span><span class="sxs-lookup"><span data-stu-id="47468-106">The cursor type conversion applies to only one statement.</span></span> <span data-ttu-id="47468-107">La siguiente **SQLExecDirect** o **SQLExecute** se realizará con la configuración original del cursor de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="47468-107">The next **SQLExecDirect** or **SQLExecute** will be done using the original statement cursor settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47468-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47468-108">See Also</span></span>  
 [<span data-ttu-id="47468-109">Detalles de la programación de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="47468-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
