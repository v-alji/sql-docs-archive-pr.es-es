---
title: Asignación explícita de elementos y atributos XSD a tablas y columnas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- sql:field
- row mapping [SQLXML]
- attribute mapping [SQLXML], explicit mapping
- field annotation
- XSD schemas [SQLXML], mapping attributes and elements
- names [SQLXML]
- relation annotation
- table/view mapping [SQLXML], explicit mapping
- sql:relation
- mapping schema [SQLXML], explicit mapping
- annotated XSD schemas, mapping attributes and elements
- column mapping [SQLXML]
- element mapping [SQLXML], explicit mapping
- table mapping [SQLXML], explicit mapping
- element/attribute mapping [SQLXML]
ms.assetid: 7a5ebeb6-7322-4141-a307-ebcf95976146
author: rothja
ms.author: jroth
ms.openlocfilehash: f3400682b5f28835ca039912aab058691929a6c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669547"
---
# <a name="explicit-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="4604b-102">Asignación explícita de elementos y atributos XSD a tablas y columnas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4604b-102">Explicit Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="4604b-103">Cuando se utiliza un esquema XSD para proporcionar una vista XML de la base de datos relacional, los elementos y atributos del esquema se deben asignar a tablas y columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4604b-103">When using an XSD schema to provide an XML view of the relational database , the elements and attributes of the schema must be mapped to tables and columns of the database.</span></span> <span data-ttu-id="4604b-104">Las filas de la tabla o vista de la base de datos se asignarán a elementos del documento XML.</span><span class="sxs-lookup"><span data-stu-id="4604b-104">The rows in the database table/view will map to elements in the XML document.</span></span> <span data-ttu-id="4604b-105">Los valores de columna de la base de datos se asignan a atributos o elementos.</span><span class="sxs-lookup"><span data-stu-id="4604b-105">The column values in the database map to attributes or elements.</span></span>  
  
 <span data-ttu-id="4604b-106">Cuando se especifican consultas XPath en el esquema XSD agregado, los datos de los elementos y atributos del esquema se recuperan de las tablas y columnas a las que se asignan.</span><span class="sxs-lookup"><span data-stu-id="4604b-106">When XPath queries are specified against the annotated XSD schema, the data for the elements and attributes in the schema is retrieved from the tables and columns to which they map.</span></span> <span data-ttu-id="4604b-107">Para obtener un único valor de la base de datos, la asignación especificada en el esquema XSD debe tener una especificación de campo y relación.</span><span class="sxs-lookup"><span data-stu-id="4604b-107">To obtain a single value from the database, the mapping specified in the XSD schema must have both relation and field specification.</span></span> <span data-ttu-id="4604b-108">Si el nombre de un elemento o atributo no es el mismo que el nombre de la tabla/vista o columna al que se asigna, las anotaciones `sql:relation` y `sql:field` se utilizan para especificar la asignación entre un elemento o atributo de un documento XML y la tabla (vista) o columna de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4604b-108">If the name of an element/attribute is not the same name as the table/view or column name to which it maps, the `sql:relation` and `sql:field` annotations are used to specify the mapping between an element or attribute in an XML document and the table (view) or column in a database.</span></span>  
  
## <a name="sql-relation"></a><span data-ttu-id="4604b-109">sql-relation</span><span class="sxs-lookup"><span data-stu-id="4604b-109">sql-relation</span></span>  
 <span data-ttu-id="4604b-110">La anotación `sql:relation` se agrega para asignar un nodo XML en el esquema XSD a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4604b-110">The `sql:relation` annotation is added to map an XML node in the XSD schema to a database table.</span></span> <span data-ttu-id="4604b-111">El nombre de una tabla (vista) se especifica como el valor de la anotación `sql:relation`.</span><span class="sxs-lookup"><span data-stu-id="4604b-111">The name of a table (view) is specified as the value of the `sql:relation` annotation.</span></span>  
  
 <span data-ttu-id="4604b-112">Cuando se especifica `sql:relation` en un elemento, el ámbito de esta anotación se aplica a todos los atributos y elementos secundarios que se describen en la definición del tipo complejo de ese elemento, proporcionando por lo tanto un acceso directo para escribir anotaciones.</span><span class="sxs-lookup"><span data-stu-id="4604b-112">When `sql:relation` is specified on an element, the scope of this annotation applies to all attributes and child elements that are described in the complex type definition of that element, therefore providing a shortcut in writing annotations.</span></span>  
  
 <span data-ttu-id="4604b-113">La `sql:relation` anotación también es útil cuando los identificadores que son válidos en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no son válidos en XML.</span><span class="sxs-lookup"><span data-stu-id="4604b-113">The `sql:relation` annotation is also useful when identifiers that are valid in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are not valid in XML.</span></span> <span data-ttu-id="4604b-114">Por ejemplo, "Order Details" es un nombre de tabla válido en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pero no en XML.</span><span class="sxs-lookup"><span data-stu-id="4604b-114">For example, "Order Details" is a valid table name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but not in XML.</span></span> <span data-ttu-id="4604b-115">En casos como éste, la anotación `sql:relation` se puede utilizar para especificar la asignación, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4604b-115">In such cases, the `sql:relation` annotation can be used to specify the mapping, for example:</span></span>  
  
```  
<xsd:element name="OD" sql:relation="[Order Details]">  
```  
  
## <a name="sql-field"></a><span data-ttu-id="4604b-116">sql-field</span><span class="sxs-lookup"><span data-stu-id="4604b-116">sql-field</span></span>  
 <span data-ttu-id="4604b-117">La anotación `sql-field` asigna un elemento o atributo a una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4604b-117">The `sql-field` annotation maps an element or attribute to a database column.</span></span> <span data-ttu-id="4604b-118">La anotación `sql:field` se agrega para asignar un nodo XML del esquema a una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4604b-118">The `sql:field` annotation is added to map an XML node in the schema to a database column.</span></span> <span data-ttu-id="4604b-119">No se puede especificar `sql:field` en un elemento de contenido vacío.</span><span class="sxs-lookup"><span data-stu-id="4604b-119">You cannot specify `sql:field` on an empty content element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4604b-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4604b-120">Examples</span></span>  
 <span data-ttu-id="4604b-121">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="4604b-121">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="4604b-122">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4604b-122">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelation-and-sqlfield-annotations"></a><span data-ttu-id="4604b-123">A.</span><span class="sxs-lookup"><span data-stu-id="4604b-123">A.</span></span> <span data-ttu-id="4604b-124">Especificar las anotaciones sql:relation y sql:field</span><span class="sxs-lookup"><span data-stu-id="4604b-124">Specifying the sql:relation and sql:field annotations</span></span>  
 <span data-ttu-id="4604b-125">En este ejemplo, el esquema XSD está compuesto de un **\<Contact>** elemento de tipo complejo con los **\<FName>** **\<LName>** elementos secundarios y y el atributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="4604b-125">In this example, the XSD schema consists of an **\<Contact>** element of complex type with **\<FName>** and **\<LName>** child elements and the **ContactID** attribute.</span></span>  
  
 <span data-ttu-id="4604b-126">La `sql:relation` anotación asigna el **\<Contact>** elemento a la tabla person. contact de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4604b-126">The `sql:relation` annotation maps the **\<Contact>** element to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="4604b-127">La `sql:field` anotación asigna el **\<FName>** elemento a la columna FirstName y el **\<LName>** elemento a la columna LastName.</span><span class="sxs-lookup"><span data-stu-id="4604b-127">The `sql:field` annotation maps the **\<FName>** element to the FirstName column and the **\<LName>** element to the LastName column.</span></span>  
  
 <span data-ttu-id="4604b-128">No se especifica ninguna anotación para el atributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="4604b-128">No annotation is specified for the **ContactID** attribute.</span></span> <span data-ttu-id="4604b-129">Esto produce una asignación predeterminada del atributo a la columna del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="4604b-129">This results in a default mapping of the attribute to the column with the same name.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4604b-130">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="4604b-130">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4604b-131">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4604b-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="4604b-132">Guarde el archivo como MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="4604b-132">Save the file as MySchema-annotated.xml.</span></span>  
  
2.  <span data-ttu-id="4604b-133">Copie la siguiente plantilla y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4604b-133">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="4604b-134">Guarde el archivo como MySchema-annotatedT.xml en el mismo directorio donde guardó MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="4604b-134">Save the file as MySchema-annotatedT.xml in the same directory where you saved MySchema-annotated.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="MySchema-annotated.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4604b-135">La ruta de acceso al directorio especificada para el esquema de asignación (MySchema-annotated.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4604b-135">The directory path specified for the mapping schema (MySchema-annotated.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4604b-136">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4604b-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema-annotated.xml"  
    ```  
  
3.  <span data-ttu-id="4604b-137">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4604b-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4604b-138">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4604b-138">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4604b-139">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="4604b-139">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
 <Contact ContactID="1">   
    <FName>Gustavo</FName>   
    <LName>Achong</LName>   
 </Contact>   
  .....  
</ROOT>  
```  
  
  
