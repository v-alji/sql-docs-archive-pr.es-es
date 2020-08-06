---
title: SQLSetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b8290fd90c0c9bb91f08d94e119689d38fbc04e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677040"
---
# <a name="sqlsetdescfield"></a><span data-ttu-id="db598-102">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="db598-102">SQLSetDescField</span></span>
  <span data-ttu-id="db598-103">SQLSetDescField se puede usar para establecer los campos de descriptor para los parámetros con valores de tabla y las columnas de parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="db598-103">SQLSetDescField can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="db598-104">Para obtener información acerca de los campos disponibles, vea campos de descriptor de [parámetros con valores de tabla](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) y [campos de descriptor para columnas de componentes de parámetros con valores de tabla](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span><span class="sxs-lookup"><span data-stu-id="db598-104">For information about the available fields, see [Table-Valued Parameter Descriptor Fields](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) and [Descriptor Fields for Table-Valued Parameter Constituent Columns](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db598-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db598-105">Remarks</span></span>  
 <span data-ttu-id="db598-106">Las columnas de parámetro con valores de tabla únicamente están disponibles cuando el campo de encabezado del descriptor SQL_SOPT_SS_PARAM_FOCUS está establecido en el ordinal de un registro con SQL_DESC_TYPE establecido en SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="db598-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="db598-107">Para obtener más información acerca de SQL_SOPT_SS_PARAM_FOCUS, vea [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="db598-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="db598-108">Si se realiza un intento de establecer SQL_SOPT_SS_PARAM_FOCUS en el ordinal de un parámetro que no es un parámetro con valores de tabla, SQLSetStmtAttr devuelve SQL_ERROR y se crea un registro de diagnóstico con SQLSTATE = HY024 y el mensaje "valor de atributo no válido".</span><span class="sxs-lookup"><span data-stu-id="db598-108">If an attempt is made to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a parameter that is not a table-valued parameter, SQLSetStmtAttr returns SQL_ERROR, and a diagnostic record is created with SQLSTATE = HY024 and the message "Invalid attribute value".</span></span> <span data-ttu-id="db598-109">SQL_SOPT_SS_PARAM_FOCUS no cambia cuando se devuelve SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="db598-109">SQL_SOPT_SS_PARAM_FOCUS is not changed when SQL_ERROR is returned.</span></span>  
  
 <span data-ttu-id="db598-110">Al establecer SQL_SOPT_SS_PARAM_FOCUS en 0, se restaura acceso a los registros descriptores para parámetros.</span><span class="sxs-lookup"><span data-stu-id="db598-110">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores access to descriptor records for parameters.</span></span>  
  
 <span data-ttu-id="db598-111">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="db598-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="db598-112">SQLSetDescField admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="db598-112">SQLSetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="db598-113">Las características de fecha y hora se han mejorado en ODBC.</span><span class="sxs-lookup"><span data-stu-id="db598-113">Date/time features have been enhanced in ODBC.</span></span> <span data-ttu-id="db598-114">Para obtener información sobre el campo descriptor proporcionado para los nuevos tipos de fecha y hora, vea [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="db598-114">For information about the descriptor field provided for the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="db598-115">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="db598-115">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="db598-116">SQLSetDescField admite UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="db598-116">SQLSetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="db598-117">SQLSetDescField admite tipos definidos por el usuario (UDT) CLR grandes.</span><span class="sxs-lookup"><span data-stu-id="db598-117">SQLSetDescField supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="db598-118">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="db598-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a><span data-ttu-id="db598-119">SQLSetDescField admite columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="db598-119">SQLSetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="db598-120">SQLSetDecField se puede usar para establecer SQL_SOPT_SS_NAME_SCOPE en el descriptor de parámetros de la aplicación (APD) en los valores SQL_SS_NAME_SCOPE_EXTENDED y SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="db598-120">SQLSetDecField can be used to set SQL_SOPT_SS_NAME_SCOPE in the application parameter descriptor (APD) to the values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span>  
  
 <span data-ttu-id="db598-121">Para obtener más información, consulte [compatibilidad con columnas Dispersas &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="db598-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db598-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db598-122">See Also</span></span>  
 <span data-ttu-id="db598-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span><span class="sxs-lookup"><span data-stu-id="db598-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span></span>  
 [<span data-ttu-id="db598-124">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="db598-124">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
