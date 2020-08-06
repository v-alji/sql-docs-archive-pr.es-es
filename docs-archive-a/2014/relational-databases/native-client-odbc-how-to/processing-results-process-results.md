---
title: Procesar resultados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- processing results [ODBC]
ms.assetid: 4810fe3f-78ee-4f0d-8bcc-a4659fbcf46f
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a22e9d7280f88de7799c31d2d0611e5299043d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748761"
---
# <a name="process-results-odbc"></a><span data-ttu-id="be27b-102">Procesar resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="be27b-102">Process Results (ODBC)</span></span>
    
### <a name="to-process-results"></a><span data-ttu-id="be27b-103">Para procesar resultados</span><span class="sxs-lookup"><span data-stu-id="be27b-103">To process results</span></span>  
  
1.  <span data-ttu-id="be27b-104">Recupere información del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="be27b-104">Retrieve result set information.</span></span>  
  
2.  <span data-ttu-id="be27b-105">Si se usan columnas enlazadas, por cada columna a la que quiera enlazar, llame a [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) para enlazar un búfer de programa a la columna.</span><span class="sxs-lookup"><span data-stu-id="be27b-105">If bound columns are used, for each column you want to bind to, call [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) to bind a program buffer to the column.</span></span>  
  
3.  <span data-ttu-id="be27b-106">Por cada fila del conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="be27b-106">For each row in the result set:</span></span>  
  
    -   <span data-ttu-id="be27b-107">Llame a [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) para obtener la siguiente fila.</span><span class="sxs-lookup"><span data-stu-id="be27b-107">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) to get the next row.</span></span>  
  
    -   <span data-ttu-id="be27b-108">Si se utilizan columnas enlazadas, utilice los datos que están ahora disponibles en los búferes de columna enlazada.</span><span class="sxs-lookup"><span data-stu-id="be27b-108">If bound columns are used, use the data now available in the bound column buffers.</span></span>  
  
    -   <span data-ttu-id="be27b-109">Si se usan columnas sin enlazar, llame a [SQLGetData](../native-client-odbc-api/sqlgetdata.md) una o más veces para obtener los datos de las columnas sin enlazar después de la última columna enlazada.</span><span class="sxs-lookup"><span data-stu-id="be27b-109">If unbound columns are used, call [SQLGetData](../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column.</span></span> <span data-ttu-id="be27b-110">Las llamadas a `SQLGetData` deber estar en orden creciente de número de columna.</span><span class="sxs-lookup"><span data-stu-id="be27b-110">Calls to `SQLGetData` should be in increasing order of column number.</span></span>  
  
    -   <span data-ttu-id="be27b-111">Llame a `SQLGetData` varias veces para obtener datos de una columna de texto o de imagen.</span><span class="sxs-lookup"><span data-stu-id="be27b-111">Call `SQLGetData` multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="be27b-112">Cuando [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) señale el fin del conjunto de resultados devolviendo SQL_NO_DATA, llame a [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) para determinar si está disponible otro conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="be27b-112">When [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signals the end of the result set by returning SQL_NO_DATA, call [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="be27b-113">Si devuelve SQL_SUCCESS, está disponible otro conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="be27b-113">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="be27b-114">Si devuelve SQL_NO_DATA, no hay ningún otro conjunto de resultados disponible.</span><span class="sxs-lookup"><span data-stu-id="be27b-114">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="be27b-115">Si devuelve SQL_SUCCESS_WITH_INFO o SQL_ERROR, llame a [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) para determinar si está disponible la salida de una instrucción PRINT o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="be27b-115">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
         <span data-ttu-id="be27b-116">Si se utilizan parámetros de instrucción enlazados como parámetros de salida o como valor devuelto de un procedimiento almacenado, utilice los datos ahora disponibles en los búferes de parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="be27b-116">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span> <span data-ttu-id="be27b-117">Asimismo, si se usan parámetros enlazados, cada llamada a [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) o [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) ejecutará la instrucción SQL *S* veces, donde *S* es el número de elementos en la matriz de parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="be27b-117">Also, when bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement *S* times, where *S* is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="be27b-118">Esto significa que habrá *S* conjuntos de resultados para procesar, donde cada conjunto de resultados comprende todos los conjuntos de resultados, parámetros de salida y códigos de retorno devueltos normalmente por una ejecución única de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="be27b-118">This means that there will be *S* sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="be27b-119">Cuando un conjunto de resultados contiene filas del cálculo, cada fila del cálculo está disponible como un conjunto de resultados independiente.</span><span class="sxs-lookup"><span data-stu-id="be27b-119">When a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="be27b-120">Estos conjuntos de resultados de cálculo se intercalan entre las filas normales e interrumpen las filas normales en varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="be27b-120">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
5.  <span data-ttu-id="be27b-121">Opcionalmente, llame a [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) con SQL_UNBIND para liberar los búferes de columna enlazada.</span><span class="sxs-lookup"><span data-stu-id="be27b-121">Optionally, call [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
6.  <span data-ttu-id="be27b-122">Si está disponible otro conjunto de resultados, vaya al paso 1.</span><span class="sxs-lookup"><span data-stu-id="be27b-122">If another result set is available, go to Step 1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be27b-123">Para cancelar el procesamiento de un conjunto de resultados antes de que [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) devuelva SQL_NO_DATA, llame a [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="be27b-123">To cancel processing a result set before [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) returns SQL_NO_DATA, call [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be27b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be27b-124">See Also</span></span>  
 [<span data-ttu-id="be27b-125">Temas de procedimientos de procesamiento de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="be27b-125">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
