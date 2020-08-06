---
title: Configurar un servidor de informes en modo nativo para la administración local (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- UAC
- installing Reporting Services
- Windows Vista
- Localhost
- windows server 2008
- Vista
ms.assetid: 312c6bb8-b3f7-4142-a55f-c69ee15bbf52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad53f293ef825a382d9e39b58527a36ef291687a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674601"
---
# <a name="configure-a-native-mode-report-server-for-local-administration-ssrs"></a><span data-ttu-id="e524c-102">Configurar un servidor de informes en modo nativo para la administración local (SSRS)</span><span class="sxs-lookup"><span data-stu-id="e524c-102">Configure a Native Mode Report Server for Local Administration (SSRS)</span></span>
  <span data-ttu-id="e524c-103">La implementación de un servidor de informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en uno de los sistemas operativos siguientes requiere más pasos de configuración si desea administrar la instancia del servidor de informes localmente.</span><span class="sxs-lookup"><span data-stu-id="e524c-103">Deploying a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server on one of the following operating systems requires more configuration steps if you want to administer the report server instance locally.</span></span> <span data-ttu-id="e524c-104">En este tema, se describe cómo configurar el servidor de informes para la administración local.</span><span class="sxs-lookup"><span data-stu-id="e524c-104">This topic explains how to configure the report server for local administration.</span></span> <span data-ttu-id="e524c-105">Si aún no ha instalado o configurado el servidor de informes, vea [instalar SQL Server 2014 desde el Asistente para la instalación &#40;&#41;de instalación](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) y [Administración de un servidor de informes en modo nativo de Reporting Services](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="e524c-105">If you have not yet installed or configured the report server, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) and [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="e524c-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e524c-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
-   [!INCLUDE[winblue_server_2](../../includes/winblue-server-2-md.md)]  
  
-   [!INCLUDE[winblue_client_2](../../includes/winblue-client-2-md.md)]  
  
-   [!INCLUDE[win8](../../includes/win8-md.md)]  
  
-   [!INCLUDE[win8srv](../../includes/win8srv-md.md)]  
  
-   [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)]  
  
-   [!INCLUDE[win7](../../includes/win7-md.md)]  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]  
  
 <span data-ttu-id="e524c-107">Puesto que los sistemas operativos indicados limitan los permisos, los miembros del grupo local Administradores ejecutan la mayoría de las aplicaciones como si usaran la cuenta de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="e524c-107">Because the noted operating systems limit permissions, members of the local Administrators group run most applications as if they are using the Standard User account.</span></span>  
  
 <span data-ttu-id="e524c-108">Aunque esta práctica mejora la seguridad global del sistema, impide que utilice las asignaciones de roles predefinidas e integradas que Reporting Services crea para los administradores locales.</span><span class="sxs-lookup"><span data-stu-id="e524c-108">While this practice improves the overall security of your system, it prevents you from using the predefined, built-in role assignments that Reporting Services creates for local administrators.</span></span>  
  
-   [<span data-ttu-id="e524c-109">Información general de los cambios de configuración</span><span class="sxs-lookup"><span data-stu-id="e524c-109">Overview of Configuration Changes</span></span>](#bkmk_configuraiton_overview)  
  
-   [<span data-ttu-id="e524c-110">Para configurar el servidor de informes local y la administración del Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="e524c-110">To Configure Local Report Server and Report Manager Administration</span></span>](#bkmk_configure_local_server)  
  
-   [<span data-ttu-id="e524c-111">Para configurar SQL Server Management Studio (SSMS) para la administración del servidor de informes local</span><span class="sxs-lookup"><span data-stu-id="e524c-111">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>](#bkmk_configure_ssms)  
  
-   [<span data-ttu-id="e524c-112">Para configurar SQL Server Data Tools BI (SSDT) para publicar en un servidor de informes local</span><span class="sxs-lookup"><span data-stu-id="e524c-112">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>](#bkmk_configure_ssdt)  
  
-   [<span data-ttu-id="e524c-113">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e524c-113">Additional Information</span></span>](#bkmk_addiitonal_informaiton)  
  
##  <a name="overview-of-configuration-changes"></a><a name="bkmk_configuraiton_overview"></a><span data-ttu-id="e524c-114">Información general de los cambios de configuración</span><span class="sxs-lookup"><span data-stu-id="e524c-114">Overview of Configuration Changes</span></span>  
 <span data-ttu-id="e524c-115">Los cambios de configuración siguientes configuran el servidor de forma que pueda usar los permisos de usuario estándar para administrar el contenido y las operaciones del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="e524c-115">The following configuration changes configure the server so that you can use standard user permissions to manage report server content and operations:</span></span>  
  
-   <span data-ttu-id="e524c-116">Agrega direcciones URL de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a los sitios de confianza.</span><span class="sxs-lookup"><span data-stu-id="e524c-116">Add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs to trusted sites.</span></span> <span data-ttu-id="e524c-117">De forma predeterminada, cuando Internet Explorer se ejecuta en los sistemas operativos enumerados lo hace en **Modo protegido**, una característica que impide que las solicitudes del explorador lleguen a los procesos de alto nivel que se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="e524c-117">By default, Internet Explorer running on the listed operating systems runs in **Protected Mode**, a feature that blocks browser requests from reaching high-level processes that run on the same computer.</span></span> <span data-ttu-id="e524c-118">Puede deshabilitar el modo protegido para las aplicaciones del servidor de informes agregándolas como sitios de confianza.</span><span class="sxs-lookup"><span data-stu-id="e524c-118">You can disable protected mode for the report server applications by adding them as Trusted Sites.</span></span>  
  
-   <span data-ttu-id="e524c-119">Crea asignaciones de roles que le conceden, como administrador del servidor de informes, permiso para administrar el contenido y las operaciones sin tener que utilizar la característica **Ejecutar como administrador** de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e524c-119">Create role assignments that grant you, the report server administrator, permission to manage content and operations without having to use the **Run as administrator** feature on Internet Explorer.</span></span> <span data-ttu-id="e524c-120">Mediante la creación de asignaciones de roles para su cuenta de usuario de Windows, obtiene acceso a un servidor de informes con los permisos Administrador de contenido y Administrador del sistema a través de las asignaciones de roles explícitas que reemplazan a las asignaciones de roles predefinidas e integradas, que Reporting Services crea.</span><span class="sxs-lookup"><span data-stu-id="e524c-120">By creating role assignments for your Windows user account, you gain access to a report server with Content Manager and System Administrator permissions through explicit role assignments that replace the predefined, built-in role assignments that Reporting Services creates.</span></span>  
  
##  <a name="to-configure-local-report-server-and-report-manager-administration"></a><a name="bkmk_configure_local_server"></a><span data-ttu-id="e524c-121">Para configurar el servidor de informes local y la administración de Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="e524c-121">To Configure Local Report Server and Report Manager Administration</span></span>  
 <span data-ttu-id="e524c-122">Complete los pasos de configuración de esta sección si va a examinar un servidor de informes local y ve errores similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e524c-122">Complete the configuration steps in this section if you are browsing to a local report server and you see errors similar to the following:</span></span>  
  
-   <span data-ttu-id="e524c-123">El usuario `'Domain\[user name]`' no tiene los permisos requeridos.</span><span class="sxs-lookup"><span data-stu-id="e524c-123">User `'Domain\[user name]`' does not have required permissions.</span></span> <span data-ttu-id="e524c-124">Compruebe que se han concedido suficientes permisos y que se han tratado las restricciones del control de cuentas de usuario (UAC) de Windows.</span><span class="sxs-lookup"><span data-stu-id="e524c-124">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
###  <a name="trusted-site-settings-in-the-browser"></a><a name="bkmk_site_settings"></a><span data-ttu-id="e524c-125">Configuración del sitio de confianza en el explorador</span><span class="sxs-lookup"><span data-stu-id="e524c-125">Trusted Site Settings in the Browser</span></span>  
  
1.  <span data-ttu-id="e524c-126">Abra una ventana del explorador con los permisos Ejecutar como administrador.</span><span class="sxs-lookup"><span data-stu-id="e524c-126">Open a browser window with Run as administrator permissions.</span></span> <span data-ttu-id="e524c-127">En el menú **Inicio** , haga clic en **Todos los programas**, haga clic con el botón derecho en **Internet Explorer**y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e524c-127">From the **Start** menu, click **All Programs**, right-click **Internet Explorer**, and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="e524c-128">Haga clic en **Permitir** para continuar.</span><span class="sxs-lookup"><span data-stu-id="e524c-128">Click **Allow** to continue.</span></span>  
  
3.  <span data-ttu-id="e524c-129">En la dirección URL, escriba la dirección URL del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="e524c-129">In the URL address, enter the Report Manager URL.</span></span> <span data-ttu-id="e524c-130">Para obtener instrucciones, vea [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e524c-130">For instructions, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="e524c-131">Haga clic en **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e524c-131">Click **Tools**.</span></span>  
  
5.  <span data-ttu-id="e524c-132">Haga clic en **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="e524c-132">Click **Internet Options**.</span></span>  
  
6.  <span data-ttu-id="e524c-133">Haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e524c-133">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="e524c-134">Haga clic en **Sitios de confianza**.</span><span class="sxs-lookup"><span data-stu-id="e524c-134">Click **Trusted Sites**.</span></span>  
  
8.  <span data-ttu-id="e524c-135">Haga clic en **Sitios**.</span><span class="sxs-lookup"><span data-stu-id="e524c-135">Click **Sites**.</span></span>  
  
9. <span data-ttu-id="e524c-136">Agregue `http://<your-server-name>`.</span><span class="sxs-lookup"><span data-stu-id="e524c-136">Add `http://<your-server-name>`.</span></span>  
  
10. <span data-ttu-id="e524c-137">Desactive la casilla **Requerir comprobación del servidor (https:) para todos los sitios de esta zona** si no usa HTTP en el sitio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e524c-137">Clear the check box **Require server certification (https:) for all sites in this zone** if you are not using HTTPS for the default site.</span></span>  
  
11. <span data-ttu-id="e524c-138">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e524c-138">Click **Add**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-folder-settings"></a><a name="bkmk_configure_folder_settings"></a> <span data-ttu-id="e524c-139">Configuración de carpeta del Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="e524c-139">Report Manager Folder Settings</span></span>  
  
1.  <span data-ttu-id="e524c-140">En el Administrador de informes, en la página Inicio, haga clic en **Configuración de carpeta**.</span><span class="sxs-lookup"><span data-stu-id="e524c-140">In Report Manager, on the Home page, click **Folder Settings**.</span></span>  
  
2.  <span data-ttu-id="e524c-141">En la página Configuración de carpeta, haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e524c-141">In the Folder Settings page, click **Security**.</span></span>  
  
3.  <span data-ttu-id="e524c-142">Haga clic en **Nueva asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="e524c-142">Click **New Role Assignment**.</span></span>  
  
4.  <span data-ttu-id="e524c-143">En el campo **Nombre de grupo o de usuario** , escriba su cuenta de usuario de Windows en este formato: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="e524c-143">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
5.  <span data-ttu-id="e524c-144">Seleccione **Administrador de contenido**.</span><span class="sxs-lookup"><span data-stu-id="e524c-144">Select **Content Manager**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-site-settings"></a><a name="bkmk_configure_site_settings"></a> <span data-ttu-id="e524c-145">Configuración del sitio del Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="e524c-145">Report Manager Site Settings</span></span>  
  
1.  <span data-ttu-id="e524c-146">Abra el explorador con privilegios administrativos y vaya al administrador de informes, `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="e524c-146">Open your browser with administrative privileges and browse to report manager, `http://<server name>/reports`.</span></span>  
  
2.  <span data-ttu-id="e524c-147">Haga clic en **Configuración del sitio** en la esquina superior de la página Inicio.</span><span class="sxs-lookup"><span data-stu-id="e524c-147">Click **Site Settings** in the upper corner of the Home page.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e524c-148">**Nota** : si no ve la opción **Configuración del sitio** , cierre y vuelva a abrir el explorador y vaya al Administrador de informes con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e524c-148">**Note:** If you do not see the **Site Settings** option, close and reopen your browser and browse to report manager with administrative privileges.</span></span>  
  
3.  <span data-ttu-id="e524c-149">Haga clic en **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e524c-149">Click **security**.</span></span>  
  
4.  <span data-ttu-id="e524c-150">Haga clic en **Nueva asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="e524c-150">Click **New Role Assignment**.</span></span>  
  
5.  <span data-ttu-id="e524c-151">En el campo **Nombre de grupo o de usuario** , escriba su cuenta de usuario de Windows en este formato: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="e524c-151">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
6.  <span data-ttu-id="e524c-152">Seleccione **Administrador del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e524c-152">Select **System Administrator**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="e524c-153">Cierre el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="e524c-153">Close Report Manager.</span></span>  
  
9. <span data-ttu-id="e524c-154">Vuelva a abrir el Administrador de informes en Internet Explorer, sin usar **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e524c-154">Re-open Report Manager in Internet Explorer, without using **Run as administrator**.</span></span>  
  
##  <a name="to-configure-sql-server-management-studio-ssms-for-local-report-server-administration"></a><a name="bkmk_configure_ssms"></a><span data-ttu-id="e524c-155">Para configurar SQL Server Management Studio (SSMS) para la administración del servidor de informes local</span><span class="sxs-lookup"><span data-stu-id="e524c-155">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>  
 <span data-ttu-id="e524c-156">De forma predeterminada, no puede tener acceso a todas las propiedades del servidor de informes disponibles en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] a menos que inicie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e524c-156">By default, you cannot access all of the report server properties available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unless you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
 <span data-ttu-id="e524c-157">**Para configurar asignaciones de roles de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** no es necesario iniciar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con permisos elevados todas las veces:</span><span class="sxs-lookup"><span data-stu-id="e524c-157">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** role properties and role assignments so you do not need to start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with elevated permissions each time:</span></span>  
  
-   <span data-ttu-id="e524c-158">En el menú **Inicio** , haga clic en **Todos los programas**y en **SQL Server 2014**, haga clic con el botón derecho en **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]** y luego haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e524c-158">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, and then click **Run as administrator**.</span></span>  
  
-   <span data-ttu-id="e524c-159">Conéctese al servidor local de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e524c-159">Connect to your local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="e524c-160">En el nodo **Seguridad** , haga clic en **Roles del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e524c-160">In the **Security** node, click **System Roles**.</span></span>  
  
-   <span data-ttu-id="e524c-161">Haga clic con el botón derecho en **Administrador del sistema** y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e524c-161">Right-click **System Administrator** and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="e524c-162">En la página **Propiedades de rol del sistema** , seleccione **Ver propiedades del servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="e524c-162">In the **System Role Properties** page, select **View report server properties**.</span></span> <span data-ttu-id="e524c-163">Seleccione todas las demás propiedades que desee asociar a miembros del rol de administradores del sistema.</span><span class="sxs-lookup"><span data-stu-id="e524c-163">Select any other properties you want associated with members of the system administrators role.</span></span>  
  
-   <span data-ttu-id="e524c-164">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e524c-164">Click **OK**.</span></span>  
  
-   <span data-ttu-id="e524c-165">Cerrar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e524c-165">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span></span>  
  
-   <span data-ttu-id="e524c-166">Para agregar un usuario al rol del sistema "administrador del sistema", vea la anterior sección [Configuración del sitio del Administrador de informes](#bkmk_configure_site_settings) en este tema.</span><span class="sxs-lookup"><span data-stu-id="e524c-166">To add a user to the system role "system administrator", see the [Report Manager Site Settings](#bkmk_configure_site_settings) section earlier in this topic.</span></span>  
  
 <span data-ttu-id="e524c-167">Ahora, cuando abra [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y no seleccione explícitamente **Ejecutar como administrador** tendrá acceso a las propiedades del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e524c-167">Now when you open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and do not explicitly select **Run as administrator** you have access to the report server properties.</span></span>  
  
##  <a name="to-configure-sql-server-data-tools-bi-ssdt-to-publish-to-a-local-report-server"></a><a name="bkmk_configure_ssdt"></a><span data-ttu-id="e524c-168">Para configurar SQL Server Data Tools BI (SSDT) para publicar en un servidor de informes local</span><span class="sxs-lookup"><span data-stu-id="e524c-168">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>  
 <span data-ttu-id="e524c-169">Si instaló [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] en uno de los sistemas operativos enumerados en la primera sección de este tema y desea que SSDT interactúe con un servidor de informes local en modo nativo, aparecerán errores con los permisos a menos que abra [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] con permisos elevados o que configure roles de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e524c-169">If you installed [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] on one of the operating systems listed in the first section of this topic, and you want SSDT to interact with a local Native mode report server, you will experiences permission errors unless you open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] with elevated permissions or configure reporting services roles.</span></span> <span data-ttu-id="e524c-170">Por ejemplo, si no tiene los permisos necesarios, encontrará problemas similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e524c-170">For example, if you do not have sufficient permissions, you experience issues similar to the following:</span></span>  
  
-   <span data-ttu-id="e524c-171">Cuando intenta implementar elementos de informe en el servidor de informes local, aparece un mensaje de error similar al siguiente en la ventana **Lista de errores** :</span><span class="sxs-lookup"><span data-stu-id="e524c-171">When you attempt to deploy report items to the local report server, you see an error message similar to the following in the **Error List** window:</span></span>  
  
    -   <span data-ttu-id="e524c-172">Los permisos otorgados al usuario "Dominio\\<nombre de usuario\>" son insuficientes para realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="e524c-172">The permissions granted to user 'Domain\\<user name\>' are insufficient for performing this operation.</span></span>  
  
 <span data-ttu-id="e524c-173">**Para ejecutar SSDT con permisos elevados cada vez que lo abre:**</span><span class="sxs-lookup"><span data-stu-id="e524c-173">**To run with elevated permissions each time you open SSDT:**</span></span>  
  
1.  <span data-ttu-id="e524c-174">En la pantalla Inicio, escriba `sql server` y, a continuación, haga clic con el botón derecho en **SQL Server Data Tools para Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e524c-174">From the start screen, type `sql server` and then right-click **SQL Server Data Tools for Visual Studio**.</span></span> <span data-ttu-id="e524c-175">Haga clic en **Ejecutar como administrador**</span><span class="sxs-lookup"><span data-stu-id="e524c-175">Click **Run as administrator**</span></span>  
  
     <span data-ttu-id="e524c-176">**O bien**, en sistemas operativos anteriores:</span><span class="sxs-lookup"><span data-stu-id="e524c-176">**Or**, on older operating systems:</span></span>  
  
     <span data-ttu-id="e524c-177">En el menú **Inicio** , haga clic en **Todos los programas**y en **SQL Server 2014**, haga clic con el botón derecho en **Herramientas de datos de SQL Server**y luego haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e524c-177">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **SQL Server Data Tools**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="e524c-178">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="e524c-178">Click **Continue**.</span></span>  
  
3.  <span data-ttu-id="e524c-179">Haga clic en **Ejecutar programa**.</span><span class="sxs-lookup"><span data-stu-id="e524c-179">Click **Run Program**.</span></span>  
  
 <span data-ttu-id="e524c-180">Ahora debe poder implementar informes y otros elementos en un servidor de informes local.</span><span class="sxs-lookup"><span data-stu-id="e524c-180">You should now be able to deploy reports and other items to a local report server.</span></span>  
  
 <span data-ttu-id="e524c-181">**Para configurar asignaciones de roles de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no es necesario iniciar SSDT con permisos elevados todas las veces:**</span><span class="sxs-lookup"><span data-stu-id="e524c-181">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role assignments so you do not need to start SSDT with elevated permissions each time:**</span></span>  
  
-   <span data-ttu-id="e524c-182">Vea las secciones [Configuración de carpeta del Administrador de informes](#bkmk_configure_folder_settings) y [Configuración del sitio del Administrador de informes](#bkmk_configure_site_settings) anteriores de este tema.</span><span class="sxs-lookup"><span data-stu-id="e524c-182">See the [Report Manager Folder Settings](#bkmk_configure_folder_settings) and [Report Manager Site Settings](#bkmk_configure_site_settings) sections earlier in this topic.</span></span>  
  
##  <a name="additional-information"></a><a name="bkmk_addiitonal_informaiton"></a><span data-ttu-id="e524c-183">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e524c-183">Additional Information</span></span>  
 <span data-ttu-id="e524c-184">Un paso de configuración frecuente adicional relacionado con la administración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] consiste en abrir el puerto 80 en Firewall de Windows para permitir el acceso al equipo servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e524c-184">An additional and common configuration step related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] administration is to open port 80 in Windows Firewall to allow access to the report server computer.</span></span> <span data-ttu-id="e524c-185">Para obtener instrucciones, consulte [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="e524c-185">For instructions, see [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e524c-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e524c-186">See Also</span></span>  
 [<span data-ttu-id="e524c-187">Administración de un servidor de informes en modo nativo de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e524c-187">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
