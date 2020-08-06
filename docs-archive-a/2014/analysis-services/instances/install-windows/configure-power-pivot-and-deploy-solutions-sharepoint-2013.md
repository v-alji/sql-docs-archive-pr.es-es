---
title: Configurar PowerPivot e implementar soluciones (SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6401fd92-f43b-450e-8298-12db644c25bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7eaea7f9c490fd320d6dbd0777519eeca218b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744938"
---
# <a name="configure-powerpivot-and-deploy-solutions-sharepoint-2013"></a><span data-ttu-id="8f033-102">Configurar PowerPivot e implementar soluciones (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="8f033-102">Configure PowerPivot and Deploy Solutions (SharePoint 2013)</span></span>
  <span data-ttu-id="8f033-103">En estos temas se describen la implementación y la configuración de mejoras de nivel intermedio realizadas en las características de PowerPivot en [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] , incluidas la galería de PowerPivot, la programación de actualización de datos, el panel de administración y los proveedores de datos.</span><span class="sxs-lookup"><span data-stu-id="8f033-103">This topics describes the deployment and configuration of middle-tier enhancements to the PowerPivot features in [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] including PowerPivot Gallery, Schedule data refresh, Management Dashboard, and data providers.</span></span> <span data-ttu-id="8f033-104">Ejecute la herramienta de **Configuración de PowerPivot para SharePoint 2013** para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f033-104">Run **PowerPivot for SharePoint 2013 Configuration** tool to complete the following:</span></span>  
  
-   <span data-ttu-id="8f033-105">Implementar archivos de solución de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-105">Deploy SharePoint solution files.</span></span>  
  
-   <span data-ttu-id="8f033-106">Crear una aplicación de servicio PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="8f033-106">Create a PowerPivot service application.</span></span>  
  
-   <span data-ttu-id="8f033-107">Configurar una aplicación de Excel Services para que use un servidor de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-107">Configure an Excel Services Application to use an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="8f033-108">Para obtener información sobre los servicios back-end e instalar un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] servidor en modo de SharePoint, consulte [PowerPivot para SharePoint instalación de 2013](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode).</span><span class="sxs-lookup"><span data-stu-id="8f033-108">For information on backend services and installing a [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode, see [PowerPivot for SharePoint 2013 Installation](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode).</span></span>  
  
 <span data-ttu-id="8f033-109">Para obtener información sobre cómo instalar la herramienta de configuración de PowerPivot para SharePoint 2013, vea [instalar o desinstalar el complemento de PowerPivot para SharePoint &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013)</span><span class="sxs-lookup"><span data-stu-id="8f033-109">For information on installing the PowerPivot for SharePoint 2013 Configuration tool, see [Install or Uninstall the PowerPivot for SharePoint Add-in &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013)</span></span>  
  
 <span data-ttu-id="8f033-110">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="8f033-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="8f033-111">Ejecutar la configuración de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="8f033-111">Run PowerPivot for SharePoint 2013 configuration</span></span>](#bkmk_run_configuration_tool)  
  
 [<span data-ttu-id="8f033-112">Comprobar la configuración de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-112">Verify PowerPivot Configuration</span></span>](#bkmk_verify_powerpivot)  
  
 [<span data-ttu-id="8f033-113">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="8f033-113">Troubleshoot Issues</span></span>](#bkmk_troubleshoot_issues)  
  
##  <a name="run-powerpivot-for-sharepoint-2013-configuration"></a><a name="bkmk_run_configuration_tool"></a><span data-ttu-id="8f033-114">Ejecución de la configuración de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="8f033-114">Run PowerPivot for SharePoint 2013 configuration</span></span>  
 <span data-ttu-id="8f033-115">**Nota** : el asistente para la instalación de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] instala dos herramientas de configuración diferentes para [!INCLUDE[ssGeminiLong](../../../includes/ssgeminilong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f033-115">**Note:** The [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] setup wizard installs two different configuration tools for [!INCLUDE[ssGeminiLong](../../../includes/ssgeminilong-md.md)].</span></span> <span data-ttu-id="8f033-116">Cada una de ellas admite una versión diferente de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-116">They each support a different version of SharePoint.</span></span>  
  
|<span data-ttu-id="8f033-117">Nombre</span><span class="sxs-lookup"><span data-stu-id="8f033-117">Name</span></span>|<span data-ttu-id="8f033-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f033-118">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8f033-119">Configuración de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="8f033-119">PowerPivot for SharePoint 2013 Configuration</span></span>|<span data-ttu-id="8f033-120">SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="8f033-120">SharePoint 2013</span></span>|  
|<span data-ttu-id="8f033-121">Herramienta de configuración de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-121">PowerPivot Configuration Tool</span></span>|<span data-ttu-id="8f033-122">SharePoint 2010 con SharePoint 2010 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="8f033-122">SharePoint 2010 with SharePoint 2010 Service Pack 1 (SP1)</span></span>|  
  
 <span data-ttu-id="8f033-123">**Nota** : para completar los pasos siguientes, debe ser administrador de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="8f033-123">**Note:** To complete the following steps, you must be a farm administrator.</span></span> <span data-ttu-id="8f033-124">Si ve un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f033-124">If you see an error message similar to the following:</span></span>  
  
-   <span data-ttu-id="8f033-125">"El usuario no es un administrador de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="8f033-125">"The user is not a farm administrator.</span></span> <span data-ttu-id="8f033-126">Solucione los errores de validación y vuelva a intentarlo."</span><span class="sxs-lookup"><span data-stu-id="8f033-126">Please address the validation failures and try again."</span></span>  
  
 <span data-ttu-id="8f033-127">Inicie sesión como la cuenta que instaló SharePoint o configure la cuenta de instalación como administrador principal del sitio de Administración central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-127">Either login as the account that installed SharePoint or configure the setup account as the primary administrator of the SharePoint Central Administration Site.</span></span>  
  
1.  <span data-ttu-id="8f033-128">En el menú **Inicio** , haga clic sucesivamente en **Todos los programas**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Herramientas de configuración**y **Configuración de PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="8f033-128">On the **Start** menu, click **All Programs**, and then click [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], click **Configuration Tools**, and then click **PowerPivot For SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="8f033-129">Esta herramienta solo se muestra cuando PowerPivot para SharePoint está instalado en el servidor local.</span><span class="sxs-lookup"><span data-stu-id="8f033-129">Toold is listed only when PowerPivot for SharePoint is installed on the local server.</span></span>  
  
2.  <span data-ttu-id="8f033-130">Haga clic en **Configurar o reparar PowerPivot para SharePoint** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f033-130">Click **Configure or Repair PowerPivot for SharePoint** and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8f033-131">La herramienta ejecuta una validación para comprobar el estado actual de PowerPivot y los pasos necesarios para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="8f033-131">The tool runs validation to verify the current state of PowerPivot and what steps are required to complete configuration.</span></span> <span data-ttu-id="8f033-132">Expanda la ventana al tamaño máximo.</span><span class="sxs-lookup"><span data-stu-id="8f033-132">Expand the window to full size.</span></span> <span data-ttu-id="8f033-133">Aparecerá una barra de botones en la parte inferior de la ventana con los comandos **Validar\*\*\*\*Ejecutar**y **Salir** .</span><span class="sxs-lookup"><span data-stu-id="8f033-133">You should see a button bar at the bottom of the window that includes **Validate**, **Run**, and **Exit** commands.</span></span>  
  
4.  <span data-ttu-id="8f033-134">En la pestaña **Parámetros** :</span><span class="sxs-lookup"><span data-stu-id="8f033-134">On the **Parameters** tab:</span></span>  
  
    1.  <span data-ttu-id="8f033-135">**Nombre de usuario de cuenta predeterminada**: escriba una cuenta de usuario de dominio para la cuenta predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8f033-135">**Default Account UserName**: Enter a domain user account for the default account.</span></span> <span data-ttu-id="8f033-136">Esta cuenta se usará para aprovisionar servicios, incluido el grupo de aplicaciones de servicios PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="8f033-136">This account will be used to provision services, including the PowerPivot service application pool.</span></span> <span data-ttu-id="8f033-137">No especifique ninguna cuenta integrada, como Network Service o Local System.</span><span class="sxs-lookup"><span data-stu-id="8f033-137">Do not specify a built-in account such as Network Service or Local System.</span></span> <span data-ttu-id="8f033-138">La herramienta bloquea las configuraciones que especifican cuentas integradas.</span><span class="sxs-lookup"><span data-stu-id="8f033-138">The tool blocks configurations that specify built-in accounts.</span></span>  
  
    2.  <span data-ttu-id="8f033-139">**Servidor de bases de datos**: puede usar el motor de bases de datos de SQL Server admitido para la granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-139">**Database Server**: You can use SQL Server Database engine that is supported for the SharePoint farm.</span></span>  
  
    3.  <span data-ttu-id="8f033-140">**Frase de contraseña**: escriba una frase de contraseña.</span><span class="sxs-lookup"><span data-stu-id="8f033-140">**Passphrase**: Enter a passphrase.</span></span> <span data-ttu-id="8f033-141">Si va a crear una nueva granja de SharePoint, la frase de contraseña se usa siempre que se agrega un servidor o una aplicación a la granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-141">If you are creating a new SharePoint farm, the passphrase is used whenever you add a server or application to the SharePoint farm.</span></span> <span data-ttu-id="8f033-142">Si la granja existe todavía, escriba la frase de contraseña que le permitirá agregar una aplicación de servidor a la granja.</span><span class="sxs-lookup"><span data-stu-id="8f033-142">If the farm already exists, enter the passphrase that allows you to add a server application to the farm.</span></span>  
  
    4.  <span data-ttu-id="8f033-143">**Servidor PowerPivot para Excel Services**: escriba el nombre de un servidor de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f033-143">**PowerPivot Server for Excel Services**: Type the name of an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] SharePoint mode server.</span></span> <span data-ttu-id="8f033-144">En una implementación de un solo servidor, es el mismo que el servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="8f033-144">In a single-server deployment, it is the same as the database server.</span></span> `[ServerName]\powerpivot`  
  
    5.  <span data-ttu-id="8f033-145">Haga clic en **Crear colección de sitios** en la ventana izquierda.</span><span class="sxs-lookup"><span data-stu-id="8f033-145">Click **Create Site Collection** in the left window.</span></span> <span data-ttu-id="8f033-146">Anote la **Dirección URL del sitio** para pueda consultarla en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f033-146">Note **Site URL** so you can reference it in later steps.</span></span> <span data-ttu-id="8f033-147">Si el servidor de SharePoint no está configurado todavía, el asistente para la configuración usa como valor predeterminado la aplicación web y las direcciones URL de las colecciones de sitios hasta la raíz de `http://[ServerName]`.</span><span class="sxs-lookup"><span data-stu-id="8f033-147">If the SharePoint server is not already configured, then the configuration wizard defaults the web application, and site collection URLs to the root of `http://[ServerName]`.</span></span> <span data-ttu-id="8f033-148">Para modificar los valores predeterminados, examine las páginas siguientes en la ventana izquierda: **Crear aplicación web predeterminada** e **Implementar solución de aplicación web**</span><span class="sxs-lookup"><span data-stu-id="8f033-148">To modify the defaults review the following pages in the left window: **Create Default Web application** and **Deploy Web Application Solution**</span></span>  
  
5.  <span data-ttu-id="8f033-149">Opcionalmente, revise los valores restantes de entrada utilizados para completar cada acción.</span><span class="sxs-lookup"><span data-stu-id="8f033-149">Optionally, review the remaining input values used to complete each action.</span></span> <span data-ttu-id="8f033-150">Haga clic en cada acción de la ventana izquierda para ver y examinar los detalles de la acción.</span><span class="sxs-lookup"><span data-stu-id="8f033-150">Click each action in the left window to see and review the details of the action.</span></span> <span data-ttu-id="8f033-151">Para obtener más información acerca de cada uno, vea la sección "valores de entrada utilizados para configurar el servidor en [configurar o reparar PowerPivot para SharePoint 2010 &#40;herramienta de configuración de PowerPivot&#41;](../../configure-repair-powerpivot-sharepoint-2010.md) en este tema.</span><span class="sxs-lookup"><span data-stu-id="8f033-151">For more information about each one, see the section "Input values used to configure the server in [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../configure-repair-powerpivot-sharepoint-2010.md) in this topic.</span></span>  
  
6.  <span data-ttu-id="8f033-152">Si lo desea, quite cualquier acción que no desee procesar en este momento.</span><span class="sxs-lookup"><span data-stu-id="8f033-152">Optionally, remove any actions that you do not want to process at this time.</span></span> <span data-ttu-id="8f033-153">Por ejemplo, si desea configurar el Servicio de almacenamiento seguro más adelante, haga clic en **Configurar el servicio de almacenamiento seguro**y, a continuación, desactive la casilla **Incluir esta acción en la lista de tareas**.</span><span class="sxs-lookup"><span data-stu-id="8f033-153">For example, if you want to configure Secure Store Service later, click **Configure Secure Store Service**, and then clear the checkbox **Include this action in the task list**.</span></span>  
  
7.  <span data-ttu-id="8f033-154">Haga clic en **Validar** para comprobar si la herramienta tiene suficiente información para procesar las acciones de la lista.</span><span class="sxs-lookup"><span data-stu-id="8f033-154">Click **Validate** to check whether the tool has sufficient information to process the actions in the list.</span></span> <span data-ttu-id="8f033-155">Si ve errores de validación, haga clic las en advertencias en el panel izquierdo para ver detalles del error de validación.</span><span class="sxs-lookup"><span data-stu-id="8f033-155">If you see validation errors, click the warnings in the left pane to see details of the validation error.</span></span> <span data-ttu-id="8f033-156">Corrija los errores de validación y vuelva a hacer clic en **Validar** .</span><span class="sxs-lookup"><span data-stu-id="8f033-156">Correct any validation errors and then click **Validate** again.</span></span>  
  
8.  <span data-ttu-id="8f033-157">Haga clic en **Ejecutar** para procesar todas las acciones de la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="8f033-157">Click **Run** to process all of the actions in the task list.</span></span> <span data-ttu-id="8f033-158">Tenga en cuenta que **Ejecutar** estará disponible cuando valide las acciones.</span><span class="sxs-lookup"><span data-stu-id="8f033-158">Note that **Run** becomes available after you validate the actions.</span></span> <span data-ttu-id="8f033-159">Si **Ejecutar** no está habilitado, haga clic en **Validar** primero.</span><span class="sxs-lookup"><span data-stu-id="8f033-159">If **Run** is not enabled, click **Validate** first.</span></span>  
  
 <span data-ttu-id="8f033-160">Para obtener más información, vea [configurar o reparar PowerPivot para SharePoint 2010 &#40;herramienta de configuración de PowerPivot&#41;](../../configure-repair-powerpivot-sharepoint-2010.md)</span><span class="sxs-lookup"><span data-stu-id="8f033-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../configure-repair-powerpivot-sharepoint-2010.md)</span></span>  
  
##  <a name="verify-powerpivot-configuration"></a><a name="bkmk_verify_powerpivot"></a><span data-ttu-id="8f033-161">Comprobar la configuración de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-161">Verify PowerPivot Configuration</span></span>  
 <span data-ttu-id="8f033-162">**Servicios:**</span><span class="sxs-lookup"><span data-stu-id="8f033-162">**Services:**</span></span>  
  
1.  <span data-ttu-id="8f033-163">En administración central, en configuración del sistema, haga clic en **administrar servicios en el servidor**.</span><span class="sxs-lookup"><span data-stu-id="8f033-163">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="8f033-164">Compruebe que se hayan iniciado **SQL Server Analysis Services** y **Servicio de sistema de SQL Server PowerPivot** .</span><span class="sxs-lookup"><span data-stu-id="8f033-164">Verify that **SQL Server Analysis Services** and **SQL Server PowerPivot System Service** are started.</span></span>  
  
 <span data-ttu-id="8f033-165">**Característica de granja:**</span><span class="sxs-lookup"><span data-stu-id="8f033-165">**Farm Feature:**</span></span>  
  
1.  <span data-ttu-id="8f033-166">En Administración central, en Configuración del sistema, haga clic en **Administrar características de la granja**.</span><span class="sxs-lookup"><span data-stu-id="8f033-166">In Central Administration, in System Settings, click **Manage farm features**.</span></span>  
  
2.  <span data-ttu-id="8f033-167">Compruebe que la **Característica de integración de PowerPivot** está **Activa**.</span><span class="sxs-lookup"><span data-stu-id="8f033-167">Verify that **PowerPivot Integration Feature** is **Active**.</span></span>  
  
 <span data-ttu-id="8f033-168">**Característica de colección de sitios:**</span><span class="sxs-lookup"><span data-stu-id="8f033-168">**Site Collection Feature:**</span></span>  
  
1.  <span data-ttu-id="8f033-169">Vaya a la dirección URL del sitio creada por la herramienta de configuración.</span><span class="sxs-lookup"><span data-stu-id="8f033-169">Browse to your site URL that was created by the Configuration tool.</span></span>  
  
     <span data-ttu-id="8f033-170">Haga clic en **configuración**![configuración de SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Configuración de SharePoint")y, a continuación, en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="8f033-170">Click **Settings**![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings"), and then click **Site Settings**.</span></span>  
  
     <span data-ttu-id="8f033-171">Haga clic en **Características de la colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="8f033-171">Click **Site Collection Features**.</span></span>  
  
2.  <span data-ttu-id="8f033-172">Compruebe que **Característica de integración de PowerPivot para colecciones de sitios** está **Activa**.</span><span class="sxs-lookup"><span data-stu-id="8f033-172">Verify that **PowerPivot Feature Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="8f033-173">**Aplicación de servicio PowerPivot:**</span><span class="sxs-lookup"><span data-stu-id="8f033-173">**PowerPivot Service Application:**</span></span>  
  
1.  <span data-ttu-id="8f033-174">En Administración central, en **Administración de aplicaciones**, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="8f033-174">In Central Administration, in the **Application Management**, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="8f033-175">Compruebe que el estado de la aplicación de servicio es **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="8f033-175">Verify the service application status is **started**.</span></span> <span data-ttu-id="8f033-176">El nombre predeterminado es **aplicación de servicio PowerPivot predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="8f033-176">The default name is **Default PowerPivot Service Application**.</span></span>  
  
     <span data-ttu-id="8f033-177">Haga clic en el nombre de la aplicación de servicio para abrir el Panel de administración de PowerPivot para la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="8f033-177">Click the name of the services application to open the PowerPivot Management Dashboard for the service application opens.</span></span> <span data-ttu-id="8f033-178">Al usarse por primera vez, el panel tarda varios minutos en cargarse.</span><span class="sxs-lookup"><span data-stu-id="8f033-178">On first use, the dashboard takes several minutes to load.</span></span>  
  
 <span data-ttu-id="8f033-179">Para obtener más información, consulte [Verify a PowerPivot for SharePoint Installation](https://docs.microsoft.com/analysis-services/instances/install-windows/verify-a-power-pivot-for-sharepoint-installation).</span><span class="sxs-lookup"><span data-stu-id="8f033-179">For more information, see [Verify a PowerPivot for SharePoint Installation](https://docs.microsoft.com/analysis-services/instances/install-windows/verify-a-power-pivot-for-sharepoint-installation).</span></span>  
  
##  <a name="troubleshoot-issues"></a><a name="bkmk_troubleshoot_issues"></a><span data-ttu-id="8f033-180">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="8f033-180">Troubleshoot Issues</span></span>  
 <span data-ttu-id="8f033-181">Como ayuda para solucionar problemas, es conveniente comprobar que el registro de diagnósticos esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="8f033-181">To assist in troubleshooting issues, it is a good idea to verify the diagnostic logging is enabled.</span></span>  
  
1.  <span data-ttu-id="8f033-182">En Administración central de SharePoint, haga clic en **Supervisión** y, a continuación, haga clic en **Configurar la recolección de datos de uso y estado**.</span><span class="sxs-lookup"><span data-stu-id="8f033-182">In SharePoint Central Administration, click **Monitoring** and then click **Configure usage and health data collection**.</span></span>  
  
2.  <span data-ttu-id="8f033-183">Compruebe que **Habilitar la recolección de datos de uso** esté activada.</span><span class="sxs-lookup"><span data-stu-id="8f033-183">Verify **Enable usage data collection** is selected.</span></span>  
  
3.  <span data-ttu-id="8f033-184">Compruebe que los eventos siguientes estén seleccionados:</span><span class="sxs-lookup"><span data-stu-id="8f033-184">Verify the following events are selected:</span></span>  
  
    -   <span data-ttu-id="8f033-185">Definición de campos de uso para telemetría de educación</span><span class="sxs-lookup"><span data-stu-id="8f033-185">Definition of usage fields for Education telemetry</span></span>  
  
    -   <span data-ttu-id="8f033-186">Conexiones de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-186">PowerPivot Connects</span></span>  
  
    -   <span data-ttu-id="8f033-187">Uso de datos de carga de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-187">PowerPivot Load Data Usage</span></span>  
  
    -   <span data-ttu-id="8f033-188">Uso de consultas de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-188">PowerPivot Query Usage</span></span>  
  
    -   <span data-ttu-id="8f033-189">Uso de datos de descarga de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="8f033-189">PowerPivot Unload Data Usage</span></span>  
  
4.  <span data-ttu-id="8f033-190">Compruebe que **Habilitar la recolección de datos de mantenimiento** esté activada.</span><span class="sxs-lookup"><span data-stu-id="8f033-190">Verify **Enable health data collection** is selected.</span></span>  
  
5.  <span data-ttu-id="8f033-191">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f033-191">Click **OK**.</span></span>  
  
 <span data-ttu-id="8f033-192">Para obtener más información acerca de la solución de problemas de la actualización de datos, consulte [Troubleshooting PowerPivot Data Refresh](https://social.technet.microsoft.com/wiki/contents/articles/3870.troubleshooting-powerpivot-data-refresh.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/3870.troubleshooting-powerpivot-data-refresh.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8f033-192">For more information on trouble shooting data refresh, see [Troubleshooting PowerPivot Data Refresh](https://social.technet.microsoft.com/wiki/contents/articles/3870.troubleshooting-powerpivot-data-refresh.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/3870.troubleshooting-powerpivot-data-refresh.aspx).</span></span>  
  
 <span data-ttu-id="8f033-193">Para obtener más información acerca de la herramienta de configuración, vea [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8f033-193">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>  
  
  