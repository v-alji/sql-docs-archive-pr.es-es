---
title: Implementación de extremos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- endpoints [SMO]
ms.assetid: f8674dbb-9bc0-488f-9def-e9e0ce1ddf86
author: stevestein
ms.author: sstein
ms.openlocfilehash: 293a661c6e1ad6f6139e30e0824e99686af98f90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749203"
---
# <a name="implementing-endpoints"></a><span data-ttu-id="b9e4c-102">Implementar extremos</span><span class="sxs-lookup"><span data-stu-id="b9e4c-102">Implementing Endpoints</span></span>
  <span data-ttu-id="b9e4c-103">Un extremo es un servicio que puede escuchar originalmente las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-103">An endpoint is a service that can listen natively for requests.</span></span> <span data-ttu-id="b9e4c-104">SMO admite varios tipos de extremos utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-104">SMO supports various types of endpoints by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object.</span></span> <span data-ttu-id="b9e4c-105">Puede crear un servicio de extremos que administre un tipo específico de carga útil, que utiliza un protocolo concreto, creando una instancia de un objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint> y estableciendo sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-105">You can create an endpoint service that handles a specific type of payload, which uses a specific protocol, by creating an instance of an <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object and setting its properties.</span></span>  
  
 <span data-ttu-id="b9e4c-106">La propiedad <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint> puede utilizarse para especificar los siguientes tipos de carga:</span><span class="sxs-lookup"><span data-stu-id="b9e4c-106">The <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object can be used to specify on of the following payload types:</span></span>  
  
-   <span data-ttu-id="b9e4c-107">Creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="b9e4c-107">Database mirroring</span></span>  
  
-   <span data-ttu-id="b9e4c-108">SOAP (la compatibilidad con los extremos SOAP se encuentra en [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] y versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="b9e4c-108">SOAP (support for SOAP endpoints is present in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] and earlier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] versions)</span></span>  
  
-   <span data-ttu-id="b9e4c-109">Service Broker</span><span class="sxs-lookup"><span data-stu-id="b9e4c-109">Service Broker</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]  
  
 <span data-ttu-id="b9e4c-110">Asimismo, la propiedad <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> puede utilizarse para especificar los dos protocolos admitidos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9e4c-110">Also, the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property can be used to specify the following two supported protocols:</span></span>  
  
-   <span data-ttu-id="b9e4c-111">Protocolo HTTP</span><span class="sxs-lookup"><span data-stu-id="b9e4c-111">HTTP protocol</span></span>  
  
-   <span data-ttu-id="b9e4c-112">Protocolo TCP</span><span class="sxs-lookup"><span data-stu-id="b9e4c-112">TCP protocol</span></span>  
  
 <span data-ttu-id="b9e4c-113">Si ha especificado el tipo de carga útil, la carga útil real se puede establecer utilizando la propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A>.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-113">Having specified the type of payload, the actual payload can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> object property.</span></span> <span data-ttu-id="b9e4c-114">La propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.Payload> proporciona una referencia a un objeto de carga útil del tipo especificado, para el que se pueden modificar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-114">The <xref:Microsoft.SqlServer.Management.Smo.Payload> object property provides a reference to a payload object of the specified type, for which the properties can be modified.</span></span>  
  
 <span data-ttu-id="b9e4c-115">Para el objeto <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload>, debe especificar el rol de creación de reflejo y si el cifrado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-115">For the <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> object, you must specify the mirroring role and whether encryption is enabled.</span></span> <span data-ttu-id="b9e4c-116">El objeto <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> requiere información sobre el reenvío de mensajes, el número máximo de conexiones permitido y el modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-116">The <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> object requires information about message forwarding, maximum number of connections allowed and the authentication mode.</span></span> <span data-ttu-id="b9e4c-117">El objeto <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> exige establecer varias propiedades incluida la propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A>, que especifica los métodos de carga útil de SOAP disponibles para los clientes (procedimientos almacenados y funciones definidas por el usuario).</span><span class="sxs-lookup"><span data-stu-id="b9e4c-117">The <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> object requires various properties to be set including the <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> object property that specifies the SOAP payload methods available to clients (stored procedures and user-defined functions).</span></span>  
  
 <span data-ttu-id="b9e4c-118">De igual forma, el protocolo actual se puede establecer utilizando la propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> que hace referencia a un objeto de protocolo del tipo especificado por propiedad <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-118">Similarly, the actual protocol can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> object property that references a protocol object of the type specified by <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property.</span></span> <span data-ttu-id="b9e4c-119">El objeto <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> requiere una lista de direcciones IP restringidas y la información sobre el puerto, sitio web y autenticación.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-119">The <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> object requires a list of restricted IP addresses, and port, website, and authentication information.</span></span> <span data-ttu-id="b9e4c-120">El objeto <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> también requiere una lista de direcciones IP restringidas e información de puerto.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-120">The <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> object also requires a list of restricted IP addresses and port information.</span></span>  
  
 <span data-ttu-id="b9e4c-121">Si se ha creado el extremo y se ha definido totalmente, se puede conceder, revocar y denegar el acceso a los usuarios de la base de datos, grupos, roles e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-121">When the endpoint has been created and fully defined, access can be granted to, revoked from, and denied to database users, groups, roles, and logons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9e4c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9e4c-122">Example</span></span>  
 <span data-ttu-id="b9e4c-123">Para el siguiente ejemplo de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-123">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="b9e4c-124">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="b9e4c-124">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-basic"></a><span data-ttu-id="b9e4c-125">Crear un servicio de extremo de creación de reflejo de base de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9e4c-125">Creating a Database Mirroring Endpoint Service in Visual Basic</span></span>  
 <span data-ttu-id="b9e4c-126">En el ejemplo de código se muestra cómo crear un extremo de creación de reflejo de base de datos en SMO.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-126">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="b9e4c-127">Esto es necesario antes de crear un espejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-127">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="b9e4c-128">Utilice <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> y otras propiedades en el objeto <xref:Microsoft.SqlServer.Management.Smo.Database> para crear un espejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-128">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEndpoints1](SMO How to#SMO_VBEndpoints1)]  -->  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-c"></a><span data-ttu-id="b9e4c-129">Crear un servicio de extremo de creación de reflejo de base de datos en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b9e4c-129">Creating a Database Mirroring Endpoint Service in Visual C#</span></span>  
 <span data-ttu-id="b9e4c-130">En el ejemplo de código se muestra cómo crear un extremo de creación de reflejo de base de datos en SMO.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-130">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="b9e4c-131">Esto es necesario antes de crear un espejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-131">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="b9e4c-132">Utilice <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> y otras propiedades en el objeto <xref:Microsoft.SqlServer.Management.Smo.Database> para crear un espejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-132">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```csharp
{  
            //Set up a database mirroring endpoint on the server before   
        //setting up a database mirror.   
        //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Define an Endpoint object variable for database mirroring.   
            Endpoint ep = default(Endpoint);  
            ep = new Endpoint(srv, "Mirroring_Endpoint");  
            ep.ProtocolType = ProtocolType.Tcp;  
            ep.EndpointType = EndpointType.DatabaseMirroring;  
            //Specify the protocol ports.   
            ep.Protocol.Http.SslPort = 5024;  
            ep.Protocol.Tcp.ListenerPort = 6666;  
            //Specify the role of the payload.   
            ep.Payload.DatabaseMirroring.ServerMirroringRole = ServerMirroringRole.All;  
            //Create the endpoint on the instance of SQL Server.   
            ep.Create();  
            //Start the endpoint.   
            ep.Start();  
            Console.WriteLine(ep.EndpointState);  
        }  
```  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-powershell"></a><span data-ttu-id="b9e4c-133">Crear un servicio de extremo de creación de reflejo de la base de datos en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9e4c-133">Creating a Database Mirroring Endpoint Service in PowerShell</span></span>  
 <span data-ttu-id="b9e4c-134">En el ejemplo de código se muestra cómo crear un extremo de creación de reflejo de base de datos en SMO.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-134">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="b9e4c-135">Esto es necesario antes de crear un espejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-135">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="b9e4c-136">Utilice <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> y otras propiedades en el objeto <xref:Microsoft.SqlServer.Management.Smo.Database> para crear un espejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9e4c-136">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get a new endpoint to congure and add  
$ep = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Endpoint -argumentlist $srv,"Mirroring_Endpoint"  
  
#Set some properties  
$ep.ProtocolType = [Microsoft.SqlServer.Management.SMO.ProtocolType]::Tcp  
$ep.EndpointType = [Microsoft.SqlServer.Management.SMO.EndpointType]::DatabaseMirroring  
$ep.Protocol.Http.SslPort = 5024  
$ep.Protocol.Tcp.ListenerPort = 6666 #inline comment  
$ep.Payload.DatabaseMirroring.ServerMirroringRole = [Microsoft.SqlServer.Management.SMO.ServerMirroringRole]::All  
  
# Create the endpoint on the instance  
$ep.Create()  
  
# Start the endpoint  
$ep.Start()  
  
# Report its state  
$ep.EndpointState;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9e4c-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9e4c-137">See Also</span></span>  
 [<span data-ttu-id="b9e4c-138">El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9e4c-138">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
