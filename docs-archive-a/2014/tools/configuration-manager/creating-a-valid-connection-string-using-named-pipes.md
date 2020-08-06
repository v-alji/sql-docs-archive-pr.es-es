---
title: Crear una cadena de conexión válida con canalizaciones con nombre | Microsoft Docs
description: Obtenga información sobre cómo crear una cadena de conexión válida al usar el protocolo canalizaciones con nombre para conectarse a una instancia de SQL Server. Ver ejemplos de nombres de canalización válidos.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], named pipes
- pipes [SQL Server]
- pipes [SQL Server], connecting to
- aliases [SQL Server], named pipes
- Named Pipes [SQL Server], connection strings
ms.assetid: 90930ff2-143b-4651-8ae3-297103600e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f3e1d01e9e5b7b1d1c0d1bb822bf233ceee636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672338"
---
# <a name="creating-a-valid-connection-string-using-named-pipes"></a><span data-ttu-id="16a29-104">Crear una cadena de conexión válida con canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="16a29-104">Creating a Valid Connection String Using Named Pipes</span></span>
  <span data-ttu-id="16a29-105">A menos que el usuario lo cambie, cuando la instancia predeterminada de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha en el protocolo canalizaciones con nombre, usa `\\.\pipe\sql\query` como nombre de canalización.</span><span class="sxs-lookup"><span data-stu-id="16a29-105">Unless changed by the user, when the default instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on the named pipes protocol, it uses `\\.\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="16a29-106">El punto indica que el equipo es el equipo local, `pipe` indica que la conexión es una canalización con nombre y `sql\query` es el nombre de la canalización.</span><span class="sxs-lookup"><span data-stu-id="16a29-106">The period indicates that the computer is the local computer, `pipe` indicates that the connection is a named pipe, and `sql\query` is the name of the pipe.</span></span> <span data-ttu-id="16a29-107">Para conectarse a la canalización predeterminada, debe tener el alias `\\<computer_name>\pipe\sql\query` como el nombre de canalización.</span><span class="sxs-lookup"><span data-stu-id="16a29-107">To connect to the default pipe, the alias must have `\\<computer_name>\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="16a29-108">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ha configurado para escuchar en una canalización diferente, el nombre de canalización debe utilizar esa canalización.</span><span class="sxs-lookup"><span data-stu-id="16a29-108">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to listen on a different pipe, the pipe name must use that pipe.</span></span> <span data-ttu-id="16a29-109">Por ejemplo, si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa `\\.\pipe\unit\app` como canalización, el alias debe usar `\\<computer_name>\pipe\unit\app` como el nombre de canalización.</span><span class="sxs-lookup"><span data-stu-id="16a29-109">For instance, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using `\\.\pipe\unit\app` as the pipe, the alias must use `\\<computer_name>\pipe\unit\app` as the pipe name.</span></span>  
  
 <span data-ttu-id="16a29-110">Para crear un nombre de canalización válido:</span><span class="sxs-lookup"><span data-stu-id="16a29-110">To create a valid pipe name, you must:</span></span>  
  
-   <span data-ttu-id="16a29-111">Especifique un **Nombre de alias**.</span><span class="sxs-lookup"><span data-stu-id="16a29-111">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="16a29-112">Seleccione **canalizaciones con nombre** como **Protocolo**.</span><span class="sxs-lookup"><span data-stu-id="16a29-112">Select **Named Pipes** as the **Protocol**.</span></span>  
  
-   <span data-ttu-id="16a29-113">Escriba el **nombre de la canalización**.</span><span class="sxs-lookup"><span data-stu-id="16a29-113">Enter the **Pipe Name**.</span></span> <span data-ttu-id="16a29-114">Como alternativa, puede dejar el **nombre de la canalización** en blanco y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager completará el nombre de canalización adecuado después de especificar el **Protocolo** y el **servidor** .</span><span class="sxs-lookup"><span data-stu-id="16a29-114">Alternatively, you can leave **Pipe Name** blank and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager will complete the appropriate pipe name after you specify the **Protocol** and **Server**</span></span>  
  
-   <span data-ttu-id="16a29-115">Especifique un **servidor**.</span><span class="sxs-lookup"><span data-stu-id="16a29-115">Specify a **Server**.</span></span> <span data-ttu-id="16a29-116">Para una instancia con nombre, puede proporcionar un nombre de servidor y un nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="16a29-116">For a named instance you can provide a server name and instance name.</span></span>  
  
 <span data-ttu-id="16a29-117">En el momento de la conexión, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componente Native Client Lee los valores de servidor, protocolo y nombre de canalización del registro para el nombre de alias especificado y crea un nombre de canalización con el formato `np:\\<computer_name>\pipe\<pipename>` o `np:\\<IPAddress>\pipe\<pipename>` . En el caso de una instancia con nombre, el nombre de canalización predeterminado es `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="16a29-117">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and pipe name values from the registry for the specified alias name, and creates a pipe name in the format `np:\\<computer_name>\pipe\<pipename>` or `np:\\<IPAddress>\pipe\<pipename>`.For a named instance, the default pipe name is `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16a29-118">De forma predeterminada, el Firewall de Windows de [!INCLUDE[msCoName](../../includes/msconame-md.md)] cierra el puerto 445.</span><span class="sxs-lookup"><span data-stu-id="16a29-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 445 by default.</span></span> <span data-ttu-id="16a29-119">Dado que [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se comunica a través del puerto 445, debe volver a abrir el puerto si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ha configurado para escuchar las conexiones de cliente entrantes que utilizan canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="16a29-119">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 445, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using named pipes.</span></span> <span data-ttu-id="16a29-120">Para obtener más información acerca de cómo configurar un firewall, vea “Cómo configurar un firewall para el acceso a SQL Server” en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o revise la documentación del firewall.</span><span class="sxs-lookup"><span data-stu-id="16a29-120">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="16a29-121">Conectarse al servidor local</span><span class="sxs-lookup"><span data-stu-id="16a29-121">Connecting to the Local Server</span></span>  
 <span data-ttu-id="16a29-122">Al conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se ejecuta en el mismo equipo que el cliente, puede utilizar `(local)` como el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="16a29-122">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)`as the server name.</span></span> <span data-ttu-id="16a29-123">El uso de `(local)` no se recomienda porque genera ambigüedad, pero puede ser útil cuando se sabe que el cliente se ejecuta en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="16a29-123">Using `(local)` is not encouraged because it leads to ambiguity; however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="16a29-124">Por ejemplo, al crear una aplicación para usuarios desconectados móviles, como puede ser el personal de ventas, en la que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecutará en equipos portátiles y se almacenarán datos de proyectos, un cliente que se conecte a (local) siempre se conectará al servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta en el equipo portátil.</span><span class="sxs-lookup"><span data-stu-id="16a29-124">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to (local) would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="16a29-125">En lugar de `localhost`, es posible usar `(local)` o un punto (.).</span><span class="sxs-lookup"><span data-stu-id="16a29-125">The word `localhost` or a period (.) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="16a29-126">Comprobar el protocolo de conexión</span><span class="sxs-lookup"><span data-stu-id="16a29-126">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="16a29-127">La siguiente consulta devolverá el protocolo utilizado para la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="16a29-127">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="16a29-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="16a29-128">Examples</span></span>  
 <span data-ttu-id="16a29-129">Conectarse por el nombre de servidor a la canalización predeterminada:</span><span class="sxs-lookup"><span data-stu-id="16a29-129">Connecting by server name to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="16a29-130">Conectarse por la dirección IP a la canalización predeterminada:</span><span class="sxs-lookup"><span data-stu-id="16a29-130">Connecting by IP Address to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <leave blank>  
Protocol           Named Pipes  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="16a29-131">Conectarse por el nombre de servidor a una canalización no predeterminada:</span><span class="sxs-lookup"><span data-stu-id="16a29-131">Connecting by server name to a non-default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\unit\app  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="16a29-132">Conectarse por el nombre de servidor a una instancia con nombre:</span><span class="sxs-lookup"><span data-stu-id="16a29-132">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\MSSQL$<instancename>\SQL\query  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="16a29-133">Conectarse al equipo local utilizando `localhost`:</span><span class="sxs-lookup"><span data-stu-id="16a29-133">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             localhost  
  
```  
  
 <span data-ttu-id="16a29-134">Conectarse al equipo local utilizando un punto:</span><span class="sxs-lookup"><span data-stu-id="16a29-134">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <left blank>  
Protocol           Named Pipes  
Server             .  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="16a29-135">Para especificar el protocolo de red como un parámetro **sqlcmd** , vea "Cómo conectar con el Motor de base de datos mediante sqlcmd.exe" en los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="16a29-135">To specify the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a29-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16a29-136">See Also</span></span>  
 <span data-ttu-id="16a29-137">[Crear una cadena de conexión válida con el protocolo de memoria compartida](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="16a29-137">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="16a29-138">[Crear una cadena de conexión válida con TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="16a29-138">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 [<span data-ttu-id="16a29-139">Elegir un protocolo de red</span><span class="sxs-lookup"><span data-stu-id="16a29-139">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
