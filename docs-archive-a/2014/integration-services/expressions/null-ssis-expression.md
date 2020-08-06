---
title: NULL (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14cd51b4e245ca6984a4c62eae2b9d5536ab1f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663024"
---
# <a name="null-ssis-expression"></a><span data-ttu-id="7ad05-102">NULL (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="7ad05-102">NULL (SSIS Expression)</span></span>
  <span data-ttu-id="7ad05-103">Devuelve un valor NULL asociado al tipo de datos solicitado.</span><span class="sxs-lookup"><span data-stu-id="7ad05-103">Returns a null value of a requested data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ad05-104">Syntax</span></span>  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7ad05-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7ad05-105">Arguments</span></span>  
 <span data-ttu-id="7ad05-106">*typespec*</span><span class="sxs-lookup"><span data-stu-id="7ad05-106">*typespec*</span></span>  
 <span data-ttu-id="7ad05-107">Tipo de datos válido.</span><span class="sxs-lookup"><span data-stu-id="7ad05-107">Is a valid data type.</span></span> <span data-ttu-id="7ad05-108">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7ad05-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7ad05-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="7ad05-109">Result Types</span></span>  
 <span data-ttu-id="7ad05-110">Cualquier tipo de datos válido con valor NULL.</span><span class="sxs-lookup"><span data-stu-id="7ad05-110">Any valid data type with a null value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ad05-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ad05-111">Remarks</span></span>  
 <span data-ttu-id="7ad05-112">NULL devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="7ad05-112">NULL returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="7ad05-113">Para solicitar un valor NULL para algunos tipos de datos es necesario utilizar parámetros.</span><span class="sxs-lookup"><span data-stu-id="7ad05-113">Parameters are required to request a null value for some data types.</span></span> <span data-ttu-id="7ad05-114">En la tabla siguiente se muestran estos tipos de datos y sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="7ad05-114">The following table lists these data types and their parameters.</span></span>  
  
|<span data-ttu-id="7ad05-115">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7ad05-115">Data type</span></span>|<span data-ttu-id="7ad05-116">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7ad05-116">Parameter</span></span>|<span data-ttu-id="7ad05-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ad05-117">Example</span></span>|  
|---------------|---------------|-------------|  
|<span data-ttu-id="7ad05-118">DT_STR</span><span class="sxs-lookup"><span data-stu-id="7ad05-118">DT_STR</span></span>|<span data-ttu-id="7ad05-119">*charcount*</span><span class="sxs-lookup"><span data-stu-id="7ad05-119">*charcount*</span></span><br /><br /> <span data-ttu-id="7ad05-120">*codepage*</span><span class="sxs-lookup"><span data-stu-id="7ad05-120">*codepage*</span></span>|<span data-ttu-id="7ad05-121">(DT_STR,30,1252) convierte 30 caracteres al tipo de datos DT_STR con la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="7ad05-121">(DT_STR,30,1252) casts 30 characters to the DT_STR data type using the 1252 code page.</span></span>|  
|<span data-ttu-id="7ad05-122">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7ad05-122">DT_WSTR</span></span>|<span data-ttu-id="7ad05-123">*charcount*</span><span class="sxs-lookup"><span data-stu-id="7ad05-123">*charcount*</span></span>|<span data-ttu-id="7ad05-124">(DT_WSTR,20) convierte 20 caracteres al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7ad05-124">(DT_WSTR,20) casts 20 characters to the DT_WSTR data type.</span></span>|  
|<span data-ttu-id="7ad05-125">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="7ad05-125">DT_BYTES</span></span>|<span data-ttu-id="7ad05-126">*bytecount*</span><span class="sxs-lookup"><span data-stu-id="7ad05-126">*bytecount*</span></span>|<span data-ttu-id="7ad05-127">(DT_BYTES,50) convierte 50 bytes al tipo de datos DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="7ad05-127">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|  
|<span data-ttu-id="7ad05-128">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="7ad05-128">DT_DECIMAL</span></span>|<span data-ttu-id="7ad05-129">*scale*</span><span class="sxs-lookup"><span data-stu-id="7ad05-129">*scale*</span></span>|<span data-ttu-id="7ad05-130">(DT_DECIMAL,2) convierte un valor numérico al tipo de datos DT_DECIMAL con una escala de 2.</span><span class="sxs-lookup"><span data-stu-id="7ad05-130">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|  
|<span data-ttu-id="7ad05-131">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="7ad05-131">DT_NUMERIC</span></span>|<span data-ttu-id="7ad05-132">*precisión*</span><span class="sxs-lookup"><span data-stu-id="7ad05-132">*precision*</span></span><br /><br /> <span data-ttu-id="7ad05-133">*scale*</span><span class="sxs-lookup"><span data-stu-id="7ad05-133">*scale*</span></span>|<span data-ttu-id="7ad05-134">(DT_NUMERIC,10,3) convierte un valor numérico al tipo de datos DT_NUMERIC con una precisión de 10 decimales y una escala de 3.</span><span class="sxs-lookup"><span data-stu-id="7ad05-134">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|  
|<span data-ttu-id="7ad05-135">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="7ad05-135">DT_TEXT</span></span>|<span data-ttu-id="7ad05-136">*codepage*</span><span class="sxs-lookup"><span data-stu-id="7ad05-136">*codepage*</span></span>|<span data-ttu-id="7ad05-137">(DT_TEXT,1252) convierte un valor al tipo de datos DT_TEXT con la página de códigos 1252.</span><span class="sxs-lookup"><span data-stu-id="7ad05-137">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="7ad05-138">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="7ad05-138">Expression Examples</span></span>  
 <span data-ttu-id="7ad05-139">Estos ejemplos devuelven el valor NULL asociado a los tipos de datos DT_STR, DT_DATE y DT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="7ad05-139">These examples return the null value of the data types: DT_STR, DT_DATE, and DT_BOOL.</span></span>  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ad05-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ad05-140">See Also</span></span>  
 <span data-ttu-id="7ad05-141">[ISNULL &#40;expresión de SSIS&#41;](null-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7ad05-141">[ISNULL &#40;SSIS Expression&#41;](null-ssis-expression.md) </span></span>  
 [<span data-ttu-id="7ad05-142">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7ad05-142">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
