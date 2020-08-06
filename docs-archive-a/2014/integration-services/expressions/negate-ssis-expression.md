---
title: '- (Negar) (expresión de SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (negative)'
- negative operator (-)
ms.assetid: f0118dfc-aced-4de2-953e-5ebf9c962b8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2a2d8ba292f2d24633598ab080ddf75ded5e8bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747702"
---
# <a name="--negate-ssis-expression"></a><span data-ttu-id="2a2e9-102">- (Negativo) (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="2a2e9-102">- (Negate) (SSIS Expression)</span></span>
  <span data-ttu-id="2a2e9-103">Niega una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-103">Negates a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a2e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a2e9-104">Syntax</span></span>  
  
```  
  
-numeric_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a2e9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2a2e9-105">Arguments</span></span>  
 <span data-ttu-id="2a2e9-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="2a2e9-106">*numeric_expression*</span></span>  
 <span data-ttu-id="2a2e9-107">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-107">Is any valid expression of any numeric data type.</span></span> <span data-ttu-id="2a2e9-108">Solo se admiten tipos de datos numéricos con signo.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-108">Only signed numeric data types are supported.</span></span> <span data-ttu-id="2a2e9-109">Para obtener más información, vea [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2a2e9-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2a2e9-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="2a2e9-110">Result Types</span></span>  
 <span data-ttu-id="2a2e9-111">Devuelve el tipo de datos de *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-111">Returns the data type of *numeric_expression*.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2a2e9-112">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="2a2e9-112">Expression Examples</span></span>  
 <span data-ttu-id="2a2e9-113">Este ejemplo niega el valor de la variable **Counter** y le suma el literal numérico 50.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-113">This example negates the value of the **Counter** variable and adds the numeric literal 50.</span></span>  
  
```  
-@Counter + 50  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a2e9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a2e9-114">See Also</span></span>  
 <span data-ttu-id="2a2e9-115">[Precedencia y capacidad de asociación de operadores](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="2a2e9-115">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="2a2e9-116">Operadores &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2a2e9-116">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
