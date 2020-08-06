---
title: Dividir (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 5bde9223-872d-443e-8a27-57735e1d8f3d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4541cd4601047770d1bf361077b1c474219e8833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669756"
---
# <a name="divide-ssis-expression"></a><span data-ttu-id="7a1d8-102">Divide (SSIS Expression)</span><span class="sxs-lookup"><span data-stu-id="7a1d8-102">Divide (SSIS Expression)</span></span>
  <span data-ttu-id="7a1d8-103">Divide la primera expresión numérica por la segunda.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-103">Divides the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a1d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a1d8-104">Syntax</span></span>  
  
```  
  
dividend / divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a1d8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7a1d8-105">Arguments</span></span>  
 <span data-ttu-id="7a1d8-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="7a1d8-106">*dividend*</span></span>  
 <span data-ttu-id="7a1d8-107">Es la expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="7a1d8-108">*dividend* puede ser cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="7a1d8-109">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7a1d8-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="7a1d8-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="7a1d8-110">*divisor*</span></span>  
 <span data-ttu-id="7a1d8-111">Es la expresión numérica entre la que se va a dividir el dividendo.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="7a1d8-112">*divisor* puede ser cualquier expresión numérica excepto cero.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7a1d8-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="7a1d8-113">Result Types</span></span>  
 <span data-ttu-id="7a1d8-114">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="7a1d8-115">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7a1d8-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a1d8-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a1d8-116">Remarks</span></span>  
 <span data-ttu-id="7a1d8-117">Si alguno de los operandos es NULL, el resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-117">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="7a1d8-118">No se permite dividir por cero.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-118">Dividing by zero is not legal.</span></span> <span data-ttu-id="7a1d8-119">En función de cómo se evalúe la subexpresión *divisor* , se producirá uno de los siguientes errores:</span><span class="sxs-lookup"><span data-stu-id="7a1d8-119">Depending on how the *divisor* subexpression is evaluated, one of following errors occurs:</span></span>  
  
-   <span data-ttu-id="7a1d8-120">Si la subexpresión *divisor* que devuelve cero es una constante, el error aparecerá en tiempo de diseño y hará que no se valide la expresión.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-120">If the *divisor* subexpression that evaluates to zero is a constant, the error appears at design time, causing the expression to fail validation.</span></span>  
  
-   <span data-ttu-id="7a1d8-121">Si la subexpresión *divisor* que devuelve cero contiene variables pero no contiene columnas de entrada, el componente al que la expresión pertenece no superará la validación previa a la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-121">If the *divisor* subexpression that evaluates to zero contains variables, but no input columns, the component to which the expression belongs fails the pre-execution validation that occurs before the package runs.</span></span>  
  
-   <span data-ttu-id="7a1d8-122">Si la subexpresión *divisor* que se evalúa como cero contiene columnas de entrada, el error aparecerá en tiempo de ejecución y se controlará en función de las reglas de flujo de errores del componente de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-122">If the *divisor* subexpression that evaluates to zero contains input columns, the error appears at run time and is handled according to the error flow rules of the data flow component.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7a1d8-123">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="7a1d8-123">Expression Examples</span></span>  
 <span data-ttu-id="7a1d8-124">Este ejemplo divide dos literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="7a1d8-124">This example divides two numeric literals.</span></span>  
  
```  
25 / 5  
```  
  
 <span data-ttu-id="7a1d8-125">Este ejemplo divide los valores de la columna **ListPrice** por los valores de la columna **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="7a1d8-125">This example divides values in the **ListPrice** column by values in the **StandardCost** column.</span></span>  
  
```  
ListPrice / StandardCost  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a1d8-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a1d8-126">See Also</span></span>  
 <span data-ttu-id="7a1d8-127">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="7a1d8-127">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="7a1d8-128">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7a1d8-128">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
