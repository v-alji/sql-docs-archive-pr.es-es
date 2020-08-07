---
title: REPLACE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- replacing string expression
- REPLACE function
ms.assetid: a6837043-ea70-4c6a-9c7a-6868b02b2adc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e483ba6c9c72cb777f2955929a717c6c2e17a8c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746369"
---
# <a name="replace-ssis-expression"></a><span data-ttu-id="1f39c-102">REPLACE (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="1f39c-102">REPLACE (SSIS Expression)</span></span>
  <span data-ttu-id="1f39c-103">Devuelve una expresión de caracteres tras reemplazar una cadena de caracteres dentro de la expresión por otra cadena de caracteres diferente o por la cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="1f39c-103">Returns a character expression after replacing a character string within the expression with either a different character string or an empty string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f39c-104">La función REPLACE usa con frecuencia cadenas largas.</span><span class="sxs-lookup"><span data-stu-id="1f39c-104">The REPLACE function frequently uses long strings.</span></span> <span data-ttu-id="1f39c-105">Las consecuencias del truncamiento pueden controlarse o pueden dar lugar a una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="1f39c-105">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="1f39c-106">Para obtener más información, vea [Sintaxis &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="1f39c-106">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f39c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f39c-107">Syntax</span></span>  
  
```  
  
REPLACE(character_expression,searchstring,replacementstring)  
```  
  
## <a name="arguments"></a><span data-ttu-id="1f39c-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1f39c-108">Arguments</span></span>  
 <span data-ttu-id="1f39c-109">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="1f39c-109">*character_expression*</span></span>  
 <span data-ttu-id="1f39c-110">Expresión de caracteres válida que busca la función.</span><span class="sxs-lookup"><span data-stu-id="1f39c-110">Is a valid character expression that the function searches.</span></span>  
  
 <span data-ttu-id="1f39c-111">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="1f39c-111">*searchstring*</span></span>  
 <span data-ttu-id="1f39c-112">Expresión de caracteres válida que intenta encontrar la función.</span><span class="sxs-lookup"><span data-stu-id="1f39c-112">Is a valid character expression that the function attempts to locate.</span></span>  
  
 <span data-ttu-id="1f39c-113">*replacementstring*</span><span class="sxs-lookup"><span data-stu-id="1f39c-113">*replacementstring*</span></span>  
 <span data-ttu-id="1f39c-114">Expresión de caracteres válida que se usa como expresión de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="1f39c-114">Is a valid character expression that is the replacement expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1f39c-115">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1f39c-115">Result Types</span></span>  
 <span data-ttu-id="1f39c-116">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="1f39c-116">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f39c-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f39c-117">Remarks</span></span>  
 <span data-ttu-id="1f39c-118">La longitud de *searchstring* no debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="1f39c-118">The length of *searchstring* must not be zero.</span></span>  
  
 <span data-ttu-id="1f39c-119">La longitud de *replacementstring* puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="1f39c-119">The length of *replacementstring* may be zero.</span></span>  
  
 <span data-ttu-id="1f39c-120">Los argumentos *searchstring* y *replacementstring* pueden utilizar variables y columnas.</span><span class="sxs-lookup"><span data-stu-id="1f39c-120">The *searchstring* and *replacementstring* arguments can use variables and columns.</span></span>  
  
 <span data-ttu-id="1f39c-121">REPLACE solo funciona con el tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1f39c-121">REPLACE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="1f39c-122">Los argumentos*character_expression1, character_expression2* y *character_expression3* que son literales de cadena o columnas de datos con el tipo de datos DT_STR se convierten implícitamente al tipo de datos DT_WSTR antes de que REPLACE realice su operación.</span><span class="sxs-lookup"><span data-stu-id="1f39c-122">*character_expression1, character_expression2,* and *character_expression3* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before REPLACE performs its operation.</span></span> <span data-ttu-id="1f39c-123">Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1f39c-123">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="1f39c-124">Para más información, vea [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1f39c-124">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="1f39c-125">REPLACE devuelve un resultado NULL si alguno de los argumentos es NULL.</span><span class="sxs-lookup"><span data-stu-id="1f39c-125">REPLACE returns a null result if any argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1f39c-126">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="1f39c-126">Expression Examples</span></span>  
 <span data-ttu-id="1f39c-127">Este ejemplo usa un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="1f39c-127">This example uses a string literal.</span></span> <span data-ttu-id="1f39c-128">El resultado devuelto es "All Terrain Bike".</span><span class="sxs-lookup"><span data-stu-id="1f39c-128">The return result is "All Terrain Bike".</span></span>  
  
```  
REPLACE("Mountain Bike", "Mountain","All Terrain")  
```  
  
 <span data-ttu-id="1f39c-129">Este ejemplo quita la cadena "Bike" de la columna **Product** .</span><span class="sxs-lookup"><span data-stu-id="1f39c-129">This example removes the string "Bike" from the **Product** column.</span></span>  
  
```  
REPLACE(Product, "Bike","")  
```  
  
 <span data-ttu-id="1f39c-130">Este ejemplo reemplaza los valores de la columna **DaysToManufacture** .</span><span class="sxs-lookup"><span data-stu-id="1f39c-130">This example replaces values in the **DaysToManufacture** column.</span></span> <span data-ttu-id="1f39c-131">La columna tiene un tipo de datos Integer y en la expresión se incluye la conversión de **DaysToManufacture** al tipo de datos DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1f39c-131">The column has an integer data type and the expression includes casting **DaysToManufacture** to the DT_WSTR data type.</span></span>  
  
```  
REPLACE((DT_WSTR,8)DaysToManufacture,"6","5")  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f39c-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f39c-132">See Also</span></span>  
 <span data-ttu-id="1f39c-133">[SUBSTRING &#40;expresión de SSIS&#41;](substring-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1f39c-133">[SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md) </span></span>  
 [<span data-ttu-id="1f39c-134">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1f39c-134">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
