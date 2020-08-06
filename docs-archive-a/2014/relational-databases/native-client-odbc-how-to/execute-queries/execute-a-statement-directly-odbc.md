---
title: Ejecutar directamente una instrucción (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
ms.assetid: b690f9de-66e1-4ee5-ab6a-121346fb5f85
author: rothja
ms.author: jroth
ms.openlocfilehash: 2aeada906a925cff93455ffd92e7c17822a80124
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661986"
---
# <a name="execute-a-statement-directly-odbc"></a><span data-ttu-id="98317-102">Ejecutar directamente una instrucción (ODBC)</span><span class="sxs-lookup"><span data-stu-id="98317-102">Execute a Statement Directly (ODBC)</span></span>
    
### <a name="to-execute-a-statement-directly-and-one-time-only"></a><span data-ttu-id="98317-103">Para ejecutar directamente y solo una vez una instrucción</span><span class="sxs-lookup"><span data-stu-id="98317-103">To execute a statement directly and one time only</span></span>  
  
1.  <span data-ttu-id="98317-104">Si la instrucción tiene marcadores de parámetro, utilice [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) para enlazar cada parámetro a una variable de programa.</span><span class="sxs-lookup"><span data-stu-id="98317-104">If the statement has parameter markers, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind each parameter to a program variable.</span></span> <span data-ttu-id="98317-105">Llene las variables de programa de valores de datos y, a continuación, prepare los parámetros de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="98317-105">Fill the program variables with data values, and then set up any data-at-execution parameters.</span></span>  
  
2.  <span data-ttu-id="98317-106">Llame a [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="98317-106">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span>  
  
3.  <span data-ttu-id="98317-107">Si se usan parámetros de entrada de datos en ejecución, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) devuelve SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="98317-107">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="98317-108">Envíe los datos en fragmentos utilizyo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) y [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="98317-108">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-column-wise-parameter-binding"></a><span data-ttu-id="98317-109">Para ejecutar varias veces una instrucción utilizando el enlace de parámetro de modo de columna</span><span class="sxs-lookup"><span data-stu-id="98317-109">To execute a statement multiple times by using column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="98317-110">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="98317-110">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="98317-111">Establezca SQL_ATTR_PARAMSET_SIZE en el número de conjuntos (S) de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-111">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="98317-112">Establezca SQL_ATTR_PARAM_BIND_TYPE en SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="98317-112">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
     <span data-ttu-id="98317-113">Establezca el atributo SQL_ATTR_PARAMS_PROCESSED_PTR para que señale a una variable SQLUINTEGER que incluya el número de parámetros procesados.</span><span class="sxs-lookup"><span data-stu-id="98317-113">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="98317-114">Establezca SQL_ATTR_PARAMS_STATUS_PTR para que señale a una matriz[S] de variables SQLUSSMALLINT que incluya los indicadores de estado de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-114">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="98317-115">Para cada marcador de parámetro:</span><span class="sxs-lookup"><span data-stu-id="98317-115">For each parameter marker:</span></span>  
  
     <span data-ttu-id="98317-116">Asigne una matriz de S búferes de parámetros donde almacenar los valores de datos.</span><span class="sxs-lookup"><span data-stu-id="98317-116">Allocate an array of S parameter buffers to store data values.</span></span>  
  
     <span data-ttu-id="98317-117">Asigne una matriz de S búferes de parámetros donde almacenar las longitudes de datos.</span><span class="sxs-lookup"><span data-stu-id="98317-117">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
     <span data-ttu-id="98317-118">Llame a [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) para enlazar el valor de datos de parámetro y las matrices de longitud de datos al parámetro de instrucción.</span><span class="sxs-lookup"><span data-stu-id="98317-118">Call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
     <span data-ttu-id="98317-119">Prepare los parámetros de texto o imagen de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="98317-119">Set up any data-at-execution text or image parameters.</span></span>  
  
     <span data-ttu-id="98317-120">Coloque S valores de datos y S longitudes de datos en las matrices de parámetros enlazadas.</span><span class="sxs-lookup"><span data-stu-id="98317-120">Put S data values and S data lengths into the bound parameter arrays.</span></span>  
  
3.  <span data-ttu-id="98317-121">Llame a [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="98317-121">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="98317-122">El controlador ejecuta eficazmente la instrucción S veces, una vez para cada conjunto de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-122">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
4.  <span data-ttu-id="98317-123">Si se usan parámetros de entrada de datos en ejecución, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) devuelve SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="98317-123">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="98317-124">Envíe los datos en fragmentos utilizyo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) y [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="98317-124">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-row-wise-parameter-binding"></a><span data-ttu-id="98317-125">Para ejecutar varias veces una instrucción utilizando el enlace de parámetro de modo de fila</span><span class="sxs-lookup"><span data-stu-id="98317-125">To execute a statement multiple times by using row-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="98317-126">Asigne una matriz[S] de estructuras, donde S es el número de conjuntos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-126">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="98317-127">La estructura tiene un elemento para cada parámetro y cada elemento tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="98317-127">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
     <span data-ttu-id="98317-128">La primera parte es una variable del tipo de datos adecuado donde almacenar los datos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-128">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
     <span data-ttu-id="98317-129">La segunda parte es una variable SQLINTEGER donde almacenar el indicador de estado.</span><span class="sxs-lookup"><span data-stu-id="98317-129">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="98317-130">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="98317-130">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="98317-131">Establezca SQL_ATTR_PARAMSET_SIZE en el número de conjuntos (S) de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-131">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="98317-132">Establezca SQL_ATTR_PARAM_BIND_TYPE en el tamaño de la estructura asignada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="98317-132">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
     <span data-ttu-id="98317-133">Establezca el atributo SQL_ATTR_PARAMS_PROCESSED_PTR para que señale a una variable SQLUINTEGER que incluya el número de parámetros procesados.</span><span class="sxs-lookup"><span data-stu-id="98317-133">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="98317-134">Establezca SQL_ATTR_PARAMS_STATUS_PTR para que señale a una matriz[S] de variables SQLUSSMALLINT que incluya los indicadores de estado de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-134">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="98317-135">Para cada marcador de parámetro, llame a [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) para que el valor de datos de parámetro y el puntero de longitud de datos señalen a sus variables en el primer elemento de la matriz de estructuras asignada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="98317-135">For each parameter marker, call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to point the parameter's data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="98317-136">Si el parámetro es un parámetro de datos en ejecución, configúrelo.</span><span class="sxs-lookup"><span data-stu-id="98317-136">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
4.  <span data-ttu-id="98317-137">Rellene la matriz de búferes de parámetros enlazados con valores de datos.</span><span class="sxs-lookup"><span data-stu-id="98317-137">Fill the bound parameter buffer array with data values.</span></span>  
  
5.  <span data-ttu-id="98317-138">Llame a [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="98317-138">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="98317-139">El controlador ejecuta eficazmente la instrucción S veces, una vez para cada conjunto de parámetros.</span><span class="sxs-lookup"><span data-stu-id="98317-139">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
6.  <span data-ttu-id="98317-140">Si se usan parámetros de entrada de datos en ejecución, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) devuelve SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="98317-140">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="98317-141">Envíe los datos en fragmentos utilizyo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) y [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="98317-141">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
 <span data-ttu-id="98317-142">**Nota** Los enlaces de modo de columna y de modo de fila se usan con mayor frecuencia con [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) y [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) que con [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="98317-142">**Note** Column-wise and row-wise binding are more typically used in conjunction with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) and [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) than with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98317-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98317-143">See Also</span></span>  
 [<span data-ttu-id="98317-144">Temas de procedimientos de ejecución de consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="98317-144">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
