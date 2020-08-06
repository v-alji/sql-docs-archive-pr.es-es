---
title: Cmdlets de PowerShell para el modo Reporting Services SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7835bc97-2827-4215-b0dd-52f692ce5e02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b20ad870fd8a9cd7f220eebb2b954d7a88a10c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751794"
---
# <a name="powershell-cmdlets-for-reporting-services-sharepoint-mode"></a><span data-ttu-id="2cb97-102">Cmdlets de PowerShell para el modo de SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cb97-102">PowerShell cmdlets for Reporting Services SharePoint Mode</span></span>
  <span data-ttu-id="2cb97-103">Al instalar el [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modo de SharePoint de, se instalan los cmdlets de PowerShell para admitir servidores de informes en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb97-103">When you install [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode, PowerShell cmdlets are installed to support report Servers in SharePoint mode.</span></span> <span data-ttu-id="2cb97-104">Los cmdlets abarcan tres categorías de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2cb97-104">The cmdlets cover three categories of functionality.</span></span>  
  
-   <span data-ttu-id="2cb97-105">La instalación del proxy y el servicio compartido de SharePoint de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-105">Installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service and proxy.</span></span>  
  
-   <span data-ttu-id="2cb97-106">El aprovisionamiento y administración de las aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y servidores proxy asociados.</span><span class="sxs-lookup"><span data-stu-id="2cb97-106">Provisioning and management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and associated proxies.</span></span>  
  
-   <span data-ttu-id="2cb97-107">La administración de las características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como las extensiones y las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="2cb97-107">Management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features, for example extensions and encryption keys.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../includes/applies-md.md)]<span data-ttu-id="2cb97-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cb97-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>|  
  
 <span data-ttu-id="2cb97-109">**Este tema contiene lo siguiente:**</span><span class="sxs-lookup"><span data-stu-id="2cb97-109">**This topic contains the following:**</span></span>  
  
-   [<span data-ttu-id="2cb97-110">Resumen de cmdlets</span><span class="sxs-lookup"><span data-stu-id="2cb97-110">Cmdlet Summary</span></span>](#bkmk_cmdlet_sum)  
  
-   [<span data-ttu-id="2cb97-111">Cmdlets de servicios compartidos y proxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-111">Shared Service and Proxy Cmdlets</span></span>](#bkmk_sharedservice_cmdlets)  
  
-   [<span data-ttu-id="2cb97-112">Cmdlets de aplicación de servicio y proxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-112">Service Application and Proxy Cmdlets</span></span>](#bkmk_serviceapp_cmdlets)  
  
-   [<span data-ttu-id="2cb97-113">Cmdlets de funcionalidad personalizada de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cb97-113">Reporting Services Custom Functionality Cmdlets</span></span>](#bkmk_ssrsfeatures_cmdlets)  
  
-   [<span data-ttu-id="2cb97-114">Ejemplos básicos</span><span class="sxs-lookup"><span data-stu-id="2cb97-114">Basic Samples</span></span>](#bkmk_basic_samples)  
  
-   [<span data-ttu-id="2cb97-115">Ejemplos detallados</span><span class="sxs-lookup"><span data-stu-id="2cb97-115">Detailed Samples</span></span>](#bkmk_detailedsamples)  
  
    -   [<span data-ttu-id="2cb97-116">Creación de una aplicación de servicio de Reporting Services y proxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-116">Create a Reporting Services service application and proxy</span></span>](#bkmk_example_create_service_application)  
  
    -   [<span data-ttu-id="2cb97-117">Revisar y actualizar una extensión de entrega de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cb97-117">Review and update a Reporting Services delivery extension</span></span>](#bkmk_example_delivery_extension)  
  
    -   [<span data-ttu-id="2cb97-118">Obtener y establecer las propiedades de la base de datos de aplicación de Reporting Services como, por ejemplo, el tiempo de espera de la base de datos</span><span class="sxs-lookup"><span data-stu-id="2cb97-118">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>](#bkmk_example_db_properties)  
  
    -   [<span data-ttu-id="2cb97-119">Enumerar extensiones de datos de Reporting Services-modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cb97-119">List reporting services data extensions - SharePoint mode</span></span>](#bkmk_example_list_data_extensions)  
  
    -   [<span data-ttu-id="2cb97-120">Cambiar propietarios de suscripciones y agregarlos a listas</span><span class="sxs-lookup"><span data-stu-id="2cb97-120">Change and list subscription owners</span></span>](#bkmk_change_subscription_owner)  
  
##  <a name="cmdlet-summary"></a><a name="bkmk_cmdlet_sum"></a><span data-ttu-id="2cb97-121">Resumen de cmdlets</span><span class="sxs-lookup"><span data-stu-id="2cb97-121">Cmdlet Summary</span></span>  

 <span data-ttu-id="2cb97-122">Para ejecutar los cmdlets es necesario abrir el Shell de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb97-122">To run the cmdlets you need to open the SharePoint Management Shell.</span></span> <span data-ttu-id="2cb97-123">También puede usar el editor de la interfaz gráfica de usuario incluido en Microsoft Windows, **Entorno de scripting integrado (ISE) de Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2cb97-123">You can also use the graphical user interface editor that is included with Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span></span> <span data-ttu-id="2cb97-124">Para más información, vea [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cb97-124">For more information, see [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span></span> <span data-ttu-id="2cb97-125">En los siguientes resúmenes de cmdlet, las referencias a las bases de datos de la aplicación de servicio, hacen referencia a todas las bases de datos creadas y usadas por una [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="2cb97-125">In the following cmdlet summaries, the references to service application 'databases', refer to all of the databases created and used by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="2cb97-126">Esto incluye la configuración, la creación de alertas y las bases de datos temporales.</span><span class="sxs-lookup"><span data-stu-id="2cb97-126">This includes the configuration, alerting, and temp databases.</span></span>  

  
 <span data-ttu-id="2cb97-127">Si ve un mensaje de error similar al siguiente al escribir los ejemplos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2cb97-127">If you see an error message similar to the following when you type the PowerShell examples:</span></span>  
  
-   <span data-ttu-id="2cb97-128">Install-SPRSService : El término 'Install-SPRSService' no se reconoce como</span><span class="sxs-lookup"><span data-stu-id="2cb97-128">Install-SPRSService : The term 'Install-SPRSService' is not recognized as the</span></span>  
    <span data-ttu-id="2cb97-129">nombre de un cmdlet, función, archivo de script o programa ejecutable.</span><span class="sxs-lookup"><span data-stu-id="2cb97-129">name of a cmdlet, function, script file, or operable program.</span></span> <span data-ttu-id="2cb97-130">Compruebe si escribió correctamente el nombre o, si incluyó una ruta de acceso, compruebe que dicha ruta es correcta e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2cb97-130">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>  
  
 <span data-ttu-id="2cb97-131">Se está produciendo uno de los problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2cb97-131">One of the following issues is occurring:</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="2cb97-132">SharePoint no está instalado y, por tanto, los cmdlets de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] no están instalados.</span><span class="sxs-lookup"><span data-stu-id="2cb97-132">SharePoint mode is not installed and therefore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets are not installed.</span></span>  
  
-   <span data-ttu-id="2cb97-133">Ejecutó el comando de PowerShell en Windows Powershell o Windows PowerShell ISE en lugar del Shell de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb97-133">You ran the PowerShell command in Windows PowerShell or Windows PowerShell ISE instead of the SharePoint Management Shell.</span></span> <span data-ttu-id="2cb97-134">Use el Shell de administración de SharePoint o agregue el Complemento de SharePoint a la ventana de Windows PowerShell con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="2cb97-134">Use the SharePoint Management shell or add the SharePoint Snap-in to the Windows PowerShell window with the following command:</span></span>  
  
    ```powershell
    Add-PSSnapin Microsoft.SharePoint.PowerShell  
    ```  
  
 <span data-ttu-id="2cb97-135">Para obtener más información, vea [usar Windows PowerShell para administrar SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) ( https://technet.microsoft.com/library/ee806878.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2cb97-135">For more information see [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) (https://technet.microsoft.com/library/ee806878.aspx).</span></span>  
  
#### <a name="to-open-the-sharepoint-management-shell-and-run-cmdlets"></a><span data-ttu-id="2cb97-136">Para abrir el Shell de administración de SharePoint y ejecutar cmdlets</span><span class="sxs-lookup"><span data-stu-id="2cb97-136">To Open the SharePoint Management Shell and run cmdlets</span></span>  
  
1.  <span data-ttu-id="2cb97-137">Haga clic en el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="2cb97-137">Click the **Start** button</span></span>  
  
2.  <span data-ttu-id="2cb97-138">Haga clic en el grupo **Productos de Microsoft SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="2cb97-138">Click the **Microsoft SharePoint Products** group.</span></span>  
  
3.  <span data-ttu-id="2cb97-139">Haga clic en **Shell de administración de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="2cb97-139">Click the **SharePoint Management Shell**.</span></span>  
  
 <span data-ttu-id="2cb97-140">Para ver la ayuda de la línea de comandos para un cmdlet, use el comando "Get-Help" de PowerShell en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cb97-140">To view command line help for a cmdlet use the PowerShell 'Get-Help' command at the PowerShell command prompt.</span></span> <span data-ttu-id="2cb97-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cb97-141">For example:</span></span>  
  
 `Get-Help Get-SPRSServiceApplicationServers`  
  
###  <a name="shared-service-and-proxy-cmdlets"></a><a name="bkmk_sharedservice_cmdlets"></a> <span data-ttu-id="2cb97-142">Cmdlets de servicios compartidos y servidores proxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-142">Shared Service and Proxy Cmdlets</span></span>  
 <span data-ttu-id="2cb97-143">La tabla siguiente contiene los cmdlets de PowerShell para el servicio compartido de SharePoint de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-143">The following table contains the PowerShell cmdlets for the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service.</span></span>  
  
|<span data-ttu-id="2cb97-144">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cb97-144">Cmdlet</span></span>|<span data-ttu-id="2cb97-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cb97-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2cb97-146">Install-SPRSService</span><span class="sxs-lookup"><span data-stu-id="2cb97-146">Install-SPRSService</span></span>|<span data-ttu-id="2cb97-147">Instala y registra, o desinstala, el servicio compartido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-147">Installs and registers, or uninstalls, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="2cb97-148">Esta operación solo se puede realizar en el equipo que tiene una instalación de SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb97-148">This can be done only on the machine that has an installation of SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="2cb97-149">Para la instalación, se producen dos operaciones:</span><span class="sxs-lookup"><span data-stu-id="2cb97-149">For installation, two operations occur:</span></span><br /><br /> <span data-ttu-id="2cb97-150">1) el [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] servicio está instalado en la granja.</span><span class="sxs-lookup"><span data-stu-id="2cb97-150">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is installed in the farm.</span></span><br /><br /> <span data-ttu-id="2cb97-151">2) la [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instancia de servicio se instala en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="2cb97-151">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service instance is installed to the current machine.</span></span><br /><br /> <span data-ttu-id="2cb97-152">Para la desinstalación, se producen dos operaciones:</span><span class="sxs-lookup"><span data-stu-id="2cb97-152">For Uninstallation, two operations occur:</span></span><br /><span data-ttu-id="2cb97-153">1) el [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] servicio se desinstala del equipo actual.</span><span class="sxs-lookup"><span data-stu-id="2cb97-153">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the current machine.</span></span><br /><span data-ttu-id="2cb97-154">2) el [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] servicio se desinstala de la granja.</span><span class="sxs-lookup"><span data-stu-id="2cb97-154">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the farm.</span></span><br /><br /> <br /><br /> <span data-ttu-id="2cb97-155">NOTA: si hay otros equipos en la granja que tienen el servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instalado, o si todavía hay aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ejecutándose en la granja, se muestra un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="2cb97-155">NOTE: If there are any other machines in the farm that have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service installed, or if there are still [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications running in the farm, a warning message is displayed.</span></span>|  
|<span data-ttu-id="2cb97-156">Install-SPRSServiceProxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-156">Install-SPRSServiceProxy</span></span>|<span data-ttu-id="2cb97-157">Instala y registra, o desinstala, el proxy de servicio de Reporting Services en la granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb97-157">Installs and registers, or uninstalls, the Reporting Services service proxy in the SharePoint farm.</span></span>|  
|<span data-ttu-id="2cb97-158">Get-SPRSProxyUrl</span><span class="sxs-lookup"><span data-stu-id="2cb97-158">Get-SPRSProxyUrl</span></span>|<span data-ttu-id="2cb97-159">Obtiene las direcciones URL para acceder al servicio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-159">Gets the URL(s) for accessing the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="2cb97-160">Get-SPRSServiceApplicationServers</span><span class="sxs-lookup"><span data-stu-id="2cb97-160">Get-SPRSServiceApplicationServers</span></span>|<span data-ttu-id="2cb97-161">Obtiene todos los servidores de la granja de SharePoint que contienen una instalación del servicio compartido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-161">Gets all servers in the local SharePoint farm that contain an installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="2cb97-162">Este cmdlet es útil para las actualizaciones de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , con el fin de determinar qué servidores ejecutan el servicio compartido y por tanto no es necesario actualizar.</span><span class="sxs-lookup"><span data-stu-id="2cb97-162">This cmdlet is useful for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] upgrades, to determine which servers run the shared service and therefore need to be upgraded.</span></span>|  
  
###  <a name="service-application-and-proxy-cmdlets"></a><a name="bkmk_serviceapp_cmdlets"></a> <span data-ttu-id="2cb97-163">Cmdlets de aplicaciones de servicio y servidores proxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-163">Service Application and Proxy Cmdlets</span></span>  
 <span data-ttu-id="2cb97-164">La tabla siguiente contiene los cmdlets de PowerShell para las aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y sus servidores proxy asociados.</span><span class="sxs-lookup"><span data-stu-id="2cb97-164">The following table contains the PowerShell cmdlets for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and their associated proxies.</span></span>  
  
|<span data-ttu-id="2cb97-165">cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cb97-165">cmdlet</span></span>|<span data-ttu-id="2cb97-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cb97-166">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2cb97-167">Get-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="2cb97-167">Get-SPRSServiceApplication</span></span>|<span data-ttu-id="2cb97-168">Obtiene uno o más objetos de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-168">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application objects.</span></span>|  
|<span data-ttu-id="2cb97-169">New-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="2cb97-169">New-SPRSServiceApplication</span></span>|<span data-ttu-id="2cb97-170">Crea una nueva aplicación de servicio de Reporting Services y las bases de datos asociadas.</span><span class="sxs-lookup"><span data-stu-id="2cb97-170">Create a new Reporting Services service application and associated databases.</span></span><br /><br /> <span data-ttu-id="2cb97-171">Parámetro LogonType: especifica si el servidor de informes utiliza la cuenta del grupo de aplicaciones SSRS o un inicio de sesión de SQL Server para tener acceso a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2cb97-171">LogonType Parameter: Specifies if the report server uses the SSRS Application Pool account or a SQL Server login to access the report server database.</span></span> <span data-ttu-id="2cb97-172">Puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2cb97-172">It can be one of the following:</span></span><br /><br /> <span data-ttu-id="2cb97-173">0 Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="2cb97-173">0 Windows Authentication</span></span><br /><br /> <span data-ttu-id="2cb97-174">1 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2cb97-174">1 SQL Server</span></span><br /><br /> <span data-ttu-id="2cb97-175">2 Cuenta del grupo de aplicaciones (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2cb97-175">2 Application Pool Account (default)</span></span>|  
|<span data-ttu-id="2cb97-176">Remove-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="2cb97-176">Remove-SPRSServiceApplication</span></span>|<span data-ttu-id="2cb97-177">Quita la aplicación de servicio de Reporting Services especificada.</span><span class="sxs-lookup"><span data-stu-id="2cb97-177">Removes the specified Reporting Services service application.</span></span> <span data-ttu-id="2cb97-178">También se quitarán las bases de datos asociadas.</span><span class="sxs-lookup"><span data-stu-id="2cb97-178">This will also remove the associated databases.</span></span>|  
|<span data-ttu-id="2cb97-179">Set-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="2cb97-179">Set-SPRSServiceApplication</span></span>|<span data-ttu-id="2cb97-180">Edita las propiedades de una aplicación de servicio de Reporting Services existente.</span><span class="sxs-lookup"><span data-stu-id="2cb97-180">Edits the properties of an existing Reporting Services service application.</span></span>|  
|<span data-ttu-id="2cb97-181">New-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-181">New-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="2cb97-182">Crea un nuevo proxy de aplicación de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cb97-182">Creates a new Reporting Services service application proxy.</span></span>|  
|<span data-ttu-id="2cb97-183">Get-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-183">Get-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="2cb97-184">Obtiene uno o varios servidores proxy de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-184">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application proxies.</span></span>|  
|<span data-ttu-id="2cb97-185">Dismount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="2cb97-185">Dismount-SPRSDatabase</span></span>|<span data-ttu-id="2cb97-186">Desmonta las bases de datos de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-186">Dismounts the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="2cb97-187">Remove-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="2cb97-187">Remove-SPRSDatabase</span></span>|<span data-ttu-id="2cb97-188">Quita las bases de datos de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-188">Remove the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="2cb97-189">Set-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="2cb97-189">Set-SPRSDatabase</span></span>|<span data-ttu-id="2cb97-190">Establece las propiedades de las bases de datos asociadas a una aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-190">Sets the properties of the databases associated to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="2cb97-191">Mount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="2cb97-191">Mount-SPRSDatabase</span></span>|<span data-ttu-id="2cb97-192">Monta las bases de datos de una aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-192">Mounts databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="2cb97-193">New-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="2cb97-193">New-SPRSDatabase</span></span>|<span data-ttu-id="2cb97-194">Crea las nuevas bases de datos para la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] especificada.</span><span class="sxs-lookup"><span data-stu-id="2cb97-194">Create new service application databases for the specified [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="2cb97-195">Get-SPRSDatabaseCreationScript</span><span class="sxs-lookup"><span data-stu-id="2cb97-195">Get-SPRSDatabaseCreationScript</span></span>|<span data-ttu-id="2cb97-196">Muestra el script de creación de bases de datos en la pantalla para una aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-196">Outputs the database creation script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="2cb97-197">Este script se puede ejecutar a continuación en SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2cb97-197">You can then run the script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="2cb97-198">Get-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="2cb97-198">Get-SPRSDatabase</span></span>|<span data-ttu-id="2cb97-199">Obtiene una o varias bases de datos de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-199">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases.</span></span> <span data-ttu-id="2cb97-200">Use el comando para obtener el identificador de la base de datos de la aplicación del servicio de forma que pueda usar el cmdlet Set-SPRSDatabase para modificar las propiedades, por ejemplo `querytimeout`.</span><span class="sxs-lookup"><span data-stu-id="2cb97-200">Use the command to get the ID of service application database so you can use the Set-SPRSDatabase comdlet to modify properties, for example the `querytimeout`.</span></span> <span data-ttu-id="2cb97-201">Vea el ejemplo de este tema, [Obtener y establecer las propiedades de la base de datos de aplicación de Reporting Services como, por ejemplo, el tiempo de espera de la base de datos](#bkmk_example_db_properties).</span><span class="sxs-lookup"><span data-stu-id="2cb97-201">See the example in this topic, [Get and set properties of the Reporting Servicea application database, for example database timeout](#bkmk_example_db_properties).</span></span>|  
|<span data-ttu-id="2cb97-202">Get-SPRSDatabaseRightsScript</span><span class="sxs-lookup"><span data-stu-id="2cb97-202">Get-SPRSDatabaseRightsScript</span></span>|<span data-ttu-id="2cb97-203">Muestra el script de permisos de base de datos en la pantalla para una aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-203">Outputs the database rights script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="2cb97-204">Solicita el usuario y la base de datos, y luego devuelve Transact-SQL que se puede ejecutar para modificar los permisos.</span><span class="sxs-lookup"><span data-stu-id="2cb97-204">It will prompt for desired user and database then returns transact SQL you can run to modify permissions.</span></span> <span data-ttu-id="2cb97-205">Este script se puede ejecutar a continuación en SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2cb97-205">You can then run this script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="2cb97-206">Get-SPRSDatabaseUpgradeScript</span><span class="sxs-lookup"><span data-stu-id="2cb97-206">Get-SPRSDatabaseUpgradeScript</span></span>|<span data-ttu-id="2cb97-207">Muestra el script de actualización de bases de datos en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="2cb97-207">Outputs a database upgrade script to the screen.</span></span> <span data-ttu-id="2cb97-208">El script actualizará las bases de datos de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] a la versión de base de datos de la instalación de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] actual.</span><span class="sxs-lookup"><span data-stu-id="2cb97-208">The script will upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases to the database version of the current [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installation.</span></span>|  
  
###  <a name="reporting-services-custom-functionality-cmdlets"></a><a name="bkmk_ssrsfeatures_cmdlets"></a> <span data-ttu-id="2cb97-209">Cmdlets de funcionalidad personalizada de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cb97-209">Reporting Services Custom Functionality Cmdlets</span></span>  
  
|<span data-ttu-id="2cb97-210">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cb97-210">Cmdlet</span></span>|<span data-ttu-id="2cb97-211">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cb97-211">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2cb97-212">Update-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="2cb97-212">Update-SPRSEncryptionKey</span></span>|<span data-ttu-id="2cb97-213">Actualiza la clave de cifrado para la aplicación de servicio de Reporting Services especificada y cifra de nuevo sus datos.</span><span class="sxs-lookup"><span data-stu-id="2cb97-213">Updates the encryption key for the specified Reporting Services service application and re-encrypts its data.</span></span>|  
|<span data-ttu-id="2cb97-214">Restore-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="2cb97-214">Restore-SPRSEncryptionKey</span></span>|<span data-ttu-id="2cb97-215">Restaura una clave de cifrado de la que se hizo copia de seguridad anteriormente para una aplicación de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cb97-215">Restores a previously backed up encryption key for a Reporting Services service application.</span></span>|  
|<span data-ttu-id="2cb97-216">Remove-SPRSEncryptedData</span><span class="sxs-lookup"><span data-stu-id="2cb97-216">Remove-SPRSEncryptedData</span></span>|<span data-ttu-id="2cb97-217">Elimina los datos cifrados para la aplicación de servicio de Reporting Services especificada.</span><span class="sxs-lookup"><span data-stu-id="2cb97-217">Delete the encrypted data for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="2cb97-218">Backup-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="2cb97-218">Backup-SPRSEncryptionKey</span></span>|<span data-ttu-id="2cb97-219">Realiza una copia de seguridad de la clave de cifrado para la aplicación de servicio de Reporting Services especificada.</span><span class="sxs-lookup"><span data-stu-id="2cb97-219">Backs up the encryption key for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="2cb97-220">New-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="2cb97-220">New-SPRSExtension</span></span>|<span data-ttu-id="2cb97-221">Registra una nueva extensión con una aplicación de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cb97-221">Registers a new extension with a Reporting Services service application.</span></span>|  
|<span data-ttu-id="2cb97-222">Set-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="2cb97-222">Set-SPRSExtension</span></span>|<span data-ttu-id="2cb97-223">Establece las propiedades de una extensión de Reporting Services existente.</span><span class="sxs-lookup"><span data-stu-id="2cb97-223">Sets the properties of an existing Reporting Services extension.</span></span>|  
|<span data-ttu-id="2cb97-224">Remove-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="2cb97-224">Remove-SPRSExtension</span></span>|<span data-ttu-id="2cb97-225">Quita una extensión de una aplicación de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cb97-225">Removes an extension from a Reporting Services service application.</span></span>|  
|<span data-ttu-id="2cb97-226">Get-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="2cb97-226">Get-SPRSExtension</span></span>|<span data-ttu-id="2cb97-227">Obtiene una o varias extensiones de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para una aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-227">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensions for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span><br /><br /> <span data-ttu-id="2cb97-228">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="2cb97-228">Valid values are:</span></span><br /><br /> <span data-ttu-id="2cb97-229">**Entrega.**</span><span class="sxs-lookup"><span data-stu-id="2cb97-229">**Delivery**</span></span><br /><br /> <span data-ttu-id="2cb97-230">**DeliveryUI**</span><span class="sxs-lookup"><span data-stu-id="2cb97-230">**DeliveryUI**</span></span><br /><br /> <span data-ttu-id="2cb97-231">**Representar**</span><span class="sxs-lookup"><span data-stu-id="2cb97-231">**Render**</span></span><br /><br /> <span data-ttu-id="2cb97-232">**Data**</span><span class="sxs-lookup"><span data-stu-id="2cb97-232">**Data**</span></span><br /><br /> <span data-ttu-id="2cb97-233">**Seguridad**</span><span class="sxs-lookup"><span data-stu-id="2cb97-233">**Security**</span></span><br /><br /> <span data-ttu-id="2cb97-234">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="2cb97-234">**Authentication**</span></span><br /><br /> <span data-ttu-id="2cb97-235">**EventProcessing**</span><span class="sxs-lookup"><span data-stu-id="2cb97-235">**EventProcessing**</span></span><br /><br /> <span data-ttu-id="2cb97-236">**ReportItems**</span><span class="sxs-lookup"><span data-stu-id="2cb97-236">**ReportItems**</span></span><br /><br /> <span data-ttu-id="2cb97-237">**Diseñador**</span><span class="sxs-lookup"><span data-stu-id="2cb97-237">**Designer**</span></span><br /><br /> <span data-ttu-id="2cb97-238">**ReportItemDesigner**</span><span class="sxs-lookup"><span data-stu-id="2cb97-238">**ReportItemDesigner**</span></span><br /><br /> <span data-ttu-id="2cb97-239">**ReportItemConverter**</span><span class="sxs-lookup"><span data-stu-id="2cb97-239">**ReportItemConverter**</span></span><br /><br /> <span data-ttu-id="2cb97-240">**ReportDefinitionCustomization**</span><span class="sxs-lookup"><span data-stu-id="2cb97-240">**ReportDefinitionCustomization**</span></span>|  
|<span data-ttu-id="2cb97-241">Get-SPRSSite</span><span class="sxs-lookup"><span data-stu-id="2cb97-241">Get-SPRSSite</span></span>|<span data-ttu-id="2cb97-242">Obtiene los sitios de SharePoint basándose en si está habilitada la característica "ReportingService".</span><span class="sxs-lookup"><span data-stu-id="2cb97-242">Gets the SharePoint sites based on whether the "ReportingService" feature is enabled.</span></span> <span data-ttu-id="2cb97-243">De forma predeterminada, se devuelven los sitios que habilitan la característica "ReportingService".</span><span class="sxs-lookup"><span data-stu-id="2cb97-243">By default, sites that enable the "ReportingService" feature are returned.</span></span>|  
  
##  <a name="basic-samples"></a><a name="bkmk_basic_samples"></a><span data-ttu-id="2cb97-244">Ejemplos básicos</span><span class="sxs-lookup"><span data-stu-id="2cb97-244">Basic Samples</span></span>  
 <span data-ttu-id="2cb97-245">Devolver una lista de cmdlets cuyo nombre contiene "SPRS".</span><span class="sxs-lookup"><span data-stu-id="2cb97-245">Return a list of cmdlets that contain 'SPRS' in the name.</span></span> <span data-ttu-id="2cb97-246">Será la lista completa de cmdlets de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cb97-246">This will be the full list of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets.</span></span>  
  
```powershell
Get-command -noun *SPRS*  
```  
  
 <span data-ttu-id="2cb97-247">O con un poco más detalle, enviar la salida a un archivo de texto denominado commandlist.txt</span><span class="sxs-lookup"><span data-stu-id="2cb97-247">Or with a little more detail, piped to a text file named commandlist.txt</span></span>  
  
```powershell
Get-Command -Noun *SPRS* | Select name, definition | Format-List | Out-File c:\commandlist.txt  
```  
  
 <span data-ttu-id="2cb97-248">Instalar el servicio de SharePoint de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y el proxy del servicio.</span><span class="sxs-lookup"><span data-stu-id="2cb97-248">Install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint service and service proxy.</span></span>  
  
```powershell
Install-SPRSService  
```  
  
```powershell
Install-SPRSServiceProxy  
```  
  
 <span data-ttu-id="2cb97-249">Iniciar el servicio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cb97-249">Start the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service</span></span>  
  
```powershell
Get-SPServiceInstance -all | where {$_.TypeName -like "SQL Server Reporting*"} | Start-SPServiceInstance  
```  
  
 <span data-ttu-id="2cb97-250">Escriba el siguiente comando desde el Shell de administración de SharePoint para devolver una lista filtrada de filas de un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="2cb97-250">Type the following command from the SharePoint Management Shell to return a filtered list of rows from the a log file.</span></span> <span data-ttu-id="2cb97-251">El comando filtrará las líneas que contengan "ssrscustomactionerror".</span><span class="sxs-lookup"><span data-stu-id="2cb97-251">The command will filter for lines that contain "ssrscustomactionerror".</span></span> <span data-ttu-id="2cb97-252">En este ejemplo se examina el archivo de registro creado cuando se instaló rssharepoint.msi.</span><span class="sxs-lookup"><span data-stu-id="2cb97-252">This example is looking at the log file created when the rssharepoint.msi was installed.</span></span>  
  
```powershell
Get-Content -Path C:\Users\testuser\AppData\Local\Temp\rs_sp_0.log | Select-String "ssrscustomactionerror"  
```  
  
##  <a name="detailed-samples"></a><a name="bkmk_detailedsamples"></a><span data-ttu-id="2cb97-253">Ejemplos detallados</span><span class="sxs-lookup"><span data-stu-id="2cb97-253">Detailed Samples</span></span>  
 <span data-ttu-id="2cb97-254">Además de los ejemplos siguientes, vea la sección "script de Windows PowerShell" en el tema [script de Windows PowerShell para los pasos 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span><span class="sxs-lookup"><span data-stu-id="2cb97-254">In addition to the following samples, see the section "Windows PowerShell Script" in the topic [Windows PowerShell script for Steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span></span>  
  
###  <a name="create-a-reporting-services-service-application-and-proxy"></a><a name="bkmk_example_create_service_application"></a><span data-ttu-id="2cb97-255">Creación de una aplicación de servicio de Reporting Services y proxy</span><span class="sxs-lookup"><span data-stu-id="2cb97-255">Create a Reporting Services service application and proxy</span></span>  
 <span data-ttu-id="2cb97-256">Este script de ejemplo realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2cb97-256">This sample script completes the following tasks:</span></span>  
  
1.  <span data-ttu-id="2cb97-257">Crea una aplicación de servicio de Reporting Services y un proxy.</span><span class="sxs-lookup"><span data-stu-id="2cb97-257">Create a Reporting Services service application and proxy.</span></span> <span data-ttu-id="2cb97-258">El script asume que el grupo de aplicaciones "My App Pool" ya existe.</span><span class="sxs-lookup"><span data-stu-id="2cb97-258">The script assumes the application pool "My App Pool" already exists.</span></span>  
  
2.  <span data-ttu-id="2cb97-259">Agrega el proxy al grupo de servidores proxy predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2cb97-259">Add the proxy to the default proxy group</span></span>  
  
3.  <span data-ttu-id="2cb97-260">Concede acceso a la aplicación de servicio al puerto 80 de la base de datos de contenido de la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="2cb97-260">Grant the service app access to the port 80 web app's content database.</span></span> <span data-ttu-id="2cb97-261">El script asume que el sitio " http://sitename " ya existe.</span><span class="sxs-lookup"><span data-stu-id="2cb97-261">The script assumes site "http://sitename" already exists.</span></span>  
  
```powershell
# Create service application and service application proxy  
$appPool = Get-SPServiceApplicationPool "My App Pool"  
$serviceApp = New-SPRSServiceApplication "My RS Service App" -ApplicationPool $appPool  
$serviceAppProxy = New-SPRSServiceApplicationProxy -Name "My RS Service App Proxy" -ServiceApplication $serviceApp  
  
# Add service application proxy to default proxy group.  Any web application that uses the default proxy group will now be able to use this service application.  
Get-SPServiceApplicationProxyGroup -default | Add-SPServiceApplicationProxyGroupMember -Member $serviceAppProxy  
  
# Grant application pool account access to the port 80 web application's content database.  
$webApp = Get-SPWebApplication "http://sitename"  
$appPoolAccountName = $appPool.ProcessAccount.LookupName()  
$webApp.GrantAccessToProcessIdentity($appPoolAccountName)
```  
  
###  <a name="review-and-update-a-reporting-services-delivery-extension"></a><a name="bkmk_example_delivery_extension"></a><span data-ttu-id="2cb97-262">Revisar y actualizar una extensión de entrega de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cb97-262">Review and update a Reporting Services delivery extension</span></span>  
 <span data-ttu-id="2cb97-263">El siguiente ejemplo de script de PowerShell actualiza la configuración de la extensión de entrega de correo electrónico del servidor de informes para la aplicación de servicio denominada `My RS Service App`.</span><span class="sxs-lookup"><span data-stu-id="2cb97-263">The following PowerShell script example, updates the configuration for the report server e-mail delivery extension for the service application named `My RS Service App`.</span></span> <span data-ttu-id="2cb97-264">Actualice los valores para el servidor SMTP (`<email server name>`) y el alias de correo electrónico FROM (`<your FROM email address>`).</span><span class="sxs-lookup"><span data-stu-id="2cb97-264">Update the values for the SMTP server (`<email server name>`) and the FROM email alias (`<your FROM email address>`).</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication -Name "My RS Service App"  
$emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
$emailXml = [xml]$emailCfg
$emailXml.SelectSingleNode("//SMTPServer").InnerText = "<email server name>"  
$emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
$emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
$emailXml.SelectSingleNode("//From").InnerText = '<your FROM email address>'  
Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
```  
  
 <span data-ttu-id="2cb97-265">En el ejemplo anterior, si no supiera el nombre exacto de la aplicación de servicio, podría reescribir la primera instrucción para obtener la aplicación de servicio a partir de una búsqueda del nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="2cb97-265">In the above example if you did not know the exact name of the service application, you could rewrite the first statement to get the service application based on a search of the partial name.</span></span> <span data-ttu-id="2cb97-266">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cb97-266">For example:</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication | Where {$_.name -like " ssrs_testapp *"}  
```  
  
 <span data-ttu-id="2cb97-267">El script siguiente devolverá los valores de configuración actual de la extensión de entrega por correo electrónico del servidor de informes para la aplicación de servicio denominada "Reporting Services Application".</span><span class="sxs-lookup"><span data-stu-id="2cb97-267">The following script will return the current configuration values for the report server e-mail delivery extension for the service application named "Reporting Services Application".</span></span> <span data-ttu-id="2cb97-268">El primer paso establece el valor de la variable $app en el objeto de la aplicación de servicio denominada " My RS Service App "</span><span class="sxs-lookup"><span data-stu-id="2cb97-268">The first step sets the value of the variable $app to the object of the service application that has a name of " My RS Service App "</span></span>  
  
 <span data-ttu-id="2cb97-269">La segunda instrucción obtendrá la extensión de entrega por correo electrónico del servidor de informes para el objeto de aplicación de servicio de la variable $app, y seleccionará el XML de configuración.</span><span class="sxs-lookup"><span data-stu-id="2cb97-269">The second statement will Get the 'Report Server Email' delivery extension for the service application object in variable $app, and select the configurationXML</span></span>  
  
```powershell
$app = Get-SPRSServiceapplication -Name "Reporting Services Application"  
Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
 <span data-ttu-id="2cb97-270">Asimismo, puede reescribir las dos instrucciones anteriores como una sola:</span><span class="sxs-lookup"><span data-stu-id="2cb97-270">You can also rewrite the above two statements as one:</span></span>  
  
```powershell
Get-SPRSServiceApplication -Name "Reporting Services Application" | Get-SPRSExtension -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
###  <a name="get-and-set-properties-of-the-reporting-servicea-application-database-for-example-database-timeout"></a><a name="bkmk_example_db_properties"></a><span data-ttu-id="2cb97-271">Obtener y establecer propiedades de la base de datos de aplicación de Reporting Services, por ejemplo, tiempo de espera de base de datos</span><span class="sxs-lookup"><span data-stu-id="2cb97-271">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>  
 <span data-ttu-id="2cb97-272">En el siguiente ejemplo, se obtiene, en primer lugar, una lista de las bases de datos y propiedades de forma que pueda determinar el GUID (identificador) de la base de datos que proporciona después al comando SET.</span><span class="sxs-lookup"><span data-stu-id="2cb97-272">The following example first returns a list of the databases and properties so you can determine the database guid (ID) that you then supply to the set command.</span></span> <span data-ttu-id="2cb97-273">Para obtener una lista completa de las propiedades, use `Get-SPRSDatabase | format-list`.</span><span class="sxs-lookup"><span data-stu-id="2cb97-273">For a full list of the properties, use `Get-SPRSDatabase | format-list`.</span></span>  
  
```powershell
Get-SPRSDatabase | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance
```  
  
 <span data-ttu-id="2cb97-274">A continuación se muestra un ejemplo del resultado.</span><span class="sxs-lookup"><span data-stu-id="2cb97-274">The following is an example of the output.</span></span> <span data-ttu-id="2cb97-275">Determine el identificador para la base de datos que desee modificar y use el identificador en el cmdlet SET.</span><span class="sxs-lookup"><span data-stu-id="2cb97-275">Determine the ID for the database you want to modify and use the ID in the SET cmdlet.</span></span>  
  
-   `Id                : 56f8d1bc-cb04-44cf-bd41-a873643c5a14`  
  
     `QueryTimeout      : 120`  
  
     `ConnectionTimeout : 15`  
  
     `Status            : Online`  
  
     `Server            : SPServer Name=uetestb01`  
  
     `ServiceInstance   : SPDatabaseServiceInstance`  
  
```powershell
Set-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 -QueryTimeout 300  
```  
  
 <span data-ttu-id="2cb97-276">Para comprobar que se ha establecido el valor, vuelva a ejecutar el cmdlet GET.</span><span class="sxs-lookup"><span data-stu-id="2cb97-276">To verify the value is set, run the GET cmdlet again.</span></span>  
  
```powershell
Get-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance  
```  
  
###  <a name="list-reporting-services-data-extensions---sharepoint-mode"></a><a name="bkmk_example_list_data_extensions"></a><span data-ttu-id="2cb97-277">Enumerar extensiones de datos de Reporting Services-modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cb97-277">List reporting services data extensions - SharePoint mode</span></span>  
 <span data-ttu-id="2cb97-278">El siguiente ejemplo recorre en bucle cada aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y muestra las extensiones de datos actuales para cada una.</span><span class="sxs-lookup"><span data-stu-id="2cb97-278">The following example loops through each [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application and lists the current data extensions for each.</span></span>  
  
```powershell
$apps = Get-SPRSServiceApplication  
foreach ($app in $apps)
{  
Write-host -ForegroundColor "yellow" Service App Name $app.Name  
Get-SPRSExtension -identity $app -ExtensionType "Data" | select name, extensiontype | Format-Table -AutoSize  
}  
```  
  
 <span data-ttu-id="2cb97-279">**Ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="2cb97-279">**Example output:**</span></span>  
  
-   `Name           ExtensionType`  
  
     `----           -------------`  
  
     `SQL                     Data`  
  
     `SQLAZURE                Data`  
  
     `SQLPDW                  Data`  
  
     `OLEDB                   Data`  
  
     `OLEDB-MD                Data`  
  
     `ORACLE                  Data`  
  
     `ODBC                    Data`  
  
     `XML                     Data`  
  
     `SHAREPOINTLIST          Data`  
  
###  <a name="change-and-list-subscription-owners"></a><a name="bkmk_change_subscription_owner"></a><span data-ttu-id="2cb97-280">Cambiar y enumerar propietarios de suscripciones</span><span class="sxs-lookup"><span data-stu-id="2cb97-280">Change and list subscription owners</span></span>  
 <span data-ttu-id="2cb97-281">Consulte [uso de PowerShell para cambiar y enumerar propietarios de suscripciones de Reporting Services y ejecutar una suscripción](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2cb97-281">See [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb97-282">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cb97-282">See Also</span></span>  
 <span data-ttu-id="2cb97-283">[Usar PowerShell para cambiar y enumerar Reporting Services propietarios de suscripciones y ejecutar una suscripción](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="2cb97-283">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span></span>  
 <span data-ttu-id="2cb97-284">[Lista de comprobación: Use PowerShell para comprobar PowerPivot para SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span><span class="sxs-lookup"><span data-stu-id="2cb97-284">[CheckList: Use PowerShell to Verify PowerPivot for SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span></span>  
 [<span data-ttu-id="2cb97-285">Scripts de PowerShell de Administración de SharePoint de CodePlex</span><span class="sxs-lookup"><span data-stu-id="2cb97-285">CodePlex SharePoint Management PowerShell scripts</span></span>](https://sharepointpsscripts.codeplex.com/)   
