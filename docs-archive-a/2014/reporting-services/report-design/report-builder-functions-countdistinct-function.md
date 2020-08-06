---
title: Función CountDistinct (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 902c251e-e1e8-41d2-ac20-5bb6138ac410
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62fab53d4f26a874ac40e0a915c4242a41c72ce0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672721"
---
# <a name="countdistinct-function-report-builder-and-ssrs"></a><span data-ttu-id="35fd2-102">Función CountDistinct (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="35fd2-102">CountDistinct Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="35fd2-103">Devuelve un recuento de todos los valores no NULL distintos especificados por la expresión, que se evalúa en el contexto del ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="35fd2-103">Returns a count of all distinct non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="35fd2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35fd2-104">Syntax</span></span>  
  
```  
  
CountDistinct(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35fd2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35fd2-105">Parameters</span></span>  
 <span data-ttu-id="35fd2-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="35fd2-106">*expression*</span></span>  
 <span data-ttu-id="35fd2-107">(`Variant`) Expresión en la que se lleva a cabo la agregación.</span><span class="sxs-lookup"><span data-stu-id="35fd2-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="35fd2-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="35fd2-108">*scope*</span></span>  
 <span data-ttu-id="35fd2-109">(`String`) (opcional).</span><span class="sxs-lookup"><span data-stu-id="35fd2-109">(`String`) Optional.</span></span> <span data-ttu-id="35fd2-110">Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="35fd2-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="35fd2-111">Si no se especifica el parámetro *scope* , se usa el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="35fd2-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="35fd2-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="35fd2-112">*recursive*</span></span>  
 <span data-ttu-id="35fd2-113">(**Tipo enumerado**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="35fd2-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="35fd2-114">`Simple` (predeterminado) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="35fd2-115">Especifica si se debe realizar la agregación de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="35fd2-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="35fd2-116">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35fd2-116">Return Type</span></span>  
 <span data-ttu-id="35fd2-117">Devuelve un valor `Integer`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-117">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35fd2-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35fd2-118">Remarks</span></span>  
 <span data-ttu-id="35fd2-119">El valor de *scope* debe ser una constante de cadena y no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="35fd2-119">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="35fd2-120">Para los agregados exteriores o los que no especifican a otros agregados, *scope* debe hacer referencia al ámbito actual o a un ámbito de contenido.</span><span class="sxs-lookup"><span data-stu-id="35fd2-120">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="35fd2-121">Para los agregados de agregados, los agregados anidados pueden especificar un ámbito secundario.</span><span class="sxs-lookup"><span data-stu-id="35fd2-121">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="35fd2-122">*Expression* puede contener las llamadas a las funciones de agregados anidados con las siguientes excepciones y condiciones:</span><span class="sxs-lookup"><span data-stu-id="35fd2-122">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="35fd2-123">*Scope* , para los agregados anidados, debe ser igual que el ámbito del agregado exterior, o ser contenido por él.</span><span class="sxs-lookup"><span data-stu-id="35fd2-123">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="35fd2-124">Para todos los ámbitos distintos de la expresión, un ámbito debe estar en una relación secundaria con respecto a todos los otros ámbitos.</span><span class="sxs-lookup"><span data-stu-id="35fd2-124">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="35fd2-125">*Scope* , para los agregados anidados, no puede ser el nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="35fd2-125">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="35fd2-126">*Expression* no debe contener `First` `Last` `Previous` las funciones,, o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="35fd2-126">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="35fd2-127">*Expression* no debe contener a los agregados anidados que especifican *recursive*.</span><span class="sxs-lookup"><span data-stu-id="35fd2-127">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="35fd2-128">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="35fd2-128">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="35fd2-129">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="35fd2-129">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35fd2-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35fd2-130">Example</span></span>  
 <span data-ttu-id="35fd2-131">El ejemplo de código siguiente muestra una expresión que calcula el número de valores no NULL únicos de `Size` para el ámbito predeterminado y para un ámbito de grupo primario.</span><span class="sxs-lookup"><span data-stu-id="35fd2-131">The following code example shows an expression that calculates the number of unique non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="35fd2-132">La expresión se agrega a una celda de una fila que pertenece al grupo secundario `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="35fd2-133">El grupo primario es `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="35fd2-134">La expresión muestra los resultados para `GroupbySubcategory` (el ámbito predeterminado) y, después, para `GroupbyCategory` (el ámbito de grupo primario).</span><span class="sxs-lookup"><span data-stu-id="35fd2-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35fd2-135">Las expresiones no deben contener retornos de carro ni saltos de línea reales; en el código de ejemplo se han incluido para posibilitar la compatibilidad con los representadores de documentación.</span><span class="sxs-lookup"><span data-stu-id="35fd2-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example code to support documentation renderers.</span></span> <span data-ttu-id="35fd2-136">Si copia el ejemplo siguiente, quite los retornos de carro de todas las líneas.</span><span class="sxs-lookup"><span data-stu-id="35fd2-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
```  
="Distinct count (Subcategory): " & CountDistinct(Fields!Size.Value) &   
"Distinct count (Category): " & CountDistinct(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="35fd2-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35fd2-137">See Also</span></span>  
 <span data-ttu-id="35fd2-138">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="35fd2-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="35fd2-139">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="35fd2-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="35fd2-140">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="35fd2-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="35fd2-141">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="35fd2-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
