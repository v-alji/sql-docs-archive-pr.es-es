---
title: LEN (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8863864168295a3a9a924df588312ee65b6f7fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671592"
---
# <a name="len-ssis-expression"></a><span data-ttu-id="c9b86-102">LEN (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="c9b86-102">LEN (SSIS Expression)</span></span>
  <span data-ttu-id="c9b86-103">Devuelve el número de caracteres de una expresión de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c9b86-103">Returns the number of characters in a character expression.</span></span> <span data-ttu-id="c9b86-104">Si la cadena incluye espacios en blanco iniciales y finales, la función puede incluirlos en el recuento.</span><span class="sxs-lookup"><span data-stu-id="c9b86-104">If the string includes leading and trailing blanks, the function includes them in the count.</span></span> <span data-ttu-id="c9b86-105">LEN devuelve valores idénticos para la misma cadena de caracteres de byte único y de doble byte.</span><span class="sxs-lookup"><span data-stu-id="c9b86-105">LEN returns identical values for the same string of single and double byte characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9b86-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9b86-106">Syntax</span></span>  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9b86-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c9b86-107">Arguments</span></span>  
 <span data-ttu-id="c9b86-108">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="c9b86-108">*character_expression*</span></span>  
 <span data-ttu-id="c9b86-109">Expresión que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="c9b86-109">Is the expression to evaluate.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c9b86-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c9b86-110">Result Types</span></span>  
 <span data-ttu-id="c9b86-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="c9b86-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9b86-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c9b86-112">Remarks</span></span>  
 <span data-ttu-id="c9b86-113">El argumento *character_expression* puede tener el tipo de datos DT_WSTR, DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="c9b86-113">The *character_expression* argument can be a DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="c9b86-114">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c9b86-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="c9b86-115">Si *character_expression* es un literal de cadena o una columna de datos con el tipo de datos DT_STR, se convertirá implícitamente al tipo de datos DT_WSTR antes de que LEN realice su operación.</span><span class="sxs-lookup"><span data-stu-id="c9b86-115">If *character_expression* is a string literal or a data column with the DT_STR data type, it is implicitly cast to the DT_WSTR data type before LEN performs its operation.</span></span> <span data-ttu-id="c9b86-116">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c9b86-116">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="c9b86-117">Para más información, vea [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c9b86-117">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="c9b86-118">Si el argumento pasado a la función LEN tiene un tipo de datos de bloque de objetos binarios grandes (BLOB), como DT_TEXT, DT_NTEXT o DT_IMAGE, la función devuelve un número de bytes.</span><span class="sxs-lookup"><span data-stu-id="c9b86-118">If the argument passed to the LEN function has a Binary Large Object Block (BLOB) data type, such as DT_TEXT, DT_NTEXT, or DT_IMAGE, the function returns a byte count.</span></span>  
  
 <span data-ttu-id="c9b86-119">LEN devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="c9b86-119">LEN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c9b86-120">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="c9b86-120">Expression Examples</span></span>  
 <span data-ttu-id="c9b86-121">Este ejemplo devuelve la longitud de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="c9b86-121">This example returns the length of a string literal.</span></span> <span data-ttu-id="c9b86-122">El resultado devuelto es 12.</span><span class="sxs-lookup"><span data-stu-id="c9b86-122">The return result is 12.</span></span>  
  
```  
LEN("Ball Bearing")  
```  
  
 <span data-ttu-id="c9b86-123">Este ejemplo devuelve la diferencia de longitud de los valores de las columnas **FirstName** y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="c9b86-123">This example returns the difference between the length of values in the **FirstName** and **LastName** columns.</span></span>  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 <span data-ttu-id="c9b86-124">Devuelve la longitud de un nombre de equipo utilizando la variable del sistema **MachineName**.</span><span class="sxs-lookup"><span data-stu-id="c9b86-124">Returns the length of a computer name using the System variable **MachineName**.</span></span>  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9b86-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9b86-125">See Also</span></span>  
 [<span data-ttu-id="c9b86-126">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c9b86-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
