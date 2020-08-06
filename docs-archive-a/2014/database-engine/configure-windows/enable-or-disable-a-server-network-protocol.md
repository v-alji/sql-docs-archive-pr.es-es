---
title: Habilitar o deshabilitar un protocolo de red de servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], disabling
- remote connections [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], disabling using Configuration Manager
- disabling network protocols, Configuration Manager
- network protocols [SQL Server], enabling
- enabling network protocols, Configuration Manager
- surface area configuration [SQL Server], connection protocols
- connections [SQL Server], enabling remote using Configuration Manager
ms.assetid: ec5ccb69-61c9-4576-8843-014b976fd46e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 737edae84ff284ed726ade69cb48e574b830611e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745966"
---
# <a name="enable-or-disable-a-server-network-protocol"></a><span data-ttu-id="c181e-102">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="c181e-102">Enable or Disable a Server Network Protocol</span></span>
  <span data-ttu-id="c181e-103">Todos los protocolos de red se instalan con el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pero se pueden habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="c181e-103">All network protocols are installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, but may or may not be enabled.</span></span> <span data-ttu-id="c181e-104">En este tema se describe cómo habilitar o deshabilitar un protocolo de red de servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c181e-104">This topic describes how to enable or disable a server network protocol in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or PowerShell.</span></span> <span data-ttu-id="c181e-105">Es preciso detener y reiniciar el [!INCLUDE[ssDE](../../includes/ssde-md.md)] para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="c181e-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be stopped and restarted for the change to take effect.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c181e-106">Durante la instalación de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se agrega un inicio de sesión para el grupo BUILTIN\Users.</span><span class="sxs-lookup"><span data-stu-id="c181e-106">During setup of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] a login is added for the BUILTIN\Users group.</span></span> <span data-ttu-id="c181e-107">Esto permite que todos los usuarios autenticados del equipo tengan acceso a la instancia de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] como un miembro del rol public.</span><span class="sxs-lookup"><span data-stu-id="c181e-107">This allows all authenticated users of the computer to access the instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] as a member of the public role.</span></span> <span data-ttu-id="c181e-108">El inicio de sesión BUILTIN\Users se pueden quitar de manera segura para restringir el acceso al [!INCLUDE[ssDE](../../includes/ssde-md.md)] a los usuarios de equipos que tienen inicios de sesión individuales o son miembros de otros grupos de Windows con inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="c181e-108">The BUILTIN\Users login can be safely removed to restrict [!INCLUDE[ssDE](../../includes/ssde-md.md)] access to computer users who have individual logins or are members of other Windows groups with logins.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c181e-109">Los proveedores de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y [!INCLUDE[msCoName](../../includes/msconame-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admiten TLS 1.0 y SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="c181e-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] data providers for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support TLS 1.0 and SSL 3.0.</span></span> <span data-ttu-id="c181e-110">Si fuerza un protocolo diferente (como por ejemplo, TLS 1.1 o TLS 1.2) realizando cambios en la capa SChannel del sistema operativo, las conexiones a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podrían no funcionar como es debido.</span><span class="sxs-lookup"><span data-stu-id="c181e-110">If you enforce a different protocol (such as TLS 1.1 or TLS 1.2) by making changes in the operating system SChannel layer, your connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might fail.</span></span>  
  
 <span data-ttu-id="c181e-111">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c181e-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c181e-112">**Para habilitar o deshabilitar un protocolo de red de servidor mediante:**</span><span class="sxs-lookup"><span data-stu-id="c181e-112">**To enable or disable a server network protocol using:**</span></span>  
  
     [<span data-ttu-id="c181e-113">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c181e-113">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c181e-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c181e-114">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c181e-115">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c181e-115">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-a-server-network-protocol"></a><span data-ttu-id="c181e-116">Para habilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="c181e-116">To enable a server network protocol</span></span>  
  
1.  <span data-ttu-id="c181e-117">En el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en el panel de la consola, expanda **Configuración de red de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c181e-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, expand **SQL Server  Network Configuration**.</span></span>  
  
2.  <span data-ttu-id="c181e-118">En el panel de la consola, haga clic en **Protocolos de** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="c181e-118">In the console pane, click **Protocols for** *\<instance name>*.</span></span>  
  
3.  <span data-ttu-id="c181e-119">En el panel de detalles, haga clic con el botón derecho en el protocolo que quiera cambiar y, después, haga clic en **Habilitar** o **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="c181e-119">In the details pane, right-click the protocol you want to change, and then click **Enable** or **Disable**.</span></span>  
  
4.  <span data-ttu-id="c181e-120">En el panel de la consola, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c181e-120">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="c181e-121">En el panel de detalles, haga clic con el botón secundario en **SQL Server ( ***\<instance name>*** )** y, a continuación, haga clic en **reiniciar**para detener y reiniciar el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio.</span><span class="sxs-lookup"><span data-stu-id="c181e-121">In the details pane, right-click **SQL Server (***\<instance name>***)**, and then click **Restart**, to stop and restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
##  <a name="using-sql-server-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c181e-122">Usar SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c181e-122">Using SQL Server PowerShell</span></span>  
  
#### <a name="to-enable-a-server-network-protocol-using-powershell"></a><span data-ttu-id="c181e-123">Para habilitar un protocolo de red de servidor mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="c181e-123">To Enable a Server Network Protocol Using PowerShell</span></span>  
  
1.  <span data-ttu-id="c181e-124">Abra un símbolo del sistema utilizando permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="c181e-124">Using administrator permissions open a command prompt.</span></span>  
  
2.  <span data-ttu-id="c181e-125">Inicie Windows PowerShell 2.0 desde la barra de tareas, o haga clic en Inicio, en Todos los programas, en Accesorios, en Windows PowerShell y, por último, en Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c181e-125">Start Windows PowerShell 2.0 from the taskbar, or click Start, then All Programs, then Accessories, then Windows PowerShell, then Windows PowerShell.</span></span>  
  
3.  <span data-ttu-id="c181e-126">Importe el módulo **sqlps** escribiendo`Import-Module "sqlps"`</span><span class="sxs-lookup"><span data-stu-id="c181e-126">Import the **sqlps** module by entering `Import-Module "sqlps"`</span></span>  
  
4.  <span data-ttu-id="c181e-127">Ejecute las siguientes instrucciones para habilitar los protocolos TCP y de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="c181e-127">Execute the following statements to enable both the TCP and named pipes protocols.</span></span> <span data-ttu-id="c181e-128">Reemplace `<computer_name>` por el nombre del equipo que ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c181e-128">Replace `<computer_name>` with the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c181e-129">Si va a configurar una instancia con nombre, sustituya `MSSQLSERVER` por el nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="c181e-129">If you are configuring a named instance, replace `MSSQLSERVER` with the instance name.</span></span>  
  
     <span data-ttu-id="c181e-130">Para deshabilitar los protocolos, establezca las propiedades `IsEnabled` en `$false`.</span><span class="sxs-lookup"><span data-stu-id="c181e-130">To disable protocols, set the `IsEnabled` properties to `$false`.</span></span>  
  
    ```powershell
    $smo = 'Microsoft.SqlServer.Management.Smo.'  
    $wmi = new-object ($smo + 'Wmi.ManagedComputer').  
  
    # List the object properties, including the instance names.  
    $Wmi  
  
    # Enable the TCP protocol on the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    $Tcp = $wmi.GetSmoObject($uri)  
    $Tcp.IsEnabled = $true  
    $Tcp.Alter()  
    $Tcp  
  
    # Enable the named pipes protocol for the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Np']"  
    $Np = $wmi.GetSmoObject($uri)  
    $Np.IsEnabled = $true  
    $Np.Alter()  
    $Np  
    ```  
  
#### <a name="to-configure-the-protocols-for-the-local-computer"></a><span data-ttu-id="c181e-131">Para configurar los protocolos en el equipo local</span><span class="sxs-lookup"><span data-stu-id="c181e-131">To configure the protocols for the local computer</span></span>  
  
-   <span data-ttu-id="c181e-132">Cuando el script se ejecuta localmente y configura el equipo local, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell puede hacer que el script sea más flexible al determinar dinámicamente el nombre del equipo local.</span><span class="sxs-lookup"><span data-stu-id="c181e-132">When the script is run locally and configures the local computer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell can make the script more flexible by dynamically determining the local computer name.</span></span> <span data-ttu-id="c181e-133">Para recuperar el nombre del equipo local, reemplace la línea donde se establece la variable `$uri` por la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="c181e-133">To retrieve the local computer name, replace the line setting the `$uri` variable with the following line.</span></span>  
  
    ```powershell
    $uri = "ManagedComputer[@Name='" + (Get-Item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    ```  
  
#### <a name="to-restart-the-database-engine-by-using-sql-server-powershell"></a><span data-ttu-id="c181e-134">Para reiniciar el motor de base de datos mediante SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c181e-134">To restart the Database Engine by using SQL Server PowerShell</span></span>  
  
-   <span data-ttu-id="c181e-135">Después de habilitar o deshabilitar protocolos, deberá detener y reiniciar [!INCLUDE[ssDE](../../includes/ssde-md.md)] para que se aplique el cambio.</span><span class="sxs-lookup"><span data-stu-id="c181e-135">After you enable or disable protocols, you must stop and restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for the change to take effect.</span></span> <span data-ttu-id="c181e-136">Ejecute las instrucciones siguientes para detener e iniciar la instancia predeterminada mediante [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c181e-136">Execute the following statements to stop and start the default instance by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span></span> <span data-ttu-id="c181e-137">Para detener e iniciar una instancia con nombre, sustituya `'MSSQLSERVER'` por `'MSSQL$<instance_name>'`.</span><span class="sxs-lookup"><span data-stu-id="c181e-137">To stop and start a named instance replace `'MSSQLSERVER'` with `'MSSQL$<instance_name>'`.</span></span>  
  
    ```powershell
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\<computer_name>  
    $Wmi = (Get-Item .).ManagedComputer  
    # Get a reference to the default instance of the Database Engine.  
    $DfltInstance = $Wmi.Services['MSSQLSERVER']  
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Start the service again.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache and display the state of the service.  
    $DfltInstance.Refresh(); $DfltInstance  
    ```  
