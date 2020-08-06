---
title: Función Union (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c87e16fe-c12a-4c9d-a9df-7a94e229fd04
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c80926be53254ec512b2189c4b67e8cd5885733f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672685"
---
# <a name="union-function-report-builder-and-ssrs"></a><span data-ttu-id="52037-102">Función Union (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="52037-102">Union Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="52037-103">Devuelve la unión de todos los valores numéricos no NULL especificados por la expresión, que se evalúa en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="52037-103">Returns the union of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="52037-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52037-104">Syntax</span></span>  
  
```  
  
Union(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52037-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52037-105">Parameters</span></span>  
 <span data-ttu-id="52037-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="52037-106">*expression*</span></span>  
 <span data-ttu-id="52037-107">(`SqlGeometry` o `SqlGeography`). Expresión en la que se lleva a cabo la agregación.</span><span class="sxs-lookup"><span data-stu-id="52037-107">(`SqlGeometry` or `SqlGeography`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="52037-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="52037-108">*scope*</span></span>  
 <span data-ttu-id="52037-109">(`String`) (opcional).</span><span class="sxs-lookup"><span data-stu-id="52037-109">(`String`) Optional.</span></span> <span data-ttu-id="52037-110">Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="52037-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="52037-111">Si no se especifica el parámetro *scope* , se usa el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="52037-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="52037-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="52037-112">*recursive*</span></span>  
 <span data-ttu-id="52037-113">(**Tipo enumerado**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="52037-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="52037-114">`Simple` (predeterminado) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="52037-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="52037-115">Especifica si se debe realizar la agregación de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="52037-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return"></a><span data-ttu-id="52037-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52037-116">Return</span></span>  
 <span data-ttu-id="52037-117">Devuelve un objeto espacial, `SqlGeometry` o bien `SqlGeography` , en función del tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="52037-117">Returns a spatial object, either `SqlGeometry` or `SqlGeography`, based on the expression type.</span></span> <span data-ttu-id="52037-118">Para obtener más información sobre los `SqlGeometry` `SqlGeography` tipos de datos espaciales y, vea [información general sobre tipos de datos espaciales](../../relational-databases/spatial/spatial-data-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="52037-118">For more information about `SqlGeometry` and `SqlGeography` spatial data types, see [Spatial Data Types Overview](../../relational-databases/spatial/spatial-data-types-overview.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52037-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52037-119">Remarks</span></span>  
 <span data-ttu-id="52037-120">El conjunto de datos especificado en la expresión debe tener el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="52037-120">The set of data specified in the expression must have the same data type.</span></span>  
  
 <span data-ttu-id="52037-121">El valor de *scope* debe ser una constante de cadena y no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="52037-121">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="52037-122">Para los agregados exteriores o los que no especifican a otros agregados, *scope* debe hacer referencia al ámbito actual o a un ámbito de contenido.</span><span class="sxs-lookup"><span data-stu-id="52037-122">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="52037-123">No se admiten los ámbitos de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="52037-123">Dataset scopes are not supported.</span></span> <span data-ttu-id="52037-124">Para los agregados de agregados, los agregados anidados pueden especificar un ámbito secundario.</span><span class="sxs-lookup"><span data-stu-id="52037-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="52037-125">*Expression* puede contener las llamadas a las funciones de agregados anidados con las siguientes excepciones y condiciones:</span><span class="sxs-lookup"><span data-stu-id="52037-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="52037-126">*Scope* , para los agregados anidados, debe ser igual que el ámbito del agregado exterior, o ser contenido por él.</span><span class="sxs-lookup"><span data-stu-id="52037-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="52037-127">Para todos los ámbitos distintos de la expresión, un ámbito debe estar en una relación secundaria con respecto a todos los otros ámbitos.</span><span class="sxs-lookup"><span data-stu-id="52037-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="52037-128">*Scope* , para los agregados anidados, no puede ser el nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="52037-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="52037-129">*Expression* no debe contener `First` `Last` `Previous` las funciones,, o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="52037-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="52037-130">*Expression* no debe contener a los agregados anidados que especifican *recursive*.</span><span class="sxs-lookup"><span data-stu-id="52037-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="52037-131">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="52037-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="52037-132">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="52037-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52037-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52037-133">Example</span></span>  
 <span data-ttu-id="52037-134">En la tabla siguiente se muestran ejemplos de las expresiones `SqlGeometry` y la expresión de resultado de `Union`, mostrados en formato de texto bien conocido (WKT, Well Known Text) para los datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="52037-134">The following table shows examples of `SqlGeometry` expressions and `Union` result expression, shown in WKT (Well Known Text) format for spatial data.</span></span>  
  
|<span data-ttu-id="52037-135">Campo con datos espaciales</span><span class="sxs-lookup"><span data-stu-id="52037-135">Field with spatial data</span></span>|<span data-ttu-id="52037-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52037-136">Example</span></span>|<span data-ttu-id="52037-137">Resultado de UNION</span><span class="sxs-lookup"><span data-stu-id="52037-137">Union result</span></span>|  
|-----------------------------|-------------|------------------|  
|<span data-ttu-id="52037-138">[PointLocation]</span><span class="sxs-lookup"><span data-stu-id="52037-138">[PointLocation]</span></span>|<span data-ttu-id="52037-139">POINT(1 2)</span><span class="sxs-lookup"><span data-stu-id="52037-139">POINT(1 2)</span></span><br /><br /> <span data-ttu-id="52037-140">POINT(3 4)</span><span class="sxs-lookup"><span data-stu-id="52037-140">POINT(3 4)</span></span>|<span data-ttu-id="52037-141">MULTIPOINT((1 2), (3 4))</span><span class="sxs-lookup"><span data-stu-id="52037-141">MULTIPOINT((1 2), (3 4))</span></span>|  
|<span data-ttu-id="52037-142">[PathDefinition]</span><span class="sxs-lookup"><span data-stu-id="52037-142">[PathDefinition]</span></span>|<span data-ttu-id="52037-143">LINESTRING(1 2, 3 4)</span><span class="sxs-lookup"><span data-stu-id="52037-143">LINESTRING(1 2, 3 4)</span></span><br /><br /> <span data-ttu-id="52037-144">LINESTRING(5 6, 7 8)</span><span class="sxs-lookup"><span data-stu-id="52037-144">LINESTRING(5 6, 7 8)</span></span>|<span data-ttu-id="52037-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span><span class="sxs-lookup"><span data-stu-id="52037-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span></span>|  
|<span data-ttu-id="52037-146">[PolygonDefinition]</span><span class="sxs-lookup"><span data-stu-id="52037-146">[PolygonDefinition]</span></span>|<span data-ttu-id="52037-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span><span class="sxs-lookup"><span data-stu-id="52037-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span></span><br /><br /> <span data-ttu-id="52037-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span><span class="sxs-lookup"><span data-stu-id="52037-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span></span>|<span data-ttu-id="52037-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span><span class="sxs-lookup"><span data-stu-id="52037-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span></span>|  
  
```  
=Union(Fields!PointLocation.Value)  
=Union(Fields!PathDefinition.Value)  
=Union(Fields!PolygonDefinition.Value, "Group1")  
```  
  
## <a name="see-also"></a><span data-ttu-id="52037-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52037-150">See Also</span></span>  
 <span data-ttu-id="52037-151">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52037-151">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52037-152">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52037-152">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52037-153">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52037-153">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="52037-154">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="52037-154">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
