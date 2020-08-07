---
title: Procesando instrucciones que generan mensajes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- PRINT statement
- messages [ODBC], statements generating messages
- statements [ODBC], message generation
- errors [ODBC], statements generating messages
- SQL Server Native Client ODBC driver, errors
- STATISTICS IO option
- STATISTICS TIME option
- DBCC statements
- SQLExecute function
- RAISERROR statement
- SQLGetDiagRec function
- ODBC error handling, statements generating messages
- SQLExecDirect function
ms.assetid: 672ebdc5-7fa1-4ceb-8d52-fd25ef646654
author: rothja
ms.author: jroth
ms.openlocfilehash: c26376eabb756d356dd71fb3bd8284a6b11dced7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745287"
---
# <a name="processing-statements-that-generate-messages"></a><span data-ttu-id="73bc9-102">Procesar instrucciones que generan mensajes</span><span class="sxs-lookup"><span data-stu-id="73bc9-102">Processing Statements That Generate Messages</span></span>
  <span data-ttu-id="73bc9-103">Las opciones STATISTICS TIME y STATISTICS IO de la instrucción SET de [!INCLUDE[tsql](../../includes/tsql-md.md)] se utilizan para obtener información que ayuda a diagnosticar las consultas de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="73bc9-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement options STATISTICS TIME and STATISTICS IO are used to get information that aids in diagnosing long-running queries.</span></span> <span data-ttu-id="73bc9-104">Las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] también admiten la opción SHOWPLAN para analizar los planes de consulta.</span><span class="sxs-lookup"><span data-stu-id="73bc9-104">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also support the SHOWPLAN option for analyzing query plans.</span></span> <span data-ttu-id="73bc9-105">Una aplicación ODBC puede establecer estas opciones ejecutando las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="73bc9-105">An ODBC application can set these options by executing the following statements:</span></span>  
  
```  
SQLExecDirect(hstmt, "SET SHOWPLAN ON", SQL_NTS);  
SQLExecDirect(hstmt, "SET STATISTICS TIME ON", SQL_NTS90  
);  
SQLExecDirect(hstmt, "SET STATISTICS IO ON", SQL_NTS);  
```  
  
 <span data-ttu-id="73bc9-106">Cuando SET STATISTICs TIME o SET SHOWPLAN son ON, **SQLExecute** y **SQLExecDirect** devuelven SQL_SUCCESS_WITH_INFO y, en ese momento, la aplicación puede recuperar la salida del plan de presentación o de estadísticas llamando a **SQLGetDiagRec** hasta que devuelve SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="73bc9-106">When SET STATISTICS TIME or SET SHOWPLAN are ON, **SQLExecute** and **SQLExecDirect** return SQL_SUCCESS_WITH_INFO, and, at that point, the application can retrieve the SHOWPLAN or STATISTICS TIME output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="73bc9-107">Cada línea de datos de SHOWPLAN se devuelve en el formato:</span><span class="sxs-lookup"><span data-stu-id="73bc9-107">Each line of SHOWPLAN data comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError=6223,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]   
              Table Scan"  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73bc9-108">versión 7.0 reemplazó la opción SHOWPLAN por SHOWPLAN_ALL y SHOWPLAN_TEXT, las dos devuelven la salida como un conjunto de resultados, no como un conjunto de mensajes.</span><span class="sxs-lookup"><span data-stu-id="73bc9-108">version 7.0 replaced the SHOWPLAN option with SHOWPLAN_ALL and SHOWPLAN_TEXT, both of which return output as a result set, not a set of messages.</span></span>  
  
 <span data-ttu-id="73bc9-109">Cada línea de STATISTICS TIME se devuelve en el formato:</span><span class="sxs-lookup"><span data-stu-id="73bc9-109">Each line of STATISTICS TIME comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3613,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
   SQL Server Parse and Compile Time: cpu time = 0 ms."  
```  
  
 <span data-ttu-id="73bc9-110">La salida de SET STATISTICS IO no está disponible hasta el final de un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="73bc9-110">The output of SET STATISTICS IO is not available until the end of a result set.</span></span> <span data-ttu-id="73bc9-111">Para obtener la salida de las estadísticas de e/s, la aplicación llama a **SQLGetDiagRec** en el momento en que **SQLFetch** o [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) devuelve SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="73bc9-111">To get STATISTICS IO output, the application calls **SQLGetDiagRec** at the time **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="73bc9-112">La salida de STATISTICS IO se devuelve en el formato:</span><span class="sxs-lookup"><span data-stu-id="73bc9-112">The output of STATISTICS IO comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3615,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table: testshow  scan count 1,  logical reads: 1,  
   physical reads: 0."  
```  
  
## <a name="using-dbcc-statements"></a><span data-ttu-id="73bc9-113">Utilizar instrucciones DBCC</span><span class="sxs-lookup"><span data-stu-id="73bc9-113">Using DBCC Statements</span></span>  
 <span data-ttu-id="73bc9-114">Las instrucciones DBCC devuelven los datos como mensajes, no como conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="73bc9-114">DBCC statements return their data as messages, not result sets.</span></span> <span data-ttu-id="73bc9-115">**SQLExecDirect** o **SQLExecute** devuelven SQL_SUCCESS_WITH_INFO, y la aplicación recupera la salida llamando a **SQLGetDiagRec** hasta que devuelve SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="73bc9-115">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and the application retrieves the output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="73bc9-116">Por ejemplo, la instrucción siguiente devuelve SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="73bc9-116">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect(hstmt, "DBCC CHECKTABLE(Authors)", SQL_NTS);  
```  
  
 <span data-ttu-id="73bc9-117">Las llamadas a **SQLGetDiagRec** devuelven:</span><span class="sxs-lookup"><span data-stu-id="73bc9-117">Calls to **SQLGetDiagRec** return:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 2536,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Checking authors"  
szSqlState = "01000", *pfNativeError = 2579,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   The total number of data pages in this table is 1."  
szSqlState = "01000", *pfNativeError = 7929,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table has 23 data rows."  
szSqlState = "01000", *pfNativeError = 2528  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   DBCC execution completed. If DBCC printed error messages,  
   see your System Administrator."  
```  
  
## <a name="using-print-and-raiserror-statements"></a><span data-ttu-id="73bc9-118">Utilizar instrucciones RAISERROR y PRINT</span><span class="sxs-lookup"><span data-stu-id="73bc9-118">Using PRINT and RAISERROR Statements</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="73bc9-119">Las instrucciones PRINT y RAISERROR también devuelven datos llamando a **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-119">PRINT and RAISERROR statements also return data by calling **SQLGetDiagRec**.</span></span> <span data-ttu-id="73bc9-120">Las instrucciones PRINT hacen que la ejecución de la instrucción SQL devuelva SQL_SUCCESS_WITH_INFO, y una llamada subsiguiente a **SQLGetDiagRec** devuelve un *SQLSTATE* de 01000.</span><span class="sxs-lookup"><span data-stu-id="73bc9-120">PRINT statements cause the SQL statement execution to return SQL_SUCCESS_WITH_INFO, and a subsequent call to **SQLGetDiagRec** returns a *SQLState* of 01000.</span></span> <span data-ttu-id="73bc9-121">Un RAISERROR con una gravedad de diez o inferior se comporta igual que PRINT.</span><span class="sxs-lookup"><span data-stu-id="73bc9-121">A RAISERROR with a severity of ten or lower behaves the same as PRINT.</span></span> <span data-ttu-id="73bc9-122">Una RAISERROR con una gravedad de 11 o superior hace que la ejecución devuelva SQL_ERROR, y una llamada subsiguiente a **SQLGetDiagRec** devuelve *SQLSTATE* 42000.</span><span class="sxs-lookup"><span data-stu-id="73bc9-122">A RAISERROR with a severity of 11 or higher causes the execute to return SQL_ERROR, and a subsequent call to **SQLGetDiagRec** returns *SQLState* 42000.</span></span> <span data-ttu-id="73bc9-123">Por ejemplo, la instrucción siguiente devuelve SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="73bc9-123">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "PRINT  'Some message' ", SQL_NTS);  
```  
  
 <span data-ttu-id="73bc9-124">La llamada a **SQLGetDiagRec** devuelve:</span><span class="sxs-lookup"><span data-stu-id="73bc9-124">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 0,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Some message"  
```  
  
 <span data-ttu-id="73bc9-125">La instrucción siguiente devuelve SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="73bc9-125">The following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 1.', 10, -1)",  
   SQL_NTS)  
```  
  
 <span data-ttu-id="73bc9-126">La llamada a **SQLGetDiagRec** devuelve:</span><span class="sxs-lookup"><span data-stu-id="73bc9-126">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 1."  
```  
  
 <span data-ttu-id="73bc9-127">La siguiente instrucción devuelve SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="73bc9-127">The following statement returns SQL_ERROR:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 2.', 11, -1)", SQL_NTS)  
```  
  
 <span data-ttu-id="73bc9-128">La llamada a **SQLGetDiagRec** devuelve:</span><span class="sxs-lookup"><span data-stu-id="73bc9-128">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "42000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 2."  
```  
  
 <span data-ttu-id="73bc9-129">La temporización de la llamada a **SQLGetDiagRec** es fundamental cuando la salida de las instrucciones Print o RAISERROR se incluye en un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="73bc9-129">The timing of calling **SQLGetDiagRec** is critical when output from PRINT or RAISERROR statements is included in a result set.</span></span> <span data-ttu-id="73bc9-130">La llamada a **SQLGetDiagRec** para recuperar la salida de Print o RAISERROR se debe realizar inmediatamente después de la instrucción que recibe SQL_ERROR o SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="73bc9-130">The call to **SQLGetDiagRec** to retrieve the PRINT or RAISERROR output must be made immediately after the statement that receives SQL_ERROR or SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="73bc9-131">Esto es sencillo cuando solo se ejecuta una instrucción SQL única, como en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="73bc9-131">This is straightforward when only a single SQL statement is executed, as in the examples above.</span></span> <span data-ttu-id="73bc9-132">En estos casos, la llamada a **SQLExecDirect** o **SQLExecute** devuelve SQL_ERROR o SQL_SUCCESS_WITH_INFO y se puede llamar a **SQLGetDiagRec** .</span><span class="sxs-lookup"><span data-stu-id="73bc9-132">In these cases, the call to **SQLExecDirect** or **SQLExecute** returns SQL_ERROR or SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** can then be called.</span></span> <span data-ttu-id="73bc9-133">Es menos sencillo al codificar los bucles para administrar la salida de un lote de instrucciones SQL o al ejecutar los procedimientos almacenados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73bc9-133">It is less straightforward when coding loops to handle the output of a batch of SQL statements or when executing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span>  
  
 <span data-ttu-id="73bc9-134">En este caso, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelve un conjunto de resultados para cada instrucción SELECT ejecutada en un lote o procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="73bc9-134">In this case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for every SELECT statement executed in a batch or stored procedure.</span></span> <span data-ttu-id="73bc9-135">Si el lote o procedimiento contiene instrucciones RAISERROR o PRINT, la salida de éstas se intercala con los conjuntos de resultados de la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="73bc9-135">If the batch or procedure contains PRINT or RAISERROR statements, the output for these is interleaved with the SELECT statement result sets.</span></span> <span data-ttu-id="73bc9-136">Si la primera instrucción del lote o procedimiento es PRINT o RAISERROR, **SQLExecute** o **SQLExecDirect** devuelve SQL_SUCCESS_WITH_INFO o SQL_ERROR, y la aplicación debe llamar a **SQLGetDiagRec** hasta que devuelva SQL_NO_DATA para recuperar la información de Print o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="73bc9-136">If the first statement in the batch or procedure is a PRINT or RAISERROR, the **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, and the application needs to call **SQLGetDiagRec** until it returns SQL_NO_DATA to retrieve the PRINT or RAISERROR information.</span></span>  
  
 <span data-ttu-id="73bc9-137">Si la instrucción PRINT o RAISERROR viene después de una instrucción SQL (por ejemplo, una instrucción SELECT), se devuelve la información de impresión o RAISERROR cuando se produce un error en las posiciones de [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)en el conjunto de resultados que contiene el error.</span><span class="sxs-lookup"><span data-stu-id="73bc9-137">If the PRINT or RAISERROR statement comes after an SQL statement (such as a SELECT statement), then the PRINT or RAISERROR information is returned when [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positions on the result set containing the error.</span></span> <span data-ttu-id="73bc9-138">**SQLMoreResults** devuelve SQL_SUCCESS_WITH_INFO o SQL_ERROR en función de la gravedad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="73bc9-138">**SQLMoreResults** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR depending on the severity of the message.</span></span> <span data-ttu-id="73bc9-139">Los mensajes se recuperan llamando a **SQLGetDiagRec** hasta que devuelva SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="73bc9-139">Messages are retrieved by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bc9-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73bc9-140">See Also</span></span>  
 [<span data-ttu-id="73bc9-141">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="73bc9-141">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
