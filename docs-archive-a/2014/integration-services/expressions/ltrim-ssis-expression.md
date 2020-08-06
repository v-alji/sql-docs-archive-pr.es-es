---
title: LTRIM (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- LTRIM function
ms.assetid: d082f42a-d7e7-49f5-a503-ac44ba630832
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 678d9d93eb1dcd7649d2085b651a08418bbcd6a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672193"
---
# <a name="ltrim-ssis-expression"></a><span data-ttu-id="486ae-102">LTRIM (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="486ae-102">LTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="486ae-103">Devuelve una expresión de caracteres tras quitar todos los espacios iniciales en blanco.</span><span class="sxs-lookup"><span data-stu-id="486ae-103">Returns a character expression after removing leading spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="486ae-104">LTRIM no quita los caracteres de espacio en blanco, como los caracteres de tabulación o de salto de línea.</span><span class="sxs-lookup"><span data-stu-id="486ae-104">LTRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="486ae-105">Unicode proporciona puntos de código para muchos tipos distintos de espacios, pero su función solo reconoce el punto de código Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="486ae-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="486ae-106">Cuando se convierten cadenas del juego de caracteres de doble byte (DBCS) a Unicode, éstas pueden incluir caracteres de espacio distintos de 0x0020 y la función no puede eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="486ae-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="486ae-107">Para eliminar cualquier tipo de espacio, puede utilizar el método LTrim de Microsoft Visual Basic .NET en un script ejecutado desde el componente Script.</span><span class="sxs-lookup"><span data-stu-id="486ae-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET LTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486ae-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="486ae-108">Syntax</span></span>  
  
```  
  
LTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="486ae-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="486ae-109">Arguments</span></span>  
 <span data-ttu-id="486ae-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="486ae-110">*character_expression*</span></span>  
 <span data-ttu-id="486ae-111">Expresión de caracteres de la que puede quitar espacios.</span><span class="sxs-lookup"><span data-stu-id="486ae-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="486ae-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="486ae-112">Result Types</span></span>  
 <span data-ttu-id="486ae-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="486ae-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="486ae-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="486ae-114">Remarks</span></span>  
 <span data-ttu-id="486ae-115">LTRIM solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="486ae-115">LTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="486ae-116">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que LTRIM realice su operación.</span><span class="sxs-lookup"><span data-stu-id="486ae-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LTRIM performs its operation.</span></span> <span data-ttu-id="486ae-117">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="486ae-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="486ae-118">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="486ae-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="486ae-119">LTRIM devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="486ae-119">LTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="486ae-120">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="486ae-120">Expression Examples</span></span>  
 <span data-ttu-id="486ae-121">Este ejemplo quita los espacios iniciales de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="486ae-121">This example removes leading spaces from a string literal.</span></span> <span data-ttu-id="486ae-122">El resultado devuelto es "Hello".</span><span class="sxs-lookup"><span data-stu-id="486ae-122">The return result is "Hello".</span></span>  
  
```  
LTRIM("    Hello")  
```  
  
 <span data-ttu-id="486ae-123">Este ejemplo quita los espacios iniciales de los valores de la columna **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="486ae-123">This example removes leading spaces from the **FirstName** column.</span></span>  
  
```  
LTRIM(FirstName)  
```  
  
 <span data-ttu-id="486ae-124">Este ejemplo quita los espacios iniciales de los valores de la variable **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="486ae-124">This example removes leading spaces from the **FirstName** variable.</span></span>  
  
```  
LTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="486ae-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="486ae-125">See Also</span></span>  
 <span data-ttu-id="486ae-126">[RTRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="486ae-126">[RTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="486ae-127">[TRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="486ae-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="486ae-128">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="486ae-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
