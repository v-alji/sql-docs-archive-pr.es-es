---
title: 'SQL: Overflow-Field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: f005182b-6151-432d-ab22-3bc025742cd3
author: rothja
ms.author: jroth
ms.openlocfilehash: ea52eb642964844a03304d082632c2b7157f723b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674752"
---
# <a name="sqloverflow-field-sqlxml-40"></a><span data-ttu-id="d7cc6-102">sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d7cc6-102">sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="d7cc6-103">En un esquema, puede identificar una columna como una columna de desbordamiento para que reciba todos los datos no consumidos del documento XML.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-103">In a schema, you can identify a column as an overflow column to receive all unconsumed data from the XML document.</span></span> <span data-ttu-id="d7cc6-104">Esta columna se especifica en el esquema utilizando la anotación `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-104">This column is specified in the schema by using the `sql:overflow-field` annotation.</span></span> <span data-ttu-id="d7cc6-105">Es posible tener varias columnas de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-105">It is possible to have multiple overflow columns.</span></span>  
  
 <span data-ttu-id="d7cc6-106">Siempre que un nodo XML (elemento o atributo) para el que hay una anotación `sql:overflow-field` definida entra en el ámbito, la columna de desbordamiento se activa y recibe los datos no consumidos.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-106">Whenever an XML node (element or attribute) for which there is a `sql:overflow-field` annotation defined enters into scope, the overflow column is activated and receives unconsumed data.</span></span> <span data-ttu-id="d7cc6-107">Cuando el nodo sale del ámbito, la columna de desbordamiento deja de estar activa y Carga masiva XML activa el campo de desbordamiento anterior (si existe).</span><span class="sxs-lookup"><span data-stu-id="d7cc6-107">When the node goes out of scope, the overflow column is no longer active and XML Bulk Load makes the previous overflow field (if any) active.</span></span>  
  
 <span data-ttu-id="d7cc6-108">Al almacenar datos en la columna de desbordamiento, Carga masiva XML también almacena las etiquetas de cierre y apertura del elemento primario para el que se define `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-108">As it stores data in the overflow column, XML Bulk Load also stores the opening and closing tags of the parent element for which `sql:overflow-field` is defined.</span></span>  
  
 <span data-ttu-id="d7cc6-109">Por ejemplo, en el esquema siguiente se describen los **\<Customers>** **\<CustOrder>** elementos y.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-109">For example, the following schema describes the **\<Customers>** and **\<CustOrder>** elements.</span></span> <span data-ttu-id="d7cc6-110">Cada uno de estos elementos identifica una columna de desbordamiento:</span><span class="sxs-lookup"><span data-stu-id="d7cc6-110">Each of these elements identifies an overflow column:</span></span>  
  
```  
<?xml version="1.0" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
 <xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
        parent="Cust"  
        parent-key="CustomerID"  
        child="CustOrder"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
 </xsd:annotation>  
 <xsd:element name="ROOT" sql:is-constant="1">  
  <xsd:complexType>  
    <xsd:sequence>   
      <xsd:element name="Customers"   
                   sql:relation="Cust"  
                   sql:overflow-field="OverflowColumn">  
        <xsd:complexType>  
             <xsd:sequence>   
             <xsd:element name="CustomerID" type="xsd:integer"/>  
             <xsd:element name="CompanyName"  type="xsd:string"/>  
             <xsd:element name="City" type="xsd:string"/>  
             <xsd:element name="Order"  
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder"  
                          sql:overflow-field="OverflowColumn">  
               <xsd:complexType>  
                 <xsd:attribute name="OrderID"/>  
                 <xsd:attribute name="CustomerID"/>  
               </xsd:complexType>  
             </xsd:element>  
          </xsd:sequence>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d7cc6-111">En el esquema, el **\<Customer>** elemento se asigna a la tabla Cust y el **\<Order>** elemento se asigna a la tabla CustOrder.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-111">In the schema, the **\<Customer>** element maps to the Cust table and the **\<Order>** element maps to the CustOrder table.</span></span>  
  
 <span data-ttu-id="d7cc6-112">Los **\<Customer>** elementos y **\<Order>** identifican una columna de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-112">Both the **\<Customer>** and **\<Order>** elements identify an overflow column.</span></span> <span data-ttu-id="d7cc6-113">Por lo tanto, la carga masiva XML guarda todos los elementos secundarios y atributos no consumidos del **\<Customer>** elemento en la columna Overflow de la tabla Cust, y todos los elementos secundarios y atributos no consumidos del **\<Order>** elemento en la columna Overflow de la tabla CustOrder.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-113">Thus, XML Bulk Load saves all the unconsumed child elements and attributes of the **\<Customer>** element in the overflow column of the Cust table, and all the unconsumed child elements and attributes of the **\<Order>** element in the overflow column of the CustOrder table.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="d7cc6-114">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="d7cc6-114">To test a working sample</span></span>  
  
1.  <span data-ttu-id="d7cc6-115">Guarde el esquema que se proporciona en este ejemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="d7cc6-115">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="d7cc6-116">Cree estas tablas:</span><span class="sxs-lookup"><span data-stu-id="d7cc6-116">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
              CustomerID     int         PRIMARY KEY,  
              CompanyName    varchar(20) NOT NULL,  
              City           varchar(20) DEFAULT 'Seattle',  
              OverflowColumn nvarchar(200))  
    GO  
    CREATE TABLE CustOrder (  
              OrderID        int         PRIMARY KEY,  
              CustomerID     int         FOREIGN KEY REFERENCES  
                                              Cust(CustomerID),  
              OverflowColumn nvarchar(200))  
    GO  
    ```  
  
3.  <span data-ttu-id="d7cc6-117">Guarde los siguientes datos XML de ejemplo como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="d7cc6-117">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
          <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
     </Customers>  
     <Customers>  
       <CustomerID>1112</CustomerID>  
       <CompanyName>Toms Spezialitten</CompanyName>  
       <City><![CDATA[LA]]> </City>  
       <xyz><address>111 Maple, Seattle</address></xyz>     
       <Order OrderID="3" />  
     </Customers>  
       <Customers>  
       <CustomerID>1113</CustomerID>  
       <CompanyName>Victuailles en stock</CompanyName>  
       <Order OrderID="4" />  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="d7cc6-118">Para ejecutar Carga masiva XML, guarde y ejecute este ejemplo de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) como Sample.vbs:</span><span class="sxs-lookup"><span data-stu-id="d7cc6-118">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
