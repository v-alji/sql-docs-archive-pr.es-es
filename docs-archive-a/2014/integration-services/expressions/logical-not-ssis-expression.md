---
title: '! (Not lógico) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672196"
---
# <a name="-logical-not-ssis-expression"></a><span data-ttu-id="977df-103">!</span><span class="sxs-lookup"><span data-stu-id="977df-103">!</span></span> <span data-ttu-id="977df-104">(Not lógico) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="977df-104">(Logical Not) (SSIS Expression)</span></span>
  <span data-ttu-id="977df-105">Niega un operando booleano.</span><span class="sxs-lookup"><span data-stu-id="977df-105">Negates a Boolean operand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="977df-106">El operador !</span><span class="sxs-lookup"><span data-stu-id="977df-106">The !</span></span> <span data-ttu-id="977df-107">no se puede utilizar con otros operadores.</span><span class="sxs-lookup"><span data-stu-id="977df-107">operator cannot be used in conjunction with other operators.</span></span> <span data-ttu-id="977df-108">Por ejemplo, los operadores !</span><span class="sxs-lookup"><span data-stu-id="977df-108">For example, you cannot combine the !</span></span> <span data-ttu-id="977df-109">y > no se pueden combinar para crear el operador !></span><span class="sxs-lookup"><span data-stu-id="977df-109">and the > operators into the !>.</span></span> <span data-ttu-id="977df-110">.</span><span class="sxs-lookup"><span data-stu-id="977df-110">operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="977df-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="977df-111">Syntax</span></span>  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="977df-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="977df-112">Arguments</span></span>  
 <span data-ttu-id="977df-113">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="977df-113">*boolean_expression*</span></span>  
 <span data-ttu-id="977df-114">Cualquier expresión válida que devuelva un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="977df-114">Is any valid expression that evaluates to a Boolean.</span></span> <span data-ttu-id="977df-115">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="977df-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="977df-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="977df-116">Result Types</span></span>  
 <span data-ttu-id="977df-117">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="977df-117">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="977df-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="977df-118">Remarks</span></span>  
 <span data-ttu-id="977df-119">La siguiente tabla muestra el resultado de la</span><span class="sxs-lookup"><span data-stu-id="977df-119">The following table shows the result of the !</span></span> <span data-ttu-id="977df-120">.</span><span class="sxs-lookup"><span data-stu-id="977df-120">operation.</span></span>  
  
|<span data-ttu-id="977df-121">Expresión booleana original</span><span class="sxs-lookup"><span data-stu-id="977df-121">Original Boolean expression</span></span>|<span data-ttu-id="977df-122">Después de aplicar ! como</span><span class="sxs-lookup"><span data-stu-id="977df-122">After applying the !</span></span> <span data-ttu-id="977df-123">operator</span><span class="sxs-lookup"><span data-stu-id="977df-123">operator</span></span>|  
|---------------------------------|------------------------------------|  
|<span data-ttu-id="977df-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="977df-124">TRUE</span></span>|<span data-ttu-id="977df-125">FALSE</span><span class="sxs-lookup"><span data-stu-id="977df-125">FALSE</span></span>|  
|<span data-ttu-id="977df-126">NULL</span><span class="sxs-lookup"><span data-stu-id="977df-126">NULL</span></span>|<span data-ttu-id="977df-127">NULL</span><span class="sxs-lookup"><span data-stu-id="977df-127">NULL</span></span>|  
|<span data-ttu-id="977df-128">FALSE</span><span class="sxs-lookup"><span data-stu-id="977df-128">FALSE</span></span>|<span data-ttu-id="977df-129">TRUE</span><span class="sxs-lookup"><span data-stu-id="977df-129">TRUE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="977df-130">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="977df-130">Expression Examples</span></span>  
 <span data-ttu-id="977df-131">En este ejemplo se devuelve FALSE si el valor de la columna **Color** es "red".</span><span class="sxs-lookup"><span data-stu-id="977df-131">This example evaluates to FALSE if the **Color** column value is "red".</span></span>  
  
```  
!(Color == "red")  
```  
  
 <span data-ttu-id="977df-132">Este ejemplo devuelve TRUE si el valor de la variable **MonthNumber** es igual que el entero que representa el mes actual.</span><span class="sxs-lookup"><span data-stu-id="977df-132">This example evaluates to TRUE if the value of the **MonthNumber** variable is the same as the integer that represents the current month.</span></span> <span data-ttu-id="977df-133">Para más información, vea [MONTH &#40;expresión de SSIS&#41;](month-ssis-expression.md) y [GETDATE &#40;expresión de SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="977df-133">For more information, see [MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) and [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="977df-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="977df-134">See Also</span></span>  
 <span data-ttu-id="977df-135">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="977df-135">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="977df-136">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="977df-136">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
