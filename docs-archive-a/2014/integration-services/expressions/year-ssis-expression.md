---
title: YEAR (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], YEAR
- YEAR function
ms.assetid: 9d88dead-ace8-44b9-b8e2-916c1842e155
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181375d489fbf7abf0718386efacf4167ba555d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675494"
---
# <a name="year-ssis-expression"></a><span data-ttu-id="d6cf9-102">YEAR (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="d6cf9-102">YEAR (SSIS Expression)</span></span>
  <span data-ttu-id="d6cf9-103">Devuelve un entero que representa la parte del año de una fecha.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-103">Returns an integer that represents the year datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6cf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6cf9-104">Syntax</span></span>  
  
```  
  
YEAR(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6cf9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6cf9-105">Arguments</span></span>  
 <span data-ttu-id="d6cf9-106">*date*</span><span class="sxs-lookup"><span data-stu-id="d6cf9-106">*date*</span></span>  
 <span data-ttu-id="d6cf9-107">Fecha con cualquier formato de fecha.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d6cf9-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="d6cf9-108">Result Types</span></span>  
 <span data-ttu-id="d6cf9-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="d6cf9-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6cf9-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6cf9-110">Remarks</span></span>  
 <span data-ttu-id="d6cf9-111">YEAR devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-111">YEAR returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="d6cf9-112">Un literal de tipo fecha debe convertirse explícitamente en uno de los tipos de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="d6cf9-113">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d6cf9-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6cf9-114">La expresión no puede validarse cuando un literal de fecha se convierte explícitamente en uno de estos tipos de datos de fecha: DT_DBTIMESTAMPOFFSET y DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="d6cf9-115">Utilizar la función YEAR es más sencillo pero equivalente a utilizar la función DATEPART("Year", date).</span><span class="sxs-lookup"><span data-stu-id="d6cf9-115">Using the YEAR function is briefer but equivalent to using the DATEPART("Year", date) function.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="d6cf9-116">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="d6cf9-116">Expression Examples</span></span>  
 <span data-ttu-id="d6cf9-117">Este ejemplo devuelve el número del año de un literal de fecha.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-117">This example returns the number of the year in a date literal.</span></span> <span data-ttu-id="d6cf9-118">Si la fecha tiene el formato mm/dd/aaaa, este ejemplo devuelve "2002".</span><span class="sxs-lookup"><span data-stu-id="d6cf9-118">If the date is in mm/dd/yyyy format, this example returns "2002".</span></span>  
  
```  
YEAR((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="d6cf9-119">Este ejemplo devuelve el entero que representa el año en la columna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="d6cf9-119">This example returns the integer that represents the year in the **ModifiedDate** column.</span></span>  
  
```  
YEAR(ModifiedDate)  
```  
  
 <span data-ttu-id="d6cf9-120">Este ejemplo devuelve el entero que representa el año de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="d6cf9-120">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
YEAR(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6cf9-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6cf9-121">See Also</span></span>  
 <span data-ttu-id="d6cf9-122">[DATEADD &#40;expresión de SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf9-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="d6cf9-123">[DATEDIFF &#40;expresión de SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf9-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="d6cf9-124">[DATEPART &#40;expresión de SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf9-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="d6cf9-125">[DAY &#40;expresión de SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf9-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="d6cf9-126">[MONTH &#40;expresión de SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf9-126">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 [<span data-ttu-id="d6cf9-127">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6cf9-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
