---
title: ISNULL (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- null values [Integration Services]
- ISNULL function
ms.assetid: 88dbf49e-1307-4dda-b9db-ff1632053550
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 51eda21b5c9b85c5f9cfd613d0d92df9729fe620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746372"
---
# <a name="isnull-ssis-expression"></a><span data-ttu-id="15074-102">ISNULL (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="15074-102">ISNULL (SSIS Expression)</span></span>
  <span data-ttu-id="15074-103">Devuelve un resultado booleano en función de si una expresión es NULL.</span><span class="sxs-lookup"><span data-stu-id="15074-103">Returns a Boolean result based on whether an expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15074-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15074-104">Syntax</span></span>  
  
```  
  
ISNULL(expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="15074-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="15074-105">Arguments</span></span>  
 <span data-ttu-id="15074-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="15074-106">*expression*</span></span>  
 <span data-ttu-id="15074-107">Expresión válida de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="15074-107">Is a valid expression of any data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="15074-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="15074-108">Result Types</span></span>  
 <span data-ttu-id="15074-109">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="15074-109">DT_BOOL</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="15074-110">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="15074-110">Expression Examples</span></span>  
 <span data-ttu-id="15074-111">Este ejemplo devuelve TRUE si la columna **DiscontinuedDate** contiene un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="15074-111">This example returns TRUE if the **DiscontinuedDate** column contains a null value.</span></span>  
  
```  
ISNULL(DiscontinuedDate)  
```  
  
 <span data-ttu-id="15074-112">Este ejemplo devuelve "Unknown last name" si el valor de la columna **LastName** es NULL; en caso contrario, devuelve el valor de **LastName**.</span><span class="sxs-lookup"><span data-stu-id="15074-112">This example returns "Unknown last name" if the value in the **LastName** column is null, otherwise it returns the value in **LastName**.</span></span>  
  
```  
ISNULL(LastName)? "Unknown last name":LastName  
```  
  
 <span data-ttu-id="15074-113">Este ejemplo siempre devuelve TRUE si la columna **DaysToManufacture** es NULL, independientemente del valor de la variable **AddDays**.</span><span class="sxs-lookup"><span data-stu-id="15074-113">This example always returns TRUE if the **DaysToManufacture** column is null, regardless of the value of the variable **AddDays**.</span></span>  
  
```  
ISNULL(DaysToManufacture + @AddDays)  
```  
  
## <a name="see-also"></a><span data-ttu-id="15074-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15074-114">See Also</span></span>  
 <span data-ttu-id="15074-115">[Funciones &#40;expresión de SSIS&#41;](functions-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="15074-115">[Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md) </span></span>  
 [<span data-ttu-id="15074-116">COALESCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15074-116">COALESCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/coalesce-transact-sql)  
  
  
