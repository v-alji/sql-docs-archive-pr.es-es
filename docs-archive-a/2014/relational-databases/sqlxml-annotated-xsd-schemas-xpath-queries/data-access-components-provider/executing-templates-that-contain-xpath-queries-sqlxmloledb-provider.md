---
title: Ejecutar plantillas que contienen consultas XPath (proveedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing template files
- Base Path property
- templates [SQLXML], XPath queries
- XPath queries [SQLXML], templates
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
- XML templates [SQLXML]
ms.assetid: 7368c188-607e-459e-8254-8f23352dfa01
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d31c95fe5d4fb1b7dc9a8d039a56b41cdd7349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746197"
---
# <a name="executing-templates-that-contain-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="4b3a4-102">Ejecutar plantillas que contienen consultas XPath (Proveedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="4b3a4-102">Executing Templates That Contain XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="4b3a4-103">En este ejemplo se muestra cómo utilizar las siguientes propiedades SQLXMLOLEDB específicas del proveedor:</span><span class="sxs-lookup"><span data-stu-id="4b3a4-103">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="4b3a4-104">Clientsidexml,</span><span class="sxs-lookup"><span data-stu-id="4b3a4-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="4b3a4-105">Ruta de base</span><span class="sxs-lookup"><span data-stu-id="4b3a4-105">Base Path</span></span>  
  
-   <span data-ttu-id="4b3a4-106">Esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="4b3a4-106">Mapping Schema</span></span>  
  
 <span data-ttu-id="4b3a4-107">En esta aplicación ADO de ejemplo, se especifica una plantilla XML compuesta de una consulta XPath (raíz) en el esquema de asignación XSD (MySchema.xml) que se describe en [ejecutar consultas xpath &#40;proveedor de SQLXMLOLEDB&#41;](executing-xpath-queries-sqlxmloledb-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4b3a4-107">In this sample ADO application, an XML template that consists of an XPath query (root) is specified against the XSD mapping schema (MySchema.xml) that is described in [Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;](executing-xpath-queries-sqlxmloledb-provider.md).</span></span>  
  
 <span data-ttu-id="4b3a4-108">La propiedad esquema de asignación proporciona el esquema de asignación XSD en el que se ejecuta la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-108">The Mapping Schema property provides the XSD mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="4b3a4-109">La propiedad ruta de acceso base proporciona la ruta de acceso del archivo al esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="4b3a4-110">La propiedad Clientsidexml, se establece en true.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="4b3a4-111">Por lo tanto, el documento XML se genera en el cliente.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="4b3a4-112">En la aplicación, se especifica una consulta XPath directamente.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="4b3a4-113">Por lo tanto, debe estar incluido el lenguaje {5d531cb2-e6ed-11d2-b252-00c04f681b71}.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-113">Therefore, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b3a4-114">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-114">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="4b3a4-115">Además, este ejemplo especifica el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para el proveedor de datos que requiere la instalación de software cliente de red adicional.</span><span class="sxs-lookup"><span data-stu-id="4b3a4-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="4b3a4-116">Para obtener más información, vea [requisitos del sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="4b3a4-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub Main()  
  
   Dim oTestStream As New ADODB.Stream  
   Dim oTestConnection As New ADODB.Connection  
   Dim oTestCommand As New ADODB.Command  
  
   oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
  
   oTestCommand.ActiveConnection = oTestConnection  
   oTestCommand.Properties("ClientSideXML") = "False"  
  
   oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:xpath-query mapping-schema='mySchema.xml' > " & _  
        "   root " & _  
        "   </sql:xpath-query> " & _  
        " </ROOT> "  
   oTestStream.Open  
   ' You need the dialect if you are executing a template.  
   oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
   oTestCommand.Properties("Output Stream").Value = oTestStream  
   oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\TemplateWithXPath\"  
   oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
   oTestCommand.Properties("Output Encoding") = "utf-8"  
   oTestCommand.Execute , , adExecuteStream  
   oTestStream.Position = 0  
   oTestStream.Charset = "utf-8"  
   Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
  
Sub Form_Load()  
   Main  
End Sub  
```  
  
 <span data-ttu-id="4b3a4-117">Éste es el esquema:</span><span class="sxs-lookup"><span data-stu-id="4b3a4-117">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contact'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  
  <xsd:element name='Contact' sql:relation='Person.Contact'>  
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
  
