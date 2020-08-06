---
title: ~ (NOT bit a bit) (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75745a0650c1744064f2a671659879e11464514e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674959"
---
# <a name="-bitwise-not-ssis-expression"></a><span data-ttu-id="e75a5-102">~ (Not bit a bit) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="e75a5-102">~ (Bitwise Not) (SSIS Expression)</span></span>
  <span data-ttu-id="e75a5-103">Realiza una negación bit a bit de un entero.</span><span class="sxs-lookup"><span data-stu-id="e75a5-103">Performs a bitwise negation of an integer.</span></span> <span data-ttu-id="e75a5-104">Este operador puede aplicarse a tipos de datos enteros con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="e75a5-104">This operator can be applied to signed and unsigned integer data types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75a5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e75a5-105">Syntax</span></span>  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e75a5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e75a5-106">Arguments</span></span>  
 <span data-ttu-id="e75a5-107">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="e75a5-107">*integer_expression*</span></span>  
 <span data-ttu-id="e75a5-108">Expresión válida de cualquier tipo de datos entero.</span><span class="sxs-lookup"><span data-stu-id="e75a5-108">Is any valid expression of an integer data type.</span></span> <span data-ttu-id="e75a5-109">*integer*_*expression* es un entero que se transforma en un número binario para la operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="e75a5-109">*integer*_*expression* is an integer that is transformed into a binary number for the bitwise operation.</span></span> <span data-ttu-id="e75a5-110">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e75a5-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e75a5-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e75a5-111">Result Types</span></span>  
 <span data-ttu-id="e75a5-112">Devuelve el tipo de datos de *integer_expression*.</span><span class="sxs-lookup"><span data-stu-id="e75a5-112">Returns the data type of *integer_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e75a5-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e75a5-113">Remarks</span></span>  
 <span data-ttu-id="e75a5-114">None</span><span class="sxs-lookup"><span data-stu-id="e75a5-114">None</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e75a5-115">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="e75a5-115">Expression Examples</span></span>  
 <span data-ttu-id="e75a5-116">Este ejemplo realiza una operación ~ (NOT) bit a bit en el número 170, cuya representación binaria es 0000 0000 1010 1010.</span><span class="sxs-lookup"><span data-stu-id="e75a5-116">This example performs a bitwise ~ (NOT) operation on the number 170 (0000 0000 1010 1010).</span></span> <span data-ttu-id="e75a5-117">Se trata de un entero con signo.</span><span class="sxs-lookup"><span data-stu-id="e75a5-117">The number is a signed integer.</span></span>  
  
```  
  
~ 170  
```  
  
 <span data-ttu-id="e75a5-118">El resultado de la operación es -170 (con representación binaria 1111111101010101).</span><span class="sxs-lookup"><span data-stu-id="e75a5-118">The expression evaluates to -170 (1111111101010101).</span></span>  
  
 <span data-ttu-id="e75a5-119">0000000010101010</span><span class="sxs-lookup"><span data-stu-id="e75a5-119">0000000010101010</span></span>  
  
 ---------------------\-  
  
 <span data-ttu-id="e75a5-120">1111111101010101</span><span class="sxs-lookup"><span data-stu-id="e75a5-120">1111111101010101</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75a5-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e75a5-121">See Also</span></span>  
 <span data-ttu-id="e75a5-122">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="e75a5-122">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="e75a5-123">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e75a5-123">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
