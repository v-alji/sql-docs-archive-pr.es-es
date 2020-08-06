---
title: HEX (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- hexadecimal data
- HEX function
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 640ae38ec5d2cd5ffb448e9aebde5ba5ceba2684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748207"
---
# <a name="hex-ssis-expression"></a><span data-ttu-id="b4dd7-102">HEX (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="b4dd7-102">HEX (SSIS Expression)</span></span>
  <span data-ttu-id="b4dd7-103">Devuelve una cadena que representa el valor hexadecimal de un entero.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-103">Returns a string representing the hexadecimal value of an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4dd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4dd7-104">Syntax</span></span>  
  
```  
  
HEX(integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4dd7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b4dd7-105">Arguments</span></span>  
 <span data-ttu-id="b4dd7-106">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="b4dd7-106">*integer_expression*</span></span>  
 <span data-ttu-id="b4dd7-107">Entero con o sin signo.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-107">Is a signed or unsigned integer.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b4dd7-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b4dd7-108">Result Types</span></span>  
 <span data-ttu-id="b4dd7-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="b4dd7-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4dd7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4dd7-110">Remarks</span></span>  
 <span data-ttu-id="b4dd7-111">HEX devuelve null si *integer_expression* es null.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-111">HEX returns null if *integer_expression* is null.</span></span>  
  
 <span data-ttu-id="b4dd7-112">El argumento *integer_expression* debe devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-112">The *integer_expression* argument must evaluate to an integer.</span></span> <span data-ttu-id="b4dd7-113">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4dd7-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="b4dd7-114">El resultado devuelto no incluye calificadores, como el prefijo 0x.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-114">The return result does not include qualifiers such as the 0x prefix.</span></span> <span data-ttu-id="b4dd7-115">Para incluir un prefijo utilice el operador + (Concatenar).</span><span class="sxs-lookup"><span data-stu-id="b4dd7-115">To include a prefix, use the + (Concatenate) operator.</span></span> <span data-ttu-id="b4dd7-116">Para más información, vea [+ &#40;Concatenar&#41; &#40;expresión de SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b4dd7-116">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="b4dd7-117">En la notación hexadecimal, las letras A-F siempre aparecen en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-117">The letters A - F, used in HEX notations, appear as uppercase characters.</span></span>  
  
 <span data-ttu-id="b4dd7-118">La longitud de la cadena resultante depende del tipo de datos entero usado, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b4dd7-118">The length of the resulting string for integer data types is as follows:</span></span>  
  
-   <span data-ttu-id="b4dd7-119">DT_I1 y DT_UI1 devuelven una cadena con una longitud máxima de 2.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-119">DT_I1 and DT_UI1 return a string with a maximum length of 2.</span></span>  
  
-   <span data-ttu-id="b4dd7-120">DT_I2 y DT_UI2 devuelven una cadena con una longitud máxima de 4.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-120">DT_I2 and DT_UI2 return a string with a maximum length of 4.</span></span>  
  
-   <span data-ttu-id="b4dd7-121">DT_I4 y DT_UI4 devuelven una cadena con una longitud máxima de 8.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-121">DT_I4 and DT_UI4 return a string with a maximum length of 8.</span></span>  
  
-   <span data-ttu-id="b4dd7-122">DT_I8 y DT_UI8 devuelven una cadena con una longitud máxima de 16.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-122">DT_I8 and DT_UI8 return a string with a maximum length of 16.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b4dd7-123">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="b4dd7-123">Expression Examples</span></span>  
 <span data-ttu-id="b4dd7-124">Este ejemplo usa un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-124">This example uses a numeric literal.</span></span> <span data-ttu-id="b4dd7-125">La función devuelve el valor 190.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-125">The function returns the value 190.</span></span>  
  
```  
HEX(400)   
```  
  
 <span data-ttu-id="b4dd7-126">Este ejemplo usa la columna **ReorderPoint** .</span><span class="sxs-lookup"><span data-stu-id="b4dd7-126">This example uses the **ReorderPoint** column.</span></span> <span data-ttu-id="b4dd7-127">El tipo de datos de la columna es `smallint`.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-127">The column data type is `smallint`.</span></span> <span data-ttu-id="b4dd7-128">Si el valor de **ReorderPoint** es 750, la función devuelve 2EE.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-128">If **ReorderPoint** is 750, the function returns 2EE.</span></span>  
  
```  
HEX(ReorderPoint)   
```  
  
 <span data-ttu-id="b4dd7-129">Este ejemplo usa **LocaleID**, una variable del sistema.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-129">This example uses **LocaleID**, a system variable.</span></span> <span data-ttu-id="b4dd7-130">Si el valor de **LocaleID** es 1033, la función devuelve 409.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-130">If **LocaleID** is 1033, the function returns 409.</span></span>  
  
```  
HEX(@LocaleID)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4dd7-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4dd7-131">See Also</span></span>  
 [<span data-ttu-id="b4dd7-132">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4dd7-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
