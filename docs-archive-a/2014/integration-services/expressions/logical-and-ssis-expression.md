---
title: '&amp;&amp; (AND lógico) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '&& (logical AND)'
- AND, logical AND
- logical AND (&&)
ms.assetid: a8cb3517-d5d1-4861-9f04-905c719185ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8d973d7d4e86f88f7ae88c820ed4e4a5c1ce526f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744792"
---
# <a name="ampamp-logical-and-ssis-expression"></a><span data-ttu-id="b042a-102">&amp;&amp; (AND lógico) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="b042a-102">&amp;&amp; (Logical AND) (SSIS Expression)</span></span>
  <span data-ttu-id="b042a-103">Realiza una operación lógica AND.</span><span class="sxs-lookup"><span data-stu-id="b042a-103">Performs a logical AND operation.</span></span> <span data-ttu-id="b042a-104">La expresión devuelve TRUE si todas las condiciones son TRUE.</span><span class="sxs-lookup"><span data-stu-id="b042a-104">The expression evaluates to TRUE if all conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b042a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b042a-105">Syntax</span></span>  
  
```  
  
boolean_expression1 && boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="b042a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b042a-106">Arguments</span></span>  
 <span data-ttu-id="b042a-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="b042a-107">*boolean _expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="b042a-108">Cualquier expresión válida cuya evaluación devuelva TRUE, FALSE o NULL.</span><span class="sxs-lookup"><span data-stu-id="b042a-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b042a-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b042a-109">Result Types</span></span>  
 <span data-ttu-id="b042a-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="b042a-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b042a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b042a-111">Remarks</span></span>  
 <span data-ttu-id="b042a-112">En la siguiente tabla se muestra el resultado del operador &&.</span><span class="sxs-lookup"><span data-stu-id="b042a-112">The following table shows the result of the && operator.</span></span>  
  
|<span data-ttu-id="b042a-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="b042a-113">Result</span></span>|<span data-ttu-id="b042a-114">Expression</span><span class="sxs-lookup"><span data-stu-id="b042a-114">Expression</span></span>|<span data-ttu-id="b042a-115">Expression</span><span class="sxs-lookup"><span data-stu-id="b042a-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="b042a-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="b042a-116">TRUE</span></span>|<span data-ttu-id="b042a-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="b042a-117">TRUE</span></span>|<span data-ttu-id="b042a-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="b042a-118">TRUE</span></span>|  
|<span data-ttu-id="b042a-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-119">FALSE</span></span>|<span data-ttu-id="b042a-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="b042a-120">TRUE</span></span>|<span data-ttu-id="b042a-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-121">FALSE</span></span>|  
|<span data-ttu-id="b042a-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-122">FALSE</span></span>|<span data-ttu-id="b042a-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-123">FALSE</span></span>|<span data-ttu-id="b042a-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-124">FALSE</span></span>|  
|<span data-ttu-id="b042a-125">NULL</span><span class="sxs-lookup"><span data-stu-id="b042a-125">NULL</span></span>|<span data-ttu-id="b042a-126">NULL</span><span class="sxs-lookup"><span data-stu-id="b042a-126">NULL</span></span>|<span data-ttu-id="b042a-127">NULL</span><span class="sxs-lookup"><span data-stu-id="b042a-127">NULL</span></span>|  
|<span data-ttu-id="b042a-128">NULL</span><span class="sxs-lookup"><span data-stu-id="b042a-128">NULL</span></span>|<span data-ttu-id="b042a-129">NULL</span><span class="sxs-lookup"><span data-stu-id="b042a-129">NULL</span></span>|<span data-ttu-id="b042a-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="b042a-130">TRUE</span></span>|  
|<span data-ttu-id="b042a-131">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-131">FALSE</span></span>|<span data-ttu-id="b042a-132">NULL</span><span class="sxs-lookup"><span data-stu-id="b042a-132">NULL</span></span>|<span data-ttu-id="b042a-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="b042a-133">FALSE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="b042a-134">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="b042a-134">Expression Examples</span></span>  
 <span data-ttu-id="b042a-135">En este ejemplo se usan las columnas **StandardCost** y **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="b042a-135">This example uses the **StandardCost** and the **ListPrice** columns.</span></span> <span data-ttu-id="b042a-136">Este ejemplo devuelve TRUE si el valor de la columna **StandardCost** es menor que 300 y el valor de la columna **ListPrice** es mayor que 500.</span><span class="sxs-lookup"><span data-stu-id="b042a-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 and the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 && ListPrice > 500  
```  
  
 <span data-ttu-id="b042a-137">En este ejemplo se utilizan las variables **SPrice** y **LPrice** en lugar de literales.</span><span class="sxs-lookup"><span data-stu-id="b042a-137">This example uses the variables **SPrice** and **LPrice** instead of literals.</span></span>  
  
```  
StandardCost < @SPrice && ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="b042a-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b042a-138">See Also</span></span>  
 <span data-ttu-id="b042a-139">[& &#40;AND bit a bit&#41; &#40;expresión de SSIS&#41;](bitwise-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b042a-139">[& &#40;Bitwise AND&#41; &#40;SSIS Expression&#41;](bitwise-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="b042a-140">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="b042a-140">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="b042a-141">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b042a-141">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
