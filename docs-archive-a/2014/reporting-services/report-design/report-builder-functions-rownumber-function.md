---
title: Función RowNumber (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d718ba8-d323-49fb-aac8-e7013a117b75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f3d16188138c2f268305fddb092d56be870a3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672692"
---
# <a name="rownumber-function-report-builder-and-ssrs"></a><span data-ttu-id="cb814-102">Función RowNumber (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="cb814-102">RowNumber Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cb814-103">Devuelve un recuento actualizado del número de filas para el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="cb814-103">Returns a running count of the number of rows for the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="cb814-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb814-104">Syntax</span></span>  
  
```  
  
RowNumber(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb814-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb814-105">Parameters</span></span>  
 <span data-ttu-id="cb814-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="cb814-106">*scope*</span></span>  
 <span data-ttu-id="cb814-107">(`String`). Nombre de un conjunto de datos, región de datos, grupo o valor NULL (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) que especifica el contexto en el que se evaluará el número de filas.</span><span class="sxs-lookup"><span data-stu-id="cb814-107">(`String`) The name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the number of rows.</span></span> <span data-ttu-id="cb814-108">`Nothing` especifica el contexto más externo, normalmente el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="cb814-108">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb814-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb814-109">Remarks</span></span>  
 <span data-ttu-id="cb814-110">`RowNumber`Devuelve un valor de ejecución del recuento de filas dentro del ámbito especificado, al igual que [RunningValue](report-builder-functions-runningvalue-function.md) devuelve el valor de ejecución de una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="cb814-110">`RowNumber` returns a running value of the count of rows within the specified scope, just as [RunningValue](report-builder-functions-runningvalue-function.md) returns the running value of an aggregate function.</span></span> <span data-ttu-id="cb814-111">Cuando especifique un ámbito, especifique cuándo se deberá restablecer el recuento de filas en 1.</span><span class="sxs-lookup"><span data-stu-id="cb814-111">When you specify a scope, you specify when to reset the row count to 1.</span></span>  
  
 <span data-ttu-id="cb814-112">*scope* no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="cb814-112">*scope* cannot be an expression.</span></span> <span data-ttu-id="cb814-113">*scope* debe ser un ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="cb814-113">*scope* must be a containing scope.</span></span> <span data-ttu-id="cb814-114">Entre los ámbitos más habituales, desde el contenedor más externo al más interno, se encuentran los conjuntos de datos de informe, las regiones de datos, los grupos de filas o los grupos de columnas.</span><span class="sxs-lookup"><span data-stu-id="cb814-114">Typical scopes, from the outermost to the innermost containment, are report dataset, data region, row groups or column groups.</span></span>  
  
 <span data-ttu-id="cb814-115">Para incrementar los valores por columnas, especifique como ámbito el nombre de un grupo de columnas.</span><span class="sxs-lookup"><span data-stu-id="cb814-115">To increment values across columns, specify a scope that is the name of a column group.</span></span> <span data-ttu-id="cb814-116">Para incrementar los números por filas, especifique como ámbito el nombre de un grupo de filas.</span><span class="sxs-lookup"><span data-stu-id="cb814-116">To increment numbers down rows, specify a scope that is the name of a row group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb814-117">No se admite la inclusión de agregados que especifican un grupo de filas y un grupo de columnas en una sola expresión.</span><span class="sxs-lookup"><span data-stu-id="cb814-117">Including aggregates that specify both a row group and a column group in a single expression is not supported.</span></span>  
  
 <span data-ttu-id="cb814-118">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="cb814-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="cb814-119">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="cb814-119">Code Example</span></span>  
 <span data-ttu-id="cb814-120">La expresión siguiente se puede usar con la propiedad `BackgroundColor` de una fila de detalles de región de datos Tablix para alternar el color de las filas de detalles para cada grupo, comenzando siempre por el blanco.</span><span class="sxs-lookup"><span data-stu-id="cb814-120">The following is an expression that you can use for the `BackgroundColor` property of a Tablix data region detail row to alternate the color of detail rows for each group, always beginning with White.</span></span>  
  
```  
=IIF(RowNumber("GroupbyCategory") Mod 2, "White", "PaleGreen")  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb814-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb814-121">See Also</span></span>  
 <span data-ttu-id="cb814-122">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cb814-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cb814-123">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cb814-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cb814-124">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cb814-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cb814-125">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb814-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
