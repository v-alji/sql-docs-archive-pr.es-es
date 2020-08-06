---
title: Ejecutar consultas SQL (proveedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXMLOLEDB Provider
- xml root property [SQLXML]
- SQLXMLOLEDB Provider, executing SQL queries
- SQL queries [SQLXML]
ms.assetid: 50334cf5-9c87-4c00-9beb-e08577c4fa82
author: rothja
ms.author: jroth
ms.openlocfilehash: a1e2cc87f90700e3b81a5a2ec3dd80f219a9b1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674744"
---
# <a name="executing-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="c9fcc-102">Ejecutar consultas SQL (proveedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="c9fcc-102">Executing SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="c9fcc-103">En este ejemplo se muestra el uso de las siguientes propiedades SQLXMLOLEDB específicas del proveedor:</span><span class="sxs-lookup"><span data-stu-id="c9fcc-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="c9fcc-104">Clientsidexml,</span><span class="sxs-lookup"><span data-stu-id="c9fcc-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="c9fcc-105">xml root</span><span class="sxs-lookup"><span data-stu-id="c9fcc-105">xml root</span></span>  
  
 <span data-ttu-id="c9fcc-106">En esta aplicación de ejemplo ADO del lado cliente, se ejecuta una consulta SQL simple en el cliente.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-106">In this client-side ADO sample application, a simple SQL query is executed on the client.</span></span> <span data-ttu-id="c9fcc-107">Dado que la propiedad Clientsidexml, está establecida en true, la instrucción SELECT sin la cláusula FOR XML se envía al servidor.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-107">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="c9fcc-108">El servidor ejecuta la consulta y devuelve un conjunto de filas al cliente.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-108">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="c9fcc-109">A continuación, el cliente aplica la transformación FOR XML al conjunto de filas y genera un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-109">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="c9fcc-110">La propiedad raíz XML proporciona el elemento raíz de nivel superior único para el documento XML que se genera.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-110">The xml root property provides the single top-level root element for the XML document that is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9fcc-111">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="c9fcc-112">Además, este ejemplo especifica el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para el proveedor de datos, que exige la instalación de software cliente de red adicional.</span><span class="sxs-lookup"><span data-stu-id="c9fcc-112">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="c9fcc-113">Para obtener más información, vea [requisitos del sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c9fcc-113">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI ;"  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = "SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO"  
oTestStream.Open  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("xml root") = "root"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
