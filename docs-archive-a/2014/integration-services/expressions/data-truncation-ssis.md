---
title: Truncamiento de datos (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677223"
---
# <a name="data-truncation-ssis"></a><span data-ttu-id="c42bd-102">Truncamiento de datos (SSIS)</span><span class="sxs-lookup"><span data-stu-id="c42bd-102">Data Truncation (SSIS)</span></span>
  <span data-ttu-id="c42bd-103">Una expresión puede provocar accidentalmente un truncamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="c42bd-103">An expression may inadvertently cause data to be truncated.</span></span> <span data-ttu-id="c42bd-104">El truncamiento puede producirse en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="c42bd-104">Truncation can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="c42bd-105">Cadenas.</span><span class="sxs-lookup"><span data-stu-id="c42bd-105">Strings.</span></span> <span data-ttu-id="c42bd-106">Por ejemplo, traducir datos de cadena con un tipo de datos DT_WSTR a una cadena de la misma longitud, medida en caracteres, con un tipo de datos DT_STR provoca una pérdida de datos si la cadena original contiene caracteres de doble byte.</span><span class="sxs-lookup"><span data-stu-id="c42bd-106">For example, translating string data with a DT_WSTR data type to the same length string, measured in characters, with a DT_STR data type causes data loss if the original string contains double-byte characters.</span></span>  
  
-   <span data-ttu-id="c42bd-107">Dígitos significativos.</span><span class="sxs-lookup"><span data-stu-id="c42bd-107">Significant digits.</span></span> <span data-ttu-id="c42bd-108">Por ejemplo, la conversión de un entero con el tipo de datos DT_I4 a un tipo de datos DT_I2 o la conversión de un entero sin signo a un entero con signo.</span><span class="sxs-lookup"><span data-stu-id="c42bd-108">For example, casting an integer from a DT_I4 data type to a DT_I2 data type or an unsigned integer to a signed integer.</span></span>  
  
-   <span data-ttu-id="c42bd-109">Dígitos no significativos.</span><span class="sxs-lookup"><span data-stu-id="c42bd-109">Insignificant digits.</span></span> <span data-ttu-id="c42bd-110">Por ejemplo, la conversión de un número real con el tipo de datos DT_R8 a DT_R4 o de un entero con el tipo de datos DT_I4 al tipo de datos DT_R4.</span><span class="sxs-lookup"><span data-stu-id="c42bd-110">For example, casting a real number from a DT_R8 to a DT_R4 or an integer from a DT_I4 data type to a DT_R4 data type.</span></span>  
  
 <span data-ttu-id="c42bd-111">El evaluador de expresiones identifica las conversiones explícitas que pueden causar el truncamiento y emite una advertencia al analizar la expresión.</span><span class="sxs-lookup"><span data-stu-id="c42bd-111">The expression evaluator identifies explicit casts that may cause truncation and issues a warning when the expression is parsed.</span></span> <span data-ttu-id="c42bd-112">Por ejemplo, el evaluador de expresiones emite una advertencia si se convierte una cadena de 30 caracteres en una cadena de 20 caracteres.</span><span class="sxs-lookup"><span data-stu-id="c42bd-112">For example, the expression evaluator warns you if a 30-character string is cast into a 20-character string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c42bd-113">El truncamiento no se comprueba en tiempo de ejecución; los datos se truncan sin advertencia.</span><span class="sxs-lookup"><span data-stu-id="c42bd-113">Truncation is not checked at run time; data is truncated without warning.</span></span> <span data-ttu-id="c42bd-114">Sin embargo, la mayoría de los adaptadores y las transformaciones de datos admiten salidas de error que pueden controlar la disposición de las filas de error.</span><span class="sxs-lookup"><span data-stu-id="c42bd-114">However, most data adapters and transformations support error outputs that can handle the disposition of error rows.</span></span> <span data-ttu-id="c42bd-115">Para obtener más información sobre cómo controlar el truncamiento de datos, vea [control de errores en los datos](../data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="c42bd-115">For more information about handling truncation of data, see [Error Handling in Data](../data-flow/error-handling-in-data.md).</span></span>  
  
  
