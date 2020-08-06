---
title: Usar conjuntos de columnas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- sparse columns, column sets
- column sets
ms.assetid: a4f9de95-dc8f-4ad8-b957-137e32bfa500
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cb496137c3986b78a55862e434c153d354a42ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677503"
---
# <a name="use-column-sets"></a><span data-ttu-id="b94fa-102">Usar conjuntos de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-102">Use Column Sets</span></span>
  <span data-ttu-id="b94fa-103">Las tablas que utilizan columnas dispersas pueden designar un conjunto de columnas que devuelva todas las columnas dispersas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-103">Tables that use sparse columns can designate a column set to return all sparse columns in the table.</span></span> <span data-ttu-id="b94fa-104">Un conjunto de columnas es una representación XML sin tipo que combina todas las columnas dispersas de una tabla en una salida estructurada.</span><span class="sxs-lookup"><span data-stu-id="b94fa-104">A column set is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="b94fa-105">Un conjunto de columnas se asemeja a una columna calculada en que el conjunto no se almacena físicamente en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-105">A column set is like a calculated column in that the column set is not physically stored in the table.</span></span> <span data-ttu-id="b94fa-106">Un conjunto de columnas difiere de una columna calculada en que el conjunto de columnas se puede actualizar directamente.</span><span class="sxs-lookup"><span data-stu-id="b94fa-106">A column set differs from a calculated column in that the column set is directly updatable.</span></span>  
  
 <span data-ttu-id="b94fa-107">Considere la posibilidad de usar los conjuntos de columnas cuando una tabla contenga un gran número de columnas y resulte complicado realizar cualquier operación con ellas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-107">You should consider using column sets when the number of columns in a table is large, and operating on them individually is cumbersome.</span></span> <span data-ttu-id="b94fa-108">Las aplicaciones pueden experimentar ciertas mejoras de rendimiento si realizan la selección e inserción de datos usando los conjuntos de columnas en tablas que contienen muchas columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-108">Applications might see some performance improvement when they select and insert data by using column sets on tables that have lots of columns.</span></span> <span data-ttu-id="b94fa-109">Sin embargo, es posible que se reduzca el rendimiento de los conjuntos de columnas si se definen muchos índices en las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-109">However, the performance of column sets can be reduced when many indexes are defined on the columns in the table.</span></span> <span data-ttu-id="b94fa-110">Esto es debido a que aumenta la cantidad de memoria necesaria para un plan de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b94fa-110">This is because the amount of memory that is required for an execution plan increases.</span></span>  
  
 <span data-ttu-id="b94fa-111">Para definir un conjunto de columnas, use las palabras clave *<nombreDeConjuntoDeColumnas>* FOR ALL_SPARSE_COLUMN de las instrucciones [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) o [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b94fa-111">To define a column set, use the *<column_set_name>* FOR ALL_SPARSE_COLUMNS keywords in the[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) or [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) statements.</span></span>  
  
## <a name="guidelines-for-using-column-sets"></a><span data-ttu-id="b94fa-112">Directrices para usar conjuntos de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-112">Guidelines for Using Column Sets</span></span>  
 <span data-ttu-id="b94fa-113">Cuando use conjuntos de columnas, tenga en cuenta las directrices siguientes:</span><span class="sxs-lookup"><span data-stu-id="b94fa-113">When you use column sets, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="b94fa-114">Se pueden agregar columnas dispersas y un conjunto de columnas como parte de la misma instrucción.</span><span class="sxs-lookup"><span data-stu-id="b94fa-114">Sparse columns and a column set can be added as part of the same statement.</span></span>  
  
-   <span data-ttu-id="b94fa-115">El conjunto de columnas no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="b94fa-115">The column set cannot be changed.</span></span> <span data-ttu-id="b94fa-116">Para modificar un conjunto de columnas, es preciso eliminarlo y volver a crearlo.</span><span class="sxs-lookup"><span data-stu-id="b94fa-116">To change a column set, you must delete and re-create the column set.</span></span>  
  
-   <span data-ttu-id="b94fa-117">No se puede agregar un conjunto de columnas a una tabla si ésta ya contiene columnas dispersas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-117">A column set cannot be added to a table if that table already contains sparse columns.</span></span>  
  
-   <span data-ttu-id="b94fa-118">Se puede agregar un conjunto de columnas a una tabla si ésta no incluye ninguna columna dispersa.</span><span class="sxs-lookup"><span data-stu-id="b94fa-118">A column set can be added to a table that does not include any sparse columns.</span></span> <span data-ttu-id="b94fa-119">Si posteriormente se agregan columnas dispersas a la tabla, dichas columnas aparecerán en el conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-119">If sparse columns are later added to the table, they will appear in the column set.</span></span>  
  
-   <span data-ttu-id="b94fa-120">Solo se permite un conjunto de columnas por tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-120">Only one column set is allowed per table.</span></span>  
  
-   <span data-ttu-id="b94fa-121">El conjunto de columnas es opcional y no es necesario para usar columnas dispersas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-121">A column set is optional and is not required to use sparse columns.</span></span>  
  
-   <span data-ttu-id="b94fa-122">No se pueden definir restricciones ni valores predeterminados en un conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-122">Constraints or default values cannot be defined on a column set.</span></span>  
  
-   <span data-ttu-id="b94fa-123">Las columnas calculadas no pueden contener columnas del conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-123">Computed columns cannot contain column set columns.</span></span>  
  
-   <span data-ttu-id="b94fa-124">Las consultas distribuidas no se pueden utilizar en tablas que contienen conjuntos de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-124">Distributed queries are not supported on tables that contain column sets.</span></span>  
  
-   <span data-ttu-id="b94fa-125">La replicación no admite conjuntos de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-125">Replication does not support column sets.</span></span>  
  
-   <span data-ttu-id="b94fa-126">La captura de datos modificados no admite conjuntos de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-126">Change data capture does not support column sets.</span></span>  
  
-   <span data-ttu-id="b94fa-127">Un conjunto de columnas no puede formar parte de ningún tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="b94fa-127">A column set cannot be part of any kind of index.</span></span> <span data-ttu-id="b94fa-128">Esto incluye índices XML, índices de texto completo y vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-128">This includes XML indexes, full-text indexes, and indexed views.</span></span> <span data-ttu-id="b94fa-129">Un conjunto de columnas no se puede agregar como columna incluida en ningún índice.</span><span class="sxs-lookup"><span data-stu-id="b94fa-129">A column set cannot be added as an included column in any index.</span></span>  
  
-   <span data-ttu-id="b94fa-130">Un conjunto de columnas no se puede utilizar en la expresión de filtro de un índice filtrado o de estadísticas filtradas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-130">A column set cannot be used in the filter expression of a filtered index or filtered statistics.</span></span>  
  
-   <span data-ttu-id="b94fa-131">Cuando una vista incluye un conjunto de columnas, éste aparece en la vista como una columna XML.</span><span class="sxs-lookup"><span data-stu-id="b94fa-131">When a view includes a column set, the column set appears in the view as an XML column.</span></span>  
  
-   <span data-ttu-id="b94fa-132">Un conjunto de columnas no se puede incluir en la definición de una vista indizada.</span><span class="sxs-lookup"><span data-stu-id="b94fa-132">A column set cannot be included in an indexed view definition.</span></span>  
  
-   <span data-ttu-id="b94fa-133">Las vistas con particiones que incluyen tablas que contienen conjuntos de columnas se actualizan cuando la vista con particiones especifica las columnas dispersas por nombre.</span><span class="sxs-lookup"><span data-stu-id="b94fa-133">Partitioned views that include tables that contain column sets are updatable when the partitioned view specifies the sparse columns by name.</span></span> <span data-ttu-id="b94fa-134">Una vista con particiones no se actualiza cuando hace referencia al conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-134">A partitioned view is not updatable when it references the column set.</span></span>  
  
-   <span data-ttu-id="b94fa-135">Las notificaciones de consulta que hacen referencia a conjuntos de columnas no se permiten.</span><span class="sxs-lookup"><span data-stu-id="b94fa-135">Query notifications that refer to column sets are not permitted.</span></span>  
  
-   <span data-ttu-id="b94fa-136">Los datos XML tienen un límite de tamaño de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="b94fa-136">XML data has a size limit of 2 GB.</span></span> <span data-ttu-id="b94fa-137">Si los datos combinados de todas las columnas dispersas cuyo valor de una fila no sea NULL superan este límite, la consulta o la operación DML generará un error.</span><span class="sxs-lookup"><span data-stu-id="b94fa-137">If the combined data of all the nonnull sparse columns in a row exceeds this limit, the query or DML operation will produce an error.</span></span>  
  
-   <span data-ttu-id="b94fa-138">Para obtener más información sobre los datos devueltos por la función COLUMNS_UPDATED, vea [Usar columnas dispersas](use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="b94fa-138">For information about the data that is returned by the COLUMNS_UPDATED function, see [Use Sparse Columns](use-sparse-columns.md).</span></span>  
  
## <a name="guidelines-for-selecting-data-from-a-column-set"></a><span data-ttu-id="b94fa-139">Directrices para seleccionar datos de un conjunto de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-139">Guidelines for Selecting Data from a Column Set</span></span>  
 <span data-ttu-id="b94fa-140">Tenga en cuenta las directrices siguientes a la hora de seleccionar datos de un conjunto de columnas:</span><span class="sxs-lookup"><span data-stu-id="b94fa-140">Consider the following guidelines for selecting data from a column set:</span></span>  
  
-   <span data-ttu-id="b94fa-141">Conceptualmente, un conjunto de columnas es un tipo de columna XML calculada y actualizable que agrega un conjunto de columnas relacionales subyacentes en una única representación XML.</span><span class="sxs-lookup"><span data-stu-id="b94fa-141">Conceptually, a column set is a type of updatable, computed XML column that aggregates a set of underlying relational columns into a single XML representation.</span></span> <span data-ttu-id="b94fa-142">El conjunto de columnas solo admite la propiedad ALL_SPARSE_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="b94fa-142">The column set only supports the ALL_SPARSE_COLUMNS property.</span></span> <span data-ttu-id="b94fa-143">Esta propiedad se usa para agregar todos los valores distintos de NULL de todas las columnas dispersas para una fila determinada.</span><span class="sxs-lookup"><span data-stu-id="b94fa-143">This property is used to aggregate all nonnull values from all sparse columns for a particular row.</span></span>  
  
-   <span data-ttu-id="b94fa-144">En el editor de tablas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , los conjuntos de columnas se muestran como un campo XML modificable.</span><span class="sxs-lookup"><span data-stu-id="b94fa-144">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] table editor, column sets are displayed as an editable XML field.</span></span> <span data-ttu-id="b94fa-145">Defina los conjuntos de columnas con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="b94fa-145">Define column sets in the format:</span></span>  
  
    ```  
    <column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...  
    ```  
  
     <span data-ttu-id="b94fa-146">A continuación se enumeran algunos ejemplos de valores de conjuntos de columnas:</span><span class="sxs-lookup"><span data-stu-id="b94fa-146">Examples of column set values are as follows:</span></span>  
  
    -   `<sparseProp1>10</sparseProp1><sparseProp3>20</sparseProp3>`  
  
    -   `<DocTitle>Bicycle Parts List</DocTitle><Region>West</Region>`  
  
-   <span data-ttu-id="b94fa-147">Las columnas dispersas que contienen valores NULL se omiten en la representación XML del conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-147">Sparse columns that contain null values are omitted from the XML representation for the column set.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="b94fa-148">Al agregar un conjunto de columnas, cambia el comportamiento de las consultas SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="b94fa-148">Adding a column set changes the behavior of SELECT \* queries.</span></span> <span data-ttu-id="b94fa-149">La consulta devolverá el conjunto de columnas como una columna XML, pero no devolverá las columnas dispersas individuales.</span><span class="sxs-lookup"><span data-stu-id="b94fa-149">The query will return the column set as an XML column and not return the individual sparse columns.</span></span> <span data-ttu-id="b94fa-150">Los diseñadores de esquemas y los desarrolladores deben tener cuidado de no alterar el comportamiento de las aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="b94fa-150">Schema designers and software developers must be careful not to break existing applications.</span></span>  
  
## <a name="inserting-or-modifying-data-in-a-column-set"></a><span data-ttu-id="b94fa-151">Insertar o modificar datos en un conjunto de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-151">Inserting or Modifying Data in a Column Set</span></span>  
 <span data-ttu-id="b94fa-152">La manipulación de los datos de una columna dispersa se puede llevar a cabo usando el nombre de las columnas individuales, o bien haciendo referencia al nombre del conjunto de columnas y especificando sus valores usando el formato XML de dicho conjunto.</span><span class="sxs-lookup"><span data-stu-id="b94fa-152">Data manipulation of a sparse column can be performed by using the name of the individual columns, or by referencing the name of the column set and specifying the values of the column set by using the XML format of the column set.</span></span> <span data-ttu-id="b94fa-153">Las columnas dispersas pueden aparecer en cualquier orden en la columna XML.</span><span class="sxs-lookup"><span data-stu-id="b94fa-153">Sparse columns can appear in any order in the XML column.</span></span>  
  
 <span data-ttu-id="b94fa-154">Cuando se insertan o actualizan valores de columnas dispersas usando el conjunto de columnas XML, los valores que se insertan en las columnas dispersas subyacentes se convierten de manera implícita desde el tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="b94fa-154">When sparse column values are inserted or updated by using the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="b94fa-155">En el caso de columnas numéricas, un valor en blanco en el XML para la columna numérica se convierte en una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="b94fa-155">In the case of numeric columns, a blank value in the XML for the numeric column converts to an empty string.</span></span> <span data-ttu-id="b94fa-156">Esto hace que se inserte un cero en la columna numérica, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b94fa-156">This causes a zero to be inserted into the numeric column as shown in the following example.</span></span>  
  
```  
CREATE TABLE t (i int SPARSE, cs xml column_set FOR ALL_SPARSE_COLUMNS);  
GO  
INSERT t(cs) VALUES ('<i/>');  
GO  
SELECT i FROM t;  
GO  
```  
  
 <span data-ttu-id="b94fa-157">En este ejemplo, no se ha especificado ningún valor para la columna `i`, pero se ha insertado el valor `0` .</span><span class="sxs-lookup"><span data-stu-id="b94fa-157">In this example, no value was specified for the column `i`, but the value `0` was inserted.</span></span>  
  
## <a name="using-the-sql_variant-data-type"></a><span data-ttu-id="b94fa-158">Usar el tipo de datos sql_variant</span><span class="sxs-lookup"><span data-stu-id="b94fa-158">Using the sql_variant Data Type</span></span>  
 <span data-ttu-id="b94fa-159">El tipo de datos `sql_variant` puede almacenar varios tipos de datos distintos, como `int`, `char` y `date`.</span><span class="sxs-lookup"><span data-stu-id="b94fa-159">The `sql_variant` date type can store multiple different data types, such as `int`, `char`, and `date`.</span></span> <span data-ttu-id="b94fa-160">Los conjuntos de columnas generan la información sobre el tipo de datos, como la escala, la precisión y la información de configuración regional que se asocia a un valor `sql_variant`, como atributos en la columna XML generada.</span><span class="sxs-lookup"><span data-stu-id="b94fa-160">Column sets output the data type information such as scale, precision, and locale information that is associated with a `sql_variant` value as attributes in the generated XML column.</span></span> <span data-ttu-id="b94fa-161">Si intenta proporcionar estos atributos en una instrucción XML generada de forma personalizada como una entrada para una operación de inserción o de actualización en un conjunto de columnas, algunos de dichos atributos son obligatorios y a otros se les asigna un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b94fa-161">If you try to provide these attributes in a custom-generated XML statement as an input for an insert or update operation on a column set, some of these attributes are required and some of them are assigned a default value.</span></span> <span data-ttu-id="b94fa-162">En la tabla siguiente se enumeran los tipos de datos y los valores predeterminados que genera el servidor cuando no se proporciona el valor.</span><span class="sxs-lookup"><span data-stu-id="b94fa-162">The following table lists the data types and the default values that the server generates when the value is not provided.</span></span>  
  
|<span data-ttu-id="b94fa-163">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b94fa-163">Data type</span></span>|<span data-ttu-id="b94fa-164">localeID\*</span><span class="sxs-lookup"><span data-stu-id="b94fa-164">localeID\*</span></span>|<span data-ttu-id="b94fa-165">sqlCompareOptions</span><span class="sxs-lookup"><span data-stu-id="b94fa-165">sqlCompareOptions</span></span>|<span data-ttu-id="b94fa-166">sqlCollationVersion</span><span class="sxs-lookup"><span data-stu-id="b94fa-166">sqlCollationVersion</span></span>|<span data-ttu-id="b94fa-167">SqlSortId</span><span class="sxs-lookup"><span data-stu-id="b94fa-167">SqlSortId</span></span>|<span data-ttu-id="b94fa-168">Longitud máxima</span><span class="sxs-lookup"><span data-stu-id="b94fa-168">Maximum length</span></span>|<span data-ttu-id="b94fa-169">Precision</span><span class="sxs-lookup"><span data-stu-id="b94fa-169">Precision</span></span>|<span data-ttu-id="b94fa-170">Escala</span><span class="sxs-lookup"><span data-stu-id="b94fa-170">Scale</span></span>|  
|---------------|----------------|-----------------------|-------------------------|---------------|--------------------|---------------|-----------|  
|<span data-ttu-id="b94fa-171">`char`, `varchar`, `binary`</span><span class="sxs-lookup"><span data-stu-id="b94fa-171">`char`, `varchar`, `binary`</span></span>|<span data-ttu-id="b94fa-172">-1</span><span class="sxs-lookup"><span data-stu-id="b94fa-172">-1</span></span>|<span data-ttu-id="b94fa-173">'Default'</span><span class="sxs-lookup"><span data-stu-id="b94fa-173">'Default'</span></span>|<span data-ttu-id="b94fa-174">0</span><span class="sxs-lookup"><span data-stu-id="b94fa-174">0</span></span>|<span data-ttu-id="b94fa-175">0</span><span class="sxs-lookup"><span data-stu-id="b94fa-175">0</span></span>|<span data-ttu-id="b94fa-176">8000</span><span class="sxs-lookup"><span data-stu-id="b94fa-176">8000</span></span>|<span data-ttu-id="b94fa-177">No aplicable\*\*</span><span class="sxs-lookup"><span data-stu-id="b94fa-177">Not applicable\*\*</span></span>|<span data-ttu-id="b94fa-178">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-178">Not applicable</span></span>|  
|`nvarchar`|<span data-ttu-id="b94fa-179">-1</span><span class="sxs-lookup"><span data-stu-id="b94fa-179">-1</span></span>|<span data-ttu-id="b94fa-180">'Default'</span><span class="sxs-lookup"><span data-stu-id="b94fa-180">'Default'</span></span>|<span data-ttu-id="b94fa-181">0</span><span class="sxs-lookup"><span data-stu-id="b94fa-181">0</span></span>|<span data-ttu-id="b94fa-182">0</span><span class="sxs-lookup"><span data-stu-id="b94fa-182">0</span></span>|<span data-ttu-id="b94fa-183">4000</span><span class="sxs-lookup"><span data-stu-id="b94fa-183">4000</span></span>|<span data-ttu-id="b94fa-184">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-184">Not applicable</span></span>|<span data-ttu-id="b94fa-185">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-185">Not applicable</span></span>|  
|<span data-ttu-id="b94fa-186">`decimal`, `float`, `real`</span><span class="sxs-lookup"><span data-stu-id="b94fa-186">`decimal`, `float`, `real`</span></span>|<span data-ttu-id="b94fa-187">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-187">Not applicable</span></span>|<span data-ttu-id="b94fa-188">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-188">Not applicable</span></span>|<span data-ttu-id="b94fa-189">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-189">Not applicable</span></span>|<span data-ttu-id="b94fa-190">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-190">Not applicable</span></span>|<span data-ttu-id="b94fa-191">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-191">Not applicable</span></span>|<span data-ttu-id="b94fa-192">18</span><span class="sxs-lookup"><span data-stu-id="b94fa-192">18</span></span>|<span data-ttu-id="b94fa-193">0</span><span class="sxs-lookup"><span data-stu-id="b94fa-193">0</span></span>|  
|<span data-ttu-id="b94fa-194">`integer`, `bigint`, `tinyint`, `smallint`</span><span class="sxs-lookup"><span data-stu-id="b94fa-194">`integer`, `bigint`, `tinyint`, `smallint`</span></span>|<span data-ttu-id="b94fa-195">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-195">Not applicable</span></span>|<span data-ttu-id="b94fa-196">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-196">Not applicable</span></span>|<span data-ttu-id="b94fa-197">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-197">Not applicable</span></span>|<span data-ttu-id="b94fa-198">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-198">Not applicable</span></span>|<span data-ttu-id="b94fa-199">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-199">Not applicable</span></span>|<span data-ttu-id="b94fa-200">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-200">Not applicable</span></span>|<span data-ttu-id="b94fa-201">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-201">Not applicable</span></span>|  
|`datetime2`|<span data-ttu-id="b94fa-202">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-202">Not applicable</span></span>|<span data-ttu-id="b94fa-203">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-203">Not applicable</span></span>|<span data-ttu-id="b94fa-204">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-204">Not applicable</span></span>|<span data-ttu-id="b94fa-205">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-205">Not applicable</span></span>|<span data-ttu-id="b94fa-206">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-206">Not applicable</span></span>|<span data-ttu-id="b94fa-207">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-207">Not applicable</span></span>|<span data-ttu-id="b94fa-208">7</span><span class="sxs-lookup"><span data-stu-id="b94fa-208">7</span></span>|  
|`datetime offset`|<span data-ttu-id="b94fa-209">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-209">Not applicable</span></span>|<span data-ttu-id="b94fa-210">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-210">Not applicable</span></span>|<span data-ttu-id="b94fa-211">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-211">Not applicable</span></span>|<span data-ttu-id="b94fa-212">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-212">Not applicable</span></span>|<span data-ttu-id="b94fa-213">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-213">Not applicable</span></span>|<span data-ttu-id="b94fa-214">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-214">Not applicable</span></span>|<span data-ttu-id="b94fa-215">7</span><span class="sxs-lookup"><span data-stu-id="b94fa-215">7</span></span>|  
|<span data-ttu-id="b94fa-216">`datetime`, `date`, `smalldatetime`</span><span class="sxs-lookup"><span data-stu-id="b94fa-216">`datetime`, `date`, `smalldatetime`</span></span>|<span data-ttu-id="b94fa-217">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-217">Not applicable</span></span>|<span data-ttu-id="b94fa-218">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-218">Not applicable</span></span>|<span data-ttu-id="b94fa-219">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-219">Not applicable</span></span>|<span data-ttu-id="b94fa-220">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-220">Not applicable</span></span>|<span data-ttu-id="b94fa-221">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-221">Not applicable</span></span>|<span data-ttu-id="b94fa-222">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-222">Not applicable</span></span>|<span data-ttu-id="b94fa-223">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-223">Not applicable</span></span>|  
|<span data-ttu-id="b94fa-224">`money`, `smallmoney`</span><span class="sxs-lookup"><span data-stu-id="b94fa-224">`money`, `smallmoney`</span></span>|<span data-ttu-id="b94fa-225">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-225">Not applicable</span></span>|<span data-ttu-id="b94fa-226">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-226">Not applicable</span></span>|<span data-ttu-id="b94fa-227">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-227">Not applicable</span></span>|<span data-ttu-id="b94fa-228">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-228">Not applicable</span></span>|<span data-ttu-id="b94fa-229">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-229">Not applicable</span></span>|<span data-ttu-id="b94fa-230">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-230">Not applicable</span></span>|<span data-ttu-id="b94fa-231">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-231">Not applicable</span></span>|  
|`time`|<span data-ttu-id="b94fa-232">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-232">Not applicable</span></span>|<span data-ttu-id="b94fa-233">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-233">Not applicable</span></span>|<span data-ttu-id="b94fa-234">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-234">Not applicable</span></span>|<span data-ttu-id="b94fa-235">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-235">Not applicable</span></span>|<span data-ttu-id="b94fa-236">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-236">Not applicable</span></span>|<span data-ttu-id="b94fa-237">No aplicable</span><span class="sxs-lookup"><span data-stu-id="b94fa-237">Not applicable</span></span>|<span data-ttu-id="b94fa-238">7</span><span class="sxs-lookup"><span data-stu-id="b94fa-238">7</span></span>|  
  
 <span data-ttu-id="b94fa-239">\*  Un valor -1 en localeID significa la configuración regional predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b94fa-239">\*  localeID -1 means the default locale.</span></span> <span data-ttu-id="b94fa-240">La configuración regional en inglés es 1033.</span><span class="sxs-lookup"><span data-stu-id="b94fa-240">The English locale is 1033.</span></span>  
  
 <span data-ttu-id="b94fa-241">No aplicable = No se genera ningún valor para estos atributos durante una operación de selección en el conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-241">\*\*  Not applicable = No values are output for these attributes during a select operation on the column set.</span></span> <span data-ttu-id="b94fa-242">Genera un error cuando el autor de la llamada especifica un valor para este atributo en la representación XML proporcionada para un conjunto de columnas durante una operación de inserción o actualización.</span><span class="sxs-lookup"><span data-stu-id="b94fa-242">Generates an error when a value is specified for this attribute by the caller in the XML representation provided for a column set in an insert or update operation.</span></span>  
  
## <a name="security"></a><span data-ttu-id="b94fa-243">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b94fa-243">Security</span></span>  
 <span data-ttu-id="b94fa-244">El modelo de seguridad para un conjunto de columnas funciona de forma similar al modelo de seguridad existente entre la tabla y columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-244">The security model for a column set works similar to the security model that exists between table and columns.</span></span> <span data-ttu-id="b94fa-245">Los conjuntos de columnas se pueden visualizar en forma de minitabla, en la que una operación de selección funciona como una operación SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="b94fa-245">Column sets can be visualized as a minitable and a select operation is like a SELECT \* operation on this minitable.</span></span> <span data-ttu-id="b94fa-246">Pero la relación entre el conjunto de columnas y las columnas dispersas es una relación de agrupación en lugar de ser estrictamente un contenedor.</span><span class="sxs-lookup"><span data-stu-id="b94fa-246">But, the relationship between column set to sparse columns is a grouping relationship instead of strictly a container.</span></span> <span data-ttu-id="b94fa-247">El modelo de seguridad comprueba la seguridad en la columna del conjunto de columnas y respeta las operaciones DENY en las columnas dispersas subyacentes.</span><span class="sxs-lookup"><span data-stu-id="b94fa-247">The security model checks the security on the column set column, and honors the DENY operations on the underlying sparse columns.</span></span> <span data-ttu-id="b94fa-248">Las características adicionales del modelo de seguridad son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b94fa-248">Additional characteristics of the security model are as follows:</span></span>  
  
-   <span data-ttu-id="b94fa-249">Los permisos de seguridad se pueden otorgar y revocar desde la columna del conjunto de columnas, de forma similar a como se haría en cualquier otra columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-249">Security permissions can be granted and revoked from the column set column, similar to any other column in the table.</span></span>  
  
-   <span data-ttu-id="b94fa-250">Una instrucción GRANT o REVOKE para los permisos SELECT, INSERT, UPDATE, DELETE o REFERENCES en una columna del conjunto de columnas no se propaga a las columnas miembro subyacentes de dicho conjunto.</span><span class="sxs-lookup"><span data-stu-id="b94fa-250">A GRANT or REVOKE of SELECT, INSERT, UPDATE, DELETE, and REFERENCES permission on a column set column does not propagate to the underlying member columns of that set.</span></span> <span data-ttu-id="b94fa-251">Solo se aplica al uso de la columna del conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-251">It applies only to the usage of the column set column.</span></span> <span data-ttu-id="b94fa-252">El permiso DENY en un conjunto de columnas sí se propaga a las columnas dispersas subyacentes de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-252">DENY permission on a column set does propagate to the underlying sparse columns of the table.</span></span>  
  
-   <span data-ttu-id="b94fa-253">La ejecución de las instrucciones SELECT, INSERT, UPDATE y DELETE en la columna del conjunto de columnas requiere que el usuario disponga de los permisos correspondientes en dicha columna, así como en todas las columnas dispersas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-253">Executing SELECT, INSERT, UPDATE, and DELETE statements on the column set column require that the user has corresponding permissions on the column set column, and also the corresponding permission on all the sparse columns in the table.</span></span> <span data-ttu-id="b94fa-254">Dado que el conjunto de columnas representa todas las columnas dispersas de la tabla, debe tener el permiso correspondiente en estas columnas, y esto incluye aquellas columnas dispersas que no va a modificar.</span><span class="sxs-lookup"><span data-stu-id="b94fa-254">Because the column set represents all the sparse columns in the table, you must have permission on all the sparse columns, and this includes sparse columns that you might not be changing.</span></span>  
  
-   <span data-ttu-id="b94fa-255">La ejecución de una instrucción REVOKE en una columna dispersa o en un conjunto de columnas hace que éstas adopten la configuración de seguridad de su objeto primario.</span><span class="sxs-lookup"><span data-stu-id="b94fa-255">Executing a REVOKE statement on a sparse column or column set defaults the security to their parent object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b94fa-256">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b94fa-256">Examples</span></span>  
 <span data-ttu-id="b94fa-257">En los ejemplos siguientes, una tabla de documentos contiene el conjunto de columnas común `DocID` y `Title`.</span><span class="sxs-lookup"><span data-stu-id="b94fa-257">In the following examples, a document table contains the common set of columns `DocID` and `Title`.</span></span> <span data-ttu-id="b94fa-258">El grupo de producción desea tener una columna `ProductionSpecification` y una columna `ProductionLocation` para todos los documentos de producción.</span><span class="sxs-lookup"><span data-stu-id="b94fa-258">The Production group wants a `ProductionSpecification` and `ProductionLocation` column for all production documents.</span></span> <span data-ttu-id="b94fa-259">El grupo de marketing desea tener una columna `MarketingSurveyGroup` para los documentos de marketing.</span><span class="sxs-lookup"><span data-stu-id="b94fa-259">The Marketing group wants a `MarketingSurveyGroup` column for marketing documents.</span></span>  
  
### <a name="a-creating-a-table-that-has-a-column-set"></a><span data-ttu-id="b94fa-260">A.</span><span class="sxs-lookup"><span data-stu-id="b94fa-260">A.</span></span> <span data-ttu-id="b94fa-261">Crear una tabla que tenga un conjunto de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-261">Creating a table that has a column set</span></span>  
 <span data-ttu-id="b94fa-262">En el ejemplo siguiente se crea la tabla que utiliza columnas dispersas y se incluye el conjunto de columnas `SpecialPurposeColumns`.</span><span class="sxs-lookup"><span data-stu-id="b94fa-262">The following example creates the table that uses sparse columns and includes the column set `SpecialPurposeColumns`.</span></span> <span data-ttu-id="b94fa-263">El ejemplo inserta dos filas en la tabla y, a continuación, selecciona datos de dicha tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-263">The example inserts two rows into the table, and then selects data from the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b94fa-264">Esta tabla solo tiene cinco columnas para facilitar su visualización y lectura.</span><span class="sxs-lookup"><span data-stu-id="b94fa-264">This table has only five columns to make it easier to display and read.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
CREATE TABLE DocumentStoreWithColumnSet  
    (DocID int PRIMARY KEY,  
     Title varchar(200) NOT NULL,  
     ProductionSpecification varchar(20) SPARSE NULL,  
     ProductionLocation smallint SPARSE NULL,  
     MarketingSurveyGroup varchar(20) SPARSE NULL,  
     MarketingProgramID int SPARSE NULL,  
     SpecialPurposeColumns XML COLUMN_SET FOR ALL_SPARSE_COLUMNS);  
GO  
```  
  
### <a name="b-inserting-data-to-a-table-by-using-the-names-of-the-sparse-columns"></a><span data-ttu-id="b94fa-265">B.</span><span class="sxs-lookup"><span data-stu-id="b94fa-265">B.</span></span> <span data-ttu-id="b94fa-266">Insertar datos en una tabla usando los nombres de las columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="b94fa-266">Inserting data to a table by using the names of the sparse columns</span></span>  
 <span data-ttu-id="b94fa-267">En los ejemplos siguientes se insertan dos filas en la tabla creada en el ejemplo A. Estos ejemplos utilizan los nombres de las columnas dispersas y no hacen referencia al conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-267">The following examples insert two rows into the table that is created in example A. The examples use the names of the sparse columns and do not reference the column set.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, ProductionSpecification, ProductionLocation)  
VALUES (1, 'Tire Spec 1', 'AXZZ217', 27);  
GO  
  
INSERT DocumentStoreWithColumnSet (DocID, Title, MarketingSurveyGroup)  
VALUES (2, 'Survey 2142', 'Men 25 - 35');  
GO  
```  
  
### <a name="c-inserting-data-to-a-table-by-using-the-name-of-the-column-set"></a><span data-ttu-id="b94fa-268">C.</span><span class="sxs-lookup"><span data-stu-id="b94fa-268">C.</span></span> <span data-ttu-id="b94fa-269">Insertar datos en una tabla usando el nombre del conjunto de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-269">Inserting data to a table by using the name of the column set</span></span>  
 <span data-ttu-id="b94fa-270">En el ejemplo siguiente se inserta una tercera fila en la tabla creada en el ejemplo A. Esta vez no se utilizan los nombres de las columnas dispersas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-270">The following example inserts a third row into the table that is created in example A. This time the names of the sparse columns are not used.</span></span> <span data-ttu-id="b94fa-271">En su lugar, se utiliza el nombre del conjunto de columnas y la operación de inserción proporciona los valores para dos de las cuatro columnas dispersas en formato XML.</span><span class="sxs-lookup"><span data-stu-id="b94fa-271">Instead, the name of the column set is used, and the insert provides the values for two of the four sparse columns in XML format.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, SpecialPurposeColumns)  
VALUES (3, 'Tire Spec 2', '<ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>');  
GO  
```  
  
### <a name="d-observing-the-results-of-a-column-set-when-select--is-used"></a><span data-ttu-id="b94fa-272">D.</span><span class="sxs-lookup"><span data-stu-id="b94fa-272">D.</span></span> <span data-ttu-id="b94fa-273">Observar los resultados de un conjunto de columnas al usar SELECT \*</span><span class="sxs-lookup"><span data-stu-id="b94fa-273">Observing the results of a column set when SELECT \* is used</span></span>  
 <span data-ttu-id="b94fa-274">En el ejemplo siguiente se seleccionan todas las columnas de la tabla que contiene un conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-274">The following example selects all the columns from the table that contains a column set.</span></span> <span data-ttu-id="b94fa-275">Devuelve una columna XML con los valores combinados de las columnas dispersas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-275">It returns an XML column with the combined values of the sparse columns.</span></span> <span data-ttu-id="b94fa-276">No devuelve las columnas dispersas de forma individual.</span><span class="sxs-lookup"><span data-stu-id="b94fa-276">It does not return the sparse columns individually.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns FROM DocumentStoreWithColumnSet ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1      Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `2      Survey 2142  <MarketingSurveyGroup>Men 25 - 35</MarketingSurveyGroup>`  
  
 `3      Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="e-observing-the-results-of-selecting-the-column-set-by-name"></a><span data-ttu-id="b94fa-277">E.</span><span class="sxs-lookup"><span data-stu-id="b94fa-277">E.</span></span> <span data-ttu-id="b94fa-278">Observar los resultados de seleccionar el conjunto de columnas por nombre</span><span class="sxs-lookup"><span data-stu-id="b94fa-278">Observing the results of selecting the column set by name</span></span>  
 <span data-ttu-id="b94fa-279">Dado que el departamento de producción no está interesado en los datos de marketing, en este ejemplo se agrega una cláusula `WHERE` para restringir la salida.</span><span class="sxs-lookup"><span data-stu-id="b94fa-279">Because the Production department is not interested in the marketing data, this example adds a `WHERE` clause to restrict the output.</span></span> <span data-ttu-id="b94fa-280">El ejemplo usa el nombre del conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-280">The example uses the name of the column set.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns  
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1     Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `3     Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="f-observing-the-results-of-selecting-sparse-columns-by-name"></a><span data-ttu-id="b94fa-281">F.</span><span class="sxs-lookup"><span data-stu-id="b94fa-281">F.</span></span> <span data-ttu-id="b94fa-282">Observar los resultados de seleccionar columnas dispersas por nombre</span><span class="sxs-lookup"><span data-stu-id="b94fa-282">Observing the results of selecting sparse columns by name</span></span>  
 <span data-ttu-id="b94fa-283">Si una tabla contiene un conjunto de columnas, también se puede consultar dicha tabla usando los nombres de columna individuales, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b94fa-283">When a table contains a column set, you can still query the table by using the individual column names as shown in the following example.</span></span>  
  
```  
SELECT DocID, Title, ProductionSpecification, ProductionLocation   
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        ProductionSpecification ProductionLocation`  
  
 `1     Tire Spec 1  AXZZ217                 27`  
  
 `3     Tire Spec 2  AXW9R411                38`  
  
### <a name="g-updating-a-table-by-using-a-column-set"></a><span data-ttu-id="b94fa-284">G.</span><span class="sxs-lookup"><span data-stu-id="b94fa-284">G.</span></span> <span data-ttu-id="b94fa-285">Actualizar una tabla usando un conjunto de columnas</span><span class="sxs-lookup"><span data-stu-id="b94fa-285">Updating a table by using a column set</span></span>  
 <span data-ttu-id="b94fa-286">En el ejemplo siguiente se actualiza el tercer registro con nuevos valores para las dos columnas dispersas que usa la fila.</span><span class="sxs-lookup"><span data-stu-id="b94fa-286">The following example updates the third record with new values for both sparse columns that are used by that row.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification><ProductionLocation>38</ProductionLocation>'  
WHERE DocID = 3 ;  
GO  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b94fa-287">Una instrucción UPDATE que usa un conjunto de columnas actualiza todas las columnas dispersas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b94fa-287">An UPDATE statement that uses a column set updates all the sparse columns in the table.</span></span> <span data-ttu-id="b94fa-288">Los valores de las columnas dispersas a las que no se hace referencia se actualizan a NULL.</span><span class="sxs-lookup"><span data-stu-id="b94fa-288">Sparse columns that are not referenced are updated to NULL.</span></span>  
  
 <span data-ttu-id="b94fa-289">En el ejemplo siguiente se actualiza el tercer registro, pero solo se especifica el valor de una de las dos columnas rellenadas.</span><span class="sxs-lookup"><span data-stu-id="b94fa-289">The following example updates the third record, but only specifies the value of one of the two populated columns.</span></span> <span data-ttu-id="b94fa-290">La segunda columna, `ProductionLocation` , no está incluida en la instrucción `UPDATE` y se actualiza a NULL.</span><span class="sxs-lookup"><span data-stu-id="b94fa-290">The second column `ProductionLocation` is not included in the `UPDATE` statement and is updated to NULL.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification>'  
WHERE DocID = 3 ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b94fa-291">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b94fa-291">See Also</span></span>  
 [<span data-ttu-id="b94fa-292">Usar columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="b94fa-292">Use Sparse Columns</span></span>](use-sparse-columns.md)  
  
  
