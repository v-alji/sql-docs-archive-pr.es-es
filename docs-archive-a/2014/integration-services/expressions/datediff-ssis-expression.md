---
title: DATEDIFF (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DATEDIFF statement
- dates [Integration Services], DATEDIFF
ms.assetid: 449b327f-47c7-4709-8bc6-4ee9a35cc330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33edf2a152f70bb8c5bbd1f69cb87354e099b246
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745918"
---
# <a name="datediff-ssis-expression"></a><span data-ttu-id="928ee-102">DATEDIFF (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="928ee-102">DATEDIFF (SSIS Expression)</span></span>
  <span data-ttu-id="928ee-103">Devuelve el número de límites de fecha y hora entre dos fechas especificadas.</span><span class="sxs-lookup"><span data-stu-id="928ee-103">Returns the number of date and time boundaries crossed between two specified dates.</span></span> <span data-ttu-id="928ee-104">El parámetro *datepart* identifica los límites de fecha y hora que se van a comparar.</span><span class="sxs-lookup"><span data-stu-id="928ee-104">The *datepart* parameter identifies which date and time boundaries to compare.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="928ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="928ee-105">Syntax</span></span>  
  
```  
  
DATEDIFF(datepart, startdate, endate)  
```  
  
## <a name="arguments"></a><span data-ttu-id="928ee-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="928ee-106">Arguments</span></span>  
 <span data-ttu-id="928ee-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="928ee-107">*datepart*</span></span>  
 <span data-ttu-id="928ee-108">Parámetro que especifica la parte de la fecha que se va a comparar y para la que se devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="928ee-108">Is the parameter that specifies which part of the date to compare and return a value for.</span></span>  
  
 <span data-ttu-id="928ee-109">*startdate*</span><span class="sxs-lookup"><span data-stu-id="928ee-109">*startdate*</span></span>  
 <span data-ttu-id="928ee-110">Fecha de inicio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="928ee-110">Is the start date of the interval.</span></span>  
  
 <span data-ttu-id="928ee-111">*endate*</span><span class="sxs-lookup"><span data-stu-id="928ee-111">*endate*</span></span>  
 <span data-ttu-id="928ee-112">Fecha de finalización del intervalo.</span><span class="sxs-lookup"><span data-stu-id="928ee-112">Is the end date of the interval.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="928ee-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="928ee-113">Result Types</span></span>  
 <span data-ttu-id="928ee-114">DT_I4</span><span class="sxs-lookup"><span data-stu-id="928ee-114">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="928ee-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="928ee-115">Remarks</span></span>  
 <span data-ttu-id="928ee-116">En la tabla siguiente se incluyen las partes de fecha y las abreviaturas reconocidas por el evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="928ee-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span>  
  
|<span data-ttu-id="928ee-117">parte de fecha</span><span class="sxs-lookup"><span data-stu-id="928ee-117">Datepart</span></span>|<span data-ttu-id="928ee-118">Abreviaturas</span><span class="sxs-lookup"><span data-stu-id="928ee-118">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="928ee-119">Year</span><span class="sxs-lookup"><span data-stu-id="928ee-119">Year</span></span>|<span data-ttu-id="928ee-120">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="928ee-120">yy, yyyy</span></span>|  
|<span data-ttu-id="928ee-121">Trimestre</span><span class="sxs-lookup"><span data-stu-id="928ee-121">Quarter</span></span>|<span data-ttu-id="928ee-122">qq, q</span><span class="sxs-lookup"><span data-stu-id="928ee-122">qq, q</span></span>|  
|<span data-ttu-id="928ee-123">Month</span><span class="sxs-lookup"><span data-stu-id="928ee-123">Month</span></span>|<span data-ttu-id="928ee-124">mm, m</span><span class="sxs-lookup"><span data-stu-id="928ee-124">mm, m</span></span>|  
|<span data-ttu-id="928ee-125">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="928ee-125">Dayofyear</span></span>|<span data-ttu-id="928ee-126">dy, y</span><span class="sxs-lookup"><span data-stu-id="928ee-126">dy, y</span></span>|  
|<span data-ttu-id="928ee-127">Día</span><span class="sxs-lookup"><span data-stu-id="928ee-127">Day</span></span>|<span data-ttu-id="928ee-128">dd, d</span><span class="sxs-lookup"><span data-stu-id="928ee-128">dd, d</span></span>|  
|<span data-ttu-id="928ee-129">Semana</span><span class="sxs-lookup"><span data-stu-id="928ee-129">Week</span></span>|<span data-ttu-id="928ee-130">wk, ww</span><span class="sxs-lookup"><span data-stu-id="928ee-130">wk, ww</span></span>|  
|<span data-ttu-id="928ee-131">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="928ee-131">Weekday</span></span>|<span data-ttu-id="928ee-132">dw, w</span><span class="sxs-lookup"><span data-stu-id="928ee-132">dw, w</span></span>|  
|<span data-ttu-id="928ee-133">Hour</span><span class="sxs-lookup"><span data-stu-id="928ee-133">Hour</span></span>|<span data-ttu-id="928ee-134">Hh</span><span class="sxs-lookup"><span data-stu-id="928ee-134">Hh</span></span>|  
|<span data-ttu-id="928ee-135">Minute</span><span class="sxs-lookup"><span data-stu-id="928ee-135">Minute</span></span>|<span data-ttu-id="928ee-136">mi, n</span><span class="sxs-lookup"><span data-stu-id="928ee-136">mi, n</span></span>|  
|<span data-ttu-id="928ee-137">Segundo</span><span class="sxs-lookup"><span data-stu-id="928ee-137">Second</span></span>|<span data-ttu-id="928ee-138">ss, s</span><span class="sxs-lookup"><span data-stu-id="928ee-138">ss, s</span></span>|  
|<span data-ttu-id="928ee-139">Millisecond</span><span class="sxs-lookup"><span data-stu-id="928ee-139">Millisecond</span></span>|<span data-ttu-id="928ee-140">Ms</span><span class="sxs-lookup"><span data-stu-id="928ee-140">Ms</span></span>|  
  
 <span data-ttu-id="928ee-141">DATEDIFF devuelve un resultado NULL si alguno de los argumentos es NULL.</span><span class="sxs-lookup"><span data-stu-id="928ee-141">DATEDIFF returns a null result if any argument is null.</span></span>  
  
 <span data-ttu-id="928ee-142">Un literal de tipo fecha debe convertirse explícitamente en uno de los tipos de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="928ee-142">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="928ee-143">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="928ee-143">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="928ee-144">Se produce un error si una fecha no es válida, si la fecha o unidad de tiempo no es una cadena, si la fecha de inicio no es una fecha o si la fecha de finalización no es una fecha.</span><span class="sxs-lookup"><span data-stu-id="928ee-144">An error occurs if a date is not valid, if the date or time unit is not a string, if the start date is not a date, or if the end date is not a date.</span></span>  
  
 <span data-ttu-id="928ee-145">Si la fecha de finalización es anterior a la fecha de inicio, la función devuelve un número negativo.</span><span class="sxs-lookup"><span data-stu-id="928ee-145">If the end date is earlier than the start date, the function returns a negative number.</span></span> <span data-ttu-id="928ee-146">Si las fechas de inicio y de finalización coinciden o están dentro del mismo intervalo, la función devuelve cero.</span><span class="sxs-lookup"><span data-stu-id="928ee-146">If the start and end dates are equal or fall within the same interval, the function returns zero.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="928ee-147">Ejemplos de expresiones de SSIS</span><span class="sxs-lookup"><span data-stu-id="928ee-147">SSIS Expression Examples</span></span>  
 <span data-ttu-id="928ee-148">Este ejemplo calcula el número de días entre dos literales de fecha.</span><span class="sxs-lookup"><span data-stu-id="928ee-148">This example calculates the number of days between two date literals.</span></span> <span data-ttu-id="928ee-149">Si la fecha tiene el formato "mm/dd/aaaa", la función devuelve 7.</span><span class="sxs-lookup"><span data-stu-id="928ee-149">If the date is in "mm/dd/yyyy" format, the function returns 7.</span></span>  
  
```  
DATEDIFF("dd", (DT_DBTIMESTAMP)"8/1/2003", (DT_DBTIMESTAMP)"8/8/2003")  
```  
  
 <span data-ttu-id="928ee-150">Este ejemplo devuelve el número de meses entre un literal de fecha y la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="928ee-150">This example returns the number of months between a date literal and the current date.</span></span>  
  
```  
DATEDIFF("mm", (DT_DBTIMESTAMP)"8/1/2003",GETDATE())  
```  
  
 <span data-ttu-id="928ee-151">Este ejemplo devuelve el número de semanas entre la fecha de la columna **ModifiedDate** y la variable **YearEndDate** .</span><span class="sxs-lookup"><span data-stu-id="928ee-151">This example returns the number of weeks between the date in the **ModifiedDate** column and the **YearEndDate** variable.</span></span> <span data-ttu-id="928ee-152">Si **YearEndDate** tiene un `date` tipo de datos, no se requiere ninguna conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="928ee-152">If **YearEndDate** has a `date` data type, no explicit casting is required.</span></span>  
  
```  
DATEDIFF("Week", ModifiedDate,@YearEndDate)  
```  
  
## <a name="see-also"></a><span data-ttu-id="928ee-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="928ee-153">See Also</span></span>  
 <span data-ttu-id="928ee-154">[DATEADD &#40;expresión de SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="928ee-154">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="928ee-155">[DATEPART &#40;expresión de SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="928ee-155">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="928ee-156">[DAY &#40;expresión de SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="928ee-156">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="928ee-157">[MONTH &#40;expresión de SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="928ee-157">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="928ee-158">[YEAR &#40;expresión de SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="928ee-158">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="928ee-159">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="928ee-159">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
