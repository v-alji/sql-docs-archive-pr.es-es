---
title: REVERSE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746365"
---
# <a name="reverse-ssis-expression"></a><span data-ttu-id="5444f-102">REVERSE (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="5444f-102">REVERSE (SSIS Expression)</span></span>
  <span data-ttu-id="5444f-103">Devuelve una expresión de caracteres en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="5444f-103">Returns a character expression in reverse order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5444f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5444f-104">Syntax</span></span>  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5444f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5444f-105">Arguments</span></span>  
 <span data-ttu-id="5444f-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="5444f-106">*character_expression*</span></span>  
 <span data-ttu-id="5444f-107">Expresión de caracteres que se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="5444f-107">Is a character expression to be reversed.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5444f-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="5444f-108">Result Types</span></span>  
 <span data-ttu-id="5444f-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="5444f-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5444f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5444f-110">Remarks</span></span>  
 <span data-ttu-id="5444f-111">El argumento *character_expression* ha de tener el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="5444f-111">The *character_expression* argument must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="5444f-112">REVERSE devuelve un resultado NULL si el valor de *character_expression* es NULL.</span><span class="sxs-lookup"><span data-stu-id="5444f-112">REVERSE returns a null result if *character_expression* is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5444f-113">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="5444f-113">Expression Examples</span></span>  
 <span data-ttu-id="5444f-114">Este ejemplo usa un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="5444f-114">This example uses a string literal.</span></span> <span data-ttu-id="5444f-115">El resultado devuelto es "ekiB niatnuoM".</span><span class="sxs-lookup"><span data-stu-id="5444f-115">The return result is "ekiB niatnuoM".</span></span>  
  
```  
REVERSE("Mountain Bike")  
```  
  
 <span data-ttu-id="5444f-116">En este ejemplo se utiliza una variable.</span><span class="sxs-lookup"><span data-stu-id="5444f-116">This example uses a variable.</span></span> <span data-ttu-id="5444f-117">Si **Name** contiene Touring Bike, el resultado devuelto es "ekiB gniruoT".</span><span class="sxs-lookup"><span data-stu-id="5444f-117">If **Name** contains Touring Bike, the return result is "ekiB gniruoT".</span></span>  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5444f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5444f-118">See Also</span></span>  
 [<span data-ttu-id="5444f-119">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5444f-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
