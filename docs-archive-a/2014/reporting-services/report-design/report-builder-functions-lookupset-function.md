---
title: Función LookupSet (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7685acfd-1c8d-420c-993c-903236fbe1ff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4edc7a17f2aa3813e8aa73e538594b5df3aeabc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672707"
---
# <a name="lookupset-function-report-builder-and-ssrs"></a><span data-ttu-id="cca42-102">Función LookupSet (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="cca42-102">LookupSet Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cca42-103">Devuelve el conjunto de valores coincidentes para el nombre especificado de un conjunto de datos que contiene pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="cca42-103">Returns the set of matching values for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="cca42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cca42-104">Syntax</span></span>  
  
```  
  
LookupSet(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cca42-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cca42-105">Parameters</span></span>  
 <span data-ttu-id="cca42-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="cca42-106">*source_expression*</span></span>  
 <span data-ttu-id="cca42-107">(`Variant`) Una expresión que se evalúa en el ámbito actual y que especifica el nombre o la clave que se buscará.</span><span class="sxs-lookup"><span data-stu-id="cca42-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="cca42-108">Por ejemplo, `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="cca42-108">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="cca42-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="cca42-109">*destination_expression*</span></span>  
 <span data-ttu-id="cca42-110">(`Variant`) Una expresión que se evalúa para cada fila de un conjunto de datos y que especifica el nombre o la clave que se hará coincidir.</span><span class="sxs-lookup"><span data-stu-id="cca42-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="cca42-111">Por ejemplo, `=Fields!CustomerID.Value`.</span><span class="sxs-lookup"><span data-stu-id="cca42-111">For example, `=Fields!CustomerID.Value`.</span></span>  
  
 <span data-ttu-id="cca42-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="cca42-112">*result_expression*</span></span>  
 <span data-ttu-id="cca42-113">( `Variant` ) Una expresión que se evalúa para la fila del conjunto de información donde *source_expression*  =  *destination_expression*y que especifica el valor que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="cca42-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="cca42-114">Por ejemplo, `=Fields!PhoneNumber.Value`.</span><span class="sxs-lookup"><span data-stu-id="cca42-114">For example, `=Fields!PhoneNumber.Value`.</span></span>  
  
 <span data-ttu-id="cca42-115">*conjunto de datos*</span><span class="sxs-lookup"><span data-stu-id="cca42-115">*dataset*</span></span>  
 <span data-ttu-id="cca42-116">Una constante que especifica el nombre de un conjunto de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="cca42-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="cca42-117">Por ejemplo, "ContactInformation".</span><span class="sxs-lookup"><span data-stu-id="cca42-117">For example, "ContactInformation".</span></span>  
  
## <a name="return"></a><span data-ttu-id="cca42-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cca42-118">Return</span></span>  
 <span data-ttu-id="cca42-119">Devuelve `VariantArray` o `Nothing` si no hay ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="cca42-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cca42-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cca42-120">Remarks</span></span>  
 <span data-ttu-id="cca42-121">Use `LookupSet` para recuperar un conjunto de valores del conjunto de datos especificado correspondiente a un par de nombre/valor donde hay una relación de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="cca42-121">Use `LookupSet` to retrieve a set of values from the specified dataset for a name/value pair where there is a 1-to-many relationship.</span></span> <span data-ttu-id="cca42-122">Por ejemplo, para un identificador de cliente en una tabla, puede usar `LookupSet` para recuperar todos los números de teléfono asociados a ese cliente de un conjunto de datos que no está enlazado a la región de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-122">For example, for a customer identifier in a table, you can use `LookupSet` to retrieve all the associated phone numbers for that customer from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="cca42-123">`LookupSet` realiza las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cca42-123">`LookupSet` does the following:</span></span>  
  
-   <span data-ttu-id="cca42-124">Evalúa la expresión de origen en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="cca42-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="cca42-125">Evalúa la expresión de destino para cada fila del conjunto de datos especificado una vez aplicados los filtros, según la intercalación del conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="cca42-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="cca42-126">Por cada coincidencia de las expresiones de origen y de destino, evalúa la expresión de resultado para dicha fila del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-126">For each match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="cca42-127">Devuelve el conjunto de valores de expresión de resultado.</span><span class="sxs-lookup"><span data-stu-id="cca42-127">Returns the set of result expression values.</span></span>  
  
 <span data-ttu-id="cca42-128">Para recuperar un único valor de un conjunto de datos con pares nombre-valor para un nombre especificado donde hay una relación de uno a uno, use la [función Lookup &#40;Generador de informes y SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="cca42-128">To retrieve a single value from a dataset with name/value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="cca42-129">Para llamar a `Lookup` para un conjunto de valores, utilice la [función de multibúsqueda &#40;generador de informes y SSRS&#41;](report-builder-functions-multilookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="cca42-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-multilookup-function.md).</span></span>  
  
 <span data-ttu-id="cca42-130">Se aplican las restricciones que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="cca42-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="cca42-131">`LookupSet`se evalúa después de aplicar todas las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="cca42-131">`LookupSet` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="cca42-132">Solo se admite un nivel de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cca42-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="cca42-133">Un origen, un destino o una expresión de resultado no pueden incluir una referencia a una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cca42-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="cca42-134">Las expresiones de origen y de destino deben dar el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="cca42-135">Las expresiones de origen, destino y resultado no pueden incluir referencias a variables de informe o de grupo.</span><span class="sxs-lookup"><span data-stu-id="cca42-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="cca42-136">`LookupSet` no se puede usar como una expresión para los siguientes elementos de informe:</span><span class="sxs-lookup"><span data-stu-id="cca42-136">`LookupSet` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="cca42-137">Cadenas de conexión dinámicas para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="cca42-138">Campos calculados de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="cca42-139">Parámetros de consulta de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="cca42-140">Filtros de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="cca42-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="cca42-141">Parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="cca42-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="cca42-142">La propiedad Report.Language.</span><span class="sxs-lookup"><span data-stu-id="cca42-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="cca42-143">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="cca42-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca42-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cca42-144">Example</span></span>  
 <span data-ttu-id="cca42-145">En el siguiente ejemplo se supone que la tabla está enlazada a un conjunto de datos que incluye un identificador de territorio de ventas, TerritoryGroupID.</span><span class="sxs-lookup"><span data-stu-id="cca42-145">In the following example, assume the table is bound to a dataset that includes a sales territory identifier TerritoryGroupID.</span></span> <span data-ttu-id="cca42-146">Un conjunto de datos independiente denominado "Stores" contiene la lista de todas las tiendas de un territorio e incluye el identificador de territorio, ID, y el nombre de la tienda, StoreName.</span><span class="sxs-lookup"><span data-stu-id="cca42-146">A separate dataset called "Stores" contains the list of all stores in a territory and includes the territory identifier ID and the name of the store StoreName.</span></span>  
  
 <span data-ttu-id="cca42-147">En la siguiente expresión, `LookupSet` compara el valor TerritoryGroupID con ID por cada fila del conjunto de datos denominado "Stores".</span><span class="sxs-lookup"><span data-stu-id="cca42-147">In the following expression, `LookupSet` compares the value TerritoryGroupID to ID for each row in the dataset called "Stores".</span></span> <span data-ttu-id="cca42-148">Por cada coincidencia, el valor del campo StoreName de dicha fila se agrega al conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="cca42-148">For each match, the value of the StoreName field for that row is added to the result set.</span></span>  
  
```  
=LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores")  
```  
  
## <a name="example"></a><span data-ttu-id="cca42-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cca42-149">Example</span></span>  
 <span data-ttu-id="cca42-150">Dado que `LookupSet` devuelve una colección de objetos, no se puede mostrar la expresión de resultado directamente en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="cca42-150">Because `LookupSet` returns a collection of objects, you cannot display the result expression directly in a text box.</span></span> <span data-ttu-id="cca42-151">Puede concatenar el valor de cada objeto de la colección como una cadena.</span><span class="sxs-lookup"><span data-stu-id="cca42-151">You can concatenate the value of each object in the collection as a string.</span></span>  
  
 <span data-ttu-id="cca42-152">Use la función `Join` de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para crear una cadena delimitada a partir de un conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="cca42-152">Use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] function `Join` create a delimited string from a set of objects.</span></span> <span data-ttu-id="cca42-153">Use la coma como separador para combinar los objetos en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="cca42-153">Use a comma as a separator to combine the objects in a single line.</span></span> <span data-ttu-id="cca42-154">En algunos representadores, puede usar un salto de línea de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] (`vbCrLF`) como separador para enumerar cada valor en una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="cca42-154">In some renderers, you might use a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] line feed (`vbCrLF`) as a separator to list each value on a new line.</span></span>  
  
 <span data-ttu-id="cca42-155">La siguiente expresión, cuando se usa como la propiedad Value de un cuadro de texto, utiliza `Join` para crear una lista.</span><span class="sxs-lookup"><span data-stu-id="cca42-155">The following expression, when it is used as the Value property for a text box, uses `Join` to create a list.</span></span>  
  
```  
=Join(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"),",")  
```  
  
## <a name="example"></a><span data-ttu-id="cca42-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cca42-156">Example</span></span>  
 <span data-ttu-id="cca42-157">Para los cuadros de texto que solo se representan pocas veces, puede agregar código personalizado para generar el código HTML para mostrar valores en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="cca42-157">For text boxes that only render a few times, you might choose to add custom code to generate HTML to display values in a text box.</span></span> <span data-ttu-id="cca42-158">El código HTML en un cuadro de texto requiere procesamiento adicional, por lo que no es una buena opción para un cuadro de texto que se representa miles de veces.</span><span class="sxs-lookup"><span data-stu-id="cca42-158">HTML in a text box requires extra processing, so this would not be a good choice for a text box that is rendered thousands of times.</span></span>  
  
 <span data-ttu-id="cca42-159">Copie las siguientes funciones de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] en un bloque Code en una definición de informe.</span><span class="sxs-lookup"><span data-stu-id="cca42-159">Copy the following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to a Code block in a report definition.</span></span> <span data-ttu-id="cca42-160">**MakeList** toma la matriz de objetos que se devuelve en *result_expression* y genera una lista no ordenada mediante etiquetas HTML.</span><span class="sxs-lookup"><span data-stu-id="cca42-160">**MakeList** takes the object array that is returned in *result_expression* and builds an unordered list by using HTML tags.</span></span> <span data-ttu-id="cca42-161">**Length** devuelve el número de elementos en la matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="cca42-161">**Length** returns the number of items in the object array.</span></span>  
  
```  
Function MakeList(ByVal items As Object()) As String  
   If items Is Nothing Then  
      Return Nothing  
   End If  
  
   Dim builder As System.Text.StringBuilder =   
      New System.Text.StringBuilder()  
   builder.Append("<ul>")  
  
   For Each item As Object In items  
      builder.Append("<li>")  
      builder.Append(item)  
   Next  
   builder.Append("</ul>")  
  
   Return builder.ToString()  
End Function  
  
Function Length(ByVal items as Object()) as Integer  
   If items is Nothing Then  
      Return 0  
   End If  
   Return items.Length  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="cca42-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cca42-162">Example</span></span>  
 <span data-ttu-id="cca42-163">Para generar el código HTML, debe llamar a la función.</span><span class="sxs-lookup"><span data-stu-id="cca42-163">To generate the HTML, you must call the function.</span></span> <span data-ttu-id="cca42-164">Pegue la siguiente expresión en la propiedad Value del cuadro de texto y establezca el tipo de marcado del texto en HTML.</span><span class="sxs-lookup"><span data-stu-id="cca42-164">Paste the following expression in the Value property for the text box and set the markup type for text to HTML.</span></span> <span data-ttu-id="cca42-165">Para más información, vea [Agregar HTML a un informe &#40;Generador de informes y SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cca42-165">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
```  
=Code.MakeList(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca42-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cca42-166">See Also</span></span>  
 <span data-ttu-id="cca42-167">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cca42-167">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cca42-168">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cca42-168">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cca42-169">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cca42-169">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cca42-170">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cca42-170">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
