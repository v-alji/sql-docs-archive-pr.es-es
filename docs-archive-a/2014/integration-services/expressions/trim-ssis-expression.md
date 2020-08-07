---
title: TRIM (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 42cef8a816f399e39ac99061f34c394156bde45f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746338"
---
# <a name="trim-ssis-expression"></a><span data-ttu-id="f4088-102">TRIM (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="f4088-102">TRIM (SSIS Expression)</span></span>
  <span data-ttu-id="f4088-103">Devuelve una expresión de caracteres después de quitar los espacios iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="f4088-103">Returns a character expression after removing leading and trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4088-104">TRIM no quita los caracteres de espacio en blanco, como los caracteres de tabulación o de salto de línea.</span><span class="sxs-lookup"><span data-stu-id="f4088-104">TRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="f4088-105">Unicode proporciona puntos de código para muchos tipos distintos de espacios, pero su función solo reconoce el punto de código Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="f4088-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="f4088-106">Cuando se convierten cadenas del juego de caracteres de doble byte (DBCS) a Unicode, éstas pueden incluir caracteres de espacio distintos de 0x0020 y la función no puede eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="f4088-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="f4088-107">Para eliminar cualquier tipo de espacio, puede utilizar el método Trim de Microsoft Visual Basic .NET en un script ejecutado desde el componente Script.</span><span class="sxs-lookup"><span data-stu-id="f4088-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET Trim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4088-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4088-108">Syntax</span></span>  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4088-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f4088-109">Arguments</span></span>  
 <span data-ttu-id="f4088-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="f4088-110">*character_expression*</span></span>  
 <span data-ttu-id="f4088-111">Expresión de caracteres de la que puede quitar espacios.</span><span class="sxs-lookup"><span data-stu-id="f4088-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f4088-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="f4088-112">Result Types</span></span>  
 <span data-ttu-id="f4088-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="f4088-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4088-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f4088-114">Remarks</span></span>  
 <span data-ttu-id="f4088-115">TRIM devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="f4088-115">TRIM returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="f4088-116">TRIM solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="f4088-116">TRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="f4088-117">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que TRIM realice su operación.</span><span class="sxs-lookup"><span data-stu-id="f4088-117">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TRIM performs its operation.</span></span> <span data-ttu-id="f4088-118">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="f4088-118">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="f4088-119">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f4088-119">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f4088-120">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="f4088-120">Expression Examples</span></span>  
 <span data-ttu-id="f4088-121">Este ejemplo quita los espacios iniciales y finales de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="f4088-121">This example removes leading and trailing spaces from a string literal.</span></span> <span data-ttu-id="f4088-122">El resultado devuelto es "New York".</span><span class="sxs-lookup"><span data-stu-id="f4088-122">The return result is "New York".</span></span>  
  
```  
TRIM("   New York   ")  
```  
  
 <span data-ttu-id="f4088-123">Este ejemplo quita los espacios iniciales y finales del resultado de concatenar las columnas **FirstName** y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="f4088-123">This example removes leading and trailing spaces from the result of concatenating the **FirstName** and **LastName** columns.</span></span> <span data-ttu-id="f4088-124">La cadena vacía entre **FirstName** y **LastName** no se quita.</span><span class="sxs-lookup"><span data-stu-id="f4088-124">The empty string between **FirstName** and **LastName** is not removed.</span></span>  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4088-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4088-125">See Also</span></span>  
 <span data-ttu-id="f4088-126">[LTRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f4088-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="f4088-127">[RTRIM &#40;expresión de SSIS&#41;](rtrim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f4088-127">[RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="f4088-128">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f4088-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
