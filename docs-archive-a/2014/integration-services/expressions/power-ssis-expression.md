---
title: POWER (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- POWER function
ms.assetid: db48ae65-bfa6-4db1-8d3c-d0d4f8a399bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1f5742f482ae52620ec11d95b84cb3d06199fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673775"
---
# <a name="power-ssis-expression"></a><span data-ttu-id="5626a-102">POWER (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="5626a-102">POWER (SSIS Expression)</span></span>
  <span data-ttu-id="5626a-103">Devuelve el resultado de elevar una expresión numérica a una determinada potencia.</span><span class="sxs-lookup"><span data-stu-id="5626a-103">Returns the result of raising a numeric expression to a power.</span></span> <span data-ttu-id="5626a-104">La evaluación del parámetro de potencia debe devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="5626a-104">The power parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5626a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5626a-105">Syntax</span></span>  
  
```  
  
POWER(numeric_expression,power)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5626a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5626a-106">Arguments</span></span>  
 <span data-ttu-id="5626a-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="5626a-107">*numeric_expression*</span></span>  
 <span data-ttu-id="5626a-108">Expresión numérica válida.</span><span class="sxs-lookup"><span data-stu-id="5626a-108">Is a valid numeric expression.</span></span>  
  
 <span data-ttu-id="5626a-109">*power*</span><span class="sxs-lookup"><span data-stu-id="5626a-109">*power*</span></span>  
 <span data-ttu-id="5626a-110">Expresión numérica válida.</span><span class="sxs-lookup"><span data-stu-id="5626a-110">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5626a-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="5626a-111">Result Types</span></span>  
 <span data-ttu-id="5626a-112">DT_R8</span><span class="sxs-lookup"><span data-stu-id="5626a-112">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5626a-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5626a-113">Remarks</span></span>  
 <span data-ttu-id="5626a-114">Los argumentos *numeric_expression* y *power* se convierten al tipo de datos DT_R8 antes de que se calcule la potencia.</span><span class="sxs-lookup"><span data-stu-id="5626a-114">The *numeric_expression* and *power* arguments are cast to the DT_R8 data type before the power is computed.</span></span> <span data-ttu-id="5626a-115">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5626a-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="5626a-116">Si el valor de *numeric_expression* da como resultado cero y el valor de *power* es negativo, el evaluador de expresiones devolverá un error y establecerá el resultado devuelto en NULL.</span><span class="sxs-lookup"><span data-stu-id="5626a-116">If *numeric_expression* evaluates to zero and *power* is negative, the expression evaluator returns an error and sets the return result to null.</span></span>  
  
 <span data-ttu-id="5626a-117">Si *numeric_expression* o *power* producen resultados indeterminados, el resultado devuelto será NULL.</span><span class="sxs-lookup"><span data-stu-id="5626a-117">If *numeric_expression* or *power* evaluate to indeterminate results, the return result is null.</span></span>  
  
 <span data-ttu-id="5626a-118">El argumento *power* puede ser una fracción.</span><span class="sxs-lookup"><span data-stu-id="5626a-118">The *power* argument can be a fraction.</span></span> <span data-ttu-id="5626a-119">Por ejemplo, puede utilizar el valor 0,5 como potencia.</span><span class="sxs-lookup"><span data-stu-id="5626a-119">For example, you can use the value 0.5 as the power.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5626a-120">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="5626a-120">Expression Examples</span></span>  
 <span data-ttu-id="5626a-121">Este ejemplo usa un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="5626a-121">This example uses a numeric literal.</span></span> <span data-ttu-id="5626a-122">La función eleva 4 a la potencia 3 y devuelve 64.</span><span class="sxs-lookup"><span data-stu-id="5626a-122">The function raises 4 to the power of 3 and returns 64.</span></span>  
  
```  
POWER(4,3)  
```  
  
 <span data-ttu-id="5626a-123">Este ejemplo utiliza la columna **Length** y la variable **DimensionCount** .</span><span class="sxs-lookup"><span data-stu-id="5626a-123">This example uses the **Length** column and the **DimensionCount** variable.</span></span> <span data-ttu-id="5626a-124">Si el valor de **Length** es 8 y el de **DimensionCount** es 2, el resultado devuelto es 64.</span><span class="sxs-lookup"><span data-stu-id="5626a-124">If **Length** is 8, and **DimensionCount** is 2, the return result is 64.</span></span>  
  
```  
POWER(Length, @DimensionCount)   
```  
  
## <a name="see-also"></a><span data-ttu-id="5626a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5626a-125">See Also</span></span>  
 [<span data-ttu-id="5626a-126">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5626a-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
