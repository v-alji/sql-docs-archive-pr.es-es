---
title: Usar una instrucción (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ff3bc8c545cc9b55f0da3bb31d68d1ecbb5b547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749288"
---
# <a name="use-a-statement-odbc"></a><span data-ttu-id="b8c21-102">Usar una instrucción (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b8c21-102">Use a Statement (ODBC)</span></span>
    
### <a name="to-use-a-statement"></a><span data-ttu-id="b8c21-103">Para utilizar una instrucción</span><span class="sxs-lookup"><span data-stu-id="b8c21-103">To use a statement</span></span>  
  
1.  <span data-ttu-id="b8c21-104">Llame a [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un *HandleType* de SQL_HANDLE_STMT para asignar un identificador de instrucción.</span><span class="sxs-lookup"><span data-stu-id="b8c21-104">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a *HandleType* of SQL_HANDLE_STMT to allocate a statement handle.</span></span>  
  
2.  <span data-ttu-id="b8c21-105">Opcionalmente, llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer las opciones de la instrucción o a [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) para obtener atributos de instrucción.</span><span class="sxs-lookup"><span data-stu-id="b8c21-105">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set statement options or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get statement attributes.</span></span>  
  
     <span data-ttu-id="b8c21-106">Para utilizar cursores de servidor, debe establecer los atributos de cursor en valores distintos de sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b8c21-106">To use server cursors, you must set cursor attributes to values other than their defaults.</span></span>  
  
3.  <span data-ttu-id="b8c21-107">Opcionalmente, si la instrucción se va a ejecutar varias veces, prepárela para la ejecución con [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="b8c21-107">Optionally, if the statement will be executed several times, prepare the statement for execution with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span>  
  
4.  <span data-ttu-id="b8c21-108">Opcionalmente, si la instrucción ha enlazado marcadores de parámetros, enlace los marcadores de parámetros a las variables del programa utilizando [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="b8c21-108">Optionally, if the statement has bound parameter markers, bind the parameter markers to program variables by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="b8c21-109">Si se ha preparado la instrucción, puede llamar a [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) y [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number y characteristics of the parameters.</span><span class="sxs-lookup"><span data-stu-id="b8c21-109">If the statement was prepared, you can call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) and [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number and characteristics of the parameters.</span></span>  
  
5.  <span data-ttu-id="b8c21-110">Ejecute directamente una instrucción utilizando SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="b8c21-110">Execute a statement directly by using SQLExecDirect.</span></span>  
  
     <span data-ttu-id="b8c21-111">\- o -</span><span class="sxs-lookup"><span data-stu-id="b8c21-111">\- or -</span></span>  
  
     <span data-ttu-id="b8c21-112">Si se ha preparado la instrucción, ejecútela varias veces utilizando [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span><span class="sxs-lookup"><span data-stu-id="b8c21-112">If the statement was prepared, execute it multiple times by using [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span></span>  
  
     <span data-ttu-id="b8c21-113">\- o -</span><span class="sxs-lookup"><span data-stu-id="b8c21-113">\- or -</span></span>  
  
     <span data-ttu-id="b8c21-114">Llame a una función de catálogo, que devuelve los resultados.</span><span class="sxs-lookup"><span data-stu-id="b8c21-114">Call a catalog function, which returns results.</span></span>  
  
6.  <span data-ttu-id="b8c21-115">Procese los resultados enlazando las columnas del conjunto de resultados a variables de programa, moviendo los datos de las columnas del conjunto de resultados a las variables del programa mediante [SQLGetData](../../native-client-odbc-api/sqlgetdata.md)o una combinación de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="b8c21-115">Process the results by binding the result set columns to program variables, by moving data from the result set columns to program variables by using [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), or a combination of the two methods.</span></span>  
  
     <span data-ttu-id="b8c21-116">Capture una fila cada vez del conjunto de resultados de una instrucción.</span><span class="sxs-lookup"><span data-stu-id="b8c21-116">Fetch through the result set of a statement one row at a time.</span></span>  
  
     <span data-ttu-id="b8c21-117">\- o -</span><span class="sxs-lookup"><span data-stu-id="b8c21-117">\- or -</span></span>  
  
     <span data-ttu-id="b8c21-118">Capture varias filas cada vez del conjunto de resultados mediante un cursor de bloque.</span><span class="sxs-lookup"><span data-stu-id="b8c21-118">Fetch through the result set several rows at a time by using a block cursor.</span></span>  
  
     <span data-ttu-id="b8c21-119">\- o -</span><span class="sxs-lookup"><span data-stu-id="b8c21-119">\- or -</span></span>  
  
     <span data-ttu-id="b8c21-120">Llame a [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) para determinar el número de filas afectado por una instrucción INSERT, UPDATE o DELETE.</span><span class="sxs-lookup"><span data-stu-id="b8c21-120">Call [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) to determine the number of rows affected by an INSERT, UPDATE, or DELETE statement.</span></span>  
  
     <span data-ttu-id="b8c21-121">Si la instrucción SQL puede tener varios conjuntos de resultados, llame a [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) al final de cada conjunto de resultados para determinar si hay más conjuntos de resultados que procesar.</span><span class="sxs-lookup"><span data-stu-id="b8c21-121">If the SQL statement can have multiple result sets, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) at the end of each result set to see if there are additional result sets to process.</span></span>  
  
7.  <span data-ttu-id="b8c21-122">Una vez procesados los resultados, pueden requerirse las acciones siguientes para que el identificador de instrucción esté disponible para ejecutar una nueva instrucción:</span><span class="sxs-lookup"><span data-stu-id="b8c21-122">After results are processed, the following actions may be necessary to make the statement handle available to execute a new statement:</span></span>  
  
    -   <span data-ttu-id="b8c21-123">Si no llamó a [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) hasta que se devolvió SQL_NO_DATA, llame a [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) para cerrar el cursor.</span><span class="sxs-lookup"><span data-stu-id="b8c21-123">If you did not call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) until it returned SQL_NO_DATA, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) to close the cursor.</span></span>  
  
    -   <span data-ttu-id="b8c21-124">Si ha enlazado marcadores de parámetros a las variables del programa, llame a [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con *Option* establecido en SQL_RESET_PARAMS para liberar los parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="b8c21-124">If you bound parameter markers to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_RESET_PARAMS to free the bound parameters.</span></span>  
  
    -   <span data-ttu-id="b8c21-125">Si ha enlazado columnas de conjuntos de resultados a las variables del programa, llame a [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con *Option* establecido en SQL_UNBIND para liberar las columnas enlazadas.</span><span class="sxs-lookup"><span data-stu-id="b8c21-125">If you bound result set columns to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_UNBIND to free the bound columns.</span></span>  
  
    -   <span data-ttu-id="b8c21-126">Para reutilizar el identificador de instrucción, vaya al paso 2.</span><span class="sxs-lookup"><span data-stu-id="b8c21-126">To reuse the statement handle, go to Step 2.</span></span>  
  
8.  <span data-ttu-id="b8c21-127">Llame a [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) con un *HandleType* de SQL_HANDLE_STMT para liberar el identificador de instrucción.</span><span class="sxs-lookup"><span data-stu-id="b8c21-127">Call [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) with a *HandleType* of SQL_HANDLE_STMT to free the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8c21-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8c21-128">See Also</span></span>  
 [<span data-ttu-id="b8c21-129">Temas de procedimientos de ejecución de consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b8c21-129">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
