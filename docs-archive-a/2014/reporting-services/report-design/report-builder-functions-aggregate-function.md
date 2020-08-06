---
title: Función Aggregate (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 16ce643f-bbb3-40a5-ba78-7aed73156f3e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fcc65f1e60c29ba9ea6a4206b419eb0b13edb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673489"
---
# <a name="aggregate-function-report-builder-and-ssrs"></a><span data-ttu-id="d6bcd-102">Función de agregado (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6bcd-102">Aggregate Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d6bcd-103">Devuelve un agregado personalizado de la expresión especificada, según esté definido en el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-103">Returns a custom aggregate of the specified expression, as defined by the data provider.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="d6bcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6bcd-104">Syntax</span></span>  
  
```  
  
Aggregate(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6bcd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6bcd-105">Parameters</span></span>  
 <span data-ttu-id="d6bcd-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="d6bcd-106">*expression*</span></span>  
 <span data-ttu-id="d6bcd-107">Expresión en la que se lleva a cabo la agregación.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-107">The expression on which to perform the aggregation.</span></span> <span data-ttu-id="d6bcd-108">La expresión debe ser una referencia de campo sencilla.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-108">The expression must be a simple field reference.</span></span>  
  
 <span data-ttu-id="d6bcd-109">*scope*</span><span class="sxs-lookup"><span data-stu-id="d6bcd-109">*scope*</span></span>  
 <span data-ttu-id="d6bcd-110">(`String`). Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-110">(`String`) The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="d6bcd-111">*Scope* tiene que ser una constante de cadena y no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-111">*Scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="d6bcd-112">Si no se especifica el parámetro *scope* , se usa el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-112">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="d6bcd-113">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6bcd-113">Return Type</span></span>  
 <span data-ttu-id="d6bcd-114">El tipo de valor devuelto viene determinado por el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-114">Return type is determined by the data provider.</span></span> <span data-ttu-id="d6bcd-115">Devuelve el valor `Nothing` si el proveedor de datos no admite esta función o no hay datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-115">Returns `Nothing` if the data provider does not support this function or data is not available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6bcd-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6bcd-116">Remarks</span></span>  
 <span data-ttu-id="d6bcd-117">La función `Aggregate` proporciona una manera de utilizar los agregados que se calculan en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-117">The `Aggregate` function provides a way to use aggregates that are calculated on the external data source.</span></span> <span data-ttu-id="d6bcd-118">La extensión de datos determina la compatibilidad con esta característica.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-118">Support for this feature is determined by the data extension.</span></span> <span data-ttu-id="d6bcd-119">Por ejemplo, la extensión de procesamiento de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] recupera los conjuntos de filas planas de una consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-119">For example, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data processing extension retrieves flattened rowsets from an MDX query.</span></span> <span data-ttu-id="d6bcd-120">Algunas filas del conjunto de resultados pueden contener valores agregados calculados en el servidor del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-120">Some rows in the result set can contain aggregate values calculated on the data source server.</span></span> <span data-ttu-id="d6bcd-121">Estos se conocen como *agregados de servidor*.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-121">These are known as *server aggregates*.</span></span> <span data-ttu-id="d6bcd-122">Para ver los agregados de servidor en el diseñador gráfico de consultas para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], puede usar el botón **Mostrar agregaciones** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-122">To view server aggregates in the graphical query designer for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the **Show Aggregate** button on the toolbar.</span></span> <span data-ttu-id="d6bcd-123">Para más información, vea [Interfaz de usuario del Diseñador de consultas MDX de Analysis Services &#40;Generador de informes&#41;](../analysis-services-mdx-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d6bcd-123">For more information, see [Analysis Services MDX Query Designer User Interface &#40;Report Builder&#41;](../analysis-services-mdx-query-designer-user-interface-report-builder.md).</span></span>  
  
 <span data-ttu-id="d6bcd-124">Cuando se muestra la combinación de valores agregados y valores de conjunto de datos de detalle en las filas de detalles de una región de datos Tablix, normalmente no se incluyen los agregados de servidor porque no son datos de detalle.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-124">When you display the combination of aggregate and detail dataset values on detail rows of a Tablix data region, server aggregates would not typically be included because they are not detail data.</span></span> <span data-ttu-id="d6bcd-125">Sin embargo, es probable que desee mostrar todos los valores recuperados para el conjunto de datos y personalizar la forma en que se calculan y se muestran los datos agregados.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-125">However, you may want to display all values retrieved for the dataset and customize the way aggregate data is calculated and displayed.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="d6bcd-126">detecta el uso de la función `Aggregate` en las expresiones del informe y con ello determina si debe mostrar los agregados de servidor en las filas de detalles.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-126">detects the use of the `Aggregate` function in expressions in your report in order to determine whether to display server aggregates on detail rows.</span></span> <span data-ttu-id="d6bcd-127">Si incluye `Aggregate` en una expresión en una región de datos, los agregados de servidor solo podrán aparecer en las filas de total de grupo o en las filas de total general, no en las filas de detalles.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-127">If you include `Aggregate` in an expression in a data region, server aggregates can only appear on group total or grand total rows, not on detail rows.</span></span> <span data-ttu-id="d6bcd-128">Si desea mostrar los agregados de servidor en las filas de detalles, no use la función `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-128">If you want to display server aggregates on detail rows, do not use the `Aggregate` function.</span></span>  
  
 <span data-ttu-id="d6bcd-129">Para cambiar este comportamiento predeterminado, cambie el valor de la opción **Interpretar los subtotales como filas de detalles** en el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="d6bcd-129">You can change this default behavior by changing the value of the **Interpret subtotals as details** option on the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="d6bcd-130">Si esta opción se establece en `True`, todos los datos, incluidos los agregados de servidor, aparecen como datos de detalle.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-130">When this option is set to `True`, all data, including server aggregates, appears as detail data.</span></span> <span data-ttu-id="d6bcd-131">Si se establece en `False`, los agregados de servidor aparecen como totales.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-131">When set to `False`, server aggregates appear as totals.</span></span> <span data-ttu-id="d6bcd-132">El valor de esta propiedad afecta a todas las regiones de datos que están vinculadas a este conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-132">The setting for this property affects all data regions that are linked to this dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6bcd-133">Todos los grupos contenedores del elemento de informe que hacen referencia a  `Aggregate` deben incluir referencias de campo sencillas en sus expresiones de grupo; por ejemplo, `[FieldName]`.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-133">All containing groups for the report item that references `Aggregate` must have simple field references for their group expressions, for example, `[FieldName]`.</span></span> <span data-ttu-id="d6bcd-134">No puede usar `Aggregate` en una región de datos que usa expresiones de grupo complejas.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-134">You cannot use `Aggregate` in a data region that uses complex group expressions.</span></span> <span data-ttu-id="d6bcd-135">Para la extensión de procesamiento de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], la consulta debe incluir campos MDX de tipo `LevelProperty` (no `MemberProperty`) para admitir la agregación mediante la función `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-135">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data processing extension, your query must include MDX fields of type `LevelProperty` (not `MemberProperty`) to support aggregation using the `Aggregate`function.</span></span>  
  
 <span data-ttu-id="d6bcd-136">*Expression* puede contener las llamadas a las funciones de agregados anidados con las siguientes excepciones y condiciones:</span><span class="sxs-lookup"><span data-stu-id="d6bcd-136">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="d6bcd-137">*Scope* , para los agregados anidados, debe ser igual que el ámbito del agregado exterior, o ser contenido por él.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-137">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="d6bcd-138">Para todos los ámbitos distintos de la expresión, un ámbito debe estar en una relación secundaria con respecto a todos los otros ámbitos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-138">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="d6bcd-139">*Scope* , para los agregados anidados, no puede ser el nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-139">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="d6bcd-140">*Expression* no debe contener `First` `Last` `Previous` las funciones,, o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="d6bcd-140">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="d6bcd-141">*Expression* no debe contener a los agregados anidados que especifican *recursive*.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-141">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="d6bcd-142">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="d6bcd-142">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="d6bcd-143">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d6bcd-143">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="comparing-the-aggregate-and-sum-functions"></a><span data-ttu-id="d6bcd-144">Diferencias entre las funciones Aggregate y Sum</span><span class="sxs-lookup"><span data-stu-id="d6bcd-144">Comparing the Aggregate and Sum Functions</span></span>  
 <span data-ttu-id="d6bcd-145">La función `Aggregate` difiere de las funciones de agregado numéricas como `Sum` en que `Aggregate` devuelve un valor calculado por el proveedor de datos o por la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-145">The `Aggregate` function differs from numeric aggregate functions like `Sum` in that the `Aggregate` function returns a value that is calculated by the data provider or data processing extension.</span></span> <span data-ttu-id="d6bcd-146">Las funciones de agregado numéricas como `Sum` devuelven un valor calculado por el procesador de informes en un conjunto de datos del conjunto de datos determinado por el parámetro de *ámbito* .</span><span class="sxs-lookup"><span data-stu-id="d6bcd-146">Numeric aggregate functions like `Sum` return a value that is calculated by the report processor on a set of data from the dataset that is determined by the *scope* parameter.</span></span> <span data-ttu-id="d6bcd-147">Para más información, vea la lista de funciones de agregado en [Referencia a las funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d6bcd-147">For more information, see the aggregate functions listed in [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6bcd-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6bcd-148">Example</span></span>  
 <span data-ttu-id="d6bcd-149">El ejemplo de código siguiente muestra una expresión que recupera un agregado de servidor para el campo `LineTotal`.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-149">The following code example shows an expression that retrieves a server aggregate for the field `LineTotal`.</span></span> <span data-ttu-id="d6bcd-150">La expresión se agrega a una celda de una fila que pertenece al grupo `GroupbyOrder`.</span><span class="sxs-lookup"><span data-stu-id="d6bcd-150">The expression is added to a cell in a row that belongs to the group `GroupbyOrder`.</span></span>  
  
```  
=Aggregate(Fields!LineTotal.Value, "GroupbyOrder")  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6bcd-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6bcd-151">See Also</span></span>  
 <span data-ttu-id="d6bcd-152">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6bcd-152">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6bcd-153">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6bcd-153">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6bcd-154">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6bcd-154">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d6bcd-155">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d6bcd-155">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  