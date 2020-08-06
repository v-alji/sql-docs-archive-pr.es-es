---
title: Preparar y ejecutar una instrucción (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
- statement preparation
ms.assetid: 0adecc63-4da5-486c-bc48-09a004a2fae6
author: rothja
ms.author: jroth
ms.openlocfilehash: 607d8ad1509eca1204f6d029842b04120d3f5d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749287"
---
# <a name="prepare-and-execute-a-statement-odbc"></a><span data-ttu-id="09a35-102">Preparar y ejecutar una instrucción (ODBC)</span><span class="sxs-lookup"><span data-stu-id="09a35-102">Prepare and Execute a Statement (ODBC)</span></span>
    
### <a name="to-prepare-a-statement-once-and-then-execute-it-multiple-times"></a><span data-ttu-id="09a35-103">Para preparar una instrucción una sola vez y ejecutarla varias veces</span><span class="sxs-lookup"><span data-stu-id="09a35-103">To prepare a statement once, and then execute it multiple times</span></span>  
  
1.  <span data-ttu-id="09a35-104">Llame a [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) para preparar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="09a35-104">Call [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) to prepare the statement.</span></span>  
  
2.  <span data-ttu-id="09a35-105">Puede llamar a [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) para determinar el número de parámetros de la instrucción preparada.</span><span class="sxs-lookup"><span data-stu-id="09a35-105">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
3.  <span data-ttu-id="09a35-106">Para cada uno de los parámetros de la instrucción preparada, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09a35-106">Optionally, for each parameter in the prepared statement:</span></span>  
  
    -   <span data-ttu-id="09a35-107">Llamar a [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) para obtener información sobre los parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-107">Call [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to get parameter information.</span></span>  
  
    -   <span data-ttu-id="09a35-108">Enlazar cada parámetro a una variable de programa utilizando [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="09a35-108">Bind each parameter to a program variable by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="09a35-109">Configurar cualquier parámetro de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="09a35-109">Set up any data-at-execution parameters.</span></span>  
  
4.  <span data-ttu-id="09a35-110">Para cada ejecución de una instrucción preparada:</span><span class="sxs-lookup"><span data-stu-id="09a35-110">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="09a35-111">Si la instrucción incluye marcadores de parámetros, coloque los valores de datos en el búfer de parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="09a35-111">If the statement has parameter markers, put the data values into the bound parameter buffer.</span></span>  
  
    -   <span data-ttu-id="09a35-112">Llame a [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) para ejecutar la instrucción preparada.</span><span class="sxs-lookup"><span data-stu-id="09a35-112">Call [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="09a35-113">Si se usan parámetros de entrada de datos en ejecución, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) devuelve SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="09a35-113">If data-at-execution input parameters are used, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="09a35-114">Envíe los datos en fragmentos utilizyo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) y [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="09a35-114">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-prepare-a-statement-with-column-wise-parameter-binding"></a><span data-ttu-id="09a35-115">Para preparar una instrucción con enlace de parámetros de modo de columna</span><span class="sxs-lookup"><span data-stu-id="09a35-115">To prepare a statement with column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="09a35-116">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="09a35-116">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="09a35-117">Establezca SQL_ATTR_PARAMSET_SIZE en el número de conjuntos (S) de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-117">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="09a35-118">Establezca SQL_ATTR_PARAM_BIND_TYPE en SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="09a35-118">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="09a35-119">Establezca el atributo SQL_ATTR_PARAMS_PROCESSED_PTR para que señale a una variable SQLUINTEGER que incluya el número de parámetros procesados.</span><span class="sxs-lookup"><span data-stu-id="09a35-119">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="09a35-120">Establezca SQL_ATTR_PARAMS_STATUS_PTR para que señale a una matriz[S] de variables SQLUSSMALLINT que incluya indicadores de estado de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-120">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="09a35-121">Llame a SQLPrepare para preparar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="09a35-121">Call SQLPrepare to prepare the statement.</span></span>  
  
3.  <span data-ttu-id="09a35-122">Puede llamar a [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) para determinar el número de parámetros de la instrucción preparada.</span><span class="sxs-lookup"><span data-stu-id="09a35-122">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
4.  <span data-ttu-id="09a35-123">Opcionalmente, para cada parámetro de la instrucción preparada, llame a SQLDescribeParam para obtener información sobre los parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-123">Optionally, for each parameter in the prepared statement, call SQLDescribeParam to get parameter information.</span></span>  
  
5.  <span data-ttu-id="09a35-124">Para cada marcador de parámetro:</span><span class="sxs-lookup"><span data-stu-id="09a35-124">For each parameter marker:</span></span>  
  
    -   <span data-ttu-id="09a35-125">Asigne una matriz de S búferes de parámetros donde almacenar los valores de datos.</span><span class="sxs-lookup"><span data-stu-id="09a35-125">Allocate an array of S parameter buffers to store data values.</span></span>  
  
    -   <span data-ttu-id="09a35-126">Asigne una matriz de S búferes de parámetros donde almacenar las longitudes de datos.</span><span class="sxs-lookup"><span data-stu-id="09a35-126">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="09a35-127">Llame a SQLBindParameter para enlazar el valor de datos de parámetro y las matrices de longitud de datos al parámetro de instrucción.</span><span class="sxs-lookup"><span data-stu-id="09a35-127">Call SQLBindParameter to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
    -   <span data-ttu-id="09a35-128">Si el parámetro es un parámetro de imagen o texto de datos en ejecución, configúrelo.</span><span class="sxs-lookup"><span data-stu-id="09a35-128">If the parameter is a data-at-execution text or image parameter, set it up.</span></span>  
  
    -   <span data-ttu-id="09a35-129">Si se utiliza algún parámetro de datos en ejecución, configúrelo.</span><span class="sxs-lookup"><span data-stu-id="09a35-129">If any data-at-execution parameters are used, set them up.</span></span>  
  
6.  <span data-ttu-id="09a35-130">Para cada ejecución de una instrucción preparada:</span><span class="sxs-lookup"><span data-stu-id="09a35-130">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="09a35-131">Coloque los S valores de datos y S longitudes de datos en las matrices de parámetros enlazadas.</span><span class="sxs-lookup"><span data-stu-id="09a35-131">Put the S data values and S data lengths into the bound parameter arrays.</span></span>  
  
    -   <span data-ttu-id="09a35-132">Llame a SQLExecute para ejecutar la instrucción preparada.</span><span class="sxs-lookup"><span data-stu-id="09a35-132">Call SQLExecute to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="09a35-133">Si se usan parámetros de entrada de datos en ejecución, SQLExecute devuelve SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="09a35-133">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="09a35-134">Envíe los datos en fragmentos utilizyo SQLParamData y SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="09a35-134">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
### <a name="to-prepare-a-statement-with-row-wise-bound-parameters"></a><span data-ttu-id="09a35-135">Para preparar una instrucción con parámetros enlazados de modo de fila</span><span class="sxs-lookup"><span data-stu-id="09a35-135">To prepare a statement with row-wise bound parameters</span></span>  
  
1.  <span data-ttu-id="09a35-136">Asigne una matriz[S] de estructuras, donde S es el número de conjuntos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-136">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="09a35-137">La estructura tiene un elemento para cada parámetro y cada elemento tiene dos partes:</span><span class="sxs-lookup"><span data-stu-id="09a35-137">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="09a35-138">La primera parte es una variable del tipo de datos adecuado donde almacenar los datos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-138">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
    -   <span data-ttu-id="09a35-139">La segunda parte es una variable SQLINTEGER donde almacenar el indicador de estado.</span><span class="sxs-lookup"><span data-stu-id="09a35-139">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="09a35-140">Llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="09a35-140">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="09a35-141">Establezca SQL_ATTR_PARAMSET_SIZE en el número de conjuntos (S) de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-141">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="09a35-142">Establezca SQL_ATTR_PARAM_BIND_TYPE en el tamaño de la estructura asignada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="09a35-142">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="09a35-143">Establezca el atributo SQL_ATTR_PARAMS_PROCESSED_PTR para que señale a una variable SQLUINTEGER que incluya el número de parámetros procesados.</span><span class="sxs-lookup"><span data-stu-id="09a35-143">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="09a35-144">Establezca SQL_ATTR_PARAMS_STATUS_PTR para que señale a una matriz[S] de variables SQLUSSMALLINT que incluya indicadores de estado de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-144">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="09a35-145">Llame a SQLPrepare para preparar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="09a35-145">Call SQLPrepare to prepare the statement.</span></span>  
  
4.  <span data-ttu-id="09a35-146">Para cada marcador de parámetro, llame a SQLBindParameter para que el valor de datos de parámetro y el puntero de longitud de datos apunten a sus variables en el primer elemento de la matriz de estructuras asignada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="09a35-146">For each parameter marker, call SQLBindParameter to point the parameter data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="09a35-147">Si el parámetro es un parámetro de datos en ejecución, configúrelo.</span><span class="sxs-lookup"><span data-stu-id="09a35-147">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
5.  <span data-ttu-id="09a35-148">Para cada ejecución de una instrucción preparada:</span><span class="sxs-lookup"><span data-stu-id="09a35-148">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="09a35-149">Rellene la matriz de búferes de parámetros enlazados con valores de datos.</span><span class="sxs-lookup"><span data-stu-id="09a35-149">Fill the bound parameter buffer array with data values.</span></span>  
  
    -   <span data-ttu-id="09a35-150">Llame a SQLExecute para ejecutar la instrucción preparada.</span><span class="sxs-lookup"><span data-stu-id="09a35-150">Call SQLExecute to execute the prepared statement.</span></span> <span data-ttu-id="09a35-151">El controlador ejecuta eficazmente la instrucción SQL S veces, una vez para cada conjunto de parámetros.</span><span class="sxs-lookup"><span data-stu-id="09a35-151">The driver efficiently executes the SQL statement S times, once for each set of parameters.</span></span>  
  
    -   <span data-ttu-id="09a35-152">Si se usan parámetros de entrada de datos en ejecución, SQLExecute devuelve SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="09a35-152">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="09a35-153">Envíe los datos en fragmentos utilizyo SQLParamData y SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="09a35-153">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a35-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09a35-154">See Also</span></span>  
 [<span data-ttu-id="09a35-155">Temas de procedimientos de ejecución de consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="09a35-155">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
