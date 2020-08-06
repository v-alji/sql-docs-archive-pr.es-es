---
title: Función First (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0914520-30c5-4d63-9b59-8d9342ed63b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cd8578a1d9a17030d603457d4eaadf107316bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672712"
---
# <a name="first-function-report-builder-and-ssrs"></a><span data-ttu-id="1173a-102">Función First (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="1173a-102">First Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1173a-103">Devuelve el primer valor de la expresión especificada en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="1173a-103">Returns the first value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="1173a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1173a-104">Syntax</span></span>  
  
```  
  
First(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1173a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1173a-105">Parameters</span></span>  
 <span data-ttu-id="1173a-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="1173a-106">*expression*</span></span>  
 <span data-ttu-id="1173a-107">(`Variant` o `Binary`). Expresión en la que se lleva a cabo la agregación, por ejemplo, `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="1173a-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="1173a-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="1173a-108">*scope*</span></span>  
 <span data-ttu-id="1173a-109">(`String`) (opcional).</span><span class="sxs-lookup"><span data-stu-id="1173a-109">(`String`) Optional.</span></span> <span data-ttu-id="1173a-110">Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="1173a-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="1173a-111">Si no se especifica el parámetro *scope* , se usa el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="1173a-111">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="1173a-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1173a-112">Return Type</span></span>  
 <span data-ttu-id="1173a-113">Varía según el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="1173a-113">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1173a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1173a-114">Remarks</span></span>  
 <span data-ttu-id="1173a-115">La función `First` devuelve el primer valor de un conjunto de datos después de aplicar todos los filtros y la configuración de ordenación al ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="1173a-115">The `First` function returns the first value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="1173a-116">La función `First` solo se puede usar en expresiones de filtro de grupo con el ámbito actual (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="1173a-116">The `First` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="1173a-117">También puede usar `First` en un encabezado de página para devolver el primer valor de la colección `ReportItems` para una página; esto permite generar encabezados de estilo diccionario que muestren la primera y la última entrada de cada página.</span><span class="sxs-lookup"><span data-stu-id="1173a-117">You can also use `First` in a page header to return the first value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="1173a-118">El valor de *scope* tiene que ser una constante de cadena y no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="1173a-118">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="1173a-119">Para los agregados exteriores o los que no especifican a otros agregados, *scope* debe hacer referencia al ámbito actual o a un ámbito de contenido.</span><span class="sxs-lookup"><span data-stu-id="1173a-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="1173a-120">Para los agregados de agregados, los agregados anidados pueden especificar un ámbito secundario.</span><span class="sxs-lookup"><span data-stu-id="1173a-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="1173a-121">*Expression* puede contener las llamadas a las funciones de agregados anidados con las siguientes excepciones y condiciones:</span><span class="sxs-lookup"><span data-stu-id="1173a-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="1173a-122">*Scope* , para los agregados anidados, debe ser igual que el ámbito del agregado exterior, o ser contenido por él.</span><span class="sxs-lookup"><span data-stu-id="1173a-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="1173a-123">Para todos los ámbitos distintos de la expresión, un ámbito debe estar en una relación secundaria con respecto a todos los otros ámbitos.</span><span class="sxs-lookup"><span data-stu-id="1173a-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="1173a-124">*Scope* , para los agregados anidados, no puede ser el nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="1173a-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="1173a-125">*Expression* no debe contener `First` `Last` `Previous` las funciones,, o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="1173a-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="1173a-126">*Expression* no debe contener a los agregados anidados que especifican *recursive*.</span><span class="sxs-lookup"><span data-stu-id="1173a-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="1173a-127">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="1173a-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="1173a-128">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1173a-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1173a-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1173a-129">Example</span></span>  
 <span data-ttu-id="1173a-130">El siguiente ejemplo de código devuelve el primer número de producto del grupo `Category` de una región de datos:</span><span class="sxs-lookup"><span data-stu-id="1173a-130">The following code example returns the first product number in the `Category` group of a data region:</span></span>  
  
```  
=First(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="1173a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1173a-131">See Also</span></span>  
 <span data-ttu-id="1173a-132">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1173a-132">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1173a-133">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1173a-133">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1173a-134">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1173a-134">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1173a-135">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1173a-135">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
