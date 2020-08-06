---
title: MONTH (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1f56906b4d25f2ba01f54fbdbc404d2c9ae4704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672192"
---
# <a name="month-ssis-expression"></a><span data-ttu-id="c5381-102">MONTH (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="c5381-102">MONTH (SSIS Expression)</span></span>
  <span data-ttu-id="c5381-103">Devuelve un entero que representa la parte del mes de una fecha.</span><span class="sxs-lookup"><span data-stu-id="c5381-103">Returns an integer that represents the month datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5381-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5381-104">Syntax</span></span>  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5381-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c5381-105">Arguments</span></span>  
 <span data-ttu-id="c5381-106">*date*</span><span class="sxs-lookup"><span data-stu-id="c5381-106">*date*</span></span>  
 <span data-ttu-id="c5381-107">Fecha con cualquier formato de fecha.</span><span class="sxs-lookup"><span data-stu-id="c5381-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c5381-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c5381-108">Result Types</span></span>  
 <span data-ttu-id="c5381-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="c5381-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5381-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5381-110">Remarks</span></span>  
 <span data-ttu-id="c5381-111">MONTH devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="c5381-111">MONTH returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="c5381-112">Un literal de tipo fecha debe convertirse explícitamente en uno de los tipos de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="c5381-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="c5381-113">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c5381-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5381-114">La expresión no puede validarse cuando un literal de fecha se convierte explícitamente en uno de estos tipos de datos de fecha: DT_DBTIMESTAMPOFFSET y DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="c5381-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="c5381-115">Utilizar la función MONTH es más sencillo pero equivalente a utilizar la función DATEPART("Month", date).</span><span class="sxs-lookup"><span data-stu-id="c5381-115">Using the MONTH function is briefer but equivalent to using DATEPART("Month", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c5381-116">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="c5381-116">Expression Examples</span></span>  
 <span data-ttu-id="c5381-117">Este ejemplo devuelve el número del mes de un literal de fecha.</span><span class="sxs-lookup"><span data-stu-id="c5381-117">This example returns the number of the month in a date literal.</span></span> <span data-ttu-id="c5381-118">Si la fecha tiene el formato "mm/dd/aaaa", este ejemplo devuelve 11.</span><span class="sxs-lookup"><span data-stu-id="c5381-118">If the date is in "mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="c5381-119">Este ejemplo devuelve el entero que representa el mes en la columna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="c5381-119">This example returns the integer that represents the month in the **ModifiedDate** column.</span></span>  
  
```  
MONTH(ModifiedDate)  
```  
  
 <span data-ttu-id="c5381-120">Este ejemplo devuelve el entero que representa el mes de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="c5381-120">This example returns the integer that represents the month of the current date.</span></span>  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5381-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5381-121">See Also</span></span>  
 <span data-ttu-id="c5381-122">[DATEADD &#40;expresión de SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5381-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="c5381-123">[DATEDIFF &#40;expresión de SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5381-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="c5381-124">[DATEPART &#40;expresión de SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5381-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="c5381-125">[DAY &#40;expresión de SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5381-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="c5381-126">[YEAR &#40;expresión de SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5381-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c5381-127">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c5381-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
