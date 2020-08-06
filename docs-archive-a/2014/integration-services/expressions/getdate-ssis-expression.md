---
title: GETDATE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671597"
---
# <a name="getdate-ssis-expression"></a><span data-ttu-id="2d803-102">GETDATE (expresión de SSIS)</span><span class="sxs-lookup"><span data-stu-id="2d803-102">GETDATE (SSIS Expression)</span></span>
  <span data-ttu-id="2d803-103">Devuelve la fecha actual del sistema con formato DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="2d803-103">Returns the current date of the system in a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="2d803-104">La función GETDATE no tiene argumentos.</span><span class="sxs-lookup"><span data-stu-id="2d803-104">The GETDATE function takes no arguments.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d803-105">El resultado devuelto de la función GETDATE tiene una longitud de 29 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d803-105">The length of the return result from the GETDATE function is 29 characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d803-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d803-106">Syntax</span></span>  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d803-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2d803-107">Arguments</span></span>  
 <span data-ttu-id="2d803-108">None</span><span class="sxs-lookup"><span data-stu-id="2d803-108">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2d803-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="2d803-109">Result Types</span></span>  
 <span data-ttu-id="2d803-110">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="2d803-110">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2d803-111">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="2d803-111">Expression Examples</span></span>  
 <span data-ttu-id="2d803-112">Este ejemplo devuelve el año de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="2d803-112">This example returns the year of the current date.</span></span>  
  
```  
DATEPART("year",GETDATE())  
```  
  
 <span data-ttu-id="2d803-113">Este ejemplo devuelve el número de días entre una fecha de la columna **ModifiedDate** y la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="2d803-113">This example returns the number of days between a date in the **ModifiedDate** column and the current date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 <span data-ttu-id="2d803-114">Este ejemplo agrega tres meses a la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="2d803-114">This example adds three months to the current date.</span></span>  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d803-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d803-115">See Also</span></span>  
 <span data-ttu-id="2d803-116">[GETUTCDATE &#40;expresión de SSIS&#41;](getutcdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2d803-116">[GETUTCDATE &#40;SSIS Expression&#41;](getutcdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="2d803-117">Funciones &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2d803-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
