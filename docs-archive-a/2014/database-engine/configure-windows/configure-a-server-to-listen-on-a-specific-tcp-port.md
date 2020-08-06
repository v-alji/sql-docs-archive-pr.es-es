---
title: Configurar un servidor para que escuche en un puerto TCP específico (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fixed port
- static ports
- ports [SQL Server], assigning numbers
- assigning port numbers
- dynamic ports [SQL Server]
- TCP/IP [SQL Server], port numbers
ms.assetid: 2276a5ed-ae3f-4855-96d8-f5bf01890640
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb740910c65580e8ea3170d03481e6cb628860
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663117"
---
# <a name="configure-a-server-to-listen-on-a-specific-tcp-port-sql-server-configuration-manager"></a><span data-ttu-id="4efa0-102">Configurar un servidor para que escuche en un puerto TCP específico (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4efa0-102">Configure a Server to Listen on a Specific TCP Port (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="4efa0-103">En este tema se describe cómo configurar una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] para escuchar en un puerto fijo específico mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4efa0-103">This topic describes how to configure an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to listen on a specific fixed port by using the SQL Server Configuration Manager.</span></span> <span data-ttu-id="4efa0-104">Si está habilitada, la instancia predeterminada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] escucha en el puerto TCP 1433.</span><span class="sxs-lookup"><span data-stu-id="4efa0-104">If enabled, the default instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on TCP port 1433.</span></span> <span data-ttu-id="4efa0-105">Las instancias con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y [!INCLUDE[ssEW](../../includes/ssew-md.md)] están configuradas para puertos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="4efa0-105">Named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] are configured for dynamic ports.</span></span> <span data-ttu-id="4efa0-106">Esto significa que seleccionan un puerto disponible cuando se inicia el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4efa0-106">This means they select an available port when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is started.</span></span> <span data-ttu-id="4efa0-107">Cuando se conecte a una instancia con nombre a través de un firewall, configure el [!INCLUDE[ssDE](../../includes/ssde-md.md)] para que escuche en un puerto específico, de modo que el puerto adecuado pueda abrirse en el firewall.</span><span class="sxs-lookup"><span data-stu-id="4efa0-107">When you are connecting to a named instance through a firewall, configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on a specific port, so that the appropriate port can be opened in the firewall.</span></span>  
  
 <span data-ttu-id="4efa0-108">Para obtener más información sobre la configuración predeterminada de Firewall de Windows y una descripción de los puertos TCP que afectan al motor de base de datos, Analysis Services, Reporting Services e Integration Services, vea [Configurar Firewall de Windows para permitir el acceso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="4efa0-108">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="4efa0-109">Al seleccionar un número de puerto, consulte [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) para obtener una lista de los números de puerto asignados a determinadas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4efa0-109">When selecting a port number, consult [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) for a list of port numbers that are assigned to specific applications.</span></span> <span data-ttu-id="4efa0-110">Seleccione un número de puerto sin asignar.</span><span class="sxs-lookup"><span data-stu-id="4efa0-110">Select an unassigned port number.</span></span> <span data-ttu-id="4efa0-111">Para obtener más información, vea [El rango de puertos dinámicos predeterminado para TCP/IP ha cambiado en Windows Vista y Windows Server 2008](https://support.microsoft.com/kb/929851).</span><span class="sxs-lookup"><span data-stu-id="4efa0-111">For more information, see [The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008](https://support.microsoft.com/kb/929851).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="4efa0-112">El Motor de base de datos empieza a escuchar en un puerto nuevo cuando se reinicia.</span><span class="sxs-lookup"><span data-stu-id="4efa0-112">The Database Engine begins listening on a new port when restarted.</span></span> <span data-ttu-id="4efa0-113">Sin embargo, el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser supervisa el Registro e informa del nuevo número de puerto en cuanto cambia la configuración, incluso aunque el Motor de base de datos no lo use.</span><span class="sxs-lookup"><span data-stu-id="4efa0-113">However the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service monitors the registry and reports the new port number as soon as the configuration is changed, even though the Database Engine might not be using it.</span></span> <span data-ttu-id="4efa0-114">Reinicie el Motor de base de datos para asegurar la coherencia y evitar errores de conexión.</span><span class="sxs-lookup"><span data-stu-id="4efa0-114">Restart the Database Engine to ensure consistency and avoid connection failures.</span></span>  
  
 <span data-ttu-id="4efa0-115">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4efa0-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4efa0-116">**Para configurar un servidor de modo que la escucha se realice en un puerto TCP específico, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="4efa0-116">**To configure a server to listen on a specific TCP port, using:**</span></span>  
  
     [<span data-ttu-id="4efa0-117">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4efa0-117">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4efa0-118">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4efa0-118">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-assign-a-tcpip-port-number-to-the-sql-server-database-engine"></a><span data-ttu-id="4efa0-119">Para asignar un número de puerto TCP/IP al Motor de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4efa0-119">To assign a TCP/IP port number to the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="4efa0-120">En el panel de la consola del Administrador de configuración de SQL Server, expanda **Configuración de red de SQL Server**, **Protocolos de \<instance name>** y, después, haga doble clic en **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="4efa0-120">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, expand **Protocols for \<instance name>**, and then double-click **TCP/IP**.</span></span>  
  
2.  <span data-ttu-id="4efa0-121">En el cuadro de diálogo **Propiedades de TCP/IP** , en la pestaña **Direcciones IP** , aparecen varias direcciones IP con el formato **IP1**, **IP2**, hasta **IPAll**.</span><span class="sxs-lookup"><span data-stu-id="4efa0-121">In the **TCP/IP Properties** dialog box, on the **IP Addresses** tab, several IP addresses appear in the format **IP1**, **IP2**, up to **IPAll**.</span></span> <span data-ttu-id="4efa0-122">Una de estas direcciones IP, 127.0.0.1, se utiliza para el adaptador de bucle invertido.</span><span class="sxs-lookup"><span data-stu-id="4efa0-122">One of these is for the IP address of the loopback adapter, 127.0.0.1.</span></span> <span data-ttu-id="4efa0-123">Aparecen direcciones IP adicionales para cada dirección IP del equipo.</span><span class="sxs-lookup"><span data-stu-id="4efa0-123">Additional IP addresses appear for each IP Address on the computer.</span></span> <span data-ttu-id="4efa0-124">Haga clic con el botón derecho en cada dirección y luego haga clic en **Propiedades** para identificar la dirección IP que quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="4efa0-124">Right-click each address, and then click **Properties** to identify the IP address that you want to configure.</span></span>  
  
3.  <span data-ttu-id="4efa0-125">Si el cuadro de diálogo **Puertos dinámicos TCP** contiene **0**, que indica que el [!INCLUDE[ssDE](../../includes/ssde-md.md)] escucha en los puertos dinámicos, elimine el 0.</span><span class="sxs-lookup"><span data-stu-id="4efa0-125">If the **TCP Dynamic Ports** dialog box contains **0**, indicating the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is listening on dynamic ports, delete the 0.</span></span>  
  
4.  <span data-ttu-id="4efa0-126">En el cuadro **Propiedades** de **IP_n_**, en **Puerto TCP**, escriba el número de puerto en el que quiere que esta dirección IP escuche y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4efa0-126">In the **IP**_n_ **Properties** area box, in the **TCP Port** box, type the port number you want this IP address to listen on, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4efa0-127">En el panel de la consola, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4efa0-127">In the console pane, click **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="4efa0-128">En el panel de detalles, haga clic con el botón derecho en **SQL Server (** \<instance name> **)** y, después, haga clic en **Reiniciar** para detener y reiniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4efa0-128">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4efa0-129">Después de haber configurado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que escuche en un puerto específico, dispone de tres métodos para conectarse a un puerto específico con una aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="4efa0-129">After you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on a specific port, there are three ways to connect to a specific port with a client application:</span></span>  
  
-   <span data-ttu-id="4efa0-130">Ejecute el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el servidor para conectarse a la instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] por nombre.</span><span class="sxs-lookup"><span data-stu-id="4efa0-130">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance by name.</span></span>  
  
-   <span data-ttu-id="4efa0-131">Cree un alias en el cliente; para ello, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="4efa0-131">Create an alias on the client, specifying the port number.</span></span>  
  
-   <span data-ttu-id="4efa0-132">Programar el cliente para conectarse mediante una cadena de conexión personalizada.</span><span class="sxs-lookup"><span data-stu-id="4efa0-132">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efa0-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4efa0-133">See Also</span></span>  
 [<span data-ttu-id="4efa0-134">Crear o eliminar un alias de servidor para que lo utilice un cliente &#40;Administrador de configuración de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4efa0-134">Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;</span></span>](create-or-delete-a-server-alias-for-use-by-a-client.md)  
  
  
