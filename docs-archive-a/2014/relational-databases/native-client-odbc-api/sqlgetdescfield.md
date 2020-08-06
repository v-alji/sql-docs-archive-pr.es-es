---
title: SQLGetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetDescField function
ms.assetid: 3e59a37a-28ee-4c91-8968-7fe3b966739d
author: rothja
ms.author: jroth
ms.openlocfilehash: 4538396dbfb5406d0464c4730c1f6f3bd5882799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674099"
---
# <a name="sqlgetdescfield"></a><span data-ttu-id="2eaf8-102">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="2eaf8-102">SQLGetDescField</span></span>
  <span data-ttu-id="2eaf8-103">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client solamente expone campos de descriptor específicos del controlador para el descriptor de fila de implementación (IRD).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver exposes driver-specific descriptor fields for the implementation row descriptor (IRD) only.</span></span> <span data-ttu-id="2eaf8-104">En IRD, se hace referencia a los campos de descriptor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de atributos de columna específicos del controlador.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-104">Within the IRD, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] descriptor fields are referenced through driver-specific column attributes.</span></span> <span data-ttu-id="2eaf8-105">Para obtener información sobre una lista completa de campos de descriptor específicos del controlador disponibles, vea [SQLColAttribute](sqlcolattribute.md).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-105">For information about a complete list of available driver-specific descriptor fields, see [SQLColAttribute](sqlcolattribute.md).</span></span>  
  
 <span data-ttu-id="2eaf8-106">Los campos de descriptor que contienen cadenas de identificador de columna son a menudo cadenas de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-106">Descriptor fields that contain column identifier strings are often zero-length strings.</span></span> <span data-ttu-id="2eaf8-107">Todos los valores de campos de descriptor específicos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-107">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific descriptor field values are read-only.</span></span>  
  
 <span data-ttu-id="2eaf8-108">Al igual que los atributos recuperados con SQLColAttribute, los campos de descriptor que notifican atributos de nivel de fila (como SQL_CA_SS_COMPUTE_ID) se notifican para todas las columnas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-108">Like attributes retrieved with SQLColAttribute, descriptor fields that report row-level attributes (such as SQL_CA_SS_COMPUTE_ID) are reported for all columns in the result set.</span></span>  
  
## <a name="sqlgetdescfield-and-table-valued-parameters"></a><span data-ttu-id="2eaf8-109">SQLGetDescField y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="2eaf8-109">SQLGetDescField and Table-Valued Parameters</span></span>  
 <span data-ttu-id="2eaf8-110">SQLGetDescField se puede usar para obtener valores para atributos extendidos de parámetros con valores de tabla y columnas de parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-110">SQLGetDescField can be used to get values for extended attributes of table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="2eaf8-111">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="2eaf8-112">SQLGetDescField admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="2eaf8-112">SQLGetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="2eaf8-113">Para obtener información sobre los campos de descriptor disponibles con los nuevos tipos de fecha y hora, vea [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-113">For information about the descriptor fields available with the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="2eaf8-114">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-114">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
 <span data-ttu-id="2eaf8-115">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , SQLGetDescField puede devolver `SQL_C_SS_TIME2` (para los `time` tipos) o `SQL_C_SS_TIMESTAMPOFFSET` (para `datetimeoffset` ) en lugar de `SQL_C_BINARY` , si la aplicación usa ODBC 3,8.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-115">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], SQLGetDescField can return `SQL_C_SS_TIME2` (for `time` types) or `SQL_C_SS_TIMESTAMPOFFSET` (for `datetimeoffset`) instead of `SQL_C_BINARY`, if your application uses ODBC 3.8.</span></span>  
  
## <a name="sqlgetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="2eaf8-116">SQLGetDescField admite UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="2eaf8-116">SQLGetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="2eaf8-117">`SQLGetDescField` admite tipos CLR definidos por el usuario (UDT) grandes.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-117">`SQLGetDescField` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="2eaf8-118">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-sparse-columns"></a><span data-ttu-id="2eaf8-119">SQLGetDescField admite columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="2eaf8-119">SQLGetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="2eaf8-120">SQLGetDescField se puede usar para consultar el nuevo campo IRD SQL_CA_SS_IS_COLUMN_SET para determinar si una columna es una `column_set` columna.</span><span class="sxs-lookup"><span data-stu-id="2eaf8-120">SQLGetDescField can be used to query the new IRD field SQL_CA_SS_IS_COLUMN_SET to determine if a column is a `column_set` column.</span></span>  
  
 <span data-ttu-id="2eaf8-121">Para obtener más información, consulte [compatibilidad con columnas Dispersas &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2eaf8-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2eaf8-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2eaf8-122">Example</span></span>  
  
```  
typedef struct tagCOMPUTEBYLIST  
    {  
    SQLSMALLINT nBys;  
    SQLSMALLINT aByList[1];  
    } COMPUTEBYLIST;  
typedef COMPUTEBYLIST* PCOMPUTEBYLIST;   
  
SQLHDESC    hIRD;   
SQLINTEGER  cbIRD;   
SQLINTEGER  nSet = 0;   
  
// . . .  
// Execute a statement that contains a COMPUTE clause,  
//  then get the descriptor handle of the IRD and  
//  get some IRD values.  
  
SQLGetStmtAttr(g_hStmt, SQL_ATTR_IMP_ROW_DESC,  
    (SQLPOINTER) &hIRD, sizeof(SQLHDESC), &cbIRD);  
  
// For statement-wide column attributes, any  
//  descriptor record will do. You know that 1 exists,  
//  so use it.  
SQLGetDescField(hIRD, 1, SQL_CA_SS_NUM_COMPUTES,  
    (SQLPOINTER) &nComputes, SQL_IS_INTEGER, &cbIRD);  
  
if (nSet == 0)  
    {  
    SQLINTEGER      nOrderID;  
  
    printf_s("Normal result set.\n");  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ORDER,  
            (SQLPOINTER) &nOrderID, SQL_IS_INTEGER,  
            &cbIRD);  
  
        if (nOrderID != 0)  
            {  
            printf_s("Col in ORDER BY, pos: %ld",  
                nOrderID);  
            }  
            printf_s("\n");  
        }  
  
    printf_s("\n");  
    }  
else  
    {  
    PCOMPUTEBYLIST  pByList;  
    SQLSMALLINT     nBy;  
    SQLINTEGER      nColID;  
  
    printf_s("Computed result set number: %lu\n",  
        nSet);  
  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_BYLIST,  
        (SQLPOINTER) &pByList, SQL_IS_INTEGER,  
        &cbIRD);  
  
    if (pByList != NULL)  
        {  
        printf_s("Clause ordered by columns: ");  
        for (nBy = 0; nBy < pByList->nBys; )  
            {  
            printf_s("%u", pByList->aByList[nBy]);  
            nBy++;  
  
            if (nBy == pByList->nBys)  
                {  
                printf_s("\n");  
                }  
            else  
                {  
                printf_s(", ");  
                }  
            }  
        }  
    else  
        {  
        printf_s("Compute clause set not ordered.\n");  
        }  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ID, (SQLPOINTER) &nColID,  
            SQL_IS_INTEGER, &cbIRD);  
        printf_s("ColumnID: %lu, nColID);  
        }  
    printf_s("\n");  
    }  
  
if (SQLMoreResults(g_hStmt) == SQL_SUCCESS)  
    {  
    // Determine the result set indicator.  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_ID,  
        (SQLPOINTER) &nSet, SQL_IS_INTEGER, &cbIRD);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="2eaf8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2eaf8-123">See Also</span></span>  
 <span data-ttu-id="2eaf8-124">[SQLGetDescField función)](https://go.microsoft.com/fwlink/?LinkId=59351) </span><span class="sxs-lookup"><span data-stu-id="2eaf8-124">[SQLGetDescField Function](https://go.microsoft.com/fwlink/?LinkId=59351) </span></span>  
 [<span data-ttu-id="2eaf8-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="2eaf8-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
