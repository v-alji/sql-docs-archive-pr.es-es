---
title: '&amp; (AND bit a bit) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 06d2958e-66a5-44d8-8bc4-56209ebe1ff2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbf3c8ffcef079e25c82478947bc3b92a6b4be93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674966"
---
# <a name="amp-bitwise-and-ssis-expression"></a><span data-ttu-id="6bbd7-102">&amp; (AND bit a bit) (Expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="6bbd7-102">&amp; (Bitwise AND) (SSIS Expression)</span></span>
  <span data-ttu-id="6bbd7-103">Lleva a cabo una operación AND bit a bit entre dos valores enteros.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-103">Performs a bitwise AND operation of two integer values.</span></span> <span data-ttu-id="6bbd7-104">Compara cada bit del primer operando con el bit correspondiente del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="6bbd7-105">Si ambos bits son 1, el bit de resultado correspondiente se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-105">If both bits are 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="6bbd7-106">De lo contrario, se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-106">Otherwise, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="6bbd7-107">Ambas condiciones deben ser de tipo entero con signo o de tipo entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-107">Both conditions must be a signed integer type or both conditions must be an unsigned integer type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bbd7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6bbd7-108">Syntax</span></span>  
  
```  
  
integer_expression1 & integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6bbd7-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6bbd7-109">Arguments</span></span>  
 <span data-ttu-id="6bbd7-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="6bbd7-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="6bbd7-111">Cualquier expresión válida de tipo entero con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="6bbd7-112">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="6bbd7-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6bbd7-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6bbd7-113">Result Types</span></span>  
 <span data-ttu-id="6bbd7-114">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="6bbd7-115">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6bbd7-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bbd7-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6bbd7-116">Remarks</span></span>  
 <span data-ttu-id="6bbd7-117">Si alguna de las condiciones es NULL, el resultado de la expresión será NULL.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6bbd7-118">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="6bbd7-118">Expression Examples</span></span>  
 <span data-ttu-id="6bbd7-119">Este ejemplo realiza una operación AND bit a bit entre las columnas **NumberA** y **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-119">This example performs a bitwise AND operation between the columns **NumberA** and **NumberB**.</span></span> <span data-ttu-id="6bbd7-120">**NumberA** contiene 3 (0000011) y la columna **NumberB** contiene 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="6bbd7-120">**NumberA** contains 3 (0000011) and column **NumberB** contains 7 (00000111).</span></span>  
  
```  
NumberA & NumberB  
```  
  
 <span data-ttu-id="6bbd7-121">El resultado de evaluar la expresión es 3 (00000011).</span><span class="sxs-lookup"><span data-stu-id="6bbd7-121">The expression evaluates to 3 (00000011).</span></span>  
  
 <span data-ttu-id="6bbd7-122">00000011</span><span class="sxs-lookup"><span data-stu-id="6bbd7-122">00000011</span></span>  
  
 <span data-ttu-id="6bbd7-123">00000111</span><span class="sxs-lookup"><span data-stu-id="6bbd7-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="6bbd7-124">00000011</span><span class="sxs-lookup"><span data-stu-id="6bbd7-124">00000011</span></span>  
  
 <span data-ttu-id="6bbd7-125">Este ejemplo realiza una operación AND bit a bit entre las columnas **ReorderPoint** y **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="6bbd7-125">This example performs a bitwise AND operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint & SafetyStockLevel  
```  
  
 <span data-ttu-id="6bbd7-126">Si el valor de **ReorderPoint** es 10 y el valor de **SafetyStockLevel** es 8, la expresión da como resultado 8 (00001000).</span><span class="sxs-lookup"><span data-stu-id="6bbd7-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 8 (00001000).</span></span>  
  
 <span data-ttu-id="6bbd7-127">00001010</span><span class="sxs-lookup"><span data-stu-id="6bbd7-127">00001010</span></span>  
  
 <span data-ttu-id="6bbd7-128">00001000</span><span class="sxs-lookup"><span data-stu-id="6bbd7-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="6bbd7-129">00001000</span><span class="sxs-lookup"><span data-stu-id="6bbd7-129">00001000</span></span>  
  
 <span data-ttu-id="6bbd7-130">Este ejemplo realiza una operación AND bit a bit entre dos enteros.</span><span class="sxs-lookup"><span data-stu-id="6bbd7-130">This example performs a bitwise AND operation between two integers.</span></span>  
  
```  
3 & 5   
```  
  
 <span data-ttu-id="6bbd7-131">El resultado de evaluar la expresión es 1 (00000001).</span><span class="sxs-lookup"><span data-stu-id="6bbd7-131">The expression evaluates to 1(00000001).</span></span>  
  
 <span data-ttu-id="6bbd7-132">00000011</span><span class="sxs-lookup"><span data-stu-id="6bbd7-132">00000011</span></span>  
  
 <span data-ttu-id="6bbd7-133">00000101</span><span class="sxs-lookup"><span data-stu-id="6bbd7-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="6bbd7-134">00000001</span><span class="sxs-lookup"><span data-stu-id="6bbd7-134">00000001</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbd7-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bbd7-135">See Also</span></span>  
 <span data-ttu-id="6bbd7-136">[&& &#40;AND lógico&#41; &#40;expresión de SSIS&#41;](logical-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6bbd7-136">[&& &#40;Logical AND&#41; &#40;SSIS Expression&#41;](logical-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="6bbd7-137">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="6bbd7-137">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="6bbd7-138">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6bbd7-138">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
