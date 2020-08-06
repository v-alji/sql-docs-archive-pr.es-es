---
title: '- (Restar) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (subtract)'
- subtract operator (-)
ms.assetid: b48da086-37dd-460a-8a4b-912f52c9b158
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 79c47689baf47c33952c6b208ac622e9920d05fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746345"
---
# <a name="--subtract-ssis-expression"></a><span data-ttu-id="e7388-102">- (Restar) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="e7388-102">- (Subtract) (SSIS Expression)</span></span>
  <span data-ttu-id="e7388-103">Resta la segunda expresión numérica de la primera.</span><span class="sxs-lookup"><span data-stu-id="e7388-103">Subtracts the second numeric expression from the first one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7388-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7388-104">Syntax</span></span>  
  
```  
  
numeric_expression1 - numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7388-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e7388-105">Arguments</span></span>  
 <span data-ttu-id="e7388-106">*expresión_numérica1, expresión_numérica2*</span><span class="sxs-lookup"><span data-stu-id="e7388-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="e7388-107">Expresión válida de un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="e7388-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="e7388-108">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e7388-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e7388-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e7388-109">Result Types</span></span>  
 <span data-ttu-id="e7388-110">Dependen de los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="e7388-110">Determined by the data types of the two arguments.</span></span> <span data-ttu-id="e7388-111">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e7388-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7388-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7388-112">Remarks</span></span>  
 <span data-ttu-id="e7388-113">Incluya la expresión unaria menos entre paréntesis para asegurarse de que se evalúa en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="e7388-113">Enclose the minus unary expression in parenthesis to ensure that the expression is evaluated in the correct order</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7388-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7388-114">Remarks</span></span>  
 <span data-ttu-id="e7388-115">Si alguno de los operandos es NULL, el resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="e7388-115">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e7388-116">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="e7388-116">Expression Examples</span></span>  
 <span data-ttu-id="e7388-117">Este ejemplo resta literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="e7388-117">This example subtracts numeric literals.</span></span>  
  
```  
5 - 6.09  
```  
  
 <span data-ttu-id="e7388-118">Este ejemplo resta el valor de la columna **StandardCost** del valor de la columna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="e7388-118">This example subtracts the value in the **StandardCost** column from the value in the **ListPrice** column.</span></span>  
  
```  
ListPrice - StandardCost  
```  
  
 <span data-ttu-id="e7388-119">Este ejemplo resta un valor calculado de la columna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="e7388-119">This example subtracts a calculated value from the **ListPrice** column.</span></span> <span data-ttu-id="e7388-120">La variable **Discount%** debe escribirse entre corchetes porque el nombre incluye el carácter %.</span><span class="sxs-lookup"><span data-stu-id="e7388-120">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="e7388-121">Para más información, vea [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="e7388-121">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7388-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7388-122">See Also</span></span>  
 <span data-ttu-id="e7388-123">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="e7388-123">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="e7388-124">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e7388-124">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
