---
title: SIGN (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a34992b0029cd378274e38ce4e37fcd313d2b788
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746358"
---
# <a name="sign-ssis-expression"></a><span data-ttu-id="0e3de-102">SIGN (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="0e3de-102">SIGN (SSIS Expression)</span></span>
  <span data-ttu-id="0e3de-103">Devuelve el signo positivo (+1), negativo (-1) o cero (0) de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="0e3de-103">Returns the positive (+1), negative (-1), or zero (0) sign of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e3de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e3de-104">Syntax</span></span>  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e3de-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0e3de-105">Arguments</span></span>  
 <span data-ttu-id="0e3de-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="0e3de-106">*numeric_expression*</span></span>  
 <span data-ttu-id="0e3de-107">Expresión numérica con signo válida.</span><span class="sxs-lookup"><span data-stu-id="0e3de-107">Is a valid signed numeric expression.</span></span> <span data-ttu-id="0e3de-108">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0e3de-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0e3de-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="0e3de-109">Result Types</span></span>  
 <span data-ttu-id="0e3de-110">DT_I4</span><span class="sxs-lookup"><span data-stu-id="0e3de-110">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e3de-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e3de-111">Remarks</span></span>  
 <span data-ttu-id="0e3de-112">SIGN devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="0e3de-112">SIGN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0e3de-113">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="0e3de-113">Expression Examples</span></span>  
 <span data-ttu-id="0e3de-114">Este ejemplo devuelve el signo de un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="0e3de-114">This example returns the sign of a numeric literal.</span></span> <span data-ttu-id="0e3de-115">El resultado devuelto es -1.</span><span class="sxs-lookup"><span data-stu-id="0e3de-115">The return result is -1.</span></span>  
  
```  
SIGN(-123.45)  
```  
  
 <span data-ttu-id="0e3de-116">Este ejemplo devuelve el signo del resultado de restar la columna **StandardCost** de la columna **DealerPrice** .</span><span class="sxs-lookup"><span data-stu-id="0e3de-116">This example returns the sign of the result of subtracting the **StandardCost** column from the **DealerPrice** column.</span></span>  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e3de-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e3de-117">See Also</span></span>  
 [<span data-ttu-id="0e3de-118">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e3de-118">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
