---
title: Rellenar cadenas (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- padding strings [Integration Services]
- expressions [Integration Services], string padding
- string padding
ms.assetid: d3fed73d-e0d4-4c67-9355-fb7083a72dd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3985fd1b2f29260e2313a761797d2528f5d0e328
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746350"
---
# <a name="string-padding-ssis"></a><span data-ttu-id="14ce3-102">Rellenar cadenas (SSIS)</span><span class="sxs-lookup"><span data-stu-id="14ce3-102">String Padding (SSIS)</span></span>
  <span data-ttu-id="14ce3-103">El evaluador de expresiones no comprueba si una cadena contiene espacios en blanco iniciales y finales, ni rellena cadenas para que tengan la misma longitud antes de compararlas.</span><span class="sxs-lookup"><span data-stu-id="14ce3-103">The expression evaluator does not check if a string contains leading and trailing spaces, and it does not pad strings to make them the same length before it compares them.</span></span> <span data-ttu-id="14ce3-104">Si las expresiones requieren rellenar cadenas, puede utilizar el operador + para concatenar valores de columnas y cadenas de espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="14ce3-104">If expressions requires string padding, you can use the + operator to concatenate column values and blank strings.</span></span> <span data-ttu-id="14ce3-105">Para más información, vea [+ &#40;Concatenar&#41; &#40;expresión de SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="14ce3-105">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="14ce3-106">Por otra parte, si desea quitar espacios, el evaluador de expresiones proporciona las funciones LTRIM, RTRIM y TRIM, que quitan los espacios en blanco iniciales o finales, o ambos.</span><span class="sxs-lookup"><span data-stu-id="14ce3-106">On the other hand, if you want to remove spaces, the expression evaluator provides the LTRIM, RTRIM, and TRIM functions, which remove leading or trailing spaces, or both.</span></span> <span data-ttu-id="14ce3-107">Para más información, vea [LTRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md), [RTRIM &#40;expresión de SSIS&#41;](rtrim-ssis-expression.md) y [TRIM &#40;expresión de SSIS&#41;](trim-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="14ce3-107">For more information, see [LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md), and [TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14ce3-108">La función LEN incluye en el recuento los espacios en blanco iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="14ce3-108">The LEN function includes leading and trailing blanks in its count.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="14ce3-109">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="14ce3-109">Related Content</span></span>  
 <span data-ttu-id="14ce3-110">Artículo técnico, sobre la [referencia rápida de expresiones de SSIS](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), en pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="14ce3-110">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), on pragmaticworks.com</span></span>  
  
  
