---
title: GETUTCDATE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f157ab5641e521a42cb3c96c96446b31de5dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746384"
---
# <a name="getutcdate-ssis-expression"></a><span data-ttu-id="62716-102">GETUTCDATE (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="62716-102">GETUTCDATE (SSIS Expression)</span></span>
  <span data-ttu-id="62716-103">Devuelve la fecha actual del sistema en hora UTC (horario universal coordinado u hora del meridiano de Greenwich) usando un formato DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="62716-103">Returns the current date of the system in UTC time (Universal Time Coordinate or Greenwich Mean Time) using a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="62716-104">La función GETUTCDATE no tiene argumentos.</span><span class="sxs-lookup"><span data-stu-id="62716-104">The GETUTCDATE function takes no arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62716-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62716-105">Syntax</span></span>  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="62716-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="62716-106">Arguments</span></span>  
 <span data-ttu-id="62716-107">None</span><span class="sxs-lookup"><span data-stu-id="62716-107">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="62716-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="62716-108">Result Types</span></span>  
 <span data-ttu-id="62716-109">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="62716-109">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="62716-110">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="62716-110">Expression Examples</span></span>  
 <span data-ttu-id="62716-111">Este ejemplo devuelve el año de la fecha actual en hora UTC.</span><span class="sxs-lookup"><span data-stu-id="62716-111">This example returns the year of the current date in UTC time.</span></span>  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 <span data-ttu-id="62716-112">Este ejemplo devuelve el número de días entre una fecha de la columna **ModifiedDate** y la fecha UTC actual.</span><span class="sxs-lookup"><span data-stu-id="62716-112">This example returns the number of days between a date in the **ModifiedDate** column and the current UTC date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 <span data-ttu-id="62716-113">Este ejemplo agrega tres meses a la fecha UTC actual.</span><span class="sxs-lookup"><span data-stu-id="62716-113">This example adds three months to the current UTC date.</span></span>  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="62716-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62716-114">See Also</span></span>  
 <span data-ttu-id="62716-115">[GETDATE &#40;expresión de SSIS&#41;](getdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="62716-115">[GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="62716-116">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="62716-116">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
