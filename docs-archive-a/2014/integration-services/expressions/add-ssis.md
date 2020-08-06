---
title: + (Sumar) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- + (add)
- add operator (+)
- adding expressions
ms.assetid: 44df4154-fed5-4e7f-9995-e703a0164f6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fe1e8f2118e6328582cb24abfd44eef5f3b15f79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674971"
---
# <a name="-add-ssis"></a><span data-ttu-id="92683-102">+ (Sumar) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="92683-102">+ (Add) (SSIS)</span></span>
  <span data-ttu-id="92683-103">Suma dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="92683-103">Adds two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92683-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92683-104">Syntax</span></span>  
  
```  
  
numeric_expression1 + numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="92683-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="92683-105">Arguments</span></span>  
 <span data-ttu-id="92683-106">*numeric_expression1, numeric_ expression2*</span><span class="sxs-lookup"><span data-stu-id="92683-106">*numeric_expression1, numeric_ expression2*</span></span>  
 <span data-ttu-id="92683-107">Expresión válida de un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="92683-107">Is any valid expression of a numeric data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="92683-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="92683-108">Result Types</span></span>  
 <span data-ttu-id="92683-109">Determinados por los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="92683-109">Determined by data types of the two arguments.</span></span> <span data-ttu-id="92683-110">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="92683-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92683-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="92683-111">Remarks</span></span>  
 <span data-ttu-id="92683-112">Si alguno de los operandos es NULL, el resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="92683-112">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="92683-113">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="92683-113">Expression Examples</span></span>  
 <span data-ttu-id="92683-114">Este ejemplo suma literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="92683-114">This example adds numeric literals.</span></span>  
  
```  
5 + 6.09 + 7.0  
```  
  
 <span data-ttu-id="92683-115">Este ejemplo suma los valores de las columnas **VacationHours** y **SickLeaveHours** .</span><span class="sxs-lookup"><span data-stu-id="92683-115">This example adds values in the **VacationHours** and **SickLeaveHours** columns.</span></span>  
  
```  
VacationHours + SickLeaveHours  
```  
  
 <span data-ttu-id="92683-116">Este ejemplo suma un valor calculado a la columna **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="92683-116">This example adds a calculated value to the **StandardCost** column.</span></span> <span data-ttu-id="92683-117">La variable **Profit%** debe escribirse entre corchetes porque el nombre incluye el carácter %.</span><span class="sxs-lookup"><span data-stu-id="92683-117">The variable **Profit%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="92683-118">Para más información, vea [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="92683-118">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
StandardCost + (StandardCost * @[Profit%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="92683-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92683-119">See Also</span></span>  
 <span data-ttu-id="92683-120">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="92683-120">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="92683-121">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="92683-121">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  