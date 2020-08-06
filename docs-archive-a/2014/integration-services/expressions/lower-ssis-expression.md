---
title: LOWER (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting uppercase to lowercase
- LOWER function
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: 109328e1-5604-40ff-895e-f2e7c13fff41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 180be8f3cfb5a15eb0fcd6ddd3d63b09fe874af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672195"
---
# <a name="lower-ssis-expression"></a><span data-ttu-id="1174a-102">LOWER (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="1174a-102">LOWER (SSIS Expression)</span></span>
  <span data-ttu-id="1174a-103">Devuelve una expresión de caracteres después de convertir los caracteres en mayúsculas a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1174a-103">Returns a character expression after converting uppercase characters to lowercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1174a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1174a-104">Syntax</span></span>  
  
```  
  
LOWER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="1174a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1174a-105">Arguments</span></span>  
 <span data-ttu-id="1174a-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="1174a-106">*character_expression*</span></span>  
 <span data-ttu-id="1174a-107">Expresión de caracteres para convertir a caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1174a-107">Is a character expression to convert to lowercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1174a-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1174a-108">Result Types</span></span>  
 <span data-ttu-id="1174a-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="1174a-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1174a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1174a-110">Remarks</span></span>  
 <span data-ttu-id="1174a-111">LOWER solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1174a-111">LOWER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="1174a-112">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR, se convertirá implícitamente al tipo de datos DT_WSTR antes de que LOWER realice su operación.</span><span class="sxs-lookup"><span data-stu-id="1174a-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LOWER performs its operation.</span></span> <span data-ttu-id="1174a-113">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1174a-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="1174a-114">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1174a-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="1174a-115">LOWER devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="1174a-115">LOWER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1174a-116">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="1174a-116">Expression Examples</span></span>  
 <span data-ttu-id="1174a-117">Este ejemplo convierte un literal de cadena a caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1174a-117">This example converts a string literal to lowercase characters.</span></span> <span data-ttu-id="1174a-118">El resultado devuelto es "new york".</span><span class="sxs-lookup"><span data-stu-id="1174a-118">The return result is "new york".</span></span>  
  
```  
LOWER("New York")  
```  
  
 <span data-ttu-id="1174a-119">Este ejemplo convierte todos los caracteres de la columna de entrada **Color** , a excepción del primer carácter, a caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1174a-119">This example converts all characters from the **Color** input column, except the first character, to lowercase characters.</span></span> <span data-ttu-id="1174a-120">Si el valor de Color es YELLOW, el resultado devuelto es "Yellow".</span><span class="sxs-lookup"><span data-stu-id="1174a-120">If Color is YELLOW, the return result is "Yellow".</span></span> <span data-ttu-id="1174a-121">Para más información, vea [SUBSTRING &#40;expresión de SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1174a-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
LOWER(SUBSTRING(Color, 2, 15))  
```  
  
 <span data-ttu-id="1174a-122">Este ejemplo convierte el valor de la variable **CityName** a caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1174a-122">This example converts the value in the **CityName** variable to lowercase characters.</span></span>  
  
```  
LOWER(@CityName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1174a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1174a-123">See Also</span></span>  
 <span data-ttu-id="1174a-124">[UPPER &#40;expresión de SSIS&#41;](upper-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1174a-124">[UPPER &#40;SSIS Expression&#41;](upper-ssis-expression.md) </span></span>  
 [<span data-ttu-id="1174a-125">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1174a-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
