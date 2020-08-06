---
title: Crear una cadena de conexión válida con TCP/IP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine]
- ports [SQL Server], connecting to
- TCP/IP [SQL Server], connection strings
- connection strings [Database Engine], TCP/IP
- aliases [SQL Server], TCP/IP
ms.assetid: ee5dbc2c-1fc6-42bd-bdf5-efa792557934
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f761fa86ec4ed09c13bf4807489754c10b979ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672336"
---
# <a name="creating-a-valid-connection-string-using-tcp-ip"></a><span data-ttu-id="39e41-102">Crear una cadena de conexión válida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="39e41-102">Creating a Valid Connection String Using TCP IP</span></span>
  <span data-ttu-id="39e41-103">Para crear una cadena de conexión válida con TCP/IP, debe:</span><span class="sxs-lookup"><span data-stu-id="39e41-103">To create a valid connection string using TCP/IP, you must:</span></span>  
  
-   <span data-ttu-id="39e41-104">Especifique un **Nombre de alias**.</span><span class="sxs-lookup"><span data-stu-id="39e41-104">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="39e41-105">En el cuadro **Servidor**, escriba un nombre de servidor al que se pueda conectar con la herramienta **PING** , o bien una dirección IP a la que se pueda conectar con la herramienta **PING** .</span><span class="sxs-lookup"><span data-stu-id="39e41-105">For the **Server**, enter either a server name to which you can connect using the **PING** utility, or an IP address to which you can connect using the **PING** utility.</span></span> <span data-ttu-id="39e41-106">Para una instancia con nombre, incluya el nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="39e41-106">For a named instance append the instance name.</span></span>  
  
-   <span data-ttu-id="39e41-107">Especifique **TCP/IP** como el **Protocolo**.</span><span class="sxs-lookup"><span data-stu-id="39e41-107">Specify **TCP/IP** for the **Protocol**.</span></span>  
  
-   <span data-ttu-id="39e41-108">Opcionalmente, especifique un nombre de puerto en **Nº de puerto**.</span><span class="sxs-lookup"><span data-stu-id="39e41-108">Optionally, enter a port number for the **Port No**.</span></span> <span data-ttu-id="39e41-109">El valor predeterminado es 1433, que es el número de puerto de la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en un servidor.</span><span class="sxs-lookup"><span data-stu-id="39e41-109">The default is 1433, which is the port number of the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a server.</span></span> <span data-ttu-id="39e41-110">Para conectarse a una instancia con nombre o una instancia predeterminada que no escuche en el puerto 1433, debe proporcionar un número de puerto o iniciar el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39e41-110">To connect to a named instance or a default instance that is not listening on port 1433, you must provide the port number, or start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span> <span data-ttu-id="39e41-111">Para más información sobre la configuración del servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [Servicio SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="39e41-111">For information on configuring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service, see [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="39e41-112">En el momento de la conexión, el componente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client lee los valores de servidor, protocolo y puerto del Registro para el nombre de alias especificado, y crea una cadena de conexión con el formato `tcp:<servername>[\<instancename>],<port>` o `tcp:<IPAddress>[\<instancename>],<port>`.</span><span class="sxs-lookup"><span data-stu-id="39e41-112">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and port values from the registry for the specified alias name, and creates a connection string in the format `tcp:<servername>[\<instancename>],<port>` or `tcp:<IPAddress>[\<instancename>],<port>`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39e41-113">De forma predeterminada, el Firewall de Windows de [!INCLUDE[msCoName](../../includes/msconame-md.md)] cierra el puerto 1433.</span><span class="sxs-lookup"><span data-stu-id="39e41-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 1433 by default.</span></span> <span data-ttu-id="39e41-114">Dado que [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se comunica a través del puerto 1433, debe volver a abrir el puerto si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se configura para escuchar las conexiones de cliente entrantes que usan TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="39e41-114">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 1433, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using TCP/IP.</span></span> <span data-ttu-id="39e41-115">Para obtener más información acerca de cómo configurar un firewall, vea “Cómo configurar un firewall para el acceso a SQL Server” en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o revise la documentación del firewall.</span><span class="sxs-lookup"><span data-stu-id="39e41-115">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="39e41-116">y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client son totalmente compatibles con el Protocolo de Internet versión 4 (IPv4) y con el Protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="39e41-116">and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fully support both Internet Protocol version 4 (IPv4) and Internet Protocol version 6 (IPv6).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="39e41-117">acepta los formatos de IPv4 e IPv6 para direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="39e41-117">Configuration Manager accepts both IPv4 and IPv6 formats for IP addresses.</span></span> <span data-ttu-id="39e41-118">Para obtener más información sobre IPv6, vea el tema sobre la conexión mediante IPv6 en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39e41-118">For information on IPv6, see "Connecting Using IPv6" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="39e41-119">Conectarse al servidor local</span><span class="sxs-lookup"><span data-stu-id="39e41-119">Connecting to the Local Server</span></span>  
 <span data-ttu-id="39e41-120">Al conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se ejecuta en el mismo equipo que el cliente, puede utilizar `(local)` como el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="39e41-120">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)` as the server name.</span></span> <span data-ttu-id="39e41-121">Esta posibilidad no se recomienda ya que genera ambigüedad, pero puede ser útil cuando se sabe que el cliente se ejecuta en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="39e41-121">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="39e41-122">Por ejemplo, al crear una aplicación para usuarios desconectados móviles, como puede ser el personal de ventas, en la que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecutará en equipos portátiles y se almacenarán datos de proyectos, un cliente que se conecte a `(local)` siempre se conectará al servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta en el equipo portátil.</span><span class="sxs-lookup"><span data-stu-id="39e41-122">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to `(local)` would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="39e41-123">En lugar de `localhost` , es posible usar la palabra**o un punto (** . `(local)`).</span><span class="sxs-lookup"><span data-stu-id="39e41-123">The word `localhost` or a period (**.**) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="39e41-124">Comprobar el protocolo de conexión</span><span class="sxs-lookup"><span data-stu-id="39e41-124">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="39e41-125">La siguiente consulta devolverá el protocolo utilizado para la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="39e41-125">The following query returns the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="39e41-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="39e41-126">Examples</span></span>  
 <span data-ttu-id="39e41-127">Conectarse por el nombre de servidor:</span><span class="sxs-lookup"><span data-stu-id="39e41-127">Connecting by server name:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="39e41-128">Conectarse por el nombre de servidor a una instancia con nombre:</span><span class="sxs-lookup"><span data-stu-id="39e41-128">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>\<instancename>  
  
```  
  
 <span data-ttu-id="39e41-129">Conectarse por el nombre de servidor a un puerto especificado:</span><span class="sxs-lookup"><span data-stu-id="39e41-129">Connecting by server name to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="39e41-130">Conectarse por la dirección IP:</span><span class="sxs-lookup"><span data-stu-id="39e41-130">Connecting by IP address:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="39e41-131">Conectarse mediante la dirección IP a una instancia con nombre:</span><span class="sxs-lookup"><span data-stu-id="39e41-131">Connecting by IP address to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>\<instancename>  
  
```  
  
 <span data-ttu-id="39e41-132">Conectarse mediante la dirección IP a un puerto especificado:</span><span class="sxs-lookup"><span data-stu-id="39e41-132">Connecting by IP address to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port number>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="39e41-133">Conectarse al equipo local utilizando `(local)`:</span><span class="sxs-lookup"><span data-stu-id="39e41-133">Connecting to the local computer using `(local)`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             (local)  
  
```  
  
 <span data-ttu-id="39e41-134">Conectarse al equipo local utilizando `localhost`:</span><span class="sxs-lookup"><span data-stu-id="39e41-134">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost  
  
```  
  
 <span data-ttu-id="39e41-135">Conectarse a una instancia con nombre en el equipo local utilizando `localhost`:</span><span class="sxs-lookup"><span data-stu-id="39e41-135">Connecting to a named instance on the local computer `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost\<instancename>  
  
```  
  
 <span data-ttu-id="39e41-136">Conectarse al equipo local utilizando un punto:</span><span class="sxs-lookup"><span data-stu-id="39e41-136">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .  
  
```  
  
 <span data-ttu-id="39e41-137">Conectarse a una instancia con nombre en el equipo local usando un punto:</span><span class="sxs-lookup"><span data-stu-id="39e41-137">Connecting to a named instance on the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .\<instancename>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="39e41-138">Para más información sobre la especificación del protocolo de red como un parámetro **sqlcmd** , vea "Cómo conectarse al motor de base de datos mediante sqlcmd.exe" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39e41-138">For information on specifying the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e41-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39e41-139">See Also</span></span>  
 <span data-ttu-id="39e41-140">[Crear una cadena de conexión válida con el protocolo de memoria compartida](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="39e41-140">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="39e41-141">[Crear una cadena de conexión válida con canalizaciones con nombre](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="39e41-141">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="39e41-142">Elegir un protocolo de red</span><span class="sxs-lookup"><span data-stu-id="39e41-142">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
