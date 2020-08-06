---
title: Ejemplos de carga masiva XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- ConnectionCommand property
- XMLFragment property
- relationship chains [SQLXML]
- multiple table bulk loading
- examples [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:datatype
- transaction mode [SQLXML]
- CheckConstraints property
- sql:overflow-field
- XML Bulk Load [SQLXML], examples
- TempFilePath property
- datatype annotation
- Transaction property
- KeepIdentity property
- Execute method
- streaming XML data
- xml data type [SQL Server], SQLXML
- bulk load [SQLXML], examples
ms.assetid: 970e4553-b41d-4a12-ad50-0ee65d1f305d
author: rothja
ms.author: jroth
ms.openlocfilehash: c7eaec77ef068efd28c4da65833afa5047b222f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744022"
---
# <a name="xml-bulk-load-examples-sqlxml-40"></a><span data-ttu-id="c2bca-102">Ejemplos de carga masiva XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c2bca-102">XML Bulk Load Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="c2bca-103">En los ejemplos siguientes se muestra la funcionalidad de la carga masiva XML en Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2bca-103">The following examples illustrate the XML Bulk Load functionality in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c2bca-104">En cada ejemplo se proporcionan un esquema XSD y su esquema XDR equivalente.</span><span class="sxs-lookup"><span data-stu-id="c2bca-104">Each example provides an XSD schema and its equivalent XDR schema.</span></span>  
  
## <a name="bulk-loader-script-validateandbulkloadvbs"></a><span data-ttu-id="c2bca-105">Script de carga masiva (ValidateAndBulkload.vbs)</span><span class="sxs-lookup"><span data-stu-id="c2bca-105">Bulk Loader Script (ValidateAndBulkload.vbs)</span></span>  
 <span data-ttu-id="c2bca-106">El script siguiente, escrito en el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), carga un documento XML en el DOM XML; lo valida con respecto a un esquema; y, si el documento es válido, ejecuta una carga masiva XML para cargar el XML en una [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabla.</span><span class="sxs-lookup"><span data-stu-id="c2bca-106">The following script, written in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), loads an XML document into the XML DOM; validates it against a schema; and, if the document is valid, executes an XML bulk load to load the XML into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c2bca-107">Este script puede usarse en cada uno de los ejemplos individuales que hacen referencia a él más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="c2bca-107">This script can be used with each of the individual examples that refer to it later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2bca-108">La carga masiva XML no genera ninguna advertencia o error si no se carga contenido del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c2bca-108">XML Bulk Load does not throw a warning or an error if no content is uploaded from the data file.</span></span> <span data-ttu-id="c2bca-109">Por lo tanto, es recomendable validar el archivo de datos XML antes de ejecutar cualquier operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="c2bca-109">Therefore, it is a good practice to validate your XML data file prior to executing a bulk load operation.</span></span>  
  
```  
Dim FileValid  
  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
'Validate the data file prior to bulkload  
Dim sOutput   
sOutput = ValidateFile("SampleXMLData.xml", "", "SampleSchema.xml")  
WScript.Echo sOutput  
  
If FileValid Then  
   ' Check constraints and initiate transaction (if needed)  
   ' objBL.CheckConstraints = True  
   ' objBL.Transaction=True  
  'Execute XML bulkload using file.  
  objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
  set objBL=Nothing  
End If  
  
Function ValidateFile(strXmlFile,strUrn,strXsdFile)  
  
   ' Create a schema cache and add SampleSchema.xml to it.  
   Dim xs, fso, sAppPath  
   Set fso = CreateObject("Scripting.FileSystemObject")   
   Set xs = CreateObject("MSXML2.XMLSchemaCache.6.0")  
   sAppPath = fso.GetFolder(".")   
   xs.Add strUrn, sAppPath & "\" & strXsdFile  
  
   ' Create an XML DOMDocument object.  
   Dim xd   
   Set xd = CreateObject("MSXML2.DOMDocument.6.0")  
  
   ' Assign the schema cache to the DOM document.  
   ' schemas collection.  
   Set xd.schemas = xs  
  
   ' Load XML document as DOM document.  
   xd.async = False  
   xd.Load sAppPath & "\" & strXmlFile  
  
   ' Return validation results in message to the user.  
   If xd.parseError.errorCode <> 0 Then  
        ValidateFile = "Validation failed on " & _  
             strXmlFile & vbCrLf & _  
             "=======" & vbCrLf & _  
             "Reason: " & xd.parseError.reason & _  
             vbCrLf & "Source: " & _  
             xd.parseError.srcText & _  
             vbCrLf & "Line: " & _  
             xd.parseError.Line & vbCrLf  
             FileValid = False  
    Else  
        ValidateFile = "Validation succeeded for " & _  
             strXmlFile & vbCrLf & _  
             "========" & _  
             vbCrLf & "Contents to be bulkloaded" & vbCrLf  
             FileValid = True  
    End If  
End Function  
```  
  
## <a name="a-bulk-loading-xml-in-a-table"></a><span data-ttu-id="c2bca-110">A.</span><span class="sxs-lookup"><span data-stu-id="c2bca-110">A.</span></span> <span data-ttu-id="c2bca-111">Cargar XML de forma masiva en una tabla</span><span class="sxs-lookup"><span data-stu-id="c2bca-111">Bulk loading XML in a table</span></span>  
 <span data-ttu-id="c2bca-112">En este ejemplo se establece una conexión con la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que se especifica en la propiedad ConnectionString (mi Server).</span><span class="sxs-lookup"><span data-stu-id="c2bca-112">This example establishes a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is specified in the ConnectionString property (MyServer).</span></span> <span data-ttu-id="c2bca-113">En el ejemplo también se especifica la propiedad ErrorLogFile.</span><span class="sxs-lookup"><span data-stu-id="c2bca-113">The example also specifies the ErrorLogFile property.</span></span> <span data-ttu-id="c2bca-114">Por lo tanto, la salida de error se guarda en el archivo especificado ("C:\error.log"), aunque es posible cambiar esta ubicación por otra distinta.</span><span class="sxs-lookup"><span data-stu-id="c2bca-114">Therefore, the error output is saved in the specified file ("C:\error.log"), which you might also decide to change to a different location.</span></span> <span data-ttu-id="c2bca-115">Observe también que el método Execute tiene como parámetros el archivo de esquema de asignación (SampleSchema.xml) y el archivo de datos XML (SampleXMLData.xml).</span><span class="sxs-lookup"><span data-stu-id="c2bca-115">Notice also that the Execute method has as its parameters both the mapping schema file (SampleSchema.xml) and the XML data file (SampleXMLData.xml).</span></span> <span data-ttu-id="c2bca-116">Cuando se ejecuta la carga masiva, la tabla Cust que ha creado en la base de datos **tempdb** contendrá nuevos registros basados en el contenido del archivo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="c2bca-116">When the bulk load executes, the Cust table you have created in **tempdb** database will contain new records based upon the contents of the XML data file.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="c2bca-117">Para probar una carga masiva del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2bca-117">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="c2bca-118">Cree esta tabla:</span><span class="sxs-lookup"><span data-stu-id="c2bca-118">Create this table:</span></span>  
  
    ```  
    CREATE TABLE Cust(CustomerID  int PRIMARY KEY,  
                      CompanyName varchar(20),  
                      City        varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="c2bca-119">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-119">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-120">En este archivo, agregue el siguiente esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="c2bca-120">To this file, add the following XSD schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
       <xsd:element name="ROOT" sql:is-constant="1" >  
         <xsd:complexType>  
           <xsd:sequence>  
             <xsd:element name="Customers" sql:relation="Cust" maxOccurs="unbounded">  
               <xsd:complexType>  
                 <xsd:sequence>  
                   <xsd:element name="CustomerID"  type="xsd:integer" />  
                   <xsd:element name="CompanyName" type="xsd:string" />  
                   <xsd:element name="City"        type="xsd:string" />  
                 </xsd:sequence>  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
          </xsd:complexType>  
         </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="c2bca-121">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-121">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-122">En este archivo, agregue el siguiente documento XML:</span><span class="sxs-lookup"><span data-stu-id="c2bca-122">To this file, add the following XML document:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Sean Chai</CompanyName>  
        <City>New York</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Tom Johnston</CompanyName>  
         <City>Los Angeles</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Institute of Art</CompanyName>  
        <City>Chicago</City>  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="c2bca-123">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-123">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-124">En este archivo, agregue el código VBScript proporcionado anteriormente al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="c2bca-124">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="c2bca-125">Modifique la cadena de conexión para especificar el nombre de servidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-125">Modify the connection string to provide the appropriate server name.</span></span> <span data-ttu-id="c2bca-126">Especifique la ruta de acceso adecuada para los archivos que se especifican como parámetros para el método Execute.</span><span class="sxs-lookup"><span data-stu-id="c2bca-126">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="c2bca-127">Ejecute el código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-127">Execute the VBScript code.</span></span> <span data-ttu-id="c2bca-128">La carga masiva XML carga el XML en la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="c2bca-128">XML Bulk Load loads the XML into the Cust table.</span></span>  
  
 <span data-ttu-id="c2bca-129">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-129">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers"  sql:relation="Cust" >  
      <element type="CustomerID"  sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City"        sql:field="City" />  
  
   </ElementType>  
</Schema>  
```  
  
## <a name="b-bulk-loading-xml-data-in-multiple-tables"></a><span data-ttu-id="c2bca-130">B.</span><span class="sxs-lookup"><span data-stu-id="c2bca-130">B.</span></span> <span data-ttu-id="c2bca-131">Cargar datos XML de forma masiva en varias tablas</span><span class="sxs-lookup"><span data-stu-id="c2bca-131">Bulk loading XML data in multiple tables</span></span>  
 <span data-ttu-id="c2bca-132">En este ejemplo, el documento XML está compuesto de **\<Customer>** los **\<Order>** elementos y.</span><span class="sxs-lookup"><span data-stu-id="c2bca-132">In this example, the XML document consists of the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Sean Chai</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Tom Johnston</CompanyName>  
     <City>LA</City>    
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Institute of Art</CompanyName>  
    <Order OrderID="4" />  
  </Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="c2bca-133">En este ejemplo se cargan de forma masiva los datos XML en dos tablas, **Cust** y **CustOrder**:</span><span class="sxs-lookup"><span data-stu-id="c2bca-133">This example bulk loads the XML data into two tables, **Cust** and **CustOrder**:</span></span>  
  
```  
Cust(CustomerID, CompanyName, City)  
CustOrder(OrderID, CustomerID)  
```  
  
 <span data-ttu-id="c2bca-134">El esquema XSD siguiente define la vista XML de estas tablas.</span><span class="sxs-lookup"><span data-stu-id="c2bca-134">The following XSD schema defines the XML view of these tables.</span></span> <span data-ttu-id="c2bca-135">El esquema especifica la relación primario-secundario entre los **\<Customer>** **\<Order>** elementos y.</span><span class="sxs-lookup"><span data-stu-id="c2bca-135">The schema specifies the parent-child relationship between the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
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
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Customers" sql:relation="Cust" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="CustomerID"  type="xsd:integer" />  
              <xsd:element name="CompanyName" type="xsd:string" />  
              <xsd:element name="City"        type="xsd:string" />  
              <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
                <xsd:complexType>  
                  <xsd:attribute name="OrderID" type="xsd:integer" />  
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
  
 <span data-ttu-id="c2bca-136">La carga masiva XML usa la relación de clave principal y clave externa especificada anteriormente entre los **\<Cust>** **\<CustOrder>** elementos y para cargar de forma masiva los datos en ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="c2bca-136">XML Bulk Load uses the primary key/foreign key relationship specified above between the **\<Cust>** and **\<CustOrder>** elements to bulk load the data into both tables.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="c2bca-137">Para probar una carga masiva del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2bca-137">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="c2bca-138">Cree dos tablas en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="c2bca-138">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
           CustomerID  int PRIMARY KEY,  
           CompanyName varchar(20),  
           City        varchar(20));  
    CREATE TABLE CustOrder(        OrderID     int PRIMARY KEY,   
            CustomerID int FOREIGN KEY REFERENCES Cust(CustomerID));  
    ```  
  
2.  <span data-ttu-id="c2bca-139">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-139">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-140">Agregue al archivo el esquema XSD que se proporciona en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-140">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="c2bca-141">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-141">Create a file in your preferred text or XML editor, and save it as SampleData.xml.</span></span> <span data-ttu-id="c2bca-142">Agregue al archivo el documento XML proporcionado anteriormente en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-142">Add the XML document that was provided earlier in this example to the file.</span></span>  
  
4.  <span data-ttu-id="c2bca-143">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-143">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-144">En este archivo, agregue el código VBScript proporcionado anteriormente al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="c2bca-144">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="c2bca-145">Modifique la cadena de conexión para especificar el nombre de servidor y de base de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-145">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="c2bca-146">Especifique la ruta de acceso adecuada para los archivos que se especifican como parámetros para el método Execute.</span><span class="sxs-lookup"><span data-stu-id="c2bca-146">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="c2bca-147">Ejecute el código VBScript anterior.</span><span class="sxs-lookup"><span data-stu-id="c2bca-147">Execute the VBScript code above.</span></span> <span data-ttu-id="c2bca-148">La carga masiva XML carga el documento XML en las tablas Cust y CustOrder.</span><span class="sxs-lookup"><span data-stu-id="c2bca-148">XML Bulk Load loads the XML document into the Cust and CustOrder tables.</span></span>  
  
 <span data-ttu-id="c2bca-149">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-149">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
<sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="c-using-chain-relationships-in-the-schema-to-bulk-load-xml"></a><span data-ttu-id="c2bca-150">C.</span><span class="sxs-lookup"><span data-stu-id="c2bca-150">C.</span></span> <span data-ttu-id="c2bca-151">Usar las relaciones de cadena del esquema para cargar XML de forma masiva</span><span class="sxs-lookup"><span data-stu-id="c2bca-151">Using chain relationships in the schema to bulk load XML</span></span>  
 <span data-ttu-id="c2bca-152">En este ejemplo se muestra la forma en que la carga masiva XML usa la relación M:N especificada en el esquema de asignación para cargar datos en una tabla que representa una relación M:N.</span><span class="sxs-lookup"><span data-stu-id="c2bca-152">This example illustrates how the M:N relationship that is specified in the mapping schema is used by XML Bulk Load to load data in a table that represents an M:N relationship.</span></span>  
  
 <span data-ttu-id="c2bca-153">Por ejemplo, fíjese en este esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="c2bca-153">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Ord"  
          parent-key="OrderID"  
          child="OrderDetail"  
          child-key="OrderID" />  
  
    <sql:relationship name="ODProduct"  
          parent="OrderDetail"  
          parent-key="ProductID"  
          child="Product"  
          child-key="ProductID"   
          inverse="true"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Ord"   
                     sql:key-fields="OrderID" >  
          <xsd:complexType>  
            <xsd:sequence>  
             <xsd:element name="Product"  
                          sql:relation="Product"   
                          sql:key-fields="ProductID"  
                          sql:relationship="OrderOD ODProduct">  
               <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
           <xsd:attribute name="OrderID"   type="xsd:integer" />   
           <xsd:attribute name="CustomerID"   type="xsd:string" />  
         </xsd:complexType>  
       </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c2bca-154">El esquema especifica un **\<Order>** elemento con un **\<Product>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="c2bca-154">The schema specifies an **\<Order>** element with a **\<Product>** child element.</span></span> <span data-ttu-id="c2bca-155">El **\<Order>** elemento se asigna a la tabla Ord y el **\<Product>** elemento se asigna a la tabla Product de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c2bca-155">The **\<Order>** element maps to Ord table and the **\<Product>** element maps to the Product table in the database.</span></span> <span data-ttu-id="c2bca-156">La relación de cadena especificada en el **\<Product>** elemento identifica una relación M:N representada por la tabla OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="c2bca-156">The chain relationship specified on the **\<Product>** element identifies a M:N relationship represented by the OrderDetail table.</span></span> <span data-ttu-id="c2bca-157">(Un pedido puede incluir muchos productos y un producto puede estar incluido en muchos pedidos.)</span><span class="sxs-lookup"><span data-stu-id="c2bca-157">(An order can include many products, and a product can be included in many orders.)</span></span>  
  
 <span data-ttu-id="c2bca-158">Al cargar un documento XML de forma masiva con este esquema, los registros se agregan a las tablas Ord, Product y OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="c2bca-158">When you are bulk loading an XML document with this schema, records are added to the Ord, Product, and OrderDetail tables.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-159">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-159">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-160">Cree tres tablas:</span><span class="sxs-lookup"><span data-stu-id="c2bca-160">Create three tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="c2bca-161">Guarde el esquema proporcionado anteriormente en este ejemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-161">Save the schema that is provided above in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="c2bca-162">Guarde los siguientes datos XML de ejemplo como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="c2bca-162">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="1" CustomerID="ALFKI">  
        <Product ProductID="1" ProductName="Chai" />  
        <Product ProductID="2" ProductName="Chang" />  
      </Order>  
      <Order OrderID="2" CustomerID="ANATR">  
        <Product ProductID="3" ProductName="Aniseed Syrup" />  
        <Product ProductID="4" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="c2bca-163">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-163">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-164">En este archivo, agregue el código VBScript proporcionado anteriormente al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="c2bca-164">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="c2bca-165">Modifique la cadena de conexión para especificar el nombre de servidor y de base de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-165">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="c2bca-166">Para este ejemplo, quite los comentarios de las siguientes líneas del código fuente.</span><span class="sxs-lookup"><span data-stu-id="c2bca-166">Uncomment the following lines from the source code for this example.</span></span>  
  
    ```  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    ```  
  
5.  <span data-ttu-id="c2bca-167">Ejecute el código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-167">Execute the VBScript code.</span></span> <span data-ttu-id="c2bca-168">La carga masiva XML carga el documento XML en las tablas Ord y Product.</span><span class="sxs-lookup"><span data-stu-id="c2bca-168">XML Bulk Load loads the XML document into the Ord and Product tables.</span></span>  
  
## <a name="d-bulk-loading-in-identity-type-columns"></a><span data-ttu-id="c2bca-169">D.</span><span class="sxs-lookup"><span data-stu-id="c2bca-169">D.</span></span> <span data-ttu-id="c2bca-170">Cargar datos de forma masiva en columnas de tipo Identity</span><span class="sxs-lookup"><span data-stu-id="c2bca-170">Bulk loading in identity type columns</span></span>  
 <span data-ttu-id="c2bca-171">En este ejemplo se muestra la forma en que la carga masiva administra las columnas de tipo Identity.</span><span class="sxs-lookup"><span data-stu-id="c2bca-171">This example illustrates how bulk load handles identity type columns.</span></span> <span data-ttu-id="c2bca-172">En el ejemplo, los datos se cargan de forma masiva en tres tablas (Ord, Product y OrderDetail).</span><span class="sxs-lookup"><span data-stu-id="c2bca-172">In the example, data is bulk loaded into three tables (Ord, Product, and OrderDetail).</span></span>  
  
 <span data-ttu-id="c2bca-173">En estas tablas:</span><span class="sxs-lookup"><span data-stu-id="c2bca-173">In these tables:</span></span>  
  
-   <span data-ttu-id="c2bca-174">La columna OrderID de la tabla Ord es una columna de tipo Identity</span><span class="sxs-lookup"><span data-stu-id="c2bca-174">OrderID in the Ord table is an identity type column</span></span>  
  
-   <span data-ttu-id="c2bca-175">La columna ProductID de la tabla Product es una columna de tipo Identity.</span><span class="sxs-lookup"><span data-stu-id="c2bca-175">ProductID in the Product table is an identity type column.</span></span>  
  
-   <span data-ttu-id="c2bca-176">Las columnas OrderID y ProductID de OrderDetail son columnas de clave externa que hacen referencia a las columnas de clave principal correspondientes de las tablas Ord y Product.</span><span class="sxs-lookup"><span data-stu-id="c2bca-176">OrderID and ProductID columns in the OrderDetail are foreign key columns referring to corresponding primary key columns in the Ord and Product tables.</span></span>  
  
 <span data-ttu-id="c2bca-177">Los esquemas de tabla de este ejemplo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2bca-177">The following are the table schemas for this example:</span></span>  
  
```  
Ord (OrderID, CustomerID)  
Product (ProductID, ProductName)  
OrderDetail (OrderID, ProductID)  
```  
  
 <span data-ttu-id="c2bca-178">En este ejemplo de carga masiva XML, la propiedad KeepIdentity del modelo de objetos de carga masiva está establecida en false.</span><span class="sxs-lookup"><span data-stu-id="c2bca-178">In this example of XML Bulk Load, the KeepIdentity property of the BulkLoad object model is set to false.</span></span> <span data-ttu-id="c2bca-179">Por lo tanto, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] genera valores de identidad para las columnas ProductID y OrderID de las tablas Product y Ord, respectivamente (se omiten los valores proporcionados en los documentos que van a cargarse de forma masiva).</span><span class="sxs-lookup"><span data-stu-id="c2bca-179">Therefore, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generates identity values for the ProductID and OrderID columns in the Product and Ord tables, respectively (any values provided in the documents to be bulk loaded are ignored).</span></span>  
  
 <span data-ttu-id="c2bca-180">En este caso, la carga masiva XML identifica la relación de clave principal y clave externa entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="c2bca-180">In this case, XML Bulk Load identifies the primary key/foreign key relationship among tables.</span></span> <span data-ttu-id="c2bca-181">En primer lugar, la carga masiva inserta los registros en las tablas con la clave principal y, a continuación, propaga el valor de identidad generado por [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a las tablas con columnas de clave externa.</span><span class="sxs-lookup"><span data-stu-id="c2bca-181">Bulk Load first inserts records in the tables with the primary key, then propagates the identity value generated by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the tables with foreign key columns.</span></span> <span data-ttu-id="c2bca-182">En el siguiente ejemplo, la carga masiva XML inserta datos en las tablas en el orden que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c2bca-182">In the following example, XML Bulk Load inserts data in tables in this order:</span></span>  
  
1.  <span data-ttu-id="c2bca-183">Producto</span><span class="sxs-lookup"><span data-stu-id="c2bca-183">Product</span></span>  
  
2.  <span data-ttu-id="c2bca-184">Ord</span><span class="sxs-lookup"><span data-stu-id="c2bca-184">Ord</span></span>  
  
3.  <span data-ttu-id="c2bca-185">OrderDetail</span><span class="sxs-lookup"><span data-stu-id="c2bca-185">OrderDetail</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c2bca-186">Para propagar los valores de identidad generados en las tablas Products y Orders, la lógica de procesamiento exige que la carga masiva XML realice un seguimiento de estos valores para insertarlos posteriormente en la tabla OrderDetails.</span><span class="sxs-lookup"><span data-stu-id="c2bca-186">In order to propagate identity values generated in the Products and Orders tables, the processing logic requires XML Bulk Load to keep track of these values for later insertion into the OrderDetails table.</span></span> <span data-ttu-id="c2bca-187">Para ello, la carga masiva XML crea tablas intermedias, rellena de datos estas tablas y, a continuación, quita estos datos.</span><span class="sxs-lookup"><span data-stu-id="c2bca-187">To do that, XML Bulk Load creates intermediate tables, populates the data in these tables, and later removes them.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-188">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-188">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-189">Cree estas tablas:</span><span class="sxs-lookup"><span data-stu-id="c2bca-189">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="c2bca-190">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-190">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-191">Agregue este esquema XSD al archivo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-191">Add this XSD schema to this file.</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
       <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
       </xsd:appinfo>  
     </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="c2bca-192">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-192">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-193">Agregue el siguiente documento XML.</span><span class="sxs-lookup"><span data-stu-id="c2bca-193">Add the following XML document.</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="c2bca-194">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-194">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-195">En este archivo, agregue el siguiente código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-195">To this file, add the following VBScript code.</span></span> <span data-ttu-id="c2bca-196">Modifique la cadena de conexión para especificar el nombre de servidor y de base de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-196">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="c2bca-197">Especifique la ruta de acceso adecuada para los archivos que actúan como parámetros para el `Execute` método.</span><span class="sxs-lookup"><span data-stu-id="c2bca-197">Specify the appropriate path for the files that serve as parameters to the `Execute` method.</span></span>  
  
    ```  
    Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "C:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction = False  
    objBL.KeepIdentity = False  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    Set objBL = Nothing  
    MsgBox "Done."  
    ```  
  
5.  <span data-ttu-id="c2bca-198">Ejecute el código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-198">Execute the VBScript code.</span></span> <span data-ttu-id="c2bca-199">La carga masiva XML cargará los datos en las tablas pertinentes.</span><span class="sxs-lookup"><span data-stu-id="c2bca-199">The XML Bulk Load will load the data into the appropriate tables.</span></span>  
  
## <a name="e-generating-table-schemas-before-bulk-loading"></a><span data-ttu-id="c2bca-200">E.</span><span class="sxs-lookup"><span data-stu-id="c2bca-200">E.</span></span> <span data-ttu-id="c2bca-201">Generar esquemas de tabla antes de la carga masiva</span><span class="sxs-lookup"><span data-stu-id="c2bca-201">Generating table schemas before bulk loading</span></span>  
 <span data-ttu-id="c2bca-202">La carga masiva XML puede generar las tablas si no existen antes de la carga masiva.</span><span class="sxs-lookup"><span data-stu-id="c2bca-202">XML Bulk Load can optionally generate the tables if they do not exist before bulk loading.</span></span> <span data-ttu-id="c2bca-203">El establecimiento de la propiedad SchemaGen del objeto SQLXMLBulkLoad en TRUE hace esto.</span><span class="sxs-lookup"><span data-stu-id="c2bca-203">Setting the SchemaGen property of the SQLXMLBulkLoad object to TRUE does this.</span></span> <span data-ttu-id="c2bca-204">Opcionalmente, también puede solicitar la carga masiva XML para quitar las tablas existentes y volver a crearlas estableciendo la propiedad SGDropTables en TRUE.</span><span class="sxs-lookup"><span data-stu-id="c2bca-204">You can also optionally request XML Bulk Load to drop any existing tables and re-create them by setting the SGDropTables property to TRUE.</span></span> <span data-ttu-id="c2bca-205">En el siguiente ejemplo de VBScript se muestra el uso de estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="c2bca-205">The following VBScript example illustrates the use of these properties.</span></span>  
  
 <span data-ttu-id="c2bca-206">Asimismo, este ejemplo establece dos propiedades adicionales en TRUE:</span><span class="sxs-lookup"><span data-stu-id="c2bca-206">Also, this example sets two additional properties to TRUE:</span></span>  
  
-   <span data-ttu-id="c2bca-207">CheckConstraints.</span><span class="sxs-lookup"><span data-stu-id="c2bca-207">CheckConstraints.</span></span> <span data-ttu-id="c2bca-208">Estableciendo esta propiedad en TRUE se asegurará de que los datos que se inserten en las tablas no infrinjan ninguna restricción especificada en las tablas (en este caso, las restricciones PRIMARY KEY y FOREIGN KEY especificadas entre las tablas Cust y CustOrder).</span><span class="sxs-lookup"><span data-stu-id="c2bca-208">Setting this property to TRUE ensures that the data being inserted into the tables does not violate any constraints that have been specified on the tables (in this case the PRIMARY KEY/FOREIGN KEY constraints specified between the Cust and CustOrder tables).</span></span> <span data-ttu-id="c2bca-209">Si se infringe alguna restricción, se produce un error en la carga masiva.</span><span class="sxs-lookup"><span data-stu-id="c2bca-209">If there is a constraint violation, the bulk load fails.</span></span>  
  
-   <span data-ttu-id="c2bca-210">XMLFragment.</span><span class="sxs-lookup"><span data-stu-id="c2bca-210">XMLFragment.</span></span> <span data-ttu-id="c2bca-211">Esta propiedad debe establecerse en TRUE porque el documento XML de ejemplo (origen de datos) no contiene ningún elemento único de nivel superior (y, por lo tanto, es un fragmento).</span><span class="sxs-lookup"><span data-stu-id="c2bca-211">This property must be set to TRUE because the sample XML document (data source) contains no single, top-level element (and is thus a fragment).</span></span>  
  
 <span data-ttu-id="c2bca-212">Éste es el código VBScript:</span><span class="sxs-lookup"><span data-stu-id="c2bca-212">This is the VBScript code:</span></span>  
  
```  
Dim objBL   
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
objBL.CheckConstraints=true  
objBL.XMLFragment = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-213">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-213">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-214">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-214">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-215">Agregue al archivo el esquema XSD proporcionado en el ejemplo anterior, "Usar las relaciones de cadena del esquema para cargar XML de forma masiva".</span><span class="sxs-lookup"><span data-stu-id="c2bca-215">Add the XSD schema that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span>  
  
2.  <span data-ttu-id="c2bca-216">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-216">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-217">Agregue al archivo el documento XML proporcionado en el ejemplo anterior, "Usar las relaciones de cadena del esquema para cargar XML de forma masiva".</span><span class="sxs-lookup"><span data-stu-id="c2bca-217">Add the XML document that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span> <span data-ttu-id="c2bca-218">Quite el \<ROOT> elemento del documento (para convertirlo en un fragmento).</span><span class="sxs-lookup"><span data-stu-id="c2bca-218">Remove the \<ROOT> element from the document (to make it a fragment).</span></span>  
  
3.  <span data-ttu-id="c2bca-219">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-219">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-220">En este archivo, agregue el código VBScript de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-220">To this file, add the VBScript code in this example.</span></span> <span data-ttu-id="c2bca-221">Modifique la cadena de conexión para especificar el nombre de servidor y de base de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-221">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="c2bca-222">Especifique la ruta de acceso adecuada para los archivos que se especifican como parámetros para el método Execute.</span><span class="sxs-lookup"><span data-stu-id="c2bca-222">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
4.  <span data-ttu-id="c2bca-223">Ejecute el código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-223">Execute the VBScript code.</span></span> <span data-ttu-id="c2bca-224">La carga masiva XML crea las tablas necesarias en función del esquema de asignación proporcionado y carga los datos de forma masiva en el mismo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-224">The XML Bulk Load creates the necessary tables on the basis of the mapping schema that is provided and bulk loads the data in it.</span></span>  
  
## <a name="f-bulk-loading-from-a-stream"></a><span data-ttu-id="c2bca-225">F.</span><span class="sxs-lookup"><span data-stu-id="c2bca-225">F.</span></span> <span data-ttu-id="c2bca-226">Cargar datos de forma masiva desde un flujo</span><span class="sxs-lookup"><span data-stu-id="c2bca-226">Bulk loading from a stream</span></span>  
 <span data-ttu-id="c2bca-227">El método Execute del modelo de objetos de carga masiva XML toma dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="c2bca-227">The Execute method of the XML Bulk Load object model takes two parameters.</span></span> <span data-ttu-id="c2bca-228">El primer parámetro es el archivo de esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="c2bca-228">The first parameter is the mapping schema file.</span></span> <span data-ttu-id="c2bca-229">El segundo, proporciona los datos XML que se cargarán en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c2bca-229">The second parameter provides the XML data that is to be loaded in the database.</span></span> <span data-ttu-id="c2bca-230">Hay dos maneras de pasar los datos XML al método Execute de carga masiva XML:</span><span class="sxs-lookup"><span data-stu-id="c2bca-230">There are two ways to pass the XML data to the Execute method of XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="c2bca-231">Especificar el nombre de archivo como parámetro.</span><span class="sxs-lookup"><span data-stu-id="c2bca-231">Specify the file name as the parameter.</span></span>  
  
-   <span data-ttu-id="c2bca-232">Pasar un flujo que contenga los datos XML.</span><span class="sxs-lookup"><span data-stu-id="c2bca-232">Pass a stream that contains the XML data.</span></span>  
  
 <span data-ttu-id="c2bca-233">Este ejemplo muestra cómo realizar la carga masiva desde un flujo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-233">This example illustrates how to bulk load from a stream.</span></span>  
  
 <span data-ttu-id="c2bca-234">VBScript ejecuta primero una instrucción SELECT para recuperar la información del cliente de la tabla Customers de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="c2bca-234">VBScript first executes a SELECT statement to retrieve customer information from the Customers table in the Northwind database.</span></span> <span data-ttu-id="c2bca-235">Puesto que se ha especificado la cláusula FOR XML (con la opción ELEMENTS) en la instrucción SELECT, la consulta devuelve un documento XML centrado en elementos de este formulario:</span><span class="sxs-lookup"><span data-stu-id="c2bca-235">Because the FOR XML clause is specified (with the ELEMENTS option) in the SELECT statement, the query returns an element-centric XML document of this form:</span></span>  
  
```  
<Customer>  
  <CustomerID>..</CustomerID>  
  <CompanyName>..</CompanyName>  
  <City>..</City>  
</Customer>  
...  
```  
  
 <span data-ttu-id="c2bca-236">A continuación, el script pasa el XML como un flujo al método Execute como su segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="c2bca-236">The script then passes the XML as a stream to the Execute method as its second parameter.</span></span> <span data-ttu-id="c2bca-237">El método Execute carga de forma masiva los datos en la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="c2bca-237">The Execute method bulk loads the data into the Cust table.</span></span>  
  
 <span data-ttu-id="c2bca-238">Dado que este script establece la propiedad SchemaGen en TRUE y la propiedad SGDropTables en TRUE, la carga masiva XML crea la tabla Cust en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="c2bca-238">Because this script sets the SchemaGen property to TRUE and SGDropTables property to TRUE, XML Bulk Load creates the Cust table in the specified database.</span></span> <span data-ttu-id="c2bca-239">(Si la tabla ya existe, quita primero la tabla y, a continuación, vuelve a crearla.)</span><span class="sxs-lookup"><span data-stu-id="c2bca-239">(If the table already exists, it first drops the table and then re-creates it.)</span></span>  
  
 <span data-ttu-id="c2bca-240">Éste es el ejemplo de VBScript:</span><span class="sxs-lookup"><span data-stu-id="c2bca-240">This is the VBScript example:</span></span>  
  
```  
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
Set objCmd = CreateObject("ADODB.Command")  
Set objConn = CreateObject("ADODB.Connection")  
Set objStrmOut = CreateObject ("ADODB.Stream")  
  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile     = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen        = True  
objBL.SGDropTables     = True  
objBL.XMLFragment      = True  
' Open a connection to the instance of SQL Server to get the source data.  
  
objConn.Open "provider=SQLOLEDB;server=(local);database=tempdb;integrated security=SSPI"  
Set objCmd.ActiveConnection = objConn  
objCmd.CommandText = "SELECT CustomerID, CompanyName, City FROM Customers FOR XML AUTO, ELEMENTS"  
  
' Open the return stream and execute the command.  
Const adCRLF = -1  
Const adExecuteStream = 1024  
objStrmOut.Open  
objStrmOut.LineSeparator = adCRLF  
objCmd.Properties("Output Stream").Value = objStrmOut  
objCmd.Execute , , adExecuteStream  
objStrmOut.Position = 0  
  
' Execute bulk load. Read source XML data from the stream.  
objBL.Execute "SampleSchema.xml", objStrmOut  
  
Set objBL = Nothing  
```  
  
 <span data-ttu-id="c2bca-241">El siguiente esquema de asignación XSD proporciona la información necesaria para crear la tabla:</span><span class="sxs-lookup"><span data-stu-id="c2bca-241">The following XSD mapping schema provides the necessary information to create the table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="true" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customers"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="Customers" sql:relation="Cust" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element name="CustomerID"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(5)"/>  
      <xsd:element name="CompanyName"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
      <xsd:element name="City"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c2bca-242">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-242">This is equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
    </ElementType>  
</Schema>  
```  
  
### <a name="opening-a-stream-on-an-existing-file"></a><span data-ttu-id="c2bca-243">Abrir un flujo en un archivo existente</span><span class="sxs-lookup"><span data-stu-id="c2bca-243">Opening a Stream on an Existing File</span></span>  
 <span data-ttu-id="c2bca-244">También puede abrir un flujo en un archivo de datos XML existente y pasar la secuencia como un parámetro al método execute (en lugar de pasar el nombre de archivo como parámetro).</span><span class="sxs-lookup"><span data-stu-id="c2bca-244">You can also open a stream on an existing XML data file and pass the stream as a parameter to the Execute method (instead of passing the file name as the parameter).</span></span>  
  
 <span data-ttu-id="c2bca-245">Éste es un ejemplo de Visual Basic que muestra cómo pasar un flujo como parámetro:</span><span class="sxs-lookup"><span data-stu-id="c2bca-245">This is a Visual Basic example of passing a stream as the parameter:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad  
Dim objStrm As New ADODB.Stream  
Dim objFileSystem As New Scripting.FileSystemObject  
Dim objFile As Scripting.TextStream  
  
MsgBox "Begin BulkLoad..."  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
' Here again a stream is specified that contains the source data   
' (instead of the file name). But this is just an illustration.  
' Usually this is useful if you have an XML data   
' stream that is created by some other means that you want to bulk   
' load. This example starts with an XML text file, so it may not be the   
' best to use a stream (you can specify the file name directly).  
' Here you could have specified the file name itself.   
Set objFile = objFileSystem.OpenTextFile("c:\SampleData.xml")  
objStrm.Open  
objStrm.WriteText objFile.ReadAll  
objStrm.Position = 0  
objBL.Execute "c:\SampleSchema.xml", objStrm  
  
Set objBL = Nothing  
MsgBox "Done."  
End Sub  
```  
  
 <span data-ttu-id="c2bca-246">Para probar la aplicación, use el siguiente documento XML en un archivo (SampleData.xml) y el esquema XSD proporcionado en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c2bca-246">To test the application, use the following XML document in a file (SampleData.xml) and the XSD schema that is provided in this example:</span></span>  
  
 <span data-ttu-id="c2bca-247">Éstos son los datos de origen XML (SampleData.xml):</span><span class="sxs-lookup"><span data-stu-id="c2bca-247">This is the XML source data (SampleData.xml):</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Hanari Carnes</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Toms Spezialitten</CompanyName>  
     <City>LA</City>  
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Victuailles en stock</CompanyName>  
    <Order CustomerID= "4444" OrderID="4" />  
</Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="c2bca-248">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-248">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="g-bulk-loading-in-overflow-columns"></a><span data-ttu-id="c2bca-249">G.</span><span class="sxs-lookup"><span data-stu-id="c2bca-249">G.</span></span> <span data-ttu-id="c2bca-250">Cargar datos de forma masiva en columnas de desbordamiento</span><span class="sxs-lookup"><span data-stu-id="c2bca-250">Bulk loading in overflow columns</span></span>  
 <span data-ttu-id="c2bca-251">Si el esquema de asignación especifica una columna de desbordamiento mediante la anotación `sql:overflow-field`, la carga masiva XML copia todos los datos sin consumir del documento de origen a esta columna.</span><span class="sxs-lookup"><span data-stu-id="c2bca-251">If the mapping schema specifies an overflow column by using the `sql:overflow-field` annotation, XML Bulk Load copies all unconsumed data from the source document into this column.</span></span>  
  
 <span data-ttu-id="c2bca-252">Fíjese en este esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="c2bca-252">Consider this XSD schema:</span></span>  
  
```  
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
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
          <xsd:attribute name="CustomerID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c2bca-253">El esquema identifica una columna de desbordamiento (OverflowColumn) para la tabla Cust.</span><span class="sxs-lookup"><span data-stu-id="c2bca-253">The schema identifies an overflow column (OverflowColumn) for the Cust table.</span></span> <span data-ttu-id="c2bca-254">Como resultado, todos los datos XML no consumidos de cada **\<Customer>** elemento se agregan a esta columna.</span><span class="sxs-lookup"><span data-stu-id="c2bca-254">As a result, all unconsumed XML data for each **\<Customer>** element is added to this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2bca-255">Todos los elementos abstractos (elementos para los que se especifica **abstract = "true"** ) y todos los atributos prohibidos (atributos para los que se especifica **Prohibited = "true"** ) se consideran desbordamiento mediante la carga masiva XML y se agregan a la columna de desbordamiento, si se especifica.</span><span class="sxs-lookup"><span data-stu-id="c2bca-255">All abstract elements (elements for which **abstract="true"** is specified) and all prohibited attributes (attributes for which **prohibited="true"** is specified) are considered overflow by XML Bulk Load and are added to the overflow column, if specified.</span></span> <span data-ttu-id="c2bca-256">(De lo contrario, se omiten.)</span><span class="sxs-lookup"><span data-stu-id="c2bca-256">(Otherwise, they are ignored.)</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-257">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-257">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-258">Cree dos tablas en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="c2bca-258">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle',  
                  OverflowColumn nvarchar(200));  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID    int PRIMARY KEY,  
                  CustomerID int FOREIGN KEY   
                                 REFERENCES Cust(CustomerID));  
    GO  
    ```  
  
2.  <span data-ttu-id="c2bca-259">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-259">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-260">Agregue al archivo el esquema XSD que se proporciona en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-260">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="c2bca-261">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-261">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-262">Agregue al archivo el siguiente documento XML:</span><span class="sxs-lookup"><span data-stu-id="c2bca-262">Add the following XML document to the file:</span></span>  
  
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
         <![CDATA[LA]]>   
        <!-- <xyz><address>111 Maple, Seattle</address></xyz>   -->  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="c2bca-263">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-263">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-264">Agregue a este archivo el siguiente código Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="c2bca-264">To this file, add the following Microsoft Visual Basic Scripting Edition (VBScript) code.</span></span> <span data-ttu-id="c2bca-265">Modifique la cadena de conexión para especificar el nombre de servidor y de base de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-265">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="c2bca-266">Especifique la ruta de acceso adecuada para los archivos que se especifican como parámetros para el método Execute.</span><span class="sxs-lookup"><span data-stu-id="c2bca-266">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="c2bca-267">Ejecute el código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-267">Execute the VBScript code.</span></span>  
  
 <span data-ttu-id="c2bca-268">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-268">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"   
                       sql:overflow-field="OverflowColumn"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="h-specifying-the-file-path-for-temp-files-in-transaction-mode"></a><span data-ttu-id="c2bca-269">H.</span><span class="sxs-lookup"><span data-stu-id="c2bca-269">H.</span></span> <span data-ttu-id="c2bca-270">Especificar la ruta de acceso de los archivos temporales en modo de transacción</span><span class="sxs-lookup"><span data-stu-id="c2bca-270">Specifying the file path for temp files in transaction mode</span></span>  
 <span data-ttu-id="c2bca-271">Cuando se realiza una carga masiva en modo de transacción (es decir, cuando la propiedad de la transacción está establecida en TRUE), también debe establecer la propiedad TempFilePath cuando se cumple alguna de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2bca-271">When you are bulk loading in transaction mode (that is, when the Transaction property is set to TRUE), you also must set the TempFilePath property when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="c2bca-272">La carga masiva se realiza en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="c2bca-272">You are bulk loading to a remote server.</span></span>  
  
-   <span data-ttu-id="c2bca-273">Se desea usar una unidad local o carpeta alternativa (distinta de la ruta de acceso especificada por la variable de entorno TEMP) para almacenar los archivos temporales creados en el modo de transacción.</span><span class="sxs-lookup"><span data-stu-id="c2bca-273">You want to use an alternate local drive or folder (one other than the path that is specified by the TEMP environment variable) to store the temporary files that are created in the transaction mode.</span></span>  
  
 <span data-ttu-id="c2bca-274">Por ejemplo, el siguiente código VBScript carga datos de forma masiva del archivo SampleXMLData.xml a las tablas de base de datos en modo de transacción.</span><span class="sxs-lookup"><span data-stu-id="c2bca-274">For example, the following VBScript code bulk loads data from the SampleXMLData.xml file into the database tables in transaction mode.</span></span> <span data-ttu-id="c2bca-275">La propiedad TempFilePath se especifica para establecer la ruta de acceso de los archivos temporales que se generan en el modo de transacción.</span><span class="sxs-lookup"><span data-stu-id="c2bca-275">The TempFilePath property is specified to set the path for the temporary files that are generated in transaction mode.</span></span>  
  
```  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.Transaction=True  
objBL.TempFilePath="\\Server\MyDir"  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
set objBL=Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c2bca-276">La ruta de acceso de los archivos temporales debe ser una ubicación compartida accesible para la cuenta de servicio de la instancia de destino de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y para la cuenta que está ejecutando la aplicación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="c2bca-276">The temporary file path must be a shared location that is accessible to the service account of the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and to the account that is running the bulk load application.</span></span> <span data-ttu-id="c2bca-277">A menos que esté cargando de forma masiva en un servidor local, la ruta de acceso del archivo temporal debe ser una ruta de acceso UNC (por ejemplo, \\ \nombreservidor\nombrerecursocompartido).</span><span class="sxs-lookup"><span data-stu-id="c2bca-277">Unless you are bulk loading on a local server, the temporary file path must be a UNC path (such as \\\servername\sharename).</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-278">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-278">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-279">Cree esta tabla en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="c2bca-279">Create this table in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (     CustomerID uniqueidentifier,   
          LastName  varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="c2bca-280">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-280">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-281">Agregue al archivo el siguiente esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="c2bca-281">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="c2bca-282">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-282">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-283">Agregue al archivo el siguiente documento XML:</span><span class="sxs-lookup"><span data-stu-id="c2bca-283">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="6F9619FF-8B86-D011-B42D-00C04FC964FF"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="c2bca-284">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-284">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="c2bca-285">En este archivo, agregue el siguiente código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-285">To this file, add the following VBScript code.</span></span> <span data-ttu-id="c2bca-286">Modifique la cadena de conexión para especificar el nombre de servidor y de base de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="c2bca-286">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="c2bca-287">Especifique la ruta de acceso adecuada para los archivos que se especifican como parámetros para el método Execute.</span><span class="sxs-lookup"><span data-stu-id="c2bca-287">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span> <span data-ttu-id="c2bca-288">Especifique también la ruta de acceso adecuada para la propiedad TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="c2bca-288">Also specify the appropriate path for the TempFilePath property.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.TempFilePath="\\server\folder"  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="c2bca-289">Ejecute el código VBScript.</span><span class="sxs-lookup"><span data-stu-id="c2bca-289">Execute the VBScript code.</span></span>  
  
     <span data-ttu-id="c2bca-290">El esquema debe especificar el correspondiente `sql:datatype` para el atributo **CustomerID** cuando el valor de **CustomerID** se especifica como un GUID que incluye llaves ({y}), como:</span><span class="sxs-lookup"><span data-stu-id="c2bca-290">The schema must specify the corresponding `sql:datatype` for the **CustomerID** attribute when the value for **CustomerID** is specified as a GUID that includes braces ({ and }), such as:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="{6F9619FF-8B86-D011-B42D-00C04FC964FF}"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c2bca-291">Éste es el esquema actualizado:</span><span class="sxs-lookup"><span data-stu-id="c2bca-291">This is the updated schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string"   
                        sql:datatype="uniqueidentifier" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
     <span data-ttu-id="c2bca-292">Cuando `sql:datatype` se especifica que identifica el tipo de columna como `uniqueidentifier` , la operación de carga masiva quita las llaves ({y}) del valor **CustomerID** antes de insertarlo en la columna.</span><span class="sxs-lookup"><span data-stu-id="c2bca-292">When `sql:datatype` is specified identifying the column type as `uniqueidentifier`, the bulk load operation removes the braces ({ and }) from the **CustomerID** value before inserting it in the column.</span></span>  
  
 <span data-ttu-id="c2bca-293">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-293">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
<ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
</ElementType>  
<ElementType name="Customers" sql:relation="Cust" >  
  <AttributeType name="CustomerID"  sql:datatype="uniqueidentifier" />  
  <AttributeType name="LastName"   />  
  
  <attribute type="CustomerID" />  
  <attribute type="LastName"   />  
</ElementType>  
</Schema>  
```  
  
## <a name="i-using-an-existing-database-connection-with-the-connectioncommand-property"></a><span data-ttu-id="c2bca-294">I.</span><span class="sxs-lookup"><span data-stu-id="c2bca-294">I.</span></span> <span data-ttu-id="c2bca-295">Usar una conexión de base de datos existente con la propiedad ConnectionCommand</span><span class="sxs-lookup"><span data-stu-id="c2bca-295">Using an existing database connection with the ConnectionCommand property</span></span>  
 <span data-ttu-id="c2bca-296">Puede usar una conexión ADO existente para la carga masiva XML.</span><span class="sxs-lookup"><span data-stu-id="c2bca-296">You can use an existing ADO connection to bulk load XML.</span></span> <span data-ttu-id="c2bca-297">Esto resulta de gran utilidad si la carga masiva XML es simplemente una de entre las muchas operaciones que se realizarán en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c2bca-297">This is useful if XML Bulk Load is just one of many operations that will be performed on a data source.</span></span>  
  
 <span data-ttu-id="c2bca-298">La propiedad ConnectionCommand permite usar una conexión ADO existente mediante un objeto Command de ADO.</span><span class="sxs-lookup"><span data-stu-id="c2bca-298">The ConnectionCommand property enables you to use an existing ADO connection by using an ADO command object.</span></span> <span data-ttu-id="c2bca-299">Esto se muestra en el siguiente ejemplo de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="c2bca-299">This is illustrated in the following Visual Basic example:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad4  
Dim objCmd As New ADODB.Command  
Dim objConn As New ADODB.Connection  
  
'Open a connection to an instance of SQL Server.  
objConn.Open "provider=SQLOLEDB;data source=(local);database=tempdb;integrated security=SSPI"  
'Ask the Command object to use the connection just established.  
Set objCmd.ActiveConnection = objConn  
  
'Tell Bulk Load to use the active command object that is using the Connection obj.  
objBL.ConnectionCommand = objCmd  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
'The Transaction property must be set to True if you use ConnectionCommand.  
objBL.Transaction = True  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
End Sub  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-300">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-300">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-301">Cree dos tablas en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="c2bca-301">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
                   CustomerID   varchar(5) PRIMARY KEY,  
                   CompanyName  varchar(30),  
                   City         varchar(20));  
    GO  
    CREATE TABLE CustOrder(  
                   CustomerID  varchar(5) references Cust (CustomerID),  
                   OrderID     varchar(5) PRIMARY KEY);  
    GO  
    ```  
  
2.  <span data-ttu-id="c2bca-302">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-302">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-303">Agregue al archivo el siguiente esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="c2bca-303">Add the following XSD schema to the file:</span></span>  
  
    ```  
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
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:sequence>  
           <xsd:element name="CustomerID"  type="xsd:integer" />  
           <xsd:element name="CompanyName" type="xsd:string" />  
           <xsd:element name="City"        type="xsd:string" />  
           <xsd:element name="Order"   
                              sql:relation="CustOrder"  
                              sql:relationship="CustCustOrder" >  
             <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:integer" />  
             </xsd:complexType>  
           </xsd:element>  
         </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="c2bca-304">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-304">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-305">Agregue al archivo el siguiente documento XML:</span><span class="sxs-lookup"><span data-stu-id="c2bca-305">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="c2bca-306">Cree una aplicación de Visual Basic (EXE estándar) y el código anterior.</span><span class="sxs-lookup"><span data-stu-id="c2bca-306">Create a Visual Basic (Standard EXE) application and the preceding code.</span></span> <span data-ttu-id="c2bca-307">Agregue estas referencias al proyecto:</span><span class="sxs-lookup"><span data-stu-id="c2bca-307">Add these references to the project:</span></span>  
  
    ```  
    Microsoft XML BulkLoad for SQL Server 4.0 Type Library  
    Microsoft ActiveX Data objects 2.6 Library  
    ```  
  
5.  <span data-ttu-id="c2bca-308">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c2bca-308">Execute the application.</span></span>  
  
 <span data-ttu-id="c2bca-309">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2bca-309">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
         <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="j-bulk-loading-in-xml-data-type-columns"></a><span data-ttu-id="c2bca-310">J.</span><span class="sxs-lookup"><span data-stu-id="c2bca-310">J.</span></span> <span data-ttu-id="c2bca-311">Cargar datos de forma masiva en columnas de tipo de datos xml</span><span class="sxs-lookup"><span data-stu-id="c2bca-311">Bulk loading in xml Data Type columns</span></span>  
 <span data-ttu-id="c2bca-312">Si el esquema de asignación especifica una columna de [tipo de datos XML](/sql/t-sql/xml/xml-transact-sql) mediante la `sql:datatype="xml"` anotación, la carga masiva XML puede copiar los elementos secundarios XML del campo asignado del documento de origen en esta columna.</span><span class="sxs-lookup"><span data-stu-id="c2bca-312">If the mapping schema specifies a [xml data type](/sql/t-sql/xml/xml-transact-sql) column by using the `sql:datatype="xml"` annotation, XML Bulk Load can copy XML child elements for the mapped field from the source document into this column.</span></span>  
  
 <span data-ttu-id="c2bca-313">Fíjese en el esquema XSD siguiente, que asigna una vista de la tabla Production.ProductModel de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c2bca-313">Consider the following XSD schema, which maps a view of the Production.ProductModel table in the AdventureWorks sample database.</span></span> <span data-ttu-id="c2bca-314">En esta tabla, el campo CatalogDescription del `xml` tipo de datos se asigna a un **\<Desc>** elemento mediante `sql:field` las `sql:datatype="xml"` anotaciones y.</span><span class="sxs-lookup"><span data-stu-id="c2bca-314">In this table, the CatalogDescription field of `xml` data type is mapped to a **\<Desc>** element using the `sql:field` and `sql:datatype="xml"` annotations.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Name" type="xs:string"></xsd:element>  
        <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element name="ProductDescription">  
              <xsd:complexType>  
                <xsd:sequence>  
                  <xsd:element name="Summary" type="xs:anyType"/>  
                </xsd:sequence>  
              </xsd:complexType>  
            </xsd:element>  
          </xsd:sequence>  
        </xsd:complexType>  
        </xsd:element>   
     </xsd:sequence>  
     <xsd:attribute name="ProductModelID" sql:field="ProductModelID" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="c2bca-315">Para probar un ejemplo funcional</span><span class="sxs-lookup"><span data-stu-id="c2bca-315">To test a working sample</span></span>  
  
1.  <span data-ttu-id="c2bca-316">Compruebe que esté instalada la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c2bca-316">Verify that the AdventureWorks sample database is installed.</span></span>  
  
2.  <span data-ttu-id="c2bca-317">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-317">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="c2bca-318">Copie el esquema XSD anterior, péguelo en el archivo y guárdelo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-318">Copy the XSD schema above and paste it into the file and save it.</span></span>  
  
3.  <span data-ttu-id="c2bca-319">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="c2bca-319">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="c2bca-320">Copie el siguiente documento XML, péguelo en el archivo y guárdelo en la misma carpeta utilizada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="c2bca-320">Copy the following XML document below and paste it into the file and save it in the same folder as was used for the previous step.</span></span>  
  
    ```  
    <ProductModel ProductModelID="2005">  
        <Name>Mountain-100 (2005 model)</Name>  
        <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
            <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
                  xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
                  xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
                  xmlns:html="http://www.w3.org/1999/xhtml"   
                  xmlns="">  
                <p1:Summary>  
                    <html:p>Our top-of-the-line competition mountain bike.   
          Performance-enhancing options include the innovative HL Frame,   
          super-smooth front suspension, and traction for all terrain.  
                            </html:p>  
                </p1:Summary>  
                <p1:Manufacturer>  
                    <p1:Name>AdventureWorks</p1:Name>  
                    <p1:Copyright>2002-2005</p1:Copyright>  
                    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
                </p1:Manufacturer>  
                <p1:Features>These are the product highlights.   
                     <wm:Warranty>  
                        <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
                        <wm:Description>parts and labor</wm:Description>  
                    </wm:Warranty><wm:Maintenance>  
                        <wm:NoOfYears>10 years</wm:NoOfYears>  
                        <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
                    </wm:Maintenance><wf:wheel>High performance wheels.</wf:wheel><wf:saddle>  
                        <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle><wf:pedal>  
                        <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal><wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter   
          and wall-thickness required of a premium mountain frame.   
          The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame><wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset></p1:Features>  
                <!-- add one or more of these elements... one for each specific product in this product model -->  
                <p1:Picture>  
                    <p1:Angle>front</p1:Angle>  
                    <p1:Size>small</p1:Size>  
                    <p1:ProductPhotoID>118</p1:ProductPhotoID>  
                </p1:Picture>  
                <!-- add any tags in <specifications> -->  
                <p1:Specifications> These are the product specifications.  
                       <Material>Almuminum Alloy</Material><Color>Available in most colors</Color><ProductLine>Mountain bike</ProductLine><Style>Unisex</Style><RiderExperience>Advanced to Professional riders</RiderExperience></p1:Specifications>  
            </p1:ProductDescription>  
        </Desc>  
    </ProductModel>  
    ```  
  
4.  <span data-ttu-id="c2bca-321">Cree un archivo en su editor de texto o editor XML preferido y guárdelo como BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-321">Create a file in your preferred text or XML editor, and save it as BulkloadXml.vbs.</span></span> <span data-ttu-id="c2bca-322">Copie el siguiente código VBScript y péguelo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="c2bca-322">Copy the following VBScript code and paste it into the file.</span></span> <span data-ttu-id="c2bca-323">Guárdelo en la misma carpeta utilizada para los archivos de esquema y datos XML anteriores.</span><span class="sxs-lookup"><span data-stu-id="c2bca-323">Save it in the same folder as was used for the previous XML data and schema files.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=AdventureWorks;integrated security=SSPI"  
  
    Dim fso, sAppPath  
    Set fso = CreateObject("Scripting.FileSystemObject")   
    sAppPath = fso.GetFolder(".")   
  
    objBL.ErrorLogFile = sAppPath & "\error.log"  
  
    'Execute XML bulkload using file.  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="c2bca-324">Ejecute el script BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="c2bca-324">Execute the BulkloadXml.vbs script.</span></span>  
  
  
