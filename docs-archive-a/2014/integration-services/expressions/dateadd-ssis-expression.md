---
title: DATEADD (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEADD
- dates [Integration Services]
- DATEADD function
ms.assetid: fa5c37b1-2ddc-4857-8f8e-f6d5643b654f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9feb288318bdf9705928cb930f175f5c170c384e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748209"
---
# <a name="dateadd-ssis-expression"></a><span data-ttu-id="6030f-102">DATEADD (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="6030f-102">DATEADD (SSIS Expression)</span></span>
  <span data-ttu-id="6030f-103">Devuelve un nuevo valor de tipo DT_DBTIMESTAMP tras agregar un número que representa una fecha o un intervalo de tiempo a la parte de fecha especificada de una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="6030f-103">Returns a new DT_DBTIMESTAMP value after adding a number that represents a date or time interval to the specified datepart in a date.</span></span> <span data-ttu-id="6030f-104">La evaluación del parámetro number debe devolver un entero y la del parámetro date debe devolver una fecha válida.</span><span class="sxs-lookup"><span data-stu-id="6030f-104">The number parameter must evaluate to an integer, and the date parameter must evaluate to a valid date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6030f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6030f-105">Syntax</span></span>  
  
```  
  
DATEADD(datepart, number, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="6030f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6030f-106">Arguments</span></span>  
 <span data-ttu-id="6030f-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="6030f-107">*datepart*</span></span>  
 <span data-ttu-id="6030f-108">Parámetro que especifica a qué parte de la fecha se agregará un número.</span><span class="sxs-lookup"><span data-stu-id="6030f-108">Is the parameter that specifies which part of the date to add a number to.</span></span>  
  
 <span data-ttu-id="6030f-109">*número*</span><span class="sxs-lookup"><span data-stu-id="6030f-109">*number*</span></span>  
 <span data-ttu-id="6030f-110">Valor que se usa para incrementar *datepart*.</span><span class="sxs-lookup"><span data-stu-id="6030f-110">Is the value used to increment *datepart*.</span></span> <span data-ttu-id="6030f-111">El valor debe ser de tipo entero y debe conocerse al analizar la expresión.</span><span class="sxs-lookup"><span data-stu-id="6030f-111">The value must be an integer value that is known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="6030f-112">*date*</span><span class="sxs-lookup"><span data-stu-id="6030f-112">*date*</span></span>  
 <span data-ttu-id="6030f-113">Expresión que devuelve una fecha válida o una cadena con formato de fecha.</span><span class="sxs-lookup"><span data-stu-id="6030f-113">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6030f-114">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6030f-114">Result Types</span></span>  
 <span data-ttu-id="6030f-115">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6030f-115">DT_DBTIMESTAMP</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6030f-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6030f-116">Remarks</span></span>  
 <span data-ttu-id="6030f-117">En la tabla siguiente se incluyen las partes de fecha y las abreviaturas reconocidas por el evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="6030f-117">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="6030f-118">En los nombres de partes de fecha no se distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6030f-118">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="6030f-119">parte de fecha</span><span class="sxs-lookup"><span data-stu-id="6030f-119">Datepart</span></span>|<span data-ttu-id="6030f-120">Abreviaturas</span><span class="sxs-lookup"><span data-stu-id="6030f-120">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="6030f-121">Year</span><span class="sxs-lookup"><span data-stu-id="6030f-121">Year</span></span>|<span data-ttu-id="6030f-122">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="6030f-122">yy, yyyy</span></span>|  
|<span data-ttu-id="6030f-123">Trimestre</span><span class="sxs-lookup"><span data-stu-id="6030f-123">Quarter</span></span>|<span data-ttu-id="6030f-124">qq, q</span><span class="sxs-lookup"><span data-stu-id="6030f-124">qq, q</span></span>|  
|<span data-ttu-id="6030f-125">Month</span><span class="sxs-lookup"><span data-stu-id="6030f-125">Month</span></span>|<span data-ttu-id="6030f-126">mm, m</span><span class="sxs-lookup"><span data-stu-id="6030f-126">mm, m</span></span>|  
|<span data-ttu-id="6030f-127">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="6030f-127">Dayofyear</span></span>|<span data-ttu-id="6030f-128">dy, y</span><span class="sxs-lookup"><span data-stu-id="6030f-128">dy, y</span></span>|  
|<span data-ttu-id="6030f-129">Día</span><span class="sxs-lookup"><span data-stu-id="6030f-129">Day</span></span>|<span data-ttu-id="6030f-130">dd, d</span><span class="sxs-lookup"><span data-stu-id="6030f-130">dd, d</span></span>|  
|<span data-ttu-id="6030f-131">Semana</span><span class="sxs-lookup"><span data-stu-id="6030f-131">Week</span></span>|<span data-ttu-id="6030f-132">wk, ww</span><span class="sxs-lookup"><span data-stu-id="6030f-132">wk, ww</span></span>|  
|<span data-ttu-id="6030f-133">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="6030f-133">Weekday</span></span>|<span data-ttu-id="6030f-134">dw, w</span><span class="sxs-lookup"><span data-stu-id="6030f-134">dw, w</span></span>|  
|<span data-ttu-id="6030f-135">Hour</span><span class="sxs-lookup"><span data-stu-id="6030f-135">Hour</span></span>|<span data-ttu-id="6030f-136">Hh</span><span class="sxs-lookup"><span data-stu-id="6030f-136">Hh</span></span>|  
|<span data-ttu-id="6030f-137">Minute</span><span class="sxs-lookup"><span data-stu-id="6030f-137">Minute</span></span>|<span data-ttu-id="6030f-138">mi, n</span><span class="sxs-lookup"><span data-stu-id="6030f-138">mi, n</span></span>|  
|<span data-ttu-id="6030f-139">Segundo</span><span class="sxs-lookup"><span data-stu-id="6030f-139">Second</span></span>|<span data-ttu-id="6030f-140">ss, s</span><span class="sxs-lookup"><span data-stu-id="6030f-140">ss, s</span></span>|  
|<span data-ttu-id="6030f-141">Millisecond</span><span class="sxs-lookup"><span data-stu-id="6030f-141">Millisecond</span></span>|<span data-ttu-id="6030f-142">Ms</span><span class="sxs-lookup"><span data-stu-id="6030f-142">Ms</span></span>|  
  
 <span data-ttu-id="6030f-143">El argumento *number* debe estar disponible al analizar la expresión.</span><span class="sxs-lookup"><span data-stu-id="6030f-143">The *number* argument must be available when the expression is parsed.</span></span> <span data-ttu-id="6030f-144">Puede ser una constante o una variable.</span><span class="sxs-lookup"><span data-stu-id="6030f-144">The argument can be a constant or a variable.</span></span> <span data-ttu-id="6030f-145">No pueden usarse valores de columnas porque estos valores no se conocen en el momento de analizar la expresión.</span><span class="sxs-lookup"><span data-stu-id="6030f-145">You cannot use column values because the values are not known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="6030f-146">El argumento *datepart* debe entrecomillarse.</span><span class="sxs-lookup"><span data-stu-id="6030f-146">The *datepart* argument must be enclosed by quotation marks.</span></span>  
  
 <span data-ttu-id="6030f-147">Un literal de tipo fecha debe convertirse explícitamente en uno de los tipos de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="6030f-147">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="6030f-148">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="6030f-148">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="6030f-149">DATEADD devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="6030f-149">DATEADD returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="6030f-150">Se producen errores si la fecha no es válida, si la unidad de fecha o de hora no se indica mediante una cadena, o si el incremento no es un entero estático.</span><span class="sxs-lookup"><span data-stu-id="6030f-150">Errors occur if a date is invalid, if the date or time unit is not a string, or if the increment is not a static integer.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="6030f-151">Ejemplos de expresiones de SSIS</span><span class="sxs-lookup"><span data-stu-id="6030f-151">SSIS Expression Examples</span></span>  
 <span data-ttu-id="6030f-152">Este ejemplo agrega un mes a la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="6030f-152">This example adds one month to the current date.</span></span>  
  
```  
DATEADD("Month", 1,GETDATE())  
```  
  
 <span data-ttu-id="6030f-153">Este ejemplo agrega 21 días a las fechas de la columna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="6030f-153">This example adds 21 days to the dates in the **ModifiedDate** column.</span></span>  
  
```  
DATEADD("day", 21, ModifiedDate)  
```  
  
 <span data-ttu-id="6030f-154">Este ejemplo agrega 2 años a un literal de fecha.</span><span class="sxs-lookup"><span data-stu-id="6030f-154">This example adds 2 years to a literal date.</span></span>  
  
```  
DATEADD("yyyy", 2, (DT_DBTIMESTAMP)"8/6/2003")  
```  
  
## <a name="see-also"></a><span data-ttu-id="6030f-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6030f-155">See Also</span></span>  
 <span data-ttu-id="6030f-156">[DATEDIFF &#40;expresión de SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6030f-156">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="6030f-157">[DATEPART &#40;expresión de SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6030f-157">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="6030f-158">[DAY &#40;expresión de SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6030f-158">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="6030f-159">[MONTH &#40;expresión de SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6030f-159">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="6030f-160">[YEAR &#40;expresión de SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6030f-160">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="6030f-161">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6030f-161">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
