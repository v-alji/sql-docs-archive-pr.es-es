---
title: Función CountRows (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b1c403d-6afd-44c8-b5f6-5ecff2a29a45
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d5311dfc5dfcb89449a4039fdac4100fc5a3b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672717"
---
# <a name="countrows-function-report-builder-and-ssrs"></a><span data-ttu-id="bed51-102">Función CountRows (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="bed51-102">CountRows Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bed51-103">Devuelve el número de filas del ámbito especificado, incluidas las filas con valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bed51-103">Returns the number of rows in the specified scope, including rows with null values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="bed51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bed51-104">Syntax</span></span>  
  
```  
  
CountRows(scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bed51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bed51-105">Parameters</span></span>  
 <span data-ttu-id="bed51-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="bed51-106">*scope*</span></span>  
 <span data-ttu-id="bed51-107">(`String`) Nombre de un conjunto de datos, una región de datos o un grupo que contiene los elementos de informe que hay que contar.</span><span class="sxs-lookup"><span data-stu-id="bed51-107">(`String`) The name of a dataset, data region, or group that contains the report items to count.</span></span>  
  
 <span data-ttu-id="bed51-108">*recursive*</span><span class="sxs-lookup"><span data-stu-id="bed51-108">*recursive*</span></span>  
 <span data-ttu-id="bed51-109">(**Tipo enumerado**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="bed51-109">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="bed51-110">`Simple` (predeterminado) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="bed51-110">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="bed51-111">Especifica si se debe realizar la agregación de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="bed51-111">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="bed51-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bed51-112">Return Type</span></span>  
 <span data-ttu-id="bed51-113">Devuelve un valor `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bed51-113">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bed51-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bed51-114">Remarks</span></span>  
 <span data-ttu-id="bed51-115">`CountRows` cuenta todas las filas del ámbito especificado, incluso las filas que contienen valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bed51-115">`CountRows` counts all rows in the specified scope, including rows that have null values.</span></span>  
  
 <span data-ttu-id="bed51-116">El valor de *scope* no puede ser una expresión y debe hacer referencia al ámbito actual o a un ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="bed51-116">The value of *scope* cannot be an expression and must refer to the current scope or a containing scope.</span></span>  
  
 <span data-ttu-id="bed51-117">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="bed51-117">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="bed51-118">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bed51-118">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed51-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bed51-119">Example</span></span>  
 <span data-ttu-id="bed51-120">El ejemplo de código siguiente muestra una expresión que calcula el número de filas de un grupo de filas denominado `GroupbyCategory` (se basa en la expresión `[Category]`).</span><span class="sxs-lookup"><span data-stu-id="bed51-120">The following code example shows an expression that calculates the number of rows in a row group named `GroupbyCategory` (based on the expression `[Category]`).</span></span>  
  
```  
="Number of rows: " & CountRows("GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="bed51-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bed51-121">See Also</span></span>  
 <span data-ttu-id="bed51-122">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bed51-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bed51-123">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bed51-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bed51-124">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bed51-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bed51-125">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bed51-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
