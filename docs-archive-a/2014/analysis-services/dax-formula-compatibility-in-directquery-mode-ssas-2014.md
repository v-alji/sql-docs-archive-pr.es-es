---
title: Compatibilidad de las fórmulas DAX en el modo DirectQuery (SSAS 2014) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: de83cfa9-9ffe-4e24-9c74-96a3876cb4bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: acaac82d6930787a45281c0e942def8df764f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671813"
---
# <a name="dax-formula-compatibility-in-directquery-mode-ssas-2014"></a><span data-ttu-id="cc9af-102">Compatibilidad de fórmulas DAX en el modo DirectQuery (SSAS 2014)</span><span class="sxs-lookup"><span data-stu-id="cc9af-102">DAX Formula Compatibility in DirectQuery Mode (SSAS 2014)</span></span>
<span data-ttu-id="cc9af-103">El lenguaje de expresiones de análisis de datos (DAX) se puede usar para crear medidas y otras fórmulas personalizadas para usarlas en Analysis Services modelos tabulares, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelos de datos en libros de Excel y Power BI Desktop modelos de datos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-103">The Data Analysis Expression language (DAX) can be used to create measures and other custom formulas for use in Analysis Services Tabular models, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data models in Excel workbooks, and Power BI Desktop data models.</span></span> <span data-ttu-id="cc9af-104">En la mayoría de los casos, los modelos que se crean en estos entornos son idénticos, y puede usar las mismas medidas, relaciones y KPI, etc. Sin embargo, si crea un modelo tabular de Analysis Services e lo implementa en el modo DirectQuery, existen algunas restricciones en las fórmulas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="cc9af-104">In most respects, the models you create in these environments are identical, and you can use the same measures, relationships, and KPIs, etc. However, if you author an Analysis Services Tabular model and deploy it in DirectQuery mode, there are some restrictions on the formulas that you can use.</span></span> <span data-ttu-id="cc9af-105">En este tema se proporciona información general sobre estas diferencias, se enumeran las funciones que no se admiten en SQL Server 2014 Analysis Services modelo tabulares en el nivel de compatibilidad 1100 o 1103 y en el modo DirectQuery, y se enumeran las funciones que se admiten, pero que pueden devolver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-105">This topic provides an overview of those differences, lists the functions that are not supported in SQL Server 2014 Analysis Services tabulars model at compatibility level 1100 or 1103 and in DirectQuery mode, and lists the functions that are supported but might return different results.</span></span>  
  
<span data-ttu-id="cc9af-106">En este tema, usamos el término *modelo en memoria* para hacer referencia a los modelos tabulares, que son datos almacenados en memoria caché totalmente hospedados en un servidor Analysis Services que se ejecuta en modo tabular.</span><span class="sxs-lookup"><span data-stu-id="cc9af-106">Within this topic, we use the term *in-memory model* to refer to  Tabular models, which are fully hosted in-memory cached data on an Analysis Services server running in Tabular mode.</span></span> <span data-ttu-id="cc9af-107">Usamos *modelos de directquery* para hacer referencia a los modelos tabulares que se han creado o implementado en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-107">We use *DirectQuery models* to refer to Tabular models that have been authored and/or deployed in DirectQuery mode.</span></span> <span data-ttu-id="cc9af-108">Para obtener información sobre el modo DirectQuery, vea [modo directquery (SSAS tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span><span class="sxs-lookup"><span data-stu-id="cc9af-108">For information about DirectQuery mode, see [DirectQuery Mode (SSAS Tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span></span>  
  
  
## <a name="differences-between-in-memory-and-directquery-mode"></a><a name="bkmk_SemanticDifferences"></a><span data-ttu-id="cc9af-109">Diferencias entre el modo en memoria y el modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="cc9af-109">Differences between in-memory and DirectQuery mode</span></span>  
<span data-ttu-id="cc9af-110">Las consultas en un modelo implementado en el modo DirectQuery pueden devolver unos resultados distintos a los que devolvería el mismo modelo implementado en el modo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-110">Queries on a model deployed in DirectQuery mode can return different results than the same model deployed in in-memory mode.</span></span> <span data-ttu-id="cc9af-111">Esto se debe a que con DirectQuery, los datos se consultan directamente desde un almacén de datos relacional y las agregaciones necesarias para las fórmulas se realizan mediante el motor relacional correspondiente, en lugar de usar el motor analítico en memoria xVelocity (VertiPaq) para el almacenamiento y el cálculo.</span><span class="sxs-lookup"><span data-stu-id="cc9af-111">This is because with DirectQuery, data is queried directly from a relational data store and aggregations required by formulas are performed using the relevant relational engine, rather than using the xVelocity in-memory analytics engine (VertiPaq) for storage and calculation.</span></span>  
  
<span data-ttu-id="cc9af-112">Por ejemplo, existen diferencias en la manera en la que determinados almacenes de datos relacionales procesan los valores numéricos, las fechas, los valores NULL, etc.</span><span class="sxs-lookup"><span data-stu-id="cc9af-112">For example, there are differences in the way that certain relational data stores handle numeric values, dates, nulls, and so forth.</span></span>  
  
<span data-ttu-id="cc9af-113">En cambio, el lenguaje DAX intenta emular con la mayor fidelidad posible el comportamiento de las funciones de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="cc9af-113">In contrast, the DAX language is intended to emulate as closely as possible the behavior of functions in Microsoft Excel.</span></span> <span data-ttu-id="cc9af-114">Por ejemplo, al procesar los valores NULL, las cadenas vacías y los valores cero, Excel intenta proporcionar la mejor respuesta independientemente del tipo de datos preciso y, por lo tanto, el motor xVelocity actúa de igual manera.</span><span class="sxs-lookup"><span data-stu-id="cc9af-114">For example, when handling nulls, empty strings and zero values, Excel attempts to provide the best answer regardless of the precise data type, and therefore the xVelocity engine does the same.</span></span> <span data-ttu-id="cc9af-115">Sin embargo, cuando se implementa un modelo tabular en el modo DirectQuery y dicho modelo pasa fórmulas a un origen de datos relacional para su evaluación, los datos se deben procesar de acuerdo con la semántica del origen de datos relacional, que normalmente requiere un tratamiento distinto de las cadenas vacías frente a nulas.</span><span class="sxs-lookup"><span data-stu-id="cc9af-115">However, when a tabular model is deployed in DirectQuery mode and passes formulas to a relational data source for evaluation, the data must be handled according to the semantics of the relational data source, which typically require distinct handling of empty strings vs. nulls.</span></span> <span data-ttu-id="cc9af-116">Por este motivo, la misma fórmula puede devolver resultados diferentes cuando se evalúa con los datos en caché y con los datos obtenidos exclusivamente del almacén relacional.</span><span class="sxs-lookup"><span data-stu-id="cc9af-116">For this reason, the same formula might return a different result when evaluated against cached data and against data returned solely from the relational store.</span></span>  
  
<span data-ttu-id="cc9af-117">Además, algunas funciones no se pueden usar en el modo DirectQuery porque el cálculo requeriría que los datos del contexto actual se envíen al origen de datos relacional como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="cc9af-117">Additionally, some functions cannot be used at all in DirectQuery mode because the calculation would require the data in the current context be sent to the relational data source as a parameter.</span></span> <span data-ttu-id="cc9af-118">Por ejemplo, las medidas de un [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] libro a menudo usan funciones de inteligencia de tiempo que hacen referencia a intervalos de fechas disponibles en el libro.</span><span class="sxs-lookup"><span data-stu-id="cc9af-118">For example, measures in a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook often use time-intelligence functions that reference date ranges available within the workbook.</span></span> <span data-ttu-id="cc9af-119">Normalmente, estas fórmulas no se pueden utilizar en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-119">Such formulas generally cannot be used in DirectQuery mode.</span></span>  
  
## <a name="semantic-differences"></a><span data-ttu-id="cc9af-120">Diferencias semánticas</span><span class="sxs-lookup"><span data-stu-id="cc9af-120">Semantic differences</span></span>  
<span data-ttu-id="cc9af-121">En esta sección se enumeran los tipos de diferencias semánticas que puede encontrar, y se describen las limitaciones que se pueden aplicar al uso de las funciones o a los resultados de las consultas.</span><span class="sxs-lookup"><span data-stu-id="cc9af-121">This section lists the types of semantic differences that you can expect, and describes any limitations that might apply to the usage of functions or to query results.</span></span>  
  
### <a name="comparisons"></a><a name="bkmk_Comparisons"></a><span data-ttu-id="cc9af-122">Comparaciones</span><span class="sxs-lookup"><span data-stu-id="cc9af-122">Comparisons</span></span>  
<span data-ttu-id="cc9af-123">En los modelos en memoria, DAX admite comparaciones de dos expresiones que dan como resultado valores escalares de tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-123">DAX in in-memory models support comparisons of two expressions that resolve to scalar values of different data types.</span></span> <span data-ttu-id="cc9af-124">Sin embargo, los modelos que se implementan en el modo DirectQuery utilizan los tipos de datos y los operadores de comparación del motor relacional y, por lo tanto, pueden devolver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-124">However, models that are deployed in DirectQuery mode use the data types and comparison operators of the relational engine, and therefore might return different results.</span></span>  
  
<span data-ttu-id="cc9af-125">Las siguientes comparaciones siempre devolverán un error si se usan en cálculos en un origen de datos DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="cc9af-125">The following comparisons will always return an error when used in a calculation on a DirectQuery data source:</span></span>  
  
-   <span data-ttu-id="cc9af-126">Tipo de datos numérico comparado con cualquier tipo de datos de cadena</span><span class="sxs-lookup"><span data-stu-id="cc9af-126">Numeric data type compared to any string data type</span></span>  
  
-   <span data-ttu-id="cc9af-127">Tipo de datos numérico comparado con un valor booleano</span><span class="sxs-lookup"><span data-stu-id="cc9af-127">Numeric data type compared to a Boolean value</span></span>  
  
-   <span data-ttu-id="cc9af-128">Cualquier tipo de datos de cadena comparado con un valor booleano</span><span class="sxs-lookup"><span data-stu-id="cc9af-128">Any string data type compared to a Boolean value</span></span>  
  
<span data-ttu-id="cc9af-129">En general, DAX es más permisivo con los errores de tipo de datos en los modelos en memoria, e intentará realizar una conversión implícita de valores un máximo de dos veces, tal y como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="cc9af-129">In general, DAX is more forgiving of data type mismatches in in-memory models and will attempt an implicit cast of values up to two times, as described in this section.</span></span> <span data-ttu-id="cc9af-130">Sin embargo, las fórmulas que se envían a un almacén de datos relacional en el modo DirectQuery se evalúan de forma más estricta, siguiendo las reglas del motor relacional, y es más probable que generen errores.</span><span class="sxs-lookup"><span data-stu-id="cc9af-130">However, formulas sent to a relational data store in DirectQuery mode are evaluated more strictly, following the rules of the relational engine, and are more likely to fail.</span></span>  
  
<span data-ttu-id="cc9af-131">**Comparaciones de cadenas y números**</span><span class="sxs-lookup"><span data-stu-id="cc9af-131">**Comparisons of strings and numbers**</span></span>  
<span data-ttu-id="cc9af-132">EJEMPLO: `"2" < 3`</span><span class="sxs-lookup"><span data-stu-id="cc9af-132">EXAMPLE: `"2" < 3`</span></span>  
  
<span data-ttu-id="cc9af-133">La fórmula compara una cadena de texto con un número.</span><span class="sxs-lookup"><span data-stu-id="cc9af-133">The formula compares a text string to a number.</span></span> <span data-ttu-id="cc9af-134">La expresión es **true** tanto en el modo DirectQuery como en los modelos en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-134">The expression is **true** in both DirectQuery mode and in-memory models.</span></span>  
  
<span data-ttu-id="cc9af-135">En un modelo en memoria, el resultado es **true** porque los números especificados como cadenas se convierten implícitamente en un tipo de datos numérico con el fin de realizar comparaciones con otros números.</span><span class="sxs-lookup"><span data-stu-id="cc9af-135">In an in-memory model, the result is **true** because numbers as strings are implicitly cast to a numerical data type for comparisons with other numbers.</span></span> <span data-ttu-id="cc9af-136">SQL también convierte implícitamente números de texto en números para realizar comparaciones con tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-136">SQL also implicitly casts text numbers as numbers for comparison to numerical data types.</span></span>  
  
<span data-ttu-id="cc9af-137">Tenga en cuenta que esto representa un cambio de comportamiento de la primera versión de [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , que devolvería **false**, ya que el texto "2" se consideraría siempre mayor que cualquier número.</span><span class="sxs-lookup"><span data-stu-id="cc9af-137">Note that this represents a change in behavior from the first version of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)], which would return **false**, because the text "2" would always be considered larger than any number.</span></span>  
  
<span data-ttu-id="cc9af-138">**Comparación de cadenas de texto con valores booleanos**</span><span class="sxs-lookup"><span data-stu-id="cc9af-138">**Comparison of text with Boolean**</span></span>  
<span data-ttu-id="cc9af-139">EJEMPLO: `"VERDADERO" = TRUE`</span><span class="sxs-lookup"><span data-stu-id="cc9af-139">EXAMPLE: `"VERDADERO" = TRUE`</span></span>  
  
<span data-ttu-id="cc9af-140">Esta expresión compara una cadena de texto con un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="cc9af-140">This expression compares a text string with a Boolean value.</span></span> <span data-ttu-id="cc9af-141">En general, en los modelos en memoria o DirectQuery, la comparación de un valor de cadena con un valor booleano genera un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-141">In general, for DirectQuery or In-Memory models, comparing a string value to a Boolean value results in an error.</span></span> <span data-ttu-id="cc9af-142">Las únicas excepciones a esta regla se producen cuando la cadena contiene las palabras **true** o **false**; si la cadena contiene un valor true o false, se realiza una conversión a un valor booleano y se lleva a cabo la comparación proporcionando el resultado lógico.</span><span class="sxs-lookup"><span data-stu-id="cc9af-142">The only exceptions to the rule are when the string contains the word **true** or the word **false**; if the string contains any of true or false values, a conversion to Boolean is made and the comparison takes place giving the logical result.</span></span>  
  
<span data-ttu-id="cc9af-143">**Comparación de valores NULL**</span><span class="sxs-lookup"><span data-stu-id="cc9af-143">**Comparison of nulls**</span></span>  
<span data-ttu-id="cc9af-144">EJEMPLO: `EVALUATE ROW("X", BLANK() = BLANK())`</span><span class="sxs-lookup"><span data-stu-id="cc9af-144">EXAMPLE: `EVALUATE ROW("X", BLANK() = BLANK())`</span></span>  
  
<span data-ttu-id="cc9af-145">Esta fórmula compara el equivalente a un valor NULL en SQL con un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-145">This formula compares the SQL equivalent of a null to a null.</span></span> <span data-ttu-id="cc9af-146">Devuelve **true** en los modelos en memoria y DirectQuery; en el modelo DirectQuery, se realiza una previsión que garantiza un comportamiento similar al del modelo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-146">It returns **true** in in-memory and DirectQuery models; a provision is made in DirectQuery model to guarantee similar behavior to in-memory model.</span></span>  
  
<span data-ttu-id="cc9af-147">Tenga en cuenta que en Transact-SQL, un valor NULL nunca es igual a otro valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-147">Note that in Transact-SQL, a null is never equal to a null.</span></span> <span data-ttu-id="cc9af-148">Sin embargo, en DAX, un espacio en blanco es igual a otro espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="cc9af-148">However, in DAX, a blank is equal to another blank.</span></span> <span data-ttu-id="cc9af-149">Este comportamiento es el mismo para todos los modelos en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-149">This behavior is the same for all in-memory models.</span></span> <span data-ttu-id="cc9af-150">Es importante destacar que el modo DirectQuery utiliza generalmente la semántica de SQL Server; pero en este caso no lo hace, proporcionando un nuevo comportamiento para las comparaciones de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-150">It is important to note that DirectQuery mode uses, most of, the semantics of SQL Server; but, in this case it separates from it giving a new behavior to NULL comparisons.</span></span>  
  
### <a name="casts"></a><a name="bkmk_Casts"></a><span data-ttu-id="cc9af-151">Conversiones</span><span class="sxs-lookup"><span data-stu-id="cc9af-151">Casts</span></span>  
  
<span data-ttu-id="cc9af-152">No hay ninguna función de conversión como tal en DAX, pero las conversiones implícitas se realizan en muchas operaciones aritméticas y de comparación.</span><span class="sxs-lookup"><span data-stu-id="cc9af-152">There is no cast function as such in DAX, but implicit casts are performed in many comparison and arithmetic operations.</span></span> <span data-ttu-id="cc9af-153">Es la operación aritmética o de comparación la que determina el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="cc9af-153">It is the comparison or arithmetic operation that determines the data type of the result.</span></span> <span data-ttu-id="cc9af-154">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="cc9af-154">For example,</span></span>  
  
-   <span data-ttu-id="cc9af-155">Los valores booleanos se tratan como numéricos en las operaciones aritméticas, como TRUE + 1, o la función MIN aplicada a una columna de valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-155">Boolean values are treated as numeric in arithmetic operations, such as TRUE + 1, or the function MIN applied to a column of Boolean values.</span></span> <span data-ttu-id="cc9af-156">Una operación NOT también devuelve un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="cc9af-156">A NOT operation also returns a numeric value.</span></span>  
  
-   <span data-ttu-id="cc9af-157">Los valores booleanos siempre se tratan como valores lógicos en las comparaciones y cuando se usan con EXACT, AND, OR, &amp;&amp;o ||.</span><span class="sxs-lookup"><span data-stu-id="cc9af-157">Boolean values are always treated as logical values in comparisons and when used with EXACT, AND, OR, &amp;&amp;, or ||.</span></span>  
  
<span data-ttu-id="cc9af-158">**Conversión de valores de cadena en valores booleanos**</span><span class="sxs-lookup"><span data-stu-id="cc9af-158">**Cast from string to Boolean**</span></span>  
<span data-ttu-id="cc9af-159">En los modelos en memoria y DirectQuery, solo se permiten las conversiones de valores booleanos de estas cadenas: **""** (cadena vacía), **"true"**, **"false"**; donde una cadena vacía se convierte en un valor false.</span><span class="sxs-lookup"><span data-stu-id="cc9af-159">In in-memory and DirectQuery models, casts are permitted to Boolean values from these strings only: **""** (empty string), **"true"**, **"false"**; where an empty string casts to false value.</span></span>  
  
<span data-ttu-id="cc9af-160">Las conversiones de cualquier otra cadena al tipo de datos booleano producirán un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-160">Casts to the Boolean data type of any other string results in an error.</span></span>  
  
<span data-ttu-id="cc9af-161">**Conversión de valores de cadena en valores de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="cc9af-161">**Cast from string to date/time**</span></span>  
<span data-ttu-id="cc9af-162">En el modo DirectQuery, las conversiones de representaciones de cadena de fechas y horas en valores **datetime** reales se comportan de la misma manera que en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc9af-162">In DirectQuery mode, casts from string representations of dates and times to actual **datetime** values behave the same way as they do in SQL Server.</span></span>  
  
<span data-ttu-id="cc9af-163">Para obtener información sobre las reglas que rigen las conversiones de tipos de datos de cadena a **DateTime** en [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelos, vea la [referencia de sintaxis de Dax](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="cc9af-163">For information about the rules governing casts from string to **datetime** data types in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, see the [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="cc9af-164">Los modelos que utilizan el almacén de datos en memoria admiten una gama más limitada de formatos de texto para fechas que los formatos de cadena para fechas que admite SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc9af-164">Models that use the in-memory data store support a more limited range of text formats for dates than the string formats for dates that are supported by SQL Server.</span></span> <span data-ttu-id="cc9af-165">Sin embargo, DAX admite formatos de fecha y hora personalizados.</span><span class="sxs-lookup"><span data-stu-id="cc9af-165">However, DAX supports custom date and time formats.</span></span>  
  
<span data-ttu-id="cc9af-166">**Conversión de valores de cadena en otros valores no booleanos**</span><span class="sxs-lookup"><span data-stu-id="cc9af-166">**Cast from string to other non Boolean values**</span></span>  
<span data-ttu-id="cc9af-167">Cuando se realiza la conversión de cadenas en valores no booleanos, el modo DirectQuery se comporta igual que SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc9af-167">When casting from strings to non-Boolean values, DirectQuery mode behaves the same as SQL Server.</span></span> <span data-ttu-id="cc9af-168">Para más información, vea [CAST y CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span><span class="sxs-lookup"><span data-stu-id="cc9af-168">For more information, see [CAST and CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span></span>  
  
<span data-ttu-id="cc9af-169">**No se permite la conversión de números en cadenas**</span><span class="sxs-lookup"><span data-stu-id="cc9af-169">**Cast from numbers to string not allowed**</span></span>  
<span data-ttu-id="cc9af-170">EJEMPLO: `CONCATENATE(102,",345")`</span><span class="sxs-lookup"><span data-stu-id="cc9af-170">EXAMPLE: `CONCATENATE(102,",345")`</span></span>  
  
<span data-ttu-id="cc9af-171">La conversión de números en cadenas no se admite en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc9af-171">Casting from numbers to strings is not allowed in SQL Server.</span></span>  
  
<span data-ttu-id="cc9af-172">Esta fórmula devuelve un error en los modelos tabulares y en el modo DirectQuery, pero genera un resultado en [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9af-172">This formula returns an error in tabular models and in DirectQuery mode; however, the formula produces a result in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span></span>  
  
<span data-ttu-id="cc9af-173">**No se admiten las conversiones de dos intentos en DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="cc9af-173">**No support for two-try casts in DirectQuery**</span></span>  
<span data-ttu-id="cc9af-174">A menudo, los modelos en memoria intentan una segunda conversión si se produce un error en la primera.</span><span class="sxs-lookup"><span data-stu-id="cc9af-174">In-memory models often attempt a second cast when the first one fails.</span></span> <span data-ttu-id="cc9af-175">Esto nunca sucede en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-175">This never happens in DirectQuery mode.</span></span>  
  
<span data-ttu-id="cc9af-176">EJEMPLO: `TODAY() + "13:14:15"`</span><span class="sxs-lookup"><span data-stu-id="cc9af-176">EXAMPLE: `TODAY() + "13:14:15"`</span></span>  
  
<span data-ttu-id="cc9af-177">En esta expresión, el primer parámetro tiene el tipo **datetime** y el segundo parámetro, el tipo **string**.</span><span class="sxs-lookup"><span data-stu-id="cc9af-177">In this expression, the first parameter has type **datetime** and second parameter has type **string**.</span></span> <span data-ttu-id="cc9af-178">Sin embargo, las conversiones se tratan de forma diferente al combinar los operandos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-178">However, the casts when combining the operands are handled differently.</span></span> <span data-ttu-id="cc9af-179">DAX realizará una conversión implícita de **string** a **double**.</span><span class="sxs-lookup"><span data-stu-id="cc9af-179">DAX will perform an implicit cast from **string** to **double**.</span></span> <span data-ttu-id="cc9af-180">En los modelos en memoria, el motor de las fórmulas intenta realizar la conversión directamente en **double**y, si esto no es posible, intentará convertir la cadena en **datetime**.</span><span class="sxs-lookup"><span data-stu-id="cc9af-180">In in-memory models, the formula engine attempts to cast directly to **double**, and if that fails, it will try to cast the string to **datetime**.</span></span>  
  
<span data-ttu-id="cc9af-181">En el modo DirectQuery, solo se aplicará la conversión directa de **string** en **double** .</span><span class="sxs-lookup"><span data-stu-id="cc9af-181">In DirectQuery mode, only the direct cast from **string** to **double** will be applied.</span></span> <span data-ttu-id="cc9af-182">Si no es posible realizar esta conversión, la fórmula devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-182">If this cast fails, the formula will return an error.</span></span>  
  
### <a name="math-functions-and-arithmetic-operations"></a><a name="bkmk_Math"></a><span data-ttu-id="cc9af-183">Funciones matemáticas y operaciones aritméticas</span><span class="sxs-lookup"><span data-stu-id="cc9af-183">Math functions and arithmetic operations</span></span>  
<span data-ttu-id="cc9af-184">Algunas funciones matemáticas devolverán resultados diferentes en el modo DirectQuery debido a diferencias en el tipo de datos subyacente o en la conversión que se puede aplicar en las operaciones.</span><span class="sxs-lookup"><span data-stu-id="cc9af-184">Some mathematical functions will return different results in DirectQuery mode because of differences in the underlying data type or the casts that can be applied in operations.</span></span> <span data-ttu-id="cc9af-185">Asimismo, las restricciones descritas anteriormente en el intervalo de valores permitidos pueden afectar al resultado de las operaciones aritméticas.</span><span class="sxs-lookup"><span data-stu-id="cc9af-185">Also, the restrictions described above on the allowed range of values might affect the outcome of arithmetic operations.</span></span>  
  
<span data-ttu-id="cc9af-186">**Orden de adición**</span><span class="sxs-lookup"><span data-stu-id="cc9af-186">**Order of addition**</span></span>  
<span data-ttu-id="cc9af-187">Al crear una fórmula que agrega una serie de números, un modelo en memoria podría procesar los números en un orden distinto al de un modelo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-187">When you create a formula that adds a series of numbers, an in-memory model might process the numbers in a different order than a DirectQuery model.</span></span>  <span data-ttu-id="cc9af-188">Por lo tanto, si dispone de muchos números positivos y negativos muy grandes, es posible que obtenga un error en una operación y resultados correctos en otra.</span><span class="sxs-lookup"><span data-stu-id="cc9af-188">Therefore, when you have many very large positive numbers and very large negative numbers, you may get an error in one operation and results in another operation.</span></span>  
  
<span data-ttu-id="cc9af-189">**Uso de la función POWER**</span><span class="sxs-lookup"><span data-stu-id="cc9af-189">**Use of the POWER function**</span></span>  
<span data-ttu-id="cc9af-190">EJEMPLO: `POWER(-64, 1/3)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-190">EXAMPLE: `POWER(-64, 1/3)`</span></span>  
  
<span data-ttu-id="cc9af-191">En el modo DirectQuery, la función POWER no puede utilizar valores negativos como base cuando se eleva a un exponente fraccionario.</span><span class="sxs-lookup"><span data-stu-id="cc9af-191">In DirectQuery mode, the POWER function cannot use negative values as the base when raised to a fractional exponent.</span></span> <span data-ttu-id="cc9af-192">Este es el comportamiento previsto de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc9af-192">This is the expected behavior in SQL Server.</span></span>  
  
<span data-ttu-id="cc9af-193">En un modelo en memoria, la fórmula devuelve -4.</span><span class="sxs-lookup"><span data-stu-id="cc9af-193">In an in-memory model, the formula returns -4.</span></span>  
  
<span data-ttu-id="cc9af-194">**Operaciones de desbordamiento numérico**</span><span class="sxs-lookup"><span data-stu-id="cc9af-194">**Numerical overflow operations**</span></span>  
<span data-ttu-id="cc9af-195">En Transact-SQL, las operaciones que dan como resultado un desbordamiento numérico devuelven un error de desbordamiento; por lo tanto, las fórmulas que producen un desbordamiento también generan un error en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-195">In Transact-SQL, operations that result in a numerical overflow return an overflow error; therefore, formulas that result in an overflow also raise an error in DirectQuery mode.</span></span>  
  
<span data-ttu-id="cc9af-196">Sin embargo, si se utiliza la misma fórmula en un modelo en memoria, esta devuelve un entero de ocho bytes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-196">However, the same formula when used in an in-memory model returns an eight-byte integer.</span></span> <span data-ttu-id="cc9af-197">Esto se debe a que el motor de fórmulas no realiza comprobaciones de desbordamientos numéricos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-197">That is because the formula engine does not perform checks for numerical overflows.</span></span>  
  
<span data-ttu-id="cc9af-198">**Las funciones LOG con valores en blanco devuelven resultados diferentes**</span><span class="sxs-lookup"><span data-stu-id="cc9af-198">**LOG functions with blanks return different results**</span></span>  
<span data-ttu-id="cc9af-199">SQL Server procesa los valores NULL y los valores en blanco de forma diferente a como lo hace el motor xVelocity.</span><span class="sxs-lookup"><span data-stu-id="cc9af-199">SQL Server handles nulls and blanks differently than the xVelocity engine.</span></span> <span data-ttu-id="cc9af-200">Como resultado, la siguiente fórmula devuelve un error en el modo DirectQuery, pero devuelve Infinity (-INF) en el modo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-200">As a result, the following formula returns an error in DirectQuery mode, but return infinity (-inf) in in-memory mode.</span></span>  
  
`EXAMPLE: LOG(blank())`  
  
<span data-ttu-id="cc9af-201">Las mismas limitaciones se aplican al resto de funciones logarítmicas: LOG10 y LN.</span><span class="sxs-lookup"><span data-stu-id="cc9af-201">The same limitations apply to the other logarithmic functions: LOG10 and LN.</span></span>  
  
<span data-ttu-id="cc9af-202">Para más información sobre el tipo de datos **blank** de DAX, vea see [Especificación de sintaxis de DAX](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="cc9af-202">For more information about the **blank** data type in DAX, see [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="cc9af-203">**División por 0 y división por un valor en blanco**</span><span class="sxs-lookup"><span data-stu-id="cc9af-203">**Division by 0 and division by Blank**</span></span>  
<span data-ttu-id="cc9af-204">En el modo DirectQuery, la división por cero (0) o la división por un valor en blanco siempre producirá un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-204">In DirectQuery mode, division by zero (0) or division by BLANK will always result in an error.</span></span> <span data-ttu-id="cc9af-205">SQL Server no admite la noción de infinito y, dado que el resultado natural de una división por 0 es infinito, el resultado es un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-205">SQL Server does not support the notion of infinity, and because the natural result of any division by 0 is infinity, the result is an error.</span></span> <span data-ttu-id="cc9af-206">Sin embargo, SQL Server admite la división por valores NULL, y el resultado siempre deberá ser un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-206">However, SQL Server supports division by nulls, and the result must always equal null.</span></span>  
  
<span data-ttu-id="cc9af-207">En lugar de devolver resultados diferentes para estas operaciones, en el modo DirectQuery, ambos tipos de operaciones (la división por cero y la división por valores NULL) devuelven un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-207">Rather than return different results for these operations, in DirectQuery mode, both types of operations (division by zero and division by null) return an error.</span></span>  
  
<span data-ttu-id="cc9af-208">Tenga en cuenta que, tanto en Excel como en los modelos de [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , la división entre cero también devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-208">Note that, in Excel and in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, division by zero also returns an error.</span></span> <span data-ttu-id="cc9af-209">La división por un valor en blanco devuelve un valor en blanco.</span><span class="sxs-lookup"><span data-stu-id="cc9af-209">Division by a blank returns a blank.</span></span>  
  
<span data-ttu-id="cc9af-210">Las expresiones siguientes son todas válidas en los modelos en memoria, pero producirán un error en el modo DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="cc9af-210">The following expressions are all valid in in-memory models, but will fail in DirectQuery mode:</span></span>  
  
`1/BLANK`  
  
`1/0`  
  
`0.0/BLANK`  
  
`0/0`  
  
<span data-ttu-id="cc9af-211">La expresión `BLANK/BLANK` es un caso especial que devuelve `BLANK` tanto en los modelos en memoria como en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-211">The expression `BLANK/BLANK` is a special case that returns `BLANK` in both for in-memory models, and in DirectQuery mode.</span></span>  
  
### <a name="supported-numeric-and-date-time-ranges"></a><a name="bkmk_Ranges"></a><span data-ttu-id="cc9af-212">Rangos numéricos y de fecha y hora admitidos</span><span class="sxs-lookup"><span data-stu-id="cc9af-212">Supported numeric and date-time ranges</span></span>  
<span data-ttu-id="cc9af-213">Las fórmulas en los [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelos tabulares y en memoria están sujetas a las mismas limitaciones que Excel con respecto a los valores máximos permitidos para los números y las fechas reales.</span><span class="sxs-lookup"><span data-stu-id="cc9af-213">Formulas in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and tabular models in-memory are subject to the same limitations as Excel with regard to maximum allowed values for real numbers and dates.</span></span> <span data-ttu-id="cc9af-214">Sin embargo, pueden surgir diferencias cuando se devuelve el valor máximo de un cálculo o de una consulta, o cuando se convierten, redondean o truncan los valores.</span><span class="sxs-lookup"><span data-stu-id="cc9af-214">However, differences can arise when the maximum value is returned from a calculation or query, or when values are converted, cast, rounded, or truncated.</span></span>  
  
-   <span data-ttu-id="cc9af-215">En el modo DirectQuery, si se multiplican valores de los tipos **Currency** y **Real** y el resultado es mayor que el valor máximo posible, no se genera ningún error y se devuelve un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-215">If values of types **Currency** and **Real** are multiplied, and the result is larger than the maximum possible value, in DirectQuery mode, no error is raised, and a null is returned.</span></span>  
  
-   <span data-ttu-id="cc9af-216">En los modelos en memoria, no se genera ningún error, pero se devuelve el valor máximo.</span><span class="sxs-lookup"><span data-stu-id="cc9af-216">In in-memory models, no error is raised, but the maximum value is returned.</span></span>  
  
<span data-ttu-id="cc9af-217">En general, dado que los intervalos de fechas aceptados son diferentes para Excel y para SQL Server, los resultados solo coincidirán si las fechas se encuentran dentro del intervalo de fechas común, que incluye las fechas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc9af-217">In general, because the accepted date ranges are different for Excel and SQL Server, results can be guaranteed to match only when dates are within the common date range, which is inclusive of the following dates:</span></span>  
  
-   <span data-ttu-id="cc9af-218">Fecha más antigua: 1 de marzo de 1990</span><span class="sxs-lookup"><span data-stu-id="cc9af-218">Earliest date: March 1, 1990</span></span>  
  
-   <span data-ttu-id="cc9af-219">Fecha más reciente: 31 diciembre de 9999</span><span class="sxs-lookup"><span data-stu-id="cc9af-219">Latest date: December 31, 9999</span></span>  
  
<span data-ttu-id="cc9af-220">Si cualquiera de las fechas utilizadas en las fórmulas queda fuera de este intervalo, la fórmula generará un error o los resultados no coincidirán.</span><span class="sxs-lookup"><span data-stu-id="cc9af-220">If any dates used in formulas fall outside this range, either the formula will result in an error, or the results will not match.</span></span>  
  
<span data-ttu-id="cc9af-221">**Valores de coma flotante admitidos por CEILING**</span><span class="sxs-lookup"><span data-stu-id="cc9af-221">**Floating point values supported by CEILING**</span></span>  
<span data-ttu-id="cc9af-222">EJEMPLO: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span><span class="sxs-lookup"><span data-stu-id="cc9af-222">EXAMPLE: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span></span>  
  
<span data-ttu-id="cc9af-223">El equivalente en Transact-SQL de la función DAX CEILING solo admite valores con magnitudes de 10^19 o inferiores.</span><span class="sxs-lookup"><span data-stu-id="cc9af-223">The Transact-SQL equivalent of the DAX CEILING function only supports values with magnitude of 10^19 or less.</span></span> <span data-ttu-id="cc9af-224">Una regla general es que los valores de coma flotante tienen que caber en **bigint**.</span><span class="sxs-lookup"><span data-stu-id="cc9af-224">A rule of thumb is that floating point values should be able to fit into **bigint**.</span></span>  
  
<span data-ttu-id="cc9af-225">**Funciones Datepart con fechas que están fuera del intervalo**</span><span class="sxs-lookup"><span data-stu-id="cc9af-225">**Datepart functions with dates that are out of range**</span></span>  
<span data-ttu-id="cc9af-226">Los resultados en el modo DirectQuery solo coincidirán con los resultados de los modelos en memoria cuando la fecha utilizada como argumento se encuentre en el intervalo de fechas válido.</span><span class="sxs-lookup"><span data-stu-id="cc9af-226">Results in DirectQuery mode are guaranteed to match those in in-memory models only when the date used as the argument is in the valid date range.</span></span> <span data-ttu-id="cc9af-227">Si no se cumplen estas condiciones, pueden suceder dos cosas: que se genere un error o que los resultados devueltos por la fórmula en DirectQuery sean diferentes de los obtenidos en el modo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-227">If these conditions are not satisfied, either an error will be raised, or the formula will return different results in DirectQuery than in in-memory mode.</span></span>  
  
<span data-ttu-id="cc9af-228">EJEMPLO: `MONTH(0)` o `YEAR(0)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-228">EXAMPLE: `MONTH(0)` or `YEAR(0)`</span></span>  
  
<span data-ttu-id="cc9af-229">En el modo DirectQuery, las expresiones devuelven 12 y 1899, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cc9af-229">In DirectQuery mode, the expressions return 12 and 1899, respectively.</span></span>  
  
<span data-ttu-id="cc9af-230">En los modelos en memoria, las expresiones devuelven 1 y 1900, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cc9af-230">In in-memory models, the expressions return 1 and 1900, respectively.</span></span>  
  
<span data-ttu-id="cc9af-231">EJEMPLO:  `EOMONTH(0.0001, 1)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-231">EXAMPLE:  `EOMONTH(0.0001, 1)`</span></span>  
  
<span data-ttu-id="cc9af-232">Los resultados de esta expresión solo coincidirán cuando los datos proporcionados como parámetro se encuentren dentro del intervalo de fechas válido.</span><span class="sxs-lookup"><span data-stu-id="cc9af-232">The results of this expression will match only when the data supplied as a parameter is within the valid date range.</span></span>  
  
<span data-ttu-id="cc9af-233">EJEMPLO: `EOMONTH(blank(), blank())` o `EDATE(blank(), blank())`</span><span class="sxs-lookup"><span data-stu-id="cc9af-233">EXAMPLE: `EOMONTH(blank(), blank())` or `EDATE(blank(), blank())`</span></span>  
  
<span data-ttu-id="cc9af-234">Los resultados de esta expresión deben coincidir en el modo DirectQuery y en el modo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-234">The results of this expression should be the same in DirectQuery mode and in-memory mode.</span></span>  
  
<span data-ttu-id="cc9af-235">**Truncamiento de los valores de hora**</span><span class="sxs-lookup"><span data-stu-id="cc9af-235">**Truncation of time values**</span></span>  
<span data-ttu-id="cc9af-236">EJEMPLO: `SECOND(1231.04097222222)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-236">EXAMPLE: `SECOND(1231.04097222222)`</span></span>  
  
<span data-ttu-id="cc9af-237">En el modo DirectQuery, el resultado se trunca, de acuerdo con las reglas de SQL Server, y la expresión se evalúa como 59.</span><span class="sxs-lookup"><span data-stu-id="cc9af-237">In DirectQuery mode, the result is truncated, following the rules of SQL Server, and the expression evaluates to 59.</span></span>  
  
<span data-ttu-id="cc9af-238">En los modelos en memoria, los resultados de cada operación provisional se redondean; por lo tanto, la expresión se evalúa como 0.</span><span class="sxs-lookup"><span data-stu-id="cc9af-238">In in-memory models, the results of each interim operation are rounded; therefore, the expression evaluates to 0.</span></span>  
  
<span data-ttu-id="cc9af-239">A continuación se explica cómo se calcula este valor:</span><span class="sxs-lookup"><span data-stu-id="cc9af-239">The following example demonstrates how this value is calculated:</span></span>  
  
1.  <span data-ttu-id="cc9af-240">La fracción de la entrada (0,04097222222) se multiplica por 24.</span><span class="sxs-lookup"><span data-stu-id="cc9af-240">The fraction of the input (0.04097222222) is multiplied by 24.</span></span>  
  
2.  <span data-ttu-id="cc9af-241">El valor de hora resultante (0,98333333328) se multiplica por 60.</span><span class="sxs-lookup"><span data-stu-id="cc9af-241">The resulting hour value (0.98333333328) is multiplied by 60.</span></span>  
  
3.  <span data-ttu-id="cc9af-242">El valor de minuto resultante es 58,9999999968.</span><span class="sxs-lookup"><span data-stu-id="cc9af-242">The resulting minute value is 58.9999999968.</span></span>  
  
4.  <span data-ttu-id="cc9af-243">La fracción del valor de minuto (0,9999999968) se multiplica por 60.</span><span class="sxs-lookup"><span data-stu-id="cc9af-243">The fraction of the minute value (0.9999999968) is multiplied by 60.</span></span>  
  
5.  <span data-ttu-id="cc9af-244">El valor de segundo resultante (59.999999808) se redondea a 60.</span><span class="sxs-lookup"><span data-stu-id="cc9af-244">The resulting second value (59.999999808) rounds up to 60.</span></span>  
  
6.  <span data-ttu-id="cc9af-245">60 equivale a 0.</span><span class="sxs-lookup"><span data-stu-id="cc9af-245">60 is equivalent to 0.</span></span>  
  
<span data-ttu-id="cc9af-246">**El tipo de datos Time de SQL no se admite**</span><span class="sxs-lookup"><span data-stu-id="cc9af-246">**SQL Time data type not supported**</span></span>  
<span data-ttu-id="cc9af-247">En los modelos en memoria no se puede usar el nuevo tipo de datos **Time** de SQL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-247">In-memory models do not support use of the new SQL **Time** data type.</span></span> <span data-ttu-id="cc9af-248">En el modo DirectQuery, las fórmulas que hagan referencia a columnas con este tipo de datos devolverán un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-248">In DirectQuery mode, formulas that reference columns with this data type will return an error.</span></span> <span data-ttu-id="cc9af-249">Las columnas de con datos Time no se pueden importar en un modelo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-249">Time data columns cannot be imported into an in-memory model.</span></span>  
  
<span data-ttu-id="cc9af-250">Sin embargo, en [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] y en los modelos almacenados en caché, a veces el motor convierte el valor de hora en un tipo de datos aceptable y la fórmula devuelve un resultado.</span><span class="sxs-lookup"><span data-stu-id="cc9af-250">However, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and in cached models, sometimes the engine casts the time value to an acceptable data type, and the formula returns a result.</span></span>  
  
<span data-ttu-id="cc9af-251">Este comportamiento afecta a todas las funciones que utilizan una columna de fecha como parámetro.</span><span class="sxs-lookup"><span data-stu-id="cc9af-251">This behavior affects all functions that use a date column as a parameter.</span></span>  
  
### <a name="currency"></a><a name="bkmk_Currency"></a><span data-ttu-id="cc9af-252">Moneda</span><span class="sxs-lookup"><span data-stu-id="cc9af-252">Currency</span></span>  
<span data-ttu-id="cc9af-253">En el modo DirectQuery, si el resultado de una operación aritmética tiene el tipo **Currency**, el valor ha de estar dentro del siguiente rango:</span><span class="sxs-lookup"><span data-stu-id="cc9af-253">In DirectQuery mode, if the result of an arithmetic operation has the type **Currency**, the value must be within the following range:</span></span>  
  
-   <span data-ttu-id="cc9af-254">Mínimo: -922337203685477.5808</span><span class="sxs-lookup"><span data-stu-id="cc9af-254">Minimum: -922337203685477.5808</span></span>  
  
-   <span data-ttu-id="cc9af-255">Máximo: 922337203685477.5807</span><span class="sxs-lookup"><span data-stu-id="cc9af-255">Maximum: 922337203685477.5807</span></span>  
  
<span data-ttu-id="cc9af-256">**Combinar tipos de datos de moneda y REAL**</span><span class="sxs-lookup"><span data-stu-id="cc9af-256">**Combining currency and REAL data types**</span></span>  
<span data-ttu-id="cc9af-257">EJEMPLO: `Currency sample 1`</span><span class="sxs-lookup"><span data-stu-id="cc9af-257">EXAMPLE: `Currency sample 1`</span></span>  
  
<span data-ttu-id="cc9af-258">Si los tipos **Currency** y **Real** se multiplican y el resultado es mayor que 9223372036854774784 (0x7ffffffffffffc00), el modo DirectQuery no generará un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-258">If **Currency** and **Real** types are multiplied, and the result is larger than 9223372036854774784 (0x7ffffffffffffc00), DirectQuery mode will not raise an error.</span></span>  
  
<span data-ttu-id="cc9af-259">En un modelo en memoria, se generará un error si el valor absoluto del resultado es mayor que 922337203685477.4784.</span><span class="sxs-lookup"><span data-stu-id="cc9af-259">In an in-memory model, an error is raised if the absolute value of the result is larger than 922337203685477.4784.</span></span>  
  
<span data-ttu-id="cc9af-260">**Operaciones cuyo resultado es un valor que está fuera del intervalo**</span><span class="sxs-lookup"><span data-stu-id="cc9af-260">**Operation results in an out-of-range value**</span></span>  
<span data-ttu-id="cc9af-261">EJEMPLO: `Currency sample 2`</span><span class="sxs-lookup"><span data-stu-id="cc9af-261">EXAMPLE: `Currency sample 2`</span></span>  
  
<span data-ttu-id="cc9af-262">Si las operaciones realizadas con dos valores de moneda cualesquiera dan como resultado un valor que está fuera del intervalo especificado, se generará un error en los modelos en memoria, pero no en los modelos DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-262">If operations on any two currency values result in a value that is outside the specified range, an error is raised in in-memory models, but not in DirectQuery models.</span></span>  
  
<span data-ttu-id="cc9af-263">**Combinar datos de moneda con otros tipos de datos**</span><span class="sxs-lookup"><span data-stu-id="cc9af-263">**Combining currency with other data types**</span></span>  
<span data-ttu-id="cc9af-264">La división de valores de moneda por valores de otros tipos numéricos puede dar lugar a resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-264">Division of currency values by values of other numeric types can result in different results.</span></span>  
  
### <a name="aggregation-functions"></a><a name="bkmk_Aggregations"></a><span data-ttu-id="cc9af-265">Funciones de agregación</span><span class="sxs-lookup"><span data-stu-id="cc9af-265">Aggregation functions</span></span>  
<span data-ttu-id="cc9af-266">Las funciones estadísticas en una tabla con una fila devuelven resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-266">Statistical functions on a table with one row return different results.</span></span> <span data-ttu-id="cc9af-267">Las funciones de agregación realizadas en tablas vacías también se comportan de forma diferente en los modelos en memoria de como lo hacen en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-267">Aggregation functions over empty tables also behave differently in in-memory models than they do in DirectQuery mode.</span></span>  
  
<span data-ttu-id="cc9af-268">**Funciones estadísticas en una tabla con una sola fila**</span><span class="sxs-lookup"><span data-stu-id="cc9af-268">**Statistical functions over a table with a single row**</span></span>  
<span data-ttu-id="cc9af-269">Si la tabla que se utiliza como argumento contiene una sola fila, en el modo DirectQuery, las funciones estadísticas como STDEV y VAR devolverán un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-269">If the table that is used as argument contains a single row, in DirectQuery mode, statistical functions such as STDEV and VAR return null.</span></span>  
  
<span data-ttu-id="cc9af-270">En un modelo en memoria, una fórmula que utilice STDEV o VAR en una tabla con una sola fila devuelve un error de división por cero.</span><span class="sxs-lookup"><span data-stu-id="cc9af-270">In an in-memory model, a formula that uses STDEV or VAR over a table with a single row returns a division by zero error.</span></span>  
  
### <a name="text-functions"></a><a name="bkmk_Text"></a><span data-ttu-id="cc9af-271">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="cc9af-271">Text functions</span></span>  
<span data-ttu-id="cc9af-272">Puesto que los almacenes de datos relacionales proporcionan tipos de datos de texto diferentes de los de Excel, es posible que se muestren resultados distintos al buscar cadenas o trabajar con subcadenas.</span><span class="sxs-lookup"><span data-stu-id="cc9af-272">Because relational data stores provide different text data types than does Excel, you may see different results when searching strings or working with substrings.</span></span> <span data-ttu-id="cc9af-273">Asimismo, la longitud de las cadenas puede ser diferente.</span><span class="sxs-lookup"><span data-stu-id="cc9af-273">The length of strings also can be different.</span></span>  
  
<span data-ttu-id="cc9af-274">En general, las funciones de manipulación de cadenas que utilicen columnas de tamaño fijo como argumentos pueden tener resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="cc9af-274">In general, any string manipulation functions that use fixed-size columns as arguments can have different results.</span></span>  
  
<span data-ttu-id="cc9af-275">Además, en SQL Server, algunas funciones de texto admiten argumentos adicionales que no se proporcionan en Excel.</span><span class="sxs-lookup"><span data-stu-id="cc9af-275">Additionally, in SQL Server, some text functions support additional arguments that are not provided in Excel.</span></span> <span data-ttu-id="cc9af-276">Si la fórmula requiere el argumento que falta, es posible que se obtengan resultados diferentes o errores en el modelo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cc9af-276">If the formula requires the missing argument you can get different results or errors in the in-memory model.</span></span>  
  
<span data-ttu-id="cc9af-277">**Las operaciones que devuelven un carácter mediante las funciones LEFT, RIGHT, etc. pueden devolver el carácter correcto pero en minúsculas o mayúsculas, o no devolver ningún resultado**</span><span class="sxs-lookup"><span data-stu-id="cc9af-277">**Operations that return a character using LEFT, RIGHT, etc. may return the correct character but in a different case, or no results**</span></span>  
<span data-ttu-id="cc9af-278">EJEMPLO: `LEFT(["text"], 2)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-278">EXAMPLE: `LEFT(["text"], 2)`</span></span>  
  
<span data-ttu-id="cc9af-279">En el modo DirectQuery, el formato de mayúsculas o minúsculas que se devuelve es siempre exactamente el mismo que el de la letra almacenada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-279">In DirectQuery mode, the case of the character that is returned is always exactly the same as the letter that is stored in the database.</span></span> <span data-ttu-id="cc9af-280">Sin embargo, el motor xVelocity utiliza un algoritmo diferente para la compresión y la indización de valores con objeto de mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cc9af-280">However, the xVelocity engine uses a different algorithm for compression and indexing of values, to improve performance.</span></span>  
  
<span data-ttu-id="cc9af-281">De forma predeterminada, se utiliza la intercalación Latin1_General, que no distingue entre mayúsculas y minúsculas pero que sí distingue los acentos.</span><span class="sxs-lookup"><span data-stu-id="cc9af-281">By default, the Latin1_General collation is used, which is case-insensitive but accent-sensitive.</span></span> <span data-ttu-id="cc9af-282">Por lo tanto, si hay varias instancias de una cadena de texto en minúsculas, mayúsculas o en ambas, todas las instancias se consideran la misma cadena, y solo la primera de ellas se almacena en el índice.</span><span class="sxs-lookup"><span data-stu-id="cc9af-282">Therefore, if there are multiple instances of a text string in lower case, upper case, or mixed case, all instances are considered the same string, and only the first instance of the string is stored in the index.</span></span> <span data-ttu-id="cc9af-283">Todas las funciones de texto que actúan sobre cadenas almacenadas recuperarán la porción especificada de la forma indizada.</span><span class="sxs-lookup"><span data-stu-id="cc9af-283">All text functions that operate on stored strings will retrieve the specified portion of the indexed form.</span></span> <span data-ttu-id="cc9af-284">Por lo tanto, la fórmula del ejemplo devolverá el mismo valor para toda la columna, utilizando la primera instancia como entrada.</span><span class="sxs-lookup"><span data-stu-id="cc9af-284">Therefore, the example formula would return the same value for the entire column, using the first instance as the input.</span></span>  
  
[<span data-ttu-id="cc9af-285">Almacenamiento e intercalación de cadenas en modelos tabulares</span><span class="sxs-lookup"><span data-stu-id="cc9af-285">String Storage and Collation in Tabular Models</span></span>](https://msdn.microsoft.com/8516f0ad-32ee-4688-a304-e705143642ca)  
  
<span data-ttu-id="cc9af-286">Este comportamiento también se aplica a otras funciones de texto, incluyendo RIGHT, MID, etc.</span><span class="sxs-lookup"><span data-stu-id="cc9af-286">This behavior also applies to other text functions, including RIGHT, MID, and so forth.</span></span>  
  
<span data-ttu-id="cc9af-287">**La longitud de la cadena influye en los resultados**</span><span class="sxs-lookup"><span data-stu-id="cc9af-287">**String length affects results**</span></span>  
<span data-ttu-id="cc9af-288">EJEMPLO: `SEARCH("within string", "sample target  text", 1, 1)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-288">EXAMPLE: `SEARCH("within string", "sample target  text", 1, 1)`</span></span>  
  
<span data-ttu-id="cc9af-289">Si busca una cadena mediante la función SEARCH, y la cadena de destino es más larga que la cadena original, el modo DirectQuery genera un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-289">If you search for a string using the SEARCH function, and the target string is longer than the within string, DirectQuery mode raises an error.</span></span>  
  
<span data-ttu-id="cc9af-290">En un modelo en memoria, se devuelve la cadena buscada, pero con su longitud truncada a la longitud del &lt;texto original&gt;.</span><span class="sxs-lookup"><span data-stu-id="cc9af-290">In an in-memory model, the searched string is returned, but with its length truncated to the length of &lt;within text&gt;.</span></span>  
  
<span data-ttu-id="cc9af-291">EJEMPLO: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span><span class="sxs-lookup"><span data-stu-id="cc9af-291">EXAMPLE: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span></span>  
  
<span data-ttu-id="cc9af-292">En el modo DirectQuery, si la longitud de la cadena de reemplazo es mayor que la longitud de la cadena original, la fórmula devuelve un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-292">If the length of the replacement string is greater than the length of the original string, in DirectQuery mode, the formula returns null.</span></span>  
  
<span data-ttu-id="cc9af-293">En los modelos en memoria, la fórmula sigue el comportamiento de Excel, que concatena la cadena de origen y la de reemplazo, lo que devuelve CACalifornia.</span><span class="sxs-lookup"><span data-stu-id="cc9af-293">In in-memory models, the formula follows the behavior of Excel, which concatenates the source string and the replacement string, which returns CACalifornia.</span></span>  
  
<span data-ttu-id="cc9af-294">**TRIM implícito en el centro de las cadenas**</span><span class="sxs-lookup"><span data-stu-id="cc9af-294">**Implicit TRIM in the middle of strings**</span></span>  
<span data-ttu-id="cc9af-295">EJEMPLO: `TRIM(" A sample sentence with leading white space")`</span><span class="sxs-lookup"><span data-stu-id="cc9af-295">EXAMPLE: `TRIM(" A sample sentence with leading white space")`</span></span>  
  
<span data-ttu-id="cc9af-296">El modo DirectQuery traduce la función DAX TRIM a la instrucción `LTRIM(RTRIM(<column>))`de SQL.</span><span class="sxs-lookup"><span data-stu-id="cc9af-296">DirectQuery mode translates the DAX TRIM function to the SQL statement `LTRIM(RTRIM(<column>))`.</span></span> <span data-ttu-id="cc9af-297">Como resultado, solo se quitan los caracteres de espacio en blanco iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="cc9af-297">As a result, only leading and trailing white space is removed.</span></span>  
  
<span data-ttu-id="cc9af-298">En cambio, la misma fórmula en un modelo en memoria quita los espacios situados dentro de la cadena, siguiendo el comportamiento de Excel.</span><span class="sxs-lookup"><span data-stu-id="cc9af-298">In contrast, the same formula in an in-memory model removes spaces within the string, following the behavior of Excel.</span></span>  
  
<span data-ttu-id="cc9af-299">**RTRIM implícito con uso de la función LEN**</span><span class="sxs-lookup"><span data-stu-id="cc9af-299">**Implicit RTRIM with use of LEN function**</span></span>  
<span data-ttu-id="cc9af-300">EJEMPLO: `LEN('string_column')`</span><span class="sxs-lookup"><span data-stu-id="cc9af-300">EXAMPLE: `LEN('string_column')`</span></span>  
  
<span data-ttu-id="cc9af-301">Al igual que SQL Server, el modo DirectQuery quita automáticamente el espacio en blanco del final de las columnas de cadena: es decir, realiza un RTRIM implícito.</span><span class="sxs-lookup"><span data-stu-id="cc9af-301">Like SQL Server, DirectQuery mode automatically removes white space from the end of string columns: that is, it performs an implicit RTRIM.</span></span> <span data-ttu-id="cc9af-302">Por lo tanto, las fórmulas que utilizan la función LEN pueden devolver valores diferentes si la cadena tiene espacios finales.</span><span class="sxs-lookup"><span data-stu-id="cc9af-302">Therefore, formulas that use the LEN function can return different values if the string has trailing spaces.</span></span>  
  
<span data-ttu-id="cc9af-303">**In-memory admite parámetros adicionales para SUBSTITUTE**</span><span class="sxs-lookup"><span data-stu-id="cc9af-303">**In-memory supports additional parameters for SUBSTITUTE**</span></span>  
<span data-ttu-id="cc9af-304">EJEMPLO: `SUBSTITUTE([Title],"Doctor","Dr.")`</span><span class="sxs-lookup"><span data-stu-id="cc9af-304">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.")`</span></span>  
  
<span data-ttu-id="cc9af-305">EJEMPLO: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-305">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span></span>  
  
<span data-ttu-id="cc9af-306">En el modo DirectQuery, solo se puede puede utilizar la versión de esta función que tiene tres (3) parámetros: una referencia a una columna, el texto antiguo y el texto nuevo.</span><span class="sxs-lookup"><span data-stu-id="cc9af-306">In DirectQuery mode, you can use only the version of this function that has three (3) parameters: a reference to a column, the old text, and the new text.</span></span> <span data-ttu-id="cc9af-307">Si se utiliza la segunda fórmula, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-307">If you use the second formula, an error is raised.</span></span>  
  
<span data-ttu-id="cc9af-308">En los modelos en memoria, puede utilizar un cuarto parámetro opcional para especificar el número de repetición de la cadena que desea reemplazar.</span><span class="sxs-lookup"><span data-stu-id="cc9af-308">In in-memory models, you can use an optional fourth parameter to specify the instance number of the string to replace.</span></span> <span data-ttu-id="cc9af-309">Por ejemplo, puede reemplazar solo la segunda repetición, etc.</span><span class="sxs-lookup"><span data-stu-id="cc9af-309">For example, you can replace only the second instance, etc.</span></span>  
  
<span data-ttu-id="cc9af-310">**Restricciones en las longitudes de cadena para las operaciones REPT**</span><span class="sxs-lookup"><span data-stu-id="cc9af-310">**Restrictions on string lengths for REPT operations**</span></span>  
<span data-ttu-id="cc9af-311">En los modelos en memoria, la longitud de una cadena que resulta de una operación REPT debe ser inferior a 32.767 caracteres.</span><span class="sxs-lookup"><span data-stu-id="cc9af-311">In in-memory models, the length of a string resulting from an operation using REPT must be less than 32,767 characters.</span></span>  
  
<span data-ttu-id="cc9af-312">Esta limitación no se aplica en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-312">This limitation does not apply in DirectQuery mode.</span></span>  
  
<span data-ttu-id="cc9af-313">**Las operaciones de subcadena devuelven resultados diferentes en función del tipo de carácter**</span><span class="sxs-lookup"><span data-stu-id="cc9af-313">**Substring operations return different results depending on character type**</span></span>  
<span data-ttu-id="cc9af-314">EJEMPLO: `MID([col], 2, 5)`</span><span class="sxs-lookup"><span data-stu-id="cc9af-314">EXAMPLE: `MID([col], 2, 5)`</span></span>  
  
<span data-ttu-id="cc9af-315">Si el texto de entrada es **varchar** o **nvarchar**, el resultado de la fórmula es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="cc9af-315">If the input text is **varchar** or **nvarchar**, the result of the formula is always the same.</span></span>  
  
<span data-ttu-id="cc9af-316">Sin embargo, si el texto es un carácter de longitud fija y el valor de \* &lt; num_chars &gt; \* es mayor que la longitud de la cadena de destino, en el modo DirectQuery, se agrega un espacio en blanco al final de la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="cc9af-316">However, if the text is a fixed-length character and the value for *&lt;num_chars&gt;* is greater than the length of the target string, in DirectQuery mode, a blank is added at the end of the result string.</span></span>  
  
<span data-ttu-id="cc9af-317">En un modelo en memoria, el resultado termina en el último carácter de la cadena, sin relleno.</span><span class="sxs-lookup"><span data-stu-id="cc9af-317">In an in-memory model, the result terminates at the last string character, with no padding.</span></span>  
  
## <a name="functions-supported-in-directquery-mode"></a><a name="bkmk_SupportedFunc"></a><span data-ttu-id="cc9af-318">Funciones admitidas en el modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="cc9af-318">Functions supported in DirectQuery mode</span></span>  
<span data-ttu-id="cc9af-319">Se pueden utilizar las funciones DAX siguientes en el modo DirectQuery, pero con las restricciones descritas en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="cc9af-319">The following DAX functions can be used in DirectQuery mode, but with the qualifications as described in the preceding section.</span></span>  
  
<span data-ttu-id="cc9af-320">**Funciones de texto**</span><span class="sxs-lookup"><span data-stu-id="cc9af-320">**Text functions**</span></span>  
  
<span data-ttu-id="cc9af-321">CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="cc9af-321">CONCATENATE</span></span>  
  
<span data-ttu-id="cc9af-322">FIND</span><span class="sxs-lookup"><span data-stu-id="cc9af-322">FIND</span></span>  
  
<span data-ttu-id="cc9af-323">LEFT</span><span class="sxs-lookup"><span data-stu-id="cc9af-323">LEFT</span></span>  
  
<span data-ttu-id="cc9af-324">LEN</span><span class="sxs-lookup"><span data-stu-id="cc9af-324">LEN</span></span>  
  
<span data-ttu-id="cc9af-325">MID</span><span class="sxs-lookup"><span data-stu-id="cc9af-325">MID</span></span>  
  
<span data-ttu-id="cc9af-326">REPLACE</span><span class="sxs-lookup"><span data-stu-id="cc9af-326">REPLACE</span></span>  
  
<span data-ttu-id="cc9af-327">REPT</span><span class="sxs-lookup"><span data-stu-id="cc9af-327">REPT</span></span>  
  
<span data-ttu-id="cc9af-328">RIGHT</span><span class="sxs-lookup"><span data-stu-id="cc9af-328">RIGHT</span></span>  
  
<span data-ttu-id="cc9af-329">SUBSTITUTE</span><span class="sxs-lookup"><span data-stu-id="cc9af-329">SUBSTITUTE</span></span>  
  
<span data-ttu-id="cc9af-330">TRIM</span><span class="sxs-lookup"><span data-stu-id="cc9af-330">TRIM</span></span>  
  
<span data-ttu-id="cc9af-331">**Funciones estadísticas**</span><span class="sxs-lookup"><span data-stu-id="cc9af-331">**Statistical functions**</span></span>  
  
<span data-ttu-id="cc9af-332">COUNT</span><span class="sxs-lookup"><span data-stu-id="cc9af-332">COUNT</span></span>  
  
<span data-ttu-id="cc9af-333">STDEV.P</span><span class="sxs-lookup"><span data-stu-id="cc9af-333">STDEV.P</span></span>  
  
<span data-ttu-id="cc9af-334">STDEV.S</span><span class="sxs-lookup"><span data-stu-id="cc9af-334">STDEV.S</span></span>  
  
<span data-ttu-id="cc9af-335">STDEVX.P</span><span class="sxs-lookup"><span data-stu-id="cc9af-335">STDEVX.P</span></span>  
  
<span data-ttu-id="cc9af-336">STDEVX.S</span><span class="sxs-lookup"><span data-stu-id="cc9af-336">STDEVX.S</span></span>  
  
<span data-ttu-id="cc9af-337">VAR.P</span><span class="sxs-lookup"><span data-stu-id="cc9af-337">VAR.P</span></span>  
  
<span data-ttu-id="cc9af-338">VAR.S</span><span class="sxs-lookup"><span data-stu-id="cc9af-338">VAR.S</span></span>  
  
<span data-ttu-id="cc9af-339">VARX.P</span><span class="sxs-lookup"><span data-stu-id="cc9af-339">VARX.P</span></span>  
  
<span data-ttu-id="cc9af-340">VARX.S</span><span class="sxs-lookup"><span data-stu-id="cc9af-340">VARX.S</span></span>  
  
<span data-ttu-id="cc9af-341">**Funciones de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="cc9af-341">**Date/time functions**</span></span>  
  
<span data-ttu-id="cc9af-342">DATE</span><span class="sxs-lookup"><span data-stu-id="cc9af-342">DATE</span></span>  
  
<span data-ttu-id="cc9af-343">EDATE</span><span class="sxs-lookup"><span data-stu-id="cc9af-343">EDATE</span></span>  
  
<span data-ttu-id="cc9af-344">EOMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-344">EOMONTH</span></span>  
  
<span data-ttu-id="cc9af-345">DATE</span><span class="sxs-lookup"><span data-stu-id="cc9af-345">DATE</span></span>  
  
<span data-ttu-id="cc9af-346">TIME</span><span class="sxs-lookup"><span data-stu-id="cc9af-346">TIME</span></span>  
  
<span data-ttu-id="cc9af-347">SECOND</span><span class="sxs-lookup"><span data-stu-id="cc9af-347">SECOND</span></span>  
  
<span data-ttu-id="cc9af-348">**Funciones matemáticas numéricas**</span><span class="sxs-lookup"><span data-stu-id="cc9af-348">**Math and number functions**</span></span>  
  
<span data-ttu-id="cc9af-349">CEILING</span><span class="sxs-lookup"><span data-stu-id="cc9af-349">CEILING</span></span>  
  
<span data-ttu-id="cc9af-350">LN</span><span class="sxs-lookup"><span data-stu-id="cc9af-350">LN</span></span>  
  
<span data-ttu-id="cc9af-351">REGISTRO</span><span class="sxs-lookup"><span data-stu-id="cc9af-351">LOG</span></span>  
  
<span data-ttu-id="cc9af-352">LOG10</span><span class="sxs-lookup"><span data-stu-id="cc9af-352">LOG10</span></span>  
  
<span data-ttu-id="cc9af-353">POWER</span><span class="sxs-lookup"><span data-stu-id="cc9af-353">POWER</span></span>  
  
<span data-ttu-id="cc9af-354">**Consultas de tablas de DAX**</span><span class="sxs-lookup"><span data-stu-id="cc9af-354">**DAX Table queries**</span></span>  
  
<span data-ttu-id="cc9af-355">Existen algunas limitaciones al evaluar fórmulas en un modelo DirectQuery mediante consultas de tablas de DAX.</span><span class="sxs-lookup"><span data-stu-id="cc9af-355">There are some limitations when you evaluate formulas against a DirectQuery model by using DAX Table queries.</span></span> <span data-ttu-id="cc9af-356">DirectQuery no admite que se haga referencia dos veces a la misma columna en una cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="cc9af-356">DirectQuery does not support referring to the same column twice in an ORDER BY clause.</span></span> <span data-ttu-id="cc9af-357">La instrucción equivalente en Transact-SQL no se puede crear y la consulta produce un error.</span><span class="sxs-lookup"><span data-stu-id="cc9af-357">The equivalent Transact-SQL statement cannot be created and the query fails.</span></span>  
  
<span data-ttu-id="cc9af-358">En un modelo en memoria, la repetición de la cláusula ORDER no influye en los resultados.</span><span class="sxs-lookup"><span data-stu-id="cc9af-358">In an in-memory model, repeating the ORDER by clause has no effect on the results.</span></span>  
  
## <a name="functions-not-supported-in-directquery-mode"></a><a name="bkmk_NotSupportedFunc"></a><span data-ttu-id="cc9af-359">Funciones no admitidas en el modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="cc9af-359">Functions not supported in DirectQuery Mode</span></span>  
<span data-ttu-id="cc9af-360">Algunas funciones DAX no se admiten en los modelos implementados en el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-360">Some DAX functions are not supported in models that are deployed in DirectQuery mode.</span></span> <span data-ttu-id="cc9af-361">Los motivos por los que una determinada función no se admite pueden ser uno o varios de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc9af-361">The reasons that a particular function is not supported can include any or a combination of these reasons:</span></span>  
  
-   <span data-ttu-id="cc9af-362">El motor relacional subyacente no puede realizar cálculos equivalentes a los realizados por el motor xVelocity.</span><span class="sxs-lookup"><span data-stu-id="cc9af-362">The underlying relational engine cannot perform calculations equivalent to those performed by the xVelocity engine.</span></span>  
  
-   <span data-ttu-id="cc9af-363">La fórmula no se puede convertir en una expresión SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="cc9af-363">The formula cannot be converted to en equivalent SQL expression.</span></span>  
  
-   <span data-ttu-id="cc9af-364">El rendimiento de la expresión convertida y de los cálculos resultantes sería inaceptable.</span><span class="sxs-lookup"><span data-stu-id="cc9af-364">The performance of the converted expression and the resulting calculations would be unacceptable.</span></span>  
  
<span data-ttu-id="cc9af-365">Las funciones DAX siguientes no se pueden utilizar en los modelos DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="cc9af-365">The following DAX functions cannot be used in DirectQuery models.</span></span>  
  
<span data-ttu-id="cc9af-366">**Funciones Path**</span><span class="sxs-lookup"><span data-stu-id="cc9af-366">**Path functions**</span></span>  
  
<span data-ttu-id="cc9af-367">PATH</span><span class="sxs-lookup"><span data-stu-id="cc9af-367">PATH</span></span>  
  
<span data-ttu-id="cc9af-368">PATHCONTAINS</span><span class="sxs-lookup"><span data-stu-id="cc9af-368">PATHCONTAINS</span></span>  
  
<span data-ttu-id="cc9af-369">PATHITEM</span><span class="sxs-lookup"><span data-stu-id="cc9af-369">PATHITEM</span></span>  
  
<span data-ttu-id="cc9af-370">PATHITEMREVERSE</span><span class="sxs-lookup"><span data-stu-id="cc9af-370">PATHITEMREVERSE</span></span>  
  
<span data-ttu-id="cc9af-371">PATHLENGTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-371">PATHLENGTH</span></span>  
  
<span data-ttu-id="cc9af-372">**Funciones adicionales**</span><span class="sxs-lookup"><span data-stu-id="cc9af-372">**Misc functions**</span></span>  
  
<span data-ttu-id="cc9af-373">COUNTBLANK</span><span class="sxs-lookup"><span data-stu-id="cc9af-373">COUNTBLANK</span></span>  
  
<span data-ttu-id="cc9af-374">FIXED</span><span class="sxs-lookup"><span data-stu-id="cc9af-374">FIXED</span></span>  
  
<span data-ttu-id="cc9af-375">FORMAT</span><span class="sxs-lookup"><span data-stu-id="cc9af-375">FORMAT</span></span>  
  
<span data-ttu-id="cc9af-376">RAND</span><span class="sxs-lookup"><span data-stu-id="cc9af-376">RAND</span></span>  
  
<span data-ttu-id="cc9af-377">RANDBETWEEN</span><span class="sxs-lookup"><span data-stu-id="cc9af-377">RANDBETWEEN</span></span>  
  
<span data-ttu-id="cc9af-378">**Funciones de inteligencia de tiempo: fechas de inicio y fin**</span><span class="sxs-lookup"><span data-stu-id="cc9af-378">**Time intelligence functions: Start and end dates**</span></span>  
  
<span data-ttu-id="cc9af-379">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-379">DATESQTD</span></span>  
  
<span data-ttu-id="cc9af-380">DATESYTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-380">DATESYTD</span></span>  
  
<span data-ttu-id="cc9af-381">DATESMTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-381">DATESMTD</span></span>  
  
<span data-ttu-id="cc9af-382">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-382">DATESQTD</span></span>  
  
<span data-ttu-id="cc9af-383">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="cc9af-383">DATESINPERIOD</span></span>  
  
<span data-ttu-id="cc9af-384">TOTALMTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-384">TOTALMTD</span></span>  
  
<span data-ttu-id="cc9af-385">TOTALQTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-385">TOTALQTD</span></span>  
  
<span data-ttu-id="cc9af-386">TOTALYTD</span><span class="sxs-lookup"><span data-stu-id="cc9af-386">TOTALYTD</span></span>  
  
<span data-ttu-id="cc9af-387">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="cc9af-387">DATESINPERIOD</span></span>  
  
<span data-ttu-id="cc9af-388">SAMEPERIODLASTYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-388">SAMEPERIODLASTYEAR</span></span>  
  
<span data-ttu-id="cc9af-389">PARALLELPERIOD</span><span class="sxs-lookup"><span data-stu-id="cc9af-389">PARALLELPERIOD</span></span>  
  
<span data-ttu-id="cc9af-390">**Funciones de inteligencia de tiempo: saldos**</span><span class="sxs-lookup"><span data-stu-id="cc9af-390">**Time-intelligence functions: Balances**</span></span>  
  
<span data-ttu-id="cc9af-391">OPENINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-391">OPENINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="cc9af-392">OPENINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="cc9af-392">OPENINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="cc9af-393">OPENINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-393">OPENINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="cc9af-394">CLOSINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-394">CLOSINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="cc9af-395">CLOSINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="cc9af-395">CLOSINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="cc9af-396">CLOSINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-396">CLOSINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="cc9af-397">**Funciones de inteligencia de tiempo: períodos anteriores y siguientes**</span><span class="sxs-lookup"><span data-stu-id="cc9af-397">**Time intelligence functions: Previous and next periods**</span></span>  
  
<span data-ttu-id="cc9af-398">PREVIOUSDAY</span><span class="sxs-lookup"><span data-stu-id="cc9af-398">PREVIOUSDAY</span></span>  
  
<span data-ttu-id="cc9af-399">PREVIOUSMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-399">PREVIOUSMONTH</span></span>  
  
<span data-ttu-id="cc9af-400">PREVIOUSQUARTER</span><span class="sxs-lookup"><span data-stu-id="cc9af-400">PREVIOUSQUARTER</span></span>  
  
<span data-ttu-id="cc9af-401">PREVIOUSYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-401">PREVIOUSYEAR</span></span>  
  
<span data-ttu-id="cc9af-402">NEXTDAY</span><span class="sxs-lookup"><span data-stu-id="cc9af-402">NEXTDAY</span></span>  
  
<span data-ttu-id="cc9af-403">NEXTMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-403">NEXTMONTH</span></span>  
  
<span data-ttu-id="cc9af-404">NEXTQUARTER</span><span class="sxs-lookup"><span data-stu-id="cc9af-404">NEXTQUARTER</span></span>  
  
<span data-ttu-id="cc9af-405">NEXTYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-405">NEXTYEAR</span></span>  
  
<span data-ttu-id="cc9af-406">**Funciones de inteligencia de tiempo: períodos y cálculos durante períodos**</span><span class="sxs-lookup"><span data-stu-id="cc9af-406">**Time intelligence functions: Periods and calculations over periods**</span></span>  
  
<span data-ttu-id="cc9af-407">STARTOFMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-407">STARTOFMONTH</span></span>  
  
<span data-ttu-id="cc9af-408">STARTOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="cc9af-408">STARTOFQUARTER</span></span>  
  
<span data-ttu-id="cc9af-409">STARTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-409">STARTOFYEAR</span></span>  
  
<span data-ttu-id="cc9af-410">ENDOFMONTH</span><span class="sxs-lookup"><span data-stu-id="cc9af-410">ENDOFMONTH</span></span>  
  
<span data-ttu-id="cc9af-411">ENDOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="cc9af-411">ENDOFQUARTER</span></span>  
  
<span data-ttu-id="cc9af-412">ENDOFYEAR</span><span class="sxs-lookup"><span data-stu-id="cc9af-412">ENDOFYEAR</span></span>  
  
<span data-ttu-id="cc9af-413">FIRSTDATE</span><span class="sxs-lookup"><span data-stu-id="cc9af-413">FIRSTDATE</span></span>  
  
<span data-ttu-id="cc9af-414">LASTDATE</span><span class="sxs-lookup"><span data-stu-id="cc9af-414">LASTDATE</span></span>  
  
<span data-ttu-id="cc9af-415">DATEADD</span><span class="sxs-lookup"><span data-stu-id="cc9af-415">DATEADD</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9af-416">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc9af-416">See also</span></span>  
[<span data-ttu-id="cc9af-417">Modo DirectQuery (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="cc9af-417">DirectQuery Mode (SSAS Tabular)</span></span>](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5)  
  

