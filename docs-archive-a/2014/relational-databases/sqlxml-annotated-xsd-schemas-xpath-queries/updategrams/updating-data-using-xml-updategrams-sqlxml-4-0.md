---
title: Actualizar datos mediante diagramas XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREF type attribute [SQLXML]
- before attribute
- <sync> block
- <after> block
- id attribute
- <before> block
- updg:after attribute
- mapping-schema attribute
- IDREFS type attribute [SQLXML]
- updg:id attribute
- multiple record updates
- after attribute
- updategrams [SQLXML], updating data
- updg:before attribute
- record updates [SQLXML]
ms.assetid: 90ef8a33-5ae3-4984-8259-608d2f1d727f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6b019478868b61f293eda824d9b302099728dec4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674732"
---
# <a name="updating-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="28f04-102">Actualizar datos con diagramas de actualización XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="28f04-102">Updating Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="28f04-103">Al actualizar los datos existentes, debe especificar los dos **\<before>** bloques y **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="28f04-103">When you update existing data, you must specify both the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="28f04-104">Los elementos especificados en **\<before>** los **\<after>** bloques y describen el cambio deseado.</span><span class="sxs-lookup"><span data-stu-id="28f04-104">The elements specified in the **\<before>** and **\<after>** blocks describe the desired change.</span></span> <span data-ttu-id="28f04-105">Diagrama usa los elementos que se especifican en el **\<before>** bloque para identificar los registros existentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-105">The updategram uses the element(s) that are specified in the **\<before>** block to identify the existing record(s) in the database.</span></span> <span data-ttu-id="28f04-106">Los elementos correspondientes en el **\<after>** bloque indican cómo deben ser los registros después de ejecutar la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-106">The corresponding element(s) in the **\<after>** block indicate how the records should look after executing the update operation.</span></span> <span data-ttu-id="28f04-107">A partir de esta información, diagrama crea una instrucción SQL que coincide con el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="28f04-107">From this information, the updategram creates an SQL statement that matches the **\<after>** block.</span></span> <span data-ttu-id="28f04-108">A continuación, el diagrama de actualización utiliza esta instrucción para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-108">The updategram then uses this statement to update the database.</span></span>  
  
 <span data-ttu-id="28f04-109">Este es el formato del diagrama de actualización para una operación de actualización:</span><span class="sxs-lookup"><span data-stu-id="28f04-109">This is the updategram format for an update operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
      <ElementName [updg:id="value"] .../>  
      [<ElementName [updg:id="value"] .../> ... ]  
   </updg:before>  
   <updg:after>  
      <ElementName [updg:id="value"] ... />  
      [<ElementName [updg:id="value"] .../> ...]  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 `<updg:before>`  
 <span data-ttu-id="28f04-110">Los elementos del **\<before>** bloque identifican los registros existentes en las tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-110">The elements in the **\<before>** block identify existing records in the database tables.</span></span>  
  
 `<updg:after>`  
 <span data-ttu-id="28f04-111">Los elementos del **\<after>** bloque describen cómo deben ser los registros especificados en el **\<before>** bloque después de aplicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="28f04-111">The elements in the **\<after>** block describe how the records specified in the **\<before>** block should look after the updates are applied.</span></span>  
  
 <span data-ttu-id="28f04-112">El atributo `mapping-schema` identifica el esquema de asignación que va a ser utilizado por el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-112">The `mapping-schema` attribute identifies the mapping schema to be used by the updategram.</span></span> <span data-ttu-id="28f04-113">Si diagrama especifica un esquema de asignación, los nombres de elemento y atributo especificados en los **\<before>** **\<after>** bloques y deben coincidir con los nombres del esquema.</span><span class="sxs-lookup"><span data-stu-id="28f04-113">If the updategram specifies a mapping schema, the element and attribute names specified in the **\<before>** and **\<after>** blocks must match the names in the schema.</span></span> <span data-ttu-id="28f04-114">El esquema de asignación asigna estos nombres de elementos o atributos a los nombres de columnas y tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-114">The mapping schema maps these element or attribute names to the database table and column names.</span></span>  
  
 <span data-ttu-id="28f04-115">Si un diagrama de actualización no especifica un esquema, utilizará la asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="28f04-115">If an updategram does not specify a schema, the updategam uses default mapping.</span></span> <span data-ttu-id="28f04-116">En la asignación predeterminada, el **\<ElementName>** especificado en diagrama se asigna a la tabla de base de datos y los elementos secundarios o atributos se asignan a las columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-116">In default mapping, the **\<ElementName>** specified in the updategram maps to the database table and the child elements or attributes map to the database columns.</span></span>  
  
 <span data-ttu-id="28f04-117">Un elemento del **\<before>** bloque debe coincidir con solo una fila de la tabla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-117">An element in the **\<before>** block must match with only one table row in the database.</span></span> <span data-ttu-id="28f04-118">Si el elemento coincide con varias filas de la tabla o no coincide con ninguna fila de la tabla, diagrama devuelve un error y cancela el **\<sync>** bloque completo.</span><span class="sxs-lookup"><span data-stu-id="28f04-118">If the element either matches multiple table rows or does not match any table row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span>  
  
 <span data-ttu-id="28f04-119">Un diagrama puede incluir varios **\<sync>** bloques.</span><span class="sxs-lookup"><span data-stu-id="28f04-119">An updategram can include multiple **\<sync>** blocks.</span></span> <span data-ttu-id="28f04-120">Cada **\<sync>** bloque se trata como una transacción.</span><span class="sxs-lookup"><span data-stu-id="28f04-120">Each **\<sync>** block is treated as a transaction.</span></span> <span data-ttu-id="28f04-121">Cada **\<sync>** bloque puede tener varios **\<before>** **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="28f04-121">Each **\<sync>** block can have multiple **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="28f04-122">Por ejemplo, si está actualizando dos de los registros existentes, puede especificar dos **\<before>** pares de y **\<after>** , uno para cada registro que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="28f04-122">For example, if you are updating two of the existing records, you could specify two **\<before>** and **\<after>** pairs, one for each record being updated.</span></span>  
  
## <a name="using-the-updgid-attribute"></a><span data-ttu-id="28f04-123">Utilizar el atributo updg:id</span><span class="sxs-lookup"><span data-stu-id="28f04-123">Using the updg:id Attribute</span></span>  
 <span data-ttu-id="28f04-124">Cuando se especifican varios elementos en **\<before>** los **\<after>** bloques y, utilice el `updg:id` atributo para marcar las filas en los **\<before>** **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="28f04-124">When multiple elements are specified in the **\<before>** and **\<after>** blocks, use the `updg:id` attribute to mark rows in the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="28f04-125">La lógica de procesamiento utiliza esta información para determinar qué registro en los **\<before>** pares de bloques con qué registro hay en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="28f04-125">The processing logic uses this information to determine what record in the **\<before>** block pairs with what record in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="28f04-126">El atributo `updg:id` no es necesario (aunque se recomienda) si se da alguna de las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="28f04-126">The `updg:id` attribute is not necessary (although recommended) if either of the following exists:</span></span>  
  
-   <span data-ttu-id="28f04-127">Los elementos del esquema de asignación especificado tienen definido el atributo `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="28f04-127">The elements in the specified mapping schema have the `sql:key-fields` attribute defined on them.</span></span>  
  
-   <span data-ttu-id="28f04-128">Hay uno o más valores concretos proporcionados para los campos de clave del diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-128">There is one or more specific value supplied for the key field(s) in the updategram.</span></span>  
  
 <span data-ttu-id="28f04-129">Si es así, el diagrama usa las columnas de clave que se especifican en `sql:key-fields` para emparejar los elementos de los **\<before>** **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="28f04-129">If either is the case, the updategram uses the key columns that are specified in the `sql:key-fields` to pair the elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="28f04-130">Si el esquema de asignación no identifica las columnas de clave (utilizando `sql:key-fields`) o si el diagrama de actualización está actualizando un valor de columna de clave, se debe especificar `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="28f04-130">If the mapping schema does not identify key columns (by using `sql:key-fields`) or if the updategram is updating a key column value, you must specify `updg:id`.</span></span>  
  
 <span data-ttu-id="28f04-131">Los registros que se identifican en **\<before>** los **\<after>** bloques y no tienen que estar en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="28f04-131">The records that are identified in the **\<before>** and **\<after>** blocks do not have to be in the same order.</span></span> <span data-ttu-id="28f04-132">El `updg:id` atributo fuerza la asociación entre los elementos que se especifican en **\<before>** los **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="28f04-132">The `updg:id` attribute forces the association between the elements that are specified in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="28f04-133">Si especifica un elemento en el **\<before>** bloque y solo un elemento correspondiente en el **\<after>** bloque, el uso de `updg:id` no es necesario.</span><span class="sxs-lookup"><span data-stu-id="28f04-133">If you specify one element in the **\<before>** block and only one corresponding element in the **\<after>** block, using `updg:id` is not necessary.</span></span> <span data-ttu-id="28f04-134">Sin embargo, se recomienda que de todas formas especifique `updg:id` para evitar la ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="28f04-134">However, it is recommended that you specify `updg:id` anyway to avoid ambiguity.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="28f04-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="28f04-135">Examples</span></span>  
 <span data-ttu-id="28f04-136">Antes de utilizar los ejemplos del diagrama de actualización, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28f04-136">Before you use the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="28f04-137">En la mayoría de los ejemplos se usa una asignación predeterminada (es decir, no se especifica ningún esquema de asignación en el diagrama de actualización).</span><span class="sxs-lookup"><span data-stu-id="28f04-137">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="28f04-138">Para obtener más ejemplos de diagramas que usan esquemas de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-138">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="28f04-139">La mayoría de los ejemplos utilizan la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="28f04-139">Most of the examples use the AdventureWorks sample database.</span></span> <span data-ttu-id="28f04-140">Todas las actualizaciones se aplican a las tablas de esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-140">All the updates are applied to the tables in this database.</span></span> <span data-ttu-id="28f04-141">Puede restaurar la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="28f04-141">You can restore the AdventureWorks database.</span></span>  
  
### <a name="a-updating-a-record"></a><span data-ttu-id="28f04-142">A.</span><span class="sxs-lookup"><span data-stu-id="28f04-142">A.</span></span> <span data-ttu-id="28f04-143">Actualizar un registro</span><span class="sxs-lookup"><span data-stu-id="28f04-143">Updating a record</span></span>  
 <span data-ttu-id="28f04-144">El siguiente diagrama de actualización actualiza el apellido del empleado a Fuller en la tabla Person.Contact de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="28f04-144">The following updategram updates the employee last name to Fuller in the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="28f04-145">El diagrama de actualización no especifica ningún esquema de asignación, por lo que utilizará la asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="28f04-145">The updategram does not specify any mapping schema; therefore, the updategram uses default mapping.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact LastName="Abel-Achong" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="28f04-146">El registro descrito en el **\<before>** bloque representa el registro actual de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-146">The record described in the **\<before>** block represents the current record in the database.</span></span> <span data-ttu-id="28f04-147">Diagrama usa todos los valores de columna especificados en el **\<before>** bloque para buscar el registro.</span><span class="sxs-lookup"><span data-stu-id="28f04-147">The updategram uses all of the column values specified in the **\<before>** block to search for the record.</span></span> <span data-ttu-id="28f04-148">En este diagrama, el **\<before>** bloque proporciona solo la columna ContactID; por lo tanto, el diagrama usa solo el valor para buscar el registro.</span><span class="sxs-lookup"><span data-stu-id="28f04-148">In this updategram, the **\<before>** block provides only the ContactID column; therefore, the updategram uses only the value to search for the record.</span></span> <span data-ttu-id="28f04-149">Si fuera a agregar el valor LastName a este bloque, el diagrama de actualización utilizaría los valores ContactID y LastName para buscar.</span><span class="sxs-lookup"><span data-stu-id="28f04-149">If you were to add the LastName value to this block, the updategram would use both the ContactID and LastName values to search.</span></span>  
  
 <span data-ttu-id="28f04-150">En este diagrama, el **\<after>** bloque proporciona solo el valor de la columna LastName porque es el único valor que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="28f04-150">In this updategram, the **\<after>** block provides only the LastName column value because this is the only value that is being changed.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="28f04-151">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="28f04-151">To test the updategram</span></span>  
  
1.  <span data-ttu-id="28f04-152">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-152">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="28f04-153">Guarde el archivo como UpdateLastName.xml.</span><span class="sxs-lookup"><span data-stu-id="28f04-153">Save the file as UpdateLastName.xml.</span></span>  
  
2.  <span data-ttu-id="28f04-154">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-154">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="28f04-155">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-155">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="b-updating-multiple-records-by-using-the-updgid-attribute"></a><span data-ttu-id="28f04-156">B.</span><span class="sxs-lookup"><span data-stu-id="28f04-156">B.</span></span> <span data-ttu-id="28f04-157">Actualizar varios registros utilizando el atributo updg:id</span><span class="sxs-lookup"><span data-stu-id="28f04-157">Updating multiple records by using the updg:id attribute</span></span>  
 <span data-ttu-id="28f04-158">En este ejemplo, el diagrama de actualización realiza dos actualizaciones en la tabla HumanResources.Shift de la base de datos AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="28f04-158">In this example, the updategram performs two updates on the HumanResources.Shift table in the AdventureWorks database:</span></span>  
  
-   <span data-ttu-id="28f04-159">Cambia el nombre del turno de día original, que empieza a las 7:00 a. m., de "Day" a "Early Morning".</span><span class="sxs-lookup"><span data-stu-id="28f04-159">It changes the name of the original day shift that starts at 7:00AM from "Day" to "Early Morning".</span></span>  
  
-   <span data-ttu-id="28f04-160">Inserta un nuevo turno denominado "Late Morning" que empieza a las 10:00 a. m.</span><span class="sxs-lookup"><span data-stu-id="28f04-160">It inserts a new shift named "Late Morning" that starts at 10:00AM.</span></span>  
  
 <span data-ttu-id="28f04-161">En diagrama, el `updg:id` atributo crea asociaciones entre los elementos de los **\<before>** **\<after>** bloques y.</span><span class="sxs-lookup"><span data-stu-id="28f04-161">In the updategram, the `updg:id` attribute creates associations between elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift updg:id="x" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift updg:id="y" Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
      <HumanResources.Shift updg:id="x" Name="Early Morning" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="28f04-162">Observe cómo el `updg:id` atributo empareja la primera instancia del \<HumanResources.Shift> elemento en el **\<before>** bloque con la segunda instancia del \<HumanResources.Shift> elemento en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="28f04-162">Notice how the `updg:id` attribute pairs the first instance of the \<HumanResources.Shift> element in the **\<before>** block with the second instance of the \<HumanResources.Shift> element in the **\<after>** block.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="28f04-163">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="28f04-163">To test the updategram</span></span>  
  
1.  <span data-ttu-id="28f04-164">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-164">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="28f04-165">Guarde el archivo como UpdateMultipleRecords.xml.</span><span class="sxs-lookup"><span data-stu-id="28f04-165">Save the file as UpdateMultipleRecords.xml.</span></span>  
  
2.  <span data-ttu-id="28f04-166">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-166">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="28f04-167">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-167">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="c-specifying-multiple-before-and-after-blocks"></a><span data-ttu-id="28f04-168">C.</span><span class="sxs-lookup"><span data-stu-id="28f04-168">C.</span></span> <span data-ttu-id="28f04-169">Especificar varios \<before> bloques and \<after></span><span class="sxs-lookup"><span data-stu-id="28f04-169">Specifying multiple \<before> and \<after> blocks</span></span>  
 <span data-ttu-id="28f04-170">Para evitar ambigüedades, puede escribir diagrama en el ejemplo B mediante el uso de **\<before>** varios **\<after>** pares de bloques y.</span><span class="sxs-lookup"><span data-stu-id="28f04-170">To avoid ambiguity, you can write the updategram in Example B by using multiple **\<before>** and **\<after>** block pairs.</span></span> <span data-ttu-id="28f04-171">Especificar **\<before>** pares and **\<after>** es una manera de especificar varias actualizaciones con un mínimo de confusión.</span><span class="sxs-lookup"><span data-stu-id="28f04-171">Specifying **\<before>** and **\<after>** pairs is one way of specifying multiple updates with a minimum of confusion.</span></span> <span data-ttu-id="28f04-172">Además, si cada uno de **\<before>** los **\<after>** bloques y especifica como máximo un elemento, no es necesario usar el `updg:id` atributo.</span><span class="sxs-lookup"><span data-stu-id="28f04-172">Also, if each of the **\<before>** and **\<after>** blocks specify at most one element, you do not have to use the `updg:id` attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28f04-173">Para formar un par, la **\<after>** etiqueta debe seguir inmediatamente a su **\<before>** etiqueta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="28f04-173">To form a pair, the **\<after>** tag must immediately follow its corresponding **\<before>** tag.</span></span>  
  
 <span data-ttu-id="28f04-174">En el siguiente diagrama, el primero **\<before>** y el **\<after>** par actualizan el nombre del turno para el turno de día.</span><span class="sxs-lookup"><span data-stu-id="28f04-174">In the following updategram, the first **\<before>** and **\<after>** pair updates the shift name for the day shift.</span></span> <span data-ttu-id="28f04-175">El segundo par inserta un nuevo registro de turno.</span><span class="sxs-lookup"><span data-stu-id="28f04-175">The second pair inserts a new shift record.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Early Morning" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="28f04-176">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="28f04-176">To test the updategram</span></span>  
  
1.  <span data-ttu-id="28f04-177">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-177">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="28f04-178">Guarde el archivo como UpdateMultipleBeforeAfter.xml.</span><span class="sxs-lookup"><span data-stu-id="28f04-178">Save the file as UpdateMultipleBeforeAfter.xml.</span></span>  
  
2.  <span data-ttu-id="28f04-179">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-179">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="28f04-180">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-180">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-specifying-multiple-sync-blocks"></a><span data-ttu-id="28f04-181">D.</span><span class="sxs-lookup"><span data-stu-id="28f04-181">D.</span></span> <span data-ttu-id="28f04-182">Especificar varios \<sync> bloques</span><span class="sxs-lookup"><span data-stu-id="28f04-182">Specifying multiple \<sync> blocks</span></span>  
 <span data-ttu-id="28f04-183">Puede especificar varios **\<sync>** bloques en un diagrama.</span><span class="sxs-lookup"><span data-stu-id="28f04-183">You can specify multiple **\<sync>** blocks in an updategram.</span></span> <span data-ttu-id="28f04-184">Cada **\<sync>** bloque que se especifica es una transacción independiente.</span><span class="sxs-lookup"><span data-stu-id="28f04-184">Each **\<sync>** block that is specified is an independent transaction.</span></span>  
  
 <span data-ttu-id="28f04-185">En el siguiente diagrama, el primer **\<sync>** bloque actualiza un registro en la tabla sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="28f04-185">In the following updategram, the first **\<sync>** block updates a record in the Sales.Customer table.</span></span> <span data-ttu-id="28f04-186">Para que resulte más sencillo, el diagrama de actualización especifica solamente los valores de columna necesarios; el valor de identidad (CustomerID) y el valor que se está actualizando (SalesPersonID).</span><span class="sxs-lookup"><span data-stu-id="28f04-186">For the sake of simplicity, the updategram specifies only the required column values; the identity value (CustomerID) and the value being updated (SalesPersonID).</span></span>  
  
 <span data-ttu-id="28f04-187">El segundo **\<sync>** bloque agrega dos registros a la tabla sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="28f04-187">The second **\<sync>** block adds two records to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="28f04-188">En esta tabla, SalesOrderID es una columna de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="28f04-188">For this table, SalesOrderID is an IDENTITY-type column.</span></span> <span data-ttu-id="28f04-189">Por lo tanto, diagrama no especifica el valor de SalesOrderID en cada uno de los \<Sales.SalesOrderHeader> elementos.</span><span class="sxs-lookup"><span data-stu-id="28f04-189">Therefore, the updategram does not specify the value of SalesOrderID in each of the \<Sales.SalesOrderHeader> elements.</span></span>  
  
 <span data-ttu-id="28f04-190">Especificar varios **\<sync>** bloques es útil porque si el segundo **\<sync>** bloque (una transacción) no agrega registros a la tabla sales. SalesOrderHeader, el primer **\<sync>** bloque todavía puede actualizar el registro del cliente en la tabla sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="28f04-190">Specifying multiple **\<sync>** blocks is useful because if the second **\<sync>** block (a transaction) fails to add records to Sales.SalesOrderHeader table, the first **\<sync>** block can still update the customer record in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
      <Sales.Customer CustomerID="1" SalesPersonID="280" />  
    </updg:before>  
    <updg:after>  
      <Sales.Customer CustomerID="1" SalesPersonID="283" />  
    </updg:after>  
  </updg:sync>  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
   <Sales.SalesOrderHeader   
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="01010101-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-08 00:00:00.000" />  
   <Sales.SalesOrderHeader  
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="1000.0000"  
             TaxAmt="0.0000"  
             Freight="0.0000"  
             rowguid="10101010-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-09 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="28f04-191">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="28f04-191">To test the updategram</span></span>  
  
1.  <span data-ttu-id="28f04-192">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-192">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="28f04-193">Guarde el archivo como UpdateMultipleSyncs.xml.</span><span class="sxs-lookup"><span data-stu-id="28f04-193">Save the file as UpdateMultipleSyncs.xml.</span></span>  
  
2.  <span data-ttu-id="28f04-194">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-194">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="28f04-195">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-195">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-a-mapping-schema"></a><span data-ttu-id="28f04-196">E.</span><span class="sxs-lookup"><span data-stu-id="28f04-196">E.</span></span> <span data-ttu-id="28f04-197">Usar un esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="28f04-197">Using a mapping schema</span></span>  
 <span data-ttu-id="28f04-198">En este ejemplo, el diagrama de actualización especifica un esquema de asignación utilizando el atributo `mapping-schema`.</span><span class="sxs-lookup"><span data-stu-id="28f04-198">In this example, the updategram specifies a mapping schema by using the `mapping-schema` attribute.</span></span> <span data-ttu-id="28f04-199">(No hay ninguna asignación predeterminada; es decir, el esquema de asignación proporciona la asignación necesaria de elementos y atributos en el diagrama de actualización a las tablas y columnas de base de datos.)</span><span class="sxs-lookup"><span data-stu-id="28f04-199">(There is no default mapping; that is, the mapping schema provides the necessary mapping of elements and attributes in the updategram to the database tables and columns.)</span></span>  
  
 <span data-ttu-id="28f04-200">Los elementos y atributos especificados en el diagrama de actualización hacen referencia a los elementos y atributos del esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="28f04-200">The elements and attributes specified in the updategram refer to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="28f04-201">El siguiente esquema de asignación XSD tiene los **\<Customer>** **\<Order>** elementos, y **\<OD>** que se asignan a las tablas sales. Customer, sales. SalesOrderHeader y sales. SalesOrderDetail de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f04-201">The following XSD mapping schema has **\<Customer>**, **\<Order>**, and **\<OD>** elements that map to the Sales.Customer, Sales.SalesOrderHeader, and Sales.SalesOrderDetail tables in the database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustomerOrder"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustomerOrder" >  
           <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OD"   
                             sql:relation="Sales.SalesOrderDetail"  
                             sql:relationship="OrderOD" >  
                 <xsd:complexType>  
                  <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                  <xsd:attribute name="ProductID" type="xsd:integer" />  
                  <xsd:attribute name="UnitPrice" type="xsd:decimal" />  
                  <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  <xsd:attribute name="UnitPriceDiscount" type="xsd:decimal" />   
                 </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
           </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="28f04-202">Este esquema de asignación (UpdategramMappingSchema.xml) se especifica en el siguiente diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-202">This mapping schema (UpdategramMappingSchema.xml) is specified in the following updategram.</span></span> <span data-ttu-id="28f04-203">El diagrama de actualización agrega un elemento de detalle de pedido en la tabla Sales.SalesOrderDetail para un pedido concreto.</span><span class="sxs-lookup"><span data-stu-id="28f04-203">The updategram adds an order detail item in the Sales.SalesOrderDetail table for a specific order.</span></span> <span data-ttu-id="28f04-204">Diagrama incluye elementos anidados: un **\<OD>** elemento anidado dentro de un **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="28f04-204">The updategram includes nested elements: an **\<OD>** element nested inside an **\<Order>** element.</span></span> <span data-ttu-id="28f04-205">La relación de clave principal/clave externa entre estos dos elementos se especifica en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="28f04-205">The primary key/foreign key relationship between these two elements is specified in the mapping schema.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="UpdategramMappingSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43659" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43659" >  
          <OD ProductID="776" UnitPrice="2329.0000"  
              OrderQty="2" UnitPriceDiscount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="28f04-206">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="28f04-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="28f04-207">Copie el esquema de asignación anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-207">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="28f04-208">Guarde el archivo como UpdategramMappingSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="28f04-208">Save the file as UpdategramMappingSchema.xml.</span></span>  
  
2.  <span data-ttu-id="28f04-209">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-209">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="28f04-210">Guarde el archivo como UpdateWithMappingSchema.xml en la misma carpeta que se utilizó para guardar el esquema de asignación (UpdategramMappingSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="28f04-210">Save the file as UpdateWithMappingSchema.xml in the same folder as was used to save the mapping schema (UpdategramMappingSchema.xml).</span></span>  
  
3.  <span data-ttu-id="28f04-211">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-211">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="28f04-212">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-212">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="28f04-213">Para obtener más ejemplos de diagramas que usan esquemas de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-213">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="f-using-a-mapping-schema-with-idrefs-attributes"></a><span data-ttu-id="28f04-214">F.</span><span class="sxs-lookup"><span data-stu-id="28f04-214">F.</span></span> <span data-ttu-id="28f04-215">Usar un esquema de asignación con atributos IDREFS</span><span class="sxs-lookup"><span data-stu-id="28f04-215">Using a mapping schema with IDREFS attributes</span></span>  
 <span data-ttu-id="28f04-216">En este ejemplo se muestra cómo los diagramas de actualización utilizan los atributos IDREFS en el esquema de asignación para actualizar registros en varias tablas.</span><span class="sxs-lookup"><span data-stu-id="28f04-216">This example illustrates how updategrams use the IDREFS attributes in the mapping schema to update records in multiple tables.</span></span> <span data-ttu-id="28f04-217">En este ejemplo, suponga que la base de datos está compuesta de las tablas siguientes:</span><span class="sxs-lookup"><span data-stu-id="28f04-217">For this example, assume that the database consists of the following tables:</span></span>  
  
-   <span data-ttu-id="28f04-218">Student(StudentID, LastName)</span><span class="sxs-lookup"><span data-stu-id="28f04-218">Student(StudentID, LastName)</span></span>  
  
-   <span data-ttu-id="28f04-219">Course(CourseID, CourseName)</span><span class="sxs-lookup"><span data-stu-id="28f04-219">Course(CourseID, CourseName)</span></span>  
  
-   <span data-ttu-id="28f04-220">Enrollment(StudentID, CourseID)</span><span class="sxs-lookup"><span data-stu-id="28f04-220">Enrollment(StudentID, CourseID)</span></span>  
  
 <span data-ttu-id="28f04-221">Dado que un alumno se puede inscribir en muchos cursos y un curso puede tener muchos alumnos, hace falta una tercera tabla, la tabla Enrollment, que represente esta relación M:N.</span><span class="sxs-lookup"><span data-stu-id="28f04-221">Because a student can enroll in many courses and a course can have many students, the third table, the Enrollment table, is required to represent this M:N relationship.</span></span>  
  
 <span data-ttu-id="28f04-222">El siguiente esquema de asignación XSD proporciona una vista XML de las tablas mediante los **\<Student>** **\<Course>** elementos, y **\<Enrollment>** .</span><span class="sxs-lookup"><span data-stu-id="28f04-222">The following XSD mapping schema provides an XML view of the tables by using the **\<Student>**, **\<Course>**, and **\<Enrollment>** elements.</span></span> <span data-ttu-id="28f04-223">Los atributos **IDREFS** en el esquema de asignación especifican la relación entre estos elementos.</span><span class="sxs-lookup"><span data-stu-id="28f04-223">The **IDREFS** attributes in the mapping schema specify the relationship between these elements.</span></span> <span data-ttu-id="28f04-224">El atributo **StudentIDList** del **\<Course>** elemento es un atributo de tipo **IDREFS** que hace referencia a la columna StudentID de la tabla de inscripción.</span><span class="sxs-lookup"><span data-stu-id="28f04-224">The **StudentIDList** attribute on the **\<Course>** element is an **IDREFS** type attribute that refers to the StudentID column in the Enrollment table.</span></span> <span data-ttu-id="28f04-225">Del mismo modo **, el atributo** inscrito en el **\<Student>** elemento es un atributo de tipo **IDREFS** que hace referencia a la columna CourseID de la tabla de inscripción.</span><span class="sxs-lookup"><span data-stu-id="28f04-225">Likewise, the **EnrolledIn** attribute on the **\<Student>** element is an **IDREFS** type attribute that refers to the CourseID column in the Enrollment table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="StudentEnrollment"  
          parent="Student"  
          parent-key="StudentID"  
          child="Enrollment"  
          child-key="StudentID" />  
  
    <sql:relationship name="CourseEnrollment"  
          parent="Course"  
          parent-key="CourseID"  
          child="Enrollment"  
          child-key="CourseID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Course" sql:relation="Course"   
                             sql:key-fields="CourseID" >  
    <xsd:complexType>  
    <xsd:attribute name="CourseID"  type="xsd:string" />   
    <xsd:attribute name="CourseName"   type="xsd:string" />   
    <xsd:attribute name="StudentIDList" sql:relation="Enrollment"  
                 sql:field="StudentID"  
                 sql:relationship="CourseEnrollment"   
                                     type="xsd:IDREFS" />  
  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name="Student" sql:relation="Student" >  
    <xsd:complexType>  
    <xsd:attribute name="StudentID"  type="xsd:string" />   
    <xsd:attribute name="LastName"   type="xsd:string" />   
    <xsd:attribute name="EnrolledIn" sql:relation="Enrollment"  
                 sql:field="CourseID"  
                 sql:relationship="StudentEnrollment"   
                                     type="xsd:IDREFS" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="28f04-226">Cada vez que especifique este esquema en un diagrama de actualización e inserte un registro en la tabla Course, el diagrama de actualización insertará un nuevo registro de curso en la tabla Course.</span><span class="sxs-lookup"><span data-stu-id="28f04-226">Whenever you specify this schema in an updategram and insert a record in the Course table, the updategram inserts a new course record in the Course table.</span></span> <span data-ttu-id="28f04-227">Si especifica uno o más identificadores de alumnos nuevos para el atributo StudentIDList, el diagrama de actualización también insertará un registro en la tabla Enrollment para cada nuevo alumno.</span><span class="sxs-lookup"><span data-stu-id="28f04-227">If you specify one or more new student IDs for the StudentIDList attribute, the updategram also inserts a record in the Enrollment table for the each new student.</span></span> <span data-ttu-id="28f04-228">El diagrama de actualización asegura que no se agregan registros duplicados a la tabla Enrollment.</span><span class="sxs-lookup"><span data-stu-id="28f04-228">The updategram ensures that no duplicates are added to the Enrollment table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="28f04-229">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="28f04-229">To test the updategram</span></span>  
  
1.  <span data-ttu-id="28f04-230">Cree estas tablas en la base de datos especificada en la raíz virtual:</span><span class="sxs-lookup"><span data-stu-id="28f04-230">Create these tables in the database that is specified in the virtual root:</span></span>  
  
    ```  
    CREATE TABLE Student(StudentID varchar(10) primary key,   
                         LastName varchar(25))  
    CREATE TABLE Course(CourseID varchar(10) primary key,   
                        CourseName varchar(25))  
    CREATE TABLE Enrollment(StudentID varchar(10)   
                                      references Student(StudentID),  
                           CourseID varchar(10)   
                                      references Course(CourseID))  
    ```  
  
2.  <span data-ttu-id="28f04-231">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="28f04-231">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Student VALUES ('S1','Davoli')  
    INSERT INTO Student VALUES ('S2','Fuller')  
  
    INSERT INTO Course VALUES  ('CS101', 'C Programming')  
    INSERT INTO Course VALUES  ('CS102', 'Understanding XML')  
  
    INSERT INTO Enrollment VALUES ('S1', 'CS101')  
    INSERT INTO Enrollment VALUES ('S1', 'CS102')  
    ```  
  
3.  <span data-ttu-id="28f04-232">Copie el esquema de asignación anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28f04-232">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="28f04-233">Guarde el archivo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="28f04-233">Save the file as SampleSchema.xml.</span></span>  
  
4.  <span data-ttu-id="28f04-234">Guarde el diagrama de actualización (SampleUpdategram) en la misma carpeta utilizada para guardar el esquema de asignación en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="28f04-234">Save the updategram (SampleUpdategram) in the same folder used to save the mapping schema in the previous step.</span></span> <span data-ttu-id="28f04-235">(Este diagrama de actualización quita un alumno con StudentID = "1" del curso CS102.)</span><span class="sxs-lookup"><span data-stu-id="28f04-235">(This updategram drops a student with StudentID="1" from the CS102 course.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="28f04-236">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="28f04-236">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="28f04-237">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-237">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
6.  <span data-ttu-id="28f04-238">Guarde y ejecute el siguiente diagrama de actualización tal y como se describe en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="28f04-238">Save and execute the following updategram as described in the previous steps.</span></span> <span data-ttu-id="28f04-239">El diagrama de actualización vuelve a incluir al alumno con StudentID = "1" en el curso CS102 agregando un registro en la tabla Enrollment.</span><span class="sxs-lookup"><span data-stu-id="28f04-239">The updategram adds the student with StudentID="1" back into the CS102 course by adding a record in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
7.  <span data-ttu-id="28f04-240">Guarde y ejecute este siguiente diagrama como se describe en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="28f04-240">Save and execute this next updategram as described in the previous steps.</span></span> <span data-ttu-id="28f04-241">Este diagrama de actualización inserta tres nuevos alumnos y los inscribe en el curso CS101.</span><span class="sxs-lookup"><span data-stu-id="28f04-241">This updategram inserts three new students and enrolls them in the CS101 course.</span></span> <span data-ttu-id="28f04-242">De nuevo, la relación IDREFS inserta registros en la tabla Enrollment.</span><span class="sxs-lookup"><span data-stu-id="28f04-242">Again, the IDREFS relationship inserts records in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
           <Course updg:id="y" CourseID="CS101"   
                               CourseName="C Programming" />  
        </updg:before>  
        <updg:after >  
           <Student updg:id="x1" StudentID="S3" LastName="Leverling" />  
           <Student updg:id="x2" StudentID="S4" LastName="Pecock" />  
           <Student updg:id="x3" StudentID="S5" LastName="Buchanan" />  
           <Course updg:id="y" CourseID="CS101"  
                               CourseName="C Programming"  
                               StudentIDList="S3 S4 S5" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
 <span data-ttu-id="28f04-243">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="28f04-243">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ElementType name="Enrollment" sql:relation="Enrollment" sql:key-fields="StudentID CourseID">  
    <AttributeType name="StudentID" dt:type="id" />  
    <AttributeType name="CourseID" dt:type="id" />  
  
    <attribute type="StudentID" />  
    <attribute type="CourseID" />  
  </ElementType>  
  <ElementType name="Course" sql:relation="Course" sql:key-fields="CourseID">  
    <AttributeType name="CourseID" dt:type="id" />  
    <AttributeType name="CourseName" />  
  
    <attribute type="CourseID" />  
    <attribute type="CourseName" />  
  
    <AttributeType name="StudentIDList" dt:type="idrefs" />  
    <attribute type="StudentIDList" sql:relation="Enrollment" sql:field="StudentID" >  
        <sql:relationship  
                key-relation="Course"  
                key="CourseID"  
                foreign-relation="Enrollment"  
                foreign-key="CourseID" />  
    </attribute>  
  
  </ElementType>  
  <ElementType name="Student" sql:relation="Student">  
    <AttributeType name="StudentID" dt:type="id" />  
     <AttributeType name="LastName" />  
  
    <attribute type="StudentID" />  
    <attribute type="LastName" />  
  
    <AttributeType name="EnrolledIn" dt:type="idrefs" />  
    <attribute type="EnrolledIn" sql:relation="Enrollment" sql:field="CourseID" >  
        <sql:relationship  
                key-relation="Student"  
                key="StudentID"  
                foreign-relation="Enrollment"  
                foreign-key="StudentID" />  
    </attribute>  
  
    <element type="Enrollment" sql:relation="Enrollment" >  
        <sql:relationship key-relation="Student"  
                          key="StudentID"  
                          foreign-relation="Enrollment"  
                          foreign-key="StudentID" />  
    </element>  
  </ElementType>  
  
</Schema>  
```  
  
 <span data-ttu-id="28f04-244">Para obtener más ejemplos de diagramas que usan esquemas de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="28f04-244">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f04-245">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28f04-245">See Also</span></span>  
 [<span data-ttu-id="28f04-246">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="28f04-246">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
