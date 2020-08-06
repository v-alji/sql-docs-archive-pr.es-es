---
title: Capturar y actualizar conjuntos de filas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [ODBC]
ms.assetid: cf0eb3b4-8b72-49fc-a845-95edc360cf93
author: rothja
ms.author: jroth
ms.openlocfilehash: e09a3033e0883452ecd69b82c9375ed28c920da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661997"
---
# <a name="fetch-and-update-rowsets-odbc"></a><span data-ttu-id="c1e3b-102">Capturar y actualizar conjuntos de filas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c1e3b-102">Fetch and Update Rowsets (ODBC)</span></span>
    
### <a name="to-fetch-and-update-rowsets"></a><span data-ttu-id="c1e3b-103">Para capturar y actualizar conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="c1e3b-103">To fetch and update rowsets</span></span>  
  
1.  <span data-ttu-id="c1e3b-104">Opcionalmente, llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) con SQL_ROW_ARRAY_SIZE para cambiar el número de filas (R) del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-104">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) with SQL_ROW_ARRAY_SIZE to change the number of rows (R) in the rowset.</span></span>  
  
2.  <span data-ttu-id="c1e3b-105">Llame a [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) o [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) para obtener un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-105">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) to get a rowset.</span></span>  
  
3.  <span data-ttu-id="c1e3b-106">Si se usan columnas enlazadas, use ahora los valores de datos y las longitudes de datos disponibles de los búferes de la columna enlazada para el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-106">If bound columns are used, use the data values and data lengths now available in the bound column buffers for the rowset.</span></span>  
  
     <span data-ttu-id="c1e3b-107">Si se usan columnas desenlazadas, para cada fila llame a [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) con SQL_POSITION establecer la posición del cursor; a continuación, para cada columna desenlazada:</span><span class="sxs-lookup"><span data-stu-id="c1e3b-107">If unbound columns are used, for each row call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) with SQL_POSITION to set the cursor position; then, for each unbound column:</span></span>  
  
    -   <span data-ttu-id="c1e3b-108">Llame a [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) una o más veces para obtener los datos para las columnas desenlazadas después de la última columna enlazada del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-108">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column of the rowset.</span></span> <span data-ttu-id="c1e3b-109">Las llamadas a [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) deber estar en orden de número de columna creciente.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-109">Calls to [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) should be in order of increasing column number.</span></span>  
  
    -   <span data-ttu-id="c1e3b-110">Llame a [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) varias veces para obtener datos de una columna de texto o de imagen.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-110">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="c1e3b-111">Configure cualquier columna de imagen o texto de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-111">Set up any data-at-execution text or image columns.</span></span>  
  
5.  <span data-ttu-id="c1e3b-112">Llame a [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) o [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) para establecer la posición del cursor, actualizar, eliminar o agregar filas dentro del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-112">Call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) or [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) to set the cursor position, refresh, update, delete, or add row(s) within the rowset.</span></span>  
  
     <span data-ttu-id="c1e3b-113">Si se usan columnas de imagen o texto de datos en ejecución para una operación de actualización o adición, contrólelas.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-113">If data-at-execution text or image columns are used for an update or add operation, handle them.</span></span>  
  
6.  <span data-ttu-id="c1e3b-114">Opcionalmente, ejecute una instrucción UPDATE o DELETE colocada, especificando el nombre del cursor (disponible desde [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) y usando un identificador de instrucción diferente en la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="c1e3b-114">Optionally, execute a positioned UPDATE or DELETE statement, specifying the cursor name (available from [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) and using a different statement handle on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e3b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1e3b-115">See Also</span></span>  
 [<span data-ttu-id="c1e3b-116">Temas de procedimientos de uso de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e3b-116">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
