---
title: LOG (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674954"
---
# <a name="log-ssis-expression"></a><span data-ttu-id="84e46-102">LOG (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="84e46-102">LOG (SSIS Expression)</span></span>
  <span data-ttu-id="84e46-103">Devuelve el logaritmo en base 10 de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="84e46-103">Returns the base-10 logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e46-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84e46-104">Syntax</span></span>  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="84e46-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="84e46-105">Arguments</span></span>  
 <span data-ttu-id="84e46-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="84e46-106">*numeric_expression*</span></span>  
 <span data-ttu-id="84e46-107">Expresión numérica válida, distinta de cero y no negativa.</span><span class="sxs-lookup"><span data-stu-id="84e46-107">Is a valid nonzero or nonnegative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="84e46-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="84e46-108">Result Types</span></span>  
 <span data-ttu-id="84e46-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="84e46-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e46-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="84e46-110">Remarks</span></span>  
 <span data-ttu-id="84e46-111">La *expresión numérica* se convierte al tipo de datos DT_R8 antes de que se calcule el logaritmo.</span><span class="sxs-lookup"><span data-stu-id="84e46-111">The *numeric expression* is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="84e46-112">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="84e46-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="84e46-113">Si la evaluación de *numeric_expression* devuelve cero o un valor negativo, el resultado devuelto será NULL.</span><span class="sxs-lookup"><span data-stu-id="84e46-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="84e46-114">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="84e46-114">Expression Examples</span></span>  
 <span data-ttu-id="84e46-115">Este ejemplo usa un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="84e46-115">This example uses a numeric literal.</span></span> <span data-ttu-id="84e46-116">La función devuelve el valor 1,988291341907488.</span><span class="sxs-lookup"><span data-stu-id="84e46-116">The function returns the value 1.988291341907488.</span></span>  
  
```  
LOG(97.34)  
```  
  
 <span data-ttu-id="84e46-117">En este ejemplo se utiliza la columna **Length**.</span><span class="sxs-lookup"><span data-stu-id="84e46-117">This example uses the column **Length**.</span></span> <span data-ttu-id="84e46-118">Si el valor de la columna es 101,24, la función devuelve 2,005352136486217.</span><span class="sxs-lookup"><span data-stu-id="84e46-118">If the column is 101.24, the function returns 2.005352136486217.</span></span>  
  
```  
LOG(Length)   
```  
  
 <span data-ttu-id="84e46-119">En este ejemplo se utiliza la variable **Length**.</span><span class="sxs-lookup"><span data-stu-id="84e46-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="84e46-120">La variable debe tener un tipo de datos numérico o la expresión debe incluir una conversión explícita a un tipo de datos numérico [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84e46-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span> <span data-ttu-id="84e46-121">Si el valor de **Length** es 234,567, la función devuelve 2.370266913465859.</span><span class="sxs-lookup"><span data-stu-id="84e46-121">If **Length** is 234.567, the function returns 2.370266913465859.</span></span>  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="84e46-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84e46-122">See Also</span></span>  
 <span data-ttu-id="84e46-123">[EXP &#40;expresión de SSIS&#41;](exp-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="84e46-123">[EXP &#40;SSIS Expression&#41;](exp-ssis-expression.md) </span></span>  
 <span data-ttu-id="84e46-124">[LN &#40;expresión de SSIS&#41;](ln-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="84e46-124">[LN &#40;SSIS Expression&#41;](ln-ssis-expression.md) </span></span>  
 [<span data-ttu-id="84e46-125">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="84e46-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
