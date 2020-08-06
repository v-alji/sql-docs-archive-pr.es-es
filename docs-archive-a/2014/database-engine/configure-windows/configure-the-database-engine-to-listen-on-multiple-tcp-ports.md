---
title: Configurar el motor de base de datos para escuchar en varios puertos TCP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab803bcaa5ab6b6187c1a994abef02f81ae105c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663706"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a><span data-ttu-id="8f9cb-102">Configurar el motor de base de datos para escuchar en varios puertos TCP</span><span class="sxs-lookup"><span data-stu-id="8f9cb-102">Configure the Database Engine to Listen on Multiple TCP Ports</span></span>
  <span data-ttu-id="8f9cb-103">En este tema se describe cómo configurar el [!INCLUDE[ssDE](../../includes/ssde-md.md)] para que escuche en varios puertos TCP en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-103">This topic describes how to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on multiple TCP ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="8f9cb-104">Si se ha habilitado TCP/IP para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el [!INCLUDE[ssDE](../../includes/ssde-md.md)] escuchará las conexiones entrantes en un punto de conexión compuesto por una dirección IP y un número de puerto TCP. Los procedimientos siguientes crean un extremo de flujo TDS para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuche en otro puerto TCP.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-104">When TCP/IP is enabled for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will listen for incoming connections on a connection point consisting of an IP address and TCP port number.The following procedures create a tabular data stream (TDS) endpoint, so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will listen on an additional TCP port.</span></span>  
  
 <span data-ttu-id="8f9cb-105">A continuación se detallan algunos posibles motivos que pueden llevar a crear un segundo extremo de TDS:</span><span class="sxs-lookup"><span data-stu-id="8f9cb-105">Possible reasons to create a second TDS endpoint include:</span></span>  
  
-   <span data-ttu-id="8f9cb-106">Incrementar la seguridad configurando el firewall de modo que se restrinja el acceso al extremo predeterminado a equipos cliente locales de una subred específica.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-106">Increase security by configuring the firewall to restrict access to the default endpoint to local client computers on a specific subnet.</span></span> <span data-ttu-id="8f9cb-107">Mantener el acceso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de Internet para el equipo de soporte creando un nuevo extremo que quede expuesto a Internet a través del firewall y restringiendo los derechos de conexión a este extremo al equipo de soporte del servidor.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-107">Maintain Internet access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for your support team by creating a new endpoint that the firewall exposes to the Internet, and restricting connection rights to this endpoint to your server support team.</span></span>  
  
-   <span data-ttu-id="8f9cb-108">Establecer afinidades entre conexiones y procesadores específicos al utilizar acceso no uniforme a memoria (NUMA).</span><span class="sxs-lookup"><span data-stu-id="8f9cb-108">Affinitizing connections to specific processors when using Non-Uniform Memory Access (NUMA).</span></span>  
  
 <span data-ttu-id="8f9cb-109">Para configurar un extremo de TDS hay que realizar los siguientes pasos, que se pueden efectuar en cualquier orden:</span><span class="sxs-lookup"><span data-stu-id="8f9cb-109">Configuring a TDS endpoint consists of the following steps, which can be done in any order:</span></span>  
  
-   <span data-ttu-id="8f9cb-110">Cree el extremo de TDS para el puerto TCP y restaure el acceso al extremo predeterminado si procede.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-110">Create the TDS endpoint for the TCP port, and restore access to the default endpoint if appropriate.</span></span>  
  
-   <span data-ttu-id="8f9cb-111">Conceda acceso al extremo a las entidades de seguridad de servidor que desee.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-111">Grant access to the endpoint to the desired server principals.</span></span>  
  
-   <span data-ttu-id="8f9cb-112">Especifique el número de puerto TCP para la dirección IP seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-112">Specify the TCP port number for the selected IP address.</span></span>  
  
 <span data-ttu-id="8f9cb-113">Para obtener más información sobre la configuración predeterminada de Firewall de Windows y una descripción de los puertos TCP que afectan al motor de base de datos, Analysis Services, Reporting Services e Integration Services, vea [Configurar Firewall de Windows para permitir el acceso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="8f9cb-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a><span data-ttu-id="8f9cb-114">Para crear un extremo de TDS</span><span class="sxs-lookup"><span data-stu-id="8f9cb-114">To create a TDS endpoint</span></span>  
  
-   <span data-ttu-id="8f9cb-115">Ejecute la siguiente instrucción para crear un extremo denominado **CustomConnection** para el puerto 1500, para todas las direcciones TCP disponibles en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-115">Issue the following statement to create an endpoint named **CustomConnection** for port 1500 for all available TCP addresses on the server.</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 <span data-ttu-id="8f9cb-116">Cuando se crea un nuevo extremo de [!INCLUDE[tsql](../../includes/tsql-md.md)] , los permisos de conexión correspondientes a **public** se revocan para el extremo de TDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-116">When you create a new [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoint, connect permissions for **public** are revoked for the default TDS endpoint.</span></span> <span data-ttu-id="8f9cb-117">Si el acceso al grupo **public** es necesario para el extremo predeterminado, aplique de nuevo este permiso mediante la instrucción `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` .</span><span class="sxs-lookup"><span data-stu-id="8f9cb-117">If access to the **public** group is needed for the default endpoint, reapply this permission by using the `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` statement.</span></span>  
  
#### <a name="to-grant-access-to-the-endpoint"></a><span data-ttu-id="8f9cb-118">Para conceder acceso al extremo</span><span class="sxs-lookup"><span data-stu-id="8f9cb-118">To grant access to the endpoint</span></span>  
  
-   <span data-ttu-id="8f9cb-119">Ejecute la siguiente instrucción para conceder acceso al extremo **CustomConnection** al grupo de soporte de SQL en el dominio corporativo.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-119">Issue the following statement to grant access to the **CustomConnection** endpoint to the SQLSupport group in the corp domain.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a><span data-ttu-id="8f9cb-120">Para configurar el motor de la base de datos de SQL Server para escuchar en otro puerto TCP</span><span class="sxs-lookup"><span data-stu-id="8f9cb-120">To configure the SQL Server Database Engine to listen on an additional TCP port</span></span>  
  
1.  <span data-ttu-id="8f9cb-121">En Administrador de configuración de SQL Server, expanda **Configuración de red de SQL Server** y, después, haga clic en **Protocolos de** _&lt;nombre_instancia&gt;_ .</span><span class="sxs-lookup"><span data-stu-id="8f9cb-121">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for**_<instance_name>_.</span></span>  
  
2.  <span data-ttu-id="8f9cb-122">Expanda **Protocolos de** _&lt;nombre_instancia&gt;_ y, después, haga clic en **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-122">Expand **Protocols for**_<instance_name>_, and then click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="8f9cb-123">En el panel derecho, haga clic con el botón derecho en cada dirección IP deshabilitada que quiera habilitar y, después, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-123">In the right pane, right-click each disabled IP address that you want to enable, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="8f9cb-124">Haga clic con el botón derecho en **IPAll**y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-124">Right-click **IPAll**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8f9cb-125">En el cuadro **Puerto TCP** , escriba los puertos en los que desee que escuche el [!INCLUDE[ssDE](../../includes/ssde-md.md)] , separados por comas.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-125">In the **TCP Port** box, type the ports that you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, separated by commas.</span></span> <span data-ttu-id="8f9cb-126">En nuestro ejemplo, si aparece el puerto predeterminado 1433, escriba `,1500` para que el cuadro lea `1433,1500` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-126">In our example, if the default port 1433 is listed, type `,1500` so the box reads `1433,1500`, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f9cb-127">Si no va a habilitar el puerto en todas las direcciones IP, configure el puerto adicional en el cuadro de propiedades solo para la dirección deseada.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-127">If you are not enabling the port on all IP addresses, configure the additional port in the property box for only for the desired address.</span></span> <span data-ttu-id="8f9cb-128">Después, en el panel de la consola, haga clic con el botón derecho en **TCP/IP**, haga clic en **Propiedades**y, en el cuadro **Escuchar todo** , seleccione **No**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-128">Then, in the console pane, right-click **TCP/IP**, click **Properties**, and in the **Listen All** box, select **No**.</span></span>  
  
6.  <span data-ttu-id="8f9cb-129">En el panel izquierdo, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-129">In the left pane, click **SQL Server Services**.</span></span>  
  
7.  <span data-ttu-id="8f9cb-130">En el panel derecho, haga clic con el botón derecho en **SQL Server** _&lt;nombre_instancia&gt;_ y, después, haga clic en **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-130">In the right pane, right-click **SQL Server**_<instance_name>_, and then click **Restart**.</span></span>  
  
     <span data-ttu-id="8f9cb-131">Cuando se reinicie el [!INCLUDE[ssDE](../../includes/ssde-md.md)], el registro de errores mostrará los puertos en los que escucha [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f9cb-131">When the [!INCLUDE[ssDE](../../includes/ssde-md.md)] restarts, the Error log will list the ports on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening.</span></span>  
  
#### <a name="to-connect-to-the-new-endpoint"></a><span data-ttu-id="8f9cb-132">Para conectarse al nuevo extremo</span><span class="sxs-lookup"><span data-stu-id="8f9cb-132">To connect to the new endpoint</span></span>  
  
-   <span data-ttu-id="8f9cb-133">Ejecute la siguiente instrucción para conectarse al punto de conexión **CustomConnection** de la instancia predeterminada de SQL Server en el servidor llamado ACCT, usando una conexión de confianza y suponiendo que el usuario es miembro del grupo [corp\SQLSupport].</span><span class="sxs-lookup"><span data-stu-id="8f9cb-133">Issue the following statement to connect to the **CustomConnection** endpoint of the default instance of SQL Server on the server named ACCT, using a trusted connection, and assuming the user is a member of the [corp\SQLSupport] group.</span></span>  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8f9cb-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f9cb-134">See Also</span></span>  
 <span data-ttu-id="8f9cb-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8f9cb-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="8f9cb-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8f9cb-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="8f9cb-137">[GRANT &#40;permisos de punto de conexión de Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8f9cb-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="8f9cb-138">Asignación de puertos TCP/IP a nodos NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f9cb-138">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  
