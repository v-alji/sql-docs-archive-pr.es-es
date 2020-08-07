---
title: ROUND (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d77045787eafbc3dd402db9982d8d7a98190bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746361"
---
# <a name="round-ssis-expression"></a><span data-ttu-id="43ef6-102">ROUND (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="43ef6-102">ROUND (SSIS Expression)</span></span>
  <span data-ttu-id="43ef6-103">Devuelve una expresión numérica, redondeada a la longitud o precisión especificada.</span><span class="sxs-lookup"><span data-stu-id="43ef6-103">Returns a numeric expression that is rounded to the specified length or precision.</span></span> <span data-ttu-id="43ef6-104">La evaluación del parámetro de longitud debe devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="43ef6-104">The length parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ef6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43ef6-105">Syntax</span></span>  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="43ef6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="43ef6-106">Arguments</span></span>  
 <span data-ttu-id="43ef6-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="43ef6-107">*numeric_expression*</span></span>  
 <span data-ttu-id="43ef6-108">Expresión con un tipo numérico válido.</span><span class="sxs-lookup"><span data-stu-id="43ef6-108">Is an expression of a valid numeric type.</span></span> <span data-ttu-id="43ef6-109">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="43ef6-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="43ef6-110">*length*</span><span class="sxs-lookup"><span data-stu-id="43ef6-110">*length*</span></span>  
 <span data-ttu-id="43ef6-111">Expresión entera.</span><span class="sxs-lookup"><span data-stu-id="43ef6-111">Is an integer expression.</span></span> <span data-ttu-id="43ef6-112">Es la precisión con la que *numeric_expression* se redondea.</span><span class="sxs-lookup"><span data-stu-id="43ef6-112">It is the precision to which *numeric_expression* is rounded.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="43ef6-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="43ef6-113">Result Types</span></span>  
 <span data-ttu-id="43ef6-114">El mismo tipo que *numeric*_*expression*.</span><span class="sxs-lookup"><span data-stu-id="43ef6-114">The same type as *numeric*_*expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43ef6-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="43ef6-115">Remarks</span></span>  
 <span data-ttu-id="43ef6-116">La evaluación del argumento *length* debe devolver cero o un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="43ef6-116">The *length* argument must evaluate to a positive integer or zero.</span></span>  
  
 <span data-ttu-id="43ef6-117">ROUND devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="43ef6-117">ROUND returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="43ef6-118">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="43ef6-118">Expression Examples</span></span>  
 <span data-ttu-id="43ef6-119">Estos ejemplos redondean los literales numéricos a una longitud de tres.</span><span class="sxs-lookup"><span data-stu-id="43ef6-119">These examples round numeric literals to a length of three.</span></span> <span data-ttu-id="43ef6-120">El primer resultado devuelto es 137,1570, el segundo 137,1580.</span><span class="sxs-lookup"><span data-stu-id="43ef6-120">The first return result is 137.1570, the second 137.1580.</span></span>  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a><span data-ttu-id="43ef6-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43ef6-121">See Also</span></span>  
 [<span data-ttu-id="43ef6-122">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="43ef6-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
