---
title: 'Excluir elementos de esquema del documento XML resultante mediante SQL: alpped (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c79ae005b9630fcbfcd16bfc22c2aeb21b7bf9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672896"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a><span data-ttu-id="00266-102">Excluir elementos de esquema del documento XML resultante mediante sql:mapped (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="00266-102">Excluding Schema Elements from the Resulting XML Document Using sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="00266-103">Cada elemento y atributo del esquema XSD se asigna a una tabla/vista y columna de base de datos debido a la asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00266-103">Every element and attribute in the XSD schema maps to a database table/view and column because of the default mapping.</span></span> <span data-ttu-id="00266-104">Si desea crear un elemento en el esquema XSD que no se asigne a ninguna tabla (vista) o columna de base de datos y que no aparezca en el XML, puede especificar la anotación `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="00266-104">If you want to create an element in the XSD schema that does not map to any database table (view) or column and that does not appear in the XML, you can specify the `sql:mapped` annotation.</span></span>  
  
 <span data-ttu-id="00266-105">La anotación `sql:mapped` es especialmente útil si no se puede modificar el esquema o si se utiliza para validar XML de otros orígenes y, aun así, contiene datos que no están almacenados en su base de datos.</span><span class="sxs-lookup"><span data-stu-id="00266-105">The `sql:mapped` annotation is especially useful if the schema cannot be modified or if the schema is used to validate XML from other sources and yet contains data that is not stored in your database.</span></span> <span data-ttu-id="00266-106">La anotación `sql:mapped` difiere de `sql:is-constant` en que los elementos y atributos no asignados no aparecen en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="00266-106">The `sql:mapped` annotation differs from `sql:is-constant` in that the unmapped elements and attributes do not appear in the XML document.</span></span>  
  
 <span data-ttu-id="00266-107">La anotación `sql:mapped` toma un valor booleano (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="00266-107">The `sql:mapped` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="00266-108">Los valores permitidos son 0, 1, true y false.</span><span class="sxs-lookup"><span data-stu-id="00266-108">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="00266-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="00266-109">Examples</span></span>  
 <span data-ttu-id="00266-110">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="00266-110">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="00266-111">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="00266-111">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a><span data-ttu-id="00266-112">A.</span><span class="sxs-lookup"><span data-stu-id="00266-112">A.</span></span> <span data-ttu-id="00266-113">Especificar la anotación sql:mapped</span><span class="sxs-lookup"><span data-stu-id="00266-113">Specifying the sql:mapped annotation</span></span>  
 <span data-ttu-id="00266-114">Suponga que tiene un esquema XSD de algún otro origen.</span><span class="sxs-lookup"><span data-stu-id="00266-114">Assume you have an XSD schema from some other source.</span></span> <span data-ttu-id="00266-115">Este esquema XSD está compuesto de un **\<Person.Contact>** elemento con los atributos **ContactID**, **FirstName**, **LastName**y **HomeAddress** .</span><span class="sxs-lookup"><span data-stu-id="00266-115">This XSD schema consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, **LastName**, and **HomeAddress** attributes.</span></span>  
  
 <span data-ttu-id="00266-116">Al asignar este esquema XSD a la tabla person. contact de la base de datos AdventureWorks, `sql:mapped` se especifica en el atributo **HomeAddress** porque la tabla Employees no almacena las direcciones particulares de los empleados.</span><span class="sxs-lookup"><span data-stu-id="00266-116">In mapping this XSD schema to the Person.Contact table in the AdventureWorks database, `sql:mapped` is specified on the **HomeAddress** attribute because the Employees table does not store the home addresses of employees.</span></span> <span data-ttu-id="00266-117">Por consiguiente, este atributo no se asigna a la base de datos y no se devuelve en el documento XML resultante cuando se especifica una consulta XPath en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="00266-117">As a result, this attribute is not mapped to the database and is not returned in the resulting XML document when an XPath query is specified against the mapping schema.</span></span>  
  
 <span data-ttu-id="00266-118">Para el resto del esquema se produce una asignación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00266-118">Default mapping takes place for the rest of the schema.</span></span> <span data-ttu-id="00266-119">El **\<Person.Contact>** elemento se asigna a la tabla person. contact y todos los atributos se asignan a las columnas con el mismo nombre en la tabla person. contact.</span><span class="sxs-lookup"><span data-stu-id="00266-119">The **\<Person.Contact>** element maps to the Person.Contact table, and all the attributes map to the columns with the same name in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="00266-120">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="00266-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="00266-121">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="00266-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="00266-122">Guarde el archivo como sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="00266-122">Save the file as sql-mapped.xml.</span></span>  
  
2.  <span data-ttu-id="00266-123">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="00266-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="00266-124">Guarde el archivo como sql-mappedT.xml en el mismo directorio donde guardó sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="00266-124">Save the file as sql-mappedT.xml in the same directory where you saved sql-mapped.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="00266-125">La ruta de acceso al directorio especificada para el esquema de asignación (MySchema.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="00266-125">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="00266-126">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="00266-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  <span data-ttu-id="00266-127">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="00266-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="00266-128">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="00266-128">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="00266-129">Éste es el conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="00266-129">This is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 <span data-ttu-id="00266-130">Observe que ContactID, FirstName y LastName están presentes, pero no lo está HomeAddress porque el esquema de asignación especificó 0 para el atributo `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="00266-130">Note that the ContactID, FirstName, and LastName are present, but HomeAddress is not because the mapping schema specified 0 for the `sql:mapped` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00266-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00266-131">See Also</span></span>  
 [<span data-ttu-id="00266-132">Asignación predeterminada de elementos y atributos XSD a tablas y columnas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="00266-132">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
