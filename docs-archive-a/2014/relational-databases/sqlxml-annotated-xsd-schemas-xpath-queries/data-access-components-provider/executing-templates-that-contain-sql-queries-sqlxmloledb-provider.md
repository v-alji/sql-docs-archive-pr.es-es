---
title: Ejecutar plantillas que contienen consultas SQL (proveedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- templates [SQLXML]
- SQLXMLOLEDB Provider, executing template files
- templates [SQLXML], SQL queries
- XML templates [SQLXML]
- SQL queries [SQLXML]
ms.assetid: ff2bc36f-e3fb-4d8f-8e3a-2680a39eda11
author: rothja
ms.author: jroth
ms.openlocfilehash: c3d3bc340612286e211d85f52a3d914d1d1b6b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674030"
---
# <a name="executing-templates-that-contain-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="41639-102">Ejecutar plantillas que contienen consultas SQL (proveedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="41639-102">Executing Templates That Contain SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="41639-103">En este ejemplo se muestra el uso de la propiedad específica del proveedor SQLXMLOLEDB Clientsidexml,.</span><span class="sxs-lookup"><span data-stu-id="41639-103">This example illustrates the use of the SQLXMLOLEDB Provider-specific property ClientSideXML.</span></span> <span data-ttu-id="41639-104">En esta aplicación de ejemplo ADO del lado cliente, se ejecuta en el servidor una plantilla XML que consta de una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="41639-104">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="41639-105">Dado que la propiedad Clientsidexml, está establecida en true, la instrucción SELECT sin la cláusula FOR XML se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="41639-105">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="41639-106">El servidor ejecuta la consulta y devuelve un conjunto de filas al cliente.</span><span class="sxs-lookup"><span data-stu-id="41639-106">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="41639-107">A continuación, el cliente aplica la transformación FOR XML al conjunto de filas y genera un documento XML.</span><span class="sxs-lookup"><span data-stu-id="41639-107">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="41639-108">La plantilla XML proporciona un único elemento raíz de nivel superior ( \<ROOT> ) para el documento XML que se genera; por lo tanto, no se proporciona la propiedad raíz de XML.</span><span class="sxs-lookup"><span data-stu-id="41639-108">The XML template provides a single top-level root element (\<ROOT>) for the XML document that is generated; therefore, the xml root property is not provided.</span></span>  
  
 <span data-ttu-id="41639-109">Para ejecutar plantillas XML, se debe especificar el dialecto {5d531cb2-e6ed-11d2-b252-00c04f681b71}.</span><span class="sxs-lookup"><span data-stu-id="41639-109">To execute XML templates, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41639-110">En el código, debe suministrarse el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="41639-110">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="41639-111">Además, este ejemplo especifica el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para el proveedor de datos que requiere la instalación de software cliente de red adicional.</span><span class="sxs-lookup"><span data-stu-id="41639-111">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="41639-112">Para obtener más información, vea [requisitos del sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="41639-112">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
  
Sub Main()  
  Dim oTestStream As New ADODB.Stream  
  Dim oTestConnection As New ADODB.Connection  
  Dim oTestCommand As New ADODB.Command  
  oTestConnection.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
  
  Set oTestCommand.ActiveConnection = oTestConnection  
  oTestCommand.Properties("ClientSideXML") = True  
  oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:query> " & _  
        "   SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
  oTestStream.Open  
  ' You need the dialect if you are executing   
  ' XML templates (not for SQL queries).  
  oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  oTestCommand.Properties("Output Stream").Value = oTestStream  
  oTestCommand.Execute , , adExecuteStream  
  
  oTestStream.Position = 0  
  oTestStream.Charset = "utf-8"  
  Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
  
Sub Form_Load()  
  Main  
End Sub  
```  
  
  
