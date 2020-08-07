---
title: REPLICATE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9502df5bc20c6ad85f1f98fb57fe6b3cf431cc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746366"
---
# <a name="replicate-ssis-expression"></a><span data-ttu-id="8940a-102">REPLICATE (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="8940a-102">REPLICATE (SSIS Expression)</span></span>
  <span data-ttu-id="8940a-103">Devuelve una expresión de caracteres replicada un determinado número de veces.</span><span class="sxs-lookup"><span data-stu-id="8940a-103">Returns a character expression that is replicated a number of times.</span></span> <span data-ttu-id="8940a-104">El argumento *times* debe devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="8940a-104">The *times* argument must evaluate to an integer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8940a-105">La función REPLICATE utiliza con frecuencia cadenas largas y, por consiguiente, es más probable que incurra en el límite de 4.000 caracteres en la longitud de la expresión.</span><span class="sxs-lookup"><span data-stu-id="8940a-105">The REPLICATE function frequently uses long strings, and therefore is more likely to incur the 4000-character limit on expression length.</span></span> <span data-ttu-id="8940a-106">Si el resultado de la evaluación de una expresión tiene el tipo de datos DT_WSTR o DT_STR de Integration Services, la expresión se truncará a 4.000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8940a-106">If the evaluation result of an expression has the Integration Services data type DT_WSTR or DT_STR, the expression will be truncated at 4000 characters.</span></span> <span data-ttu-id="8940a-107">Si el tipo de resultado de una subexpresión es DT_STR o DT_WSTR, dicha subexpresión se truncará también a 4.000 caracteres, independientemente del tipo de resultado de la expresión general.</span><span class="sxs-lookup"><span data-stu-id="8940a-107">If the result type of a sub-expression is DT_STR or DT_WSTR, that sub-expression likewise will be truncated to 4000 characters, regardless of the overall expression result type.</span></span> <span data-ttu-id="8940a-108">Las consecuencias del truncamiento pueden controlarse o pueden dar lugar a una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="8940a-108">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="8940a-109">Para obtener más información, vea [Sintaxis &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="8940a-109">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8940a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8940a-110">Syntax</span></span>  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a><span data-ttu-id="8940a-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8940a-111">Arguments</span></span>  
 <span data-ttu-id="8940a-112">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="8940a-112">*character_expression*</span></span>  
 <span data-ttu-id="8940a-113">Expresión de caracteres que se va a replicar.</span><span class="sxs-lookup"><span data-stu-id="8940a-113">Is a character expression to replicate.</span></span>  
  
 <span data-ttu-id="8940a-114">*times*</span><span class="sxs-lookup"><span data-stu-id="8940a-114">*times*</span></span>  
 <span data-ttu-id="8940a-115">Expresión de tipo entero que especifica el número de veces que se va a replicar *character_expression* .</span><span class="sxs-lookup"><span data-stu-id="8940a-115">Is an integer expression that specifies the number of times *character_expression* is replicated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8940a-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="8940a-116">Result Types</span></span>  
 <span data-ttu-id="8940a-117">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="8940a-117">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8940a-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8940a-118">Remarks</span></span>  
 <span data-ttu-id="8940a-119">Si el valor de *times* es cero, la función devuelve una cadena de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="8940a-119">If *times* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="8940a-120">Si el valor de *times* es un número negativo, la función devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="8940a-120">If *times* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="8940a-121">El argumento *times* también puede utilizar variables y columnas.</span><span class="sxs-lookup"><span data-stu-id="8940a-121">The *times* argument can also use variables and columns.</span></span>  
  
 <span data-ttu-id="8940a-122">REPLICATE solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8940a-122">REPLICATE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="8940a-123">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que REPLICATE realice su operación.</span><span class="sxs-lookup"><span data-stu-id="8940a-123">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before REPLICATE performs its operation.</span></span> <span data-ttu-id="8940a-124">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="8940a-124">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="8940a-125">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8940a-125">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="8940a-126">REPLICATE devuelve un resultado NULL si alguno de los argumentos es NULL.</span><span class="sxs-lookup"><span data-stu-id="8940a-126">REPLICATE returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8940a-127">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="8940a-127">Expression Examples</span></span>  
 <span data-ttu-id="8940a-128">Este ejemplo replica un literal de cadena tres veces.</span><span class="sxs-lookup"><span data-stu-id="8940a-128">This example replicates a string literal three times.</span></span> <span data-ttu-id="8940a-129">El resultado devuelto es "Mountain BikeMountain BikeMountain Bike".</span><span class="sxs-lookup"><span data-stu-id="8940a-129">The return result is "Mountain BikeMountain BikeMountain Bike".</span></span>  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 <span data-ttu-id="8940a-130">Este ejemplo replica los valores de la columna **Name** tantas veces como indique el valor de la variable **Times** .</span><span class="sxs-lookup"><span data-stu-id="8940a-130">This example replicates values in the **Name** column by the value in the **Times** variable.</span></span> <span data-ttu-id="8940a-131">Si el valor de **Times** es 3 y el valor de **Name** es "Touring Front Wheel", el resultado devuelto será "Touring Front WheelTouring Front WheelTouring Front Wheel".</span><span class="sxs-lookup"><span data-stu-id="8940a-131">If **Times** is 3 and **Name** is Touring Front Wheel, the return result is Touring Front WheelTouring Front WheelTouring Front Wheel.</span></span>  
  
```  
REPLICATE(Name, @Times)  
```  
  
 <span data-ttu-id="8940a-132">Este ejemplo replica el valor de la variable **Name** tantas veces como indique el valor de la columna **Times** .</span><span class="sxs-lookup"><span data-stu-id="8940a-132">This example replicates the value in the **Name** variable by the value in the **Times** column.</span></span> <span data-ttu-id="8940a-133">**Times** contiene un tipo de datos no entero y la expresión incluye una conversión explícita a un tipo de datos entero.</span><span class="sxs-lookup"><span data-stu-id="8940a-133">**Times** has a non-integer data type and the expression includes an explicit cast to an integer data type.</span></span> <span data-ttu-id="8940a-134">Si el valor de **Name** es Helmet y el valor de **Times** es 2, la cadena devuelta es "HelmetHelmet".</span><span class="sxs-lookup"><span data-stu-id="8940a-134">If **Name** contains Helmet and **Times** is 2, the return result is "HelmetHelmet".</span></span>  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="8940a-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8940a-135">See Also</span></span>  
 [<span data-ttu-id="8940a-136">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8940a-136">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
