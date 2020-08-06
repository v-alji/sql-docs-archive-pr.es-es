---
title: Especificar un esquema de asignación anotado en un diagrama (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, updategrams
- data types [SQLXML], mapping schema in updategrams
- updategrams [SQLXML], annotated mapping schemas
- annotated XDR schemas, updategrams
- inverse attribute
- parent-child relationships [SQLXML]
- mapping-schema attribute
- mapping schema [SQLXML], updategrams
- sql:inverse
ms.assetid: 2e266ed9-4cfb-434a-af55-d0839f64bb9a
author: rothja
ms.author: jroth
ms.openlocfilehash: a181b3081b51cca160709703364c248e495e0214
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674733"
---
# <a name="specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-40"></a><span data-ttu-id="86b3f-102">Cómo especificar un esquema de asignación anotado en un diagrama de actualización (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="86b3f-102">Specifying an Annotated Mapping Schema in an Updategram (SQLXML 4.0)</span></span>
  <span data-ttu-id="86b3f-103">En este tema se explica el modo de usar el esquema de asignación (XSD o XDR) especificado en un diagrama de actualización para procesar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="86b3f-103">This topic explains how the mapping schema (XSD or XDR) that is specified in an updategram is used to process the updates.</span></span> <span data-ttu-id="86b3f-104">En una diagrama, puede proporcionar el nombre de un esquema de asignación anotado para usarlo en la asignación de los elementos y atributos de diagrama a tablas y columnas en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86b3f-104">In an updategram, you can provide the name of an annotated mapping schema to use in mapping the elements and attributes in the updategram to tables and columns in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86b3f-105">Al especificar un esquema de asignación en un diagrama de actualización, los nombres de elementos y atributos especificados en el diagrama de actualización deben asignarse a los elementos y atributos del esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="86b3f-105">When a mapping schema is specified in an updategram, the element and attribute names that are specified in the updategram must map to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="86b3f-106">Para especificar un esquema de asignación, se usa el `mapping-schema` atributo del **\<sync>** elemento.</span><span class="sxs-lookup"><span data-stu-id="86b3f-106">To specify a mapping schema, you use the `mapping-schema` attribute of the **\<sync>** element.</span></span> <span data-ttu-id="86b3f-107">En los ejemplos siguientes se muestran dos diagramas de actualización: uno que usa un esquema de asignación simple y otro que usa un esquema más complejo.</span><span class="sxs-lookup"><span data-stu-id="86b3f-107">The following examples show two updategrams: one that uses a simple mapping schema, and one that uses a more complex schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86b3f-108">En esta documentación se asume que está familiarizado con la compatibilidad de las plantillas y el esquema de asignación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86b3f-108">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86b3f-109">Para obtener más información, vea [Introducción a los esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-109">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="86b3f-110">En el caso de las aplicaciones heredadas que usan XDR, consulte [esquemas XDR anotados &#40;en desuso en SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-110">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="dealing-with-data-types"></a><span data-ttu-id="86b3f-111">Trabajar con tipos de datos</span><span class="sxs-lookup"><span data-stu-id="86b3f-111">Dealing with Data Types</span></span>  
 <span data-ttu-id="86b3f-112">Si el esquema especifica el `image` `binary` tipo de datos, o (mediante `varbinary` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `sql:datatype` ) y no especifica un tipo de datos XML, el diagrama supone que el tipo de datos XML es `binary base 64` .</span><span class="sxs-lookup"><span data-stu-id="86b3f-112">If the schema specifies the `image`, `binary`, or `varbinary`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (by using `sql:datatype`) and does not specify an XML data type, the updategram assumes that the XML data type is `binary base 64`.</span></span> <span data-ttu-id="86b3f-113">Si los datos son de tipo `bin.base`, debe especificar de forma explícita el tipo (`dt:type=bin.base` o `type="xsd:hexBinary"`).</span><span class="sxs-lookup"><span data-stu-id="86b3f-113">If your data is `bin.base` type, you must explicitly specify the type (`dt:type=bin.base` or `type="xsd:hexBinary"`).</span></span>  
  
 <span data-ttu-id="86b3f-114">Si el sistema especifica el tipo de datos XSD `dateTime`, `date` o `time`, también debe especificar el tipo de datos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] correspondiente mediante `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="86b3f-114">If the schema specifies the `dateTime`, `date`, or `time` XSD data type, you must also specify the corresponding [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type by using `sql:datatype="dateTime"`.</span></span>  
  
 <span data-ttu-id="86b3f-115">Al controlar los parámetros de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` tipo, debe especificar explícitamente `sql:datatype="money"` en el nodo adecuado en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="86b3f-115">When handling parameters of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, you must explicitly specify `sql:datatype="money"` on the appropriate node in the mapping schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="86b3f-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86b3f-116">Examples</span></span>  
 <span data-ttu-id="86b3f-117">Para crear ejemplos funcionales mediante los ejemplos siguientes, debe cumplir los requisitos especificados en [requisitos para ejecutar ejemplos de SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-117">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-creating-an-updategram-with-a-simple-mapping-schema"></a><span data-ttu-id="86b3f-118">A.</span><span class="sxs-lookup"><span data-stu-id="86b3f-118">A.</span></span> <span data-ttu-id="86b3f-119">Crear un diagrama de actualización con un esquema de asignación simple</span><span class="sxs-lookup"><span data-stu-id="86b3f-119">Creating an updategram with a simple mapping schema</span></span>  
 <span data-ttu-id="86b3f-120">El siguiente esquema XSD (SampleSchema.xml) es un esquema de asignación que asigna el **\<Customer>** elemento a la tabla sales. Customer:</span><span class="sxs-lookup"><span data-stu-id="86b3f-120">The following XSD schema (SampleSchema.xml) is a mapping schema that maps the **\<Customer>** element to the Sales.Customer table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustID"    
                       sql:field="CustomerID"   
                       type="xsd:string" />  
        <xsd:attribute name="RegionID"    
                       sql:field="TerritoryID"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="86b3f-121">El diagrama de actualización siguiente inserta un registro en la tabla Sales.Customer y se basa en el esquema de asignación anterior para asignar correctamente estos datos a la tabla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-121">The following updategram inserts a record into the Sales.Customer table and relies on the previous mapping schema to properly map this data to the table.</span></span> <span data-ttu-id="86b3f-122">Observe que diagrama usa el mismo nombre de elemento, **\<Customer>** , tal y como se define en el esquema.</span><span class="sxs-lookup"><span data-stu-id="86b3f-122">Notice that the updategram uses the same element name, **\<Customer>**, as defined in the schema.</span></span> <span data-ttu-id="86b3f-123">Esto resulta obligatorio porque el diagrama de actualización especifica un esquema determinado.</span><span class="sxs-lookup"><span data-stu-id="86b3f-123">This is mandatory because the updategram specifies a particular schema.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="86b3f-124">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="86b3f-124">To test the updategram</span></span>  
  
1.  <span data-ttu-id="86b3f-125">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86b3f-125">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86b3f-126">Guarde el archivo como SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86b3f-126">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="86b3f-127">Copie la plantilla de diagrama de actualización siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86b3f-127">Copy the updategram template below and paste it into a text file.</span></span> <span data-ttu-id="86b3f-128">Guarde el archivo como SampleUpdategram.xml en el mismo directorio donde guardó SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86b3f-128">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleUpdateSchema.xml">  
        <updg:before>  
          <Customer CustID="1" RegionID="1"  />  
        </updg:before>  
        <updg:after>  
          <Customer CustID="1" RegionID="2" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="86b3f-129">La ruta de acceso al directorio especificada para el esquema de asignación (SampleUpdateSchema.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-129">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86b3f-130">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86b3f-130">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="86b3f-131">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-131">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86b3f-132">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-132">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="86b3f-133">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="86b3f-133">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Customer" sql:relation="Sales.Customer" >  
       <AttributeType name="CustID" />  
       <AttributeType name="RegionID" />  
  
       <attribute type="CustID" sql:field="CustomerID" />  
       <attribute type="RegionID" sql:field="TerritoryID" />  
     </ElementType>  
   </Schema>   
```  
  
### <a name="b-inserting-a-record-by-using-the-parent-child-relationship-specified-in-the-mapping-schema"></a><span data-ttu-id="86b3f-134">B.</span><span class="sxs-lookup"><span data-stu-id="86b3f-134">B.</span></span> <span data-ttu-id="86b3f-135">Insertar un registro mediante la relación de elementos primarios y secundarios especificada en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="86b3f-135">Inserting a record by using the parent-child relationship specified in the mapping schema</span></span>  
 <span data-ttu-id="86b3f-136">Los elementos de esquema pueden estar relacionados.</span><span class="sxs-lookup"><span data-stu-id="86b3f-136">Schema elements can be related.</span></span> <span data-ttu-id="86b3f-137">El **\<sql:relationship>** elemento especifica la relación primario-secundario entre los elementos del esquema.</span><span class="sxs-lookup"><span data-stu-id="86b3f-137">The **\<sql:relationship>** element specifies the parent-child relationship between the schema elements.</span></span> <span data-ttu-id="86b3f-138">Esta información se usa para actualizar las tablas correspondientes que tienen una relación de clave principal y clave externa.</span><span class="sxs-lookup"><span data-stu-id="86b3f-138">This information is used to update corresponding tables that have primary-key/foreign-key relationship.</span></span>  
  
 <span data-ttu-id="86b3f-139">El siguiente esquema de asignación (SampleSchema.xml) consta de dos elementos, **\<Order>** y **\<OD>** :</span><span class="sxs-lookup"><span data-stu-id="86b3f-139">The following mapping schema (SampleSchema.xml) consists of two elements, **\<Order>** and **\<OD>**:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="OD"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOD" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID"   type="xsd:integer" />  
              <xsd:attribute name="ProductID" type="xsd:integer" />  
             <xsd:attribute name="UnitPrice"  type="xsd:decimal" />  
             <xsd:attribute name="OrderQty"   type="xsd:integer" />  
             <xsd:attribute name="UnitPriceDiscount"   type="xsd:decimal" />  
  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesOrderID"  type="xsd:integer" />  
        <xsd:attribute name="OrderDate"  type="xsd:date" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="86b3f-140">El siguiente diagrama usa este esquema XSD para agregar un nuevo registro de detalle de pedido (un **\<OD>** elemento en el **\<after>** bloque) para el pedido 43860.</span><span class="sxs-lookup"><span data-stu-id="86b3f-140">The following updategram uses this XSD schema to add a new order detail record (an **\<OD>** element in the **\<after>** block) for order 43860.</span></span> <span data-ttu-id="86b3f-141">El atributo `mapping-schema` se usa para especificar el esquema de asignación en el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="86b3f-141">The `mapping-schema` attribute is used to specify the mapping schema in the updategram.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43860" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43860" >  
           <OD ProductID="753" UnitPrice="$10.00"  
               Quantity="5" Discount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="86b3f-142">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="86b3f-142">To test the updategram</span></span>  
  
1.  <span data-ttu-id="86b3f-143">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86b3f-143">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86b3f-144">Guarde el archivo como SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86b3f-144">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="86b3f-145">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86b3f-145">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="86b3f-146">Guarde el archivo como SampleUpdategram.xml en el mismo directorio donde guardó SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86b3f-146">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="86b3f-147">La ruta de acceso al directorio especificada para el esquema de asignación (SampleUpdateSchema.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-147">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86b3f-148">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86b3f-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="86b3f-149">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86b3f-150">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="86b3f-151">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="86b3f-151">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="OD" sql:relation="Sales.SalesOrderDetail" >  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="ProductID" />  
    <AttributeType name="UnitPrice"  dt:type="fixed.14.4" />  
    <AttributeType name="OrderQty" />  
    <AttributeType name="UnitPriceDiscount" />  
  
    <attribute type="SalesOrderID" />  
    <attribute type="ProductID" />  
    <attribute type="UnitPrice" />  
    <attribute type="OrderQty" />  
    <attribute type="UnitPriceDiscount" />  
</ElementType>  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="OrderDate" />  
  
    <attribute type="CustomerID" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <element type="OD" >  
             <sql:relationship   
                   key-relation="Sales.SalesOrderHeader"  
                   key="SalesOrderID"  
                   foreign-key="SalesOrderID"  
                   foreign-relation="Sales.SalesOrderDetail" />  
    </element>  
</ElementType>  
</Schema>  
```  
  
### <a name="c-inserting-a-record-by-using-the-parent-child-relationship-and-inverse-annotation-specified-in-the-xsd-schema"></a><span data-ttu-id="86b3f-152">C.</span><span class="sxs-lookup"><span data-stu-id="86b3f-152">C.</span></span> <span data-ttu-id="86b3f-153">Insertar un registro mediante la relación de elementos primarios y secundarios y la anotación inversa especificada en el esquema XSD</span><span class="sxs-lookup"><span data-stu-id="86b3f-153">Inserting a record by using the parent-child relationship and inverse annotation specified in the XSD schema</span></span>  
 <span data-ttu-id="86b3f-154">En este ejemplo se muestra el modo en que la lógica del diagrama de actualización usa la relación de elementos primarios y secundarios especificada en el esquema XSD para procesar actualizaciones, y el modo en que se usa la anotación `inverse`.</span><span class="sxs-lookup"><span data-stu-id="86b3f-154">This example illustrates how the updategram logic uses the parent-child relationship specified in the XSD to process updates, and how the `inverse` annotation is used.</span></span> <span data-ttu-id="86b3f-155">Para obtener más información sobre la `inverse` anotación, vea [especificar el atributo SQL: inverso en SQL: Relationship &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-155">For more information about the `inverse` annotation, see [Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="86b3f-156">En este ejemplo se da por supuesto que las tablas siguientes se encuentran en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="86b3f-156">This example assumes that the following tables are in the **tempdb** database:</span></span>  
  
-   <span data-ttu-id="86b3f-157">`Cust (CustomerID, CompanyName)`, donde `CustomerID` es la clave principal</span><span class="sxs-lookup"><span data-stu-id="86b3f-157">`Cust (CustomerID, CompanyName)`, where `CustomerID` is the primary key</span></span>  
  
-   <span data-ttu-id="86b3f-158">`Ord (OrderID, CustomerID)`, donde `CustomerID` es una clave externa que hace referencia a la clave principal `CustomerID` de la tabla `Cust`.</span><span class="sxs-lookup"><span data-stu-id="86b3f-158">`Ord (OrderID, CustomerID)`, where `CustomerID` is a foreign key that refers to the `CustomerID` primary key in the `Cust` table.</span></span>  
  
 <span data-ttu-id="86b3f-159">El diagrama de actualización usa el esquema XSD siguiente para insertar registros en las tablas Cust y Ord:</span><span class="sxs-lookup"><span data-stu-id="86b3f-159">The updategram uses the following XSD schema to insert records into the Cust and Ord tables :</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
       <sql:relationship name="OrdCust" inverse="true"  
                  parent="Ord"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Cust"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
<xsd:element name="Order" sql:relation="Ord">  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customer" sql:relationship="OrdCust"/>  
    </xsd:sequence>  
    <xsd:attribute name="OrderID"   type="xsd:int"/>  
    <xsd:attribute name="CustomerID" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
<xsd:element name="Customer" sql:relation="Cust">  
  <xsd:complexType>  
     <xsd:attribute name="CustomerID"  type="xsd:string"/>  
    <xsd:attribute name="CompanyName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="86b3f-160">El esquema XSD de este ejemplo tiene **\<Customer>** **\<Order>** elementos y, y especifica una relación de elementos primarios y secundarios entre los dos elementos.</span><span class="sxs-lookup"><span data-stu-id="86b3f-160">The XSD schema in this example has **\<Customer>** and **\<Order>** elements, and it specifies a parent-child relationship between the two elements.</span></span> <span data-ttu-id="86b3f-161">Identifica **\<Order>** como el elemento primario y **\<Customer>** como el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="86b3f-161">It identifies **\<Order>** as the parent element and **\<Customer>** as the child element.</span></span>  
  
 <span data-ttu-id="86b3f-162">La lógica de procesamiento del diagrama de actualización usa la información de la relación de elementos primarios y secundarios para determinar el orden en que los registros se insertan en las tablas.</span><span class="sxs-lookup"><span data-stu-id="86b3f-162">The updategram processing logic uses the information about the parent-child relationship to determine the order in which records are inserted into tables.</span></span> <span data-ttu-id="86b3f-163">En este ejemplo, la lógica de diagrama primero intenta insertar un registro en la tabla Ord (porque **\<Order>** es el elemento primario) y, a continuación, intenta insertar un registro en la tabla Cust (porque **\<Customer>** es el elemento secundario).</span><span class="sxs-lookup"><span data-stu-id="86b3f-163">In this example, the updategram logic first attempts to insert a record into the Ord table (because **\<Order>** is the parent) and then attempts to insert a record into the Cust table (because **\<Customer>** is the child).</span></span> <span data-ttu-id="86b3f-164">Sin embargo, debido a la información de clave principal y clave externa incluida en el esquema de tabla de base de datos, esta operación de inserción provoca una infracción de clave externa en la base de datos y se produce un error en la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="86b3f-164">However, because of the primary key/foreign key information that is contained in the database table schema, this insert operation causes a foreign key violation in the database and the insert fails.</span></span>  
  
 <span data-ttu-id="86b3f-165">Para indicar a la lógica de diagrama que invierta la relación de elementos primarios y secundarios durante la operación de actualización, la `inverse` anotación se especifica en el **\<relationship>** elemento.</span><span class="sxs-lookup"><span data-stu-id="86b3f-165">To instruct the updategram logic to reverse the parent-child relationship during the update operation, the `inverse` annotation is specified on the **\<relationship>** element.</span></span> <span data-ttu-id="86b3f-166">Como resultado, los registros se agregan primero en la tabla Cust y después en la tabla Ord, y la operación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="86b3f-166">As a result, records are added first in the Cust table and then in the Ord table, and the operation succeeds.</span></span>  
  
 <span data-ttu-id="86b3f-167">El diagrama de actualización siguiente inserta un pedido (OrderID=2) en la tabla Ord y un cliente (CustomerID='AAAAA) en la tabla Cust mediante el esquema XSD especificado:</span><span class="sxs-lookup"><span data-stu-id="86b3f-167">The following updategram inserts an order (OrderID=2) in the Ord table and a customer (CustomerID='AAAAA') in the Cust table by using the specified XSD schema:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before/>  
    <updg:after>  
      <Order OrderID="2" CustomerID="AAAAA" >  
        <Customer CustomerID="AAAAA" CompanyName="AAAAA Company" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="86b3f-168">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="86b3f-168">To test the updategram</span></span>  
  
1.  <span data-ttu-id="86b3f-169">Cree estas tablas en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="86b3f-169">Create these tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust(CustomerID varchar(5) primary key,   
                      CompanyName varchar(20))  
    GO  
    CREATE TABLE Ord (OrderID int primary key,   
                      CustomerID varchar(5) references Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="86b3f-170">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86b3f-170">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86b3f-171">Guarde el archivo como SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86b3f-171">Save the file as SampleUpdateSchema.xml.</span></span>  
  
3.  <span data-ttu-id="86b3f-172">Copie la plantilla de diagrama de actualización anterior y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86b3f-172">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="86b3f-173">Guarde el archivo como SampleUpdategram.xml en el mismo directorio donde guardó SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86b3f-173">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="86b3f-174">La ruta de acceso al directorio especificada para el esquema de asignación (SampleUpdateSchema.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-174">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86b3f-175">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86b3f-175">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
4.  <span data-ttu-id="86b3f-176">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="86b3f-176">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86b3f-177">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86b3f-177">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b3f-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86b3f-178">See Also</span></span>  
 [<span data-ttu-id="86b3f-179">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="86b3f-179">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
