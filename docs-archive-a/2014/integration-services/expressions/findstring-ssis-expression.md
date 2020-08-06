---
title: FINDSTRING (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FINDSTRING function
ms.assetid: c83cb1b1-3c52-4496-b518-4c9253b9336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72f2ff21cb179ce565e60c6550b8ecc2618a5adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672197"
---
# <a name="findstring-ssis-expression"></a><span data-ttu-id="99e92-102">FINDSTRING (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="99e92-102">FINDSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="99e92-103">Devuelve la ubicación de la repetición especificada de una cadena en una expresión de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99e92-103">Returns the location of the specified occurrence of a string within a character expression.</span></span> <span data-ttu-id="99e92-104">El resultado devuelto es el índice de base uno de la repetición.</span><span class="sxs-lookup"><span data-stu-id="99e92-104">The return result is the one-based index of the occurrence.</span></span> <span data-ttu-id="99e92-105">El parámetro string debe devolver una expresión de caracteres y el parámetro occurrence debe devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="99e92-105">The string parameter must evaluate to a character expression, and the occurrence parameter must evaluate to an integer.</span></span> <span data-ttu-id="99e92-106">Si no se encuentra la cadena, el valor devuelto es 0.</span><span class="sxs-lookup"><span data-stu-id="99e92-106">If the string is not found, the return value is 0.</span></span> <span data-ttu-id="99e92-107">Si la cadena aparece menos veces de las que especifica el argumento de repetición, el valor devuelto es 0.</span><span class="sxs-lookup"><span data-stu-id="99e92-107">If the string occurs fewer times than the occurrence argument specifies, the return value is 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e92-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99e92-108">Syntax</span></span>  
  
```  
  
FINDSTRING(character_expression, searchstring, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="99e92-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="99e92-109">Arguments</span></span>  
 <span data-ttu-id="99e92-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="99e92-110">*character_expression*</span></span>  
 <span data-ttu-id="99e92-111">Cadena de caracteres en la que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="99e92-111">Is the character string to search in.</span></span>  
  
 <span data-ttu-id="99e92-112">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="99e92-112">*searchstring*</span></span>  
 <span data-ttu-id="99e92-113">Cadena de caracteres que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="99e92-113">Is the character string to search for.</span></span>  
  
 <span data-ttu-id="99e92-114">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="99e92-114">*occurrence*</span></span>  
 <span data-ttu-id="99e92-115">Entero con o sin signo que especifica la repetición de *searchstring* que se debe notificar.</span><span class="sxs-lookup"><span data-stu-id="99e92-115">Is a signed or unsigned integer specifying which occurrence of *searchstring* to report.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="99e92-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="99e92-116">Result Types</span></span>  
 <span data-ttu-id="99e92-117">DT_I4</span><span class="sxs-lookup"><span data-stu-id="99e92-117">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99e92-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99e92-118">Remarks</span></span>  
 <span data-ttu-id="99e92-119">FINDSTRING solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="99e92-119">FINDSTRING works only with the DT_WSTR data type.</span></span>  <span data-ttu-id="99e92-120">Los argumentos*character_expression* y *searchstring* , que son literales de cadena o columnas de datos con el tipo de datos DT_STR, se convierten implícitamente al tipo de datos DT_WSTR antes de que FINDSTRING realice su operación.</span><span class="sxs-lookup"><span data-stu-id="99e92-120">*character_expression* and *searchstring* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before FINDSTRING performs its operation.</span></span> <span data-ttu-id="99e92-121">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="99e92-121">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="99e92-122">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="99e92-122">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="99e92-123">FINDSTRING devuelve NULL si el valor de *character_expression* o *searchstring* es NULL.</span><span class="sxs-lookup"><span data-stu-id="99e92-123">FINDSTRING returns null if either *character_expression* or *searchstring* are null.</span></span>  
  
 <span data-ttu-id="99e92-124">Para obtener el índice de la primera repetición, use el valor 1 para el argumento *occurrence* , use 2 para obtener el índice de la segunda repetición, etc.</span><span class="sxs-lookup"><span data-stu-id="99e92-124">Use a value of 1 in the *occurrence* argument to get the index of the first occurrence, 2 for the second occurrence and so forth.</span></span>  
  
 <span data-ttu-id="99e92-125">El valor de *occurrence* debe ser un entero con un valor mayor que 0.</span><span class="sxs-lookup"><span data-stu-id="99e92-125">The *occurrence* must be an integer with a value greater than 0.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="99e92-126">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="99e92-126">Expression Examples</span></span>  
 <span data-ttu-id="99e92-127">Este ejemplo usa un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="99e92-127">This example uses a string literal.</span></span> <span data-ttu-id="99e92-128">Devuelve el valor 11.</span><span class="sxs-lookup"><span data-stu-id="99e92-128">It returns the value 11.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 1)   
```  
  
 <span data-ttu-id="99e92-129">Este ejemplo usa un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="99e92-129">This example uses a string literal.</span></span> <span data-ttu-id="99e92-130">Dado que la cadena "NY" solo aparece dos veces, el resultado devuelto es 0.</span><span class="sxs-lookup"><span data-stu-id="99e92-130">Because the string "NY" occurs only two times, the return result is 0.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 3)   
```  
  
 <span data-ttu-id="99e92-131">Este ejemplo usa la columna **Name** .</span><span class="sxs-lookup"><span data-stu-id="99e92-131">This example uses the **Name** column.</span></span> <span data-ttu-id="99e92-132">Devuelve la ubicación del valor n en la columna **Name** .</span><span class="sxs-lookup"><span data-stu-id="99e92-132">It returns the location of the value n in the **Name** column.</span></span> <span data-ttu-id="99e92-133">El resultado devuelto varía en función del valor de **Name**.</span><span class="sxs-lookup"><span data-stu-id="99e92-133">The return result varies depending on the value in **Name**.</span></span> <span data-ttu-id="99e92-134">Si **Name** contiene Anderson, la función devuelve 8.</span><span class="sxs-lookup"><span data-stu-id="99e92-134">If **Name** contains Anderson, the function returns 8.</span></span>  
  
```  
FINDSTRING(Name,"n", 2)   
```  
  
 <span data-ttu-id="99e92-135">En este ejemplo se utilizan las columnas **Name** y **Size** .</span><span class="sxs-lookup"><span data-stu-id="99e92-135">This example uses the **Name** and **Size** columns.</span></span> <span data-ttu-id="99e92-136">Devuelve la ubicación del primer carácter por la izquierda del valor **Size** de la columna **Name** .</span><span class="sxs-lookup"><span data-stu-id="99e92-136">It returns the location of the leftmost character of the **Size** value in the **Name** column.</span></span> <span data-ttu-id="99e92-137">El resultado devuelto varía en función de los valores de columna.</span><span class="sxs-lookup"><span data-stu-id="99e92-137">The return result varies depending on column values.</span></span> <span data-ttu-id="99e92-138">Si **Name** contiene Mountain,500Red,42 y **Size** contiene 42, el resultado devuelto es 17.</span><span class="sxs-lookup"><span data-stu-id="99e92-138">If **Name** contains Mountain,500Red,42 and **Size** contains 42, the return result is 17.</span></span>  
  
```  
FINDSTRING(Name,Size,1)   
```  
  
## <a name="see-also"></a><span data-ttu-id="99e92-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99e92-139">See Also</span></span>  
 <span data-ttu-id="99e92-140">[REPLACE &#40;expresión de SSIS&#41;](replace-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="99e92-140">[REPLACE &#40;SSIS Expression&#41;](replace-ssis-expression.md) </span></span>  
 [<span data-ttu-id="99e92-141">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="99e92-141">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
