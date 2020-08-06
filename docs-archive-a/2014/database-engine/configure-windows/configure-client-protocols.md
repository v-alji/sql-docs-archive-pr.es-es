---
title: Configurar protocolos de cliente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default protocols
- network protocols [SQL Server], client configuration
- TCP/IP [SQL Server], client protocols
- disabling client protocols
- ordering protocols [SQL Server]
- protocols [SQL Server], order for client computers
- configure client protocols
- client protocols [SQL Server]
- protocols [SQL Server], client configuration
ms.assetid: 3dfa2702-ba65-43b4-a777-6727846e133a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2eb223815c3e3af50813e02d3ded60573c327155
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677890"
---
# <a name="configure-client-protocols"></a><span data-ttu-id="18c51-102">configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="18c51-102">Configure Client Protocols</span></span>
  <span data-ttu-id="18c51-103">En este tema se describe cómo configurar los protocolos de cliente utilizados por aplicaciones cliente de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18c51-103">This topic describes how to configure client protocols used by client applications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="18c51-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite comunicaciones de cliente con el protocolo de red TCP/IP y el protocolo de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="18c51-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports client communication with the TCP/IP network protocol and the named pipes protocol.</span></span> <span data-ttu-id="18c51-105">El protocolo de memoria compartida también está disponible si el cliente se está conectando a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="18c51-105">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="18c51-106">Hay varios métodos habituales para seleccionar el protocolo.</span><span class="sxs-lookup"><span data-stu-id="18c51-106">There are three common methods of selecting the protocol.</span></span>  
  
-   <span data-ttu-id="18c51-107">Configure todas las aplicaciones cliente para que usen el mismo protocolo de red estableciendo el orden de protocolos en el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18c51-107">Configure all client applications to use the same network protocol by setting the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
-   <span data-ttu-id="18c51-108">Configure una sola aplicación cliente para que use otro protocolo de red creando un alias.</span><span class="sxs-lookup"><span data-stu-id="18c51-108">Configure a single client application to use a different network protocol by creating an alias.</span></span> <span data-ttu-id="18c51-109">Para obtener más información, vea [Crear o eliminar un alias de servidor para que lo utilice un cliente &#40;Administrador de configuración de SQL Server&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="18c51-109">For more information, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="18c51-110">Algunas aplicaciones cliente, como sqlcmd.exe, pueden especificar el protocolo como parte de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="18c51-110">Some client applications, such as sqlcmd.exe, can specify the protocol as part of the connection string.</span></span> <span data-ttu-id="18c51-111">Para obtener más información, vea [Conectarse al motor de base de datos con sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="18c51-111">For more information, see [Connect to the Database Engine With sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="18c51-112">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="18c51-112">Using SQL Server Configuration Manager</span></span>  
  
###  <a name="to-enable-or-disable-a-client-protocol"></a><a name="EnableDisable"></a> <span data-ttu-id="18c51-113">Para habilitar o deshabilitar un protocolo de cliente</span><span class="sxs-lookup"><span data-stu-id="18c51-113">To enable or disable a client protocol</span></span>  
  
1.  <span data-ttu-id="18c51-114">En el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], expanda **Configuración de SQL Server Native Client**, haga clic con el botón derecho en **Protocolos de cliente** y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="18c51-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="18c51-115">Haga clic en un protocolo en el cuadro **Protocolos deshabilitados** y, a continuación, haga clic en **Habilitar**para habilitar el protocolo.</span><span class="sxs-lookup"><span data-stu-id="18c51-115">Click a protocol in the **Disabled Protocols** box, and then click **Enable**, to enable a protocol.</span></span>  
  
3.  <span data-ttu-id="18c51-116">Haga clic en un protocolo en el cuadro **Protocolos habilitados** y, a continuación, haga clic en **Deshabilitar**para deshabilitar el protocolo.</span><span class="sxs-lookup"><span data-stu-id="18c51-116">Click a protocol in the **Enabled Protocols** box, and then click **Disable**, to disable a protocol.</span></span>  
  
###  <a name="to-change-the-default-protocol-or-the-protocol-order-for-client-computers"></a><a name="ChangeDefault"></a> <span data-ttu-id="18c51-117">Para cambiar el protocolo o el orden de protocolos predeterminado de los equipos cliente</span><span class="sxs-lookup"><span data-stu-id="18c51-117">To change the default protocol or the protocol order for client computers</span></span>  
  
1.  <span data-ttu-id="18c51-118">En el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], expanda **Configuración de SQL Server Native Client**, haga clic con el botón derecho en **Protocolos de cliente** y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="18c51-118">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="18c51-119">En el cuadro **Protocolos habilitados** , haga clic en **Subir** o **Bajar**para cambiar el orden en el que los protocolos se utilizan cuando se intenta la conexión a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18c51-119">In the **Enabled Protocols** box, click **Move Up** or **Move Down**, to change the order in which protocols are tried, when attempting to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="18c51-120">El protocolo superior del cuadro **Protocolos habilitados** es el protocolo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="18c51-120">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="18c51-121">El Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea entradas del Registro para las configuraciones de alias del servidor y la biblioteca de red de cliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18c51-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager creates registry entries for the server alias configurations and default client network library.</span></span> <span data-ttu-id="18c51-122">Sin embargo, la aplicación no instala ni las bibliotecas de red de cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ni los protocolos de red.</span><span class="sxs-lookup"><span data-stu-id="18c51-122">However, the application does not install either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries or the network protocols.</span></span> <span data-ttu-id="18c51-123">Las bibliotecas de red de cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se instalan durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; los protocolos de red se instalan como parte del programa de instalación de Microsoft Windows (o desde **Redes** en el **Panel de control**).</span><span class="sxs-lookup"><span data-stu-id="18c51-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries are installed during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup; the network protocols are installed as part of Microsoft Windows Setup (or through **Networks** in **Control Panel**).</span></span> <span data-ttu-id="18c51-124">Es posible que un protocolo de red específico no esté disponible como parte del programa de instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="18c51-124">A particular network protocol may not be available as part of Windows Setup.</span></span> <span data-ttu-id="18c51-125">Para obtener más información acerca de cómo instalar estos protocolos de red, consulte la documentación del fabricante.</span><span class="sxs-lookup"><span data-stu-id="18c51-125">For more information about installing these network protocols, see the vendor documentation.</span></span>  
  
###  <a name="to-configure-a-client-to-use-tcpip"></a><a name="Configure"></a> <span data-ttu-id="18c51-126">Para configurar el uso de TCP/IP en un cliente</span><span class="sxs-lookup"><span data-stu-id="18c51-126">To configure a client to use TCP/IP</span></span>  
  
1.  <span data-ttu-id="18c51-127">En el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], expanda **Configuración de SQL Server Native Client**, haga clic con el botón derecho en **Protocolos de cliente** y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="18c51-127">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="18c51-128">En el cuadro **Protocolos habilitados** , haga clic en las flechas arriba o abajo para cambiar el orden en que se prueban los protocolos al intentar conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18c51-128">In the **Enabled Protocols** box, click the up and down arrows to change the order in which protocols are tried, when attempting to connect to SQL Server.</span></span> <span data-ttu-id="18c51-129">El protocolo superior del cuadro **Protocolos habilitados** es el protocolo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="18c51-129">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
 <span data-ttu-id="18c51-130">El protocolo de memoria compartida se habilita de forma independiente activando la casilla **Habilitar el protocolo de memoria compartida** .</span><span class="sxs-lookup"><span data-stu-id="18c51-130">The shared memory protocol is enabled separately by checking the **Enabled Shared Memory Protocol** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c51-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18c51-131">See Also</span></span>  
 [<span data-ttu-id="18c51-132">Establecer la opción de configuración del servidor Tiempo de espera de inicio de sesión remoto</span><span class="sxs-lookup"><span data-stu-id="18c51-132">Configure the remote login timeout Server Configuration Option</span></span>](configure-the-remote-login-timeout-server-configuration-option.md)  
  
  
