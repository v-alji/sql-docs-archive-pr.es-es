---
title: Desplazamiento y captura de filas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- SQLFetchScroll function
- ODBC applications, cursors
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- fetching [ODBC]
- ODBC cursors, scrolling rows
ms.assetid: 9109f10d-326b-4a6d-8c97-831f60da8c4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 97586f82ddddb79581b0f9c027aa60d7822b472c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749296"
---
# <a name="scrolling-and-fetching-rows"></a><span data-ttu-id="ace81-102">Desplazamiento y captura de filas</span><span class="sxs-lookup"><span data-stu-id="ace81-102">Scrolling and Fetching Rows</span></span>
  <span data-ttu-id="ace81-103">Para utilizar un cursor desplazable, una aplicación ODBC debe:</span><span class="sxs-lookup"><span data-stu-id="ace81-103">To use a scrollable cursor, an ODBC application must:</span></span>  
  
-   <span data-ttu-id="ace81-104">Establezca las capacidades del cursor mediante [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="ace81-104">Set the cursor capabilities using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
-   <span data-ttu-id="ace81-105">Abra el cursor con **SQLExecute** o **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="ace81-105">Open the cursor using **SQLExecute** or **SQLExecDirect**.</span></span>  
  
-   <span data-ttu-id="ace81-106">Desplazamiento y captura de filas con **SQLFetch** o [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="ace81-106">Scroll and fetch rows using **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span>  
  
 <span data-ttu-id="ace81-107">**SQLFetch** y **SQLFetchSroll** pueden capturar bloques de filas a la vez.</span><span class="sxs-lookup"><span data-stu-id="ace81-107">Both **SQLFetch** and **SQLFetchSroll** can fetch blocks of rows at a time.</span></span> <span data-ttu-id="ace81-108">El número de filas devueltas se especifica mediante **SQLSetStmtAttr** para establecer el parámetro SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="ace81-108">The number of rows returned is specified by using **SQLSetStmtAttr** to set the SQL_ATTR_ROW_ARRAY_SIZE parameter.</span></span>  
  
 <span data-ttu-id="ace81-109">Las aplicaciones ODBC pueden usar **SQLFetch** para obtener un cursor de solo avance.</span><span class="sxs-lookup"><span data-stu-id="ace81-109">ODBC applications can use **SQLFetch** to fetch through a forward-only cursor.</span></span>  
  
 <span data-ttu-id="ace81-110">**SQLFetchScroll** se utiliza para desplazarse alrededor de un cursor.</span><span class="sxs-lookup"><span data-stu-id="ace81-110">**SQLFetchScroll** is used to scroll around a cursor.</span></span> <span data-ttu-id="ace81-111">**SQLFetchScroll** admite la captura de los conjuntos de filas siguiente, anterior, primero y último, además de la captura relativa (capturar el conjunto de filas *n* filas desde el inicio del conjunto de filas actual) y la captura absoluta (capturar el conjunto de filas a partir de la fila *n*).</span><span class="sxs-lookup"><span data-stu-id="ace81-111">**SQLFetchScroll** supports fetching the next, prior, first, and last rowsets in addition to relative fetching (fetch the rowset *n* rows from the start of the current rowset) and absolute fetching (fetch the rowset starting at row *n*).</span></span> <span data-ttu-id="ace81-112">Si *n* es negativo en una captura absoluta, las filas se cuentan desde el final del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ace81-112">If *n* is negative in an absolute fetch, rows are counted from the end of the result set.</span></span> <span data-ttu-id="ace81-113">Una captura absoluta de la fila -1 significa que se capturará el conjunto de filas que empieza con la última fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ace81-113">An absolute fetch of row -1 means to fetch the rowset that starts with the last row in the result set.</span></span>  
  
 <span data-ttu-id="ace81-114">Las aplicaciones que usan **SQLFetchScroll** solo para sus capacidades de cursor de bloque, como los informes, es probable que pasen por el conjunto de resultados una sola vez, usando solo la opción para capturar el siguiente conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="ace81-114">Applications that use **SQLFetchScroll** only for its block cursor capabilities, such as reports, are likely to pass through the result set a single time, using only the option to fetch the next rowset.</span></span> <span data-ttu-id="ace81-115">Por otro lado, las aplicaciones basadas en pantalla pueden aprovechar todas las funcionalidades de **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="ace81-115">Screen-based applications, on the other hand, can take advantage of all the capabilities of **SQLFetchScroll**.</span></span> <span data-ttu-id="ace81-116">Si la aplicación establece el tamaño del conjunto de filas en el número de filas que se muestra en la pantalla y enlaza los búferes de pantalla al conjunto de resultados, puede traducir las operaciones de la barra de desplazamiento directamente a las llamadas a **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="ace81-116">If the application sets the rowset size to the number of rows displayed on the screen and binds the screen buffers to the result set, it can translate scroll bar operations directly to calls to **SQLFetchScroll**.</span></span>  
  
|<span data-ttu-id="ace81-117">Funcionamiento de la barra de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="ace81-117">Scroll bar operation</span></span>|<span data-ttu-id="ace81-118">Opción de desplazamiento de SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="ace81-118">SQLFetchScroll scrolling option</span></span>|  
|--------------------------|-------------------------------------|  
|<span data-ttu-id="ace81-119">Re Pág</span><span class="sxs-lookup"><span data-stu-id="ace81-119">Page up</span></span>|<span data-ttu-id="ace81-120">SQL_FETCH_PRIOR</span><span class="sxs-lookup"><span data-stu-id="ace81-120">SQL_FETCH_PRIOR</span></span>|  
|<span data-ttu-id="ace81-121">Av Pág</span><span class="sxs-lookup"><span data-stu-id="ace81-121">Page down</span></span>|<span data-ttu-id="ace81-122">SQL_FETCH_NEXT</span><span class="sxs-lookup"><span data-stu-id="ace81-122">SQL_FETCH_NEXT</span></span>|  
|<span data-ttu-id="ace81-123">Línea arriba</span><span class="sxs-lookup"><span data-stu-id="ace81-123">Line up</span></span>|<span data-ttu-id="ace81-124">SQL_FETCH_RELATIVE con FetchOffset igual a-1</span><span class="sxs-lookup"><span data-stu-id="ace81-124">SQL_FETCH_RELATIVE with FetchOffset equal to -1</span></span>|  
|<span data-ttu-id="ace81-125">Línea abajo</span><span class="sxs-lookup"><span data-stu-id="ace81-125">Line down</span></span>|<span data-ttu-id="ace81-126">SQL_FETCH_RELATIVE con FetchOffset igual a 1</span><span class="sxs-lookup"><span data-stu-id="ace81-126">SQL_FETCH_RELATIVE with FetchOffset equal to 1</span></span>|  
|<span data-ttu-id="ace81-127">Cuadro de desplazamiento hacia arriba</span><span class="sxs-lookup"><span data-stu-id="ace81-127">Scroll box to top</span></span>|<span data-ttu-id="ace81-128">SQL_FETCH_FIRST</span><span class="sxs-lookup"><span data-stu-id="ace81-128">SQL_FETCH_FIRST</span></span>|  
|<span data-ttu-id="ace81-129">Cuadro de desplazamiento hacia abajo</span><span class="sxs-lookup"><span data-stu-id="ace81-129">Scroll box to bottom</span></span>|<span data-ttu-id="ace81-130">SQL_FETCH_LAST</span><span class="sxs-lookup"><span data-stu-id="ace81-130">SQL_FETCH_LAST</span></span>|  
|<span data-ttu-id="ace81-131">Posición del cuadro de desplazamiento aleatoria</span><span class="sxs-lookup"><span data-stu-id="ace81-131">Random scroll box position</span></span>|<span data-ttu-id="ace81-132">SQL_FETCH_ABSOLUTE</span><span class="sxs-lookup"><span data-stu-id="ace81-132">SQL_FETCH_ABSOLUTE</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="ace81-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ace81-133">In This Section</span></span>  
  
-   [<span data-ttu-id="ace81-134">Marcar filas en ODBC</span><span class="sxs-lookup"><span data-stu-id="ace81-134">Bookmarking Rows in ODBC</span></span>](scrolling-and-fetching-rows-bookmarking-rows-in-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="ace81-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ace81-135">See Also</span></span>  
 [<span data-ttu-id="ace81-136">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="ace81-136">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
