---
title: UPPER (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- UPPER function
- converting lowercase to uppercase
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: d33985f7-1048-4023-83e4-274090acda78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181e231d735a8e98cd2bce10c692e35668a686f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746334"
---
# <a name="upper-ssis-expression"></a><span data-ttu-id="6ad38-102">UPPER (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="6ad38-102">UPPER (SSIS Expression)</span></span>
  <span data-ttu-id="6ad38-103">Devuelve una expresión de caracteres tras convertir los caracteres en minúsculas a mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ad38-103">Returns a character expression after converting lowercase characters to uppercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ad38-104">Syntax</span></span>  
  
```  
  
UPPER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ad38-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ad38-105">Arguments</span></span>  
 <span data-ttu-id="6ad38-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="6ad38-106">*character_expression*</span></span>  
 <span data-ttu-id="6ad38-107">Expresión de caracteres para convertir a caracteres en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ad38-107">Is a character expression to convert to uppercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6ad38-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6ad38-108">Result Types</span></span>  
 <span data-ttu-id="6ad38-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="6ad38-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ad38-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6ad38-110">Remarks</span></span>  
 <span data-ttu-id="6ad38-111">UPPER solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="6ad38-111">UPPER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="6ad38-112">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR, se convertirá implícitamente al tipo de datos DT_WSTR antes de que UPPER realice su operación.</span><span class="sxs-lookup"><span data-stu-id="6ad38-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before UPPER performs its operation.</span></span> <span data-ttu-id="6ad38-113">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="6ad38-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="6ad38-114">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="6ad38-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="6ad38-115">UPPER devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="6ad38-115">UPPER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6ad38-116">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="6ad38-116">Expression Examples</span></span>  
 <span data-ttu-id="6ad38-117">Este ejemplo convierte un literal de cadena a caracteres en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ad38-117">This example converts a string literal to uppercase characters.</span></span> <span data-ttu-id="6ad38-118">El resultado devuelto es "HELLO".</span><span class="sxs-lookup"><span data-stu-id="6ad38-118">The return result is "HELLO".</span></span>  
  
```  
UPPER("hello")  
```  
  
 <span data-ttu-id="6ad38-119">Este ejemplo convierte el primer carácter de la columna **FirstName** en un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ad38-119">This example converts the first character in the **FirstName** column to an uppercase character.</span></span> <span data-ttu-id="6ad38-120">Si el valor de **FirstName** es anna, el resultado devuelto es "A".</span><span class="sxs-lookup"><span data-stu-id="6ad38-120">If **FirstName** is anna, the return result is "A".</span></span> <span data-ttu-id="6ad38-121">Para más información, vea [SUBSTRING &#40;expresión de SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="6ad38-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
UPPER(SUBSTRING(FirstName, 1, 1))  
```  
  
 <span data-ttu-id="6ad38-122">Este ejemplo convierte el valor de la variable **PostalCode** a caracteres en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ad38-122">This example converts the value in the **PostalCode** variable to uppercase characters.</span></span> <span data-ttu-id="6ad38-123">Si el valor de **PostalCode** es k4b1s2, el resultado devuelto es "K4B1S2".</span><span class="sxs-lookup"><span data-stu-id="6ad38-123">If **PostalCode** is k4b1s2, the return result is "K4B1S2".</span></span>  
  
```  
UPPER(@PostalCode)  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ad38-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ad38-124">See Also</span></span>  
 <span data-ttu-id="6ad38-125">[LOWER &#40;expresión de SSIS&#41;](lower-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6ad38-125">[LOWER &#40;SSIS Expression&#41;](lower-ssis-expression.md) </span></span>  
 [<span data-ttu-id="6ad38-126">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6ad38-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
