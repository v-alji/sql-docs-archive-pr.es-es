---
title: Insertar datos mediante diagramas XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- xsi:nil attribute
- unique values
- <after> block
- id attribute
- data insertions [SQLXML]
- nil attribute
- <before> block
- updg:guid attribute
- multiple record insertions
- returnid attribute
- updategrams [SQLXML], inserting data
- updg:at-identity attribute
- invalid characters [SQLXML]
- updg:returnid attribute
- updg:id attribute
- namespaces [SQLXML], updategrams
- IDENTITY-type column
- guid attribute
- record insertion [SQLXML]
- null values [SQLXML]
- at-identity attribute
- xml data type [SQL Server], SQLXML
ms.assetid: 4dc48762-bc12-43fb-b356-ea1b9c1e287e
author: rothja
ms.author: jroth
ms.openlocfilehash: a80f2cb157e59f30ebcbff5c14abba1003de9e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746182"
---
# <a name="inserting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="4ebd6-102">Insertar datos con diagramas de actualización XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4ebd6-102">Inserting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="4ebd6-103">Un diagrama indica una operación de inserción cuando una instancia de registro aparece en el **\<after>** bloque, pero no en el **\<before>** bloque correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-103">An updategram indicates an insert operation when a record instance appears in the **\<after>** block but not in the corresponding **\<before>** block.</span></span> <span data-ttu-id="4ebd6-104">En este caso, diagrama inserta el registro del **\<after>** bloque en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-104">In this case, the updategram inserts the record in the **\<after>** block into the database.</span></span>  
  
 <span data-ttu-id="4ebd6-105">Éste es el formato del diagrama de actualización para una operación de inserción:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-105">This is the updategram format for an insert operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   [<updg:before>  
   </updg:before>]  
    <updg:after [updg:returnid="x y ...] >  
       <ElementName [updg:id="value"]   
                   [updg:at-identity="x"]   
                   [updg:guid="y"]  
                   attribute="value"   
                   attribute="value"  
                   ...  
       />  
      [<ElementName .../>... ]  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
## <a name="before-block"></a><span data-ttu-id="4ebd6-106">\<before>Sin</span><span class="sxs-lookup"><span data-stu-id="4ebd6-106">\<before> Block</span></span>  
 <span data-ttu-id="4ebd6-107">El **\<before>** bloque se puede omitir para una operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-107">The **\<before>** block can be omitted for an insert operation.</span></span> <span data-ttu-id="4ebd6-108">Si `mapping-schema` no se especifica el atributo opcional, el **\<ElementName>** especificado en diagrama se asigna a una tabla de base de datos y los elementos secundarios o atributos se asignan a las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-108">If the optional `mapping-schema` attribute is not specified, the **\<ElementName>** that is specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
## <a name="after-block"></a><span data-ttu-id="4ebd6-109">\<after>Sin</span><span class="sxs-lookup"><span data-stu-id="4ebd6-109">\<after> Block</span></span>  
 <span data-ttu-id="4ebd6-110">Puede especificar uno o varios registros en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-110">You can specify one or more records in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="4ebd6-111">Si el **\<after>** bloque no proporciona un valor para una columna determinada, diagrama usa el valor predeterminado que se especifica en el esquema anotado (si se ha especificado un esquema).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-111">If the **\<after>** block does not supply a value for a particular column, the updategram uses the default value that is specified in the annotated schema (if a schema has been specified).</span></span> <span data-ttu-id="4ebd6-112">Si el esquema no especifica un valor predeterminado para la columna, diagrama no especifica ningún valor explícito para esta columna y, en su lugar, asigna el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] valor predeterminado (si se especifica) a esta columna.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-112">If the schema does not specify a default value for the column, the updategram does not specify any explicit value to this column and, instead, assigns the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value (if specified) to this column.</span></span> <span data-ttu-id="4ebd6-113">Si no hay ningún valor predeterminado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y la columna acepta un valor NULL, el diagrama de actualización establece el valor de columna en NULL.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-113">If there is no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value and the column accepts a NULL value, the updategram sets the column value to NULL.</span></span> <span data-ttu-id="4ebd6-114">Si la columna no tiene un valor predeterminado ni acepta un valor NULL, se produce un error en el comando y el diagrama de actualización devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-114">If the column neither has a default value nor accepts a NULL value, the command fails and the updategram returns an error.</span></span> <span data-ttu-id="4ebd6-115">El atributo `updg:returnid` opcional se utiliza para devolver el valor de identidad que genera el sistema cuando se agrega un registro a una tabla con una columna de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-115">The optional `updg:returnid` attribute is used to return the identity value that is generated by the system when a record is added in a table with an IDENTITY-type column.</span></span>  
  
## <a name="updgid-attribute"></a><span data-ttu-id="4ebd6-116">Atributo updg:id</span><span class="sxs-lookup"><span data-stu-id="4ebd6-116">updg:id Attribute</span></span>  
 <span data-ttu-id="4ebd6-117">Si el diagrama de actualización inserta solamente registros, no requiere el atributo `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-117">If the updategram is inserting only records, the updategram does not require the `updg:id` attribute.</span></span> <span data-ttu-id="4ebd6-118">Para obtener más información acerca de `updg:id` , vea [actualizar datos mediante XML diagramas &#40;SQLXML 4,0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-118">For more information about `updg:id`, see [Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="updgat-identity-attribute"></a><span data-ttu-id="4ebd6-119">Atributo updg:at-identity</span><span class="sxs-lookup"><span data-stu-id="4ebd6-119">updg:at-identity Attribute</span></span>  
 <span data-ttu-id="4ebd6-120">Cuando un diagrama de actualización inserta un registro en una tabla que tiene una columna de tipo IDENTITY, el diagrama de actualización puede capturar el valor asignado por el sistema mediante el atributo `updg:at-identity` opcional.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-120">When an updategram inserts a record in a table that has an IDENTITY-type column, the updategram can capture the system assigned value by using the optional `updg:at-identity` attribute.</span></span> <span data-ttu-id="4ebd6-121">El diagrama de actualización puede utilizar este valor en operaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-121">The updategram can then use this value in subsequent operations.</span></span> <span data-ttu-id="4ebd6-122">Al ejecutar el diagrama de actualización, puede devolver el valor de identidad que se genera especificando el atributo `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-122">Upon execution of the updategram, you can return the identity value that is generated by specifying the `updg:returnid` attribute.</span></span>  
  
## <a name="updgguid-attribute"></a><span data-ttu-id="4ebd6-123">Atributo updg:guid</span><span class="sxs-lookup"><span data-stu-id="4ebd6-123">updg:guid Attribute</span></span>  
 <span data-ttu-id="4ebd6-124">El atributo `updg:guid` es un atributo opcional que genera un identificador único global.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-124">The `updg:guid` attribute is an optional attribute that generates a globally unique identifier.</span></span> <span data-ttu-id="4ebd6-125">Este valor permanece en el ámbito de todo el **\<sync>** bloque en el que se especifica.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-125">This value remains in scope for the entire **\<sync>** block in which it is specified.</span></span> <span data-ttu-id="4ebd6-126">Puede usar este valor en cualquier parte del **\<sync>** bloque.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-126">You can use this value anywhere in the **\<sync>** block.</span></span> <span data-ttu-id="4ebd6-127">El atributo llama `NEWGUID()` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a la función para generar el identificador único.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-127">The attribute calls the `NEWGUID()`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] function to generate the unique identifier.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4ebd6-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4ebd6-128">Examples</span></span>  
 <span data-ttu-id="4ebd6-129">Para crear ejemplos funcionales mediante los ejemplos siguientes, debe cumplir los requisitos especificados en [requisitos para ejecutar ejemplos de SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-129">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="4ebd6-130">Antes de usar los ejemplos del diagrama de actualización, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-130">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="4ebd6-131">En la mayoría de los ejemplos se usa una asignación predeterminada (es decir, no se especifica ningún esquema de asignación en el diagrama de actualización).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-131">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="4ebd6-132">Para obtener más ejemplos de diagramas que usan esquemas de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-132">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="4ebd6-133">La mayoría de los ejemplos usan la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ebd6-133">Most of the examples use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="4ebd6-134">Todas las actualizaciones se aplican a las tablas de esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-134">All the updates are applied to the tables in this database.</span></span>  
  
### <a name="a-inserting-a-record-by-using-an-updategram"></a><span data-ttu-id="4ebd6-135">A.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-135">A.</span></span> <span data-ttu-id="4ebd6-136">Insertar un registro usando un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-136">Inserting a record by using an updategram</span></span>  
 <span data-ttu-id="4ebd6-137">Este diagrama de actualización centrado en atributos inserta un registro en la tabla HumanResources.Employee de la base de datos [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ebd6-137">This attribute-centric updategram inserts a record in the HumanResources.Employee table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="4ebd6-138">En este ejemplo, el diagrama de actualización no especifica ningún esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-138">In this example, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="4ebd6-139">Por lo tanto, el diagrama de actualización usa la asignación predeterminada, en la que el nombre de elemento se asigna a un nombre de tabla y los atributos o elementos secundarios se asignan a columnas de dicha tabla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-139">Therefore, the updategram uses default mapping, in which the element name maps to a table name and the attributes or child elements map to columns in that table.</span></span>  
  
 <span data-ttu-id="4ebd6-140">El esquema [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] para la tabla HumanResources.Department impone una restricción 'not null' en todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-140">The [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] schema for the HumanResources.Department table imposes a 'not null' restriction on all columns.</span></span> <span data-ttu-id="4ebd6-141">Por lo tanto, el diagrama de actualización debe tener valores especificados para todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-141">Therefore, the updategram must include values specified for all columns.</span></span> <span data-ttu-id="4ebd6-142">DepartmentID es una columna de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-142">The DepartmentID is an IDENTITY-type column.</span></span> <span data-ttu-id="4ebd6-143">Por ello, no se especifica ningún valor para ella.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-143">Therefore, no values are specified for it.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name="New Product Research"   
            GroupName="Research and Development"   
            ModifiedDate="2010-08-31"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4ebd6-144">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="4ebd6-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4ebd6-145">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-145">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-146">Guarde el archivo como MyUpdategram.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-146">Save the file as MyUpdategram.xml.</span></span>  
  
2.  <span data-ttu-id="4ebd6-147">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-147">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4ebd6-148">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-148">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4ebd6-149">En una asignación centrada en elementos, el diagrama de actualización presenta un aspecto como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-149">In an element-centric mapping, the updategram looks like this:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department>  
            <Name> New Product Research </Name>  
            <GroupName> Research and Development </GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-150">En un diagrama de actualización de modo mixto (centrado en elementos y en atributos), un elemento puede incluir atributos y subelementos, tal y como se muestra en este diagrama de actualización:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-150">In a mixed-mode (element-centric and attribute-centric) updategram, an element can have both attributes and subelements, as shown in this updategram:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name=" New Product Research "   
            <GroupName>Research and Development</GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="b-inserting-multiple-records-by-using-an-updategram"></a><span data-ttu-id="4ebd6-151">B.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-151">B.</span></span> <span data-ttu-id="4ebd6-152">Insertar varios registros utilizando un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-152">Inserting multiple records by using an updategram</span></span>  
 <span data-ttu-id="4ebd6-153">Este diagrama de actualización agrega dos nuevos registros de turno a la tabla HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-153">This updategram adds two new shift records to the HumanResources.Shift table.</span></span> <span data-ttu-id="4ebd6-154">Diagrama no especifica el **\<before>** bloque opcional.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-154">The updategram does not specify the optional **\<before>** block.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4ebd6-155">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="4ebd6-155">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4ebd6-156">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-156">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-157">Guarde el archivo como Updategram-AddShifts.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-157">Save the file as Updategram-AddShifts.xml.</span></span>  
  
2.  <span data-ttu-id="4ebd6-158">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4ebd6-159">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4ebd6-160">Otra versión de este ejemplo es una diagrama que usa dos bloques independientes en **\<after>** lugar de un bloque para insertar los dos empleados.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-160">Another version of this example is an updategram that uses two separate **\<after>** blocks instead of one block to insert the two employees.</span></span> <span data-ttu-id="4ebd6-161">Esta versión es válida y puede codificarse del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-161">This is valid and can be encoded as follows:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after >  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="c-working-with-valid-sql-server-characters-that-are-not-valid-in-xml"></a><span data-ttu-id="4ebd6-162">C.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-162">C.</span></span> <span data-ttu-id="4ebd6-163">Trabajar con caracteres de SQL Server válidos que no son válidos en XML</span><span class="sxs-lookup"><span data-stu-id="4ebd6-163">Working with valid SQL Server characters that are not valid in XML</span></span>  
 <span data-ttu-id="4ebd6-164">En [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], los nombres de tabla pueden incluir un espacio, como la tabla Order Details de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space, such as the Order Details table in the Northwind database.</span></span> <span data-ttu-id="4ebd6-165">Sin embargo, esto no es válido en caracteres XML que son [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificadores válidos, pero los identificadores XML no válidos se pueden codificar mediante ' __xHHHH \_ \_ ' como valor de codificación, donde HHHH representa el código UCS-2 hexadecimal de cuatro dígitos para el carácter en el orden más significativo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-165">However, this is not valid in XML characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but not valid XML identifiers can be encoded using '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ebd6-166">Este ejemplo usa la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-166">This example uses the Northwind database.</span></span> <span data-ttu-id="4ebd6-167">Puede instalar la base de datos Northwind mediante un script SQL disponible para su descarga desde este [sitio web de Microsoft](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-167">You can install the Northwind database by using an SQL script available for download from this [Microsoft Web site](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>  
  
 <span data-ttu-id="4ebd6-168">Además, el nombre del elemento debe incluirse entre corchetes ([ ]).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-168">Also, the element name must be enclosed within brackets ([ ]).</span></span> <span data-ttu-id="4ebd6-169">Dado que los caracteres [y] no son válidos en XML, debe codificarlos como _x005B \_ y _x005D \_ , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-169">Because the characters [and] are not valid in XML, you must encode them as _x005B\_ and _x005D\_, respectively.</span></span> <span data-ttu-id="4ebd6-170">(Si utiliza un esquema de asignación, puede especificar nombres de elemento que no contengan caracteres no válidos, como espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-170">(If you use a mapping schema, you can provide element names that do not contain characters that are not valid, such as white spaces.</span></span> <span data-ttu-id="4ebd6-171">El esquema de asignación realiza la asignación necesaria; por lo tanto, no necesita codificar estos caracteres.)</span><span class="sxs-lookup"><span data-stu-id="4ebd6-171">The mapping schema does the necessary mapping; therefore, you do not need to encode for these characters).</span></span>  
  
 <span data-ttu-id="4ebd6-172">Este diagrama de actualización agrega un registro a la tabla Order Details de la base de datos Northwind:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-172">This updategram adds a record to the Order Details table in the Northwind database:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <_x005B_Order_x0020_Details_x005D_ OrderID="1"  
            ProductID="11"  
            UnitPrice="$1.0"  
            Quantity="1"  
            Discount="0.0" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-173">La columna UnitPrice de la tabla Order Details es de tipo `money`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-173">The UnitPrice column in the Order Details table is of the `money` type.</span></span> <span data-ttu-id="4ebd6-174">Para aplicar la conversión de tipos adecuada (de un tipo `string` a un tipo `money`), debe agregarse el carácter del signo de dólar ($) como parte del valor.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-174">To apply the appropriate type conversion (from a `string` type to a `money` type), the dollar sign character ($) must be added as part of the value.</span></span> <span data-ttu-id="4ebd6-175">Si el diagrama de actualización no especifica ningún esquema de asignación, se evalúa el primer carácter del valor `string`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-175">If the updategram does not specify a mapping schema, the first character of the `string` value is evaluated.</span></span> <span data-ttu-id="4ebd6-176">Si el primer carácter es un signo de dólar ($), se aplica la conversión adecuada.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-176">If the first character is a dollar sign ($), the appropriate conversion is applied.</span></span>  
  
 <span data-ttu-id="4ebd6-177">Si el diagrama de actualización se especifica en un esquema de asignación donde la columna está correctamente marcada como `dt:type="fixed.14.4"` o `sql:datatype="money"`, no se requiere el signo de dólar ($) y la asignación controla la conversión.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-177">If the updategram is specified against a mapping schema where the column is appropriately marked as either `dt:type="fixed.14.4"` or `sql:datatype="money"`, the dollar sign ($) is not required and the conversion is handled by the mapping.</span></span> <span data-ttu-id="4ebd6-178">Ésta es la forma recomendada de asegurarse de que se realice la conversión de tipos adecuada.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-178">This is the recommended way to ensure that the appropriate type conversion occurs.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4ebd6-179">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="4ebd6-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4ebd6-180">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-180">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-181">Guarde el archivo como UpdategramSpacesInTableName.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-181">Save the file as UpdategramSpacesInTableName.xml.</span></span>  
  
2.  <span data-ttu-id="4ebd6-182">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-182">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4ebd6-183">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-183">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-using-the-at-identity-attribute-to-retrieve-the-value-that-has-been-inserted-in-the-identity-type-column"></a><span data-ttu-id="4ebd6-184">D.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-184">D.</span></span> <span data-ttu-id="4ebd6-185">Utilizar el atributo at-identity para recuperar el valor insertado en la columna de tipo IDENTITY</span><span class="sxs-lookup"><span data-stu-id="4ebd6-185">Using the at-identity attribute to retrieve the value that has been inserted in the IDENTITY-type column</span></span>  
 <span data-ttu-id="4ebd6-186">El siguiente diagrama de actualización inserta dos registros: uno en la tabla Sales.SalesOrderHeader y otra en la tabla Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-186">The following updategram inserts two records: one in the Sales.SalesOrderHeader table and another in the Sales.SalesOrderDetail table.</span></span>  
  
 <span data-ttu-id="4ebd6-187">En primer lugar, el diagrama de actualización agrega un registro a la tabla Sales.SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-187">First, the updategram adds a record to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="4ebd6-188">En esta tabla, la columna SalesOrderID es una columna de tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-188">In this table, the SalesOrderID column is an IDENTITY-type column.</span></span> <span data-ttu-id="4ebd6-189">Por lo tanto, al agregar este registro a la tabla, el diagrama de actualización usa el atributo `at-identity` para capturar el valor de SalesOrderID asignado como "x" (un valor de marcador de posición).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-189">Therefore, when you add this record to the table, the updategram uses the `at-identity` attribute to capture the assigned SalesOrderID value as "x" (a placeholder value).</span></span> <span data-ttu-id="4ebd6-190">A continuación, diagrama especifica esta `at-identity` variable como el valor del atributo SalesOrderID en el \<Sales.SalesOrderDetail> elemento.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-190">The updategam then specifies this `at-identity` variable as the value of SalesOrderID attribute in the \<Sales.SalesOrderDetail> element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
   <Sales.SalesOrderHeader updg:at-identity="x"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00001111-2222-3333-4444-556677889900"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
      <Sales.SalesOrderDetail SalesOrderID="x"  
                LineNumber="1"  
                OrderQty="1"  
                ProductID="776"  
                SpecialOfferID="1"  
                UnitPrice="2429.9928"  
                UnitPriceDiscount="0.00"  
                rowguid="aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"  
                ModifiedDate="2001-07-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-191">Si desea devolver el valor de identidad generado por el atributo `updg:at-identity`, puede usar el atributo `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-191">If you want to return the identity value that is generated by the `updg:at-identity` attribute, you can use the `updg:returnid` attribute.</span></span> <span data-ttu-id="4ebd6-192">A continuación se muestra un diagrama de actualización revisado que devuelve este valor de identidad.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-192">The following is a revised updategram that returns this identity value.</span></span> <span data-ttu-id="4ebd6-193">(Este diagrama de actualización agrega dos registros de pedido y dos registros de detalles del pedido, simplemente para complicar un poco el ejemplo.)</span><span class="sxs-lookup"><span data-stu-id="4ebd6-193">(This updategram adds two order records and two order detail records, just to make the example a little more complex.)</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync>  
  <updg:before>  
  </updg:before>  
  <updg:after updg:returnid="x y" >  
       <HumanResources.Shift updg:at-identity="x" Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift updg:at-identity="y" Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:after>  
 </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-194">Cuando se ejecuta el diagrama de actualización, devuelve resultados similares a los siguientes, que incluyen el valor de identidad generado (el valor generado de la columna ShiftID utilizada para la identidad de la tabla):</span><span class="sxs-lookup"><span data-stu-id="4ebd6-194">When the updategram is executed, it returns results similar to the following, which includes the identity value (the generated value of the ShiftID column used for table identity) that was generated:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">   
  <returnid>   
    <x>4</x>   
    <y>5</y>   
  </returnid>   
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4ebd6-195">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="4ebd6-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4ebd6-196">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-196">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-197">Guarde el archivo como Updategram-returnId.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-197">Save the file as Updategram-returnId.xml.</span></span>  
  
2.  <span data-ttu-id="4ebd6-198">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-198">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4ebd6-199">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-199">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-the-updgguid-attribute-to-generate-a-unique-value"></a><span data-ttu-id="4ebd6-200">E.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-200">E.</span></span> <span data-ttu-id="4ebd6-201">Utilizar el atributo updg:guid para generar un valor único</span><span class="sxs-lookup"><span data-stu-id="4ebd6-201">Using the updg:guid attribute to generate a unique value</span></span>  
 <span data-ttu-id="4ebd6-202">En este ejemplo, el diagrama de actualización inserta un registro en las tablas Cust y CustOrder.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-202">In this example, the updategram inserts a record in the Cust and CustOrder tables.</span></span> <span data-ttu-id="4ebd6-203">Asimismo, genera un valor único para el atributo CustomerID utilizando el atributo `updg:guid`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-203">Also, the updategram generates a unique value for the CustomerID attribute by using the `updg:guid` attribute.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after updg:returnid="x" >  
      <Cust updg:guid="x" >  
         <CustID>x</CustID>  
         <LastName>Fuller</LastName>  
      </Cust>  
      <CustOrder>  
         <CustID>x</CustID>  
         <OrderID>1</OrderID>  
      </CustOrder>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-204">El diagrama de actualización especifica el atributo `returnid`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-204">The updategram specifies the `returnid` attribute.</span></span> <span data-ttu-id="4ebd6-205">Como resultado, se devuelve el GUID generado:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-205">As a result, the GUID that is generated is returned:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <returnid>  
    <x>7111BD1A-7F0B-4CEE-B411-260DADFEFA2A</x>   
  </returnid>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4ebd6-206">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4ebd6-207">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-207">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-208">Guarde el archivo como Updategram-GenerateGuid.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-208">Save the file as Updategram-GenerateGuid.xml.</span></span>  
  
2.  <span data-ttu-id="4ebd6-209">Cree estas tablas:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-209">Create these tables:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust (CustID uniqueidentifier, LastName varchar(20))  
    CREATE TABLE CustOrder (CustID uniqueidentifier, OrderID int)  
    ```  
  
3.  <span data-ttu-id="4ebd6-210">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-210">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4ebd6-211">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-211">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="f-specifying-a-schema-in-an-updategram"></a><span data-ttu-id="4ebd6-212">F.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-212">F.</span></span> <span data-ttu-id="4ebd6-213">Especificar un esquema en un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-213">Specifying a schema in an updategram</span></span>  
 <span data-ttu-id="4ebd6-214">El diagrama de actualización de este ejemplo inserta un registro en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-214">The updategram in this example inserts a record into the following table:</span></span>  
  
```  
CustOrder(OrderID, EmployeeID, OrderType)  
```  
  
 <span data-ttu-id="4ebd6-215">En este diagrama de actualización se especifica un esquema XSD (es decir, no existe ninguna asignación predeterminada de elementos y atributos del diagrama de actualización).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-215">An XSD schema is specified in this updategram (that is, there is no default mapping of updategram elements and attributes).</span></span> <span data-ttu-id="4ebd6-216">El esquema proporciona la asignación necesaria de elementos y atributos a las tablas y columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-216">The schema provides the necessary mapping of the elements and attributes to the database tables and columns.</span></span>  
  
 <span data-ttu-id="4ebd6-217">En el esquema siguiente (CustOrderSchema.xml) se describe un **\<CustOrder>** elemento que consta de los atributos **OrderID** y **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="4ebd6-217">The following schema (CustOrderSchema.xml) describes a **\<CustOrder>** element that consists of the **OrderID** and **EmployeeID** attributes.</span></span> <span data-ttu-id="4ebd6-218">Para que el esquema sea más interesante, se asigna un valor predeterminado al atributo **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="4ebd6-218">To make the schema more interesting, a default value is assigned to the **EmployeeID** attribute.</span></span> <span data-ttu-id="4ebd6-219">Un diagrama de actualización utiliza el valor predeterminado de un atributo solamente para las operaciones de inserción y solamente si el diagrama de actualización no especifica dicho atributo.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-219">An updategram uses an attribute's default value only for insert operations, and then only if the updategram does not specify that attribute.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="CustOrder" >  
   <xsd:complexType>  
        <xsd:attribute name="OrderID"     type="xsd:integer" />   
        <xsd:attribute name="EmployeeID"  type="xsd:integer" />  
        <xsd:attribute name="OrderType  " type="xsd:integer" default="1"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4ebd6-220">Este diagrama de actualización inserta un registro en la tabla CustOrder.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-220">This updategram inserts a record into the CustOrder table.</span></span> <span data-ttu-id="4ebd6-221">El diagrama de actualización solamente especifica los valores de atributo de OrderID y EmployeeID.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-221">The updategram specifies only the OrderID and EmployeeID attribute values.</span></span> <span data-ttu-id="4ebd6-222">No especifica el valor de atributo de OrderType.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-222">It does not specify the OrderType attribute value.</span></span> <span data-ttu-id="4ebd6-223">Por lo tanto, el diagrama de actualización utiliza el valor predeterminado del atributo OrderType especificado en el esquema anterior.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-223">Therefore, the updategram uses the default value of the EmployeeID attribute that is specified in the preceding schema.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
             xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync mapping-schema='CustOrderSchema.xml'>  
<updg:after>  
       <CustOrder OrderID="98000" EmployeeID="1" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-224">Para obtener más ejemplos de diagramas que especifican un esquema de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-224">For more examples of updategrams that specify a mapping schema, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4ebd6-225">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-225">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4ebd6-226">Cree esta tabla en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="4ebd6-226">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE CustOrder(  
                     OrderID int,   
                     EmployeeID int,   
                     OrderType int)  
    ```  
  
2.  <span data-ttu-id="4ebd6-227">Copie el esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-227">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-228">Guarde el archivo como CustOrderSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-228">Save the file as CustOrderSchema.xml.</span></span>  
  
3.  <span data-ttu-id="4ebd6-229">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-229">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-230">Guarde el archivo como CustOrderUpdategram.xml en la misma carpeta utilizada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-230">Save the file as CustOrderUpdategram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="4ebd6-231">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-231">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4ebd6-232">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-232">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4ebd6-233">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-233">This is the equivalent XDR schema:</span></span>  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
 <ElementType name="CustOrder" >  
    <AttributeType name="OrderID" />  
    <AttributeType name="EmployeeID" />  
    <AttributeType name="OrderType" default="1" />  
    <attribute type="OrderID"  />  
    <attribute type="EmployeeID" />  
    <attribute type="OrderType" />  
  </ElementType>  
</Schema>  
```  
  
### <a name="g-using-the-xsinil-attribute-to-insert-null-values-in-a-column"></a><span data-ttu-id="4ebd6-234">G.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-234">G.</span></span> <span data-ttu-id="4ebd6-235">Usar el atributo xsi:nil para insertar valores NULL en una columna</span><span class="sxs-lookup"><span data-stu-id="4ebd6-235">Using the xsi:nil attribute to insert null values in a column</span></span>  
 <span data-ttu-id="4ebd6-236">Si desea insertar un valor NULL en la columna correspondiente de la tabla, puede especificar el atributo `xsi:nil` en un elemento de un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-236">If you want to insert a null value in the corresponding column in the table, you can specify the `xsi:nil` attribute on an element in an updategram.</span></span> <span data-ttu-id="4ebd6-237">En el esquema XSD correspondiente, también debe especificarse el atributo XSD `nillable`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-237">In the corresponding XSD schema, the XSD `nillable` attribute also must be specified.</span></span>  
  
 <span data-ttu-id="4ebd6-238">Por ejemplo, fíjese en este esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-238">For example, consider this XSD schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="Student" sql:relation="Students">  
  <xsd:complexType>  
    <xsd:all>  
      <xsd:element name="fname" sql:field="first_name"   
                                type="xsd:string"   
                                 nillable="true"/>  
    </xsd:all>  
    <xsd:attribute name="SID"   
                        sql:field="StudentID"  
                        type="xsd:ID"/>      
    <xsd:attribute name="lname"       
                        sql:field="last_name"  
                        type="xsd:string"/>  
    <xsd:attribute name="minitial"    
                        sql:field="middle_initial"   
                        type="xsd:string"/>  
    <xsd:attribute name="years"       
                         sql:field="no_of_years"  
                         type="xsd:integer"/>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4ebd6-239">El esquema XSD especifica **nillable = "true"** para el **\<fname>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-239">The XSD schema specifies **nillable="true"** for the **\<fname>** element.</span></span> <span data-ttu-id="4ebd6-240">El siguiente diagrama de actualización usa este esquema:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-240">The following updategram uses this schema:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
      xmlns:updg="urn:schemas-microsoft-com:xml-updategram"  
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  
<updg:sync mapping-schema='StudentSchema.xml'>  
  <updg:before/>  
  <updg:after>  
    <Student SID="S00004" lname="Elmaci" minitial="" years="2">  
      <fname xsi:nil="true">  
    </fname>  
    </Student>  
  </updg:after>  
</updg:sync>  
  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-241">Diagrama especifica `xsi:nil` para el **\<fname>** elemento en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-241">The updategram specifies `xsi:nil` for the **\<fname>** element in the **\<after>** block.</span></span> <span data-ttu-id="4ebd6-242">Por lo tanto, cuando se ejecuta este diagrama de actualización, se inserta un valor NULL en la columna first_name de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-242">Therefore, when this updategram is executed, a value of NULL is inserted for the first_name column in the table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4ebd6-243">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-243">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4ebd6-244">Cree la siguiente tabla en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="4ebd6-244">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Students (  
       StudentID char(6)NOT NULL ,  
       first_name varchar(50),  
       last_name varchar(50),  
       middle_initial char(1),  
       no_of_years int NULL)  
    GO  
    ```  
  
2.  <span data-ttu-id="4ebd6-245">Copie el esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-245">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-246">Guarde el archivo como StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-246">Save the file as StudentSchema.xml.</span></span>  
  
3.  <span data-ttu-id="4ebd6-247">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-247">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-248">Guarde el archivo como StudentUpdategram.xml en la misma carpeta que se utilizó en el paso anterior para guardar StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-248">Save the file as StudentUpdategram.xml in the same folder used in previous step to save StudentSchema.xml.</span></span>  
  
4.  <span data-ttu-id="4ebd6-249">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-249">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4ebd6-250">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-250">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="h-specifying-namespaces-in-an-updategram"></a><span data-ttu-id="4ebd6-251">H.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-251">H.</span></span> <span data-ttu-id="4ebd6-252">Especificar espacios de nombres en un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-252">Specifying namespaces in an updategram</span></span>  
 <span data-ttu-id="4ebd6-253">En un diagrama de actualización puede tener elementos que pertenezcan a un espacio de nombres declarado en el mismo elemento del diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-253">In an updategram you can have elements that belong to a namespace declared in the same element in the updategram.</span></span> <span data-ttu-id="4ebd6-254">En este caso, el esquema correspondiente también debe declarar el mismo espacio de nombres y el elemento debe pertenecer a este espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-254">In this case, the corresponding schema must also declare the same namespace and the element must belong to that target namespace.</span></span>  
  
 <span data-ttu-id="4ebd6-255">Por ejemplo, en el siguiente diagrama (UpdateGram-ElementHavingNamespace.xml), el **\<Order>** elemento pertenece a un espacio de nombres declarado en el elemento.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-255">For example, in the following updategram (UpdateGram-ElementHavingNamespace.xml), the **\<Order>** element belongs to a namespace declared in the element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema='XSD-ElementHavingNameSpace.xml'>  
    <updg:after>  
       <x:Order  xmlns:x="http://server/xyz/schemas/"  
             updg:at-identity="SalesOrderID"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00009999-8888-7777-6666-554433221100"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-256">En este caso, el esquema también debe declarar el espacio de nombres tal y como se muestra en este esquema:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-256">In this case, the schema must also declare the namespace as shown in this schema:</span></span>  
  
 <span data-ttu-id="4ebd6-257">En el esquema siguiente (XSD-ElementHavingNamespace.xml) se indica cómo debe declararse el elemento y los atributos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-257">The following schema (XSD-ElementHavingNamespace.xml) shows how the corresponding element and attributes must be declared.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns:dt="urn:schemas-microsoft-com:datatypes"   
     xmlns:sql="urn:schemas-microsoft-com:mapping-schema"    
     xmlns:x="http://server/xyz/schemas/"   
     targetNamespace="http://server/xyz/schemas/" >  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="x:Order_type"/>  
  <xsd:complexType name="Order_type">  
    <xsd:attribute name="SalesOrderID"  type="xsd:ID"/>  
    <xsd:attribute name="RevisionNumber" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OrderDate" type="xsd:dateTime"/>  
    <xsd:attribute name="DueDate" type="xsd:dateTime"/>  
    <xsd:attribute name="ShipDate" type="xsd:dateTime"/>  
    <xsd:attribute name="Status" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OnlineOrderFlag" type="xsd:boolean"/>  
    <xsd:attribute name="SalesOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="PurchaseOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="AccountNumber" type="xsd:string"/>  
    <xsd:attribute name="CustomerID" type="xsd:int"/>  
    <xsd:attribute name="ContactID" type="xsd:int"/>  
    <xsd:attribute name="SalesPersonID" type="xsd:int"/>  
    <xsd:attribute name="TerritoryID" type="xsd:int"/>  
    <xsd:attribute name="BillToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipMethodID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardApprovalCode" type="xsd:string"/>  
    <xsd:attribute name="CurrencyRateID" type="xsd:int"/>  
    <xsd:attribute name="SubTotal" type="xsd:decimal"/>  
    <xsd:attribute name="TaxAmt" type="xsd:decimal"/>  
    <xsd:attribute name="Freight" type="xsd:decimal"/>  
    <xsd:attribute name="TotalDue" type="xsd:decimal"/>  
    <xsd:attribute name="Comment" type="xsd:string"/>  
    <xsd:attribute name="rowguid" type="xsd:string"/>  
    <xsd:attribute name="ModifiedDate" type="xsd:dateTime"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4ebd6-258">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-258">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4ebd6-259">Copie el esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-259">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-260">Guarde el archivo como XSD-ElementHavingNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-260">Save the file as XSD-ElementHavingNamespace.xml.</span></span>  
  
2.  <span data-ttu-id="4ebd6-261">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-261">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-262">Guarde el archivo como Updategram-ElementHavingNamespace.xml en la misma carpeta donde haya guardado XSD-ElementHavingnamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-262">Save the file as Updategram-ElementHavingNamespace.xml in the same folder used to save XSD-ElementHavingnamespace.xml.</span></span>  
  
3.  <span data-ttu-id="4ebd6-263">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-263">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4ebd6-264">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-264">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="i-inserting-data-into-an-xml-data-type-column"></a><span data-ttu-id="4ebd6-265">I.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-265">I.</span></span> <span data-ttu-id="4ebd6-266">Insertar datos en una columna de tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="4ebd6-266">Inserting data into an XML data type column</span></span>  
 <span data-ttu-id="4ebd6-267">El tipo de datos `xml` se introdujo en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ebd6-267">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="4ebd6-268">Puede usar diagramas de actualización para insertar y actualizar datos almacenados en columnas de tipo de datos `xml` teniendo en cuenta estas indicaciones:</span><span class="sxs-lookup"><span data-stu-id="4ebd6-268">You can use updategrams to insert and update data stored in `xml` data type columns with the following provisions:</span></span>  
  
-   <span data-ttu-id="4ebd6-269">La columna `xml` no puede utilizarse para identificar una fila existente.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-269">The `xml` column cannot be used for identifying an existing row.</span></span> <span data-ttu-id="4ebd6-270">Por lo tanto, no puede incluirse en la sección `updg:before` de un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-270">Therefore, it cannot be included in the `updg:before` section of an updategram.</span></span>  
  
-   <span data-ttu-id="4ebd6-271">Se conservarán los espacios de nombres que se encuentren en el ámbito del fragmento XML insertado en la columna `xml` y sus declaraciones de espacio de nombres se agregarán al elemento superior del fragmento insertado.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-271">Namespaces that are in scope of the XML fragment inserted into the `xml` column will be preserved and their namespace declarations are added to the top element of the inserted fragment.</span></span>  
  
 <span data-ttu-id="4ebd6-272">Por ejemplo, en el siguiente diagrama (SampleUpdateGram.xml), el **\<Desc>** elemento actualiza la columna ProductDescription de la tabla Production>productModel de la [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-272">For example, in the following updategram (SampleUpdateGram.xml), the **\<Desc>** element updates the ProductDescription column in the Production>productModel table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="4ebd6-273">El resultado de este diagrama es que el contenido XML de la columna ProductDescription se actualiza con el contenido XML del **\<Desc>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-273">The result of this updategram is that the XML contents of the ProductDescription column are update with the XML contents of the **\<Desc>** element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
       <updg:before>  
<ProductModel ProductModelID="19">  
   <Name>Mountain-100</Name>  
</ProductModel>  
    </updg:before>  
    <updg:after>  
 <ProductModel>  
    <Name>Mountain-100</Name>  
    <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
        <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
              xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
              xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
              xmlns:html="http://www.w3.org/1999/xhtml"   
              xmlns="">  
  <p1:Summary>  
     <html:p>Insert Example</html:p>  
  </p1:Summary>  
  <p1:Manufacturer>  
    <p1:Name>AdventureWorks</p1:Name>  
    <p1:Copyright>2002</p1:Copyright>  
    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
  </p1:Manufacturer>  
  <p1:Features>These are the product highlights.   
    <wm:Warranty>  
       <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
       <wm:Description>parts and labor</wm:Description>  
    </wm:Warranty>  
    <wm:Maintenance>  
       <wm:NoOfYears>10 years</wm:NoOfYears>  
       <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
    </wm:Maintenance>  
    <wf:wheel>High performance wheels.</wf:wheel>  
    <wf:saddle>  
      <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle>  
    <wf:pedal>  
       <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal>  
    <wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter and wall-thickness required of a premium mountain frame. The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame>  
    <wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset>  
   </p1:Features>  
   <p1:Picture>  
      <p1:Angle>front</p1:Angle>  
      <p1:Size>small</p1:Size>  
      <p1:ProductPhotoID>118</p1:ProductPhotoID>  
   </p1:Picture>  
   <p1:Specifications> These are the product specifications.  
     <Material>Almuminum Alloy</Material>  
     <Color>Available in most colors</Color>  
     <ProductLine>Mountain bike</ProductLine>  
     <Style>Unisex</Style>  
     <RiderExperience>Advanced to Professional riders</RiderExperience>  
   </p1:Specifications>  
  </p1:ProductDescription>  
 </Desc>  
      </ProductModel>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4ebd6-274">El diagrama de actualización hace referencia al siguiente esquema XSD anotado (SampleSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-274">The updategram refers to the following annotated XSD schema (SampleSchema.xml).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
     <xsd:complexType>  
       <xsd:sequence>  
          <xsd:element name="Name" type="xsd:string"></xsd:element>  
          <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
           <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="ProductDescription">  
                 <xsd:complexType>  
                   <xsd:sequence>  
                     <xsd:element name="Summary" type="xsd:anyType">  
                     </xsd:element>  
                   </xsd:sequence>  
                 </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>   
       </xsd:sequence>  
       <xsd:attribute name="ProductModelID" sql:field="ProductModelID"/>  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="4ebd6-275">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="4ebd6-275">To test the updategram</span></span>  
  
1.  <span data-ttu-id="4ebd6-276">Copie el esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-276">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-277">Guarde el archivo como XSD-SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-277">Save the file as XSD-SampleSchema.xml.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ebd6-278">Dado que los diagramas de actualización admiten la asignación predeterminada, no existe ningún modo de identificar el principio y el final del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-278">Because updategrams support default mapping, there is no way to identify the beginning and ending of the `xml` data type.</span></span> <span data-ttu-id="4ebd6-279">Lo que esto significa realmente es que se requiere un esquema de asignación cuando se insertan o actualizan tablas con columnas de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-279">This effectively means that a mapping schema is required when inserting or updating tables with `xml` data type columns.</span></span> <span data-ttu-id="4ebd6-280">Si no se proporciona ningún esquema, SQLXML devuelve un error que indica que falta una de las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-280">When a schema is not provided, SQLXML returns an error indicating that one of the columns is missing from the table.</span></span>  
  
2.  <span data-ttu-id="4ebd6-281">Copie el diagrama de actualización anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-281">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="4ebd6-282">Guarde el archivo como SampleUpdategram.xml en la misma carpeta donde ha guardado SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-282">Save the file as SampleUpdategram.xml in the same folder used to save SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="4ebd6-283">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="4ebd6-283">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="4ebd6-284">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd6-284">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebd6-285">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ebd6-285">See Also</span></span>  
 [<span data-ttu-id="4ebd6-286">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ebd6-286">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
