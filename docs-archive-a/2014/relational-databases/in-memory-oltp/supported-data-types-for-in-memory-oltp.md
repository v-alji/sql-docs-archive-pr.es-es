---
title: Tipos de datos admitidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a7dda500486c39a66f871d5934f957028fc51e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749882"
---
# <a name="supported-data-types"></a><span data-ttu-id="ec08f-102">Tipos de datos admitidos</span><span class="sxs-lookup"><span data-stu-id="ec08f-102">Supported Data Types</span></span>
  <span data-ttu-id="ec08f-103">Los siguientes tipos de datos se **admiten** en las tablas optimizadas para memoria y los procedimientos almacenados compilados de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="ec08f-103">The following data types are **supported** in memory-optimized tables and natively compiled stored procedures:</span></span>  
  
 <span data-ttu-id="ec08f-104">**Tipos de datos numéricos**</span><span class="sxs-lookup"><span data-stu-id="ec08f-104">**Numeric Data Types**</span></span>  
  
|<span data-ttu-id="ec08f-105">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec08f-105">Data type</span></span>|<span data-ttu-id="ec08f-106">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ec08f-106">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="ec08f-107">int</span><span class="sxs-lookup"><span data-stu-id="ec08f-107">int</span></span>|[<span data-ttu-id="ec08f-108">int, bigint, smallint y tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-108">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="ec08f-109">bigint</span><span class="sxs-lookup"><span data-stu-id="ec08f-109">bigint</span></span>|[<span data-ttu-id="ec08f-110">int, bigint, smallint y tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-110">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="ec08f-111">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="ec08f-111">smallint</span></span>|[<span data-ttu-id="ec08f-112">int, bigint, smallint y tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-112">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="ec08f-113">TINYINT</span><span class="sxs-lookup"><span data-stu-id="ec08f-113">tinyint</span></span>|[<span data-ttu-id="ec08f-114">int, bigint, smallint y tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-114">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="ec08f-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="ec08f-115">decimal</span></span>|[<span data-ttu-id="ec08f-116">decimal y numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-116">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="ec08f-117">NUMERIC</span><span class="sxs-lookup"><span data-stu-id="ec08f-117">numeric</span></span>|[<span data-ttu-id="ec08f-118">decimal y numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-118">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="ec08f-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="ec08f-119">float</span></span>|[<span data-ttu-id="ec08f-120">float y real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-120">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="ec08f-121">real</span><span class="sxs-lookup"><span data-stu-id="ec08f-121">real</span></span>|[<span data-ttu-id="ec08f-122">float y real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-122">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="ec08f-123">money</span><span class="sxs-lookup"><span data-stu-id="ec08f-123">money</span></span>|[<span data-ttu-id="ec08f-124">money y smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-124">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|<span data-ttu-id="ec08f-125">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="ec08f-125">smallmoney</span></span>|[<span data-ttu-id="ec08f-126">money y smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-126">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 <span data-ttu-id="ec08f-127">**Tipos de datos String**</span><span class="sxs-lookup"><span data-stu-id="ec08f-127">**String Data Types**</span></span>  
  
|<span data-ttu-id="ec08f-128">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec08f-128">Data type</span></span>|<span data-ttu-id="ec08f-129">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ec08f-129">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="ec08f-130">char(n)</span><span class="sxs-lookup"><span data-stu-id="ec08f-130">char(n)</span></span>|[<span data-ttu-id="ec08f-131">char y varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-131">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="ec08f-132">VARCHAR (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec08f-132">varchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="ec08f-133">char y varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-133">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="ec08f-134">nchar(n)</span><span class="sxs-lookup"><span data-stu-id="ec08f-134">nchar(n)</span></span>|[<span data-ttu-id="ec08f-135">nchar y nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-135">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="ec08f-136">nvarchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec08f-136">nvarchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="ec08f-137">nchar y nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-137">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="ec08f-138">sysname</span><span class="sxs-lookup"><span data-stu-id="ec08f-138">sysname</span></span>|[<span data-ttu-id="ec08f-139">nchar y nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-139">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <span data-ttu-id="ec08f-140"><sup>1</sup> la limitación es de 8060 bytes por fila en total, contando (n) en tipos de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="ec08f-140"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="ec08f-141">Para obtener información sobre las intercalaciones admitidas, consulte [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="ec08f-141">For information about supported collations, see [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span></span>  
  
 <span data-ttu-id="ec08f-142">**Tipos de datos de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="ec08f-142">**Date and Time Data Types**</span></span>  
  
|<span data-ttu-id="ec08f-143">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec08f-143">Data type</span></span>|<span data-ttu-id="ec08f-144">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ec08f-144">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="ec08f-145">date</span><span class="sxs-lookup"><span data-stu-id="ec08f-145">date</span></span>|[<span data-ttu-id="ec08f-146">date &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-146">date &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/date-transact-sql)|  
|<span data-ttu-id="ec08f-147">time</span><span class="sxs-lookup"><span data-stu-id="ec08f-147">time</span></span>|[<span data-ttu-id="ec08f-148">time &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-148">time &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/time-transact-sql)|  
|<span data-ttu-id="ec08f-149">datetime</span><span class="sxs-lookup"><span data-stu-id="ec08f-149">datetime</span></span>|[<span data-ttu-id="ec08f-150">datetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-150">datetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime-transact-sql)|  
|<span data-ttu-id="ec08f-151">datetime2</span><span class="sxs-lookup"><span data-stu-id="ec08f-151">datetime2</span></span>|[<span data-ttu-id="ec08f-152">datetime2 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-152">datetime2 &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime2-transact-sql)|  
|<span data-ttu-id="ec08f-153">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="ec08f-153">smalldatetime</span></span>|[<span data-ttu-id="ec08f-154">smalldatetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-154">smalldatetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 <span data-ttu-id="ec08f-155">**Tipos de datos binarios**</span><span class="sxs-lookup"><span data-stu-id="ec08f-155">**Binary Data Types**</span></span>  
  
|<span data-ttu-id="ec08f-156">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec08f-156">Data type</span></span>|<span data-ttu-id="ec08f-157">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ec08f-157">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="ec08f-158">bit</span><span class="sxs-lookup"><span data-stu-id="ec08f-158">bit</span></span>|[<span data-ttu-id="ec08f-159">bit &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-159">bit &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/bit-transact-sql)|  
|<span data-ttu-id="ec08f-160">binary(n)</span><span class="sxs-lookup"><span data-stu-id="ec08f-160">binary(n)</span></span>|[<span data-ttu-id="ec08f-161">binary y varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-161">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|<span data-ttu-id="ec08f-162">varbinary (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec08f-162">varbinary(n) <sup>1</sup></span></span>|[<span data-ttu-id="ec08f-163">binary y varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-163">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <span data-ttu-id="ec08f-164"><sup>1</sup> la limitación es de 8060 bytes por fila en total, contando (n) en tipos de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="ec08f-164"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="ec08f-165">**Otros tipos de datos**</span><span class="sxs-lookup"><span data-stu-id="ec08f-165">**Other data types**</span></span>  
  
|<span data-ttu-id="ec08f-166">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec08f-166">Data type</span></span>|<span data-ttu-id="ec08f-167">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ec08f-167">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="ec08f-168">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="ec08f-168">uniqueidentifier</span></span>|[<span data-ttu-id="ec08f-169">uniqueidentifier &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec08f-169">uniqueidentifier &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 <span data-ttu-id="ec08f-170">**Tipos de datos no compatibles**</span><span class="sxs-lookup"><span data-stu-id="ec08f-170">**Unsupported Data Types**</span></span>  
  
 <span data-ttu-id="ec08f-171">No se admiten los tipos de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec08f-171">The following data types are not supported:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ec08f-172">DATETIMEOFFSET</span><span class="sxs-lookup"><span data-stu-id="ec08f-172">DATETIMEOFFSET</span></span>|<span data-ttu-id="ec08f-173">GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="ec08f-173">GEOGRAPHY</span></span>|<span data-ttu-id="ec08f-174">GEOMETRY</span><span class="sxs-lookup"><span data-stu-id="ec08f-174">GEOMETRY</span></span>|  
|<span data-ttu-id="ec08f-175">HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="ec08f-175">HIERARCHYID</span></span>|<span data-ttu-id="ec08f-176">Objetos grandes (LOB).</span><span class="sxs-lookup"><span data-stu-id="ec08f-176">Large Objects (LOBs).</span></span> <span data-ttu-id="ec08f-177">Por ejemplo, varchar(max), nvarchar(max), varbinary(max), image, xml, text y ntext.</span><span class="sxs-lookup"><span data-stu-id="ec08f-177">For example, varchar(max), nvarchar(max), varbinary(max), image, xml, text, and ntext.</span></span>|<span data-ttu-id="ec08f-178">ROWVERSION</span><span class="sxs-lookup"><span data-stu-id="ec08f-178">ROWVERSION</span></span>|  
|<span data-ttu-id="ec08f-179">sql_variant</span><span class="sxs-lookup"><span data-stu-id="ec08f-179">sql_variant</span></span>|<span data-ttu-id="ec08f-180">Funciones CLR</span><span class="sxs-lookup"><span data-stu-id="ec08f-180">CLR functions</span></span>|<span data-ttu-id="ec08f-181">Tipos definidos por el usuario (UDT)</span><span class="sxs-lookup"><span data-stu-id="ec08f-181">User-defined types (UDTs)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec08f-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec08f-182">See Also</span></span>  
 <span data-ttu-id="ec08f-183">[Compatibilidad de Transact-SQL con OLTP en memoria](transact-sql-support-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="ec08f-183">[Transact-SQL Support for In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="ec08f-184">[Implementar columnas LOB en una tabla optimizada para memoria](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span><span class="sxs-lookup"><span data-stu-id="ec08f-184">[Implementing LOB Columns in a Memory-Optimized Table](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span></span>  
 [<span data-ttu-id="ec08f-185">Implementar SQL_VARIANT en una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="ec08f-185">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  
