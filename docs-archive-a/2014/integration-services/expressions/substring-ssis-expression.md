---
title: SUBSTRING (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SUBSTRING function
- part of expression returned [Integration Services]
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba53676bc6d13ed34892f48fca3b70372cb30604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746347"
---
# <a name="substring-ssis-expression"></a><span data-ttu-id="fbdc9-102">SUBSTRING (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="fbdc9-102">SUBSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="fbdc9-103">Devuelve la parte de una expresión de caracteres que empieza en la posición especificada y tiene la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-103">Returns the part of a character expression that starts at the specified position and has the specified length.</span></span> <span data-ttu-id="fbdc9-104">Los parámetros *position* y *length* deben ser números enteros.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-104">The *position* parameter and the *length* parameter must evaluate to integers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbdc9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbdc9-105">Syntax</span></span>  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="fbdc9-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fbdc9-106">Arguments</span></span>  
 <span data-ttu-id="fbdc9-107">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="fbdc9-107">*character_expression*</span></span>  
 <span data-ttu-id="fbdc9-108">Expresión de caracteres de la que se van a extraer caracteres.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-108">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="fbdc9-109">*position*</span><span class="sxs-lookup"><span data-stu-id="fbdc9-109">*position*</span></span>  
 <span data-ttu-id="fbdc9-110">Entero que especifica el punto en que comienza la subcadena.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-110">Is an integer that specifies where the substring begins.</span></span>  
  
 <span data-ttu-id="fbdc9-111">*length*</span><span class="sxs-lookup"><span data-stu-id="fbdc9-111">*length*</span></span>  
 <span data-ttu-id="fbdc9-112">Entero que especifica la longitud de la subcadena como el número de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-112">Is an integer that specifies the length of the substring as number of characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fbdc9-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="fbdc9-113">Result Types</span></span>  
 <span data-ttu-id="fbdc9-114">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="fbdc9-114">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbdc9-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fbdc9-115">Remarks</span></span>  
 <span data-ttu-id="fbdc9-116">SUBSTRING utiliza un índice de base uno.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-116">SUBSTRING uses a one-based index.</span></span> <span data-ttu-id="fbdc9-117">Si *position* es 1, la subcadena empieza con el primer carácter de *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-117">If *position* is 1, the substring begins with the first character in *character_expression*.</span></span>  
  
 <span data-ttu-id="fbdc9-118">SUBSTRING solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-118">SUBSTRING works only with the DT_WSTR data type.</span></span> <span data-ttu-id="fbdc9-119">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR, se convertirá implícitamente al tipo de datos DT_WSTR antes de que SUBSTRING realice su operación.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-119">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before SUBSTRING performs its operation.</span></span> <span data-ttu-id="fbdc9-120">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-120">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="fbdc9-121">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="fbdc9-121">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="fbdc9-122">SUBSTRING devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-122">SUBSTRING returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="fbdc9-123">Todos los argumentos de la expresión pueden usar variables y columnas.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-123">All arguments in the expression can use variables and columns.</span></span>  
  
 <span data-ttu-id="fbdc9-124">El valor del argumento *length* puede superar la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-124">The *length* argument can exceed the length of the string.</span></span> <span data-ttu-id="fbdc9-125">En tal caso, la función devuelve el resto de la cadena.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-125">In that case, the function returns the remainder of the string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="fbdc9-126">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="fbdc9-126">Expression Examples</span></span>  
 <span data-ttu-id="fbdc9-127">Este ejemplo devuelve dos caracteres, empezando por el carácter 4, de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-127">This example returns two characters, beginning with character 4, from a string literal.</span></span> <span data-ttu-id="fbdc9-128">El resultado devuelto es "ph".</span><span class="sxs-lookup"><span data-stu-id="fbdc9-128">The return result is "ph".</span></span>  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 <span data-ttu-id="fbdc9-129">Este ejemplo devuelve el resto de una cadena literal, empezando por el cuarto carácter.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-129">This example returns the remainder of a string literal, beginning at the fourth character.</span></span> <span data-ttu-id="fbdc9-130">El resultado devuelto es "phant".</span><span class="sxs-lookup"><span data-stu-id="fbdc9-130">The return result is "phant".</span></span> <span data-ttu-id="fbdc9-131">Que el valor del argumento *length* supere la longitud de la cadena no es un error.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-131">It is not an error for the *length* argument to exceed the length of the string.</span></span>  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 <span data-ttu-id="fbdc9-132">Este ejemplo devuelve la primera letra de la columna **MiddleName** .</span><span class="sxs-lookup"><span data-stu-id="fbdc9-132">This example returns the first letter from the **MiddleName** column.</span></span>  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 <span data-ttu-id="fbdc9-133">En este ejemplo se utilizan variables en los argumentos *position* y *length* .</span><span class="sxs-lookup"><span data-stu-id="fbdc9-133">This example uses variables in the *position* and *length* arguments.</span></span> <span data-ttu-id="fbdc9-134">Si el valor de **Start** es 1 y el de **Length** es 5, la función devuelve los cinco primeros caracteres de la columna **Name** .</span><span class="sxs-lookup"><span data-stu-id="fbdc9-134">If **Start** is 1 and **Length** is 5, the function returns the first five characters in the **Name** column.</span></span>  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 <span data-ttu-id="fbdc9-135">Este ejemplo devuelve los cuatro últimos caracteres de la variable **PostalCode** , empezando por el sexto carácter.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-135">This example returns the last four characters from the **PostalCode** variable beginning at the sixth character.</span></span>  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 <span data-ttu-id="fbdc9-136">Este ejemplo devuelve una cadena de longitud cero de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="fbdc9-136">This example returns a zero-length string from a string literal.</span></span>  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbdc9-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbdc9-137">See Also</span></span>  
 [<span data-ttu-id="fbdc9-138">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="fbdc9-138">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
