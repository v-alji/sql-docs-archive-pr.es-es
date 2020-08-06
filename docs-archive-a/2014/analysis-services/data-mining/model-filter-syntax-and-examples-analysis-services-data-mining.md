---
title: Sintaxis y ejemplos del filtro de modelos (Analysis Services-minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744443"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a><span data-ttu-id="98a56-102">Sintaxis y ejemplos del filtro de modelos (Analysis Services: Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="98a56-102">Model Filter Syntax and Examples (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="98a56-103">En esta sección se proporciona información detallada sobre la sintaxis para los filtros de modelo, junto con expresiones de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="98a56-103">This section provides detailed information about the syntax for model filters, together with sample expressions.</span></span>  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a><span data-ttu-id="98a56-104">Sintaxis de filtro</span><span class="sxs-lookup"><span data-stu-id="98a56-104">Filter Syntax</span></span>  
 <span data-ttu-id="98a56-105">Las expresiones de filtro generalmente equivalen al contenido de una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="98a56-105">Filter expressions generally are equivalent to the content of a WHERE clause.</span></span> <span data-ttu-id="98a56-106">Puede conectar varias condiciones usando los operadores lógicos `AND`, `OR` y `NOT`.</span><span class="sxs-lookup"><span data-stu-id="98a56-106">You can connect multiple conditions by using the logical operators `AND`, `OR`, and `NOT`.</span></span>  
  
 <span data-ttu-id="98a56-107">En tablas anidadas, también puede usar los operadores `EXISTS` y `NOT EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="98a56-107">In nested tables, you can also use the `EXISTS` and `NOT EXISTS` operators.</span></span> <span data-ttu-id="98a56-108">Una condición `EXISTS` se evalúa como `true` si la subconsulta devuelve al menos una fila.</span><span class="sxs-lookup"><span data-stu-id="98a56-108">An `EXISTS` condition evaluates to `true` if the subquery returns at least one row.</span></span> <span data-ttu-id="98a56-109">Esto es útil en casos en los que desea restringir el modelo a los casos que contienen un valor determinado en la tabla anidada: por ejemplo, los clientes que han comprado un artículo al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="98a56-109">This is useful in cases where you want to restrict the model to cases that contain a particular value in the nested table: for example, customers who have purchased an item at least once.</span></span>  
  
 <span data-ttu-id="98a56-110">Una condición `NOT EXISTS` se evalúa como `true` si la condición especificada en la subconsulta no existe.</span><span class="sxs-lookup"><span data-stu-id="98a56-110">A `NOT EXISTS` condition evaluates to `true` if the condition specified in the subquery does not exist.</span></span> <span data-ttu-id="98a56-111">Un ejemplo es cuando se desea restringir el modelo a los clientes que nunca han comprado un artículo determinado.</span><span class="sxs-lookup"><span data-stu-id="98a56-111">An example is when you want to restrict the model to customers who have never purchased a particular item.</span></span>  
  
 <span data-ttu-id="98a56-112">La sintaxis general es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="98a56-112">The general syntax is as follows:</span></span>  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 <span data-ttu-id="98a56-113">*filter*</span><span class="sxs-lookup"><span data-stu-id="98a56-113">*filter*</span></span>  
 <span data-ttu-id="98a56-114">Contiene uno o más predicados, conectados por operadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="98a56-114">Contains one or more predicates, connected by logical operators.</span></span>  
  
 <span data-ttu-id="98a56-115">*lista de predicados*</span><span class="sxs-lookup"><span data-stu-id="98a56-115">*predicate list*</span></span>  
 <span data-ttu-id="98a56-116">Una o más expresiones de filtro válidas, separadas por operadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="98a56-116">One or more valid filter expressions, separated by logical operators.</span></span>  
  
 <span data-ttu-id="98a56-117">*columnName*</span><span class="sxs-lookup"><span data-stu-id="98a56-117">*columnName*</span></span>  
 <span data-ttu-id="98a56-118">El nombre de una columna de estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="98a56-118">The name of a mining structure column.</span></span>  
  
 <span data-ttu-id="98a56-119">operador lógico</span><span class="sxs-lookup"><span data-stu-id="98a56-119">logical operator</span></span>  
 <span data-ttu-id="98a56-120">`AND`, `OR`, `NOT`</span><span class="sxs-lookup"><span data-stu-id="98a56-120">`AND`, `OR`, `NOT`</span></span>  
  
 <span data-ttu-id="98a56-121">*avPredicate*</span><span class="sxs-lookup"><span data-stu-id="98a56-121">*avPredicate*</span></span>  
 <span data-ttu-id="98a56-122">Expresión de filtro que solamente se puede aplicar a una columna de estructura de minería de datos escalar.</span><span class="sxs-lookup"><span data-stu-id="98a56-122">Filter expression that can be applied to scalar mining structure column only.</span></span> <span data-ttu-id="98a56-123">Una expresión *avPredicate* se puede usar en ambos filtros de modelos o filtros de tablas anidadas.</span><span class="sxs-lookup"><span data-stu-id="98a56-123">An *avPredicate* expression can be used in both model filters or nested table filters.</span></span>  
  
 <span data-ttu-id="98a56-124">Una expresión que usa cualquiera de los operadores siguientes solo se puede aplicar a una columna continua.</span><span class="sxs-lookup"><span data-stu-id="98a56-124">An expression that uses any of the following operators can only be applied to a continuous column.</span></span> <span data-ttu-id="98a56-125">:</span><span class="sxs-lookup"><span data-stu-id="98a56-125">:</span></span>  
  
-   <span data-ttu-id="98a56-126">**\<**(menor que)</span><span class="sxs-lookup"><span data-stu-id="98a56-126">**\<** (less than)</span></span>  
  
-   <span data-ttu-id="98a56-127">**>**(mayor que)</span><span class="sxs-lookup"><span data-stu-id="98a56-127">**>** (greater than)</span></span>  
  
-   <span data-ttu-id="98a56-128">**>=**(mayor o igual que)</span><span class="sxs-lookup"><span data-stu-id="98a56-128">**>=** (greater than or equal to)</span></span>  
  
-   <span data-ttu-id="98a56-129">**\<=**(menor o igual que)</span><span class="sxs-lookup"><span data-stu-id="98a56-129">**\<=** (less than or equal to)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98a56-130">Sin tener en cuenta el tipo de datos, estos operadores no se pueden aplicar a una columna que tenga el tipo `Discrete`, `Discretized` o `Key`.</span><span class="sxs-lookup"><span data-stu-id="98a56-130">Regardless of the data type, these operators cannot be applied to a column that has the type `Discrete`, `Discretized`, or `Key`.</span></span>  
  
 <span data-ttu-id="98a56-131">Una expresión que usa cualquiera de los operadores siguientes se puede aplicar a una columna de clave continua, discreta o de datos discretos:</span><span class="sxs-lookup"><span data-stu-id="98a56-131">An expression that uses any of the following operators can be applied to a continuous, discrete, discretized, or key column:</span></span>  
  
-   <span data-ttu-id="98a56-132">**=** es igual a</span><span class="sxs-lookup"><span data-stu-id="98a56-132">**=** (equals)</span></span>  
  
-   <span data-ttu-id="98a56-133">**! =** (no es igual a)</span><span class="sxs-lookup"><span data-stu-id="98a56-133">**!=** (not equal to)</span></span>  
  
-   <span data-ttu-id="98a56-134">**ES NULL**</span><span class="sxs-lookup"><span data-stu-id="98a56-134">**IS NULL**</span></span>  
  
 <span data-ttu-id="98a56-135">Si el argumento *avPredicate*se aplica a una columna de datos discretos, el valor usado en el filtro puede ser cualquier valor de un depósito concreto.</span><span class="sxs-lookup"><span data-stu-id="98a56-135">If the argument, *avPredicate*, applies to a discretized column, the value used in the filter can be any value in a specific bucket.</span></span>  
  
 <span data-ttu-id="98a56-136">Es decir, no define la condición como `AgeDisc = '25-35'`, pero en su lugar calcula y, a continuación, usa un valor de ese intervalo.</span><span class="sxs-lookup"><span data-stu-id="98a56-136">In other words, you do not define the condition as `AgeDisc = '25-35'`, but instead compute and then use a value from that interval.</span></span>  
  
 <span data-ttu-id="98a56-137">Ejemplo:  `AgeDisc = 27`  indica cualquier valor del mismo intervalo que 27, que en este caso es 25-35.</span><span class="sxs-lookup"><span data-stu-id="98a56-137">Example:  `AgeDisc = 27`  means any value in the same interval as 27, which in this case is 25-35.</span></span>  
  
 <span data-ttu-id="98a56-138">*nestedTablePredicate*</span><span class="sxs-lookup"><span data-stu-id="98a56-138">*nestedTablePredicate*</span></span>  
 <span data-ttu-id="98a56-139">Expresión de filtro que se aplica a una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-139">Filter expression that applies to a nested table.</span></span> <span data-ttu-id="98a56-140">Solo se puede usar en filtros de modelos.</span><span class="sxs-lookup"><span data-stu-id="98a56-140">Can be used in model filters only.</span></span>  
  
 <span data-ttu-id="98a56-141">El argumento de subconsulta de *nestedTablePredicate*solamente se puede aplicar a una columna de estructura de minería de datos de tabla.</span><span class="sxs-lookup"><span data-stu-id="98a56-141">The sub-query argument of the argument, *nestedTablePredicate*, can only apply to a table mining structure column</span></span>  
  
 <span data-ttu-id="98a56-142">subconsulta</span><span class="sxs-lookup"><span data-stu-id="98a56-142">subquery</span></span>  
 <span data-ttu-id="98a56-143">Instrucción SELECT seguida de un predicado válido o una lista de predicados.</span><span class="sxs-lookup"><span data-stu-id="98a56-143">A SELECT statement followed by a valid predicate or list of predicates.</span></span>  
  
 <span data-ttu-id="98a56-144">Todos los predicados deben ser del tipo que se describe en *avPredicates*.</span><span class="sxs-lookup"><span data-stu-id="98a56-144">All the predicates must be of the type described in *avPredicates*.</span></span> <span data-ttu-id="98a56-145">Además, los predicados solo pueden hacer referencia a las columnas incluidas en la tabla anidada actual, identificadas por el argumento *columnName*.</span><span class="sxs-lookup"><span data-stu-id="98a56-145">Furthermore, the predicates can refer only to columns that are included in the current nested table, identified by the argument, *columnName*.</span></span>  
  
### <a name="limitations-on-filter-syntax"></a><span data-ttu-id="98a56-146">Limitaciones en la sintaxis de filtro</span><span class="sxs-lookup"><span data-stu-id="98a56-146">Limitations on Filter Syntax</span></span>  
 <span data-ttu-id="98a56-147">A los filtros se les aplican las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="98a56-147">The following restrictions apply to filters:</span></span>  
  
-   <span data-ttu-id="98a56-148">Un filtro solamente puede contener predicados simples.</span><span class="sxs-lookup"><span data-stu-id="98a56-148">A filter can contain only simple predicates.</span></span> <span data-ttu-id="98a56-149">Entre estos se incluyen operadores matemáticos, escalares y nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="98a56-149">These include mathematical operators, scalars, and column names.</span></span>  
  
-   <span data-ttu-id="98a56-150">No se admiten las funciones definidas por el usuario en la sintaxis del filtro.</span><span class="sxs-lookup"><span data-stu-id="98a56-150">User-defined functions are not supported in the filter syntax.</span></span>  
  
-   <span data-ttu-id="98a56-151">No se admiten los operadores no booleanos, como los signos más o menos, en la sintaxis del filtro.</span><span class="sxs-lookup"><span data-stu-id="98a56-151">Non-Boolean operators, such as the plus or minus signs, are not supported in the filter syntax.</span></span>  
  
## <a name="examples-of-filters"></a><span data-ttu-id="98a56-152">Ejemplos de filtros</span><span class="sxs-lookup"><span data-stu-id="98a56-152">Examples of Filters</span></span>  
 <span data-ttu-id="98a56-153">Los ejemplos siguientes muestran el uso de filtros aplicados a un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="98a56-153">The following examples demonstrate the use of filters applied to a mining model.</span></span> <span data-ttu-id="98a56-154">Si crea la expresión de filtro usando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en la ventana **Propiedad** y el panel **Expresión** del cuadro de diálogo de filtros, vería solamente la cadena que aparece después de las palabras clave WITH FILTER.</span><span class="sxs-lookup"><span data-stu-id="98a56-154">If you create the filter expression by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Property** window and the **Expression** pane of the filter dialog box, you would see only the string that appears after the WITH FILTER keywords.</span></span> <span data-ttu-id="98a56-155">Aquí, la definición de la estructura de minería de datos está incluida para facilitar la comprensión del uso y del tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="98a56-155">Here, the definition of the mining structure is included to make it easier to understand the column type and usage.</span></span>  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a> <span data-ttu-id="98a56-156">Ejemplo 1: Filtrado de nivel de caso típico</span><span class="sxs-lookup"><span data-stu-id="98a56-156">Example 1: Typical Case-Level Filtering</span></span>  
 <span data-ttu-id="98a56-157">Este ejemplo muestra un filtro simple que restringe los casos usados en el modelo a los clientes cuya profesión sea arquitecto y sean mayores de 30 años.</span><span class="sxs-lookup"><span data-stu-id="98a56-157">This example shows a simple filter that restricts the cases used in the model to customers whose occupation is architect and whose age is over 30.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a> <span data-ttu-id="98a56-158">Ejemplo 2: filtrado de nivel de caso usando atributos de tabla anidada</span><span class="sxs-lookup"><span data-stu-id="98a56-158">Example 2: Case-Level Filtering using Nested Table Attributes</span></span>  
 <span data-ttu-id="98a56-159">Si su estructura de minería de datos contiene tablas anidadas, puede filtrar por la existencia de un valor en una tabla anidada o filtrar en filas de tabla anidada que contienen un valor concreto.</span><span class="sxs-lookup"><span data-stu-id="98a56-159">If your mining structure contains nested tables, you can either filter on the existence of a value in a nested table, or filter on nested table rows that contain a specific value.</span></span> <span data-ttu-id="98a56-160">Este ejemplo restringe los casos usados para el modelo a los clientes mayores de 30 años que realizaron al menos una compra que incluía la leche.</span><span class="sxs-lookup"><span data-stu-id="98a56-160">This example restricts the cases used for the model to customers over the age of 30 who made at least one purchase that included milk.</span></span>  
  
 <span data-ttu-id="98a56-161">Como se muestra en este ejemplo, no es necesario que el filtro use solamente las columnas incluidas en el modelo.</span><span class="sxs-lookup"><span data-stu-id="98a56-161">As this example shows, it is not necessary that the filter use only columns that are included in the model.</span></span> <span data-ttu-id="98a56-162">La tabla anidada **Products** forma parte de la estructura de minería de datos pero no está incluida en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="98a56-162">The nested table **Products** is part of the mining structure, but is not included in the mining model.</span></span> <span data-ttu-id="98a56-163">Sin embargo, todavía puede filtrar por los valores y atributos de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-163">However, you can still filter on values and attributes in the nested table.</span></span> <span data-ttu-id="98a56-164">Para ver los detalles de estos casos, la obtención de detalles debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="98a56-164">To view the details of these cases, drillthrough must be enabled.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a> <span data-ttu-id="98a56-165">Ejemplo 3: filtrado del nivel de caso en varios atributos de tabla anidada</span><span class="sxs-lookup"><span data-stu-id="98a56-165">Example 3: Case-Level Filtering on Multiple Nested Table Attributes</span></span>  
 <span data-ttu-id="98a56-166">En este ejemplo se muestra un filtro de tres partes: se aplica una condición a la tabla de casos, otra condición a un atributo de la tabla anidada y otra, en un valor concreto de una de las columnas de tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-166">This example shows a three-part filter: a condition applies to the case table, another condition to an attribute in the nested table, and another condition on a specific value in one of the nested table columns.</span></span>  
  
 <span data-ttu-id="98a56-167">La primera condición del filtro, `Age > 30`, se aplica a una columna de la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="98a56-167">The first condition in the filter, `Age > 30`, applies to a column in the case table.</span></span> <span data-ttu-id="98a56-168">Las condiciones restantes se aplican a la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-168">The remaining conditions apply to the nested table.</span></span>  
  
 <span data-ttu-id="98a56-169">La segunda condición, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, comprueba la presencia de al menos una compra en la tabla anidada que incluía la leche.</span><span class="sxs-lookup"><span data-stu-id="98a56-169">The second condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, checks for the presence of at least one purchase in the nested table that included milk.</span></span> <span data-ttu-id="98a56-170">La tercera condición, `Quantity>=2`, significa que el cliente debe haber comprado al menos dos unidades de leche en una transacción única.</span><span class="sxs-lookup"><span data-stu-id="98a56-170">The third condition, `Quantity>=2`, means that the customer must have purchased at least two units of milk in a single transaction.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a> <span data-ttu-id="98a56-171">Ejemplo 4: filtrado del nivel de caso en ausencia de atributos de tabla anidada</span><span class="sxs-lookup"><span data-stu-id="98a56-171">Example 4: Case-Level Filtering On Absence of Nested Table Attributes</span></span>  
 <span data-ttu-id="98a56-172">En este ejemplo se muestra cómo limitar los casos al cliente que no compró un artículo específico, filtrando por la ausencia de un atributo en la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-172">This example shows how to limit cases to customer who did not purchase a specific item, by filtering on the absence of an attribute in the nested table.</span></span> <span data-ttu-id="98a56-173">En este ejemplo, el modelo se entrena usando clientes mayores de 30 años que nunca han comprado leche.</span><span class="sxs-lookup"><span data-stu-id="98a56-173">In this example, the model is trained using customers over the age of 30 who have never bought milk.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a> <span data-ttu-id="98a56-174">Ejemplo 5: filtrado por varios valores de tabla anidada</span><span class="sxs-lookup"><span data-stu-id="98a56-174">Example 5: Filtering on Multiple Nested Table Values</span></span>  
 <span data-ttu-id="98a56-175">El propósito del ejemplo es mostrar el filtrado de tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-175">The purpose of the example is to show nested table filtering.</span></span> <span data-ttu-id="98a56-176">El filtro de tabla anidada se aplica después del filtro de casos y solamente restringe las filas de tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="98a56-176">The nested table filter is applied after the case filter, and only restricts nested table rows.</span></span>  
  
 <span data-ttu-id="98a56-177">Este modelo podría contener varios casos con tablas anidadas vacías porque no se especifica EXISTS.</span><span class="sxs-lookup"><span data-stu-id="98a56-177">This model could contain multiple cases with empty nested tables because EXISTS is not specified.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a> <span data-ttu-id="98a56-178">Ejemplo 6: filtrar por los atributos de tabla anidada y EXISTS</span><span class="sxs-lookup"><span data-stu-id="98a56-178">Example 6: Filtering on Nested Table Attributes and EXISTS</span></span>  
 <span data-ttu-id="98a56-179">En este ejemplo, el filtro en la tabla anidada restringe las filas a aquéllas que contienen leche o agua embotellada.</span><span class="sxs-lookup"><span data-stu-id="98a56-179">In this example, the filter on the nested table restricts the rows to those that contain either milk or bottled water.</span></span> <span data-ttu-id="98a56-180">A continuación, los casos del modelo se restringen usando una instrucción `EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="98a56-180">Then, the cases in the model are restricted by using an `EXISTS` statement.</span></span> <span data-ttu-id="98a56-181">Esto asegura que la tabla anidada no está vacía.</span><span class="sxs-lookup"><span data-stu-id="98a56-181">This makes sure that the nested table is not empty.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a> <span data-ttu-id="98a56-182">Ejemplo 7: combinaciones de filtros complejas</span><span class="sxs-lookup"><span data-stu-id="98a56-182">Example 7: Complex Filter Combinations</span></span>  
 <span data-ttu-id="98a56-183">El escenario para este modelo se parece al del ejemplo 4 pero es mucho más complejo.</span><span class="sxs-lookup"><span data-stu-id="98a56-183">The scenario for this model resembles that of Example 4, but is far more complex.</span></span> <span data-ttu-id="98a56-184">La tabla anidada, **ProductsOnSale**, tiene la condición `(OnSale)` de filtro que significa que el valor de **alventa** debe ser `true` para el producto enumerado en **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="98a56-184">The nested table, **ProductsOnSale**, has the filter condition `(OnSale)` meaning that the value of **OnSale** must be `true` for the product listed in **ProductName**.</span></span> <span data-ttu-id="98a56-185">Aquí, **OnSale** es una columna de estructura.</span><span class="sxs-lookup"><span data-stu-id="98a56-185">Here, **OnSale** is a structure column.</span></span>  
  
 <span data-ttu-id="98a56-186">La segunda parte del filtro, para **ProductsNotOnSale**, repite esta sintaxis, pero filtra los productos para los que el valor de **alventa** es `not true``(!OnSale)` .</span><span class="sxs-lookup"><span data-stu-id="98a56-186">The second part of the filter, for **ProductsNotOnSale**, repeats this syntax, but filters on products for which the value of **OnSale** is `not true``(!OnSale)`.</span></span>  
  
 <span data-ttu-id="98a56-187">Finalmente, se combinan las condiciones y se agrega una restricción adicional a la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="98a56-187">Finally, the conditions are combined and one additional restriction is added to the case table.</span></span> <span data-ttu-id="98a56-188">El resultado es predecir compras de productos en la lista **ProductsNotOnSale** , basándose en los casos incluidos en la lista **ProductsOnSale** , para todos los clientes mayores de 25.</span><span class="sxs-lookup"><span data-stu-id="98a56-188">The result is to predict purchases of products in the **ProductsNotOnSale** list, based on the cases that are included in the **ProductsOnSale** list, for all customers over the age of 25.</span></span>  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a> <span data-ttu-id="98a56-189">Ejemplo 8: filtrar según las fechas</span><span class="sxs-lookup"><span data-stu-id="98a56-189">Example 8: Filtering on Dates</span></span>  
 <span data-ttu-id="98a56-190">Puede filtrar las columnas de entrada según fechas, como con cualquier otro dato.</span><span class="sxs-lookup"><span data-stu-id="98a56-190">You can filter input columns on dates, as you would any other data.</span></span> <span data-ttu-id="98a56-191">Las fechas contenidas en una columna del tipo de fecha y hora son valores continuos; por consiguiente, puede especificar un intervalo de fechas utilizando a operadores como mayor que (>) o menor que (<).</span><span class="sxs-lookup"><span data-stu-id="98a56-191">Dates contained in a column of type date/time are continuous values; therefore, you can specify a date range by using operators such as greater than (>) or less than (<).</span></span> <span data-ttu-id="98a56-192">Si el origen de datos no representa las fechas por un tipo de datos continuo, sino como valores discretos o de texto, no puede filtrar en un intervalo de fechas, sino que debe especificar valores discretos e individuales.</span><span class="sxs-lookup"><span data-stu-id="98a56-192">If your data source does not represent dates by a Continuous data type, but as discrete or text values, you cannot filter on a date range, but must specify individual discrete values.</span></span>  
  
 <span data-ttu-id="98a56-193">Sin embargo, no puede crear un filtro en la columna de fecha en un modelo del serie temporal si la columna de fecha utilizada para el filtro también es la columna de clave para el modelo.</span><span class="sxs-lookup"><span data-stu-id="98a56-193">However, you cannot create a filter on the date column in a time series model if the date column used for the filter is also the key column for the model.</span></span> <span data-ttu-id="98a56-194">Eso se debe a que, en los modelos de series temporales y de agrupación en clústeres de secuencia, la columna de fecha podría tratarse como de tipo `KeyTime` o `KeySequence`.</span><span class="sxs-lookup"><span data-stu-id="98a56-194">That is because, in time series models and sequence clustering models, the date column might be handled as type `KeyTime` or `KeySequence`.</span></span>  
  
 <span data-ttu-id="98a56-195">Si necesita filtrar en fechas continuas en un modelo de serie temporal, puede crear una copia de la columna en la estructura de minería de datos y filtrar el modelo en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="98a56-195">If you need to filter on continuous dates in a time series model, you can create a copy of the column in the mining structure, and filter the model on the new column.</span></span>  
  
 <span data-ttu-id="98a56-196">Por ejemplo, la siguiente expresión representa un filtro en una columna de fecha de tipo `Continuous` que se ha agregado al modelo de previsión.</span><span class="sxs-lookup"><span data-stu-id="98a56-196">For example, the following expression represents a filter on a date column of type `Continuous` that has been added to the Forecasting model.</span></span>  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  <span data-ttu-id="98a56-197">Observe que cualquier columna adicional que agregue al modelo podría afectar a los resultados.</span><span class="sxs-lookup"><span data-stu-id="98a56-197">Note that any extra columns that you add to the model might affect the results.</span></span> <span data-ttu-id="98a56-198">Por consiguiente, si no desea utilizar la columna en el cálculo de la serie, solo debería agregar la columna a la estructura de minería de datos y no al modelo.</span><span class="sxs-lookup"><span data-stu-id="98a56-198">Therefore, if you do not want the column to be used in computation of the series, you should add the column only to the mining structure, and not to the model.</span></span> <span data-ttu-id="98a56-199">También puede establecer la marca de modelo de la columna en `PredictOnly` o en `Ignore`.</span><span class="sxs-lookup"><span data-stu-id="98a56-199">You can also set the model flag on the column to `PredictOnly` or to `Ignore`.</span></span> <span data-ttu-id="98a56-200">Para obtener más información, vea [Marcas de modelado &#40;Minería de datos&#41;](modeling-flags-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="98a56-200">For more information, see [Modeling Flags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span></span>  
  
 <span data-ttu-id="98a56-201">En el caso de otros tipos de modelo, puede utilizar fechas como criterios de entrada o como criterios de filtro igual que con cualquier otra columna.</span><span class="sxs-lookup"><span data-stu-id="98a56-201">For other model types, you can use dates as input criteria or filter criteria just like you would in any other column.</span></span> <span data-ttu-id="98a56-202">Sin embargo, si tiene que utilizar un nivel concreto de granularidad que un tipo de datos `Continuous` no admita, puede crear un valor derivado en el origen de datos utilizando expresiones para extraer la unidad que se usará en el filtro y el análisis.</span><span class="sxs-lookup"><span data-stu-id="98a56-202">However, if you need to use a specific level of granularity that is not supported by a `Continuous` data type, you can create a derived value in the data source by using expressions to extract the unit to use in filtering and analysis.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="98a56-203">Cuando especifique fechas como criterios de filtro, debe usar el siguiente formato, independientemente del formato de fecha del sistema operativo actual: `mm/dd/yyyy`.</span><span class="sxs-lookup"><span data-stu-id="98a56-203">When you specify a dates as filter criteria, you must use the following format, regardless of the date format for the current OS: `mm/dd/yyyy`.</span></span> <span data-ttu-id="98a56-204">Cualquier otro formato produce un error.</span><span class="sxs-lookup"><span data-stu-id="98a56-204">Any other format results in an error.</span></span>  
  
 <span data-ttu-id="98a56-205">Por ejemplo, si desea filtrar los resultados del centro de llamada para mostrar solo los fines de semana, puede crear una expresión en la vista del origen de datos que extraiga el nombre del día de la semana para cada fecha y, a continuación, utilizar ese el valor de nombre de día de la semana para la entrada o como un valor discreto en el filtro.</span><span class="sxs-lookup"><span data-stu-id="98a56-205">For example, if you want to filter your call center results to show only weekends, you can create an expression in the data source view that extracts the weekday name for each date, and then use that weekday name value for input or as a discrete value in filtering.</span></span> <span data-ttu-id="98a56-206">Recuerde solo que los valores repetidos pueden afectar al modelo, de modo que debiera utilizar únicamente una de las columnas y no la columna de fecha más el valor derivado.</span><span class="sxs-lookup"><span data-stu-id="98a56-206">Just remember that repeating values can affect the model, so you should use only one of the columns, not the date column plus the derived value.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="98a56-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98a56-207">See Also</span></span>  
 <span data-ttu-id="98a56-208">[Filtros para modelos de minería de datos &#40;Analysis Services-minería de datos&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="98a56-208">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="98a56-209">Prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="98a56-209">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
  
