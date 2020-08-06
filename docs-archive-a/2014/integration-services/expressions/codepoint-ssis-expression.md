---
title: CODEPOINT (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf05cc0838763ba9e22707af57892133d449da07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663025"
---
# <a name="codepoint-ssis-expression"></a><span data-ttu-id="6751b-102">CODEPOINT (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="6751b-102">CODEPOINT (SSIS Expression)</span></span>
  <span data-ttu-id="6751b-103">Devuelve el punto de código Unicode del primer carácter de la izquierda de una expresión de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6751b-103">Returns the Unicode code point of the leftmost character of a character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6751b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6751b-104">Syntax</span></span>  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="6751b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6751b-105">Arguments</span></span>  
 <span data-ttu-id="6751b-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="6751b-106">*character_expression*</span></span>  
 <span data-ttu-id="6751b-107">Expresión de caracteres de la que se va a evaluar el primer carácter de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="6751b-107">Is a character expression whose leftmost character will be evaluated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6751b-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6751b-108">Result Types</span></span>  
 <span data-ttu-id="6751b-109">DT_UI2</span><span class="sxs-lookup"><span data-stu-id="6751b-109">DT_UI2</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6751b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6751b-110">Remarks</span></span>  
 <span data-ttu-id="6751b-111">*character_expression* necesita tener el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="6751b-111">*character_expression* must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="6751b-112">CODEPOINT devuelve un resultado NULL si *character_expression* es NULL o una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="6751b-112">CODEPOINT returns a null result if *character_expression* is null or an empty string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6751b-113">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="6751b-113">Expression Examples</span></span>  
 <span data-ttu-id="6751b-114">Este ejemplo usa un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="6751b-114">This example uses a string literal.</span></span> <span data-ttu-id="6751b-115">El resultado devuelto es 77, el punto de código Unicode correspondiente a la M.</span><span class="sxs-lookup"><span data-stu-id="6751b-115">The return result is 77, the Unicode code point for M.</span></span>  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 <span data-ttu-id="6751b-116">En este ejemplo se utiliza una variable.</span><span class="sxs-lookup"><span data-stu-id="6751b-116">This example uses a variable.</span></span> <span data-ttu-id="6751b-117">Si el valor de **Name** es Touring Front Wheel, el resultado devuelto es 84, el punto de código Unicode correspondiente a la T.</span><span class="sxs-lookup"><span data-stu-id="6751b-117">If **Name** is Touring Front Wheel, the return result is 84, the Unicode code point for T.</span></span>  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="6751b-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6751b-118">See Also</span></span>  
 [<span data-ttu-id="6751b-119">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6751b-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
