---
title: Aplicar una transformación XSL (proveedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, applying XSL transformations
- applying XSL transformations [SQLXML]
- xsl property
- Base Path property
- XSL Transformations [SQLXML]
ms.assetid: cb5e41ab-dd20-4873-af20-f417bd1bbf6d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fbb427a95d9f2308bf65724758a4a1563b42575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674031"
---
# <a name="applying-an-xsl-transformation-sqlxmloledb-provider"></a><span data-ttu-id="c5f5d-102">Aplicar una transformación XSL (proveedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="c5f5d-102">Applying an XSL Transformation (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="c5f5d-103">En esta aplicación ADO de ejemplo, se ejecuta una consulta SQL y se aplica una transformación XSL al resultado.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-103">In this sample ADO application, an SQL query is executed, and an XSL transformation is applied to the result.</span></span> <span data-ttu-id="c5f5d-104">Al establecer la propiedad Clientsidexml, en true, se exige el procesamiento del conjunto de filas en el lado cliente.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-104">Setting the ClientSideXML property to True enforces the processing of the rowset on the client side.</span></span> <span data-ttu-id="c5f5d-105">El lenguaje de comandos se establece en {5d531cb2-e6ed-11d2-b252-00c04f681b71}, porque la consulta SQL se especifica en una plantilla y se debe especificar este lenguaje al ejecutar una plantilla.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-105">The command dialect is set to {5d531cb2-e6ed-11d2-b252-00c04f681b71}, because the SQL query is specified in a template and this dialect must be specified when executing a template.</span></span> <span data-ttu-id="c5f5d-106">La propiedad XSL especifica el archivo XSL que se va a utilizar para aplicar la transformación.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-106">The xsl property specifies the XSL file to use to apply the transformation.</span></span> <span data-ttu-id="c5f5d-107">El valor de la propiedad ruta de acceso base se utiliza para buscar el archivo XSL.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-107">The value of Base Path property is used to search for the XSL file.</span></span> <span data-ttu-id="c5f5d-108">Si especifica una ruta de acceso en el valor de la propiedad XSL, la ruta de acceso es relativa a la ruta de acceso especificada en la propiedad ruta de acceso base.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-108">If you specify a path in the value of the xsl property, the path is relative to the path that is specified in the Base Path property.</span></span>  
  
 <span data-ttu-id="c5f5d-109">En este ejemplo se muestra cómo utilizar las siguientes propiedades SQLXMLOLEDB específicas del proveedor:</span><span class="sxs-lookup"><span data-stu-id="c5f5d-109">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="c5f5d-110">Clientsidexml,</span><span class="sxs-lookup"><span data-stu-id="c5f5d-110">ClientSideXML</span></span>  
  
-   <span data-ttu-id="c5f5d-111">xsl</span><span class="sxs-lookup"><span data-stu-id="c5f5d-111">xsl</span></span>  
  
 <span data-ttu-id="c5f5d-112">En esta aplicación de ejemplo ADO del lado cliente, se ejecuta en el servidor una plantilla XML que consta de una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-112">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="c5f5d-113">Dado que la propiedad Clientsidexml, está establecida en true, la instrucción SELECT sin la cláusula FOR XML se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-113">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="c5f5d-114">El servidor ejecuta la consulta y devuelve un conjunto de filas al cliente.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-114">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="c5f5d-115">A continuación, el cliente aplica la transformación FOR XML al conjunto de filas y genera el documento XML.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-115">The client then applies the FOR XML transformation to the rowset and produces the XML document.</span></span>  
  
 <span data-ttu-id="c5f5d-116">La propiedad XSL se especifica en la aplicación; por lo tanto, la transformación XSL se aplica al documento XML que se genera en el cliente y el resultado es una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-116">The xsl property is specified in the application; therefore, the XSL transformation is applied to the XML document that is generated on the client, and the result is a two-column table.</span></span>  
  
 <span data-ttu-id="c5f5d-117">Para ejecutar el comando de plantilla, se debe especificar la plantilla XML Dialect-{5d531cb2-e6ed-11D2-b252-00c04f681b71}-.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-117">To execute the template command, the XML template dialect - {5d531cb2-e6ed-11d2-b252-00c04f681b71} - must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5f5d-118">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-118">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="c5f5d-119">Además, este ejemplo especifica el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para el proveedor de datos, que exige la instalación de software cliente de red adicional.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-119">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="c5f5d-120">Para obtener más información, vea [requisitos del sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c5f5d-120">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
Set oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = _  
        "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' >" & _  
       " <sql:query> " & _  
        "   SELECT TOP 25 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
oTestStream.Open  
' You need the dialect if you are executing a template.  
oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\ExecuteTemplateWithXSL\"  
oTestCommand.Properties("xsl").Value = "myxsl.xsl"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
 <span data-ttu-id="c5f5d-121">La plantilla XSL sigue.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-121">The XSL template follows.</span></span> <span data-ttu-id="c5f5d-122">El resultado de aplicar esta plantilla XSL es una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="c5f5d-122">The result of applying this XSL template is a two-column table.</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>            
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR>  
              <TH >First name</TH>  
              <TH>Last name</TH>  
           </TR>  
           <xsl:apply-templates select = 'ROOT' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
  
