---
title: CEILING (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- smallest integer great than or equal to expression
- CEILING function [SSIS]
ms.assetid: c35bd4ee-1ab6-46ab-89a7-cf771527faa2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd2f9f455226925d6bf00842e80a8713e6c72771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677783"
---
# <a name="ceiling-ssis-expression"></a><span data-ttu-id="02a33-102">CEILING (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="02a33-102">CEILING (SSIS Expression)</span></span>
  <span data-ttu-id="02a33-103">Devuelve el menor entero mayor o igual que una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="02a33-103">Returns the smallest integer that is greater than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02a33-104">Syntax</span></span>  
  
```  
  
CEILING(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="02a33-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="02a33-105">Arguments</span></span>  
 <span data-ttu-id="02a33-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="02a33-106">*numeric_expression*</span></span>  
 <span data-ttu-id="02a33-107">Expresión numérica válida.</span><span class="sxs-lookup"><span data-stu-id="02a33-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="02a33-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="02a33-108">Result Types</span></span>  
 <span data-ttu-id="02a33-109">El tipo de datos de la expresión numérica pasada a la función.</span><span class="sxs-lookup"><span data-stu-id="02a33-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a33-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02a33-110">Remarks</span></span>  
 <span data-ttu-id="02a33-111">CEILING devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="02a33-111">CEILING returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="02a33-112">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="02a33-112">Expression Examples</span></span>  
 <span data-ttu-id="02a33-113">Estos ejemplos aplican la función CEILING a valores positivos, negativos y cero.</span><span class="sxs-lookup"><span data-stu-id="02a33-113">These examples apply the CEILING function to positive, negative, and zero values.</span></span>  
  
```  
CEILING(123.74)  
```  
  
 <span data-ttu-id="02a33-114">Devuelve 124.00.</span><span class="sxs-lookup"><span data-stu-id="02a33-114">Returns 124.00</span></span>  
  
```  
CEILING(-124.27)  
```  
  
 <span data-ttu-id="02a33-115">Devuelve -124,00</span><span class="sxs-lookup"><span data-stu-id="02a33-115">Returns -124.00</span></span>  
  
```  
CEILING(0.00)  
```  
  
 <span data-ttu-id="02a33-116">Devuelve 0,00.</span><span class="sxs-lookup"><span data-stu-id="02a33-116">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a33-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02a33-117">See Also</span></span>  
 <span data-ttu-id="02a33-118">[FLOOR &#40;expresión de SSIS&#41;](floor-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="02a33-118">[FLOOR &#40;SSIS Expression&#41;](floor-ssis-expression.md) </span></span>  
 [<span data-ttu-id="02a33-119">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="02a33-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
