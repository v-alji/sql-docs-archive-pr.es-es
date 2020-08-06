---
title: Usar enlace de conjuntos de filas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowset binding [ODBC]
ms.assetid: a7be05f0-6b11-4b53-9fbc-501e591eef09
author: rothja
ms.author: jroth
ms.openlocfilehash: e2e0671fd1140e72005cd1a7532ea581f077382f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661990"
---
# <a name="use-rowset-binding-odbc"></a><span data-ttu-id="aa4db-102">Usar enlace de conjuntos de filas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="aa4db-102">Use Rowset Binding (ODBC)</span></span>
    
### <a name="to-use-column-wise-binding"></a><span data-ttu-id="aa4db-103">Para utilizar el enlace de modo de columna</span><span class="sxs-lookup"><span data-stu-id="aa4db-103">To use column-wise binding</span></span>  
  
1.  <span data-ttu-id="aa4db-104">Para cada columna enlazada, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa4db-104">For each bound column, do the following:</span></span>  
  
    -   <span data-ttu-id="aa4db-105">Asigne una matriz de R (o más) búferes de columna para almacenar los valores de datos, donde R es el número de filas del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-105">Allocate an array of R (or more) column buffers to store data values, where R is number of rows in the rowset.</span></span>  
  
    -   <span data-ttu-id="aa4db-106">De modo opcional, asigne una matriz de R (o más) búferes de columna para almacenar las longitudes de los datos.</span><span class="sxs-lookup"><span data-stu-id="aa4db-106">Optionally, allocate an array of R (or more) column buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="aa4db-107">Llame a [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) para enlazar las matrices de valores de datos y de longitud de datos de columna a la columna del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-107">Call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to bind the column's data value and data length arrays to the column of the rowset.</span></span>  
  
2.  <span data-ttu-id="aa4db-108">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa4db-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="aa4db-109">Establezca SQL_ATTR_ROW_ARRAY_SIZE en el número de filas del conjunto de filas (R).</span><span class="sxs-lookup"><span data-stu-id="aa4db-109">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="aa4db-110">Establezca SQL_ATTR_ROW_BIND_TYPE en SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="aa4db-110">Set SQL_ATTR_ROW_BIND_TYPE to SQL_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="aa4db-111">Establezca el atributo SQL_ATTR_ROWS FETCHED_PTR para que señale a una variable SQLUINTEGER que incluya el número de filas capturadas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-111">Set the SQL_ATTR_ROWS FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="aa4db-112">Establezca SQL_ATTR_ROW_STATUS_PTR para que señale a una matriz[R] de variables SQLUSSMALLINT que incluya indicadores de estado de filas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-112">Set SQL_ATTR_ROW_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="aa4db-113">Ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="aa4db-113">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="aa4db-114">Cada llamada a [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) o a [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) recupera R filas y transfiere los datos a las columnas enlazadas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-114">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
### <a name="to-use-row-wise-binding"></a><span data-ttu-id="aa4db-115">Para utilizar el enlace de modo de fila</span><span class="sxs-lookup"><span data-stu-id="aa4db-115">To use row-wise binding</span></span>  
  
1.  <span data-ttu-id="aa4db-116">Asigne una matriz [R] de estructuras, donde R es el número de filas del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-116">Allocate an array[R] of structures, where R is the number of rows in the rowset.</span></span> <span data-ttu-id="aa4db-117">La estructura tiene un elemento para cada columna y cada elemento tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="aa4db-117">The structure has one element for each column, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="aa4db-118">La primera parte es una variable del tipo de datos adecuado donde almacenar los datos de columnas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-118">The first part is a variable of the appropriate data type to hold the column data.</span></span>  
  
    -   <span data-ttu-id="aa4db-119">La segunda parte es una variable SQLINTEGER donde almacenar el indicador de estado de columnas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-119">The second part is a SQLINTEGER variable to hold the column status indicator.</span></span>  
  
2.  <span data-ttu-id="aa4db-120">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa4db-120">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="aa4db-121">Establezca SQL_ATTR_ROW_ARRAY_SIZE en el número de filas del conjunto de filas (R).</span><span class="sxs-lookup"><span data-stu-id="aa4db-121">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="aa4db-122">Establezca SQL_ATTR_ROW_BIND_TYPE en el tamaño de la estructura asignada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="aa4db-122">Set SQL_ATTR_ROW_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="aa4db-123">Establezca el atributo SQL_ATTR_ROWS_FETCHED_PTR para que señale a una variable SQLUINTEGER que incluya el número de filas capturadas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-123">Set the SQL_ATTR_ROWS_FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="aa4db-124">Establezca SQL_ATTR_PARAMS_STATUS_PTR para que señale a una matriz[R] de variables SQLUSSMALLINT que incluya indicadores de estado de filas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-124">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="aa4db-125">Para cada columna del conjunto de resultados, llame a [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) para que el valor de datos y puntero de longitud de datos de la columna señalen a sus variables en el primer elemento de la matriz de estructuras asignada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="aa4db-125">For each column in the result set, call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to point the data value and data length pointer of the column to their variables in the first element of the array of structures allocated in Step 1.</span></span>  
  
4.  <span data-ttu-id="aa4db-126">Ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="aa4db-126">Execute the statement.</span></span>  
  
5.  <span data-ttu-id="aa4db-127">Cada llamada a [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) o a [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) recupera R filas y transfiere los datos a las columnas enlazadas.</span><span class="sxs-lookup"><span data-stu-id="aa4db-127">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4db-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa4db-128">See Also</span></span>  
 <span data-ttu-id="aa4db-129">[Temas de procedimientos de uso de cursores &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="aa4db-129">[Using Cursors How-to Topics &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="aa4db-130">[Cómo se implementan los cursores](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span><span class="sxs-lookup"><span data-stu-id="aa4db-130">[How Cursors Are Implemented](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span></span>  
 [<span data-ttu-id="aa4db-131">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="aa4db-131">Use Cursors &#40;ODBC&#41;</span></span>](use-cursors-odbc.md)  
  
  
