---
title: SQLGetData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
author: rothja
ms.author: jroth
ms.openlocfilehash: c351cf7340bc7b0afeb76b139bd75aa429f56e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662009"
---
# <a name="sqlgetdata"></a><span data-ttu-id="0b696-102">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="0b696-102">SQLGetData</span></span>
  <span data-ttu-id="0b696-103">**SQLGetData** se usa para recuperar datos del conjunto de resultados sin enlazar valores de columna.</span><span class="sxs-lookup"><span data-stu-id="0b696-103">**SQLGetData** is used to retrieve result set data without binding column values.</span></span> <span data-ttu-id="0b696-104">Se puede llamar sucesivamente a**SQLGetData** en la misma columna para recuperar cantidades grandes de datos de una columna con un tipo de datos **text**, **ntext**o **image** .</span><span class="sxs-lookup"><span data-stu-id="0b696-104">**SQLGetData** can be called successively on the same column to retrieve large amounts of data from a column with a **text**, **ntext**, or **image** data type.</span></span>  
  
 <span data-ttu-id="0b696-105">No es necesario que una aplicación enlace variables para capturar datos del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b696-105">There is no requirement that an application bind variables to fetch result set data.</span></span> <span data-ttu-id="0b696-106">Los datos de cualquier columna se pueden recuperar del controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client mediante **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="0b696-106">The data of any column can be retrieved from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by using **SQLGetData**.</span></span>  
  
 <span data-ttu-id="0b696-107">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client no permite usar **SQLGetData** para recuperar datos en orden aleatorio de columna.</span><span class="sxs-lookup"><span data-stu-id="0b696-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using **SQLGetData** to retrieve data in random column order.</span></span> <span data-ttu-id="0b696-108">Todas las columnas sin enlazar procesadas con **SQLGetData** deben tener los ordinales de las columnas más altos que los de las columnas enlazadas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b696-108">All unbound columns processed with **SQLGetData** must have higher column ordinals than the bound columns in the result set.</span></span> <span data-ttu-id="0b696-109">La aplicación debe procesar datos desde el valor ordinal de la columna sin enlazar más bajo hasta el valor más alto.</span><span class="sxs-lookup"><span data-stu-id="0b696-109">The application must process data from the lowest unbound ordinal column value to the highest.</span></span> <span data-ttu-id="0b696-110">Al intentar recuperar datos de una columna con un número ordinal más bajo, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="0b696-110">Attempting to retrieve data from a lower ordinally numbered column results in an error.</span></span> <span data-ttu-id="0b696-111">Si la aplicación está usando cursores de servidor para notificar las filas del conjunto de resultados, la aplicación puede intentar volver a capturar la fila actual y, a continuación, capturar el valor de una columna.</span><span class="sxs-lookup"><span data-stu-id="0b696-111">If the application is using server cursors to report result set rows, the application can refetch the current row and then fetch the value of a column.</span></span> <span data-ttu-id="0b696-112">Si una instrucción se ejecuta en el valor predeterminado de solo lectura, cursor de solo avance, se debe volver a ejecutar la instrucción para realizar un copia de seguridad de **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="0b696-112">If a statement is executed on the default read-only, forward-only cursor, you must re-execute the statement to back up **SQLGetData**.</span></span>  
  
 <span data-ttu-id="0b696-113">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client notifica con precisión la longitud de los datos recuperados **text**, **ntext**e **image** mediante **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="0b696-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver accurately reports the length of **text**, **ntext**, and **image** data retrieved using **SQLGetData**.</span></span> <span data-ttu-id="0b696-114">La aplicación puede hacer buen uso del parámetro *StrLen_or_IndPtr* devuelto para recuperar rápidamente los datos largos.</span><span class="sxs-lookup"><span data-stu-id="0b696-114">The application can make good use of the *StrLen_or_IndPtr* parameter return to retrieve long data rapidly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b696-115">Para tipos de valor grandes, *StrLen_or_IndPtr* devolverá SQL_NO_TOTAL en casos de truncamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="0b696-115">For large value types, *StrLen_or_IndPtr* will return SQL_NO_TOTAL in cases of data truncation.</span></span>  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="0b696-116">SQLGetData admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="0b696-116">SQLGetData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="0b696-117">Los valores de las columnas de resultados de los tipos de fecha y hora se convierten como se describe en [conversiones de SQL a C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="0b696-117">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="0b696-118">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0b696-118">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a><span data-ttu-id="0b696-119">SQLGetData admite UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="0b696-119">SQLGetData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="0b696-120">**SQLGetData** admite los tipos definidos por el usuario (UDT) CLR grandes.</span><span class="sxs-lookup"><span data-stu-id="0b696-120">**SQLGetData** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="0b696-121">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0b696-121">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b696-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b696-122">Example</span></span>  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b696-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b696-123">See Also</span></span>  
 <span data-ttu-id="0b696-124">[SQLGetData, función](https://go.microsoft.com/fwlink/?LinkId=59350) </span><span class="sxs-lookup"><span data-stu-id="0b696-124">[SQLGetData Function](https://go.microsoft.com/fwlink/?LinkId=59350) </span></span>  
 [<span data-ttu-id="0b696-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="0b696-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
