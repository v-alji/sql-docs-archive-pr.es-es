---
title: Transferir datos | Microsoft Docs
ms.custom: ''
ms.date: 10/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- data transfers [SMO]
- transferring data
ms.assetid: eea255c3-8251-40f0-973b-fe4ef6cb5261
author: stevestein
ms.author: sstein
ms.openlocfilehash: dcbcdc1e61c2d18f6a98f797385145f04dfecc7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746202"
---
# <a name="transferring-data"></a><span data-ttu-id="b1713-102">Transferir datos</span><span class="sxs-lookup"><span data-stu-id="b1713-102">Transferring Data</span></span>
  <span data-ttu-id="b1713-103">La clase <xref:Microsoft.SqlServer.Management.Smo.Transfer> es una clase de utilidad que proporciona herramientas para transferir objetos y datos.</span><span class="sxs-lookup"><span data-stu-id="b1713-103">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> class is a utility class that provides tools to transfer objects and data.</span></span>  
  
 <span data-ttu-id="b1713-104">Los objetos del esquema de la base de datos se transfieren ejecutando un script generado en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="b1713-104">Objects in the database schema are transferred by executing a generated script on the target server.</span></span> <span data-ttu-id="b1713-105">Los datos de <xref:Microsoft.SqlServer.Management.Smo.Table> se transfieren con un paquete DTS creado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="b1713-105"><xref:Microsoft.SqlServer.Management.Smo.Table> data is transferred with a dynamically created DTS package.</span></span>  
  
 <span data-ttu-id="b1713-106">El objeto <xref:Microsoft.SqlServer.Management.Smo.Transfer> contiene toda la funcionalidad de los objetos <xref:Microsoft.SqlServer.Management.Smo.Transfer> de DMO y otra funcionalidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] adicional.</span><span class="sxs-lookup"><span data-stu-id="b1713-106">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> object contains all the functionality of the <xref:Microsoft.SqlServer.Management.Smo.Transfer> objects in DMO and additional [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="b1713-107">Sin embargo, en SMO en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , el <xref:Microsoft.SqlServer.Management.Smo.Transfer> objeto usa la API [SQLBulkCopy](https://msdn.microsoft.com/library/system.data.sqlclient.sqlbulkcopy\(v=VS.90\).aspx) para transferir datos.</span><span class="sxs-lookup"><span data-stu-id="b1713-107">However, in SMO in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object uses the [SQLBulkCopy](https://msdn.microsoft.com/library/system.data.sqlclient.sqlbulkcopy\(v=VS.90\).aspx) API to transfer data.</span></span> <span data-ttu-id="b1713-108">Además, los métodos y propiedades que se utilizan para realizar transferencias de datos residen en el objeto <xref:Microsoft.SqlServer.Management.Smo.Transfer> en lugar del objeto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="b1713-108">Also, the methods and properties that are used to perform data transfers reside on the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object instead of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="b1713-109">Mover la funcionalidad de las clases de instancia a las clases de utilidad es coherente con un modelo de objetos más ligero porque el código para las tareas concretas solamente se carga cuando se requiere.</span><span class="sxs-lookup"><span data-stu-id="b1713-109">Moving functionality from the instance classes to utility classes is consistent with a lighter object model because the code for specific tasks is loaded only when it is required.</span></span>  
  
 <span data-ttu-id="b1713-110">El objeto <xref:Microsoft.SqlServer.Management.Smo.Transfer> no admite transferencias de datos a una base de datos de destino cuyo valor de <xref:Microsoft.SqlServer.Management.Smo.Database.CompatibilityLevel%2A> sea menor que la versión de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1713-110">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> object does not support data transfers to a target database that has a <xref:Microsoft.SqlServer.Management.Smo.Database.CompatibilityLevel%2A> less than the version of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1713-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1713-111">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-visual-basic"></a><span data-ttu-id="b1713-112">Transferir esquemas y datos de una base de datos a otra en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1713-112">Transferring Schema and Data from One Database to Another in Visual Basic</span></span>  
 <span data-ttu-id="b1713-113">En este ejemplo de código se muestra cómo transferir esquemas y datos de una base de datos a otra utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="b1713-113">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```vb
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Reference the AdventureWorks2012 2008R2 database
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Create a new database that is to be destination database.
Dim dbCopy As Database
dbCopy = New Database(srv, "AdventureWorks2012Copy")
dbCopy.Create()
'Define a Transfer object and set the required options and properties.
Dim xfr As Transfer
xfr = New Transfer(db)
xfr.CopyAllTables = True
xfr.Options.WithDependencies = True
xfr.Options.ContinueScriptingOnError = True
xfr.DestinationDatabase = "AdventureWorks2012Copy"
xfr.DestinationServer = srv.Name
xfr.DestinationLoginSecure = True
xfr.CopySchema = True
'Script the transfer. Alternatively perform immediate data transfer with TransferData method.
xfr.ScriptTransfer()
```
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-visual-c"></a><span data-ttu-id="b1713-114">Transferir esquemas y datos de una base de datos a otra en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b1713-114">Transferring Schema and Data from One Database to Another in Visual C#</span></span>  
 <span data-ttu-id="b1713-115">En este ejemplo de código se muestra cómo transferir esquemas y datos de una base de datos a otra utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="b1713-115">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```csharp
{  
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
            //Create a new database that is to be destination database.   
            Database dbCopy;  
            dbCopy = new Database(srv, "AdventureWorks2012Copy");  
            dbCopy.Create();  
            //Define a Transfer object and set the required options and properties.   
            Transfer xfr;  
            xfr = new Transfer(db);  
            xfr.CopyAllTables = true;  
            xfr.Options.WithDependencies = true;  
            xfr.Options.ContinueScriptingOnError = true;  
            xfr.DestinationDatabase = "AdventureWorks2012Copy";  
            xfr.DestinationServer = srv.Name;  
            xfr.DestinationLoginSecure = true;  
            xfr.CopySchema = true;  
            //Script the transfer. Alternatively perform immediate data transfer   
            // with TransferData method.   
            xfr.ScriptTransfer();  
        }   
```  
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-powershell"></a><span data-ttu-id="b1713-116">Transferir esquemas y datos de una base de datos a otra en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1713-116">Transferring Schema and Data from One Database to Another in PowerShell</span></span>  
 <span data-ttu-id="b1713-117">En este ejemplo de código se muestra cómo transferir esquemas y datos de una base de datos a otra utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="b1713-117">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```powershell
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Reference the AdventureWorks2012 database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a database to hold the copy of AdventureWorks  
$dbCopy = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Database -ArgumentList $srv, "AdventureWorksCopy"  
$dbCopy.Create()  
  
#Define a Transfer object and set the required options and properties.  
$xfr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Transfer -ArgumentList $db  
  
#Set this objects properties  
$xfr.CopyAllTables = $true  
$xfr.Options.WithDependencies = $true  
$xfr.Options.ContinueScriptingOnError = $true  
$xfr.DestinationDatabase = "AdventureWorksCopy"  
$xfr.DestinationServer = $srv.Name  
$xfr.DestinationLoginSecure = $true  
$xfr.CopySchema = $true  
"Scripting Data Transfer"  
#Script the transfer. Alternatively perform immediate data transfer with TransferData method.  
$xfr.ScriptTransfer()  
```  