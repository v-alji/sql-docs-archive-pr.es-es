---
title: LN (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LN function
- natural logarithm of expression [Integration Services]
ms.assetid: 55d7b657-b5fd-4753-9c81-54ed7575e720
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c06d6e246cfa51f8e84eb93ab7eb73eab40c392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674958"
---
# <a name="ln-ssis-expression"></a><span data-ttu-id="915a0-102">LN (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="915a0-102">LN (SSIS Expression)</span></span>
  <span data-ttu-id="915a0-103">Devuelve el logaritmo natural de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="915a0-103">Returns the natural logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="915a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="915a0-104">Syntax</span></span>  
  
```  
  
LN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="915a0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="915a0-105">Arguments</span></span>  
 <span data-ttu-id="915a0-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="915a0-106">*numeric_expression*</span></span>  
 <span data-ttu-id="915a0-107">Expresión numérica distinta de cero y no negativa válida.</span><span class="sxs-lookup"><span data-stu-id="915a0-107">Is a valid non-zero and non-negative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="915a0-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="915a0-108">Result Types</span></span>  
 <span data-ttu-id="915a0-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="915a0-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="915a0-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="915a0-110">Remarks</span></span>  
 <span data-ttu-id="915a0-111">La expresión numérica se convierte al tipo de datos DT_R8 antes de que se calcule el logaritmo.</span><span class="sxs-lookup"><span data-stu-id="915a0-111">The numeric expression is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="915a0-112">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="915a0-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="915a0-113">Si la evaluación de *numeric_expression* devuelve cero o un valor negativo, el resultado devuelto será NULL.</span><span class="sxs-lookup"><span data-stu-id="915a0-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="915a0-114">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="915a0-114">Expression Examples</span></span>  
 <span data-ttu-id="915a0-115">Este ejemplo usa un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="915a0-115">This example uses a numeric literal.</span></span> <span data-ttu-id="915a0-116">La función devuelve el valor 3,737766961828337.</span><span class="sxs-lookup"><span data-stu-id="915a0-116">The function returns the value 3.737766961828337.</span></span>  
  
```  
LN(42)  
```  
  
 <span data-ttu-id="915a0-117">En este ejemplo se utiliza la columna **Length**.</span><span class="sxs-lookup"><span data-stu-id="915a0-117">This example uses the column **Length**.</span></span> <span data-ttu-id="915a0-118">Si el valor de la columna is 53,99, la función devuelve 3,9887988442302.</span><span class="sxs-lookup"><span data-stu-id="915a0-118">If the column value is 53.99, the function returns 3.9887988442302.</span></span>  
  
```  
LN(Length)   
```  
  
 <span data-ttu-id="915a0-119">En este ejemplo se utiliza la variable **Length**.</span><span class="sxs-lookup"><span data-stu-id="915a0-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="915a0-120">La variable debe tener un tipo de datos numérico o la expresión debe incluir una conversión explícita a un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="915a0-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric data type.</span></span> <span data-ttu-id="915a0-121">Si el valor de **Length** es 234,567, la función devuelve 5.45774126708797.</span><span class="sxs-lookup"><span data-stu-id="915a0-121">If **Length** is 234.567, the function returns 5.45774126708797.</span></span>  
  
```  
LN(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="915a0-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="915a0-122">See Also</span></span>  
 <span data-ttu-id="915a0-123">[LOG &#40;expresión de SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="915a0-123">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="915a0-124">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="915a0-124">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
