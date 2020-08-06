---
title: Conectarse a una instancia de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, connections
- connections [SMO]
- instances of SQL Server, connections
- SMO [SQL Server], connections
ms.assetid: ad3cf354-b2e3-468b-b986-1232e375fd84
author: stevestein
ms.author: sstein
ms.openlocfilehash: efc21451f4a876c6edfe4a2389ca937d11bc5c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676992"
---
# <a name="connecting-to-an-instance-of-sql-server"></a><span data-ttu-id="598e2-102">Conectarse a una instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="598e2-102">Connecting to an Instance of SQL Server</span></span>
  <span data-ttu-id="598e2-103">El primer paso de programación en una [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aplicación de objetos de administración de (SMO) consiste en crear una instancia del <xref:Microsoft.SqlServer.Management.Smo.Server> objeto y establecer su conexión con una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="598e2-103">The first programming step in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) application is to create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and to establish its connection to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="598e2-104">Puede crear una instancia del objeto <xref:Microsoft.SqlServer.Management.Smo.Server> y establecer una conexión a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de tres maneras.</span><span class="sxs-lookup"><span data-stu-id="598e2-104">You can create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and establish a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in three ways.</span></span> <span data-ttu-id="598e2-105">La primera es utilizar una variable de objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> para proporcionar la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="598e2-105">The first is using a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable to provide the connection information.</span></span> <span data-ttu-id="598e2-106">La segunda es proporcionar la información de conexión estableciendo explícitamente las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="598e2-106">The second is to provide the connection information by explicitly setting the <xref:Microsoft.SqlServer.Management.Smo.Server> object properties.</span></span> <span data-ttu-id="598e2-107">La tercera es pasar el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en el constructor del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="598e2-107">The third is to pass the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span>  
  
 <span data-ttu-id="598e2-108">**Utilizar un objeto ServerConnection**</span><span class="sxs-lookup"><span data-stu-id="598e2-108">**Using a ServerConnection object**</span></span>  
  
 <span data-ttu-id="598e2-109">La ventaja de utilizar la variable de objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> es que se puede reutilizar la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="598e2-109">The advantage of using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable is that the connection information can be reused.</span></span> <span data-ttu-id="598e2-110">Declare una variable de objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="598e2-110">Declare a <xref:Microsoft.SqlServer.Management.Smo.Server> object variable.</span></span> <span data-ttu-id="598e2-111">A continuación, declare un objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> y establezca las propiedades con información de conexión como el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y el modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="598e2-111">Then, declare a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object and set properties with connection information such as the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and the authentication mode.</span></span> <span data-ttu-id="598e2-112">A continuación, pase la variable de objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> como parámetro al constructor de objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="598e2-112">Then, pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable as a parameter to the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span> <span data-ttu-id="598e2-113">No se recomienda compartir a la vez las conexiones entre objetos de servidor distintos.</span><span class="sxs-lookup"><span data-stu-id="598e2-113">It is not recommended to share connections between different server objects at the same time.</span></span> <span data-ttu-id="598e2-114">Utilice el método <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> para obtener una copia de los valores de conexión existentes.</span><span class="sxs-lookup"><span data-stu-id="598e2-114">Use the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to get a copy of the existing connection settings.</span></span>  
  
 <span data-ttu-id="598e2-115">**Establecer explícitamente las propiedades del objeto Server**</span><span class="sxs-lookup"><span data-stu-id="598e2-115">**Setting Server object properties explicitly**</span></span>  
  
 <span data-ttu-id="598e2-116">De modo alternativo, puede declarar la variable de objeto <xref:Microsoft.SqlServer.Management.Smo.Server> y llamar al constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="598e2-116">Alternatively, you can declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and call the default constructor.</span></span> <span data-ttu-id="598e2-117">Tal cual, el objeto <xref:Microsoft.SqlServer.Management.Smo.Server> intenta conectarse a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con todos los valores de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="598e2-117">As is, the <xref:Microsoft.SqlServer.Management.Smo.Server> object tries to connect to the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with all the default connection settings.</span></span>  
  
 <span data-ttu-id="598e2-118">**Proporcionar el nombre de la instancia de SQL Server en el constructor de objeto Server**</span><span class="sxs-lookup"><span data-stu-id="598e2-118">**Providing the SQL Server instance name in the Server object constructor**</span></span>  
  
 <span data-ttu-id="598e2-119">Declare la variable de objeto <xref:Microsoft.SqlServer.Management.Smo.Server> y pase el nombre de instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como parámetro de cadena en el constructor.</span><span class="sxs-lookup"><span data-stu-id="598e2-119">Declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and pass the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance name as a string parameter in the constructor.</span></span> <span data-ttu-id="598e2-120">El objeto <xref:Microsoft.SqlServer.Management.Smo.Server> establece una conexión con la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con los valores de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="598e2-120">The <xref:Microsoft.SqlServer.Management.Smo.Server> object establishes a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the default connection settings.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="598e2-121">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="598e2-121">Connection Pooling</span></span>  
 <span data-ttu-id="598e2-122">No se requiere normalmente llamar al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> del objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="598e2-122">It is typically not required to call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="598e2-123">SMO establecerá automáticamente una conexión cuando sea necesario y liberará la conexión al grupo de conexiones después de haber terminado de realizar las operaciones.</span><span class="sxs-lookup"><span data-stu-id="598e2-123">SMO will automatically establish a connection when required, and release the connection to the connection pool after it has finished performing operations.</span></span> <span data-ttu-id="598e2-124">Cuando se llama al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>, no se libera la conexión al grupo.</span><span class="sxs-lookup"><span data-stu-id="598e2-124">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not released to the pool.</span></span> <span data-ttu-id="598e2-125">Es necesaria una llamada explícita al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> para liberar la conexión al grupo.</span><span class="sxs-lookup"><span data-stu-id="598e2-125">An explicit call to the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method is required to release the connection to the pool.</span></span> <span data-ttu-id="598e2-126">Además, puede solicitar una conexión no agrupada estableciendo la propiedad <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> del objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="598e2-126">Additionally, you can request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="multithreaded-applications"></a><span data-ttu-id="598e2-127">Aplicaciones multiproceso</span><span class="sxs-lookup"><span data-stu-id="598e2-127">Multithreaded Applications</span></span>  
 <span data-ttu-id="598e2-128">Para las aplicaciones multiproceso, se debe utilizar un objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> independiente en cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="598e2-128">For multithreaded applications, a separate <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object should be used in each thread.</span></span>  
  
## <a name="connecting-to-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="598e2-129">Conectarse a una instancia de SQL Server para RMO</span><span class="sxs-lookup"><span data-stu-id="598e2-129">Connecting to an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="598e2-130">Replication Management Objects (RMO) usa un método ligeramente distinto de SMO para conectarse a un servidor de replicación.</span><span class="sxs-lookup"><span data-stu-id="598e2-130">Replication Management Objects (RMO) uses a slightly different method from SMO to connect to a replication server.</span></span>  
  
 <span data-ttu-id="598e2-131">Los objetos de programación RMO requieren que se realice una conexión a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizando el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> implementado por el espacio de nombres `Microsoft.SqlServer.Management.Common`.</span><span class="sxs-lookup"><span data-stu-id="598e2-131">RMO programming objects require that a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is made by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object implemented by the `Microsoft.SqlServer.Management.Common` namespace.</span></span> <span data-ttu-id="598e2-132">Esta conexión al servidor se realiza independientemente de los objetos de programación RMO.</span><span class="sxs-lookup"><span data-stu-id="598e2-132">This connection to the server is made independently of an RMO programming object.</span></span> <span data-ttu-id="598e2-133">A continuación, se pasa al objeto RMO durante la creación de la instancia o por asignación a la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> del objeto.</span><span class="sxs-lookup"><span data-stu-id="598e2-133">It is then it is passed to the RMO object either during instance creation or by assignment to the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the object.</span></span> <span data-ttu-id="598e2-134">De esta manera, se pueden crear y administrar los objetos de programación RMO y las instancias de objeto de conexión por separado y se puede reutilizar un objeto de conexión único con varios objetos de programación RMO.</span><span class="sxs-lookup"><span data-stu-id="598e2-134">In this manner, an RMO programming object and the connection object instances can be created and managed separately, and a single connection object can be reused with multiple RMO programming objects.</span></span> <span data-ttu-id="598e2-135">Las reglas siguientes se aplican a las conexiones a un servidor de replicación:</span><span class="sxs-lookup"><span data-stu-id="598e2-135">The following rules apply for connections to a replication server:</span></span>  
  
-   <span data-ttu-id="598e2-136">Todas las propiedades de la conexión se definen para un objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> especificado.</span><span class="sxs-lookup"><span data-stu-id="598e2-136">All properties for the connection are defined for a specified <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="598e2-137">Cada conexión a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] debe tener su propio objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="598e2-137">Each connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must have its own <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="598e2-138">Toda la información de autenticación para realizar la conexión e iniciar sesión en el servidor correctamente se proporciona en el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="598e2-138">All authentication information to make the connection and successfully log on to the server is supplied in the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="598e2-139">De forma predeterminada, las conexiones se realizan mediante la autenticación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="598e2-139">By default, connections are made by using Microsoft Windows Authentication.</span></span> <span data-ttu-id="598e2-140">Para utilizar la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> debe estar establecido en False y <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> y <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> deben estar establecidos en un inicio de sesión y contraseña de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] válidos.</span><span class="sxs-lookup"><span data-stu-id="598e2-140">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> must be set to False and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> must be set to a valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logon and password.</span></span> <span data-ttu-id="598e2-141">Las credenciales de seguridad deben estar almacenadas y administradas de forma segura siempre y proporcionarse en tiempo de ejecución siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="598e2-141">Security credentials must always be stored and handled securely, and supplied at run time whenever possible.</span></span>  
  
-   <span data-ttu-id="598e2-142">Se debe llamar al método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> antes de pasar la conexión a cualquier objeto de programación RMO.</span><span class="sxs-lookup"><span data-stu-id="598e2-142">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method must be called before passing the connection to any RMO programming object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="598e2-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="598e2-143">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="598e2-144">Conectarse a la instancia local de SQL Server mediante la autenticación de Windows en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598e2-144">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="598e2-145">Para conectarse a la instancia local de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no se requiere mucho código.</span><span class="sxs-lookup"><span data-stu-id="598e2-145">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="598e2-146">En su lugar, se basa en la configuración predeterminada del método de autenticación y servidor.</span><span class="sxs-lookup"><span data-stu-id="598e2-146">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="598e2-147">La primera operación que exija la recuperación de datos hará que se cree una conexión.</span><span class="sxs-lookup"><span data-stu-id="598e2-147">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="598e2-148">Este ejemplo es [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] código de .net que se conecta a la instancia local de mediante la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="598e2-148">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB1](SMO How to#SMO_VB1)]  -->  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="598e2-149">Conectarse a la instancia local de SQL Server mediante la autenticación de Windows en Visual C#</span><span class="sxs-lookup"><span data-stu-id="598e2-149">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="598e2-150">Para conectarse a la instancia local de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no se requiere mucho código.</span><span class="sxs-lookup"><span data-stu-id="598e2-150">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="598e2-151">En su lugar, se basa en la configuración predeterminada del método de autenticación y servidor.</span><span class="sxs-lookup"><span data-stu-id="598e2-151">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="598e2-152">La primera operación que exija la recuperación de datos hará que se cree una conexión.</span><span class="sxs-lookup"><span data-stu-id="598e2-152">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="598e2-153">Este ejemplo está formado por código Visual C# .NET que se conecta a la instancia local de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="598e2-153">This example is Visual C# .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//The connection is established when a property is requested.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="598e2-154">Conectarse a una instancia remota de SQL Server mediante la autenticación de Windows en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598e2-154">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="598e2-155">Al conectarse a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la autenticación de Windows, no es necesario especificar el tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="598e2-155">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="598e2-156">La autenticación de Windows es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="598e2-156">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="598e2-157">Este ejemplo es [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] código de .net que se conecta a la instancia remota de mediante la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="598e2-157">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="598e2-158">La variable de cadena *strServer* contiene el nombre de la instancia remota.</span><span class="sxs-lookup"><span data-stu-id="598e2-158">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB2](SMO How to#SMO_VB2)]  -->  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="598e2-159">Conectarse a una instancia remota de SQL Server mediante la autenticación de Windows en Visual C#</span><span class="sxs-lookup"><span data-stu-id="598e2-159">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="598e2-160">Al conectarse a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la autenticación de Windows, no es necesario especificar el tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="598e2-160">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="598e2-161">La autenticación de Windows es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="598e2-161">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="598e2-162">Este ejemplo está formado por código Visual C# .NET que se conecta a la instancia remota de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="598e2-162">This example is Visual C# .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="598e2-163">La variable de cadena *strServer* contiene el nombre de la instancia remota.</span><span class="sxs-lookup"><span data-stu-id="598e2-163">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
```  
{   
//Connect to a remote instance of SQL Server.   
Server srv;   
//The strServer string variable contains the name of a remote instance of SQL Server.   
srv = new Server(strServer);   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-basic"></a><span data-ttu-id="598e2-164">Conectarse a una instancia de SQL Server mediante la autenticación de SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598e2-164">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual Basic</span></span>  
 <span data-ttu-id="598e2-165">Al conectarse a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], debe especificar el tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="598e2-165">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="598e2-166">En este ejemplo se muestra un método alternativo para declarar una variable de objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, que permite reutilizar la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="598e2-166">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="598e2-167">El ejemplo es [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] código de .net que muestra cómo conectarse al remoto y *vPassword* contienen el inicio de sesión y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="598e2-167">The example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim sqlServerLogin As [String] = "user_id"  
      Dim password As [String] = "pwd"  
      Dim instanceName As [String] = "instance_name"  
      Dim remoteSvrName As [String] = "remote_server_name"  
  
      ' Connecting to an instance of SQL Server using SQL Server Authentication  
      Dim srv1 As New Server()   ' connects to default instance  
      srv1.ConnectionContext.LoginSecure = False   ' set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin  
      srv1.ConnectionContext.Password = password  
      Console.WriteLine(srv1.Information.Version)   ' connection is established  
  
      ' Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      Dim srvConn As New ServerConnection()  
      srvConn.ServerInstance = ".\" & instanceName   ' connects to named instance  
      srvConn.LoginSecure = False   ' set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin  
      srvConn.Password = password  
      Dim srv2 As New Server(srvConn)  
      Console.WriteLine(srv2.Information.Version)   ' connection is established  
  
      ' For remote connection, remote server name / ServerInstance needs to be specified  
      Dim srvConn2 As New ServerConnection(remoteSvrName)  
      srvConn2.LoginSecure = False  
      srvConn2.Login = sqlServerLogin  
      srvConn2.Password = password  
      Dim srv3 As New Server(srvConn2)  
      Console.WriteLine(srv3.Information.Version)   ' connection is established  
   End Sub  
End Class  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-c"></a><span data-ttu-id="598e2-168">Conectarse a una instancia de SQL Server mediante la autenticación de SQL Server en Visual C#</span><span class="sxs-lookup"><span data-stu-id="598e2-168">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual C#</span></span>  
 <span data-ttu-id="598e2-169">Al conectarse a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], debe especificar el tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="598e2-169">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="598e2-170">En este ejemplo se muestra un método alternativo para declarar una variable de objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, que permite reutilizar la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="598e2-170">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="598e2-171">El ejemplo es código de Visual C# .NET que muestra cómo conectarse al remoto y *vPassword* contienen el inicio de sesión y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="598e2-171">The example is Visual C# .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {   
      String sqlServerLogin = "user_id";  
      String password = "pwd";  
      String instanceName = "instance_name";  
      String remoteSvrName = "remote_server_name";  
  
      // Connecting to an instance of SQL Server using SQL Server Authentication  
      Server srv1 = new Server();   // connects to default instance  
      srv1.ConnectionContext.LoginSecure = false;   // set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin;  
      srv1.ConnectionContext.Password = password;  
      Console.WriteLine(srv1.Information.Version);   // connection is established  
  
      // Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      ServerConnection srvConn = new ServerConnection();  
      srvConn.ServerInstance = @".\" + instanceName;   // connects to named instance  
      srvConn.LoginSecure = false;   // set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin;  
      srvConn.Password = password;  
      Server srv2 = new Server(srvConn);  
      Console.WriteLine(srv2.Information.Version);   // connection is established  
  
      // For remote connection, remote server name / ServerInstance needs to be specified  
      ServerConnection srvConn2 = new ServerConnection(remoteSvrName);  
      srvConn2.LoginSecure = false;  
      srvConn2.Login = sqlServerLogin;  
      srvConn2.Password = password;  
      Server srv3 = new Server(srvConn2);  
      Console.WriteLine(srv3.Information.Version);   // connection is established  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="598e2-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="598e2-172">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
