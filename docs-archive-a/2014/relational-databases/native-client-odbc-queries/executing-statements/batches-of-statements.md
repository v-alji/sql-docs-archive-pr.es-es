---
title: Lotes de instrucciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662880"
---
# <a name="batches-of-statements"></a><span data-ttu-id="7906e-102">Lotes de instrucciones</span><span class="sxs-lookup"><span data-stu-id="7906e-102">Batches of Statements</span></span>
  <span data-ttu-id="7906e-103">Un lote de [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrucciones contiene dos o más instrucciones, separadas por un punto y coma (;), integradas en una sola cadena que se pasa a la función **SQLExecDirect** o [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="7906e-103">A batch of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements contains two or more statements, separated by a semicolon (;), built into a single string passed to **SQLExecDirect** or [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span> <span data-ttu-id="7906e-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7906e-104">For example:</span></span>  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 <span data-ttu-id="7906e-105">Los lotes pueden ser más eficaces que el envío de instrucciones por separado porque el tráfico de red suele ser reducido.</span><span class="sxs-lookup"><span data-stu-id="7906e-105">Batches can be more efficient than submitting statements separately because network traffic is often reduced.</span></span> <span data-ttu-id="7906e-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) para situarse en el siguiente conjunto de resultados cuando termine con el conjunto de resultados actual.</span><span class="sxs-lookup"><span data-stu-id="7906e-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to get positioned on the next result set when finished with the current result set.</span></span>  
  
 <span data-ttu-id="7906e-107">Siempre pueden usarse lotes cuando los atributos de cursor de ODBC se establecen en los valores predeterminados de un cursor de solo avance y de solo lectura cuyo conjunto de filas tiene un tamaño de 1.</span><span class="sxs-lookup"><span data-stu-id="7906e-107">Batches can always be used when the ODBC cursor attributes are set to the defaults of a forward-only, read-only cursor with a rowset size of 1.</span></span>  
  
 <span data-ttu-id="7906e-108">Si se ejecuta un lote al utilizar los cursores del servidor en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el cursor del servidor se convierte implícitamente en un conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7906e-108">If a batch is executed when using server cursors against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="7906e-109">**SQLExecDirect** o **SQLExecute** devuelven SQL_SUCCESS_WITH_INFO, y una llamada a **SQLGetDiagRec** devuelve:</span><span class="sxs-lookup"><span data-stu-id="7906e-109">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a><span data-ttu-id="7906e-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7906e-110">See Also</span></span>  
 [<span data-ttu-id="7906e-111">Ejecutar instrucciones &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="7906e-111">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
