---
title: Función Lookup (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 053fefff51e4b4e338e262664bd7570280c92540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672704"
---
# <a name="lookup-function-report-builder-and-ssrs"></a><span data-ttu-id="b1e1c-102">Función Lookup (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="b1e1c-102">Lookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b1e1c-103">Devuelve el primer valor coincidente para el nombre especificado de un conjunto de datos que contiene pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-103">Returns the first matching value for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="b1e1c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1e1c-104">Syntax</span></span>  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1e1c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1e1c-105">Parameters</span></span>  
 <span data-ttu-id="b1e1c-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="b1e1c-106">*source_expression*</span></span>  
 <span data-ttu-id="b1e1c-107">(`Variant`) Una expresión que se evalúa en el ámbito actual y que especifica el nombre o la clave que se buscará.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="b1e1c-108">Por ejemplo, `=Fields!ProdID.Value`.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-108">For example, `=Fields!ProdID.Value`.</span></span>  
  
 <span data-ttu-id="b1e1c-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="b1e1c-109">*destination_expression*</span></span>  
 <span data-ttu-id="b1e1c-110">(`Variant`) Una expresión que se evalúa para cada fila de un conjunto de datos y que especifica el nombre o la clave que se hará coincidir.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="b1e1c-111">Por ejemplo, `=Fields!ProductID.Value`.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-111">For example, `=Fields!ProductID.Value`.</span></span>  
  
 <span data-ttu-id="b1e1c-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="b1e1c-112">*result_expression*</span></span>  
 <span data-ttu-id="b1e1c-113">( `Variant` ) Una expresión que se evalúa para la fila del conjunto de información donde *source_expression*  =  *destination_expression*y que especifica el valor que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="b1e1c-114">Por ejemplo, `=Fields!ProductName.Value`.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-114">For example, `=Fields!ProductName.Value`.</span></span>  
  
 <span data-ttu-id="b1e1c-115">*conjunto de datos*</span><span class="sxs-lookup"><span data-stu-id="b1e1c-115">*dataset*</span></span>  
 <span data-ttu-id="b1e1c-116">Una constante que especifica el nombre de un conjunto de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="b1e1c-117">Por ejemplo, "Productos".</span><span class="sxs-lookup"><span data-stu-id="b1e1c-117">For example, "Products".</span></span>  
  
## <a name="return"></a><span data-ttu-id="b1e1c-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1e1c-118">Return</span></span>  
 <span data-ttu-id="b1e1c-119">Devuelve `Variant` o `Nothing` si no hay ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-119">Returns a `Variant`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1e1c-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b1e1c-120">Remarks</span></span>  
 <span data-ttu-id="b1e1c-121">Use `Lookup` para recuperar el valor del conjunto de datos especificado correspondiente a un par nombre/valor donde hay una relación de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-121">Use `Lookup` to retrieve the value from the specified dataset for a name/value pair where there is a 1-to-1 relationship.</span></span> <span data-ttu-id="b1e1c-122">Por ejemplo, para un campo de identificador, puede usar `Lookup` para recuperar el campo Name correspondiente de un conjunto de datos que no está enlazado a la región de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-122">For example, for an ID field in a table, you can use `Lookup` to retrieve the corresponding Name field from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="b1e1c-123">`Lookup` realiza las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1e1c-123">`Lookup` does the following:</span></span>  
  
-   <span data-ttu-id="b1e1c-124">Evalúa la expresión de origen en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="b1e1c-125">Evalúa la expresión de destino para cada fila del conjunto de datos especificado una vez aplicados los filtros, según la intercalación del conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="b1e1c-126">En la primera coincidencia de las expresiones de origen y de destino, evalúa la expresión de resultado para dicha fila del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-126">On the first match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="b1e1c-127">Devuelve el valor de la expresión de resultado.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-127">Returns the result expression value.</span></span>  
  
 <span data-ttu-id="b1e1c-128">Para recuperar varios valores para un único nombre o campo de clave donde hay una relación de uno a varios, use la [función LookupSet &#40;Generador de informes y SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="b1e1c-128">To retrieve multiple values for a single name or key field where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span> <span data-ttu-id="b1e1c-129">Para llamar a `Lookup` para un conjunto de valores, utilice la [función de multibúsqueda &#40;generador de informes y SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="b1e1c-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span>  
  
 <span data-ttu-id="b1e1c-130">Se aplican las restricciones que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="b1e1c-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="b1e1c-131">`Lookup`se evalúa después de aplicar todas las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-131">`Lookup` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="b1e1c-132">Solo se admite un nivel de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="b1e1c-133">Un origen, un destino o una expresión de resultado no pueden incluir una referencia a una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="b1e1c-134">Las expresiones de origen y de destino deben dar el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-134">Source and destination expressions must evaluate to the same data type.</span></span> <span data-ttu-id="b1e1c-135">El tipo de devolución es el mismo que el tipo de datos de la expresión de resultado evaluada.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-135">The return type is the same as the data type of the evaluated result expression.</span></span>  
  
-   <span data-ttu-id="b1e1c-136">Las expresiones de origen, destino y resultado no pueden incluir referencias a variables de informe o de grupo.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-136">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="b1e1c-137">`Lookup` no se puede usar como una expresión para los siguientes elementos de informe:</span><span class="sxs-lookup"><span data-stu-id="b1e1c-137">`Lookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="b1e1c-138">Cadenas de conexión dinámicas para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-138">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="b1e1c-139">Campos calculados de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-139">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="b1e1c-140">Parámetros de consulta de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-140">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="b1e1c-141">Filtros de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-141">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="b1e1c-142">Parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-142">Report parameters.</span></span>  
  
    -   <span data-ttu-id="b1e1c-143">La propiedad Report.Language.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-143">The Report.Language property.</span></span>  
  
 <span data-ttu-id="b1e1c-144">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="b1e1c-144">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1e1c-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1e1c-145">Example</span></span>  
 <span data-ttu-id="b1e1c-146">En el ejemplo siguiente, se supone que una tabla está enlazada a un conjunto de datos que incluye un campo para el identificador de producto ProductID.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-146">In the following example, assume that a table is bound to a dataset that includes a field for the product identifier ProductID.</span></span> <span data-ttu-id="b1e1c-147">Un conjunto de datos independiente denominado "Product" contiene el identificador de producto, ID, y el nombre de producto, Name.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-147">A separate dataset called "Product" contains the corresponding product identifier ID and the product name Name.</span></span>  
  
 <span data-ttu-id="b1e1c-148">En la expresión siguiente, `Lookup` compara el valor de ProductID con ID en cada fila del conjunto de datos denominado "Product" y, cuando se encuentra una coincidencia, devuelve el valor del campo Name para dicha fila.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-148">In the following expression, `Lookup` compares the value of ProductID to ID in each row of the dataset called "Product" and, when a match is found, returns the value of the Name field for that row.</span></span>  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1e1c-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1e1c-149">See Also</span></span>  
 <span data-ttu-id="b1e1c-150">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b1e1c-150">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b1e1c-151">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b1e1c-151">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b1e1c-152">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b1e1c-152">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b1e1c-153">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b1e1c-153">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
