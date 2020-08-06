---
title: Usar cursores (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], how to topics
ms.assetid: c502736f-bca0-45c3-ae25-d2ad52d296bf
author: rothja
ms.author: jroth
ms.openlocfilehash: e08156b03407c7a05d86278c11482a568d651f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661993"
---
# <a name="use-cursors-odbc"></a><span data-ttu-id="91a13-102">Usar cursores (ODBC)</span><span class="sxs-lookup"><span data-stu-id="91a13-102">Use Cursors (ODBC)</span></span>
    
### <a name="to-use-cursors"></a><span data-ttu-id="91a13-103">Para usar cursores</span><span class="sxs-lookup"><span data-stu-id="91a13-103">To use cursors</span></span>  
  
1.  <span data-ttu-id="91a13-104">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos de cursor deseados:</span><span class="sxs-lookup"><span data-stu-id="91a13-104">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the desired cursor attributes:</span></span>  
  
     <span data-ttu-id="91a13-105">Establezca los atributos SQL_ATTR_CURSOR_TYPE y SQL_ATTR_CONCURRENCY (ésta es la opción preferida).</span><span class="sxs-lookup"><span data-stu-id="91a13-105">Set the SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY attributes (this is the preferred option).</span></span>  
  
     <span data-ttu-id="91a13-106">Or</span><span class="sxs-lookup"><span data-stu-id="91a13-106">Or</span></span>  
  
     <span data-ttu-id="91a13-107">Establezca los atributos SQL_CURSOR_SCROLLABLE y SQL_CURSOR_SENSITIVITY.</span><span class="sxs-lookup"><span data-stu-id="91a13-107">Set the SQL_CURSOR_SCROLLABLE and SQL_CURSOR_SENSITIVITY attributes.</span></span>  
  
2.  <span data-ttu-id="91a13-108">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer el tamaño del conjunto de filas mediante el atributo SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="91a13-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the rowset size by using the SQL_ATTR_ROW_ARRAY_SIZE attribute.</span></span>  
  
3.  <span data-ttu-id="91a13-109">Opcionalmente, llame a [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) para establecer un nombre de cursor si las actualizaciones posicionadas se van a hacer mediante la cláusula de WHERE CURRENT OF.</span><span class="sxs-lookup"><span data-stu-id="91a13-109">Optionally, call [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) to set a cursor name if positioned updates will be done by using the WHERE CURRENT OF clause.</span></span>  
  
4.  <span data-ttu-id="91a13-110">Ejecute la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="91a13-110">Execute the SQL statement.</span></span>  
  
5.  <span data-ttu-id="91a13-111">Opcionalmente, llame a [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) para obtener el nombre de cursor si las actualizaciones posicionadas se van a hacer mediante la cláusula WHERE ACTUAL OF y un nombre de cursor no se ha proporcionado con [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="91a13-111">Optionally, call [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) to get the cursor name if positioned updates will be done by using the WHERE CURRENT OF clause and a cursor name was not supplied with [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) in Step 3.</span></span>  
  
6.  <span data-ttu-id="91a13-112">Llame a [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) para obtener el número de columnas (C) en el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="91a13-112">Call [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns (C) in the rowset.</span></span>  
  
     <span data-ttu-id="91a13-113">Use el enlace de modo de columna.</span><span class="sxs-lookup"><span data-stu-id="91a13-113">Use column-wise binding.</span></span>  
  
     <span data-ttu-id="91a13-114">\- o -</span><span class="sxs-lookup"><span data-stu-id="91a13-114">\- or -</span></span>  
  
     <span data-ttu-id="91a13-115">Use el enlace de modo de fila.</span><span class="sxs-lookup"><span data-stu-id="91a13-115">Use row-wise binding.</span></span>  
  
7.  <span data-ttu-id="91a13-116">Capture los conjuntos de filas del cursor según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="91a13-116">Fetch rowsets from the cursor as desired.</span></span>  
  
8.  <span data-ttu-id="91a13-117">Llame a [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) para determinar si otro conjunto de resultados está disponible.</span><span class="sxs-lookup"><span data-stu-id="91a13-117">Call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="91a13-118">Si devuelve SQL_SUCCESS, está disponible otro conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="91a13-118">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="91a13-119">Si devuelve SQL_NO_DATA, no hay ningún otro conjunto de resultados disponible.</span><span class="sxs-lookup"><span data-stu-id="91a13-119">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="91a13-120">Si devuelve SQL_SUCCESS_WITH_INFO o SQL_ERROR, llame a [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) para determinar si está disponible la salida de una instrucción PRINT o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="91a13-120">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
     <span data-ttu-id="91a13-121">Si se utilizan parámetros de instrucción enlazados como parámetros de salida o como valor devuelto de un procedimiento almacenado, utilice los datos ahora disponibles en los búferes de parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="91a13-121">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span>  
  
     <span data-ttu-id="91a13-122">Si se usan parámetros enlazados, cada llamada a [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) o [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) habrá ejecutado la instrucción SQL S veces, donde S es el número de elementos en la matriz de parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="91a13-122">When bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement S times, where S is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="91a13-123">Esto significa que habrá S conjuntos de resultados para procesar, donde cada conjunto de resultados comprende todos los conjuntos de resultados, parámetros de salida y códigos de retorno devueltos normalmente por una ejecución única de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="91a13-123">This means that there will be S sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
     <span data-ttu-id="91a13-124">Tenga en cuenta que cuando un conjunto de resultados contiene filas del cálculo, cada fila del cálculo está disponible como un conjunto de resultados independiente.</span><span class="sxs-lookup"><span data-stu-id="91a13-124">Note that when a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="91a13-125">Estos conjuntos de resultados de cálculo se intercalan entre las filas normales e interrumpen las filas normales en varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="91a13-125">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
9. <span data-ttu-id="91a13-126">Opcionalmente, llame a [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con SQL_UNBIND para liberar los búferes de columna enlazada.</span><span class="sxs-lookup"><span data-stu-id="91a13-126">Optionally, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
10. <span data-ttu-id="91a13-127">Si está disponible otro conjunto de resultados, vaya al paso 6.</span><span class="sxs-lookup"><span data-stu-id="91a13-127">If another result set is available, go to Step 6.</span></span>  
  
     <span data-ttu-id="91a13-128">En el paso 9, al llamar a [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) en un conjunto de resultados procesados parcialmente se borra el resto del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="91a13-128">In Step 9, calling [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) on a partially processed result set clears the remainder of the result set.</span></span> <span data-ttu-id="91a13-129">Otra manera de borrar un conjunto de resultados procesados parcialmente es llamar a [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="91a13-129">Another way to clear a partially processed result set is to call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
     <span data-ttu-id="91a13-130">Puede controlar el tipo de cursor usado estableciendo SQL_ATTR_CURSOR_TYPE y SQL_ATTR_CONCURRENCY o estableciendo SQL_ATTR_CURSOR_SENSITIVITY y SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="91a13-130">You can control the type of cursor used by setting either SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="91a13-131">No debe mezclar los dos métodos que se utilizan para especificar el comportamiento del cursor.</span><span class="sxs-lookup"><span data-stu-id="91a13-131">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a13-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91a13-132">See Also</span></span>  
 [<span data-ttu-id="91a13-133">Temas de procedimientos de uso de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="91a13-133">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
