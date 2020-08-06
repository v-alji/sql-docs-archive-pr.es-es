---
title: Protocolos de red y bibliotecas de red | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- protocols [SQL Server]
- configuration options [SQL Server], protocols
- network libraries [SQL Server]
- protocols [SQL Server], about network protocols
- pipes [SQL Server]
- network protocols [SQL Server]
- default SQL Server configurations
- library [SQL Server]
- network protocols [SQL Server], about network protocols
- configuration options [SQL Server], libraries
ms.assetid: 8cd437f6-9af1-44ce-9cb0-4d10c83da9ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be012ea2bc9499a99ca7763446c6f26cf219a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676819"
---
# <a name="network-protocols-and-network-libraries"></a><span data-ttu-id="5b0f3-102">Protocolos de red y bibliotecas de red</span><span class="sxs-lookup"><span data-stu-id="5b0f3-102">Network Protocols and Network Libraries</span></span>
  <span data-ttu-id="5b0f3-103">Un servidor puede escuchar en, o supervisar, varios protocolos de red al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-103">A server can listen on, or monitor, multiple network protocols at one time.</span></span> <span data-ttu-id="5b0f3-104">Sin embargo, cada protocolo debe estar configurado.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-104">However, each protocol must be configured.</span></span> <span data-ttu-id="5b0f3-105">Si un protocolo concreto no está configurado, el servidor no podrá escuchar en dicho protocolo.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-105">If a particular protocol is not configured, the server cannot listen on that protocol.</span></span> <span data-ttu-id="5b0f3-106">Después de la instalación, podrá cambiar las configuraciones de protocolo mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b0f3-106">After installation, you can change the protocol configurations using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="default-sql-server-network-configuration"></a><span data-ttu-id="5b0f3-107">Configuración de red de SQL Server predeterminada</span><span class="sxs-lookup"><span data-stu-id="5b0f3-107">Default SQL Server Network Configuration</span></span>  
 <span data-ttu-id="5b0f3-108">Se configura una instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el puerto TCP/IP 1433 y la canalización con nombre \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-108">A default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for TCP/IP port 1433, and named pipe \\\\.\pipe\sql\query.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b0f3-109">se configuran para puertos dinámicos TCP, con un número de puerto asignado por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-109">named instances are configured for TCP dynamic ports, with a port number assigned by the operating system.</span></span>  
  
 <span data-ttu-id="5b0f3-110">Si no puede utilizar direcciones de puerto dinámicas (por ejemplo, cuando las conexiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deben pasar por un servidor de firewall configurado pasar a través de direcciones de puerto específicas).</span><span class="sxs-lookup"><span data-stu-id="5b0f3-110">If you cannot use dynamic port addresses (for example, when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections must pass through a firewall server configured to pass through specific port addresses).</span></span> <span data-ttu-id="5b0f3-111">Seleccione un número de puerto sin asignar.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-111">Select an unassigned port number.</span></span> <span data-ttu-id="5b0f3-112">La Internet Assigned Numbers Authority administra las asignaciones del número de puerto, que se muestran en [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span><span class="sxs-lookup"><span data-stu-id="5b0f3-112">Port number assignments are managed by the Internet Assigned Numbers Authority and are listed at [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span></span>  
  
 <span data-ttu-id="5b0f3-113">Para mejorar la seguridad, la conectividad de red no se habilita totalmente al instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b0f3-113">To enhance security, network connectivity is not fully enabled when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span> <span data-ttu-id="5b0f3-114">Para habilitar, deshabilitar y configurar protocolos de red después de completar la instalación, utilice el área Configuración de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b0f3-114">To enable, disable, and configure network protocols after Setup is complete, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Configuration area of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="server-message-block-protocol"></a><span data-ttu-id="5b0f3-115">Protocolo Bloque de mensajes del servidor</span><span class="sxs-lookup"><span data-stu-id="5b0f3-115">Server Message Block Protocol</span></span>  
 <span data-ttu-id="5b0f3-116">Los servidores de la red perimétrica deben tener todos los protocolos innecesarios deshabilitados, incluido el bloque de mensajes del servidor (SMB).</span><span class="sxs-lookup"><span data-stu-id="5b0f3-116">Servers in the perimeter network should have all unnecessary protocols disabled, including server message block (SMB).</span></span> <span data-ttu-id="5b0f3-117">Los servidores web y los servidores del Sistema de nombres de dominio (DNS) no necesitan SMB.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-117">Web servers and Domain Name System (DNS) servers do not require SMB.</span></span> <span data-ttu-id="5b0f3-118">Este protocolo debería deshabilitarse para contrarrestar la amenaza de enumeración de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-118">This protocol should be disabled to counter the threat of user enumeration.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5b0f3-119">Si deshabilita el Bloque de mensajes de servidor, se bloqueará [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el Servicio de clúster de Windows para tener acceso al recurso compartido de archivos remoto.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-119">Disabling Server Message Block will block the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Windows Cluster service from accessing the remote file share.</span></span> <span data-ttu-id="5b0f3-120">No deshabilite SMB si hace algo de lo siguiente o prevé hacerlo:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-120">Do not disable SMB if you do or plan to do one of the following:</span></span>  
> 
>  -   <span data-ttu-id="5b0f3-121">Usar el modo de quórum de la mayoría del recurso compartido de archivos y el Nodo de clúster de Windows</span><span class="sxs-lookup"><span data-stu-id="5b0f3-121">Use Windows Cluster Node and File Share Majority Quorum mode</span></span>  
> -   <span data-ttu-id="5b0f3-122">Especificar un recurso compartido de archivos SMB como directorio de datos durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b0f3-122">Specify an SMB file share as the data directory during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation</span></span>  
> -   <span data-ttu-id="5b0f3-123">Crear un archivo de base de datos en un recurso compartido de archivos SMB</span><span class="sxs-lookup"><span data-stu-id="5b0f3-123">Create a database file on an SMB file share</span></span>  
  
#### <a name="to-disable-smb"></a><span data-ttu-id="5b0f3-124">Para deshabilitar SMB</span><span class="sxs-lookup"><span data-stu-id="5b0f3-124">To disable SMB</span></span>  
  
1.  <span data-ttu-id="5b0f3-125">En el menú **Inicio** , seleccione **Configuración**y, después, haga clic en **Conexiones de red y de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-125">On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**.</span></span>  
  
     <span data-ttu-id="5b0f3-126">Haga clic con el botón derecho en la conexión con Internet y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-126">Right-click the Internet-facing connection, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5b0f3-127">Active la casilla **Cliente para redes Microsoft** y, a continuación, haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-127">Select the **Client for Microsoft Networks** check box, and then click **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="5b0f3-128">Siga los pasos de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-128">Follow the uninstall steps.</span></span>  
  
4.  <span data-ttu-id="5b0f3-129">Seleccione **Compartir impresoras y archivos para redes Microsoft** y, a continuación, haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-129">Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="5b0f3-130">Siga los pasos de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-130">Follow the uninstall steps.</span></span>  
  
#### <a name="to-disable-smb-on-servers-accessible-from-the-internet"></a><span data-ttu-id="5b0f3-131">Para deshabilitar SMB en servidores accesibles desde Internet</span><span class="sxs-lookup"><span data-stu-id="5b0f3-131">To disable SMB on servers accessible from the Internet</span></span>  
  
-   <span data-ttu-id="5b0f3-132">En las propiedades de Conexión de área local, utilice el cuadro de diálogo **Propiedades de Protocolo de control de transporte/Protocolo Internet (TCP/IP)** para quitar **Impresoras y archivos para redes Microsoft** y **Cliente para redes Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-132">In the Local Area Connection properties, use the **Transmission Control Protocol/Internet Protocol (TCP/IP) properties** dialog box to remove **File and Printer Sharing for Microsoft Networks** and **Client for Microsoft Networks**.</span></span>  
  
## <a name="endpoints"></a><span data-ttu-id="5b0f3-133">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="5b0f3-133">Endpoints</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b0f3-134">presenta un nuevo concepto para conexiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; la conexión se representa en el extremo de servidor mediante un [!INCLUDE[tsql](../../includes/tsql-md.md)]*de*.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-134">introduces a new concept for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections; the connection is represented on the server end by a [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span></span> <span data-ttu-id="5b0f3-135">Se pueden otorgar, revocar y denegar permisos para extremos de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b0f3-135">Permissions can be granted, revoked, and denied for [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints.</span></span> <span data-ttu-id="5b0f3-136">De manera predeterminada, todos los usuarios tienen permisos para obtener acceso a un extremo, a menos que los permisos sean denegados o revocados por un miembro del grupo sysadmin o por el propietario del extremo.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-136">By default, all users have permissions to access an endpoint unless the permissions are denied or revoked by a member of the sysadmin group or by the endpoint owner.</span></span> <span data-ttu-id="5b0f3-137">La sintaxis GRANT, REVOKE y DENY ENDPOINT utiliza un Id. de extremo que el administrador debe obtener de la vista de catálogo del extremo.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-137">The GRANT, REVOKE, and DENY ENDPOINT syntax uses an endpoint ID that the administrator must get from the endpoint's catalog view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b0f3-138">crea extremos de [!INCLUDE[tsql](../../includes/tsql-md.md)] para todos los protocolos de red admitidos, así como para la conexión de administrador dedicada.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-138">Setup creates [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints for all supported network protocols, as well as for the dedicated administrator connection.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="5b0f3-139">creados por el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-139">endpoints created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup are as follows:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="5b0f3-140">equipo local</span><span class="sxs-lookup"><span data-stu-id="5b0f3-140">local machine</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="5b0f3-141">canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="5b0f3-141">named pipes</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="5b0f3-142">Puerto TCP predeterminado</span><span class="sxs-lookup"><span data-stu-id="5b0f3-142">default TCP</span></span>  
  
 <span data-ttu-id="5b0f3-143">Para obtener más información sobre los puntos de conexión, vea [Configurar el motor de base de datos para escuchar en varios puertos TCP](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) y [Vistas de catálogo de puntos de conexión &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b0f3-143">For more information about endpoints, see [Configure the Database Engine to Listen on Multiple TCP Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) and [Endpoints Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span></span>  
  
 <span data-ttu-id="5b0f3-144">Para obtener más información sobre las configuraciones de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte el siguiente tema en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5b0f3-144">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network configurations, see the following topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="5b0f3-145">Configuración de red del servidor</span><span class="sxs-lookup"><span data-stu-id="5b0f3-145">Server Network Configuration</span></span>](../../database-engine/configure-windows/server-network-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b0f3-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b0f3-146">See Also</span></span>  
 <span data-ttu-id="5b0f3-147">[Configuración de Área expuesta](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5b0f3-147">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 <span data-ttu-id="5b0f3-148">[Consideraciones de seguridad para una instalación de SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="5b0f3-148">[Security Considerations for a SQL Server Installation](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="5b0f3-149">Planear una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b0f3-149">Planning a SQL Server Installation</span></span>](../../../2014/sql-server/install/planning-a-sql-server-installation.md)  
  
  
