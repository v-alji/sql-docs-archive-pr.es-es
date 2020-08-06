---
title: '* (Multiplicar) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '* (multiply operator)'
- multiply operator (*)
ms.assetid: d457f052-ffbb-4485-833f-f4bed4349b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16d8429a869b60be31a94244a2ce47d515770c6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672191"
---
# <a name="-multiply-ssis-expression"></a><span data-ttu-id="d6703-102">\* (Multiplicar) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="d6703-102">\* (Multiply) (SSIS Expression)</span></span>
  <span data-ttu-id="d6703-103">Multiplica dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="d6703-103">Multiplies two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6703-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6703-104">Syntax</span></span>  
  
```  
  
numeric_expression1 * numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6703-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6703-105">Arguments</span></span>  
 <span data-ttu-id="d6703-106">*expresión_numérica1, expresión_numérica2*</span><span class="sxs-lookup"><span data-stu-id="d6703-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="d6703-107">Expresión válida de un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="d6703-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="d6703-108">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d6703-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d6703-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="d6703-109">Result Types</span></span>  
 <span data-ttu-id="d6703-110">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="d6703-110">Determined by data types of the two arguments.</span></span> <span data-ttu-id="d6703-111">Para más información, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d6703-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6703-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6703-112">Remarks</span></span>  
 <span data-ttu-id="d6703-113">Si alguno de los operandos es NULL, el resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="d6703-113">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="d6703-114">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="d6703-114">Expression Examples</span></span>  
 <span data-ttu-id="d6703-115">Este ejemplo multiplica literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="d6703-115">This example multiplies numeric literals.</span></span>  
  
```  
5 * 6.09  
```  
  
 <span data-ttu-id="d6703-116">Este ejemplo multiplica los valores de la columna **ListPrice** por 10 %.</span><span class="sxs-lookup"><span data-stu-id="d6703-116">This example multiplies values in the **ListPrice** column by 10 percent.</span></span>  
  
```  
ListPrice * .10  
```  
  
 <span data-ttu-id="d6703-117">Este ejemplo resta el resultado de una expresión de la columna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="d6703-117">This example subtracts the result of an expression from the **ListPrice** column.</span></span> <span data-ttu-id="d6703-118">La variable **Discount%** debe escribirse entre corchetes porque el nombre incluye el carácter %.</span><span class="sxs-lookup"><span data-stu-id="d6703-118">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="d6703-119">Para más información, vea [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="d6703-119">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6703-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6703-120">See Also</span></span>  
 <span data-ttu-id="d6703-121">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="d6703-121">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="d6703-122">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6703-122">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
