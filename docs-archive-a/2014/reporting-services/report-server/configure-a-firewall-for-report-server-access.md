---
title: Configurar un firewall para el acceso al servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- firewall systems [Reporting Services]
- configuring servers [Reporting Services]
ms.assetid: 04dae07a-a3a4-424c-9bcb-a8000e20dc93
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b578c980522d24f5a24a73fdfd080ec425335aac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674602"
---
# <a name="configure-a-firewall-for-report-server-access"></a><span data-ttu-id="05112-102">Configurar un firewall para el acceso al servidor de informes</span><span class="sxs-lookup"><span data-stu-id="05112-102">Configure a Firewall for Report Server Access</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="05112-103">A las aplicaciones del servidor de informes y a los informes publicados se tiene acceso a través de direcciones URL que especifican una dirección IP, un puerto y un directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="05112-103">Report server applications and published reports are accessed through URLs that specify an IP address, port, and virtual directory.</span></span> <span data-ttu-id="05112-104">Si Firewall de Windows está activado, es probable que el puerto que el servidor de informes está configurado para usar esté cerrado.</span><span class="sxs-lookup"><span data-stu-id="05112-104">If Windows Firewall is turned on, the port that the report server is configured to use is most likely closed.</span></span> <span data-ttu-id="05112-105">Los indicios que señalan que un puerto podría estar cerrado son la aparición de una página web en blanco después de solicitar un informe o al intentar abrir el Administrador de informes desde un equipo cliente remoto.</span><span class="sxs-lookup"><span data-stu-id="05112-105">Indications that a port might be closed are the appearance of a blank Web page after requesting a report, or a blank page when you attempt to open Report Manager from a remote client computer.</span></span>  
  
 <span data-ttu-id="05112-106">Para abrir un puerto, debe utilizar la utilidad Firewall de Windows en el equipo del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="05112-106">To open a port, you must use the Windows Firewall utility on the report server computer.</span></span> <span data-ttu-id="05112-107">Reporting Services no abrirá los puertos en su lugar; debe realizar este paso manualmente.</span><span class="sxs-lookup"><span data-stu-id="05112-107">Reporting Services will not open ports for you; you must perform this step manually.</span></span>  
  
 <span data-ttu-id="05112-108">De forma predeterminada, el servidor de informes escucha las solicitudes HTTP en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="05112-108">By default, the report server listens for HTTP requests on port 80.</span></span> <span data-ttu-id="05112-109">Por tanto, las instrucciones siguientes incluyen los pasos que especifican ese puerto.</span><span class="sxs-lookup"><span data-stu-id="05112-109">As such, the following instructions include steps that specify that port.</span></span> <span data-ttu-id="05112-110">Si configuró las direcciones URL del servidor de informes para utilizar un puerto diferente, debe especificar ese número de puerto al seguir las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="05112-110">If you configured the report server URLs to use a different port, you must specify that port number when following the instructions below.</span></span>  
  
 <span data-ttu-id="05112-111">Si está teniendo acceso a las bases de datos relacionales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en equipos externos, o si la base de datos del servidor de informes se encuentra en una instancia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] externa, debe abrir el puerto 1433 y 1434 del equipo externo.</span><span class="sxs-lookup"><span data-stu-id="05112-111">If you are accessing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases on external computers, or if the report server database is on an external [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, you must open port 1433 and 1434 on the external computer.</span></span> <span data-ttu-id="05112-112">Para obtener más información, vea [Configurar Firewall de Windows para el acceso al motor de base de datos](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05112-112">For more information, see [Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="05112-113">Para obtener más información sobre la configuración predeterminada de Firewall de Windows y una descripción de los puertos TCP que afectan al [!INCLUDE[ssDE](../../includes/ssde-md.md)], a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]y a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vea [Configurar Firewall de Windows para permitir el acceso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05112-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="05112-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="05112-114">Prerequisites</span></span>  
 <span data-ttu-id="05112-115">En estas instrucciones se supone que ya configuró la cuenta de servicio, creó la base de datos del servidor de informes y configuró direcciones URL para el servicio web del servidor de informes y el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="05112-115">These instructions assume that you already configured the service account, created the report server database, and configured URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="05112-116">Para más información, vea [Administrar un servidor de informes en modo nativo de Reporting Services](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="05112-116">For more information, see [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
 <span data-ttu-id="05112-117">También debería haber comprobado que el servidor de informes es accesible a través de una conexión del explorador web local a la instancia del servidor de informes local.</span><span class="sxs-lookup"><span data-stu-id="05112-117">You should also have verified that the report server is accessible over a local Web browser connection to the local report server instance.</span></span> <span data-ttu-id="05112-118">Con este paso se establece que tiene una instalación activa.</span><span class="sxs-lookup"><span data-stu-id="05112-118">This step establishes that you have a working installation.</span></span> <span data-ttu-id="05112-119">Debería comprobar que la instalación está configurada correctamente antes de empezar a abrir los puertos.</span><span class="sxs-lookup"><span data-stu-id="05112-119">You should verify that the installation is configured correctly before you begin opening ports.</span></span> <span data-ttu-id="05112-120">Para completar este paso en Windows Server 2008, debe haber agregado también el sitio del servidor de informes a Sitios de confianza.</span><span class="sxs-lookup"><span data-stu-id="05112-120">To complete this step on  Windows Server, you must have also added the report server site to Trusted Sites.</span></span> <span data-ttu-id="05112-121">Para más información, vea [Configurar un servidor de informes en modo nativo para la administración local &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05112-121">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="opening-ports-in-windows-firewall"></a><span data-ttu-id="05112-122">Abrir puertos en Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="05112-122">Opening Ports in Windows Firewall</span></span>  
 <span data-ttu-id="05112-123">Cada versión del Firewall de Windows tiene instrucciones distintas.</span><span class="sxs-lookup"><span data-stu-id="05112-123">There are separate instructions for different versions of Windows Firewall.</span></span>  
  
#### <a name="to-open-port-80-on-windows-7-windows-server-2008-r2-windows-server-2012-and-2012-r2"></a><span data-ttu-id="05112-124">Para abrir el puerto 80 en Windows 7, Windows Server 2008 R2, Windows Server 2012 y 2012 R2</span><span class="sxs-lookup"><span data-stu-id="05112-124">To open port 80 on Windows 7, Windows Server 2008 R2, Windows Server 2012 and 2012 R2</span></span>  
  
1.  <span data-ttu-id="05112-125">En el menú **Inicio** , haga clic en **Panel de control**, en **Sistema y seguridad**y, a continuación, en **Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="05112-125">From the **Start** menu, click **Control Panel**, click **System and Security**, and then click **Windows Firewall**.</span></span> <span data-ttu-id="05112-126">El Panel de control no está configurado para la vista 'Categoría', solo necesita seleccionar **Firewall de Windows.**</span><span class="sxs-lookup"><span data-stu-id="05112-126">Control Panel is not configured for 'Category' view, you only need to select **Windows Firewall.**</span></span>  
  
2.  <span data-ttu-id="05112-127">Haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="05112-127">Click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="05112-128">Haga clic en **Reglas de entrada**</span><span class="sxs-lookup"><span data-stu-id="05112-128">Click **Inbound Rules.**</span></span>  
  
4.  <span data-ttu-id="05112-129">Haga clic en **Nueva regla** en la ventana **Acciones\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="05112-129">Click **New Rule** in the **Actions** window **.**</span></span>  
  
5.  <span data-ttu-id="05112-130">Haga clic en **Puerto** en la sección **Regla de entrada.**</span><span class="sxs-lookup"><span data-stu-id="05112-130">Click **Rule Type** of **Port.**</span></span>  
  
6.  <span data-ttu-id="05112-131">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="05112-131">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="05112-132">En la página **Protocolos y puertos** , haga clic en **TCP**.</span><span class="sxs-lookup"><span data-stu-id="05112-132">On the **Protocol and Ports** page click **TCP**.</span></span>  
  
8.  <span data-ttu-id="05112-133">Seleccione **Puertos locales específicos** y escriba un valor de **80**.</span><span class="sxs-lookup"><span data-stu-id="05112-133">Select **Specific Local Ports** and type a value of **80**.</span></span>  
  
9. <span data-ttu-id="05112-134">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="05112-134">Click **Next**.</span></span>  
  
10. <span data-ttu-id="05112-135">En la página **Acción** , haga clic en **Permitir la conexión**.</span><span class="sxs-lookup"><span data-stu-id="05112-135">On the **Action** page click **Allow the connection**.</span></span>  
  
11. <span data-ttu-id="05112-136">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="05112-136">Click **Next**.</span></span>  
  
12. <span data-ttu-id="05112-137">En la página **Perfil** , haga clic en las opciones adecuadas para su entorno.</span><span class="sxs-lookup"><span data-stu-id="05112-137">On the **Profile** page click the appropriate options for your environment.</span></span>  
  
13. <span data-ttu-id="05112-138">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="05112-138">Click **Next**.</span></span>  
  
14. <span data-ttu-id="05112-139">En la página **Nombre** , escriba un nombre de**ReportServer (TCP en el puerto 80)**.</span><span class="sxs-lookup"><span data-stu-id="05112-139">On the **Name** page enter a name of**ReportServer (TCP on port 80)**</span></span>  
  
15. <span data-ttu-id="05112-140">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="05112-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="05112-141">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="05112-141">Restart the computer.</span></span>  
  
#### <a name="to-open-port-80-on-windows-vista-or-windows-server-2008"></a><span data-ttu-id="05112-142">Para abrir el puerto 80 en Windows Vista o Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="05112-142">To open port 80 on Windows Vista or Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="05112-143">En el menú **Inicio** , haga clic en **Panel de control**, haga clic en **seguridad**y, a continuación, haga clic en firewall de **Windows**.</span><span class="sxs-lookup"><span data-stu-id="05112-143">From the **Start** menu, click **Control Panel**, click **Security**, and then click **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="05112-144">Haga clic en **Permitir un programa a través del Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="05112-144">Click **Allow a program through Windows Firewall**.</span></span>  
  
3.  <span data-ttu-id="05112-145">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="05112-145">Click **Continue**.</span></span>  
  
4.  <span data-ttu-id="05112-146">En la pestaña excepciones, haga clic en **Agregar puerto**.</span><span class="sxs-lookup"><span data-stu-id="05112-146">On the Exceptions tab, click **Add Port**.</span></span>  
  
5.  <span data-ttu-id="05112-147">En nombre, escriba **ReportServer (TCP en el puerto 80)**.</span><span class="sxs-lookup"><span data-stu-id="05112-147">In Name, type **ReportServer (TCP on port 80)**.</span></span>  
  
6.  <span data-ttu-id="05112-148">En número de puerto, escriba **80**.</span><span class="sxs-lookup"><span data-stu-id="05112-148">In Port number, type **80**.</span></span>  
  
7.  <span data-ttu-id="05112-149">Compruebe que **TCP** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="05112-149">Verify that **TCP** is selected.</span></span>  
  
8.  <span data-ttu-id="05112-150">Haga clic en **Cambiar ámbito**.</span><span class="sxs-lookup"><span data-stu-id="05112-150">Click **Change Scope**.</span></span>  
  
9. <span data-ttu-id="05112-151">Haga clic en **mi red (subred) solamente**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05112-151">Click **My network (subnet) only**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="05112-152">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="05112-152">Click **OK** to close the dialog box.</span></span>  
  
11. <span data-ttu-id="05112-153">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="05112-153">Restart the computer.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="05112-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="05112-154">Next Steps</span></span>  
 <span data-ttu-id="05112-155">Después de abrir el puerto y antes de confirmar si los usuarios remotos pueden tener acceso al servidor de informes en el puerto que abre, debe conceder acceso de usuario al servidor de informes a través de las asignaciones de roles en Inicio y en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="05112-155">After you open the port and before you confirm whether remote users can access the report server on the port that you open, you must grant user access to the report server through role assignments on Home and at the site level.</span></span> <span data-ttu-id="05112-156">Puede abrir un puerto correctamente y seguir teniendo conexiones del servidor de informes erróneas si los usuarios no tienen permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="05112-156">You can open a port correctly and still have report server connections fail if users do not have sufficient permissions.</span></span> <span data-ttu-id="05112-157">Para más información, vea [Conceder a un usuario acceso a un servidor de informes &#40;Administrador de informes&#41;](../security/grant-user-access-to-a-report-server.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05112-157">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](../security/grant-user-access-to-a-report-server.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="05112-158">También puede comprobar que el puerto se abre correctamente iniciando el Administrador de informes en un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="05112-158">You can also verify that the port is opened correctly by starting Report Manager on a different computer.</span></span> <span data-ttu-id="05112-159">Para más información, vea [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05112-159">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05112-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05112-160">See Also</span></span>  
 <span data-ttu-id="05112-161">[Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05112-161">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="05112-162">[Configurar las direcciones URL del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05112-162">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="05112-163">[Crear una base de datos del servidor de informes &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05112-163">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="05112-164">[Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05112-164">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="05112-165">Administración de un servidor de informes en modo nativo de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="05112-165">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
