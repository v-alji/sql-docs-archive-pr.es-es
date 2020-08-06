---
title: ^ (OR exclusivo bit a bit) (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- bitwise exclusive OR (^)
ms.assetid: 6ac53cab-29c4-4835-9f87-371b058b2f38
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d86c3d810e9e5572af93c97f82c2275db2c979b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674967"
---
# <a name="-bitwise-exclusive-or-ssis-expression"></a><span data-ttu-id="46f68-102">^ (OR exclusivo bit a bit) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="46f68-102">^ (Bitwise Exclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="46f68-103">Lleva a cabo una operación OR exclusiva bit a bit entre dos valores enteros.</span><span class="sxs-lookup"><span data-stu-id="46f68-103">Performs a bitwise exclusive OR operation of two integer values.</span></span> <span data-ttu-id="46f68-104">Compara cada bit del primer operando con el bit correspondiente del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="46f68-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="46f68-105">Si un bit es 0 y el otro bit es 1, el bit de resultado correspondiente se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="46f68-105">If one bit is 0 and the other bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="46f68-106">Si ambos bits son 0, o bien si ambos bits son 1, el bit de resultado correspondiente se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="46f68-106">If both bits are 0 or both bits are 1, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="46f68-107">Ambas condiciones deben ser de tipo entero con signo o de tipo entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="46f68-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f68-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46f68-108">Syntax</span></span>  
  
```  
  
integer_expression1 ^ integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="46f68-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="46f68-109">Arguments</span></span>  
 <span data-ttu-id="46f68-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="46f68-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="46f68-111">Cualquier expresión válida de tipo entero con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="46f68-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="46f68-112">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="46f68-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="46f68-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="46f68-113">Result Types</span></span>  
 <span data-ttu-id="46f68-114">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="46f68-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="46f68-115">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="46f68-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46f68-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46f68-116">Remarks</span></span>  
 <span data-ttu-id="46f68-117">Si alguna de las condiciones es NULL, el resultado de la expresión será NULL.</span><span class="sxs-lookup"><span data-stu-id="46f68-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="46f68-118">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="46f68-118">Expression Examples</span></span>  
 <span data-ttu-id="46f68-119">Este ejemplo realiza una operación OR exclusiva bit a bit entre las variables **NumberA** y **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="46f68-119">This example performs a bitwise exclusive OR operation between variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="46f68-120">**NumberA** contiene 3 (00000011) y **NumberB** contiene 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="46f68-120">**NumberA** contains 3 (00000011) and **NumberB** contains 7 (00000111).</span></span>  
  
```  
@NumberA ^ @NumberB  
```  
  
 <span data-ttu-id="46f68-121">El resultado de evaluar la expresión es 4 (00000100).</span><span class="sxs-lookup"><span data-stu-id="46f68-121">The expression evaluates to 4 (00000100).</span></span>  
  
 <span data-ttu-id="46f68-122">00000011</span><span class="sxs-lookup"><span data-stu-id="46f68-122">00000011</span></span>  
  
 <span data-ttu-id="46f68-123">00000111</span><span class="sxs-lookup"><span data-stu-id="46f68-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="46f68-124">00000100</span><span class="sxs-lookup"><span data-stu-id="46f68-124">00000100</span></span>  
  
 <span data-ttu-id="46f68-125">Este ejemplo realiza una operación OR exclusiva bit a bit entre las columnas **ReorderPoint** y **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="46f68-125">This example performs a bitwise exclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint ^ SafetyStockLevel  
```  
  
 <span data-ttu-id="46f68-126">Si el valor de **ReorderPoint** es 10 y el de **SafetyStockLevel** es 8, la expresión da como resultado 2 (00000010).</span><span class="sxs-lookup"><span data-stu-id="46f68-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 2 (00000010).</span></span>  
  
 <span data-ttu-id="46f68-127">00001010</span><span class="sxs-lookup"><span data-stu-id="46f68-127">00001010</span></span>  
  
 <span data-ttu-id="46f68-128">00001000</span><span class="sxs-lookup"><span data-stu-id="46f68-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="46f68-129">00000010</span><span class="sxs-lookup"><span data-stu-id="46f68-129">00000010</span></span>  
  
 <span data-ttu-id="46f68-130">Este ejemplo realiza una operación OR exclusiva bit a bit entre dos enteros.</span><span class="sxs-lookup"><span data-stu-id="46f68-130">This example performs a bitwise exclusive OR operation between two integers.</span></span>  
  
```  
3 ^ 5   
```  
  
 <span data-ttu-id="46f68-131">El resultado de evaluar la expresión es 6 (00000110).</span><span class="sxs-lookup"><span data-stu-id="46f68-131">The expression evaluates to 6 (00000110).</span></span>  
  
 <span data-ttu-id="46f68-132">00000011</span><span class="sxs-lookup"><span data-stu-id="46f68-132">00000011</span></span>  
  
 <span data-ttu-id="46f68-133">00000101</span><span class="sxs-lookup"><span data-stu-id="46f68-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="46f68-134">00000110</span><span class="sxs-lookup"><span data-stu-id="46f68-134">00000110</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f68-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46f68-135">See Also</span></span>  
 <span data-ttu-id="46f68-136">[&#124;&#124; &#40;Operador OR lógico&#41; &#40;expresión de SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="46f68-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="46f68-137">[&#124; &#40;OR inclusivo bit a bit&#41; &#40;expresión de SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="46f68-137">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="46f68-138">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="46f68-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="46f68-139">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="46f68-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
