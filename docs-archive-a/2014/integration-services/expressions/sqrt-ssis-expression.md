---
title: SQRT (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQRT function
- square root of given expression
ms.assetid: 54a75389-c501-4e22-87b8-905f66d6a3a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9efa3f8da2e5280692aa65a25610211aba2fa40f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746354"
---
# <a name="sqrt-ssis-expression"></a><span data-ttu-id="ba3db-102">SQRT (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="ba3db-102">SQRT (SSIS Expression)</span></span>
  <span data-ttu-id="ba3db-103">Devuelve la raíz cuadrada de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ba3db-103">Returns the square root of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba3db-104">Syntax</span></span>  
  
```  
  
SQRT(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba3db-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ba3db-105">Arguments</span></span>  
 <span data-ttu-id="ba3db-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="ba3db-106">*numeric_expression*</span></span>  
 <span data-ttu-id="ba3db-107">Expresión numérica de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="ba3db-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="ba3db-108">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba3db-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ba3db-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ba3db-109">Result Types</span></span>  
 <span data-ttu-id="ba3db-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="ba3db-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba3db-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba3db-111">Remarks</span></span>  
 <span data-ttu-id="ba3db-112">SQRT devuelve un resultado NULL si el valor del argumento es NULL.</span><span class="sxs-lookup"><span data-stu-id="ba3db-112">SQRT returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="ba3db-113">SQRT produce un error si el argumento es un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="ba3db-113">SQRT fails if the argument is a negative value.</span></span>  
  
 <span data-ttu-id="ba3db-114">Antes de realizar la operación de raíz cuadrada, se convierte el argumento al tipo de datos DT_R8.</span><span class="sxs-lookup"><span data-stu-id="ba3db-114">The argument is cast to the DT_R8 data type before the square root operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ba3db-115">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="ba3db-115">Expression Examples</span></span>  
 <span data-ttu-id="ba3db-116">Este ejemplo devuelve la raíz cuadrada de un literal numérico.</span><span class="sxs-lookup"><span data-stu-id="ba3db-116">This example returns the square root of a numeric literal.</span></span> <span data-ttu-id="ba3db-117">El resultado devuelto es 12.</span><span class="sxs-lookup"><span data-stu-id="ba3db-117">The return result is 12.</span></span>  
  
```  
SQRT(144)  
```  
  
 <span data-ttu-id="ba3db-118">Este ejemplo devuelve la raíz cuadrada de una expresión, el resultado de restar valores de las columnas **Value1** y **Value2** .</span><span class="sxs-lookup"><span data-stu-id="ba3db-118">This example returns the square root of an expression, the result of subtracting values in the **Value1** and **Value2** columns.</span></span>  
  
```  
SQRT(Value1 - Value2)  
```  
  
 <span data-ttu-id="ba3db-119">Este ejemplo devuelve la longitud del tercer lado de un triángulo rectángulo aplicando la función SQUARE a dos variables y calculando a continuación la raíz cuadrada de la suma.</span><span class="sxs-lookup"><span data-stu-id="ba3db-119">This example returns the length of the third side of a right triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="ba3db-120">Si **Side1** contiene 3 y **Side2** contiene 4, la función SQRT devuelve 5.</span><span class="sxs-lookup"><span data-stu-id="ba3db-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ba3db-121">En las expresiones, los nombres de variables siempre incluyen el prefijo \@.</span><span class="sxs-lookup"><span data-stu-id="ba3db-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3db-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba3db-122">See Also</span></span>  
 [<span data-ttu-id="ba3db-123">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ba3db-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
