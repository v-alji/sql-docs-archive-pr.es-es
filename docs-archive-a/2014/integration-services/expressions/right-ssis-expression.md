---
title: RIGHT (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2584ee33ecbf0436c4e3dc6e92b957e60ae396ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746364"
---
# <a name="right-ssis-expression"></a><span data-ttu-id="c51d1-102">RIGHT (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="c51d1-102">RIGHT (SSIS Expression)</span></span>
  <span data-ttu-id="c51d1-103">Devuelve el número de caracteres especificado de la parte más a la derecha de la expresión de caracteres dada.</span><span class="sxs-lookup"><span data-stu-id="c51d1-103">Returns the specified number of characters from the rightmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c51d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c51d1-104">Syntax</span></span>  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c51d1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c51d1-105">Arguments</span></span>  
 <span data-ttu-id="c51d1-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="c51d1-106">*character_expression*</span></span>  
 <span data-ttu-id="c51d1-107">Expresión de caracteres de la que se van a extraer caracteres.</span><span class="sxs-lookup"><span data-stu-id="c51d1-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="c51d1-108">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="c51d1-108">*integer_expression*</span></span>  
 <span data-ttu-id="c51d1-109">Expresión entera que indica el número de caracteres que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="c51d1-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c51d1-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c51d1-110">Result Types</span></span>  
 <span data-ttu-id="c51d1-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c51d1-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c51d1-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c51d1-112">Remarks</span></span>  
 <span data-ttu-id="c51d1-113">Si *integer_expression* es mayor que la longitud de *character_expression*, la función devuelve *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="c51d1-113">If *integer_expression* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="c51d1-114">Si *integer_expression* es cero, la función devuelve una cadena de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="c51d1-114">If *integer_expression* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="c51d1-115">Si *integer_expression* es un número negativo, la función devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="c51d1-115">If *integer_expression* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="c51d1-116">El argumento *integer_expression* puede admitir variables y columnas.</span><span class="sxs-lookup"><span data-stu-id="c51d1-116">The *integer_expression* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="c51d1-117">RIGHT solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c51d1-117">RIGHT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="c51d1-118">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que RIGHT realice su operación.</span><span class="sxs-lookup"><span data-stu-id="c51d1-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RIGHT performs its operation.</span></span> <span data-ttu-id="c51d1-119">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c51d1-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="c51d1-120">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c51d1-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="c51d1-121">RIGHT devuelve un resultado NULL si alguno de los argumentos es NULL.</span><span class="sxs-lookup"><span data-stu-id="c51d1-121">RIGHT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c51d1-122">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="c51d1-122">Expression Examples</span></span>  
 <span data-ttu-id="c51d1-123">En el siguiente ejemplo se utiliza un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="c51d1-123">The following example uses a string literal.</span></span> <span data-ttu-id="c51d1-124">El resultado devuelto es `"Bike"`.</span><span class="sxs-lookup"><span data-stu-id="c51d1-124">The return result is `"Bike"`.</span></span>  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 <span data-ttu-id="c51d1-125">En el ejemplo siguiente se devuelve el número de caracteres situados más a la derecha que se especifica en la variable `Times` de la columna `Name` .</span><span class="sxs-lookup"><span data-stu-id="c51d1-125">The following example returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="c51d1-126">Si `Name` es `Touring Front Wheel` y `Times` es 5, el resultado devuelto es `"Wheel"`.</span><span class="sxs-lookup"><span data-stu-id="c51d1-126">If `Name` is `Touring Front Wheel` and `Times` is 5, the return result is `"Wheel"`.</span></span>  
  
```  
RIGHT(Name, @Times)  
```  
  
 <span data-ttu-id="c51d1-127">En el ejemplo siguiente también se devuelve el número de caracteres situados más a la derecha que se especifica en la variable `Times` de la columna `Name` .</span><span class="sxs-lookup"><span data-stu-id="c51d1-127">The following example also returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="c51d1-128">`Times` tiene un tipo de datos no entero y en la expresión se incluye una conversión explícita al tipo de datos DT_I2.</span><span class="sxs-lookup"><span data-stu-id="c51d1-128">`Times` has a noninteger data type and the expression includes an explicit cast to the DT_I2 data type.</span></span> <span data-ttu-id="c51d1-129">Si `Name` es `Touring Front Wheel` y `Times` es `4.32`, el resultado devuelto es `"heel"` porque la función RIGHT convierte el valor de 4.32 a 4 y, a continuación, devuelve los cuatro caracteres situados más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c51d1-129">If `Name` is `Touring Front Wheel` and `Times` is `4.32`, the return result is `"heel"` because the RIGHT function converts the value of 4.32 to 4, and then returns the rightmost four characters.</span></span>  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="c51d1-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c51d1-130">See Also</span></span>  
 <span data-ttu-id="c51d1-131">[LEFT &#40;expresión de SSIS&#41;](left-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c51d1-131">[LEFT &#40;SSIS Expression&#41;](left-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c51d1-132">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c51d1-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
