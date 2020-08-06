---
title: FLOOR (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b638c9a7215d120c562e416cdecee463f031ad2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672198"
---
# <a name="floor-ssis-expression"></a><span data-ttu-id="27a6e-102">FLOOR (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="27a6e-102">FLOOR (SSIS Expression)</span></span>
  <span data-ttu-id="27a6e-103">Devuelve el mayor entero que es menor o igual que una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="27a6e-103">Returns the largest integer that is less than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27a6e-104">Syntax</span></span>  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="27a6e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="27a6e-105">Arguments</span></span>  
 <span data-ttu-id="27a6e-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="27a6e-106">*numeric_expression*</span></span>  
 <span data-ttu-id="27a6e-107">Expresión numérica válida.</span><span class="sxs-lookup"><span data-stu-id="27a6e-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="27a6e-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="27a6e-108">Result Types</span></span>  
 <span data-ttu-id="27a6e-109">El tipo de datos numérico de la expresión del argumento.</span><span class="sxs-lookup"><span data-stu-id="27a6e-109">The numeric data type of the argument expression.</span></span> <span data-ttu-id="27a6e-110">El resultado es la parte entera del valor calculado en el mismo tipo de datos que *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="27a6e-110">The result is the integer portion of the calculated value in the same data type as *numeric_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27a6e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27a6e-111">Remarks</span></span>  
 <span data-ttu-id="27a6e-112">FLOOR devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="27a6e-112">FLOOR returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="27a6e-113">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="27a6e-113">Expression Examples</span></span>  
 <span data-ttu-id="27a6e-114">Estos ejemplos aplican la función FLOOR a valores positivos, negativos y cero.</span><span class="sxs-lookup"><span data-stu-id="27a6e-114">These examples apply the FLOOR function to positive, negative, and zero values.</span></span>  
  
```  
FLOOR(123.45)  
```  
  
 <span data-ttu-id="27a6e-115">Devuelve 123,00</span><span class="sxs-lookup"><span data-stu-id="27a6e-115">Returns 123.00</span></span>  
  
```  
FLOOR(-123.45)  
```  
  
 <span data-ttu-id="27a6e-116">Devuelve -124,00</span><span class="sxs-lookup"><span data-stu-id="27a6e-116">Returns -124.00</span></span>  
  
```  
FLOOR(0.00)  
```  
  
 <span data-ttu-id="27a6e-117">Devuelve 0,00.</span><span class="sxs-lookup"><span data-stu-id="27a6e-117">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a6e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27a6e-118">See Also</span></span>  
 <span data-ttu-id="27a6e-119">[CEILING &#40;expresión de SSIS&#41;](ceiling-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="27a6e-119">[CEILING &#40;SSIS Expression&#41;](ceiling-ssis-expression.md) </span></span>  
 [<span data-ttu-id="27a6e-120">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="27a6e-120">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
