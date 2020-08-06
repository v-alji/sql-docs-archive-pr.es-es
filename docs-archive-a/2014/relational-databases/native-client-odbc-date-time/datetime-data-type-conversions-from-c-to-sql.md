---
title: Conversiones de C a SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC], C to SQL
ms.assetid: 7ac098db-9147-4883-8da9-a58ab24a0d31
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ec8856b9c516ff3693da2ebf1077289d414e589
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675328"
---
# <a name="conversions-from-c-to-sql"></a><span data-ttu-id="f9f67-102">Conversiones de C a SQL</span><span class="sxs-lookup"><span data-stu-id="f9f67-102">Conversions from C to SQL</span></span>
  <span data-ttu-id="f9f67-103">En este tema se enumeran los problemas que se deben tener en cuenta al convertir tipos de C a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="f9f67-103">This topic lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time types.</span></span>  
  
 <span data-ttu-id="f9f67-104">Las conversiones descritas en la tabla siguiente se aplican a conversiones realizadas en el cliente.</span><span class="sxs-lookup"><span data-stu-id="f9f67-104">The conversions described in the following table apply to conversions made on the client.</span></span> <span data-ttu-id="f9f67-105">En los casos en que el cliente especifica para un parámetro una precisión de fracciones de segundo diferente de la definida en el servidor, la conversión puede llegar a realizarse en el cliente pero el servidor devolverá un error cuando se llame a `SQLExecute` o `SQLExecuteDirect`.</span><span class="sxs-lookup"><span data-stu-id="f9f67-105">In cases where the client specifies fractional second precision for a parameter that differs from that defined on the server, the client conversion might succeed but the server will return an error when `SQLExecute` or `SQLExecuteDirect` is called.</span></span> <span data-ttu-id="f9f67-106">Concretamente, ODBC trata cualquier truncamiento de fracciones de segundo como un error, mientras que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza un redondeo; por ejemplo, el redondeo se produce cuando se pasa de `datetime2(6)` a `datetime2(2)`.</span><span class="sxs-lookup"><span data-stu-id="f9f67-106">In particular, ODBC treats any truncation of fractional seconds as an error, whereas the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] behavior is to round; for example, rounding occurs when you go from `datetime2(6)` to `datetime2(2)`.</span></span> <span data-ttu-id="f9f67-107">Los valores de las columnas datetime se redondean a la fracción 1/300 de segundo, mientras que para las columnas smalldatetime, el servidor establece los segundos en cero.</span><span class="sxs-lookup"><span data-stu-id="f9f67-107">Datetime column values are rounded to 1/300th of a second and smalldatetime columns have seconds set to zero by the server.</span></span>  
  
|||||||||  
|-|-|-|-|-|-|-|-|  
||<span data-ttu-id="f9f67-108">SQL_TYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="f9f67-108">SQL_TYPE_DATE</span></span>|<span data-ttu-id="f9f67-109">SQL_TYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="f9f67-109">SQL_TYPE_TIME</span></span>|<span data-ttu-id="f9f67-110">SQL_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="f9f67-110">SQL_SS_TIME2</span></span>|<span data-ttu-id="f9f67-111">SQL_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f9f67-111">SQL_TYPE_TIMESTAMP</span></span>|<span data-ttu-id="f9f67-112">SQL_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="f9f67-112">SQL_SS_TIMSTAMPOFFSET</span></span>|<span data-ttu-id="f9f67-113">SQL_CHAR</span><span class="sxs-lookup"><span data-stu-id="f9f67-113">SQL_CHAR</span></span>|<span data-ttu-id="f9f67-114">SQL_WCHAR</span><span class="sxs-lookup"><span data-stu-id="f9f67-114">SQL_WCHAR</span></span>|  
|<span data-ttu-id="f9f67-115">SQL_C_DATE</span><span class="sxs-lookup"><span data-stu-id="f9f67-115">SQL_C_DATE</span></span>|<span data-ttu-id="f9f67-116">1</span><span class="sxs-lookup"><span data-stu-id="f9f67-116">1</span></span>|-|-|<span data-ttu-id="f9f67-117">1,6</span><span class="sxs-lookup"><span data-stu-id="f9f67-117">1,6</span></span>|<span data-ttu-id="f9f67-118">1,5,6</span><span class="sxs-lookup"><span data-stu-id="f9f67-118">1,5,6</span></span>|<span data-ttu-id="f9f67-119">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-119">1,13</span></span>|<span data-ttu-id="f9f67-120">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-120">1,13</span></span>|  
|<span data-ttu-id="f9f67-121">SQL_C_TIME</span><span class="sxs-lookup"><span data-stu-id="f9f67-121">SQL_C_TIME</span></span>|-|<span data-ttu-id="f9f67-122">1</span><span class="sxs-lookup"><span data-stu-id="f9f67-122">1</span></span>|<span data-ttu-id="f9f67-123">1</span><span class="sxs-lookup"><span data-stu-id="f9f67-123">1</span></span>|<span data-ttu-id="f9f67-124">1,7</span><span class="sxs-lookup"><span data-stu-id="f9f67-124">1,7</span></span>|<span data-ttu-id="f9f67-125">1, 5, 7</span><span class="sxs-lookup"><span data-stu-id="f9f67-125">1,5,7</span></span>|<span data-ttu-id="f9f67-126">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-126">1,13</span></span>|<span data-ttu-id="f9f67-127">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-127">1,13</span></span>|  
|<span data-ttu-id="f9f67-128">SQL_C_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="f9f67-128">SQL_C_SS_TIME2</span></span>|-|<span data-ttu-id="f9f67-129">1,3</span><span class="sxs-lookup"><span data-stu-id="f9f67-129">1,3</span></span>|<span data-ttu-id="f9f67-130">1,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-130">1,10</span></span>|<span data-ttu-id="f9f67-131">1,7</span><span class="sxs-lookup"><span data-stu-id="f9f67-131">1,7</span></span>|<span data-ttu-id="f9f67-132">1, 5, 7</span><span class="sxs-lookup"><span data-stu-id="f9f67-132">1,5,7</span></span>|<span data-ttu-id="f9f67-133">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-133">1,13</span></span>|<span data-ttu-id="f9f67-134">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-134">1,13</span></span>|  
|<span data-ttu-id="f9f67-135">SQL_C_BINARY (SQL_SS_TIME2_STRUCT)</span><span class="sxs-lookup"><span data-stu-id="f9f67-135">SQL_C_BINARY(SQL_SS_TIME2_STRUCT)</span></span>|<span data-ttu-id="f9f67-136">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-136">N/A</span></span>|<span data-ttu-id="f9f67-137">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-137">N/A</span></span>|<span data-ttu-id="f9f67-138">1,10,11</span><span class="sxs-lookup"><span data-stu-id="f9f67-138">1,10,11</span></span>|<span data-ttu-id="f9f67-139">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-139">N/A</span></span>|<span data-ttu-id="f9f67-140">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-140">N/A</span></span>|<span data-ttu-id="f9f67-141">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-141">N/A</span></span>|<span data-ttu-id="f9f67-142">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-142">N/A</span></span>|  
|<span data-ttu-id="f9f67-143">SQL_C_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f9f67-143">SQL_C_TYPE_TIMESTAMP</span></span>|<span data-ttu-id="f9f67-144">1,2</span><span class="sxs-lookup"><span data-stu-id="f9f67-144">1,2</span></span>|<span data-ttu-id="f9f67-145">1,3,4</span><span class="sxs-lookup"><span data-stu-id="f9f67-145">1,3,4</span></span>|<span data-ttu-id="f9f67-146">1,4,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-146">1,4,10</span></span>|<span data-ttu-id="f9f67-147">1,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-147">1,10</span></span>|<span data-ttu-id="f9f67-148">1,5,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-148">1,5,10</span></span>|<span data-ttu-id="f9f67-149">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-149">1,13</span></span>|<span data-ttu-id="f9f67-150">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-150">1,13</span></span>|  
|<span data-ttu-id="f9f67-151">SQL_C_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="f9f67-151">SQL_C_SS_TIMESTAMPOFFSET</span></span>|<span data-ttu-id="f9f67-152">1,2,8</span><span class="sxs-lookup"><span data-stu-id="f9f67-152">1,2,8</span></span>|<span data-ttu-id="f9f67-153">1,3,4,8</span><span class="sxs-lookup"><span data-stu-id="f9f67-153">1,3,4,8</span></span>|<span data-ttu-id="f9f67-154">1,4,8,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-154">1,4,8,10</span></span>|<span data-ttu-id="f9f67-155">1,8,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-155">1,8,10</span></span>|<span data-ttu-id="f9f67-156">1,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-156">1,10</span></span>|<span data-ttu-id="f9f67-157">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-157">1,13</span></span>|<span data-ttu-id="f9f67-158">1,13</span><span class="sxs-lookup"><span data-stu-id="f9f67-158">1,13</span></span>|  
|<span data-ttu-id="f9f67-159">SQL_C_BINARY(SQL_SS_TIMESTAMPOFFSET_STRUCT)</span><span class="sxs-lookup"><span data-stu-id="f9f67-159">SQL_C_BINARY(SQL_SS_TIMESTAMPOFFSET_STRUCT)</span></span>|<span data-ttu-id="f9f67-160">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-160">N/A</span></span>|<span data-ttu-id="f9f67-161">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-161">N/A</span></span>|<span data-ttu-id="f9f67-162">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-162">N/A</span></span>|<span data-ttu-id="f9f67-163">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-163">N/A</span></span>|<span data-ttu-id="f9f67-164">1,10,11</span><span class="sxs-lookup"><span data-stu-id="f9f67-164">1,10,11</span></span>|<span data-ttu-id="f9f67-165">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-165">N/A</span></span>|<span data-ttu-id="f9f67-166">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-166">N/A</span></span>|  
|<span data-ttu-id="f9f67-167">SQL_C_CHAR/SQL_WCHAR (date)</span><span class="sxs-lookup"><span data-stu-id="f9f67-167">SQL_C_CHAR/SQL_WCHAR (date)</span></span>|<span data-ttu-id="f9f67-168">9</span><span class="sxs-lookup"><span data-stu-id="f9f67-168">9</span></span>|<span data-ttu-id="f9f67-169">9</span><span class="sxs-lookup"><span data-stu-id="f9f67-169">9</span></span>|<span data-ttu-id="f9f67-170">9</span><span class="sxs-lookup"><span data-stu-id="f9f67-170">9</span></span>|<span data-ttu-id="f9f67-171">9,6</span><span class="sxs-lookup"><span data-stu-id="f9f67-171">9,6</span></span>|<span data-ttu-id="f9f67-172">9,5,6</span><span class="sxs-lookup"><span data-stu-id="f9f67-172">9,5,6</span></span>|<span data-ttu-id="f9f67-173">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-173">N/A</span></span>|<span data-ttu-id="f9f67-174">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-174">N/A</span></span>|  
|<span data-ttu-id="f9f67-175">SQL_C_CHAR/SQL_WCHAR (time2)</span><span class="sxs-lookup"><span data-stu-id="f9f67-175">SQL_C_CHAR/SQL_WCHAR (time2)</span></span>|<span data-ttu-id="f9f67-176">9</span><span class="sxs-lookup"><span data-stu-id="f9f67-176">9</span></span>|<span data-ttu-id="f9f67-177">9, 3</span><span class="sxs-lookup"><span data-stu-id="f9f67-177">9,3</span></span>|<span data-ttu-id="f9f67-178">9,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-178">9,10</span></span>|<span data-ttu-id="f9f67-179">9,7,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-179">9,7,10</span></span>|<span data-ttu-id="f9f67-180">9,5,7,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-180">9,5,7,10</span></span>|<span data-ttu-id="f9f67-181">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-181">N/A</span></span>|<span data-ttu-id="f9f67-182">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-182">N/A</span></span>|  
|<span data-ttu-id="f9f67-183">SQL_C_CHAR/SQL_WCHAR (datetime)</span><span class="sxs-lookup"><span data-stu-id="f9f67-183">SQL_C_CHAR/SQL_WCHAR (datetime)</span></span>|<span data-ttu-id="f9f67-184">9,2</span><span class="sxs-lookup"><span data-stu-id="f9f67-184">9,2</span></span>|<span data-ttu-id="f9f67-185">9, 3, 4</span><span class="sxs-lookup"><span data-stu-id="f9f67-185">9,3,4</span></span>|<span data-ttu-id="f9f67-186">9,4,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-186">9,4,10</span></span>|<span data-ttu-id="f9f67-187">9,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-187">9,10</span></span>|<span data-ttu-id="f9f67-188">9,5,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-188">9,5,10</span></span>|<span data-ttu-id="f9f67-189">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-189">N/A</span></span>|<span data-ttu-id="f9f67-190">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-190">N/A</span></span>|  
|<span data-ttu-id="f9f67-191">SQL_C_CHAR/SQL_WCHAR (datetimeoffset)</span><span class="sxs-lookup"><span data-stu-id="f9f67-191">SQL_C_CHAR/SQL_WCHAR (datetimeoffset)</span></span>|<span data-ttu-id="f9f67-192">9,2,8</span><span class="sxs-lookup"><span data-stu-id="f9f67-192">9,2,8</span></span>|<span data-ttu-id="f9f67-193">9, 3, 4, 8</span><span class="sxs-lookup"><span data-stu-id="f9f67-193">9,3,4,8</span></span>|<span data-ttu-id="f9f67-194">9,4,8,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-194">9,4,8,10</span></span>|<span data-ttu-id="f9f67-195">9,8,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-195">9,8,10</span></span>|<span data-ttu-id="f9f67-196">9,10</span><span class="sxs-lookup"><span data-stu-id="f9f67-196">9,10</span></span>|<span data-ttu-id="f9f67-197">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-197">N/A</span></span>|<span data-ttu-id="f9f67-198">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-198">N/A</span></span>|  
|<span data-ttu-id="f9f67-199">SQL_C_BINARY(SQL_DATE_STRUCT)</span><span class="sxs-lookup"><span data-stu-id="f9f67-199">SQL_C_BINARY(SQL_DATE_STRUCT)</span></span>|<span data-ttu-id="f9f67-200">1,11</span><span class="sxs-lookup"><span data-stu-id="f9f67-200">1,11</span></span>|<span data-ttu-id="f9f67-201">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-201">N/A</span></span>|<span data-ttu-id="f9f67-202">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-202">N/A</span></span>|<span data-ttu-id="f9f67-203">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-203">N/A</span></span>|<span data-ttu-id="f9f67-204">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-204">N/A</span></span>|<span data-ttu-id="f9f67-205">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-205">N/A</span></span>|<span data-ttu-id="f9f67-206">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-206">N/A</span></span>|  
|<span data-ttu-id="f9f67-207">SQL_C_BINARY(SQL_TIME_STRUCT)</span><span class="sxs-lookup"><span data-stu-id="f9f67-207">SQL_C_BINARY(SQL_TIME_STRUCT)</span></span>|<span data-ttu-id="f9f67-208">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-208">N/A</span></span>|<span data-ttu-id="f9f67-209">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-209">N/A</span></span>|<span data-ttu-id="f9f67-210">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-210">N/A</span></span>|<span data-ttu-id="f9f67-211">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-211">N/A</span></span>|<span data-ttu-id="f9f67-212">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-212">N/A</span></span>|<span data-ttu-id="f9f67-213">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-213">N/A</span></span>|<span data-ttu-id="f9f67-214">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-214">N/A</span></span>|  
|<span data-ttu-id="f9f67-215">SQL_C_BINARY(SQL_TIMESTAMP_STRUCT)</span><span class="sxs-lookup"><span data-stu-id="f9f67-215">SQL_C_BINARY(SQL_TIMESTAMP_STRUCT)</span></span>|<span data-ttu-id="f9f67-216">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-216">N/A</span></span>|<span data-ttu-id="f9f67-217">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-217">N/A</span></span>|<span data-ttu-id="f9f67-218">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-218">N/A</span></span>|<span data-ttu-id="f9f67-219">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-219">N/A</span></span>|<span data-ttu-id="f9f67-220">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-220">N/A</span></span>|<span data-ttu-id="f9f67-221">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-221">N/A</span></span>|<span data-ttu-id="f9f67-222">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-222">N/A</span></span>|  
  
## <a name="key-to-symbols"></a><span data-ttu-id="f9f67-223">Clave de los símbolos</span><span class="sxs-lookup"><span data-stu-id="f9f67-223">Key to Symbols</span></span>  
  
|<span data-ttu-id="f9f67-224">Símbolo</span><span class="sxs-lookup"><span data-stu-id="f9f67-224">Symbol</span></span>|<span data-ttu-id="f9f67-225">Significado</span><span class="sxs-lookup"><span data-stu-id="f9f67-225">Meaning</span></span>|  
|------------|-------------|  
|-|<span data-ttu-id="f9f67-226">No se admite la conversión.</span><span class="sxs-lookup"><span data-stu-id="f9f67-226">No conversion is supported.</span></span> <span data-ttu-id="f9f67-227">Se genera un registro de diagnóstico con SQLSTATE 07006 y el mensaje "Infracción del atributo de tipo de datos restringido".</span><span class="sxs-lookup"><span data-stu-id="f9f67-227">A diagnostic record is generated with SQLSTATE 07006 and the message "Restricted data type attribute violation".</span></span>|  
|<span data-ttu-id="f9f67-228">1</span><span class="sxs-lookup"><span data-stu-id="f9f67-228">1</span></span>|<span data-ttu-id="f9f67-229">Si los datos proporcionados no son válidos, se genera un registro de diagnóstico con SQLSTATE 22007 y el mensaje "Formato de fecha y hora no válido".</span><span class="sxs-lookup"><span data-stu-id="f9f67-229">If the data supplied is not valid, a diagnostic record is generated with SQLSTATE 22007 and the message "Invalid datetime format".</span></span>|  
|<span data-ttu-id="f9f67-230">2</span><span class="sxs-lookup"><span data-stu-id="f9f67-230">2</span></span>|<span data-ttu-id="f9f67-231">Los campos de hora deben ser cero o, de lo contrario, se genera un registro de diagnóstico con SQLSTATE 22008 y el mensaje "Truncamiento fraccionario".</span><span class="sxs-lookup"><span data-stu-id="f9f67-231">Time fields must be zero or a diagnostic record is generated with SQLSTATE 22008 and the message "Fractional truncation".</span></span>|  
|<span data-ttu-id="f9f67-232">3</span><span class="sxs-lookup"><span data-stu-id="f9f67-232">3</span></span>|<span data-ttu-id="f9f67-233">Las fracciones de segundo deben ser cero o, de lo contrario, se genera un registro de diagnóstico con SQLSTATE 22008 y el mensaje "Truncamiento fraccionario".</span><span class="sxs-lookup"><span data-stu-id="f9f67-233">Fractional seconds must be zero or a diagnostic record is generated with SQLSTATE 22008 and the message "Fractional truncation".</span></span>|  
|<span data-ttu-id="f9f67-234">4</span><span class="sxs-lookup"><span data-stu-id="f9f67-234">4</span></span>|<span data-ttu-id="f9f67-235">Se omite el componente de fecha.</span><span class="sxs-lookup"><span data-stu-id="f9f67-235">The date component is ignored.</span></span>|  
|<span data-ttu-id="f9f67-236">5</span><span class="sxs-lookup"><span data-stu-id="f9f67-236">5</span></span>|<span data-ttu-id="f9f67-237">La zona horaria se establece en el valor de zona horaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="f9f67-237">The timezone is set to the client's timezone setting.</span></span>|  
|<span data-ttu-id="f9f67-238">6</span><span class="sxs-lookup"><span data-stu-id="f9f67-238">6</span></span>|<span data-ttu-id="f9f67-239">La hora se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="f9f67-239">The time is set to zero.</span></span>|  
|<span data-ttu-id="f9f67-240">7</span><span class="sxs-lookup"><span data-stu-id="f9f67-240">7</span></span>|<span data-ttu-id="f9f67-241">La fecha se establece en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="f9f67-241">The date is set to the current date.</span></span>|  
|<span data-ttu-id="f9f67-242">8</span><span class="sxs-lookup"><span data-stu-id="f9f67-242">8</span></span>|<span data-ttu-id="f9f67-243">La hora se convierte de la zona horaria del cliente a UTC.</span><span class="sxs-lookup"><span data-stu-id="f9f67-243">The time is converted from the client's timezone to UTC.</span></span> <span data-ttu-id="f9f67-244">Si se produce un error durante esta conversión, se genera un registro de diagnóstico con SQLSTATE 22008 y el mensaje "Desbordamiento del campo DateTime".</span><span class="sxs-lookup"><span data-stu-id="f9f67-244">If an error occurs during this conversion, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>|  
|<span data-ttu-id="f9f67-245">9</span><span class="sxs-lookup"><span data-stu-id="f9f67-245">9</span></span>|<span data-ttu-id="f9f67-246">La cadena se analiza y se convierte en un valor date, datetime, datetimeoffset o time, dependiendo del primer carácter de puntuación encontrado y de la presencia de otros componentes.</span><span class="sxs-lookup"><span data-stu-id="f9f67-246">The string is parsed and converted to a date, datetime, datetimeoffset, or time value, depending on the first punctuation character encountered and the presence of remaining components.</span></span> <span data-ttu-id="f9f67-247">A continuación, la cadena se convierte al tipo de destino, siguiendo las reglas de la tabla anterior para el tipo de origen detectado por este proceso.</span><span class="sxs-lookup"><span data-stu-id="f9f67-247">The string is then converted to the target type, following the rules in the preceding table for the source type discovered by this process.</span></span> <span data-ttu-id="f9f67-248">Si se detecta un error mientras se analizan los datos, se genera un registro de diagnóstico con SQLSTATE 22018 y el mensaje "Valor de carácter no válido para especificación cast".</span><span class="sxs-lookup"><span data-stu-id="f9f67-248">If an error is detected while parsing the data, a diagnostic record is generated with SQLSTATE 22018 and the message "Invalid character value for cast specification".</span></span> <span data-ttu-id="f9f67-249">Para los parámetros datetime y smalldatetime, si el año está fuera del intervalo admitido por estos tipos, se genera un registro de diagnóstico con SQLSTATE 22007 y el mensaje "Formato de fecha y hora no válido".</span><span class="sxs-lookup"><span data-stu-id="f9f67-249">For datetime and smalldatetime parameters, if the year is outside the range supported by these types, a diagnostic record is generated with SQLSTATE 22007 and the message "Invalid datetime format".</span></span><br /><br /> <span data-ttu-id="f9f67-250">Para datetimeoffset, el valor debe estar comprendido dentro del intervalo después de la conversión a UTC, aunque no se haya solicitado ninguna conversión a UTC.</span><span class="sxs-lookup"><span data-stu-id="f9f67-250">For datetimeoffset, the value must be within range after conversion to UTC, even if no conversion to UTC is requested.</span></span> <span data-ttu-id="f9f67-251">Esto se debe a que la secuencia de datos tabulares (TDS) y el servidor siempre normalizan la hora en valores datetimeoffset para UTC, de modo que el cliente tenga que comprobar que los componentes de hora están dentro del intervalo admitido después de la conversión a UTC.</span><span class="sxs-lookup"><span data-stu-id="f9f67-251">This is because TDS and the server always normalize the time in datetimeoffset values for UTC, so the client must verify that time components are within the range supported after conversion to UTC.</span></span> <span data-ttu-id="f9f67-252">Si el valor no está dentro del intervalo UTC admitido, se genera un registro de diagnóstico con SQLSTATE 22007 y el mensaje "Formato de fecha y hora no válido".</span><span class="sxs-lookup"><span data-stu-id="f9f67-252">If the value is not within the supported UTC range, a diagnostic record is generated with SQLSTATE 22007 and the message "Invalid datetime format".</span></span>|  
|<span data-ttu-id="f9f67-253">10</span><span class="sxs-lookup"><span data-stu-id="f9f67-253">10</span></span>|<span data-ttu-id="f9f67-254">Si se produce un truncamiento con pérdida de datos, se genera un registro de diagnóstico con SQLSTATE 22008 y el mensaje "Formato de hora no válido".</span><span class="sxs-lookup"><span data-stu-id="f9f67-254">If truncation with data loss occurs, a diagnostic record is generated with SQLSTATE 22008 and the message "Invalid time format".</span></span> <span data-ttu-id="f9f67-255">Este error también se produce si el valor está fuera del intervalo que puede representarse mediante el intervalo UTC utilizado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="f9f67-255">This error also occurs if the value falls outside the range that can be represented by the UTC range used by the server.</span></span>|  
|<span data-ttu-id="f9f67-256">11</span><span class="sxs-lookup"><span data-stu-id="f9f67-256">11</span></span>|<span data-ttu-id="f9f67-257">Si la longitud de bytes de los datos no coincide con el tamaño de la estructura requerida por el tipo SQL, se genera un registro de diagnóstico con SQLSTATE 22003 y el mensaje "Valor numérico fuera del intervalo".</span><span class="sxs-lookup"><span data-stu-id="f9f67-257">If the byte length of the data does not equal the size of the struct required by the SQL type, a diagnostic record is generated with SQLSTATE 22003 and the message "Numeric value out of range".</span></span>|  
|<span data-ttu-id="f9f67-258">12</span><span class="sxs-lookup"><span data-stu-id="f9f67-258">12</span></span>|<span data-ttu-id="f9f67-259">Si la longitud de bytes de los datos es 4 u 8, los datos se envían al servidor en formato datetime o smalldatetime TDS sin procesar.</span><span class="sxs-lookup"><span data-stu-id="f9f67-259">If the byte length of the data is 4 or 8, the data is sent to the server in raw TDS smalldatetime or datetime format.</span></span> <span data-ttu-id="f9f67-260">Si la longitud de bytes de los datos coincide exactamente con el tamaño de SQL_TIMESTAMP_STRUCT, los datos se convierten al formato TDS para datetime2.</span><span class="sxs-lookup"><span data-stu-id="f9f67-260">If the byte length of the data exactly matches the size of SQL_TIMESTAMP_STRUCT, the data is converted to the TDS format for datetime2.</span></span>|  
|<span data-ttu-id="f9f67-261">13</span><span class="sxs-lookup"><span data-stu-id="f9f67-261">13</span></span>|<span data-ttu-id="f9f67-262">Si se produce un truncamiento con pérdida de datos, se genera un registro de diagnóstico con SQLSTATE 22001 y el mensaje "Cadena truncada por la derecha".</span><span class="sxs-lookup"><span data-stu-id="f9f67-262">If truncation with data loss occurs, a diagnostic record is generated with SQLSTATE 22001 and the message "String data, right truncated".</span></span><br /><br /> <span data-ttu-id="f9f67-263">El número de dígitos de fracciones de segundo (la escala) se determina a partir del tamaño de la columna de destino según lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9f67-263">The number of fractional seconds digits (the scale) is determined from the destination column's size according to the following:</span></span><br /><br /> <span data-ttu-id="f9f67-264">**Tipo:** SQL_C_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f9f67-264">**Type:** SQL_C_TYPE_TIMESTAMP</span></span><br /><br /> <span data-ttu-id="f9f67-265">Escala supuesta</span><span class="sxs-lookup"><span data-stu-id="f9f67-265">Implied Scale</span></span><br /><br /> <span data-ttu-id="f9f67-266">0</span><span class="sxs-lookup"><span data-stu-id="f9f67-266">0</span></span><br /><br /> <span data-ttu-id="f9f67-267">19</span><span class="sxs-lookup"><span data-stu-id="f9f67-267">19</span></span><br /><br /> <span data-ttu-id="f9f67-268">Escala supuesta</span><span class="sxs-lookup"><span data-stu-id="f9f67-268">Implied Scale</span></span><br /><br /> <span data-ttu-id="f9f67-269">1.. 9</span><span class="sxs-lookup"><span data-stu-id="f9f67-269">1..9</span></span><br /><br /> <span data-ttu-id="f9f67-270">21..29</span><span class="sxs-lookup"><span data-stu-id="f9f67-270">21..29</span></span><br /><br /> <span data-ttu-id="f9f67-271">Sin embargo, para SQL_C_TYPE_TIMESTAMP, si las fracciones de segundo se pueden representar con tres dígitos sin perder datos y el tamaño de columna es 23 o superior, se generan exactamente tres dígitos de fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="f9f67-271">However, for SQL_C_TYPE_TIMESTAMP, if the fractional seconds can be represented with three digits without data loss and the column size is 23 or larger, then exactly three fractional seconds' digits are generated.</span></span> <span data-ttu-id="f9f67-272">Este comportamiento asegura la compatibilidad con versiones anteriores para aplicaciones desarrolladas utilizando controladores ODBC anteriores.</span><span class="sxs-lookup"><span data-stu-id="f9f67-272">This behavior ensures backwards compatibility for applications developed using older ODBC drivers.</span></span><br /><br /> <span data-ttu-id="f9f67-273">Si el tamaño de las columnas es mayor que el intervalo de la tabla, se presupone una escala de 9.</span><span class="sxs-lookup"><span data-stu-id="f9f67-273">For column sizes larger than the range in the table, a scale of 9 is implied.</span></span> <span data-ttu-id="f9f67-274">Esta conversión debe permitir hasta nueve dígitos de fracciones de segundo, el máximo permitido por ODBC.</span><span class="sxs-lookup"><span data-stu-id="f9f67-274">This conversion should allow for up to nine fractional seconds digits, the maximum allowed by ODBC.</span></span><br /><br /> <span data-ttu-id="f9f67-275">Un tamaño de columna igual a cero implica un tamaño ilimitado de los tipos de caracteres de longitud variable en ODBC (9 dígitos, a menos que sea aplicable la regla de 3 dígitos para SQL_C_TYPE_TIMESTAMP).</span><span class="sxs-lookup"><span data-stu-id="f9f67-275">A column size of zero implies unlimited size for variable length character types in ODBC (9 digits, unless the 3-digit rule for SQL_C_TYPE_TIMESTAMP applies).</span></span> <span data-ttu-id="f9f67-276">Especificar un tamaño de columna igual a cero con un tipo de caracteres de longitud fija es un error.</span><span class="sxs-lookup"><span data-stu-id="f9f67-276">Specifying a column size of zero with a fixed length character type is an error.</span></span>|  
|<span data-ttu-id="f9f67-277">N/D</span><span class="sxs-lookup"><span data-stu-id="f9f67-277">N/A</span></span>|<span data-ttu-id="f9f67-278">Se mantiene el comportamiento de las versiones actuales y anteriores de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9f67-278">Existing [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and earlier behavior is maintained.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9f67-279">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9f67-279">See Also</span></span>  
 [<span data-ttu-id="f9f67-280">Mejoras de fecha y hora &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f9f67-280">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  