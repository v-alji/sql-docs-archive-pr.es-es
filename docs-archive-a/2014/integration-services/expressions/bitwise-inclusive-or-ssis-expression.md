---
title: '| (OR inclusivo bit a bit) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '| (bitwise inclusive OR)'
- bitwise inclusive OR (|)
ms.assetid: 4dce9eb2-3680-4adc-81a3-816ea52cef49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 73d64886b433ffe5b4e06dc4870bbca06b2a53dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674960"
---
# <a name="-bitwise-inclusive-or-ssis-expression"></a><span data-ttu-id="76777-102">| (OR inclusivo bit a bit) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="76777-102">| (Bitwise Inclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="76777-103">Lleva a cabo una operación OR bit a bit entre dos valores enteros.</span><span class="sxs-lookup"><span data-stu-id="76777-103">Performs a bitwise OR operation of two integer values.</span></span> <span data-ttu-id="76777-104">Compara cada bit del primer operando con el bit correspondiente del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="76777-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="76777-105">Si cualquiera de los bits es 1, el bit de resultado correspondiente se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="76777-105">If either bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="76777-106">De lo contrario, se establece en cero (0).</span><span class="sxs-lookup"><span data-stu-id="76777-106">Otherwise, the corresponding result bit is set to zero (0).</span></span>  
  
 <span data-ttu-id="76777-107">Ambas condiciones deben ser de tipo entero con signo o de tipo entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="76777-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76777-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76777-108">Syntax</span></span>  
  
```  
  
integer_expression1 | integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="76777-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="76777-109">Arguments</span></span>  
 <span data-ttu-id="76777-110">*integer_expression1 ,integer_ expression2*</span><span class="sxs-lookup"><span data-stu-id="76777-110">*integer_expression1 ,integer_ expression2*</span></span>  
 <span data-ttu-id="76777-111">Cualquier expresión válida de tipo entero con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="76777-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="76777-112">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="76777-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="76777-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="76777-113">Result Types</span></span>  
 <span data-ttu-id="76777-114">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="76777-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="76777-115">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="76777-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76777-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="76777-116">Remarks</span></span>  
 <span data-ttu-id="76777-117">Si alguna de las condiciones es NULL, el resultado de la expresión será NULL.</span><span class="sxs-lookup"><span data-stu-id="76777-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="76777-118">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="76777-118">Expression Examples</span></span>  
 <span data-ttu-id="76777-119">Este ejemplo realiza una operación OR inclusiva bit a bit entre las variables **NumberA** y **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="76777-119">This example performs a bitwise inclusive OR operation between the variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="76777-120">**NumberA** contiene 3 (00000011) y **NumberB** contiene 9 (00001001).</span><span class="sxs-lookup"><span data-stu-id="76777-120">**NumberA** contains 3 (00000011) and **NumberB** contains 9 (00001001).</span></span>  
  
```  
@NumberA | @NumberB  
```  
  
 <span data-ttu-id="76777-121">El resultado de evaluar la expresión es 11 (00001011).</span><span class="sxs-lookup"><span data-stu-id="76777-121">The expression evaluates to 11 (00001011).</span></span>  
  
 <span data-ttu-id="76777-122">00000011</span><span class="sxs-lookup"><span data-stu-id="76777-122">00000011</span></span>  
  
 <span data-ttu-id="76777-123">00001001</span><span class="sxs-lookup"><span data-stu-id="76777-123">00001001</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="76777-124">00001011</span><span class="sxs-lookup"><span data-stu-id="76777-124">00001011</span></span>  
  
 <span data-ttu-id="76777-125">Este ejemplo realiza una operación OR inclusiva bit a bit entre las columnas **ReorderPoint** y **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="76777-125">This example performs a bitwise inclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint | SafetyStockLevel  
```  
  
 <span data-ttu-id="76777-126">Si el valor de **ReorderPoint** es 10 y el de **SafetyStockLevel** es 8, el resultado de evaluar la expresión es 10 (00001010).</span><span class="sxs-lookup"><span data-stu-id="76777-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 10 (00001010).</span></span>  
  
 <span data-ttu-id="76777-127">00001010</span><span class="sxs-lookup"><span data-stu-id="76777-127">00001010</span></span>  
  
 <span data-ttu-id="76777-128">00001000</span><span class="sxs-lookup"><span data-stu-id="76777-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="76777-129">00001010</span><span class="sxs-lookup"><span data-stu-id="76777-129">00001010</span></span>  
  
 <span data-ttu-id="76777-130">Este ejemplo realiza una operación OR inclusiva bit a bit entre dos enteros.</span><span class="sxs-lookup"><span data-stu-id="76777-130">This example performs a bitwise inclusive OR operation between two integers.</span></span>  
  
```  
3 | 5   
```  
  
 <span data-ttu-id="76777-131">El resultado de evaluar la expresión es 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="76777-131">The expression evaluates to 7 (00000111).</span></span>  
  
 <span data-ttu-id="76777-132">00000011</span><span class="sxs-lookup"><span data-stu-id="76777-132">00000011</span></span>  
  
 <span data-ttu-id="76777-133">00000101</span><span class="sxs-lookup"><span data-stu-id="76777-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="76777-134">00000111</span><span class="sxs-lookup"><span data-stu-id="76777-134">00000111</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76777-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76777-135">See Also</span></span>  
 <span data-ttu-id="76777-136">[&#124;&#124; &#40;Operador OR lógico&#41; &#40;expresión de SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="76777-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="76777-137">[^ &#40;OR exclusivo bit a bit&#41; &#40;expresión de SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="76777-137">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="76777-138">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="76777-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="76777-139">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="76777-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
