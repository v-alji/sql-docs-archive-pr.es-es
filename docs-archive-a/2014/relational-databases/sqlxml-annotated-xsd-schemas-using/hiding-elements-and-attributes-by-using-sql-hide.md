---
title: 'Ocultar elementos y atributos mediante SQL: Hide | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- hiding elements
- element mapping [SQLXML], hiding attributes and elements
- hide annotation
- sql:hide
- table/view mapping [SQLXML], hiding attributes and elements
- table mapping [SQLXML], hiding attributes and elements
- hiding attributes
- annotated XSD schemas, hiding attributes and elements
- attribute mapping [SQLXML], hiding attributes and elements
- column mapping [SQLXML]
- element hiding [SQLXML]
- XSD schemas [SQLXML], hiding attributes and elements
- attribute hiding [SQLXML]
ms.assetid: 0978301b-f068-46b6-82b9-dc555161f52e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a3beb48be1d9809b170faeafa964ba45156ac28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750569"
---
# <a name="hiding-elements-and-attributes-by-using-sqlhide"></a><span data-ttu-id="19581-102">Ocultar elementos y atributos mediante sql:hide</span><span class="sxs-lookup"><span data-stu-id="19581-102">Hiding Elements and Attributes by Using sql:hide</span></span>
  <span data-ttu-id="19581-103">Cuando se ejecuta una consulta XPath en un esquema XSD, el documento XML resultante tiene elementos y atributos que se especifican en el esquema.</span><span class="sxs-lookup"><span data-stu-id="19581-103">When an XPath query is executed against an XSD schema, the resulting XML document has elements and attributes that are specified in the schema.</span></span> <span data-ttu-id="19581-104">Es posible especificar que algunos elementos y atributos se oculten en el esquema utilizando la anotación `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="19581-104">You can specify that some elements and attributes be hidden in the schema by using the `sql:hide` annotation.</span></span> <span data-ttu-id="19581-105">Esto resulta muy útil cuando los criterios de selección de la consulta requieren determinados elementos o atributos en el esquema, pero no desea que se devuelvan en el documento XML que se genera.</span><span class="sxs-lookup"><span data-stu-id="19581-105">This is useful when the selection criteria of the query require particular elements or attributes in the schema, but you do not want them returned in the XML document that is generated.</span></span>  
  
 <span data-ttu-id="19581-106">La anotación `sql:hide` toma un valor booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="19581-106">The `sql:hide` annotation takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="19581-107">Los valores permitidos son 0, 1, true y false.</span><span class="sxs-lookup"><span data-stu-id="19581-107">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="19581-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="19581-108">Examples</span></span>  
 <span data-ttu-id="19581-109">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="19581-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="19581-110">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="19581-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlhide-on-an-attribute"></a><span data-ttu-id="19581-111">A.</span><span class="sxs-lookup"><span data-stu-id="19581-111">A.</span></span> <span data-ttu-id="19581-112">Especificar sql:hide en un atributo</span><span class="sxs-lookup"><span data-stu-id="19581-112">Specifying sql:hide on an attribute</span></span>  
 <span data-ttu-id="19581-113">El esquema XSD de este ejemplo consta de un **\<Person.Contact>** elemento con los atributos **ContactID**, **FirstName**y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="19581-113">The XSD schema in this example consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span>  
  
 <span data-ttu-id="19581-114">El **\<Person.Contact>** elemento es de tipo complejo y, por lo tanto, se asigna a la tabla del mismo nombre (asignación predeterminada).</span><span class="sxs-lookup"><span data-stu-id="19581-114">The **\<Person.Contact>** element is of complex type and, therefore, maps to the table of the same name (default mapping).</span></span> <span data-ttu-id="19581-115">Todos los atributos del **\<Person.Contact>** elemento son de tipo simple y se asignan a columnas con los mismos nombres en person. Contacttable en la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="19581-115">All the attributes of **\<Person.Contact>** element are of simple type and map to columns with the same names in the Person.Contacttable in the AdventureWorks database.</span></span> <span data-ttu-id="19581-116">En el esquema, la `sql:hide` anotación se especifica en el atributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="19581-116">In the schema, the `sql:hide` annotation is specified on the **ContactID** attribute.</span></span> <span data-ttu-id="19581-117">Cuando se especifica una consulta XPath en este esquema, el **ContactID** no se devuelve en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="19581-117">When an XPath query is specified against this schema, the **ContactID** is not returned in the XML document.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  sql:hide="true" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="19581-118">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="19581-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="19581-119">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="19581-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="19581-120">Guarde el archivo como Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="19581-120">Save the file as Hide.xml.</span></span>  
  
2.  <span data-ttu-id="19581-121">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="19581-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="19581-122">Guarde el archivo como HideT.xml en el mismo directorio donde guardó Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="19581-122">Save the file as HideT.xml in the same directory where you saved Hide.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Hide.xml">  
            /Person.Contact[@ContactID="1"]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="19581-123">La ruta de acceso al directorio especificada para el esquema de asignación (Hide.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="19581-123">The directory path specified for the mapping schema (Hide.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="19581-124">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19581-124">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\Hide.xml"  
    ```  
  
3.  <span data-ttu-id="19581-125">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="19581-125">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="19581-126">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="19581-126">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="19581-127">El conjunto de resultados es:</span><span class="sxs-lookup"><span data-stu-id="19581-127">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <Person.Contact FirstName="Gustavo" LastName="Achong" />   
</ROOT>  
```  
  
 <span data-ttu-id="19581-128">Cuando se especifica `sql:hide` en un elemento, el elemento y sus atributos o elementos secundarios no aparecen en el documento XML que se genera.</span><span class="sxs-lookup"><span data-stu-id="19581-128">When `sql:hide` is specified on an element, the element and its attributes or child elements do not appear in the XML document that is generated.</span></span> <span data-ttu-id="19581-129">Este es otro esquema XSD en `sql:hide` el que se especifica en el **\<OD>** elemento:</span><span class="sxs-lookup"><span data-stu-id="19581-129">Here is another XSD schema in which `sql:hide` is specified on the **\<OD>** element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:annotation>  
    <xsd:documentation>  
      Sales.Customer-Sales.SalesOrderHeader-Sales.SalesOrderDetail Schema  
      Copyright 2004 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="CustomerOrder"  
         parent="Sales.Customer"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Sales.SalesOrderHeader" />  
       <sql:relationship name="OrderOrderDetails"  
                  parent="Sales.SalesOrderHeader"  
                  parent-key="SalesOrderID"  
                  child-key="SalesOrderID"  
                  child="Sales.SalesOrderDetail"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Sales.Customer">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
                     maxOccurs="unbounded"   
                     sql:relationship="CustomerOrder">  
          <xsd:complexType>  
            <xsd:sequence>  
               <xsd:element name="OD" sql:relation="Sales.SalesOrderDetail"                                       maxOccurs="unbounded"                                       sql:relationship="OrderOrderDetails"                                       sql:hide="1">  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:string"/>  
                    <xsd:attribute name="ProductID" type="xsd:string"/>  
                  </xsd:complexType>  
               </xsd:element>  
            </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string"/>  
          <xsd:attribute name="OID" sql:field="SalesOrderID"   
                                    type="xsd:string"/>  
          <xsd:attribute name="OrderDate" type="xsd:date"/>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CID" sql:field="CustomerID"   
                                type="xsd:string"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="19581-130">Cuando se especifica una consulta XPath (por ejemplo `/Customers[@CID="1"]` ) en este esquema, el documento XML que se genera no incluye el **\<OD>** elemento y sus elementos secundarios, tal y como se muestra en este resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="19581-130">When an XPath query (for example `/Customers[@CID="1"]`) is specified against this schema, the XML document that is generated does not include the **\<OD>** element and its children, as shown in this partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers CID="1">  
    <Order CustomerID="1" OID="43860" OrderDate="2001-08-01" />   
    <Order CustomerID="1" OID="44501" OrderDate="2001-11-01" />   
    <Order CustomerID="1" OID="45283" OrderDate="2002-02-01" />   
    <Order CustomerID="1" OID="46042" OrderDate="2002-05-01" />   
  </Customers>  
</ROOT>  
```  
  
  
