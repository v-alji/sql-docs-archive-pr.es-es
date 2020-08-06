---
title: (Módulo) (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e23152fca9c9f2c7c3ac11490a56b03d1a1f9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672194"
---
# <a name="modulo-ssis-expression"></a><span data-ttu-id="cdcdb-102">(Módulo) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="cdcdb-102">(Modulo) (SSIS Expression)</span></span>
  <span data-ttu-id="cdcdb-103">Proporciona el resto entero después de dividir la primera expresión numérica por la segunda.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-103">Provides the integer remainder after dividing the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdcdb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdcdb-104">Syntax</span></span>  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cdcdb-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cdcdb-105">Arguments</span></span>  
 <span data-ttu-id="cdcdb-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="cdcdb-106">*dividend*</span></span>  
 <span data-ttu-id="cdcdb-107">Es la expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="cdcdb-108">*dividend* puede ser cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="cdcdb-109">Para más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="cdcdb-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md)</span></span>  
  
 <span data-ttu-id="cdcdb-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="cdcdb-110">*divisor*</span></span>  
 <span data-ttu-id="cdcdb-111">Es la expresión numérica entre la que se va a dividir el dividendo.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="cdcdb-112">*divisor* puede ser cualquier expresión numérica excepto cero.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cdcdb-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="cdcdb-113">Result Types</span></span>  
 <span data-ttu-id="cdcdb-114">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="cdcdb-115">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cdcdb-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdcdb-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cdcdb-116">Remarks</span></span>  
 <span data-ttu-id="cdcdb-117">La evaluación de ambas expresiones debe devolver tipos de datos enteros, con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-117">Both expressions must evaluate to signed or unsigned integer data types.</span></span>  
  
 <span data-ttu-id="cdcdb-118">Si alguno de los operandos es NULL, el resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-118">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="cdcdb-119">No se puede usar 0 como divisor.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-119">Modulo zero is not legal.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="cdcdb-120">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="cdcdb-120">Expression Examples</span></span>  
 <span data-ttu-id="cdcdb-121">Este ejemplo calcula el módulo a partir de dos literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-121">This example computes the modulus from two numeric literals.</span></span> <span data-ttu-id="cdcdb-122">El resultado es 3.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-122">The result is 3.</span></span>  
  
```  
42 % 13  
```  
  
 <span data-ttu-id="cdcdb-123">Este ejemplo calcula el módulo de la columna **SalesQuota** y un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-123">This example computes the modulus from the **SalesQuota** column and a numeric literal.</span></span>  
  
```  
SalesQuota % 12  
```  
  
 <span data-ttu-id="cdcdb-124">Este ejemplo calcula el módulo de dos variables numéricas: **Sales$** y **Month**.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-124">This example computes the modulus from two numeric variables **Sales$** and **Month**.</span></span> <span data-ttu-id="cdcdb-125">La variable **Sales$** debe escribirse entre corchetes, ya que su nombre contiene el carácter $.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-125">The variable **Sales$** must be enclosed in brackets because the name includes the $ character.</span></span> <span data-ttu-id="cdcdb-126">Para más información, vea [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="cdcdb-126">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
@[Sales$] % @Month  
```  
  
 <span data-ttu-id="cdcdb-127">Este ejemplo usa el operador módulo para determinar si el valor de la variable **Value** es par o impar, y utiliza el operador condicional para devolver una cadena que describe el resultado.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-127">This example uses the modulo operator to determine if the value of the **Value** variable is even or odd, and uses the conditional operator to return a string that describes the result.</span></span> <span data-ttu-id="cdcdb-128">Para más información, vea [? : &#40;Condicional&#41; &#40;expresión de SSIS&#41;](conditional-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="cdcdb-128">For more information, see [? : &#40;Conditional&#41; &#40;SSIS Expression&#41;](conditional-ssis-expression.md).</span></span>  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdcdb-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cdcdb-129">See Also</span></span>  
 <span data-ttu-id="cdcdb-130">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="cdcdb-130">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="cdcdb-131">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="cdcdb-131">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
