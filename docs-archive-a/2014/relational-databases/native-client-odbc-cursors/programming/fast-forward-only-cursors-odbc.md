---
title: Cursores de solo avance rápido (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fast forward-only cursors
- forward-only cursors
- cursors [ODBC], fast forward-only
- ODBC cursors, fast forward-only
ms.assetid: 0707d07e-fc95-42ed-9280-b7e508ac8c62
author: rothja
ms.author: jroth
ms.openlocfilehash: de8d82a0c72ad51741a3785fba2910f691028cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675342"
---
# <a name="fast-forward-only-cursors-odbc"></a><span data-ttu-id="49405-102">Cursores de solo avance rápido (ODBC)</span><span class="sxs-lookup"><span data-stu-id="49405-102">Fast Forward-Only Cursors (ODBC)</span></span>
  <span data-ttu-id="49405-103">Cuando se conecta a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite optimizaciones de rendimiento para cursores de solo avance y de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="49405-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports performance optimizations for forward-only, read-only cursors.</span></span> <span data-ttu-id="49405-104">Los cursores de solo avance rápido se implementan internamente mediante el controlador y el servidor de un modo muy similar a los conjuntos de resultados predeterminados.</span><span class="sxs-lookup"><span data-stu-id="49405-104">Fast forward-only cursors are implemented internally by the driver and server in a manner very similar to default result sets.</span></span> <span data-ttu-id="49405-105">Además de presentar un alto rendimiento, los cursores de solo avance rápido también presentan estas características:</span><span class="sxs-lookup"><span data-stu-id="49405-105">Besides having high performance, fast forward-only cursors also have these characteristics:</span></span>  
  
-   <span data-ttu-id="49405-106">No se admite [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) .</span><span class="sxs-lookup"><span data-stu-id="49405-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported.</span></span> <span data-ttu-id="49405-107">Las columnas del conjunto de resultados deben estar enlazadas a variables de programa.</span><span class="sxs-lookup"><span data-stu-id="49405-107">The result set columns must be bound to program variables.</span></span>  
  
-   <span data-ttu-id="49405-108">El servidor cierra automáticamente el cursor cuando se detecta el final del cursor.</span><span class="sxs-lookup"><span data-stu-id="49405-108">The server automatically closes the cursor when the end of the cursor is detected.</span></span> <span data-ttu-id="49405-109">La aplicación debe seguir llamando a [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) o [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), pero el controlador no tiene que enviar la solicitud de cierre al servidor.</span><span class="sxs-lookup"><span data-stu-id="49405-109">The application must still call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), but the driver does not have to send the close request to the server.</span></span> <span data-ttu-id="49405-110">De esta forma, se ahorra un viaje de ida y vuelta (round trip) de la red al servidor.</span><span class="sxs-lookup"><span data-stu-id="49405-110">This saves a roundtrip across the network to the server.</span></span>  
  
 <span data-ttu-id="49405-111">La aplicación solicita cursores de solo avance rápido mediante el atributo de instrucciones específico del controlador SQL_SOPT_SS_CURSOR_OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="49405-111">The application requests fast forward-only cursors using the driver-specific statement attribute SQL_SOPT_SS_CURSOR_OPTIONS.</span></span> <span data-ttu-id="49405-112">Cuando se establece en SQL_CO_FFO, los cursores de solo avance rápido se habilitan sin captura automática.</span><span class="sxs-lookup"><span data-stu-id="49405-112">When set to SQL_CO_FFO, fast forward-only cursors are enabled without autofetch.</span></span> <span data-ttu-id="49405-113">Cuando se establece en SQL_CO_FFO_AF, también se habilita la opción de captura automática.</span><span class="sxs-lookup"><span data-stu-id="49405-113">When set to SQL_CO_FFO_AF, the autofetch option is also enabled.</span></span> <span data-ttu-id="49405-114">Para obtener más información sobre la captura automática, vea [usar la captura automática con cursores ODBC](using-autofetch-with-odbc-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="49405-114">For more information about autofetch, see [Using Autofetch with ODBC Cursors](using-autofetch-with-odbc-cursors.md).</span></span>  
  
 <span data-ttu-id="49405-115">Los cursores de solo avance rápido con captura automática pueden usarse para recuperar un pequeño conjunto de resultados con solo un viaje de ida y vuelta (round trip) al servidor.</span><span class="sxs-lookup"><span data-stu-id="49405-115">Fast forward-only cursors with autofetch can be used to retrieve a small result set with only one roundtrip to the server.</span></span> <span data-ttu-id="49405-116">En estos pasos, *n* es el número de filas que se devolverán:</span><span class="sxs-lookup"><span data-stu-id="49405-116">In these steps, *n* is the number of rows to be returned:</span></span>  
  
1.  <span data-ttu-id="49405-117">Establezca SQL_SOPT_SS_CURSOR_OPTIONS en SQL_CO_FFO_AF.</span><span class="sxs-lookup"><span data-stu-id="49405-117">Set SQL_SOPT_SS_CURSOR_OPTIONS to SQL_CO_FFO_AF.</span></span>  
  
2.  <span data-ttu-id="49405-118">Establezca SQL_ATTR_ROW_ARRAY_SIZE en *n* + 1.</span><span class="sxs-lookup"><span data-stu-id="49405-118">Set SQL_ATTR_ROW_ARRAY_SIZE to *n* + 1.</span></span>  
  
3.  <span data-ttu-id="49405-119">Enlazar las columnas de resultados a matrices de *n* + 1 elementos (para que sea seguro si se capturan *n* + 1 filas realmente).</span><span class="sxs-lookup"><span data-stu-id="49405-119">Bind the result columns to arrays of *n* + 1 elements (to be safe if *n* + 1 rows are actually fetched).</span></span>  
  
4.  <span data-ttu-id="49405-120">Abra el cursor con **SQLExecDirect** o **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="49405-120">Open the cursor with either **SQLExecDirect** or **SQLExecute**.</span></span>  
  
5.  <span data-ttu-id="49405-121">Si el estado de retorno es SQL_SUCCESS, llame a **SQLFreeStmt** o **SQLCloseCursor** para cerrar el cursor.</span><span class="sxs-lookup"><span data-stu-id="49405-121">If the return status is SQL_SUCCESS, then call **SQLFreeStmt** or **SQLCloseCursor** to close the cursor.</span></span> <span data-ttu-id="49405-122">Todos los datos de las filas estarán en las variables de programa enlazadas.</span><span class="sxs-lookup"><span data-stu-id="49405-122">All data for the rows will be in the bound program variables.</span></span>  
  
 <span data-ttu-id="49405-123">Con estos pasos, **SQLExecDirect** o **SQLExecute** envía una solicitud de cursor Open con la opción de captura automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="49405-123">With these steps, the **SQLExecDirect** or **SQLExecute** sends a cursor open request with the autofetch option enabled.</span></span> <span data-ttu-id="49405-124">En esa única solicitud del cliente, el servidor:</span><span class="sxs-lookup"><span data-stu-id="49405-124">On that single request from the client, the server:</span></span>  
  
-   <span data-ttu-id="49405-125">Abre el cursor.</span><span class="sxs-lookup"><span data-stu-id="49405-125">Opens the cursor.</span></span>  
  
-   <span data-ttu-id="49405-126">Genera el conjunto de resultados y envía las filas al cliente.</span><span class="sxs-lookup"><span data-stu-id="49405-126">Builds the result set and sends the rows to the client.</span></span>  
  
-   <span data-ttu-id="49405-127">Dado que el tamaño del conjunto de filas se estableció en 1 más el número de filas del conjunto de resultados, el servidor detecta el final del cursor y cierra el cursor.</span><span class="sxs-lookup"><span data-stu-id="49405-127">Because the rowset size was set to 1 more than the number of rows in the result set, the server detects the end of the cursor and closes the cursor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49405-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49405-128">See Also</span></span>  
 [<span data-ttu-id="49405-129">Detalles de la programación de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="49405-129">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
