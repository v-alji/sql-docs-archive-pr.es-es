---
title: () (Paréntesis) (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- () (parentheses operator)
- evaluation order [Integration Services]
- parentheses operator ()
ms.assetid: 931e10eb-1707-4121-b2f1-43565561119f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e390e10e485bd9cc22480300b6a9c33098bda8f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749382"
---
# <a name="-parentheses-ssis-expression"></a><span data-ttu-id="0b63b-102">() (Paréntesis) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="0b63b-102">() (Parentheses) (SSIS Expression)</span></span>
  <span data-ttu-id="0b63b-103">Identifica el orden de evaluación de las expresiones.</span><span class="sxs-lookup"><span data-stu-id="0b63b-103">Identifies the evaluation order of expressions.</span></span> <span data-ttu-id="0b63b-104">Las expresiones escritas entre paréntesis tienen la prioridad de evaluación más alta.</span><span class="sxs-lookup"><span data-stu-id="0b63b-104">Expressions enclosed in parentheses have the highest evaluation precedence.</span></span> <span data-ttu-id="0b63b-105">Las expresiones anidadas escritas entre paréntesis se evalúan desde dentro hacia fuera.</span><span class="sxs-lookup"><span data-stu-id="0b63b-105">Nested expressions enclosed in parentheses are evaluated in inner-to-outer order.</span></span>  
  
 <span data-ttu-id="0b63b-106">Los paréntesis también se usan para hacer que resulte más fácil comprender las expresiones complejas.</span><span class="sxs-lookup"><span data-stu-id="0b63b-106">Parentheses are also used to make complex expressions easier to understand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b63b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b63b-107">Syntax</span></span>  
  
```  
  
(expression)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b63b-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0b63b-108">Arguments</span></span>  
 <span data-ttu-id="0b63b-109">*expression*</span><span class="sxs-lookup"><span data-stu-id="0b63b-109">*expression*</span></span>  
 <span data-ttu-id="0b63b-110">Es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="0b63b-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0b63b-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="0b63b-111">Result Types</span></span>  
 <span data-ttu-id="0b63b-112">El tipo de datos de *expression*.</span><span class="sxs-lookup"><span data-stu-id="0b63b-112">The data type of *expression*.</span></span> <span data-ttu-id="0b63b-113">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b63b-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0b63b-114">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="0b63b-114">Expression Examples</span></span>  
 <span data-ttu-id="0b63b-115">Este ejemplo muestra cómo el uso de paréntesis modifica la prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="0b63b-115">This example shows how the use of parenthesis modifies the precedence of operators.</span></span> <span data-ttu-id="0b63b-116">La primera expresión se evalúa como 100, mientras que la segunda se evalúa como 31.</span><span class="sxs-lookup"><span data-stu-id="0b63b-116">The first expression evaluates to 100, whereas the second one evaluates to 31.</span></span>  
  
```  
(5 + 5) * (4 + 6)  
5 + 5 * 4 + 6  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b63b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b63b-117">See Also</span></span>  
 <span data-ttu-id="0b63b-118">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="0b63b-118">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="0b63b-119">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0b63b-119">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
