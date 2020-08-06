---
title: '|| (OR lógico) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OR operator
- logical OR (||)
- '|| (logical OR)'
ms.assetid: a3c07c09-f121-4187-9617-b01adcf843c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72d4a1c7b54856675f0faa7f5f58452cb8bca450
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744793"
---
# <a name="-logical-or-ssis-expression"></a><span data-ttu-id="272a6-102">|| (OR lógico) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="272a6-102">|| (Logical OR) (SSIS Expression)</span></span>
  <span data-ttu-id="272a6-103">Realiza una operación lógica OR.</span><span class="sxs-lookup"><span data-stu-id="272a6-103">Performs a logical OR operation.</span></span> <span data-ttu-id="272a6-104">La expresión devuelve TRUE si una o ambas condiciones son TRUE.</span><span class="sxs-lookup"><span data-stu-id="272a6-104">The expression evaluates to TRUE if one or both conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="272a6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="272a6-105">Syntax</span></span>  
  
```  
  
boolean_expression1 || boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="272a6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="272a6-106">Arguments</span></span>  
 <span data-ttu-id="272a6-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="272a6-107">*boolean_expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="272a6-108">Cualquier expresión válida cuya evaluación devuelva TRUE, FALSE o NULL.</span><span class="sxs-lookup"><span data-stu-id="272a6-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="272a6-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="272a6-109">Result Types</span></span>  
 <span data-ttu-id="272a6-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="272a6-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="272a6-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="272a6-111">Remarks</span></span>  
 <span data-ttu-id="272a6-112">En la siguiente tabla se muestra el resultado del operador ||.</span><span class="sxs-lookup"><span data-stu-id="272a6-112">The following table shows the result of the || operator.</span></span>  
  
|<span data-ttu-id="272a6-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="272a6-113">Result</span></span>|<span data-ttu-id="272a6-114">Expression</span><span class="sxs-lookup"><span data-stu-id="272a6-114">Expression</span></span>|<span data-ttu-id="272a6-115">Expression</span><span class="sxs-lookup"><span data-stu-id="272a6-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="272a6-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-116">TRUE</span></span>|<span data-ttu-id="272a6-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-117">TRUE</span></span>|<span data-ttu-id="272a6-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-118">TRUE</span></span>|  
|<span data-ttu-id="272a6-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-119">TRUE</span></span>|<span data-ttu-id="272a6-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-120">TRUE</span></span>|<span data-ttu-id="272a6-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="272a6-121">FALSE</span></span>|  
|<span data-ttu-id="272a6-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="272a6-122">FALSE</span></span>|<span data-ttu-id="272a6-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="272a6-123">FALSE</span></span>|<span data-ttu-id="272a6-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="272a6-124">FALSE</span></span>|  
|<span data-ttu-id="272a6-125">NULL</span><span class="sxs-lookup"><span data-stu-id="272a6-125">NULL</span></span>|<span data-ttu-id="272a6-126">NULL</span><span class="sxs-lookup"><span data-stu-id="272a6-126">NULL</span></span>|<span data-ttu-id="272a6-127">NULL</span><span class="sxs-lookup"><span data-stu-id="272a6-127">NULL</span></span>|  
|<span data-ttu-id="272a6-128">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-128">TRUE</span></span>|<span data-ttu-id="272a6-129">NULL</span><span class="sxs-lookup"><span data-stu-id="272a6-129">NULL</span></span>|<span data-ttu-id="272a6-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="272a6-130">TRUE</span></span>|  
|<span data-ttu-id="272a6-131">NULL</span><span class="sxs-lookup"><span data-stu-id="272a6-131">NULL</span></span>|<span data-ttu-id="272a6-132">NULL</span><span class="sxs-lookup"><span data-stu-id="272a6-132">NULL</span></span>|<span data-ttu-id="272a6-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="272a6-133">FALSE</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="272a6-134">Ejemplos de expresiones de SSIS</span><span class="sxs-lookup"><span data-stu-id="272a6-134">SSIS Expression Examples</span></span>  
 <span data-ttu-id="272a6-135">En este ejemplo se usan las columnas **StandardCost** y **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="272a6-135">This example uses the **StandardCost** and **ListPrice** columns.</span></span> <span data-ttu-id="272a6-136">Este ejemplo devuelve TRUE si el valor de la columna **StandardCost** es menor que 300 o el valor de la columna **ListPrice** es mayor que 500.</span><span class="sxs-lookup"><span data-stu-id="272a6-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 or the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 || ListPrice > 500  
```  
  
 <span data-ttu-id="272a6-137">En este ejemplo se utilizan las variables **SPrice** y **LPrice** en lugar de literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="272a6-137">This example uses the variables **SPrice** and **LPrice** instead of numeric literals.</span></span>  
  
```  
StandardCost < @SPrice || ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="272a6-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="272a6-138">See Also</span></span>  
 <span data-ttu-id="272a6-139">[&#124; &#40;OR inclusivo bit a bit&#41; &#40;expresión de SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="272a6-139">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="272a6-140">[^ &#40;OR exclusivo bit a bit&#41; &#40;expresión de SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="272a6-140">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="272a6-141">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="272a6-141">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="272a6-142">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="272a6-142">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
