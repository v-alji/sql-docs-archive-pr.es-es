---
title: SQUARE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQUARE
- square values
ms.assetid: cecf1bb2-3d55-40a6-9688-ed67bcc150b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 09955e708aae707a88aa7821d2a72651a3a44d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746352"
---
# <a name="square-ssis-expression"></a><span data-ttu-id="b49a9-102">SQUARE (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="b49a9-102">SQUARE (SSIS Expression)</span></span>
  <span data-ttu-id="b49a9-103">Devuelve el cuadrado de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="b49a9-103">Returns the square of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b49a9-104">Syntax</span></span>  
  
```  
  
SQUARE(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b49a9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b49a9-105">Arguments</span></span>  
 <span data-ttu-id="b49a9-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="b49a9-106">*numeric_expression*</span></span>  
 <span data-ttu-id="b49a9-107">Expresión numérica de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="b49a9-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="b49a9-108">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b49a9-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b49a9-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b49a9-109">Result Types</span></span>  
 <span data-ttu-id="b49a9-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="b49a9-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b49a9-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b49a9-111">Remarks</span></span>  
 <span data-ttu-id="b49a9-112">SQUARE devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="b49a9-112">SQUARE returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="b49a9-113">Antes de realizar la operación de raíz cuadrada, se convierte el argumento al tipo de datos DT_R8.</span><span class="sxs-lookup"><span data-stu-id="b49a9-113">The argument is cast to the DT_R8 data type before the square operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b49a9-114">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="b49a9-114">Expression Examples</span></span>  
 <span data-ttu-id="b49a9-115">Este ejemplo devuelve el cuadrado de 12.</span><span class="sxs-lookup"><span data-stu-id="b49a9-115">This example returns the square of 12.</span></span> <span data-ttu-id="b49a9-116">El resultado devuelto es 144.</span><span class="sxs-lookup"><span data-stu-id="b49a9-116">The return result is 144.</span></span>  
  
```  
SQUARE(12)  
```  
  
 <span data-ttu-id="b49a9-117">Este ejemplo devuelve el cuadrado del resultado de restar los valores de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="b49a9-117">This example returns the square of the result of subtracting values in two columns.</span></span> <span data-ttu-id="b49a9-118">Si **Value1** contiene 12 y **Value2** contiene 4, la función SQUARE devuelve 64.</span><span class="sxs-lookup"><span data-stu-id="b49a9-118">If **Value1** contains 12 and **Value2** contains 4, the SQUARE function returns 64.</span></span>  
  
```  
SQUARE(Value1 - Value2)  
```  
  
 <span data-ttu-id="b49a9-119">Este ejemplo devuelve la longitud del tercer lado de un triángulo rectángulo aplicando la función SQUARE a dos variables y calculando a continuación la raíz cuadrada de la suma.</span><span class="sxs-lookup"><span data-stu-id="b49a9-119">This example returns the length of the third side of a right angle triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="b49a9-120">Si **Side1** contiene 3 y **Side2** contiene 4, la función SQRT devuelve 5.</span><span class="sxs-lookup"><span data-stu-id="b49a9-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b49a9-121">En las expresiones, los nombres de variables siempre incluyen el prefijo \@.</span><span class="sxs-lookup"><span data-stu-id="b49a9-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49a9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b49a9-122">See Also</span></span>  
 [<span data-ttu-id="b49a9-123">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b49a9-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
