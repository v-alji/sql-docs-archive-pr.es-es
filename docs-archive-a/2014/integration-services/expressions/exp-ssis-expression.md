---
title: EXP (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exponential functions
- EXP function
ms.assetid: 4cd96d3c-58c9-4a67-a6f6-b72758232912
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 150c92355ab3e0d3a028c98defe2e2fa9a1bf8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673778"
---
# <a name="exp-ssis-expression"></a><span data-ttu-id="819ab-102">EXP (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="819ab-102">EXP (SSIS Expression)</span></span>
  <span data-ttu-id="819ab-103">Devuelve el exponente de la base e de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="819ab-103">Returns the exponent to base e of a numeric expression.</span></span> <span data-ttu-id="819ab-104">La función EXP complementa la acción de la función LN; también se suele llamar antilogaritmo.</span><span class="sxs-lookup"><span data-stu-id="819ab-104">The EXP function complements the action of the LN function and is sometimes referred to as the antilogarithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="819ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="819ab-105">Syntax</span></span>  
  
```  
  
EXP(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="819ab-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="819ab-106">Arguments</span></span>  
 <span data-ttu-id="819ab-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="819ab-107">*numeric_expression*</span></span>  
 <span data-ttu-id="819ab-108">Expresión numérica válida.</span><span class="sxs-lookup"><span data-stu-id="819ab-108">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="819ab-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="819ab-109">Result Types</span></span>  
 <span data-ttu-id="819ab-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="819ab-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="819ab-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="819ab-111">Remarks</span></span>  
 <span data-ttu-id="819ab-112">La expresión numérica se convierte al tipo de datos DT_R8 antes de que se calcule el exponente.</span><span class="sxs-lookup"><span data-stu-id="819ab-112">The numeric expression is cast to the DT_R8 data type before the exponent is computed.</span></span> <span data-ttu-id="819ab-113">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="819ab-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="819ab-114">El resultado devuelto es siempre un número positivo.</span><span class="sxs-lookup"><span data-stu-id="819ab-114">The return result is always a positive number.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="819ab-115">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="819ab-115">Expression Examples</span></span>  
 <span data-ttu-id="819ab-116">En estos ejemplos se aplica la función EXP a cero y a valores positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="819ab-116">These examples apply the EXP function to positive and negative values and to zero.</span></span>  
  
```  
EXP(74)  
```  
  
 <span data-ttu-id="819ab-117">Devuelve 1,373382979540176E+32.</span><span class="sxs-lookup"><span data-stu-id="819ab-117">Returns 1.373382979540176E+32.</span></span>  
  
```  
EXP(-27)  
```  
  
 <span data-ttu-id="819ab-118">Devuelve 1,879528816539083E-12.</span><span class="sxs-lookup"><span data-stu-id="819ab-118">Returns 1.879528816539083E-12.</span></span>  
  
```  
EXP(0)  
```  
  
 <span data-ttu-id="819ab-119">Devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="819ab-119">Returns 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="819ab-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="819ab-120">See Also</span></span>  
 <span data-ttu-id="819ab-121">[LOG &#40;expresión de SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="819ab-121">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="819ab-122">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="819ab-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
