---
title: SQLSetDescRec | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescRec function
ms.assetid: 203d02a2-aa09-462b-a489-a2cdd6f6023b
author: rothja
ms.author: jroth
ms.openlocfilehash: f2a6c8084f092040a3fd4cccee50d6a3b940cc45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677039"
---
# <a name="sqlsetdescrec"></a><span data-ttu-id="5f76b-102">SQLSetDescRec</span><span class="sxs-lookup"><span data-stu-id="5f76b-102">SQLSetDescRec</span></span>
  <span data-ttu-id="5f76b-103">En este tema se describe la funcionalidad de SQLSetDescRec que es específica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5f76b-103">This topic discusses SQLSetDescRec functionality that is specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="sqlsetdescrec-and-table-valued-parameters"></a><span data-ttu-id="5f76b-104">SQLSetDescRec y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="5f76b-104">SQLSetDescRec and Table-Valued Parameters</span></span>  
 <span data-ttu-id="5f76b-105">SQLSetDescRec se puede usar para establecer los campos de descriptor para los parámetros con valores de tabla y las columnas de parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="5f76b-105">SQLSetDescRec can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="5f76b-106">Las columnas de parámetro con valores de tabla únicamente están disponibles cuando el campo de encabezado del descriptor SQL_SOPT_SS_PARAM_FOCUS está establecido en el ordinal de un registro con SQL_DESC_TYPE establecido en SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="5f76b-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="5f76b-107">Para obtener más información acerca de SQL_SOPT_SS_PARAM_FOCUS, vea [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="5f76b-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="5f76b-108">En la tabla siguiente se describe la asignación entre parámetros y campos descriptor.</span><span class="sxs-lookup"><span data-stu-id="5f76b-108">The following table describes the mapping between parameters and descriptor fields.</span></span>  
  
|<span data-ttu-id="5f76b-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="5f76b-109">Parameter</span></span>|<span data-ttu-id="5f76b-110">Atributo relacionado para tipos de parámetros que no son valores de tabla, incluidas columnas de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="5f76b-110">Related attribute for non-table-valued parameter types, including table-valued parameter columns</span></span>|<span data-ttu-id="5f76b-111">Atributo relacionado para parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="5f76b-111">Related attribute for table-valued parameters</span></span>|  
|---------------|--------------------------------------------------------------------------------------------------------|----------------------------------------------------|  
|<span data-ttu-id="5f76b-112">*Tipo*</span><span class="sxs-lookup"><span data-stu-id="5f76b-112">*Type*</span></span>|<span data-ttu-id="5f76b-113">SQL_DESC_TYPE</span><span class="sxs-lookup"><span data-stu-id="5f76b-113">SQL_DESC_TYPE</span></span>|<span data-ttu-id="5f76b-114">SQL_SS_TABLE</span><span class="sxs-lookup"><span data-stu-id="5f76b-114">SQL_SS_TABLE</span></span>|  
|<span data-ttu-id="5f76b-115">*Subtipo*</span><span class="sxs-lookup"><span data-stu-id="5f76b-115">*SubType*</span></span>|<span data-ttu-id="5f76b-116">Se ignora.</span><span class="sxs-lookup"><span data-stu-id="5f76b-116">Ignored</span></span>|<span data-ttu-id="5f76b-117">Para registros de tipo SQL_DATETIME o SQL_INTERVAL, establézcalo en SQL_DESC_DATETIME_INTERVAL_CODE.</span><span class="sxs-lookup"><span data-stu-id="5f76b-117">For records of type SQL_DATETIME or SQL_INTERVAL, set this to SQL_DESC_DATETIME_INTERVAL_CODE.</span></span>|  
|<span data-ttu-id="5f76b-118">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="5f76b-118">*Length*</span></span>|<span data-ttu-id="5f76b-119">SQL_DESC_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5f76b-119">SQL_DESC_OCTET_LENGTH</span></span>|<span data-ttu-id="5f76b-120">Longitud del nombre de tipo de parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="5f76b-120">The length of the table-valued parameter type name.</span></span> <span data-ttu-id="5f76b-121">Puede ser SQL_NTS si el nombre de tipo termina en NULL, o cero si no se requiere el nombre de tipo de parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="5f76b-121">This can be SQL_NTS if the type name is null terminated, or zero if the table-valued parameter type name is not required.</span></span>|  
|<span data-ttu-id="5f76b-122">*Precisión*</span><span class="sxs-lookup"><span data-stu-id="5f76b-122">*Precision*</span></span>|<span data-ttu-id="5f76b-123">SQL_DESC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5f76b-123">SQL_DESC_PRECISION</span></span>|<span data-ttu-id="5f76b-124">SQL_DESC_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="5f76b-124">SQL_DESC_ARRAY_SIZE</span></span>|  
|<span data-ttu-id="5f76b-125">*Escala*</span><span class="sxs-lookup"><span data-stu-id="5f76b-125">*Scale*</span></span>|<span data-ttu-id="5f76b-126">SQL_DESC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5f76b-126">SQL_DESC_SCALE</span></span>|<span data-ttu-id="5f76b-127">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="5f76b-127">Unused.</span></span> <span data-ttu-id="5f76b-128">Este parámetro debería ser cero.</span><span class="sxs-lookup"><span data-stu-id="5f76b-128">This parameter should be zero.</span></span>|  
|<span data-ttu-id="5f76b-129">*DataPtr*</span><span class="sxs-lookup"><span data-stu-id="5f76b-129">*DataPtr*</span></span>|<span data-ttu-id="5f76b-130">SQL_DESC_DATA_PTR en APD</span><span class="sxs-lookup"><span data-stu-id="5f76b-130">SQL_DESC_DATA_PTR in APD</span></span>|<span data-ttu-id="5f76b-131">SQL_CA_SS_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5f76b-131">SQL_CA_SS_TYPE_NAME</span></span><br /><br /> <span data-ttu-id="5f76b-132">Este parámetro es opcional para las llamadas a procedimientos almacenados y puede especificarse NULL si no se requiere.</span><span class="sxs-lookup"><span data-stu-id="5f76b-132">This parameter is optional for stored procedure calls, and NULL can be specified if it is not required.</span></span> <span data-ttu-id="5f76b-133">Este parámetro se debe especificar en instrucciones SQL que no son llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="5f76b-133">This parameter must be specified for SQL statements that are not procedure calls.</span></span><br /><br /> <span data-ttu-id="5f76b-134">*DataPtr* también actúa como un valor único que la aplicación puede usar para identificar este parámetro con valores de tabla cuando se usa el enlace de filas variable.</span><span class="sxs-lookup"><span data-stu-id="5f76b-134">*DataPtr* also serves as a unique value that the application can use to identify this table-valued parameter when variable row binding is used.</span></span>|  
|<span data-ttu-id="5f76b-135">*StringLengthPtr*</span><span class="sxs-lookup"><span data-stu-id="5f76b-135">*StringLengthPtr*</span></span>|<span data-ttu-id="5f76b-136">SQL_DESC_OCTET_LENGTH_PTR</span><span class="sxs-lookup"><span data-stu-id="5f76b-136">SQL_DESC_OCTET_LENGTH_PTR</span></span>|<span data-ttu-id="5f76b-137">SQL_DESC_OCTET_LENGTH_PTR</span><span class="sxs-lookup"><span data-stu-id="5f76b-137">SQL_DESC_OCTET_LENGTH_PTR</span></span><br /><br /> <span data-ttu-id="5f76b-138">Para un parámetro con valores de tabla, éste es el número de filas que se van a transferir o SQL_DATA_AT_EXEC.</span><span class="sxs-lookup"><span data-stu-id="5f76b-138">For a table-valued parameter, this is the number of rows to transfer or SQL_DATA_AT_EXEC.</span></span> <span data-ttu-id="5f76b-139">Es un puntero a un valor que contiene el número de filas que se van a transferir con SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="5f76b-139">This is a pointer to a value that holds the number of rows to transfer with SQLExecDirect.</span></span>|  
|<span data-ttu-id="5f76b-140">*IndicatorPtr*</span><span class="sxs-lookup"><span data-stu-id="5f76b-140">*IndicatorPtr*</span></span>|<span data-ttu-id="5f76b-141">SQL_DESC_INDICATOR_PTR</span><span class="sxs-lookup"><span data-stu-id="5f76b-141">SQL_DESC_INDICATOR_PTR</span></span>|<span data-ttu-id="5f76b-142">SQL_DESC_INDICATOR_PTR</span><span class="sxs-lookup"><span data-stu-id="5f76b-142">SQL_DESC_INDICATOR_PTR</span></span>|  
  
 <span data-ttu-id="5f76b-143">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="5f76b-143">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescrec-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="5f76b-144">SQLSetDescRec admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="5f76b-144">SQLSetDescRec Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="5f76b-145">Los valores permitidos para los tipos de fecha y hora son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f76b-145">The values allowed for date/time types are as follows:</span></span>  
  
||<span data-ttu-id="5f76b-146">*Tipo*</span><span class="sxs-lookup"><span data-stu-id="5f76b-146">*Type*</span></span>|<span data-ttu-id="5f76b-147">*Subtipo*</span><span class="sxs-lookup"><span data-stu-id="5f76b-147">*SubType*</span></span>|<span data-ttu-id="5f76b-148">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="5f76b-148">*Length*</span></span>|<span data-ttu-id="5f76b-149">*Precisión*</span><span class="sxs-lookup"><span data-stu-id="5f76b-149">*Precision*</span></span>|<span data-ttu-id="5f76b-150">*Escala*</span><span class="sxs-lookup"><span data-stu-id="5f76b-150">*Scale*</span></span>|  
|-|------------|---------------|--------------|-----------------|-------------|  
|<span data-ttu-id="5f76b-151">datetime</span><span class="sxs-lookup"><span data-stu-id="5f76b-151">datetime</span></span>|<span data-ttu-id="5f76b-152">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="5f76b-152">SQL_DATETIME</span></span>|<span data-ttu-id="5f76b-153">SQL_CODE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="5f76b-153">SQL_CODE_TIMESTAMP</span></span>|<span data-ttu-id="5f76b-154">4</span><span class="sxs-lookup"><span data-stu-id="5f76b-154">4</span></span>|<span data-ttu-id="5f76b-155">3</span><span class="sxs-lookup"><span data-stu-id="5f76b-155">3</span></span>|<span data-ttu-id="5f76b-156">3</span><span class="sxs-lookup"><span data-stu-id="5f76b-156">3</span></span>|  
|<span data-ttu-id="5f76b-157">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="5f76b-157">smalldatetime</span></span>|<span data-ttu-id="5f76b-158">SQL_SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="5f76b-158">SQL_SQL_DATETIME</span></span>|<span data-ttu-id="5f76b-159">SQL_CODE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="5f76b-159">SQL_CODE_TIMESTAMP</span></span>|<span data-ttu-id="5f76b-160">8</span><span class="sxs-lookup"><span data-stu-id="5f76b-160">8</span></span>|<span data-ttu-id="5f76b-161">0</span><span class="sxs-lookup"><span data-stu-id="5f76b-161">0</span></span>|<span data-ttu-id="5f76b-162">0</span><span class="sxs-lookup"><span data-stu-id="5f76b-162">0</span></span>|  
|<span data-ttu-id="5f76b-163">date</span><span class="sxs-lookup"><span data-stu-id="5f76b-163">date</span></span>|<span data-ttu-id="5f76b-164">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="5f76b-164">SQL_DATETIME</span></span>|<span data-ttu-id="5f76b-165">SQL_CODE_DATE</span><span class="sxs-lookup"><span data-stu-id="5f76b-165">SQL_CODE_DATE</span></span>|<span data-ttu-id="5f76b-166">6</span><span class="sxs-lookup"><span data-stu-id="5f76b-166">6</span></span>|<span data-ttu-id="5f76b-167">0</span><span class="sxs-lookup"><span data-stu-id="5f76b-167">0</span></span>|<span data-ttu-id="5f76b-168">0</span><span class="sxs-lookup"><span data-stu-id="5f76b-168">0</span></span>|  
|<span data-ttu-id="5f76b-169">time</span><span class="sxs-lookup"><span data-stu-id="5f76b-169">time</span></span>|<span data-ttu-id="5f76b-170">SQL_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="5f76b-170">SQL_SS_TIME2</span></span>|<span data-ttu-id="5f76b-171">0</span><span class="sxs-lookup"><span data-stu-id="5f76b-171">0</span></span>|<span data-ttu-id="5f76b-172">10</span><span class="sxs-lookup"><span data-stu-id="5f76b-172">10</span></span>|<span data-ttu-id="5f76b-173">0..7</span><span class="sxs-lookup"><span data-stu-id="5f76b-173">0..7</span></span>|<span data-ttu-id="5f76b-174">0..7</span><span class="sxs-lookup"><span data-stu-id="5f76b-174">0..7</span></span>|  
|<span data-ttu-id="5f76b-175">datetime2</span><span class="sxs-lookup"><span data-stu-id="5f76b-175">datetime2</span></span>|<span data-ttu-id="5f76b-176">SQL_DATETIME</span><span class="sxs-lookup"><span data-stu-id="5f76b-176">SQL_DATETIME</span></span>|<span data-ttu-id="5f76b-177">SQL_CODE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="5f76b-177">SQL_CODE_TIMESTAMP</span></span>|<span data-ttu-id="5f76b-178">16</span><span class="sxs-lookup"><span data-stu-id="5f76b-178">16</span></span>|<span data-ttu-id="5f76b-179">0..7</span><span class="sxs-lookup"><span data-stu-id="5f76b-179">0..7</span></span>|<span data-ttu-id="5f76b-180">0..7</span><span class="sxs-lookup"><span data-stu-id="5f76b-180">0..7</span></span>|  
|<span data-ttu-id="5f76b-181">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="5f76b-181">datetimeoffset</span></span>|<span data-ttu-id="5f76b-182">SQL_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="5f76b-182">SQL_SS_TIMESTAMPOFFSET</span></span>|<span data-ttu-id="5f76b-183">0</span><span class="sxs-lookup"><span data-stu-id="5f76b-183">0</span></span>|<span data-ttu-id="5f76b-184">20</span><span class="sxs-lookup"><span data-stu-id="5f76b-184">20</span></span>|<span data-ttu-id="5f76b-185">0..7</span><span class="sxs-lookup"><span data-stu-id="5f76b-185">0..7</span></span>|<span data-ttu-id="5f76b-186">0..7</span><span class="sxs-lookup"><span data-stu-id="5f76b-186">0..7</span></span>|  
  
 <span data-ttu-id="5f76b-187">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="5f76b-187">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescrec-support-for-large-clr-udts"></a><span data-ttu-id="5f76b-188">SQLSetDescRec admite UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="5f76b-188">SQLSetDescRec Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="5f76b-189">`SQLSetDescRec` admite tipos CLR definidos por el usuario (UDT) grandes.</span><span class="sxs-lookup"><span data-stu-id="5f76b-189">`SQLSetDescRec` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="5f76b-190">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="5f76b-190">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f76b-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f76b-191">See Also</span></span>  
 <span data-ttu-id="5f76b-192">[SQLSetDescRec](https://go.microsoft.com/fwlink/?LinkId=80704) </span><span class="sxs-lookup"><span data-stu-id="5f76b-192">[SQLSetDescRec](https://go.microsoft.com/fwlink/?LinkId=80704) </span></span>  
 [<span data-ttu-id="5f76b-193">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="5f76b-193">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  