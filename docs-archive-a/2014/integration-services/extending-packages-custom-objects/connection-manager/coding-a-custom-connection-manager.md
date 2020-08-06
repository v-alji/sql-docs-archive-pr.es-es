---
title: Programar un administrador de conexiones personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], coding
ms.assetid: b12b6778-1f01-4a7d-984d-73f2f7630aa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 793d70ba0a9ae6176ab35c82e16b9aba8c9ba2cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748192"
---
# <a name="coding-a-custom-connection-manager"></a><span data-ttu-id="dbe97-102">Codificar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="dbe97-102">Coding a Custom Connection Manager</span></span>
  <span data-ttu-id="dbe97-103">Una vez que haya creado una clase que herede de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> y haya aplicado el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> a la clase, debe invalidar la implementación de las propiedades y los métodos de la clase base para proporcionar su funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="dbe97-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="dbe97-104">Para obtener ejemplos de administradores de conexiones personalizados, consulte [Desarrollar una interfaz de usuario para un administrador de conexiones personalizado](developing-a-user-interface-for-a-custom-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dbe97-104">For samples of custom connection managers, see [Developing a User Interface for a Custom Connection Manager](developing-a-user-interface-for-a-custom-connection-manager.md).</span></span> <span data-ttu-id="dbe97-105">Los ejemplos de código mostrados en este tema se deducen del ejemplo de administrador de conexiones personalizado de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dbe97-105">The code examples shown in this topic are drawn from the SQL Server Custom Connection Manager sample.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbe97-106">Muchas de las tareas, orígenes y destinos que se han incluido en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] se usan únicamente con tipos específicos de administradores de conexiones integrados.</span><span class="sxs-lookup"><span data-stu-id="dbe97-106">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="dbe97-107">Por consiguiente, estos ejemplos no se pueden probar con las tareas y componentes integrados.</span><span class="sxs-lookup"><span data-stu-id="dbe97-107">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="configuring-the-connection-manager"></a><span data-ttu-id="dbe97-108">Configurar el administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="dbe97-108">Configuring the Connection Manager</span></span>  
  
### <a name="setting-the-connectionstring-property"></a><span data-ttu-id="dbe97-109">Establecer la propiedad ConnectionString</span><span class="sxs-lookup"><span data-stu-id="dbe97-109">Setting the ConnectionString Property</span></span>  
 <span data-ttu-id="dbe97-110">La propiedad <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> es una propiedad importante y la única propiedad para un administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbe97-110">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property is an important property and the only property unique to a custom connection manager.</span></span> <span data-ttu-id="dbe97-111">El administrador de conexiones usa el valor de esta propiedad para conectar al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="dbe97-111">The connection manager uses the value of this property to connect to the external data source.</span></span> <span data-ttu-id="dbe97-112">Si combina varias propiedades, como nombre de servidor y nombre de base de datos, para crear la cadena de conexión, puede usar una función del asistente para ensamblar la cadena reemplazando ciertos valores en una plantilla de cadena de conexión con el nuevo valor que proporciona el usuario.</span><span class="sxs-lookup"><span data-stu-id="dbe97-112">If you are combining several other properties, such as server name and database name, to create the connection string, you can use a helper function to assemble the string by replacing certain values in a connection string template with the new value supplied by the user.</span></span> <span data-ttu-id="dbe97-113">En el ejemplo de código siguiente se muestra una implementación de la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> que confía en una función del asistente para ensamblar la cadena.</span><span class="sxs-lookup"><span data-stu-id="dbe97-113">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property that relies on a helper function to assemble the string.</span></span>  
  
```vb  
' Default values.  
Private _serverName As String = "(local)"  
Private _databaseName As String = "AdventureWorks"  
Private _connectionString As String = String.Empty  
  
Private Const CONNECTIONSTRING_TEMPLATE As String = _  
  "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI"  
  
Public Property ServerName() As String  
  Get  
    Return _serverName  
  End Get  
  Set(ByVal value As String)  
    _serverName = value  
  End Set  
End Property  
  
Public Property DatabaseName() As String  
  Get  
    Return _databaseName  
  End Get  
  Set(ByVal value As String)  
    _databaseName = value  
  End Set  
End Property  
  
Public Overrides Property ConnectionString() As String  
  Get  
    UpdateConnectionString()  
    Return _connectionString  
  End Get  
  Set(ByVal value As String)  
    _connectionString = value  
  End Set  
End Property  
  
Private Sub UpdateConnectionString()  
  
  Dim temporaryString As String = CONNECTIONSTRING_TEMPLATE  
  
  If Not String.IsNullOrEmpty(_serverName) Then  
    temporaryString = temporaryString.Replace("<servername>", _serverName)  
  End If  
  If Not String.IsNullOrEmpty(_databaseName) Then  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName)  
  End If  
  
  _connectionString = temporaryString  
  
End Sub  
```  
  
```csharp  
// Default values.  
private string _serverName = "(local)";  
private string _databaseName = "AdventureWorks";  
private string _connectionString = String.Empty;  
  
private const string CONNECTIONSTRING_TEMPLATE = "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI";  
  
public string ServerName  
{  
  get  
  {  
    return _serverName;  
  }  
  set  
  {  
    _serverName = value;  
  }  
}  
  
public string DatabaseName  
{  
  get  
  {  
    return _databaseName;  
  }  
  set  
  {  
    _databaseName = value;  
  }  
}  
  
public override string ConnectionString  
{  
  get  
  {  
    UpdateConnectionString();  
    return _connectionString;  
  }  
  set  
  {  
    _connectionString = value;  
  }  
}  
  
private void UpdateConnectionString()  
{  
  
  string temporaryString = CONNECTIONSTRING_TEMPLATE;  
  
  if (!String.IsNullOrEmpty(_serverName))  
  {  
    temporaryString = temporaryString.Replace("<servername>", _serverName);  
  }  
  
  if (!String.IsNullOrEmpty(_databaseName))  
  {  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName);  
  }  
  
  _connectionString = temporaryString;  
  
}  
```  
  
### <a name="validating-the-connection-manager"></a><span data-ttu-id="dbe97-114">Validar el administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="dbe97-114">Validating the Connection Manager</span></span>  
 <span data-ttu-id="dbe97-115">Invalide el método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> para asegurarse de que el administrador de conexiones se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbe97-115">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method to make sure that the connection manager has been configured correctly.</span></span> <span data-ttu-id="dbe97-116">Como mínimo, debería validar el formato de la cadena de conexión y asegurarse de que se han proporcionado valores para todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="dbe97-116">At a minimum, you should validate the format of the connection string and make sure that values have been provided for all arguments.</span></span> <span data-ttu-id="dbe97-117">La ejecución no puede continuar hasta que el administrador de conexiones no devuelva <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> en el método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbe97-117">Execution cannot continue until the connection manager returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="dbe97-118">En el siguiente ejemplo de código se muestra una implementación de <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> que asegura que el usuario ha especificado un nombre de servidor para la conexión.</span><span class="sxs-lookup"><span data-stu-id="dbe97-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> that makes sure that the user has specified a server name for the connection.</span></span>  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  If String.IsNullOrEmpty(_serverName) Then  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0)  
    Return DTSExecResult.Failure  
  Else  
    Return DTSExecResult.Success  
  End If  
  
End Function  
```  
  
```csharp  
public override Microsoft.SqlServer.Dts.Runtime.DTSExecResult Validate(Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  if (String.IsNullOrEmpty(_serverName))  
  {  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0);  
    return DTSExecResult.Failure;  
  }  
  else  
  {  
    return DTSExecResult.Success;  
  }  
  
}  
```  
  
### <a name="persisting-the-connection-manager"></a><span data-ttu-id="dbe97-119">Conservar el administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="dbe97-119">Persisting the Connection Manager</span></span>  
 <span data-ttu-id="dbe97-120">Normalmente, no tiene que implementar la persistencia personalizada para un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="dbe97-120">Usually, you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="dbe97-121">Solo se requiere la persistencia personalizada cuando las propiedades de un objeto usan tipos de datos complejos.</span><span class="sxs-lookup"><span data-stu-id="dbe97-121">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="dbe97-122">Para obtener más información, vea [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) (Desarrollar objetos personalizados para Integration Services).</span><span class="sxs-lookup"><span data-stu-id="dbe97-122">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="working-with-the-external-data-source"></a><span data-ttu-id="dbe97-123">Trabajar con el origen de datos externos</span><span class="sxs-lookup"><span data-stu-id="dbe97-123">Working with the External Data Source</span></span>  
 <span data-ttu-id="dbe97-124">Los métodos que permiten conectar a un origen de datos externo son los métodos más importantes de un administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbe97-124">The methods that support connecting to an external data source are the most important methods of a custom connection manager.</span></span> <span data-ttu-id="dbe97-125">Se llama varias veces a los métodos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> durante tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dbe97-125">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods are called at various times during both design time and run time.</span></span>  
  
### <a name="acquiring-the-connection"></a><span data-ttu-id="dbe97-126">Adquirir la conexión</span><span class="sxs-lookup"><span data-stu-id="dbe97-126">Acquiring the Connection</span></span>  
 <span data-ttu-id="dbe97-127">Debe decidir el tipo de objeto que es el adecuado para devolver el método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> de su administrador de conexiones personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbe97-127">You need to decide what type of object it is appropriate for the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method to return from your custom connection manager.</span></span> <span data-ttu-id="dbe97-128">Por ejemplo, un administrador de conexiones de archivos devuelve únicamente una cadena que contiene una ruta y nombre de archivo, mientras que una conexión ADO.NET devuelve un objeto de conexión administrado que ya está abierto.</span><span class="sxs-lookup"><span data-stu-id="dbe97-128">For example, a File connection manager returns only a string that contains a path and filename, whereas an ADO.NET connection manager returns a managed connection object that is already open.</span></span> <span data-ttu-id="dbe97-129">Un administrador de conexiones OLE DB devuelve un objeto de conexión OLE DB nativo que el código administrado no puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="dbe97-129">An OLE DB connection manager returns a native OLE DB connection object that cannot be used from managed code.</span></span> <span data-ttu-id="dbe97-130">El administrador de conexiones SQL Server personalizado, del que se toman los fragmentos de código en este tema, devuelve un objeto `SqlConnection` abierto.</span><span class="sxs-lookup"><span data-stu-id="dbe97-130">The custom SQL Server connection manager, from which the code snippets in this topic are taken, returns an open `SqlConnection` object.</span></span>  
  
 <span data-ttu-id="dbe97-131">Los usuarios de su administrador de conexiones necesitan conocer de antemano el tipo de objeto que se espera, para que puedan convertir el objeto devuelto al tipo adecuado y obtener acceso sus métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="dbe97-131">Users of your connection manager need to know in advance what type of object to expect, so that they can cast the returned object to the appropriate type and access its methods and properties.</span></span>  
  
```vb  
Public Overrides Function AcquireConnection(ByVal txn As Object) As Object  
  
  Dim sqlConnection As New SqlConnection  
  
  UpdateConnectionString()  
  
  With sqlConnection  
    .ConnectionString = _connectionString  
    .Open()  
  End With  
  
  Return sqlConnection  
  
End Function  
```  
  
```csharp  
public override object AcquireConnection(object txn)  
{  
  
  SqlConnection sqlConnection = new SqlConnection();  
  
  UpdateConnectionString();  
  
  {  
    sqlConnection.ConnectionString = _connectionString;  
    sqlConnection.Open();  
  }  
  
  return sqlConnection;  
  
}  
```  
  
### <a name="releasing-the-connection"></a><span data-ttu-id="dbe97-132">Liberar la conexión</span><span class="sxs-lookup"><span data-stu-id="dbe97-132">Releasing the Connection</span></span>  
 <span data-ttu-id="dbe97-133">Las medidas que toma en el método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> dependen del tipo de objeto devuelto del método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbe97-133">The action that you take in the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> method depends on the type of object that you returned from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span> <span data-ttu-id="dbe97-134">Si hay un objeto de conexión abierto, debería cerrarlo y liberar cualquier recurso que se esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="dbe97-134">If there is an open connection object, you should close it and to release any resources that it is using.</span></span> <span data-ttu-id="dbe97-135">Si <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> devuelve únicamente un valor de cadena, ya no se necesita realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="dbe97-135">If <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> returned only a string value, no action needs to be taken.</span></span>  
  
```vb  
Public Overrides Sub ReleaseConnection(ByVal connection As Object)  
  
  Dim sqlConnection As SqlConnection  
  
  sqlConnection = DirectCast(connection, SqlConnection)  
  
  If sqlConnection.State <> ConnectionState.Closed Then  
    sqlConnection.Close()  
  End If  
  
End Sub  
```  
  
```csharp  
public override void ReleaseConnection(object connection)  
{  
  SqlConnection sqlConnection;  
  sqlConnection = (SqlConnection)connection;  
  if (sqlConnection.State != ConnectionState.Closed)  
    sqlConnection.Close();  
}  
```  
  
<span data-ttu-id="dbe97-136">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dbe97-136">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dbe97-137">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="dbe97-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dbe97-138">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="dbe97-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dbe97-139">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="dbe97-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe97-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbe97-140">See Also</span></span>  
 <span data-ttu-id="dbe97-141">[Crear un administrador de conexiones personalizado](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dbe97-141">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="dbe97-142">Desarrollar una interfaz de usuario para un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="dbe97-142">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
