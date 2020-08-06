---
title: bcp_gettypename | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_gettypename
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_gettypename function
ms.assetid: 65f036d1-f60e-4b8a-97b3-76fccf0dfed4
author: rothja
ms.author: jroth
ms.openlocfilehash: b2d92498b9d863fa2cb700ec4d88868c0984c4d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671054"
---
# <a name="bcp_gettypename"></a><span data-ttu-id="3d741-102">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="3d741-102">bcp_gettypename</span></span>
  <span data-ttu-id="3d741-103">Devuelve el nombre del tipo SQL para un token del tipo BCP especificado.</span><span class="sxs-lookup"><span data-stu-id="3d741-103">Returns the SQL type name for a specified BCP type token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d741-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d741-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_gettypename (  
INT   
token  
,  
DBBOOL   
fIsMaxType  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d741-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3d741-105">Arguments</span></span>  
 <span data-ttu-id="3d741-106">*token*</span><span class="sxs-lookup"><span data-stu-id="3d741-106">*token*</span></span>  
 <span data-ttu-id="3d741-107">Valor que indica un token de tipo BCP.</span><span class="sxs-lookup"><span data-stu-id="3d741-107">A value indicating a BCP type token.</span></span>  
  
 <span data-ttu-id="3d741-108">*campo*</span><span class="sxs-lookup"><span data-stu-id="3d741-108">*field*</span></span>  
 <span data-ttu-id="3d741-109">Indica si el token solicitado es un tipo max.</span><span class="sxs-lookup"><span data-stu-id="3d741-109">Indicates if token requested is a max type.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3d741-110">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="3d741-110">Returns</span></span>  
 <span data-ttu-id="3d741-111">Una cadena que contiene el nombre del tipo SQL que corresponde al tipo BCP.</span><span class="sxs-lookup"><span data-stu-id="3d741-111">A string containing the SQL type name corresponding to the BCP type.</span></span> <span data-ttu-id="3d741-112">Si se especifica un tipo BCP no válido, se devuelve una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="3d741-112">If an invalid BCP type is specified, an empty string is returned..</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d741-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3d741-113">Remarks</span></span>  
 <span data-ttu-id="3d741-114">Los tokens de tipo BCP se definen en el archivo de encabezado sqlncli.h y en la biblioteca sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="3d741-114">The BCP type tokens are defined in the sqlncli.h header file and the sqlncli11.lib library.</span></span>  
  
 <span data-ttu-id="3d741-115">La tabla siguiente especifica los posibles tipos BCP, tanto si son o no tipos max, y la salida esperada.</span><span class="sxs-lookup"><span data-stu-id="3d741-115">The table below specifies the possible BCP types, whether or not they are max types, and the expected output.</span></span>  
  
|<span data-ttu-id="3d741-116">Nombre de tipo de BCP</span><span class="sxs-lookup"><span data-stu-id="3d741-116">BCP type name</span></span>|<span data-ttu-id="3d741-117">MaxType</span><span class="sxs-lookup"><span data-stu-id="3d741-117">MaxType</span></span>|<span data-ttu-id="3d741-118">Output</span><span class="sxs-lookup"><span data-stu-id="3d741-118">Output</span></span>|  
|-------------------|-------------|------------|  
|`SQLDECIMAL`|<span data-ttu-id="3d741-119">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-119">Either</span></span>|<span data-ttu-id="3d741-120">**decimal**</span><span class="sxs-lookup"><span data-stu-id="3d741-120">**decimal**</span></span>|  
|`SQLNUMERIC`|<span data-ttu-id="3d741-121">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-121">Either</span></span>|<span data-ttu-id="3d741-122">**numeric**</span><span class="sxs-lookup"><span data-stu-id="3d741-122">**numeric**</span></span>|  
|`SQLINT1`|<span data-ttu-id="3d741-123">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-123">Either</span></span>|<span data-ttu-id="3d741-124">**tinyint**</span><span class="sxs-lookup"><span data-stu-id="3d741-124">**tinyint**</span></span>|  
|`SQLINT2`|<span data-ttu-id="3d741-125">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-125">Either</span></span>|<span data-ttu-id="3d741-126">**smallint**</span><span class="sxs-lookup"><span data-stu-id="3d741-126">**smallint**</span></span>|  
|`SQLINT4`|<span data-ttu-id="3d741-127">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-127">Either</span></span>|<span data-ttu-id="3d741-128">**int**</span><span class="sxs-lookup"><span data-stu-id="3d741-128">**int**</span></span>|  
|`SQLMONEY`|<span data-ttu-id="3d741-129">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-129">Either</span></span>|<span data-ttu-id="3d741-130">**money**</span><span class="sxs-lookup"><span data-stu-id="3d741-130">**money**</span></span>|  
|`SQLFLT8`|<span data-ttu-id="3d741-131">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-131">Either</span></span>|<span data-ttu-id="3d741-132">**float**</span><span class="sxs-lookup"><span data-stu-id="3d741-132">**float**</span></span>|  
|`SQLDATETIME`|<span data-ttu-id="3d741-133">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-133">Either</span></span>|<span data-ttu-id="3d741-134">**datetime**</span><span class="sxs-lookup"><span data-stu-id="3d741-134">**datetime**</span></span>|  
|`SQLBITN`|<span data-ttu-id="3d741-135">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-135">Either</span></span>|<span data-ttu-id="3d741-136">**bit-null**</span><span class="sxs-lookup"><span data-stu-id="3d741-136">**bit-null**</span></span>|  
|`SQLBIT`|<span data-ttu-id="3d741-137">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-137">Either</span></span>|<span data-ttu-id="3d741-138">**bit**</span><span class="sxs-lookup"><span data-stu-id="3d741-138">**bit**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="3d741-139">No</span><span class="sxs-lookup"><span data-stu-id="3d741-139">No</span></span>|<span data-ttu-id="3d741-140">**char**</span><span class="sxs-lookup"><span data-stu-id="3d741-140">**char**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="3d741-141">No</span><span class="sxs-lookup"><span data-stu-id="3d741-141">No</span></span>|<span data-ttu-id="3d741-142">**char**</span><span class="sxs-lookup"><span data-stu-id="3d741-142">**char**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="3d741-143">No</span><span class="sxs-lookup"><span data-stu-id="3d741-143">No</span></span>|<span data-ttu-id="3d741-144">**varchar**</span><span class="sxs-lookup"><span data-stu-id="3d741-144">**varchar**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="3d741-145">No</span><span class="sxs-lookup"><span data-stu-id="3d741-145">No</span></span>|<span data-ttu-id="3d741-146">**varchar**</span><span class="sxs-lookup"><span data-stu-id="3d741-146">**varchar**</span></span>|  
|`SQLTEXT`|<span data-ttu-id="3d741-147">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-147">Either</span></span>|<span data-ttu-id="3d741-148">**text**</span><span class="sxs-lookup"><span data-stu-id="3d741-148">**text**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="3d741-149">No</span><span class="sxs-lookup"><span data-stu-id="3d741-149">No</span></span>|<span data-ttu-id="3d741-150">**binary**</span><span class="sxs-lookup"><span data-stu-id="3d741-150">**binary**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="3d741-151">No</span><span class="sxs-lookup"><span data-stu-id="3d741-151">No</span></span>|<span data-ttu-id="3d741-152">**Binario**</span><span class="sxs-lookup"><span data-stu-id="3d741-152">**Binary**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="3d741-153">No</span><span class="sxs-lookup"><span data-stu-id="3d741-153">No</span></span>|<span data-ttu-id="3d741-154">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="3d741-154">**Varbinary**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="3d741-155">No</span><span class="sxs-lookup"><span data-stu-id="3d741-155">No</span></span>|<span data-ttu-id="3d741-156">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="3d741-156">**Varbinary**</span></span>|  
|`SQLIMAGE`|<span data-ttu-id="3d741-157">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-157">Either</span></span>|<span data-ttu-id="3d741-158">**Image**</span><span class="sxs-lookup"><span data-stu-id="3d741-158">**Image**</span></span>|  
|`SQLINTN`|<span data-ttu-id="3d741-159">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-159">Either</span></span>|<span data-ttu-id="3d741-160">**int-null**</span><span class="sxs-lookup"><span data-stu-id="3d741-160">**int-null**</span></span>|  
|`SQLDATETIMN`|<span data-ttu-id="3d741-161">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-161">Either</span></span>|<span data-ttu-id="3d741-162">**datetime-null**</span><span class="sxs-lookup"><span data-stu-id="3d741-162">**datetime-null**</span></span>|  
|`SQLMONEYN`|<span data-ttu-id="3d741-163">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-163">Either</span></span>|<span data-ttu-id="3d741-164">**money-null**</span><span class="sxs-lookup"><span data-stu-id="3d741-164">**money-null**</span></span>|  
|`SQLFLTN`|<span data-ttu-id="3d741-165">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-165">Either</span></span>|<span data-ttu-id="3d741-166">**float-null**</span><span class="sxs-lookup"><span data-stu-id="3d741-166">**float-null**</span></span>|  
|`SQLAOPSUM`|<span data-ttu-id="3d741-167">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-167">Either</span></span>|<span data-ttu-id="3d741-168">**Sum**</span><span class="sxs-lookup"><span data-stu-id="3d741-168">**Sum**</span></span>|  
|`SQLAOPAVG`|<span data-ttu-id="3d741-169">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-169">Either</span></span>|<span data-ttu-id="3d741-170">**Avg**</span><span class="sxs-lookup"><span data-stu-id="3d741-170">**Avg**</span></span>|  
|`SQLAOPCNT`|<span data-ttu-id="3d741-171">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-171">Either</span></span>|<span data-ttu-id="3d741-172">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="3d741-172">**Count**</span></span>|  
|`SQLAOPMIN`|<span data-ttu-id="3d741-173">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-173">Either</span></span>|<span data-ttu-id="3d741-174">**Min**</span><span class="sxs-lookup"><span data-stu-id="3d741-174">**Min**</span></span>|  
|`SQLAOPMAX`|<span data-ttu-id="3d741-175">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-175">Either</span></span>|<span data-ttu-id="3d741-176">**Max**</span><span class="sxs-lookup"><span data-stu-id="3d741-176">**Max**</span></span>|  
|`SQLDATETIM4`|<span data-ttu-id="3d741-177">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-177">Either</span></span>|<span data-ttu-id="3d741-178">**smalldatetime**</span><span class="sxs-lookup"><span data-stu-id="3d741-178">**smalldatetime**</span></span>|  
|`SQLMONEY4`|<span data-ttu-id="3d741-179">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-179">Either</span></span>|<span data-ttu-id="3d741-180">**Smallmoney**</span><span class="sxs-lookup"><span data-stu-id="3d741-180">**Smallmoney**</span></span>|  
|`SQLFLT4`|<span data-ttu-id="3d741-181">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-181">Either</span></span>|<span data-ttu-id="3d741-182">**Impuestos**</span><span class="sxs-lookup"><span data-stu-id="3d741-182">**Real**</span></span>|  
|`SQLUNIQUEID`|<span data-ttu-id="3d741-183">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-183">Either</span></span>|<span data-ttu-id="3d741-184">**uniqueidentifier**</span><span class="sxs-lookup"><span data-stu-id="3d741-184">**uniqueidentifier**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="3d741-185">No</span><span class="sxs-lookup"><span data-stu-id="3d741-185">No</span></span>|<span data-ttu-id="3d741-186">**Nchar**</span><span class="sxs-lookup"><span data-stu-id="3d741-186">**Nchar**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="3d741-187">No</span><span class="sxs-lookup"><span data-stu-id="3d741-187">No</span></span>|<span data-ttu-id="3d741-188">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="3d741-188">**Nvarchar**</span></span>|  
|`SQLNTEXT`|<span data-ttu-id="3d741-189">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-189">Either</span></span>|<span data-ttu-id="3d741-190">**Ntext**</span><span class="sxs-lookup"><span data-stu-id="3d741-190">**Ntext**</span></span>|  
|`SQLVARIANT`|<span data-ttu-id="3d741-191">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-191">Either</span></span>|<span data-ttu-id="3d741-192">**sql_variant**</span><span class="sxs-lookup"><span data-stu-id="3d741-192">**sql_variant**</span></span>|  
|`SQLINT8`|<span data-ttu-id="3d741-193">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-193">Either</span></span>|<span data-ttu-id="3d741-194">**BIGINT**</span><span class="sxs-lookup"><span data-stu-id="3d741-194">**Bigint**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="3d741-195">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-195">Yes</span></span>|<span data-ttu-id="3d741-196">**ntext**</span><span class="sxs-lookup"><span data-stu-id="3d741-196">**varchar(max)**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="3d741-197">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-197">Yes</span></span>|<span data-ttu-id="3d741-198">**ntext**</span><span class="sxs-lookup"><span data-stu-id="3d741-198">**varchar(max)**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="3d741-199">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-199">Yes</span></span>|<span data-ttu-id="3d741-200">**ntext**</span><span class="sxs-lookup"><span data-stu-id="3d741-200">**varchar(max)**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="3d741-201">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-201">Yes</span></span>|<span data-ttu-id="3d741-202">**ntext**</span><span class="sxs-lookup"><span data-stu-id="3d741-202">**varchar(max)**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="3d741-203">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-203">Yes</span></span>|<span data-ttu-id="3d741-204">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="3d741-204">**varbinary(max)**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="3d741-205">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-205">Yes</span></span>|<span data-ttu-id="3d741-206">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="3d741-206">**varbinary(max)**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="3d741-207">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-207">Yes</span></span>|<span data-ttu-id="3d741-208">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="3d741-208">**varbinary(max)**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="3d741-209">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-209">Yes</span></span>|<span data-ttu-id="3d741-210">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="3d741-210">**varbinary(max)**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="3d741-211">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-211">Yes</span></span>|<span data-ttu-id="3d741-212">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="3d741-212">**nvarchar(max)**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="3d741-213">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-213">Yes</span></span>|<span data-ttu-id="3d741-214">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="3d741-214">**nvarchar(max)**</span></span>|  
|`SQLXML`|<span data-ttu-id="3d741-215">Sí</span><span class="sxs-lookup"><span data-stu-id="3d741-215">Yes</span></span>|<span data-ttu-id="3d741-216">**Xml**</span><span class="sxs-lookup"><span data-stu-id="3d741-216">**Xml**</span></span>|  
|`SQLUDT`|<span data-ttu-id="3d741-217">Es posible usar el</span><span class="sxs-lookup"><span data-stu-id="3d741-217">Either</span></span>|<span data-ttu-id="3d741-218">**Definido**</span><span class="sxs-lookup"><span data-stu-id="3d741-218">**Udt**</span></span>|  
  
## <a name="bcp_gettypename-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="3d741-219">bcp_gettypename admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="3d741-219">bcp_gettypename Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="3d741-220">Los valores de los parámetros de token para los tipos de fecha y hora se describen en la columna "Type in SQLNCLI. h" de la tabla en [cambios de copia masiva para los tipos de fecha y hora mejorados &#40;OLE DB y ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="3d741-220">The token parameter values for date/time types are described in the "Type in sqlncli.h" column of the table in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span> <span data-ttu-id="3d741-221">El valor devuelto está en la fila correspondiente de la columna " Tipo de almacenamiento de archivo".</span><span class="sxs-lookup"><span data-stu-id="3d741-221">The returned value is in the corresponding row of the "File storage type" column.</span></span>  
  
 <span data-ttu-id="3d741-222">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="3d741-222">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d741-223">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d741-223">See Also</span></span>  
 [<span data-ttu-id="3d741-224">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="3d741-224">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
