---
title: Configuración del área expuesta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- reducing attackable surface area
- upgrading SQL Server, security
- surface area configuration [SQL Server]
- surface area configuration [SQL Server], about surface area configuration
- attackable surface area [SQL Server]
- installing SQL Server, security
ms.assetid: f741169c-1453-4ad2-830b-bf2be27d712f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ef64fbbeb2b8953ff3816db63572b499d42f012e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745108"
---
# <a name="surface-area-configuration"></a><span data-ttu-id="f14e0-102">Configuración de Área expuesta</span><span class="sxs-lookup"><span data-stu-id="f14e0-102">Surface Area Configuration</span></span>
  <span data-ttu-id="f14e0-103">Con la configuración predeterminada de nuevas instalaciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], no se habilitan muchas de las características.</span><span class="sxs-lookup"><span data-stu-id="f14e0-103">In the default configuration of new installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], many features are not enabled.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f14e0-104">instala selectivamente y solo inicia servicios y características claves para minimizar el número de características que pueden ser atacadas por un usuario malintencionado.</span><span class="sxs-lookup"><span data-stu-id="f14e0-104">selectively installs and starts only key services and features, to minimize the number of features that can be attacked by a malicious user.</span></span> <span data-ttu-id="f14e0-105">Un administrador del sistema puede cambiar esta configuración predeterminada en el momento de la instalación y puede habilitar o deshabilitar de forma selectiva las características de una instancia en ejecución de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f14e0-105">A system administrator can change these defaults at installation time and also selectively enable or disable features of a running instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f14e0-106">Además, algunos componentes no pueden estar disponibles al conectar desde otros equipos hasta que se configuren los protocolos.</span><span class="sxs-lookup"><span data-stu-id="f14e0-106">Additionally, some components may not be available when connecting from other computers until protocols are configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f14e0-107">A diferencia de las nuevas instalaciones, los servicios o características existentes no se desactivan durante una actualización, pero las opciones de configuración adicionales de área expuesta pueden aplicarse una vez completada la actualización.</span><span class="sxs-lookup"><span data-stu-id="f14e0-107">Unlike new installations, no existing services or features are turned off during an upgrade, but additional surface area configuration options can be applied after the upgrade is completed.</span></span>  
  
## <a name="protocols-connection-and-startup-options"></a><span data-ttu-id="f14e0-108">Opciones de protocolo, conexión e inicio</span><span class="sxs-lookup"><span data-stu-id="f14e0-108">Protocols, Connection, and Startup Options</span></span>  
 <span data-ttu-id="f14e0-109">Utilice el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para iniciar y detener servicios, configurar opciones de inicio, y habilitar protocolos y otras opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="f14e0-109">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to start and stop services, configure the startup options, and enable protocols and other connection options.</span></span>  
  
#### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="f14e0-110">Para iniciar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f14e0-110">To start SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="f14e0-111">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f14e0-111">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    -   <span data-ttu-id="f14e0-112">Utilice el área **Servicios de SQL Server** para iniciar los componentes y configurar las opciones de inicio automáticas.</span><span class="sxs-lookup"><span data-stu-id="f14e0-112">Use the **SQL Server Services** area to start components and configure the automatic starting options.</span></span>  
  
    -   <span data-ttu-id="f14e0-113">Use el área **Configuración de red de SQL Server** para habilitar protocolos de conexión y opciones de conexión tales como los puertos TCP/IP fijos o para forzar el cifrado.</span><span class="sxs-lookup"><span data-stu-id="f14e0-113">Use the **SQL Server Network Configuration** area to enable connection protocols, and connection options such as fixed TCP/IP ports, or forcing encryption.</span></span>  
  
 <span data-ttu-id="f14e0-114">Para obtener más información, vea [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f14e0-114">For more information, see [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span></span> <span data-ttu-id="f14e0-115">La conectividad remota también puede depender de la configuración correcta de un firewall.</span><span class="sxs-lookup"><span data-stu-id="f14e0-115">Remote connectivity can also depend upon the correct configuration of a firewall.</span></span> <span data-ttu-id="f14e0-116">Para más información, consulte [Configurar Firewall de Windows para permitir el acceso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="f14e0-116">For more information, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
## <a name="enabling-and-disabling-features"></a><span data-ttu-id="f14e0-117">Habilitar y deshabilitar características</span><span class="sxs-lookup"><span data-stu-id="f14e0-117">Enabling and Disabling Features</span></span>  
 <span data-ttu-id="f14e0-118">Habilitar y deshabilitar características [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se puede configurar utilizando facetas en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f14e0-118">Enabling and disabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features can be configured using facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-configure-surface-area-using-facets"></a><span data-ttu-id="f14e0-119">Para configurar área expuesta mediante facetas</span><span class="sxs-lookup"><span data-stu-id="f14e0-119">To configure surface area using facets</span></span>  
  
1.  <span data-ttu-id="f14e0-120">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , conecte con un componente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f14e0-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connect to a component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="f14e0-121">En el Explorador de objetos, haga clic con el botón derecho en el servidor y, luego, haga clic en **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="f14e0-121">In Object Explorer, right-click the server, and then click **Facets**.</span></span>  
  
3.  <span data-ttu-id="f14e0-122">En el cuadro de diálogo **Ver facetas** , expanda la lista **Faceta** y seleccione la faceta **Configuración de área expuesta** apropiada (**Configuración de área expuesta**, **Configuración de área expuesta para Analysis Services**o **Configuración de área expuesta para Reporting Services**).</span><span class="sxs-lookup"><span data-stu-id="f14e0-122">In the **View Facets** dialog box, expand the **Facet** list, and select the appropriate **Surface Area Configuration** facet (**Surface Area Configuration**, **Surface Area Configuration for Analysis Services**, or **Surface Area Configuration for Reporting Services**).</span></span>  
  
4.  <span data-ttu-id="f14e0-123">En el área **Propiedades de faceta** , seleccione los valores que desee para cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="f14e0-123">In the **Facet properties** area, select the values that you want for each property.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="f14e0-124">Para comprobar periódicamente la configuración de una faceta, use la Administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="f14e0-124">To periodically check the configuration of a facet, use Policy-Based Management.</span></span> <span data-ttu-id="f14e0-125">Para obtener más información sobre la administración basada en directivas, vea [Administrar servidores mediante administración basada en directivas](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="f14e0-125">For more information about Policy-Based Management, see [Administer Servers by Using Policy-Based Management](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="f14e0-126">También puede establecer opciones de [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante el procedimiento almacenado `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="f14e0-126">You can also set [!INCLUDE[ssDE](../../includes/ssde-md.md)] options using the `sp_configure` stored procedure.</span></span> <span data-ttu-id="f14e0-127">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f14e0-127">For more information, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
 <span data-ttu-id="f14e0-128">Para cambiar la propiedad **EnableIntegrated Security** de [!INCLUDE[ssRS](../../includes/ssrs.md)], utilice la configuración de las propiedades de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f14e0-128">To change the **EnableIntegrated Security** property of [!INCLUDE[ssRS](../../includes/ssrs.md)], use the property settings in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f14e0-129">Para cambiar la propiedad **Eventos de programación y entrega de informes habilitados** y la propiedad **Acceso HTTP y de servicios Web** , modifique el archivo de configuración **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="f14e0-129">To change the **Schedule events and report delivery** property and the **Web service and HTTP access** property, edit the **RSReportServer.config** configuration file.</span></span>  
  
## <a name="command-prompt-options"></a><span data-ttu-id="f14e0-130">Opciones del símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="f14e0-130">Command-prompt Options</span></span>  
 <span data-ttu-id="f14e0-131">Use el cmdlet **Invoke-PolicyEvaluation** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell para invocar Directivas de configuración de área expuesta.</span><span class="sxs-lookup"><span data-stu-id="f14e0-131">Use the **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell cmdlet to invoke Surface Area Configuration Policies.</span></span> <span data-ttu-id="f14e0-132">Para obtener más información, vea [Utilizar los cmdlets del motor de base de datos](../../database-engine/use-the-database-engine-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="f14e0-132">For more information, see [Use the Database Engine cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span></span>  
  
## <a name="soap-and-service-broker-endpoints"></a><span data-ttu-id="f14e0-133">Extremos SOAP y de Service Broker</span><span class="sxs-lookup"><span data-stu-id="f14e0-133">SOAP and Service Broker Endpoints</span></span>  
 <span data-ttu-id="f14e0-134">Para desactivar los extremos, use la Administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="f14e0-134">To turn endpoints off, use Policy-Based Management.</span></span> <span data-ttu-id="f14e0-135">Para crear y modificar las propiedades de los puntos de conexión, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) y [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f14e0-135">To create and alter the properties of endpoints, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) and [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f14e0-136">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f14e0-136">Related Content</span></span>  
 [<span data-ttu-id="f14e0-137">Centro de seguridad para el Motor de base de datos de SQL Server y Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="f14e0-137">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="f14e0-138">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f14e0-138">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
