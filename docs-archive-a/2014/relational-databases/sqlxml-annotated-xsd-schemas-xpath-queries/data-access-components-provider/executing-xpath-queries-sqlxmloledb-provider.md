---
title: Ejecutar consultas XPath (proveedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- queries [SQLXML], SQLXMLOLEDB Provider
- Base Path property
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
ms.assetid: 19063222-dc9c-48ae-a55f-778103674a9e
author: rothja
ms.author: jroth
ms.openlocfilehash: 667bc8dfd95c37c0a10c0bc68f3007e7d04533e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746198"
---
# <a name="executing-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="1c2eb-102">Ejecutar consultas XPath (proveedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="1c2eb-102">Executing XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="1c2eb-103">En este ejemplo se muestra el uso de las siguientes propiedades SQLXMLOLEDB específicas del proveedor:</span><span class="sxs-lookup"><span data-stu-id="1c2eb-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   `ClientSideXML`  
  
-   `Base Path`  
  
-   `Mapping Schema`  
  
 <span data-ttu-id="1c2eb-104">En esta aplicación ADO de ejemplo, se especifica una consulta XPath (raíz) en un esquema de asignación XSD (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="1c2eb-104">In this sample ADO application, an XPath query (root) is specified against an XSD mapping schema (MySchema.xml).</span></span> <span data-ttu-id="1c2eb-105">El esquema tiene un **\<Contacts>** elemento con los atributos **ContactID**, **FirstName**y **LastName** .</span><span class="sxs-lookup"><span data-stu-id="1c2eb-105">The schema has a **\<Contacts>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span> <span data-ttu-id="1c2eb-106">En el esquema, tiene lugar la asignación predeterminada: un nombre de elemento se asigna a la tabla con el mismo nombre y los atributos de tipo simple se asignan a las columnas con los mismos nombres.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-106">In the schema, default mapping takes place: an element name maps to the table with the same name, and attributes of simple type map to the columns with the same names.</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contacts'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name='Contacts' sql:relation='Person.Contact'>   
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1c2eb-107">La propiedad esquema de asignación proporciona el esquema de asignación en el que se ejecuta la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-107">The Mapping Schema property provides the mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="1c2eb-108">El esquema de asignación puede ser un esquema XSD o XDR.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-108">The mapping schema can be an XSD or XDR schema.</span></span> <span data-ttu-id="1c2eb-109">La propiedad ruta de acceso base proporciona la ruta de acceso del archivo al esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="1c2eb-110">La propiedad Clientsidexml, se establece en true.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="1c2eb-111">Por lo tanto, el documento XML se genera en el cliente.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="1c2eb-112">En la aplicación, se especifica una consulta XPath directamente.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="1c2eb-113">Por ello, debe incluirse el dialecto XPath {ec2a4293-e898-11d2-b1b7-00c04f680c56}.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-113">Therefore, the XPath dialect {ec2a4293-e898-11d2-b1b7-00c04f680c56} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c2eb-114">En el código, debe suministrarse el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-114">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="1c2eb-115">Además, este ejemplo especifica el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para el proveedor de datos que requiere la instalación de software cliente de red adicional.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="1c2eb-116">Para obtener más información, vea [requisitos del sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="1c2eb-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security= SSPI;"  
  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
  
oTestCommand.CommandText = "root"  
oTestStream.Open  
oTestCommand.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\XPathDirect\"  
oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
oTestCommand.Properties("Output Encoding") = "utf-8"  
oTestCommand.Execute , , adExecuteStream  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
