---
title: Agregar conexiones mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- connection managers [Integration Services], packages
- Integration Services packages, connections
- connections [Integration Services], packages
- SSIS packages, connections
- packages [Integration Services], connections
- intrinsic properties [Integration Services]
- SQL Server Integration Services packages, connections
- ConnectionManager class
- SSIS connection managers
- adding package connections
ms.assetid: d90716d1-4c65-466c-b82c-4aabbee1e3e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5952221dbf2689d2328695baf965ce884dc07fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671647"
---
# <a name="adding-connections-programmatically"></a><span data-ttu-id="9f0da-102">Agregar conexiones mediante programación</span><span class="sxs-lookup"><span data-stu-id="9f0da-102">Adding Connections Programmatically</span></span>
  <span data-ttu-id="9f0da-103">La clase <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> representa las conexiones físicas con los orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="9f0da-103">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class represents physical connections to external data sources.</span></span> <span data-ttu-id="9f0da-104">La clase <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> aísla los detalles de la implementación de la conexión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f0da-104">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class isolates the implementation details of the connection from the runtime.</span></span> <span data-ttu-id="9f0da-105">Esto habilita al tiempo de ejecución para que interactúe con cada administrador de conexiones de una manera coherente y de predicción.</span><span class="sxs-lookup"><span data-stu-id="9f0da-105">This enables the runtime to interact with each connection manager in a consistent and predictable manner.</span></span> <span data-ttu-id="9f0da-106">Los administradores de conexiones contienen un conjunto de propiedades estándar que todas las conexiones tienen en el común, como <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f0da-106">Connection managers contain a set of stock properties that all connections have in common, such as the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span></span> <span data-ttu-id="9f0da-107">Sin embargo, las propiedades <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> son normalmente las únicas propiedades que se requieren para configurar un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9f0da-107">However, the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> properties are ordinarily the only properties required to configure a connection manager.</span></span> <span data-ttu-id="9f0da-108">A diferencia de otros paradigmas de programación, donde las clases de conexión exponen métodos como `Open` o `Connect` para establecer físicamente una conexión al origen de datos, el motor de ejecución administra todas las conexiones para el paquete mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="9f0da-108">Unlike other programming paradigms, where connection classes expose methods such as `Open` or `Connect` to physically establish a connection to the data source, the run-time engine manages all the connections for the package while it runs.</span></span>  
  
 <span data-ttu-id="9f0da-109">La clase <xref:Microsoft.SqlServer.Dts.Runtime.Connections> es una colección de los administradores de conexiones agregados a ese paquete y que están disponibles para su uso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f0da-109">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> class is a collection of the connection managers that have been added to that package and are available for use at run time.</span></span> <span data-ttu-id="9f0da-110">Puede agregar más administradores de conexiones a la colección mediante el método <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> de la colección y proporcionando una cadena que indica el tipo de administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9f0da-110">You can add more connection managers to the collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method of the collection, and supplying a string that indicates the connection manager type.</span></span> <span data-ttu-id="9f0da-111">El método <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> devuelve la instancia <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> que se agregó al paquete.</span><span class="sxs-lookup"><span data-stu-id="9f0da-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method returns the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> instance that was added to the package.</span></span>  
  
## <a name="intrinsic-properties"></a><span data-ttu-id="9f0da-112">Propiedades intrínsecas</span><span class="sxs-lookup"><span data-stu-id="9f0da-112">Intrinsic Properties</span></span>  
 <span data-ttu-id="9f0da-113">La clase <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> expone un conjunto de propiedades comunes para todas las colecciones.</span><span class="sxs-lookup"><span data-stu-id="9f0da-113">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class exposes a set of properties that are common to all connections.</span></span> <span data-ttu-id="9f0da-114">Sin embargo, a veces se necesita tener acceso a las propiedades que son únicas para un tipo de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="9f0da-114">However, sometimes you need access to properties that are unique to the specific connection type.</span></span> <span data-ttu-id="9f0da-115">La colección <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> de la clase <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> proporciona el acceso a estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="9f0da-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class provides access to these properties.</span></span> <span data-ttu-id="9f0da-116">Las propiedades se pueden recuperar de la colección mediante el indizador, o el nombre de propiedad y el método **GetValue**, y los valores se establecen mediante el método **SetValue**.</span><span class="sxs-lookup"><span data-stu-id="9f0da-116">The properties can be retrieved from the collection using the indexer or the property name and the **GetValue** method, and the values are set using the **SetValue** method.</span></span> <span data-ttu-id="9f0da-117">Las propiedades de las propiedades de objeto de conexión subyacente también se pueden establecer adquiriendo una instancia real del objeto y estableciendo directamente sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9f0da-117">The properties of the underlying connection object properties can also be set by acquiring an actual instance of the object and setting its properties directly.</span></span> <span data-ttu-id="9f0da-118">Para obtener la conexión subyacente, use la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9f0da-118">To get the underlying connection, use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> property of the connection manager.</span></span> <span data-ttu-id="9f0da-119">La siguiente línea de código muestra una línea de C# que crea un administrador de conexiones de ADO.NET que tiene la clase subyacente, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span><span class="sxs-lookup"><span data-stu-id="9f0da-119">The following line of code shows a C# line that creates an ADO.NET connection manager that has the underlying class, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span></span>  
  
 `ConnectionManagerAdoNetClass cmado = cm.InnerObject as ConnectionManagerAdoNet;`  
  
 <span data-ttu-id="9f0da-120">Esto convierte el objeto de administrador de conexiones en su objeto de conexión subyacente.</span><span class="sxs-lookup"><span data-stu-id="9f0da-120">This casts the managed connection manager object to its underlying connection object.</span></span> <span data-ttu-id="9f0da-121">Si usa C++, se llama al método `QueryInterface` del objeto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y se solicita la interfaz del objeto de conexión subyacente.</span><span class="sxs-lookup"><span data-stu-id="9f0da-121">If you are using C++, the `QueryInterface` method of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object is called and the interface of the underlying connection object is requested.</span></span>  
  
 <span data-ttu-id="9f0da-122">En la tabla siguiente se enumeran los administradores de conexión que se incluyen en [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0da-122">The following table lists the connection managers included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="9f0da-123">y la cadena que se utiliza en la instrucción `package.Connections.Add("xxx")`.</span><span class="sxs-lookup"><span data-stu-id="9f0da-123">and the string that is used in the `package.Connections.Add("xxx")` statement.</span></span> <span data-ttu-id="9f0da-124">Para obtener una lista de todos los administradores de conexión, vea [Conexiones de Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="9f0da-124">For a list of all connection managers, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
|<span data-ttu-id="9f0da-125">String</span><span class="sxs-lookup"><span data-stu-id="9f0da-125">String</span></span>|<span data-ttu-id="9f0da-126">Administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="9f0da-126">Connection manager</span></span>|  
|------------|------------------------|  
|<span data-ttu-id="9f0da-127">"OLEDB"</span><span class="sxs-lookup"><span data-stu-id="9f0da-127">"OLEDB"</span></span>|<span data-ttu-id="9f0da-128">Administrador de conexiones para conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9f0da-128">Connection manager for OLE DB connections.</span></span>|  
|<span data-ttu-id="9f0da-129">"ODBC"</span><span class="sxs-lookup"><span data-stu-id="9f0da-129">"ODBC"</span></span>|<span data-ttu-id="9f0da-130">Administrador de conexiones para conexiones ODBC.</span><span class="sxs-lookup"><span data-stu-id="9f0da-130">Connection manager for ODBC connections.</span></span>|  
|<span data-ttu-id="9f0da-131">"ADO"</span><span class="sxs-lookup"><span data-stu-id="9f0da-131">"ADO"</span></span>|<span data-ttu-id="9f0da-132">Administrador de conexiones para conexiones ADO.</span><span class="sxs-lookup"><span data-stu-id="9f0da-132">Connection manager for ADO connections.</span></span>|  
|<span data-ttu-id="9f0da-133">"ADO.NET:SQL"</span><span class="sxs-lookup"><span data-stu-id="9f0da-133">"ADO.NET:SQL"</span></span>|<span data-ttu-id="9f0da-134">Administrador de conexiones para conexiones ADO.NET (proveedor de datos SQL).</span><span class="sxs-lookup"><span data-stu-id="9f0da-134">Connection manager for ADO.NET (SQL data provider) connections.</span></span>|  
|<span data-ttu-id="9f0da-135">"ADO.NET:OLEDB"</span><span class="sxs-lookup"><span data-stu-id="9f0da-135">"ADO.NET:OLEDB"</span></span>|<span data-ttu-id="9f0da-136">Administrador de conexiones para conexiones ADO.NET (proveedor de datos OLE DB).</span><span class="sxs-lookup"><span data-stu-id="9f0da-136">Connection manager for ADO.NET (OLE DB data provider) connections.</span></span>|  
|<span data-ttu-id="9f0da-137">"FLATFILE"</span><span class="sxs-lookup"><span data-stu-id="9f0da-137">"FLATFILE"</span></span>|<span data-ttu-id="9f0da-138">Administrador de conexiones para conexiones de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="9f0da-138">Connection manager for flat file connections.</span></span>|  
|<span data-ttu-id="9f0da-139">"FILE"</span><span class="sxs-lookup"><span data-stu-id="9f0da-139">"FILE"</span></span>|<span data-ttu-id="9f0da-140">Administrador de conexiones para conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="9f0da-140">Connection manager for file connections.</span></span>|  
|<span data-ttu-id="9f0da-141">"MULTIFLATFILE"</span><span class="sxs-lookup"><span data-stu-id="9f0da-141">"MULTIFLATFILE"</span></span>|<span data-ttu-id="9f0da-142">Administrador de conexiones para varias conexiones de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="9f0da-142">Connection manager for multiple flat file connections.</span></span>|  
|<span data-ttu-id="9f0da-143">"MULTIFILE"</span><span class="sxs-lookup"><span data-stu-id="9f0da-143">"MULTIFILE"</span></span>|<span data-ttu-id="9f0da-144">Administrador de conexiones para varias conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="9f0da-144">Connection manager for multiple file connections.</span></span>|  
|<span data-ttu-id="9f0da-145">"SQLMOBILE"</span><span class="sxs-lookup"><span data-stu-id="9f0da-145">"SQLMOBILE"</span></span>|<span data-ttu-id="9f0da-146">Administrador de conexiones para conexiones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="9f0da-146">Connection manager for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connections.</span></span>|  
|<span data-ttu-id="9f0da-147">"MSOLAP100"</span><span class="sxs-lookup"><span data-stu-id="9f0da-147">"MSOLAP100"</span></span>|<span data-ttu-id="9f0da-148">Administrador de conexiones para conexiones [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f0da-148">Connection manager for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections.</span></span>|  
|<span data-ttu-id="9f0da-149">"FTP"</span><span class="sxs-lookup"><span data-stu-id="9f0da-149">"FTP"</span></span>|<span data-ttu-id="9f0da-150">Administrador de conexiones para conexiones FTP.</span><span class="sxs-lookup"><span data-stu-id="9f0da-150">Connection manager for FTP connections.</span></span>|  
|<span data-ttu-id="9f0da-151">"HTTP"</span><span class="sxs-lookup"><span data-stu-id="9f0da-151">"HTTP"</span></span>|<span data-ttu-id="9f0da-152">Administrador de conexiones para conexiones HTTP.</span><span class="sxs-lookup"><span data-stu-id="9f0da-152">Connection manager for HTTP connections.</span></span>|  
|<span data-ttu-id="9f0da-153">"MSMQ"</span><span class="sxs-lookup"><span data-stu-id="9f0da-153">"MSMQ"</span></span>|<span data-ttu-id="9f0da-154">Administrador de conexiones para conexiones Message Queuing (también denominado MSMQ).</span><span class="sxs-lookup"><span data-stu-id="9f0da-154">Connection manager for Message Queuing (also known as MSMQ) connections.</span></span>|  
|<span data-ttu-id="9f0da-155">"SMTP"</span><span class="sxs-lookup"><span data-stu-id="9f0da-155">"SMTP"</span></span>|<span data-ttu-id="9f0da-156">Administrador de conexiones para conexiones SMTP.</span><span class="sxs-lookup"><span data-stu-id="9f0da-156">Connection manager for SMTP connections.</span></span>|  
|<span data-ttu-id="9f0da-157">"WMI"</span><span class="sxs-lookup"><span data-stu-id="9f0da-157">"WMI"</span></span>|<span data-ttu-id="9f0da-158">Administrador de conexiones para conexiones WMI (Instrumental de administración de Windows).</span><span class="sxs-lookup"><span data-stu-id="9f0da-158">Connection manager for Microsoft Windows Management Instrumentation (WMI) connections.</span></span>|  
  
 <span data-ttu-id="9f0da-159">En el siguiente ejemplo de código se muestra cómo agregar una conexión OLE DB y FILE a la colección <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span><span class="sxs-lookup"><span data-stu-id="9f0da-159">The following code example demonstrates adding an OLE DB and FILE connection to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> collection of a <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span></span> <span data-ttu-id="9f0da-160">Después, se establecen las propiedades <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f0da-160">The example then sets the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> properties.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package, and retrieve its connections.  
      Package pkg = new Package();  
      Connections pkgConns = pkg.Connections;  
  
      // Add an OLE DB connection to the package, using the   
      // method defined in the AddConnection class.  
      CreateConnection myOLEDBConn = new CreateConnection();  
      myOLEDBConn.CreateOLEDBConnection(pkg);  
  
      // View the new connection in the package.  
      Console.WriteLine("Connection description: {0}",  
         pkg.Connections["SSIS Connection Manager for OLE DB"].Description);  
  
      // Add a second connection to the package.  
      CreateConnection myFileConn = new CreateConnection();  
      myFileConn.CreateFileConnection(pkg);  
  
      // View the second connection in the package.  
      Console.WriteLine("Connection description: {0}",  
        pkg.Connections["SSIS Connection Manager for Files"].Description);  
  
      Console.WriteLine();  
      Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count);  
  
      Console.Read();  
    }  
  }  
  // <summary>  
  // This class contains the definitions for multiple  
  // connection managers.  
  // </summary>  
  public class CreateConnection  
  {  
    // Private data.  
    private ConnectionManager ConMgr;  
  
    // Class definition for OLE DB Provider.  
    public void CreateOLEDBConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("OLEDB");  
      ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" +  
        "Data Source=(local);";  
      ConMgr.Name = "SSIS Connection Manager for OLE DB";  
      ConMgr.Description = "OLE DB connection to the AdventureWorks database.";  
    }  
    public void CreateFileConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("File");  
      ConMgr.ConnectionString = @"\\<yourserver>\<yourfolder>\books.xml";  
      ConMgr.Name = "SSIS Connection Manager for Files";  
      ConMgr.Description = "Flat File connection";  
    }  
  }  
  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package, and retrieve its connections.  
    Dim pkg As New Package()  
    Dim pkgConns As Connections = pkg.Connections  
  
    ' Add an OLE DB connection to the package, using the   
    ' method defined in the AddConnection class.  
    Dim myOLEDBConn As New CreateConnection()  
    myOLEDBConn.CreateOLEDBConnection(pkg)  
  
    ' View the new connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for OLE DB").Description)  
  
    ' Add a second connection to the package.  
    Dim myFileConn As New CreateConnection()  
    myFileConn.CreateFileConnection(pkg)  
  
    ' View the second connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for Files").Description)  
  
    Console.WriteLine()  
    Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
' This class contains the definitions for multiple  
' connection managers.  
  
Public Class CreateConnection  
  ' Private data.  
  Private ConMgr As ConnectionManager  
  
  ' Class definition for OLE DB provider.  
  Public Sub CreateOLEDBConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("OLEDB")  
    ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" & _  
      "Data Source=(local);"  
    ConMgr.Name = "SSIS Connection Manager for OLE DB"  
    ConMgr.Description = "OLE DB connection to the AdventureWorks database."  
  End Sub  
  
  Public Sub CreateFileConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("File")  
    ConMgr.ConnectionString = "\\<yourserver>\<yourfolder>\books.xml"  
    ConMgr.Name = "SSIS Connection Manager for Files"  
    ConMgr.Description = "Flat File connection"  
  End Sub  
  
End Class  
```  
  
 <span data-ttu-id="9f0da-161">**Salida del ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="9f0da-161">**Sample Output:**</span></span>  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Number of connections in package: 2`  
  
## <a name="external-resources"></a><span data-ttu-id="9f0da-162">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="9f0da-162">External Resources</span></span>  
 <span data-ttu-id="9f0da-163">Artículo técnico, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743) (Cadenas de conexión), en carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="9f0da-163">Technical article, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), on carlprothman.net.</span></span>  
  
<span data-ttu-id="9f0da-164">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9f0da-164">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9f0da-165">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="9f0da-165">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9f0da-166">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="9f0da-166">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9f0da-167">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="9f0da-167">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0da-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f0da-168">See Also</span></span>  
 <span data-ttu-id="9f0da-169">[Integration Services &#40;SSIS&#41; conexiones](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="9f0da-169">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="9f0da-170">Crear administradores de conexiones</span><span class="sxs-lookup"><span data-stu-id="9f0da-170">Create Connection Managers</span></span>](../create-connection-managers.md)  
  
  
