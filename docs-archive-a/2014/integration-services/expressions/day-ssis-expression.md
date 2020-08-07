---
title: DAY (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b7acac3f3949cbbd07adbe6382ea3d875f94cb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745914"
---
# <a name="day-ssis-expression"></a><span data-ttu-id="8747d-102">DAY (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="8747d-102">DAY (SSIS Expression)</span></span>
  <span data-ttu-id="8747d-103">Devuelve un entero que representa la parte del día de una fecha.</span><span class="sxs-lookup"><span data-stu-id="8747d-103">Returns an integer that represents the day datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8747d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8747d-104">Syntax</span></span>  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="8747d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8747d-105">Arguments</span></span>  
 <span data-ttu-id="8747d-106">*date*</span><span class="sxs-lookup"><span data-stu-id="8747d-106">*date*</span></span>  
 <span data-ttu-id="8747d-107">Expresión que devuelve una fecha válida o una cadena con formato de fecha.</span><span class="sxs-lookup"><span data-stu-id="8747d-107">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8747d-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="8747d-108">Result Types</span></span>  
 <span data-ttu-id="8747d-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="8747d-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8747d-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8747d-110">Remarks</span></span>  
 <span data-ttu-id="8747d-111">DAY devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="8747d-111">DAY returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="8747d-112">Un literal de tipo fecha debe convertirse explícitamente en uno de los tipos de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="8747d-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="8747d-113">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8747d-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8747d-114">La expresión no puede validarse cuando un literal de fecha se convierte explícitamente en uno de estos tipos de datos de fecha: DT_DBTIMESTAMPOFFSET y DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="8747d-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="8747d-115">Utilizar la función DAY es más sencillo pero equivalente a utilizar la función DATEPART("Day", date).</span><span class="sxs-lookup"><span data-stu-id="8747d-115">Using the DAY function is briefer but equivalent to using DATEPART("Day", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8747d-116">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="8747d-116">Expression Examples</span></span>  
 <span data-ttu-id="8747d-117">Este ejemplo devuelve el número del día de un literal de fecha.</span><span class="sxs-lookup"><span data-stu-id="8747d-117">This example returns the number of the day in a date literal.</span></span> <span data-ttu-id="8747d-118">Si la fecha tiene el formato "mm/dd/aaaa", este ejemplo devuelve 23.</span><span class="sxs-lookup"><span data-stu-id="8747d-118">If the date format is in "mm/dd/yyyy" format, this example returns 23.</span></span>  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="8747d-119">Este ejemplo devuelve el entero que representa el día en la columna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="8747d-119">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DAY(ModifiedDate)  
```  
  
 <span data-ttu-id="8747d-120">Este ejemplo devuelve el entero que representa el día de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="8747d-120">This example returns the integer that represents the day of the current date.</span></span>  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="8747d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8747d-121">See Also</span></span>  
 <span data-ttu-id="8747d-122">[DATEADD &#40;expresión de SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8747d-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="8747d-123">[DATEDIFF &#40;expresión de SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8747d-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="8747d-124">[DATEPART &#40;expresión de SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8747d-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="8747d-125">[MONTH &#40;expresión de SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8747d-125">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="8747d-126">[YEAR &#40;expresión de SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="8747d-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="8747d-127">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8747d-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
