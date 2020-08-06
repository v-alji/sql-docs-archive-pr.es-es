---
title: Iniciar, detener, pausar, reanudar, reiniciar el servicio de Motor de base de datos, Agente SQL Server o SQL Server Browser | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, start and stop services
- stopping SQL Server Agent
- parameters [SQL Server], startup options
- SQL Server, startup options
- Database Engine [SQL Server], starting and stopping services
- pausing SQL Server
- PowerShell [SQL Server], starting and stopping services
- single-user mode [SQL Server], starting in
- SQL Server Management Studio [SQL Server], starting or stopping services
- stopping SQL Server Browser service
- starting SQL Server Agent
- default instances [SQL Server], starting and stopping
- SQL Server Agent, starting and stopping
- command prompt [SQL Server], starting and stopping SQL Server services
- continuing SQL Server
- starting SQL Server Database Engine
- net stop commands [SQL Server]
- command prompt [SQL Server], SQL Browser service
- Configuration Manager, start and stop services
- resuming SQL Server
- startup options [SQL Server]
- named instances [SQL Server], starting and stopping
- net start commands [SQL Server]
- SQL Server, starting and stopping
- stopping SQL Server
- starting SQL Server Browser service
- SQL Server Database Engine setting startup options
- administering SQL Server, starting and stopping services
- Management Studio [SQL Server], starting or stopping services
ms.assetid: 32660a02-e5a1-411a-9e57-7066ca459df6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f4b102c8fd81923d7386c8e556896e715311a07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748895"
---
# <a name="start-stop-pause-resume-restart-the-database-engine-sql-server-agent-or-sql-server-browser-service"></a><span data-ttu-id="7c551-102">Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="7c551-102">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>
  <span data-ttu-id="7c551-103">En este tema se describe cómo iniciar, comandos de detener, comandos de pausar, comandos de reanudar o reiniciar [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], comandos de el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser mediante el uso del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , comandos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], comandos de **net** desde un símbolo del sistema, comandos de [!INCLUDE[tsql](../../includes/tsql-md.md)], comandos de or PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c551-103">This topic describes how to start, stop, pause, resume, or restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **net** commands from a command prompt, [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
-   <span data-ttu-id="7c551-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7c551-104">**Before you begin:**</span></span>  
  
    -   [<span data-ttu-id="7c551-105">¿Cuáles son estos servicios?</span><span class="sxs-lookup"><span data-stu-id="7c551-105">What are these services?</span></span>](#Services)  
  
    -   [<span data-ttu-id="7c551-106">Información adicional</span><span class="sxs-lookup"><span data-stu-id="7c551-106">Additional Information</span></span>](#MoreInformation)  
  
    -   [<span data-ttu-id="7c551-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7c551-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7c551-108">**Instrucciones mediante:**</span><span class="sxs-lookup"><span data-stu-id="7c551-108">**Instructions using:**</span></span>  
  
    -   [<span data-ttu-id="7c551-109">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c551-109">SQL Server Configuration Manager</span></span>](#SSCMProcedure)  
  
    -   [<span data-ttu-id="7c551-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c551-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   [<span data-ttu-id="7c551-111">Comandos net desde una ventana del símbolo de sistema</span><span class="sxs-lookup"><span data-stu-id="7c551-111">net Commands from a Command Prompt window</span></span>](#CommandPrompt)  
  
    -   [<span data-ttu-id="7c551-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c551-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   [<span data-ttu-id="7c551-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c551-113">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7c551-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7c551-114">Before You Begin</span></span>  
  
###  <a name="what-is-the-ssdenoversion-service-the-ssnoversion-agent-service-and-the-ssnoversion-browser-service"></a><a name="Services"></a> <span data-ttu-id="7c551-115">¿Qué es el servicio [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser?</span><span class="sxs-lookup"><span data-stu-id="7c551-115">What is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7c551-116">son programas ejecutables que funcionan como un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="7c551-116">components are executable programs that run as a Windows service.</span></span> <span data-ttu-id="7c551-117">Los programas que se ejecutan como servicio de Windows pueden seguir funcionando sin mostrar actividad alguna en la pantalla del equipo.</span><span class="sxs-lookup"><span data-stu-id="7c551-117">Programs that run as a Windows service can continue to operate without displaying any activity on the computer screen.</span></span>  
  
 <span data-ttu-id="7c551-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)]servicio**</span><span class="sxs-lookup"><span data-stu-id="7c551-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)] service**</span></span>  
 <span data-ttu-id="7c551-119">El proceso ejecutable que es [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-119">The executable process that is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="7c551-120">[!INCLUDE[ssDE](../../includes/ssde-md.md)] puede ser la instancia predeterminada (límite de una por equipo) o puede ser una de las numerosas instancias con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-120">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be the default instance (limit one per computer), or can be one of many named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="7c551-121">Use el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para determinar las instancias de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7c551-121">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to determine which instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] are installed on the computer.</span></span> <span data-ttu-id="7c551-122">La instancia predeterminada (si la instala) aparece como \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)\*\*.</span><span class="sxs-lookup"><span data-stu-id="7c551-122">The default instance (if you install it) is listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)**.</span></span> <span data-ttu-id="7c551-123">Las instancias con nombre (si las instala) aparecen como \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)\*\*.</span><span class="sxs-lookup"><span data-stu-id="7c551-123">Named instances (if you install them) are listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)**.</span></span> <span data-ttu-id="7c551-124">De forma predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express se instala como \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)\*\*.</span><span class="sxs-lookup"><span data-stu-id="7c551-124">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express is installed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)**.</span></span>  
  
 <span data-ttu-id="7c551-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Servicio del agente**</span><span class="sxs-lookup"><span data-stu-id="7c551-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service**</span></span>  
 <span data-ttu-id="7c551-126">Servicio de Windows que ejecuta tareas administrativas programadas, denominadas trabajos y alertas.</span><span class="sxs-lookup"><span data-stu-id="7c551-126">A Windows service that executes scheduled administrative tasks, which are called jobs and alerts.</span></span> <span data-ttu-id="7c551-127">Para obtener más información, consulte [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="7c551-127">For more information, see [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7c551-128">no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-128">Agent is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7c551-129">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7c551-129">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="7c551-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Servicio Browser**</span><span class="sxs-lookup"><span data-stu-id="7c551-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service**</span></span>  
 <span data-ttu-id="7c551-131">Servicio de Windows que escucha las solicitudes entrantes de recursos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proporciona a los clientes información acerca de las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7c551-131">A Windows service that listens for incoming requests for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides clients information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span> <span data-ttu-id="7c551-132">Una sola instancia del servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser se usa para todas las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7c551-132">A single instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is used for all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer.</span></span>  
  
###  <a name="additional-information"></a><a name="MoreInformation"></a><span data-ttu-id="7c551-133">Información adicional</span><span class="sxs-lookup"><span data-stu-id="7c551-133">Additional Information</span></span>  
  
-   <span data-ttu-id="7c551-134">Al pausar el servicio [!INCLUDE[ssDE](../../includes/ssde-md.md)] se impide que los nuevos usuarios se conecten a [!INCLUDE[ssDE](../../includes/ssde-md.md)], pero los que ya estén conectados pueden seguir trabajando hasta que sus conexiones se interrumpan.</span><span class="sxs-lookup"><span data-stu-id="7c551-134">Pausing the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service prevents new users from connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but users who are already connected can continue to work until their connections are broken.</span></span> <span data-ttu-id="7c551-135">Use la pausa cuando desee esperar a que los usuarios completen su trabajo antes de detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="7c551-135">Use pause when you want to wait for users to complete work before you stop the service.</span></span> <span data-ttu-id="7c551-136">Esto les permite completar las transacciones que están en curso.</span><span class="sxs-lookup"><span data-stu-id="7c551-136">This enables them to complete transactions that are in progress.</span></span> <span data-ttu-id="7c551-137">La reanudación permite que [!INCLUDE[ssDE](../../includes/ssde-md.md)] vuelva a aceptar nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="7c551-137">Resume allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to accept new connections again.</span></span> <span data-ttu-id="7c551-138">El servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede pausar o reanudar.</span><span class="sxs-lookup"><span data-stu-id="7c551-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service cannot be paused or resumed.</span></span>  
  
-   <span data-ttu-id="7c551-139">El Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] muestran el estado actual de los servicios mediante el uso de los siguientes iconos.</span><span class="sxs-lookup"><span data-stu-id="7c551-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] display the current status of services by using the following icons.</span></span>  
  
     <span data-ttu-id="7c551-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="7c551-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager**</span></span>  
  
    -   <span data-ttu-id="7c551-141">La flecha verde del icono situado junto al nombre del servicio indica que el servicio está iniciado.</span><span class="sxs-lookup"><span data-stu-id="7c551-141">A green arrow on the icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="7c551-142">El cuadrado rojo del icono situado junto al nombre del servicio indica que el servicio está detenido.</span><span class="sxs-lookup"><span data-stu-id="7c551-142">A red square on the icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="7c551-143">Dos líneas azules verticales en el icono situado junto al nombre del servicio indica que el servicio está pausado.</span><span class="sxs-lookup"><span data-stu-id="7c551-143">Two vertical blue lines on the icon next to the service name indicates that the service is paused.</span></span>  
  
    -   <span data-ttu-id="7c551-144">Al reiniciar [!INCLUDE[ssDE](../../includes/ssde-md.md)], un cuadrado rojo indicará que el servicio se detuvo y una flecha verde indicará que el servicio se inició correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c551-144">When restarting the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a red square will indicate that the service stopped, and then a green arrow will indicate that he service started successfully.</span></span>  
  
     **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
    -   <span data-ttu-id="7c551-145">La flecha blanca sobre un icono de círculo verde situado junto al nombre del servicio indica que el servicio está iniciado.</span><span class="sxs-lookup"><span data-stu-id="7c551-145">A white arrow on a green circle icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="7c551-146">El cuadrado blanco sobre un icono de círculo rojo situado junto al nombre del servicio indica que el servicio está detenido.</span><span class="sxs-lookup"><span data-stu-id="7c551-146">A white square on a red circle icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="7c551-147">Dos líneas blancas verticales sobre un icono de círculo azul situado junto al nombre del servicio indica que el servicio está pausado.</span><span class="sxs-lookup"><span data-stu-id="7c551-147">Two vertical white lines on a blue circle icon next to the service name indicates that the service is paused.</span></span>  
  
-   <span data-ttu-id="7c551-148">Al usar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], solo estarán disponibles las opciones que son posibles.</span><span class="sxs-lookup"><span data-stu-id="7c551-148">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], only options that are possible will be available.</span></span> <span data-ttu-id="7c551-149">Por ejemplo, si el servicio ya está iniciado, **Iniciar** no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="7c551-149">For example, if the service is already started, **Start** will be unavailable.</span></span>  
  
-   <span data-ttu-id="7c551-150">Al ejecutar en un clúster, el servicio [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] se administra mejor mediante el Administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="7c551-150">When running on a cluster, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service is best managed by using Cluster Administrator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7c551-151">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7c551-151">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7c551-152">Permisos</span><span class="sxs-lookup"><span data-stu-id="7c551-152">Permissions</span></span>  
 <span data-ttu-id="7c551-153">De forma predeterminada, solo los miembros del grupo local de administradores pueden iniciar, detener, pausar, reanudar o reiniciar un servicio.</span><span class="sxs-lookup"><span data-stu-id="7c551-153">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="7c551-154">Para conceder la capacidad de administrar servicios a usuarios que no son administradores, vea [CÓMO: Conceder a los usuarios derechos para administrar servicios en la familia Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="7c551-154">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="7c551-155">El proceso es similar en las demás versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="7c551-155">(The process is similar on other versions of Windows.)</span></span>  
  
 <span data-ttu-id="7c551-156">La detención de [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante el [!INCLUDE[tsql](../../includes/tsql-md.md)] `SHUTDOWN` comando requiere la pertenencia a los roles fijos de servidor **sysadmin** o **ServerAdmin** , y no se pueden transferir.</span><span class="sxs-lookup"><span data-stu-id="7c551-156">Stopping the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)]`SHUTDOWN` command requires membership in the **sysadmin** or **serveradmin** fixed server roles, and is not transferable.</span></span>  
  
##  <a name="using-ssnoversion-configuration-manager"></a><a name="SSCMProcedure"></a> <span data-ttu-id="7c551-157">Usar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-157">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="7c551-158">Para iniciar, detener, pausar, reanudar o reiniciar una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-158">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="7c551-159">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7c551-159">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="7c551-160">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7c551-160">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="7c551-161">En el panel izquierdo del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7c551-161">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="7c551-162">En el panel de resultados, haga clic con el botón derecho en **SQL Server (MSSQLServer)** o en una instancia con nombre y luego haga clic en **Iniciar**, **Detener**, **Pausar**, **Reanudar**o **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="7c551-162">In the results pane, right-click **SQL Server (MSSQLServer)** or a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="7c551-163">Haga clic en **Aceptar** para cerrar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c551-163">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c551-164">Para iniciar una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con opciones de inicio, vea [Configurar opciones de inicio del servidor &#40;Administrador de configuración de SQL Server&#41;](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="7c551-164">To start an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with startup options, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-ssnoversion-browser-or-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="7c551-165">Para iniciar, detener, pausar, reanudar o reiniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser o una instancia de Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-165">To start, stop, pause, resume, or restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser or an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="7c551-166">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7c551-166">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="7c551-167">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7c551-167">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="7c551-168">En el panel izquierdo del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7c551-168">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="7c551-169">En el panel de resultados, haga clic con el botón derecho en \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Explorador**, o \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente (MSSQLServer)** o \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente (<instance_name>)\*\* para una instancia con nombre y, a continuación, haga clic en **iniciar**, **detener**, **pausar**, **reanudar**o **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="7c551-169">In the results pane, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**, or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)** for a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="7c551-170">Haga clic en **Aceptar** para cerrar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c551-170">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c551-171">El Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede pausar.</span><span class="sxs-lookup"><span data-stu-id="7c551-171">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot be paused.</span></span>  
  
##  <a name="using-ssnoversion-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7c551-172">Usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c551-172">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="7c551-173">Para iniciar, detener, pausar, reanudar o reiniciar una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-173">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="7c551-174">En el Explorador de objetos, conéctese a la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)], haga clic con el botón derecho en la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que quiere iniciar y luego haga clic en **Iniciar**, **Detener**, **Pausar**, **Reanudar**o **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="7c551-174">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
     <span data-ttu-id="7c551-175">O bien, en Servidores registrados, haga clic con el botón derecho en la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que quiere iniciar, seleccione **Control de servicios**y, luego, haga clic en **Iniciar**, **Detener**, **Pausar**, **Reanudar**o **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="7c551-175">Or, in Registered Servers, right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, point to **Service Control**, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="7c551-176">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7c551-176">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="7c551-177">Cuando se le pregunte si desea realizar la acción, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7c551-177">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
#### <a name="to-start-stop-or-restart-the-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="7c551-178">Para iniciar, detener o reiniciar una instancia del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-178">To start, stop, or restart the an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="7c551-179">En Explorador de objetos, conéctese a la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] , haga clic con el botón secundario en \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente\*\*y, a continuación, haga clic en **iniciar**, **detener**o **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="7c551-179">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent**, and then click **Start**, **Stop**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="7c551-180">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7c551-180">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="7c551-181">Cuando se le pregunte si desea realizar la acción, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7c551-181">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
##  <a name="from-the-command-prompt-window-using-net-commands"></a><a name="CommandPrompt"></a> <span data-ttu-id="7c551-182">Desde la ventana del símbolo del sistema con los comandos net</span><span class="sxs-lookup"><span data-stu-id="7c551-182">From the Command Prompt Window using net Commands</span></span>  
 <span data-ttu-id="7c551-183">Los servicios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se pueden iniciar, detener o pausar mediante comandos **net** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="7c551-183">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services can be started, stopped, or paused by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **net** commands.</span></span>  
  
###  <a name="to-start-the-default-instance-of-the-ssde"></a><a name="dbDefault"></a> <span data-ttu-id="7c551-184">Para iniciar la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-184">To start the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="7c551-185">En el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="7c551-185">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="7c551-186">**net start "SQL Server (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="7c551-186">**net start "SQL Server (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="7c551-187">O bien</span><span class="sxs-lookup"><span data-stu-id="7c551-187">-or-</span></span>  
  
     <span data-ttu-id="7c551-188">**net start MSSQLSERVER**</span><span class="sxs-lookup"><span data-stu-id="7c551-188">**net start MSSQLSERVER**</span></span>  
  
###  <a name="to-start-a-named-instance-of-the-ssde"></a><a name="dbNamed"></a> <span data-ttu-id="7c551-189">Para iniciar una instancia con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-189">To start a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="7c551-190">En el símbolo del sistema, escriba uno de los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="7c551-190">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="7c551-191">Sustituya *\<instancename>* por el nombre de la instancia que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="7c551-191">Replace *\<instancename>* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="7c551-192">**net start "SQL Server (** *instancename* **)"**</span><span class="sxs-lookup"><span data-stu-id="7c551-192">**net start "SQL Server (** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="7c551-193">O bien</span><span class="sxs-lookup"><span data-stu-id="7c551-193">-or-</span></span>  
  
     <span data-ttu-id="7c551-194">**net start MSSQL$** *instancename*</span><span class="sxs-lookup"><span data-stu-id="7c551-194">**net start MSSQL$** *instancename*</span></span>  
  
###  <a name="to-start-the-ssde-with-startup-options"></a><a name="dbStartup"></a> <span data-ttu-id="7c551-195">Para iniciar [!INCLUDE[ssDE](../../includes/ssde-md.md)] con opciones de inicio</span><span class="sxs-lookup"><span data-stu-id="7c551-195">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] with startup options</span></span>  
  
-   <span data-ttu-id="7c551-196">Agregue las opciones de inicio al final de la instrucción **net start "SQL Server (MSSQLSERVER)"** , separadas por un espacio.</span><span class="sxs-lookup"><span data-stu-id="7c551-196">Add startup options to the end of the **net start "SQL Server (MSSQLSERVER)"** statement, separated by a space.</span></span> <span data-ttu-id="7c551-197">Cuando se inicia mediante **net start**, las opciones de inicio usan una barra (/) en lugar de un guión (-).</span><span class="sxs-lookup"><span data-stu-id="7c551-197">When started using **net start**, startup options use a slash (/) instead of a hyphen (-).</span></span>  
  
     <span data-ttu-id="7c551-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span><span class="sxs-lookup"><span data-stu-id="7c551-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span></span>  
  
     <span data-ttu-id="7c551-199">O bien</span><span class="sxs-lookup"><span data-stu-id="7c551-199">-or-</span></span>  
  
     <span data-ttu-id="7c551-200">**net start MSSQLSERVER /f /m**</span><span class="sxs-lookup"><span data-stu-id="7c551-200">**net start MSSQLSERVER /f /m**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c551-201">Para obtener más información sobre las opciones de inicio del servicio, vea [Opciones de inicio del servicio de motor de base de datos](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="7c551-201">For more information about startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-the-default-instance-of-ssnoversion"></a><a name="agDefault"></a> <span data-ttu-id="7c551-202">Para iniciar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-202">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="7c551-203">En el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="7c551-203">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="7c551-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="7c551-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="7c551-205">O bien</span><span class="sxs-lookup"><span data-stu-id="7c551-205">-or-</span></span>  
  
     <span data-ttu-id="7c551-206">**net start SQLSERVERAGENT**</span><span class="sxs-lookup"><span data-stu-id="7c551-206">**net start SQLSERVERAGENT**</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-a-named-instance-of-ssnoversion"></a><a name="agNamed"></a> <span data-ttu-id="7c551-207">Para iniciar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una instancia con nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-207">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="7c551-208">En el símbolo del sistema, escriba uno de los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="7c551-208">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="7c551-209">Sustituya *instancename* por el nombre de la instancia que quiere administrar.</span><span class="sxs-lookup"><span data-stu-id="7c551-209">Replace *instancename* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="7c551-210">**net start "SQL Server Agent(** *instancename* **)"**</span><span class="sxs-lookup"><span data-stu-id="7c551-210">**net start "SQL Server Agent(** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="7c551-211">O bien</span><span class="sxs-lookup"><span data-stu-id="7c551-211">-or-</span></span>  
  
     <span data-ttu-id="7c551-212">**net start SQLAgent$** *instancename*</span><span class="sxs-lookup"><span data-stu-id="7c551-212">**net start SQLAgent$** *instancename*</span></span>  
  
 <span data-ttu-id="7c551-213">Para obtener información sobre cómo ejecutar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo detallado para la solución de problemas, vea [sqlagent90 (aplicación)](../../tools/sqlagent90-application.md).</span><span class="sxs-lookup"><span data-stu-id="7c551-213">For information about how to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in verbose mode for troubleshooting, see [sqlagent90 Application](../../tools/sqlagent90-application.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-browser"></a><a name="Browser"></a> <span data-ttu-id="7c551-214">Para iniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="7c551-214">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span></span>  
  
-   <span data-ttu-id="7c551-215">En el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="7c551-215">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="7c551-216">**net start "SQL Server Browser"**</span><span class="sxs-lookup"><span data-stu-id="7c551-216">**net start "SQL Server Browser"**</span></span>  
  
     <span data-ttu-id="7c551-217">O bien</span><span class="sxs-lookup"><span data-stu-id="7c551-217">-or-</span></span>  
  
     <span data-ttu-id="7c551-218">**net start SQLBrowser**</span><span class="sxs-lookup"><span data-stu-id="7c551-218">**net start SQLBrowser**</span></span>  
  
###  <a name="to-pause-or-stop-services-from-the-command-prompt-window"></a><a name="pauseStop"></a> <span data-ttu-id="7c551-219">Para pausar o detener los servicios desde la ventana del símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="7c551-219">To pause or stop services from the Command Prompt window</span></span>  
  
-   <span data-ttu-id="7c551-220">Para pausar o detener servicios, modifique los comandos de las formas que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="7c551-220">To pause or stop services modify the commands in the following ways.</span></span>  
  
    -   <span data-ttu-id="7c551-221">Para pausar un servicio, reemplace **net start** por **net pause**.</span><span class="sxs-lookup"><span data-stu-id="7c551-221">To pause a service, replace **net start** with **net pause**.</span></span>  
  
    -   <span data-ttu-id="7c551-222">Para detener un servicio, reemplace **net start** por **net stop**.</span><span class="sxs-lookup"><span data-stu-id="7c551-222">To stop a service, replace **net start** with use **net stop**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7c551-223">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c551-223">Using Transact-SQL</span></span>  
 <span data-ttu-id="7c551-224">[!INCLUDE[ssDE](../../includes/ssde-md.md)] se puede detener mediante la instrucción `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="7c551-224">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be stopped by using the `SHUTDOWN` statement.</span></span>  
  
#### <a name="to-stop-the-ssde-using-tsql"></a><span data-ttu-id="7c551-225">Para detener [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-225">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
-   <span data-ttu-id="7c551-226">Para esperar a que finalicen las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y los procedimientos almacenados que se encuentran en ejecución y, a continuación, detener [!INCLUDE[ssDE](../../includes/ssde-md.md)], ejecute la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c551-226">To wait for currently running [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and stored procedures to finish, and then stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN;   
    ```  
  
-   <span data-ttu-id="7c551-227">Para detener [!INCLUDE[ssDE](../../includes/ssde-md.md)] inmediatamente, ejecute la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c551-227">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] immediately, execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN WITH NOWAIT;   
    ```  
  
 <span data-ttu-id="7c551-228">Para obtener más información acerca de la `SHUTDOWN` instrucción, vea [Shutdown &#40;TRANSACT-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7c551-228">For more information about the `SHUTDOWN` statement, see [SHUTDOWN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="7c551-229">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c551-229">Using PowerShell</span></span>  
  
#### <a name="to-start-and-stop-ssde-services"></a><span data-ttu-id="7c551-230">Para iniciar y detener servicios de [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c551-230">To start and stop [!INCLUDE[ssDE](../../includes/ssde-md.md)] services</span></span>  
  
1.  <span data-ttu-id="7c551-231">En una ventana del símbolo del sistema, inicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell con el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c551-231">In a Command Prompt window, start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell by executing the following command.</span></span>  
  
    ```ms-dos  
    sqlps  
    ```  
  
2.  <span data-ttu-id="7c551-232">En un símbolo del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ejecutando el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c551-232">At a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell command prompt, by executing the following command.</span></span> <span data-ttu-id="7c551-233">Reemplace `computername` por el nombre de su equipo.</span><span class="sxs-lookup"><span data-stu-id="7c551-233">Replace `computername` with the name of your computer.</span></span>  
  
    ```powershell  
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\computername  
    $Wmi = (Get-Item .).ManagedComputer
    ```  
  
3.  <span data-ttu-id="7c551-234">Identifique el servicio que desea detener o iniciar.</span><span class="sxs-lookup"><span data-stu-id="7c551-234">Identify the service that you want to stop or start.</span></span> <span data-ttu-id="7c551-235">Elija una de las líneas siguientes.</span><span class="sxs-lookup"><span data-stu-id="7c551-235">Pick one of the following lines.</span></span> <span data-ttu-id="7c551-236">Reemplace `instancename` por el nombre de la instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="7c551-236">Replace `instancename` with the name of the named instance.</span></span>  
  
    -   <span data-ttu-id="7c551-237">Para obtener una referencia a la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-237">To get a reference to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQLSERVER']  
        ```  
  
    -   <span data-ttu-id="7c551-238">Para obtener una referencia a una instancia con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-238">To get a reference to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQL$instancename']  
        ```  
  
    -   <span data-ttu-id="7c551-239">Para obtener una referencia al servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-239">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLSERVERAGENT']  
        ```  
  
    -   <span data-ttu-id="7c551-240">Para obtener una referencia al servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una instancia con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c551-240">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLAGENT$instancename']  
        ```  
  
    -   <span data-ttu-id="7c551-241">Para obtener una referencia al servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="7c551-241">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLBROWSER']  
        ```  
  
4.  <span data-ttu-id="7c551-242">Complete el ejemplo para iniciar y detener el servicio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7c551-242">Complete the example to start and then stop the selected service.</span></span>  
  
    ```powershell  
    # Display the state of the service.  
    $DfltInstance  
    # Start the service.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7c551-243">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c551-243">See Also</span></span>  
 <span data-ttu-id="7c551-244">[Iniciar SQL Server con la configuración mínima](start-sql-server-with-minimal-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7c551-244">[Start SQL Server with Minimal Configuration](start-sql-server-with-minimal-configuration.md) </span></span>  
 [<span data-ttu-id="7c551-245">Características admitidas por las ediciones de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7c551-245">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
