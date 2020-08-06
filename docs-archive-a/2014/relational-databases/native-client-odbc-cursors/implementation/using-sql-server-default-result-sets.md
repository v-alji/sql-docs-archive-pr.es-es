---
title: Usar SQL Server conjuntos de resultados predeterminados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 18cd10dd95329f68a42497d2bea5ce63f345ceff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671058"
---
# <a name="using-sql-server-default-result-sets"></a><span data-ttu-id="32cd2-102">Utilizar conjuntos de resultados predeterminados de SQL Server</span><span class="sxs-lookup"><span data-stu-id="32cd2-102">Using SQL Server Default Result Sets</span></span>
  <span data-ttu-id="32cd2-103">Los atributos de cursor ODBC predeterminados son:</span><span class="sxs-lookup"><span data-stu-id="32cd2-103">The default ODBC cursor attributes are:</span></span>  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="32cd2-104">Cada vez que estos atributos se establecen en sus valores predeterminados, el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client utiliza un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="32cd2-104">Whenever these attributes are set to their defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set.</span></span> <span data-ttu-id="32cd2-105">Los conjuntos de resultados predeterminados se pueden utilizar para cualquier instrucción SQL admitida por [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y son el método más eficaz de transferir un conjunto de resultados completo al cliente.</span><span class="sxs-lookup"><span data-stu-id="32cd2-105">Default result sets can be used for any SQL statement supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and are the most efficient method of transferring an entire result set to the client.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="32cd2-106">se incorporó la compatibilidad con conjuntos de resultados activos múltiples (MARS). Ahora, las aplicaciones pueden tener más de un conjunto de resultados predeterminado activo por conexión.</span><span class="sxs-lookup"><span data-stu-id="32cd2-106">introduced support for multiple active result sets (MARS); applications can now have more than one active default result set per connection.</span></span> <span data-ttu-id="32cd2-107">MARS no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="32cd2-107">MARS is not enabled by default.</span></span>  
  
 <span data-ttu-id="32cd2-108">Antes de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], los conjuntos de resultados predeterminados no admitían varias instrucciones activas en la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="32cd2-108">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], default result sets did not support multiple active statements on the same connection.</span></span> <span data-ttu-id="32cd2-109">Una vez ejecutada una instrucción SQL en una conexión, el servidor no acepta comandos (excepto una solicitud para cancelar el resto del conjunto de resultados) del cliente en esa conexión hasta que se han procesado todas las filas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="32cd2-109">After an SQL statement is executed on a connection, the server does not accept commands (except a request to cancel the rest of the result set) from the client on that connection until all the rows in the result set have been processed.</span></span> <span data-ttu-id="32cd2-110">Para cancelar el resto de un conjunto de resultados procesado parcialmente, llame a [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) o [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con el parámetro *fOption* establecido en SQL_CLOSE.</span><span class="sxs-lookup"><span data-stu-id="32cd2-110">To cancel the remainder of a partially processed result set, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with the *fOption* parameter set to SQL_CLOSE.</span></span> <span data-ttu-id="32cd2-111">Para finalizar un conjunto de resultados procesado parcialmente y probar la presencia de otro conjunto de resultados, llame a [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="32cd2-111">To finish a partially processed result set and test for the presence of another result set, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span></span> <span data-ttu-id="32cd2-112">Si una aplicación ODBC intenta un comando en un identificador de conexión antes de que se haya procesado completamente un conjunto de resultados predeterminado, la llamada genera SQL_ERROR y una llamada a **SQLGetDiagRec** devuelve:</span><span class="sxs-lookup"><span data-stu-id="32cd2-112">If an ODBC application attempts a command on a connection handle before a default result set has been completely processed, the call generates SQL_ERROR and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a><span data-ttu-id="32cd2-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32cd2-113">See Also</span></span>  
 [<span data-ttu-id="32cd2-114">Cómo se implementan los cursores</span><span class="sxs-lookup"><span data-stu-id="32cd2-114">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  