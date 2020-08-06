---
title: Función Previous (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3891deec3f152cdf46da77a7f2d11d38387c5c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672698"
---
# <a name="previous-function-report-builder-and-ssrs"></a><span data-ttu-id="3528d-102">Función Previous (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="3528d-102">Previous Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3528d-103">Devuelve el valor o el valor agregado especificado para la instancia anterior de un elemento dentro del ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="3528d-103">Returns the value or the specified aggregate value for the previous instance of an item within the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="3528d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3528d-104">Syntax</span></span>  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3528d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3528d-105">Parameters</span></span>  
 <span data-ttu-id="3528d-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="3528d-106">*expression*</span></span>  
 <span data-ttu-id="3528d-107">(`Variant` o `Binary`). Expresión que se debe usar para identificar los datos cuyo valor anterior se desea recuperar; por ejemplo, `Fields!Fieldname.Value` o `Sum(Fields!Fieldname.Value)`.</span><span class="sxs-lookup"><span data-stu-id="3528d-107">(`Variant` or `Binary`) The expression to use to identify the data and for which to retrieve the previous value, for example, `Fields!Fieldname.Value` or `Sum(Fields!Fieldname.Value)`.</span></span>  
  
 <span data-ttu-id="3528d-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="3528d-108">*scope*</span></span>  
 <span data-ttu-id="3528d-109">(`String`) (opcional).</span><span class="sxs-lookup"><span data-stu-id="3528d-109">(`String`) Optional.</span></span> <span data-ttu-id="3528d-110">El nombre de un grupo o una región de datos, o null ( `Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ), que especifica el ámbito del que se va a recuperar el valor anterior especificado por *Expression*.</span><span class="sxs-lookup"><span data-stu-id="3528d-110">The name of a group or data region, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the scope from which to retrieve the previous value specified by *expression*.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="3528d-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3528d-111">Return Type</span></span>  
 <span data-ttu-id="3528d-112">Devuelve un valor `Variant` o `Binary`.</span><span class="sxs-lookup"><span data-stu-id="3528d-112">Returns a `Variant` or `Binary`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3528d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3528d-113">Remarks</span></span>  
 <span data-ttu-id="3528d-114">La función `Previous` devuelve el valor anterior para la expresión evaluada en el ámbito especificado después de aplicar todos los filtros y la configuración de ordenación.</span><span class="sxs-lookup"><span data-stu-id="3528d-114">The `Previous` function returns the previous value for the expression evaluated in the specified scope after all sorting and filtering have been applied.</span></span>  
  
 <span data-ttu-id="3528d-115">Si *Expression* no contiene un agregado, la función tiene como `Previous` valor predeterminado el ámbito actual del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="3528d-115">If *expression* does not contain an aggregate, the `Previous` function defaults to the current scope for the report item.</span></span>  
  
 <span data-ttu-id="3528d-116">En un grupo de detalles, utilice `Previous` para especificar el valor de una referencia de campo en la instancia anterior de la fila de detalles.</span><span class="sxs-lookup"><span data-stu-id="3528d-116">In a details group, use `Previous` to specify the value of a field reference in the previous instance of the detail row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3528d-117">La `Previous` función solo admite referencias de campo en el grupo de detalles.</span><span class="sxs-lookup"><span data-stu-id="3528d-117">The `Previous` function only supports field references in the details group.</span></span> <span data-ttu-id="3528d-118">Por ejemplo, en un cuadro de texto del grupo de detalles, `=Previous(Fields!Quantity.Value)` devuelve los datos para el campo `Quantity` de la fila anterior.</span><span class="sxs-lookup"><span data-stu-id="3528d-118">For example, in a text box in the details group, `=Previous(Fields!Quantity.Value)` returns the data for the field `Quantity` from the previous row.</span></span> <span data-ttu-id="3528d-119">En la primera fila, esta expresión devuelve NULL (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="3528d-119">In the first row, this expression returns a null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  
  
 <span data-ttu-id="3528d-120">Si *Expression* contiene una función de agregado que utiliza un ámbito predeterminado, `Previous` agrega los datos de la instancia anterior del ámbito especificado en la llamada a la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="3528d-120">If *expression* contains an aggregate function that uses a default scope, `Previous` aggregates the data within the previous instance of the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="3528d-121">Si *Expression* contiene una función de agregado que especifica un ámbito distinto del predeterminado, el parámetro de *ámbito* de la `Previous` función debe ser un ámbito contenedor para el ámbito especificado en la llamada a la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="3528d-121">If *expression* contains an aggregate function that specifies a scope other than the default, the *scope* parameter for the `Previous` function must be a containing scope for the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="3528d-122">Las funciones `Level` , `InScope` `Aggregate` y `Previous` no se pueden usar en el parámetro *Expression*.</span><span class="sxs-lookup"><span data-stu-id="3528d-122">The functions `Level`, `InScope`, `Aggregate` and `Previous` cannot be used in the *expression*parameter.</span></span> <span data-ttu-id="3528d-123">No se admite especificar el parámetro *recursive* para ninguna función de agregado.</span><span class="sxs-lookup"><span data-stu-id="3528d-123">Specifying the *recursive* parameter for any aggregate function is not supported.</span></span>  
  
 <span data-ttu-id="3528d-124">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="3528d-124">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3528d-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3528d-125">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="3528d-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3528d-126">Description</span></span>  
 <span data-ttu-id="3528d-127">Cuando se coloca en la fila de datos predeterminada de una región de datos, el ejemplo de código siguiente proporciona el valor para el campo `LineTotal` de la fila anterior.</span><span class="sxs-lookup"><span data-stu-id="3528d-127">The following code example, when placed in the default data row of a data region, provides the value for the field `LineTotal` in the previous row.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3528d-128">Código</span><span class="sxs-lookup"><span data-stu-id="3528d-128">Code</span></span>  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a><span data-ttu-id="3528d-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="3528d-129">Description</span></span>  
 <span data-ttu-id="3528d-130">En el ejemplo siguiente se muestra una expresión que calcula la suma de las ventas en un día concreto del mes y el valor anterior para ese día del mes del año anterior.</span><span class="sxs-lookup"><span data-stu-id="3528d-130">The following example shows an expression that calculates the sum of sales on a specific day of the month and the previous value for that day of the month in a previous year.</span></span> <span data-ttu-id="3528d-131">La expresión se agrega a una celda de una fila que pertenece al grupo secundario `GroupbyDay`.</span><span class="sxs-lookup"><span data-stu-id="3528d-131">The expression is added to a cell in a row that belongs to the child group `GroupbyDay`.</span></span> <span data-ttu-id="3528d-132">Su grupo primario es `GroupbyMonth`, cuyo grupo primario es `GroupbyYear`.</span><span class="sxs-lookup"><span data-stu-id="3528d-132">Its parent group is `GroupbyMonth`, which has a parent group `GroupbyYear`.</span></span> <span data-ttu-id="3528d-133">La expresión muestra los resultados para GroupbyDay (el ámbito predeterminado) y, a continuación, para `GroupbyYear` (el ámbito primario del grupo primario `GroupbyMonth`).</span><span class="sxs-lookup"><span data-stu-id="3528d-133">The expression displays the results for GroupbyDay (the default scope) and then for `GroupbyYear` (the parent of the parent group `GroupbyMonth`).</span></span>  
  
 <span data-ttu-id="3528d-134">Por ejemplo, para una región de datos con un grupo primario denominado `Year`, su grupo secundario se denomina `Month`y su grupo secundario se denomina `Day` (3 niveles anidados).</span><span class="sxs-lookup"><span data-stu-id="3528d-134">For example, for a data region with a parent group named `Year`, its child group named `Month`, and its child group named `Day` (3 nested levels).</span></span> <span data-ttu-id="3528d-135">Si se sitúa la expresión `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` en una fila asociada al grupo `Day` , devuelve el valor de las ventas correspondiente al mismo día y mes del año anterior.</span><span class="sxs-lookup"><span data-stu-id="3528d-135">The expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in a row associated with the group `Day` returns the sales value for the same day and month for the previous year.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3528d-136">Código</span><span class="sxs-lookup"><span data-stu-id="3528d-136">Code</span></span>  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a><span data-ttu-id="3528d-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3528d-137">See Also</span></span>  
 <span data-ttu-id="3528d-138">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3528d-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3528d-139">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3528d-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3528d-140">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3528d-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3528d-141">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3528d-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
