---
title: 'Ejemplo: solicitar esquemas como resultados con las opciones XMLDATA y XMLSCHEMA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, requesting schema example
- RAW mode, with XMLDATA and XMLSCHEMA
ms.assetid: 3504ca38-be66-42b2-8dab-f499c9584840
author: rothja
ms.author: jroth
ms.openlocfilehash: af244e3436df4d8665079ce20fb749a44021fe04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749205"
---
# <a name="example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options"></a><span data-ttu-id="97bb4-102">Ejemplo: Solicitud de esquemas como resultados con las opciones XMLDATA y XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="97bb4-102">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>
  <span data-ttu-id="97bb4-103">Esta consulta devuelve el esquema XML-DATA que describe la estructura del documento.</span><span class="sxs-lookup"><span data-stu-id="97bb4-103">The following query returns the XML-DATA schema that describes the document structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97bb4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97bb4-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLDATA  
GO  
```  
  
 <span data-ttu-id="97bb4-105">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="97bb4-105">This is the result:</span></span>  
  
```  
<Schema name="Schema1" xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes">  
  <ElementType name="row" content="empty" model="closed">  
    <AttributeType name="ProductModelID" dt:type="i4" />  
    <AttributeType name="Name" dt:type="string" />  
    <attribute type="ProductModelID" />  
    <attribute type="Name" />  
  </ElementType>  
</Schema>  
<row xmlns="x-schema:#Schema1" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="x-schema:#Schema1" ProductModelID="119" Name="Bike Wash" />  
```  
  
> [!NOTE]
>  <span data-ttu-id="97bb4-106"><`Schema`> se declara como un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="97bb4-106">The <`Schema`> is declared as a namespace.</span></span> <span data-ttu-id="97bb4-107">Para evitar conflictos de espacio de nombres al solicitar varios esquemas de datos XML en distintas consultas FOR XML, el identificador del espacio de nombres ( `Schema1` en este ejemplo) cambia en cada ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="97bb4-107">To avoid namespace collisions when multiple XML-Data schemas are requested in different FOR XML queries, the namespace identifier, `Schema1` in this example, changes with every query execution.</span></span> <span data-ttu-id="97bb4-108">El identificador de espacio de nombres se compone de **Schema_n_** donde **_n_** es un entero.</span><span class="sxs-lookup"><span data-stu-id="97bb4-108">The namespace identifier is made up of **Schema_n_** where **_n_** is an integer.</span></span>  
  
 <span data-ttu-id="97bb4-109">Al especificar la opción `XMLSCHEMA` , se puede solicitar el esquema XSD del resultado.</span><span class="sxs-lookup"><span data-stu-id="97bb4-109">By specifying the `XMLSCHEMA` option, you can request the XSD schema for the result.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLSCHEMA  
GO  
```  
  
 <span data-ttu-id="97bb4-110">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="97bb4-110">This is the result:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="row">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="119" Name="Bike Wash" />  
  
```  
  
 <span data-ttu-id="97bb4-111">Se puede especificar el URI del espacio de nombres de destino como argumento opcional de XMLSCHEMA en FOR XML.</span><span class="sxs-lookup"><span data-stu-id="97bb4-111">You can specify the target namespace URI as an optional argument to XMLSCHEMA in FOR XML.</span></span> <span data-ttu-id="97bb4-112">De esta manera, se devuelve en el esquema el espacio de nombres de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="97bb4-112">This returns the specified target namespace in the schema.</span></span> <span data-ttu-id="97bb4-113">Este espacio de nombres de destino es el mismo cada vez que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="97bb4-113">This target namespace remains the same every time you execute the query.</span></span> <span data-ttu-id="97bb4-114">Por ejemplo, en la siguiente versión modificada de la consulta anterior se incluye como argumento el URI del espacio de nombres, `'urn:example.com'`.</span><span class="sxs-lookup"><span data-stu-id="97bb4-114">For example, the following modified version of the previous query includes the namespace URI, `'urn:example.com'`, as an argument.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLSCHEMA ('urn:example.com')  
GO  
```  
  
 <span data-ttu-id="97bb4-115">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="97bb4-115">This is the result:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:example.com" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="row">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<row xmlns="urn:example.com" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="urn:example.com" ProductModelID="119" Name="Bike Wash" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="97bb4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97bb4-116">See Also</span></span>  
 [<span data-ttu-id="97bb4-117">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="97bb4-117">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
