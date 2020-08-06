---
title: Asignación predeterminada de elementos y atributos XSD a tablas y columnas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XSD schemas [SQLXML], mapping attributes and elements
- mapping schema [SQLXML], default mapping
- element mapping [SQLXML], default mapping
- element mapping [SQLXML]
- table mapping [SQLXML]
- annotated XSD schemas, mapping attributes and elements
- table/view mapping [SQLXML]
- column mapping [SQLXML]
- attribute mapping [SQLXML], default mapping
- default schema mapping
- table mapping [SQLXML], default mapping
- testing XPath query against schema
- xml data type [SQL Server], SQLXML
- table/view mapping [SQLXML], default mapping
- element/attribute mapping [SQLXML]
ms.assetid: 9a18e92a-6cfb-4a14-993a-663a95aabb63
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bccec2413e8a0a6e13283a0f3e5f63ab61e934b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672895"
---
# <a name="default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="365c6-102">Asignación predeterminada de elementos y atributos XSD a tablas y columnas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="365c6-102">Default Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="365c6-103">De forma predeterminada, un elemento de tipo complejo en un esquema XSD anotado se asigna a una tabla (vista) con el mismo nombre en la base de datos especificada, mientras que un elemento o atributo de tipo simple se asigna a la columna con el mismo nombre en la tabla.</span><span class="sxs-lookup"><span data-stu-id="365c6-103">By default, an element of complex type in an XSD annotated schema maps to the table (view) with the same name in the specified database, and an element or attribute of simple type maps to the column with the same name in the table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="365c6-104">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="365c6-104">Examples</span></span>  
 <span data-ttu-id="365c6-105">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="365c6-105">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="365c6-106">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="365c6-106">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-default-mapping"></a><span data-ttu-id="365c6-107">A.</span><span class="sxs-lookup"><span data-stu-id="365c6-107">A.</span></span> <span data-ttu-id="365c6-108">Especificar la asignación predeterminada</span><span class="sxs-lookup"><span data-stu-id="365c6-108">Specifying default mapping</span></span>  
 <span data-ttu-id="365c6-109">En este ejemplo, no hay ninguna anotación especificada en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="365c6-109">In this example, no annotations are specified in the XSD schema.</span></span> <span data-ttu-id="365c6-110">El **\<Person.Contact>** elemento es de tipo complejo y, por consiguiente, se asigna de forma predeterminada a la tabla person. contact de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="365c6-110">The **\<Person.Contact>** element is of complex type and, therefore, maps by default to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="365c6-111">Todos los atributos (ContactID, FirstName, LastName) del **\<Person.Contact>** elemento son de tipo simple y se asignan de forma predeterminada a columnas con los mismos nombres en la tabla person. contact.</span><span class="sxs-lookup"><span data-stu-id="365c6-111">All the attributes (ContactID, FirstName, LastName) of the **\<Person.Contact>** element are of simple type and map by default to columns with the same names in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  type="xsd:string" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="365c6-112">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="365c6-112">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="365c6-113">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="365c6-113">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="365c6-114">Guarde el archivo como MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="365c6-114">Save the file as MySchema.xml.</span></span>  
  
2.  <span data-ttu-id="365c6-115">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="365c6-115">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="365c6-116">Guarde el archivo como MySchemaT.xml en el mismo directorio donde guardó MySchemaT.xml.</span><span class="sxs-lookup"><span data-stu-id="365c6-116">Save the file as MySchemaT.xml in the same directory where you saved MySchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchema.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="365c6-117">La ruta de acceso al directorio especificada para el esquema de asignación (MySchema.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="365c6-117">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="365c6-118">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="365c6-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema.xml"  
    ```  
  
3.  <span data-ttu-id="365c6-119">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="365c6-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="365c6-120">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="365c6-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="365c6-121">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="365c6-121">Here is the partial result set:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8" ?>  
<ROOT>  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong"/>  
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel"/>  
   ...  
</ROOT>  
```  
  
### <a name="b-mapping-an-xml-element-to-a-database-column"></a><span data-ttu-id="365c6-122">B.</span><span class="sxs-lookup"><span data-stu-id="365c6-122">B.</span></span> <span data-ttu-id="365c6-123">Asignar un elemento XML a una columna de base de datos</span><span class="sxs-lookup"><span data-stu-id="365c6-123">Mapping an XML element to a database column</span></span>  
 <span data-ttu-id="365c6-124">En este ejemplo, la asignación predeterminada también tiene lugar debido a que no se usa ninguna anotación.</span><span class="sxs-lookup"><span data-stu-id="365c6-124">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="365c6-125">El **\<Person.Contact>** elemento es de tipo complejo y se asigna a la tabla con el mismo nombre en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="365c6-125">The **\<Person.Contact>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="365c6-126">Los elementos **\<FirstName>** y **\<LastName>** y el atributo **EmployeeID** son de tipo simple y, por lo tanto, se asignan a las columnas con los mismos nombres.</span><span class="sxs-lookup"><span data-stu-id="365c6-126">The elements **\<FirstName>** and **\<LastName>** and the **EmployeeID** attribute are of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="365c6-127">La única diferencia entre esto y el ejemplo anterior es que los elementos se usan para asignar los campos de FirstName y LastName.</span><span class="sxs-lookup"><span data-stu-id="365c6-127">The only difference between this and the previous example are that elements are used for mapping the FirstName and LastName fields.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="FirstName" type="xsd:string" />   
        <xsd:element name="LastName" type="xsd:string" />   
      </xsd:sequence>  
      <xsd:attribute name="ContactID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="365c6-128">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="365c6-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="365c6-129">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="365c6-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="365c6-130">Guarde el archivo como MySchemaElements.xml.</span><span class="sxs-lookup"><span data-stu-id="365c6-130">Save the file as MySchemaElements.xml.</span></span>  
  
2.  <span data-ttu-id="365c6-131">Cree la plantilla siguiente (MySchemaElementsT.xml) y guárdela en el mismo directorio que utilizó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="365c6-131">Create the following template (MySchemaElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaElements.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="365c6-132">La ruta de acceso al directorio especificada para el esquema de asignación es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="365c6-132">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="365c6-133">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="365c6-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaElements.xml"  
    ```  
  
3.  <span data-ttu-id="365c6-134">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="365c6-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="365c6-135">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="365c6-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="365c6-136">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="365c6-136">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1">  
    <FirstName>Gustavo</FirstName>  
    <LastName>Achong</LastName>  
  </Person.Contact>  
   ...  
</ROOT>  
```  
  
### <a name="c-mapping-an-xml-element-to-an-xml-data-type-column"></a><span data-ttu-id="365c6-137">C.</span><span class="sxs-lookup"><span data-stu-id="365c6-137">C.</span></span> <span data-ttu-id="365c6-138">Asignar un elemento XML a una columna de tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="365c6-138">Mapping an XML element to an XML data type column</span></span>  
 <span data-ttu-id="365c6-139">En este ejemplo, la asignación predeterminada también tiene lugar debido a que no se usa ninguna anotación.</span><span class="sxs-lookup"><span data-stu-id="365c6-139">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="365c6-140">El **\<Production.ProductModel>** elemento es de tipo complejo y se asigna a la tabla con el mismo nombre en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="365c6-140">The **\<Production.ProductModel>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="365c6-141">El atributo **ProductModelID** es de tipo simple y, por lo tanto, se asigna a las columnas con los mismos nombres.</span><span class="sxs-lookup"><span data-stu-id="365c6-141">The **ProductModelID** attribute is of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="365c6-142">La única diferencia entre este y los ejemplos anteriores es que el **\<Instructions>** elemento se asigna a una columna que utiliza el `xml` tipo de datos mediante el `xsd:anyType` tipo.</span><span class="sxs-lookup"><span data-stu-id="365c6-142">The only difference between this and the previous examples is that the **\<Instructions>** element is mapping to a column that uses the `xml` data type by using the `xsd:anyType` type.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Instructions" type="xsd:anyType" />   
      </xsd:sequence>  
      <xsd:attribute name="ProductModelID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="365c6-143">El tipo de datos `xml` se introdujo en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="365c6-143">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="365c6-144">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="365c6-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="365c6-145">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="365c6-145">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="365c6-146">Guarde el archivo como MySchemaXmlAnyElements.xml.</span><span class="sxs-lookup"><span data-stu-id="365c6-146">Save the file as MySchemaXmlAnyElements.xml.</span></span>  
  
2.  <span data-ttu-id="365c6-147">Cree la plantilla siguiente (MySchemaXmlAnyElements.xml) y guárdela en el mismo directorio que utilizó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="365c6-147">Create the following template (MySchemaXmlAnyElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaXmlAnyElements.xml">  
            /Production.ProductModel[@ProductModelID=7]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="365c6-148">La ruta de acceso al directorio especificada para el esquema de asignación es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="365c6-148">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="365c6-149">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="365c6-149">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaXmlAnyElements.xml"  
    ```  
  
3.  <span data-ttu-id="365c6-150">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="365c6-150">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="365c6-151">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="365c6-151">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="365c6-152">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="365c6-152">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductModel ProductModelID="7">  
    <Instructions>  
      <root xmlns="http:  
//schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstru  
ctions">  
...  
      </root>  
    <Instructions>  
  </Production.ProductModel>  
</ROOT>  
```  
  
## <a name="see-also"></a><span data-ttu-id="365c6-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="365c6-153">See Also</span></span>  
 <span data-ttu-id="365c6-154">[Consideraciones sobre la seguridad del esquema anotado &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="365c6-154">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="365c6-155">[Datos XML &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="365c6-155">[XML Data &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span></span>  
 [<span data-ttu-id="365c6-156">Compatibilidad con tipos de datos xml en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="365c6-156">xml Data Type Support in SQLXML 4.0</span></span>](../sqlxml/xml-data-type-support-in-sqlxml-4-0.md)  
  
  
