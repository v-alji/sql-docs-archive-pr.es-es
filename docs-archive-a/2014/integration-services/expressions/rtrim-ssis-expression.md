---
title: RTRIM (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RTRIM function
- trailing blanks
ms.assetid: 529bd43e-3f8a-4682-a33e-569176aa7fc4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 727c30fd72bfca5676b71f4ba42e936a9b926817
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746360"
---
# <a name="rtrim-ssis-expression"></a><span data-ttu-id="5776e-102">RTRIM (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="5776e-102">RTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="5776e-103">Devuelve una expresión de caracteres después de quitar los espacios finales.</span><span class="sxs-lookup"><span data-stu-id="5776e-103">Returns a character expression after removing trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5776e-104">RTRIM no quita los caracteres de espacio en blanco, como los caracteres de tabulación o de salto de línea.</span><span class="sxs-lookup"><span data-stu-id="5776e-104">RTRIM does not remove white space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="5776e-105">Unicode proporciona puntos de código para muchos tipos distintos de espacios, pero su función solo reconoce el punto de código Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="5776e-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="5776e-106">Cuando se convierten cadenas del juego de caracteres de doble byte (DBCS) a Unicode, éstas pueden incluir caracteres de espacio distintos de 0x0020 y la función no puede eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="5776e-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="5776e-107">Para eliminar cualquier tipo de espacio, puede utilizar el método RTrim de Microsoft Visual Basic .NET en un script ejecutado desde el componente Script.</span><span class="sxs-lookup"><span data-stu-id="5776e-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET RTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5776e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5776e-108">Syntax</span></span>  
  
```  
  
RTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5776e-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5776e-109">Arguments</span></span>  
 <span data-ttu-id="5776e-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="5776e-110">*character_expression*</span></span>  
 <span data-ttu-id="5776e-111">Expresión de caracteres de la que puede quitar espacios.</span><span class="sxs-lookup"><span data-stu-id="5776e-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5776e-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="5776e-112">Result Types</span></span>  
 <span data-ttu-id="5776e-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="5776e-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5776e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5776e-114">Remarks</span></span>  
 <span data-ttu-id="5776e-115">RTRIM solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="5776e-115">RTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="5776e-116">Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que RTRIM realice su operación.</span><span class="sxs-lookup"><span data-stu-id="5776e-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RTRIM performs its operation.</span></span> <span data-ttu-id="5776e-117">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="5776e-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="5776e-118">Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5776e-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="5776e-119">RTRIM devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="5776e-119">RTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5776e-120">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="5776e-120">Expression Examples</span></span>  
 <span data-ttu-id="5776e-121">Este ejemplo quita los espacios finales de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="5776e-121">This example removes trailing spaces from a string literal.</span></span> <span data-ttu-id="5776e-122">El resultado devuelto es "Hello".</span><span class="sxs-lookup"><span data-stu-id="5776e-122">The return result is "Hello".</span></span>  
  
```  
RTRIM("Hello   ")  
```  
  
 <span data-ttu-id="5776e-123">Este ejemplo quita los espacios finales de una concatenación de las columnas **FirstName** y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="5776e-123">This example removes trailing spaces from a concatenation of the **FirstName** and **LastName** columns.</span></span>  
  
```  
RTRIM(FirstName + " " + LastName)  
```  
  
 <span data-ttu-id="5776e-124">Este ejemplo quita los espacios finales de la variable **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="5776e-124">This example removes trailing spaces from the **FirstName** variable.</span></span>  
  
```  
RTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5776e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5776e-125">See Also</span></span>  
 <span data-ttu-id="5776e-126">[LTRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5776e-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="5776e-127">[TRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5776e-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="5776e-128">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5776e-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
