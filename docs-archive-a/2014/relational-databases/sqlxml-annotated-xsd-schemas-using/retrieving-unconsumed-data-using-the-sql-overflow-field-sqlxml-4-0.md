---
title: 'Recuperar datos no utilizados mediante SQL: Overflow-Field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- unconsumed data
- storing unconsumed data
- retrieving unconsumed data
- annotated XSD schemas, unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: 8526998d-b47d-4a32-8dc2-7f50a8d11097
author: rothja
ms.author: jroth
ms.openlocfilehash: 796fda9428954c5f18c5d37b353de9fd4122551e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676420"
---
# <a name="retrieving-unconsumed-data-using-the-sqloverflow-field-sqlxml-40"></a><span data-ttu-id="81f5e-102">Recuperar datos no utilizados mediante sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="81f5e-102">Retrieving Unconsumed Data Using the sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="81f5e-103">Cuando se insertan registros en una base de datos de un documento XML utilizando la función [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML, se pueden almacenar todos los datos no consumidos del documento XML en una columna.</span><span class="sxs-lookup"><span data-stu-id="81f5e-103">When records are inserted in a database from an XML document by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML function, all the unconsumed data from the source XML document can be stored in a column.</span></span> <span data-ttu-id="81f5e-104">Cuando recupere datos de una base de datos utilizando esquemas anotados, puede especificar el atributo `sql:overflow-field` para identificar la columna en la tabla en la que se almacenan los datos de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="81f5e-104">When you retrieve data from a database by using annotated schemas, you can specify the `sql:overflow-field` attribute to identify the column in the table in which the overflow data is stored.</span></span> <span data-ttu-id="81f5e-105">El `sql:overflow-field` atributo se puede especificar en **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="81f5e-105">The `sql:overflow-field` attribute can be specified on **\<element>**.</span></span>  
  
 <span data-ttu-id="81f5e-106">Este dato se recupera después de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="81f5e-106">This data is then retrieved in these ways:</span></span>  
  
-   <span data-ttu-id="81f5e-107">Los atributos almacenados en la columna de desbordamiento se agregan al elemento que contiene la anotación `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="81f5e-107">Attributes stored in the overflow column are added to the element that contains the `sql:overflow-field` annotation.</span></span>  
  
-   <span data-ttu-id="81f5e-108">Los elementos secundarios y sus descendientes, almacenados en la columna de desbordamiento de la base de datos, se agregan como elementos secundarios que siguen al contenido que se especifica explícitamente en el esquema.</span><span class="sxs-lookup"><span data-stu-id="81f5e-108">The child elements and their descendents, stored in the overflow column in the database, are added as child elements following the content that is explicitly specified in the schema.</span></span> <span data-ttu-id="81f5e-109">(No se mantiene ningún orden.)</span><span class="sxs-lookup"><span data-stu-id="81f5e-109">(No order is preserved.)</span></span>  
  
## <a name="examples"></a><span data-ttu-id="81f5e-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="81f5e-110">Examples</span></span>  
 <span data-ttu-id="81f5e-111">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="81f5e-111">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="81f5e-112">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="81f5e-112">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqloverflow-field-for-an-element"></a><span data-ttu-id="81f5e-113">A.</span><span class="sxs-lookup"><span data-stu-id="81f5e-113">A.</span></span> <span data-ttu-id="81f5e-114">Especificar SQL:OVERFLOW-FIELD para un elemento</span><span class="sxs-lookup"><span data-stu-id="81f5e-114">Specifying sql:overflow-field for an element</span></span>  
 <span data-ttu-id="81f5e-115">En este ejemplo se entiende que se ha ejecutado el siguiente script para que exista una tabla denominada Customers2 en la base de datos tempdb:</span><span class="sxs-lookup"><span data-stu-id="81f5e-115">This example assumes that the following script has been run so that a table named Customers2 exists in the tempdb database:</span></span>  
  
```  
USE tempdb  
CREATE TABLE Customers2 (  
CustomerID       VARCHAR(10),   
ContactName    VARCHAR(30),   
AddressOverflow    NVARCHAR(500))  
  
GO  
INSERT INTO Customers2 VALUES (  
'ALFKI',   
'Joe',  
'<Address>  
  <Address1>Maple St.</Address1>  
  <Address2>Apt. E105</Address2>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98147</Zip>  
 </Address>')  
GO  
```  
  
 <span data-ttu-id="81f5e-116">Además, debe crear un directorio virtual para la base de datos Tempdb, y un nombre virtual de plantilla de `template` tipo denominado "template".</span><span class="sxs-lookup"><span data-stu-id="81f5e-116">In addition, you must create a virtual directory for the tempdb database-and a template virtual name of `template` type named "template".</span></span>  
  
 <span data-ttu-id="81f5e-117">En el ejemplo siguiente, el esquema de asignación recupera los datos no consumidos que están almacenados en la columna AddressOverflow de la tabla Customers2:</span><span class="sxs-lookup"><span data-stu-id="81f5e-117">In the following example, the mapping schema retrieves the unconsumed data that is stored in the AddressOverflow column of the Customers2 table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customers2" sql:overflow-field="AddressOverflow" >  
    <xsd:complexType>  
      <xsd:attribute name="CustomerID"  type="xsd:integer"/>  
      <xsd:attribute name="ContactName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="81f5e-118">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="81f5e-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="81f5e-119">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="81f5e-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="81f5e-120">Guarde el archivo como Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="81f5e-120">Save the file as Overflow.xml.</span></span>  
  
2.  <span data-ttu-id="81f5e-121">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="81f5e-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="81f5e-122">Guarde el archivo como OverflowT.xml en el mismo directorio donde guardó Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="81f5e-122">Save the file as OverflowT.xml in the same directory where you saved Overflow.xml.</span></span> <span data-ttu-id="81f5e-123">La consulta de la plantilla selecciona los registros de la tabla Customers2.</span><span class="sxs-lookup"><span data-stu-id="81f5e-123">The query in the template selects the records in the Customers2 table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Overflow.xml">  
            /Customers2  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="81f5e-124">La ruta de acceso al directorio especificada para el esquema de asignación (Overflow.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f5e-124">The directory path specified for the mapping schema (Overflow.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="81f5e-125">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="81f5e-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\Overflow.xml"  
    ```  
  
3.  <span data-ttu-id="81f5e-126">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f5e-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="81f5e-127">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="81f5e-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="81f5e-128">El conjunto de resultados es:</span><span class="sxs-lookup"><span data-stu-id="81f5e-128">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers2 CustomerID="ALFKI" ContactName="Joe">  
    <Address1>Maple St.</Address1>   
    <Address2>Apt. E105</Address2>   
    <City>Seattle</City>   
    <State>WA</State>   
    <Zip>98147</Zip>   
  </Customers2>  
</ROOT>  
```  
  
  
