---
title: DATEPART (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aed7146c74c6738ba979f422bd65b7e1b539e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745916"
---
# <a name="datepart-ssis-expression"></a><span data-ttu-id="e4807-102">DATEPART (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="e4807-102">DATEPART (SSIS Expression)</span></span>
  <span data-ttu-id="e4807-103">Devuelve un entero que representa una parte de una fecha.</span><span class="sxs-lookup"><span data-stu-id="e4807-103">Returns an integer representing a datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4807-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4807-104">Syntax</span></span>  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4807-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e4807-105">Arguments</span></span>  
 <span data-ttu-id="e4807-106">*datepart*</span><span class="sxs-lookup"><span data-stu-id="e4807-106">*datepart*</span></span>  
 <span data-ttu-id="e4807-107">Parámetro que especifica para qué parte de la fecha se devuelve un valor nuevo.</span><span class="sxs-lookup"><span data-stu-id="e4807-107">Is the parameter that specifies for which part of the date to return a new value.</span></span>  
  
 <span data-ttu-id="e4807-108">*date*</span><span class="sxs-lookup"><span data-stu-id="e4807-108">*date*</span></span>  
 <span data-ttu-id="e4807-109">Expresión que devuelve una fecha válida o una cadena con formato de fecha.</span><span class="sxs-lookup"><span data-stu-id="e4807-109">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e4807-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e4807-110">Result Types</span></span>  
 <span data-ttu-id="e4807-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="e4807-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4807-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e4807-112">Remarks</span></span>  
 <span data-ttu-id="e4807-113">DATEPART devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="e4807-113">DATEPART returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="e4807-114">Un literal de tipo fecha debe convertirse explícitamente en uno de los tipos de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="e4807-114">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="e4807-115">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e4807-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="e4807-116">En la tabla siguiente se incluyen las partes de fecha y las abreviaturas reconocidas por el evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="e4807-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="e4807-117">En los nombres de partes de fecha no se distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e4807-117">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="e4807-118">parte de fecha</span><span class="sxs-lookup"><span data-stu-id="e4807-118">Datepart</span></span>|<span data-ttu-id="e4807-119">Abreviaturas</span><span class="sxs-lookup"><span data-stu-id="e4807-119">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="e4807-120">Year</span><span class="sxs-lookup"><span data-stu-id="e4807-120">Year</span></span>|<span data-ttu-id="e4807-121">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="e4807-121">yy, yyyy</span></span>|  
|<span data-ttu-id="e4807-122">Trimestre</span><span class="sxs-lookup"><span data-stu-id="e4807-122">Quarter</span></span>|<span data-ttu-id="e4807-123">qq, q</span><span class="sxs-lookup"><span data-stu-id="e4807-123">qq, q</span></span>|  
|<span data-ttu-id="e4807-124">Month</span><span class="sxs-lookup"><span data-stu-id="e4807-124">Month</span></span>|<span data-ttu-id="e4807-125">mm, m</span><span class="sxs-lookup"><span data-stu-id="e4807-125">mm, m</span></span>|  
|<span data-ttu-id="e4807-126">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="e4807-126">Dayofyear</span></span>|<span data-ttu-id="e4807-127">dy, y</span><span class="sxs-lookup"><span data-stu-id="e4807-127">dy, y</span></span>|  
|<span data-ttu-id="e4807-128">Día</span><span class="sxs-lookup"><span data-stu-id="e4807-128">Day</span></span>|<span data-ttu-id="e4807-129">dd, d</span><span class="sxs-lookup"><span data-stu-id="e4807-129">dd, d</span></span>|  
|<span data-ttu-id="e4807-130">Semana</span><span class="sxs-lookup"><span data-stu-id="e4807-130">Week</span></span>|<span data-ttu-id="e4807-131">wk, ww</span><span class="sxs-lookup"><span data-stu-id="e4807-131">wk, ww</span></span>|  
|<span data-ttu-id="e4807-132">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="e4807-132">Weekday</span></span>|<span data-ttu-id="e4807-133">dw</span><span class="sxs-lookup"><span data-stu-id="e4807-133">dw</span></span>|  
|<span data-ttu-id="e4807-134">Hour</span><span class="sxs-lookup"><span data-stu-id="e4807-134">Hour</span></span>|<span data-ttu-id="e4807-135">Hh</span><span class="sxs-lookup"><span data-stu-id="e4807-135">Hh</span></span>|  
|<span data-ttu-id="e4807-136">Minute</span><span class="sxs-lookup"><span data-stu-id="e4807-136">Minute</span></span>|<span data-ttu-id="e4807-137">mi, n</span><span class="sxs-lookup"><span data-stu-id="e4807-137">mi, n</span></span>|  
|<span data-ttu-id="e4807-138">Segundo</span><span class="sxs-lookup"><span data-stu-id="e4807-138">Second</span></span>|<span data-ttu-id="e4807-139">ss, s</span><span class="sxs-lookup"><span data-stu-id="e4807-139">ss, s</span></span>|  
|<span data-ttu-id="e4807-140">Millisecond</span><span class="sxs-lookup"><span data-stu-id="e4807-140">Millisecond</span></span>|<span data-ttu-id="e4807-141">Ms</span><span class="sxs-lookup"><span data-stu-id="e4807-141">Ms</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="e4807-142">Ejemplos de expresiones de SSIS</span><span class="sxs-lookup"><span data-stu-id="e4807-142">SSIS Expression Examples</span></span>  
 <span data-ttu-id="e4807-143">Este ejemplo devuelve el entero que representa el mes de un literal de fecha.</span><span class="sxs-lookup"><span data-stu-id="e4807-143">This example returns the integer that represents the month in a date literal.</span></span> <span data-ttu-id="e4807-144">Si la fecha tiene el formato mm/dd/aaaa, este ejemplo devuelve 11.</span><span class="sxs-lookup"><span data-stu-id="e4807-144">If the date is in mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 <span data-ttu-id="e4807-145">Este ejemplo devuelve el entero que representa el día en la columna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="e4807-145">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 <span data-ttu-id="e4807-146">Este ejemplo devuelve el entero que representa el año de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="e4807-146">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4807-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4807-147">See Also</span></span>  
 <span data-ttu-id="e4807-148">[DATEADD &#40;expresión de SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e4807-148">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="e4807-149">[DATEDIFF &#40;expresión de SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e4807-149">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="e4807-150">[DAY &#40;expresión de SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e4807-150">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="e4807-151">[MONTH &#40;expresión de SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e4807-151">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="e4807-152">[YEAR &#40;expresión de SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e4807-152">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e4807-153">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e4807-153">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
