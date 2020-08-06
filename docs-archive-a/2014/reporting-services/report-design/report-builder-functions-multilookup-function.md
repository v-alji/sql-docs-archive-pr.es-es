---
title: Función Multilookup (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1fec079e-33b3-4e4d-92b3-6b4d06a49a77
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f2aff7a2a39e1a072cf4b05f0a04e12ced529af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672702"
---
# <a name="multilookup-function-report-builder-and-ssrs"></a><span data-ttu-id="6b4c3-102">Función Multilookup (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="6b4c3-102">Multilookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6b4c3-103">Devuelve el conjunto de valores de primera coincidencia para el conjunto especificado de nombres a partir de un conjunto de datos que contiene pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-103">Returns the set of first-match values for the specified set of names from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="6b4c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b4c3-104">Syntax</span></span>  
  
```  
  
Multilookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b4c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b4c3-105">Parameters</span></span>  
 <span data-ttu-id="6b4c3-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="6b4c3-106">*source_expression*</span></span>  
 <span data-ttu-id="6b4c3-107">(`VariantArray`) Una expresión que se evalúa en el ámbito actual y que especifica el conjunto de nombres o claves que se buscará.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-107">(`VariantArray`) An expression that is evaluated in the current scope and that specifies the set of names or keys to look up.</span></span> <span data-ttu-id="6b4c3-108">Por ejemplo, para un parámetro de varios valores, `=Parameters!IDs.value`.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-108">For example, for a multivalue parameter, `=Parameters!IDs.value`.</span></span>  
  
 <span data-ttu-id="6b4c3-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="6b4c3-109">*destination_expression*</span></span>  
 <span data-ttu-id="6b4c3-110">(`Variant`) Una expresión que se evalúa para cada fila de un conjunto de datos y que especifica el nombre o la clave que se hará coincidir.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="6b4c3-111">Por ejemplo, `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-111">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="6b4c3-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="6b4c3-112">*result_expression*</span></span>  
 <span data-ttu-id="6b4c3-113">( `Variant` ) Una expresión que se evalúa para la fila del conjunto de información donde *source_expression*  =  *destination_expression*y que especifica el valor que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="6b4c3-114">Por ejemplo, `=Fields!Name.Value`.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-114">For example, `=Fields!Name.Value`.</span></span>  
  
 <span data-ttu-id="6b4c3-115">*conjunto de datos*</span><span class="sxs-lookup"><span data-stu-id="6b4c3-115">*dataset*</span></span>  
 <span data-ttu-id="6b4c3-116">Una constante que especifica el nombre de un conjunto de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="6b4c3-117">Por ejemplo, "Colores".</span><span class="sxs-lookup"><span data-stu-id="6b4c3-117">For example, "Colors".</span></span>  
  
## <a name="return"></a><span data-ttu-id="6b4c3-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6b4c3-118">Return</span></span>  
 <span data-ttu-id="6b4c3-119">Devuelve `VariantArray` o `Nothing` si no hay ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b4c3-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b4c3-120">Remarks</span></span>  
 <span data-ttu-id="6b4c3-121">Use `Multilookup` para recuperar un conjunto de valores de un conjunto de datos para los pares de nombre-valor donde cada par tiene una relación 1 a 1.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-121">Use `Multilookup` to retrieve a set of values from a dataset for name-value pairs where each pair has a 1-to-1 relationship.</span></span> <span data-ttu-id="6b4c3-122">`MultiLookup` es equivalente de llamar `Lookup` para un conjunto de nombres o de claves.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-122">`MultiLookup` is the equivalent of calling `Lookup` for a set of names or keys.</span></span> <span data-ttu-id="6b4c3-123">Por ejemplo, para un parámetro de varios valores que se base en identificadores de clave principal, puede usar `Multilookup` en una expresión de un cuadro de texto en una tabla para recuperar los valores asociados de un conjunto de datos que no esté enlazado al parámetro ni a la tabla.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-123">For example, for a multivalue parameter that is based on primary key identifiers, you can use `Multilookup` in an expression in a text box in a table to retrieve associated values from a dataset that is not bound to the parameter or to the table.</span></span>  
  
 <span data-ttu-id="6b4c3-124">`Multilookup` realiza las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6b4c3-124">`Multilookup` does the following:</span></span>  
  
-   <span data-ttu-id="6b4c3-125">Evalúa la expresión de origen en el ámbito actual y genera una matriz de objetos de variantes.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-125">Evaluates the source expression in the current scope and generates an array of variant objects.</span></span>  
  
-   <span data-ttu-id="6b4c3-126">Para cada objeto de la matriz, llama a la [Función Lookup &#40;Generador de informes y SSRS&#41;](report-builder-functions-lookup-function.md) y agrega el resultado a la matriz de devolución.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-126">For each object in the array, calls [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md) and adds the result to the return array.</span></span>  
  
-   <span data-ttu-id="6b4c3-127">Devuelve el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-127">Returns the set of results.</span></span>  
  
 <span data-ttu-id="6b4c3-128">Para recuperar un único valor de un conjunto de datos con pares de nombre y valor para un nombre especificado donde hay una relación de uno a uno, use la [función Lookup &#40;Generador de informes y SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="6b4c3-128">To retrieve a single value from a dataset with name-value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="6b4c3-129">Para recuperar varios valores de un conjunto de datos con pares de nombre y valor para un nombre donde hay una relación de uno a varios, use la [Función LookupSet &#40;Generador de informes y SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="6b4c3-129">To retrieve multiple values from a dataset with name-value pairs for a name where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span>  
  
 <span data-ttu-id="6b4c3-130">Se aplican las restricciones que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="6b4c3-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="6b4c3-131">Se evalúa `Multilookup` después de aplicar todas las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-131">`Multilookup` is evaluated after all filter expressions are applied</span></span>  
  
-   <span data-ttu-id="6b4c3-132">Solo se admite un nivel de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-132">Only one level of look-up is supported.</span></span> <span data-ttu-id="6b4c3-133">Un origen, un destino o una expresión de resultado no pueden incluir una referencia a una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="6b4c3-134">Las expresiones de origen y de destino deben dar el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="6b4c3-135">Las expresiones de origen, destino y resultado no pueden incluir referencias a variables de informe o de grupo.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="6b4c3-136">`Multilookup` no se puede usar como una expresión para los siguientes elementos de informe:</span><span class="sxs-lookup"><span data-stu-id="6b4c3-136">`Multilookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="6b4c3-137">Cadenas de conexión dinámicas para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="6b4c3-138">Campos calculados de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="6b4c3-139">Parámetros de consulta de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="6b4c3-140">Filtros de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="6b4c3-141">Parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="6b4c3-142">La propiedad Report.Language.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="6b4c3-143">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="6b4c3-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b4c3-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b4c3-144">Example</span></span>  
 <span data-ttu-id="6b4c3-145">Suponga que un conjunto de datos denominado "Category" contiene el campo CategoryList, que es un campo que incluye una lista separada por comas de identificadores de categoría, "2, 4, 2, 1", por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-145">Assume a dataset called "Category" contains the field CategoryList, which is a field that contains a comma-separated list of category identifers, for example, "2, 4, 2, 1".</span></span>  
  
 <span data-ttu-id="6b4c3-146">El conjunto de datos CategoryNames contiene el identificador y el nombre de la categoría, tal como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-146">The dataset CategoryNames contains the category identifier and category name, as shown in the following table.</span></span>  
  
|<span data-ttu-id="6b4c3-147">id</span><span class="sxs-lookup"><span data-stu-id="6b4c3-147">ID</span></span>|<span data-ttu-id="6b4c3-148">Nombre</span><span class="sxs-lookup"><span data-stu-id="6b4c3-148">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="6b4c3-149">1</span><span class="sxs-lookup"><span data-stu-id="6b4c3-149">1</span></span>|<span data-ttu-id="6b4c3-150">Accessories</span><span class="sxs-lookup"><span data-stu-id="6b4c3-150">Accessories</span></span>|  
|<span data-ttu-id="6b4c3-151">2</span><span class="sxs-lookup"><span data-stu-id="6b4c3-151">2</span></span>|<span data-ttu-id="6b4c3-152">Bikes</span><span class="sxs-lookup"><span data-stu-id="6b4c3-152">Bikes</span></span>|  
|<span data-ttu-id="6b4c3-153">3</span><span class="sxs-lookup"><span data-stu-id="6b4c3-153">3</span></span>|<span data-ttu-id="6b4c3-154">Clothing</span><span class="sxs-lookup"><span data-stu-id="6b4c3-154">Clothing</span></span>|  
|<span data-ttu-id="6b4c3-155">4</span><span class="sxs-lookup"><span data-stu-id="6b4c3-155">4</span></span>|<span data-ttu-id="6b4c3-156">Componentes</span><span class="sxs-lookup"><span data-stu-id="6b4c3-156">Components</span></span>|  
  
 <span data-ttu-id="6b4c3-157">Para buscar los nombres que corresponden a la lista de identificadores, use `Multilookup`.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-157">To look up the names that correspond to the list of  identifiers, use `Multilookup`.</span></span> <span data-ttu-id="6b4c3-158">Primero debe dividir la lista en una matriz de cadenas, llamar a `Multilookup` para recuperar los nombres de categoría y concatenar los resultados en una cadena.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-158">You must first split the list into a string array, call `Multilookup` to retrieve the category names, and concatenate the results into a string.</span></span>  
  
 <span data-ttu-id="6b4c3-159">La expresión siguiente, cuando se coloca en un cuadro de texto en una región de datos enlazada al conjunto de datos Category, muestra "Bikes, Components, Bikes, Accessories":</span><span class="sxs-lookup"><span data-stu-id="6b4c3-159">The following expression, when placed in a text box in a data region bound to the Category dataset, displays "Bikes, Components, Bikes, Accessories":</span></span>  
  
```  
=Join(MultiLookup(Split(Fields!CategoryList.Value,","),  
   Fields!CategoryID.Value,Fields!CategoryName.Value,"Category")),  
   ", ")  
```  
  
## <a name="example"></a><span data-ttu-id="6b4c3-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b4c3-160">Example</span></span>  
 <span data-ttu-id="6b4c3-161">Suponga que un conjunto de datos ProductColors contiene un campo de identificador de color, ColorID, y un campo de valor de color, Color, tal como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-161">Assume a dataset ProductColors contains a color identifier field ColorID and a color value field Color, as shown in the following table.</span></span>  
  
|<span data-ttu-id="6b4c3-162">ColorID</span><span class="sxs-lookup"><span data-stu-id="6b4c3-162">ColorID</span></span>|<span data-ttu-id="6b4c3-163">Color</span><span class="sxs-lookup"><span data-stu-id="6b4c3-163">Color</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="6b4c3-164">1</span><span class="sxs-lookup"><span data-stu-id="6b4c3-164">1</span></span>|<span data-ttu-id="6b4c3-165">Rojo</span><span class="sxs-lookup"><span data-stu-id="6b4c3-165">Red</span></span>|  
|<span data-ttu-id="6b4c3-166">2</span><span class="sxs-lookup"><span data-stu-id="6b4c3-166">2</span></span>|<span data-ttu-id="6b4c3-167">Azul</span><span class="sxs-lookup"><span data-stu-id="6b4c3-167">Blue</span></span>|  
|<span data-ttu-id="6b4c3-168">3</span><span class="sxs-lookup"><span data-stu-id="6b4c3-168">3</span></span>|<span data-ttu-id="6b4c3-169">Verde</span><span class="sxs-lookup"><span data-stu-id="6b4c3-169">Green</span></span>|  
  
 <span data-ttu-id="6b4c3-170">Suponga que el parámetro de varios valores *MyColors* no está enlazado a un conjunto para sus valores disponibles.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-170">Assume the multivalue parameter *MyColors* is not bound to a dataset for its available values.</span></span> <span data-ttu-id="6b4c3-171">Los valores predeterminados para el parámetro están establecidos en 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="6b4c3-171">The default values for the parameter are set to 2 and 3.</span></span> <span data-ttu-id="6b4c3-172">La siguiente expresión, cuando se coloca en un cuadro de texto en una tabla, concatena múltiples valores seleccionados para el parámetro en una lista separada por comas y muestra "Blue, Green".</span><span class="sxs-lookup"><span data-stu-id="6b4c3-172">The following expression, when placed in a text box in a table, concatenates the multiple selected values for the parameter into a comma-separated list and displays "Blue, Green".</span></span>  
  
```  
=Join(MultiLookup(Parameters!MyColors.Value,Fields!ColorID.Value,Fields!Color.Value,"ProductColors"),", ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b4c3-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b4c3-173">See Also</span></span>  
 <span data-ttu-id="6b4c3-174">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6b4c3-174">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6b4c3-175">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6b4c3-175">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6b4c3-176">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6b4c3-176">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6b4c3-177">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6b4c3-177">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
