---
title: Función StDev (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cb51e96e-a828-42f0-b67c-cee3f4d221e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 58f913501c708b10ca01c24dd591d3378584afa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672689"
---
# <a name="stdev-function-report-builder-and-ssrs"></a><span data-ttu-id="5723d-102">Función StDev (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="5723d-102">StDev Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5723d-103">Devuelve la desviación estándar de todos los valores numéricos no NULL especificados por la expresión, que se evalúa en el contexto del ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="5723d-103">Returns the standard deviation of all non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="5723d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5723d-104">Syntax</span></span>  
  
```  
  
StDev(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5723d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5723d-105">Parameters</span></span>  
 <span data-ttu-id="5723d-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="5723d-106">*expression*</span></span>  
 <span data-ttu-id="5723d-107">(`Integer` o `Float`). Expresión en la que se lleva a cabo la agregación.</span><span class="sxs-lookup"><span data-stu-id="5723d-107">(`Integer` or `Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="5723d-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="5723d-108">*scope*</span></span>  
 <span data-ttu-id="5723d-109">(`String`) (opcional).</span><span class="sxs-lookup"><span data-stu-id="5723d-109">(`String`) Optional.</span></span> <span data-ttu-id="5723d-110">Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="5723d-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="5723d-111">Si no se especifica el parámetro *scope* , se usa el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="5723d-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="5723d-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="5723d-112">*recursive*</span></span>  
 <span data-ttu-id="5723d-113">(**Tipo enumerado**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="5723d-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="5723d-114">`Simple` (predeterminado) o `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="5723d-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="5723d-115">Especifica si se debe realizar la agregación de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="5723d-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="5723d-116">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5723d-116">Return Type</span></span>  
 <span data-ttu-id="5723d-117">Devuelve un valor `Decimal` para expresiones decimales y un valor `Double` para las demás expresiones.</span><span class="sxs-lookup"><span data-stu-id="5723d-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5723d-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5723d-118">Remarks</span></span>  
 <span data-ttu-id="5723d-119">El conjunto de datos especificado en la expresión debe tener el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5723d-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="5723d-120">Si desea convertir datos de varios tipos de datos numéricos al mismo tipo de datos, use funciones de conversión como `CInt`, `CDbl` o `CDec`.</span><span class="sxs-lookup"><span data-stu-id="5723d-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="5723d-121">Para obtener más información, vea [Funciones de conversión de tipos](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="5723d-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="5723d-122">El valor de *scope* debe ser una constante de cadena y no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="5723d-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="5723d-123">Para los agregados exteriores o los que no especifican a otros agregados, *scope* debe hacer referencia al ámbito actual o a un ámbito de contenido.</span><span class="sxs-lookup"><span data-stu-id="5723d-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="5723d-124">Para los agregados de agregados, los agregados anidados pueden especificar un ámbito secundario.</span><span class="sxs-lookup"><span data-stu-id="5723d-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="5723d-125">*Expression* puede contener las llamadas a las funciones de agregados anidados con las siguientes excepciones y condiciones:</span><span class="sxs-lookup"><span data-stu-id="5723d-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="5723d-126">*Scope* , para los agregados anidados, debe ser igual que el ámbito del agregado exterior, o ser contenido por él.</span><span class="sxs-lookup"><span data-stu-id="5723d-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="5723d-127">Para todos los ámbitos distintos de la expresión, un ámbito debe estar en una relación secundaria con respecto a todos los otros ámbitos.</span><span class="sxs-lookup"><span data-stu-id="5723d-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="5723d-128">*Scope* , para los agregados anidados, no puede ser el nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5723d-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="5723d-129">*Expression* no debe contener `First` `Last` `Previous` las funciones,, o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="5723d-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="5723d-130">*Expression* no debe contener a los agregados anidados que especifican *recursive*.</span><span class="sxs-lookup"><span data-stu-id="5723d-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="5723d-131">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="5723d-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="5723d-132">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5723d-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5723d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5723d-133">Example</span></span>  
 <span data-ttu-id="5723d-134">El siguiente ejemplo de código devuelve la desviación estándar de los totales para cada artículo del grupo o de la región de datos `Order` .</span><span class="sxs-lookup"><span data-stu-id="5723d-134">The following code example provides the standard deviation of line item totals in the `Order` group or data region.</span></span>  
  
```  
=StDev(Fields!LineTotal.Value, "Order")  
```  
  
## <a name="see-also"></a><span data-ttu-id="5723d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5723d-135">See Also</span></span>  
 <span data-ttu-id="5723d-136">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5723d-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5723d-137">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5723d-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5723d-138">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5723d-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5723d-139">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5723d-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
