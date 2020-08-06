---
title: ABS (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674973"
---
# <a name="abs-ssis-expression"></a><span data-ttu-id="99273-102">ABS (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="99273-102">ABS (SSIS Expression)</span></span>
  <span data-ttu-id="99273-103">Devuelve el valor absoluto (positivo) de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="99273-103">Returns the absolute, positive value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99273-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99273-104">Syntax</span></span>  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="99273-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="99273-105">Arguments</span></span>  
 <span data-ttu-id="99273-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="99273-106">*numeric_expression*</span></span>  
 <span data-ttu-id="99273-107">Expresión numérica con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="99273-107">Is a signed or unsigned numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="99273-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="99273-108">Result Types</span></span>  
 <span data-ttu-id="99273-109">El tipo de datos de la expresión numérica pasada a la función.</span><span class="sxs-lookup"><span data-stu-id="99273-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99273-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99273-110">Remarks</span></span>  
 <span data-ttu-id="99273-111">ABS devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="99273-111">ABS returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="99273-112">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="99273-112">Expression Examples</span></span>  
 <span data-ttu-id="99273-113">Estos ejemplos aplican la función ABS a un número positivo y a un número negativo.</span><span class="sxs-lookup"><span data-stu-id="99273-113">These examples apply the ABS function to a positive and a negative number.</span></span> <span data-ttu-id="99273-114">Ambos devuelven 1,23.</span><span class="sxs-lookup"><span data-stu-id="99273-114">Both return 1.23.</span></span>  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 <span data-ttu-id="99273-115">Este ejemplo aplica la función ABS a una expresión que resta valores de las variables **HighTemperature** y **LowTempature**.</span><span class="sxs-lookup"><span data-stu-id="99273-115">This example applies the ABS function to an expression that subtracts values in the variables **HighTemperature** and **LowTempature**.</span></span>  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a><span data-ttu-id="99273-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99273-116">See Also</span></span>  
 [<span data-ttu-id="99273-117">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="99273-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
