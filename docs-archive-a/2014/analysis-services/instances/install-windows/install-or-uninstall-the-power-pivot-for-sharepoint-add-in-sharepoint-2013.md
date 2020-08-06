---
title: Instalar o desinstalar el complemento de PowerPivot para SharePoint (SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: fe13ce8b-9369-4126-928a-9426f9119424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7df54d11021163167149e5b0c1edd960fee1a2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744918"
---
# <a name="install-or-uninstall-the-powerpivot-for-sharepoint-add-in-sharepoint-2013"></a><span data-ttu-id="847ca-102">Instalar o desinstalar el complemento PowerPivot para SharePoint (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="847ca-102">Install or Uninstall the PowerPivot for SharePoint Add-in (SharePoint 2013)</span></span>
  [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="847ca-103">es una colección de componentes de servidor de aplicaciones y servicios back-end que ofrecen acceso a datos de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] en una granja de [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="847ca-103">is a collection of application server components and back-end services that provide [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] data access in a [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] farm.</span></span> <span data-ttu-id="847ca-104">El complemento [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint (**spPowerpivot.msi**) es un paquete de instalación que se usa para instalar los componentes de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="847ca-104">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint add-in (**spPowerpivot.msi**) is an installer package used to install the application server components.</span></span>

-   <span data-ttu-id="847ca-105">El complemento no es necesario para las implementaciones de SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="847ca-105">The add-in is not required for SharePoint 2010 deployments.</span></span>

-   <span data-ttu-id="847ca-106">El complemento no es obligatorio en una implementación de servidor única que incluya SharePoint 2013 y [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-106">The add-in is not required on a single server deployment that includes SharePoint 2013 and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="847ca-107">Los componentes que instala el complemento se incluyen al instalar un servidor de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-107">The components installed by the add-in are included when you install an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="847ca-108">Para consultar diagramas de implementaciones de ejemplo con el complemento, vea [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="847ca-108">For diagrams of example deployments with the add-in, see [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span></span>

 <span data-ttu-id="847ca-109">**Nota** : en este tema se describe la instalación de los archivos de solución de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] y de la herramienta de configuración de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="847ca-109">**Note:** This topic describes installing the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] solution files and [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span> <span data-ttu-id="847ca-110">Después de la instalación, vea el tema siguiente para obtener información sobre la herramienta de configuración y las características adicionales, [configurar PowerPivot e implementar soluciones &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="847ca-110">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

 <span data-ttu-id="847ca-111">Para obtener información sobre cómo descargar **spPowerPivot.msi**, vea [Microsoft® SQL Server® 2014 PowerPivot® de Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span><span class="sxs-lookup"><span data-stu-id="847ca-111">For information on how to download **spPowerPivot.msi**, see [Microsoft® SQL Server® 2014 PowerPivot® for Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span></span>

 <span data-ttu-id="847ca-112">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="847ca-112">**In this topic:**</span></span>

-   [<span data-ttu-id="847ca-113">Fondo</span><span class="sxs-lookup"><span data-stu-id="847ca-113">Background</span></span>](#bkmk_background)

-   [<span data-ttu-id="847ca-114">¿Dónde instalar spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="847ca-114">Where to Install spPowerPivot.msi?</span></span>](#bkmk_where_to_install)

-   [<span data-ttu-id="847ca-115">Requisitos y requisitos previos</span><span class="sxs-lookup"><span data-stu-id="847ca-115">Requirements and Prerequisites</span></span>](#bkmk_prereq)

-   [<span data-ttu-id="847ca-116">Para instalar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="847ca-116">To Install PowerPivot for SharePoint</span></span>](#bkmk_install)

-   [<span data-ttu-id="847ca-117">Implementar los archivos de solución de SharePoint con la Herramienta de configuración de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="847ca-117">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>](#bkmk_deploy_solution)

-   [<span data-ttu-id="847ca-118">Desinstalar o reparar el complemento</span><span class="sxs-lookup"><span data-stu-id="847ca-118">Uninstall or repair the add-in</span></span>](#bkmk_remove_addin)

##  <a name="background"></a><a name="bkmk_background"></a> <span data-ttu-id="847ca-119">Información previa</span><span class="sxs-lookup"><span data-stu-id="847ca-119">Background</span></span>

-   <span data-ttu-id="847ca-120">**Servidor de aplicaciones:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] en SharePoint 2013 incluye el uso de libros como un origen de datos, actualización de datos programada y el Panel de administración de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="847ca-120">**Application Server:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] functionality in SharePoint 2013 includes using workbooks as a data source, scheduled data refresh, and the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] Management Dashboard.</span></span>

     [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="847ca-121">es un paquete de Windows Installer de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] (**spPowerpivot.msi**) que implementa las bibliotecas cliente de Analysis Services y copia los archivos de instalación de [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] al equipo.</span><span class="sxs-lookup"><span data-stu-id="847ca-121">is a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer package (**spPowerpivot.msi**) that deploys Analysis Services client libraries and copies [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] installation files to the computer.</span></span> <span data-ttu-id="847ca-122">El instalador no implementa ni configura características de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-122">The installer does not deploy or configure [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] features in SharePoint.</span></span> <span data-ttu-id="847ca-123">Se instalan los componentes siguientes de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="847ca-123">The following components install by default:</span></span>

    -   [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] <span data-ttu-id="847ca-124">2013. Este componente incluye scripts de PowerShell (archivos .ps1), paquetes de solución de SharePoint (.wsp) y la herramienta de configuración de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] para SharePoint 2013 para implementar [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] en una granja de SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="847ca-124">2013. This component includes PowerShell scripts (.ps1 files), SharePoint solution packages (.wsp), and the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 configuration tool to deploy [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in a SharePoint 2013 farm.</span></span>

    -   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="847ca-125">Proveedor OLE DB para Analysis Services (MSOLAP).</span><span class="sxs-lookup"><span data-stu-id="847ca-125">OLE DB Provider for Analysis Services (MSOLAP).</span></span>

    -   <span data-ttu-id="847ca-126">Proveedor de datos de ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="847ca-126">ADOMD.NET data provider.</span></span>

    -   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="847ca-127">Analysis Management Objects.</span><span class="sxs-lookup"><span data-stu-id="847ca-127">Analysis Management Objects.</span></span>

-   <span data-ttu-id="847ca-128">**Servicios backend** : si usa [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para Excel con el fin de crear libros que contienen datos analíticos, debe tener Excel Services configurado con un servidor de BI que ejecute [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint para obtener acceso a esos datos en un entorno de servidor.</span><span class="sxs-lookup"><span data-stu-id="847ca-128">**Backend services:** If you use [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for Excel to create workbooks that contain analytical data, you must have Excel Services configured with a BI server running [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode to access that data in a server environment.</span></span> <span data-ttu-id="847ca-129">Puede ejecutar el programa de instalación de SQL Server en un equipo que tenga instalado SharePoint Server 2013 o en un equipo diferente que no tenga ningún software de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-129">You can run SQL Server Setup on a computer that has SharePoint Server 2013 installed, or on a different computer that has no SharePoint software.</span></span> <span data-ttu-id="847ca-130">Analysis Services no tiene ninguna dependencia en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-130">Analysis Services does not have any dependencies on SharePoint.</span></span>

     <span data-ttu-id="847ca-131">Para obtener información acerca de la instalación, la desinstalación y la configuración de los servicios back-end, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="847ca-131">For more information on installing, uninstalling, and configuring the backend services, see the following:</span></span>

    -   [<span data-ttu-id="847ca-132">Instalación de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="847ca-132">PowerPivot for SharePoint 2013 Installation</span></span>](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode)

    -   [<span data-ttu-id="847ca-133">Desinstalar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="847ca-133">Uninstall PowerPivot for SharePoint</span></span>](../../../sql-server/install/uninstall-power-pivot-for-sharepoint.md)

##  <a name="where-to-install-sppowerpivotmsi"></a><a name="bkmk_where_to_install"></a><span data-ttu-id="847ca-134">¿Dónde instalar spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="847ca-134">Where to Install spPowerPivot.msi?</span></span>
 <span data-ttu-id="847ca-135">Se recomienda instalar **spPowerPivot.msi** en todos los servidores de la granja de servidores de SharePoint para mantener la coherencia de la configuración, incluidos los servidores de aplicaciones y los servidores front-end web.</span><span class="sxs-lookup"><span data-stu-id="847ca-135">A recommended best practice is to install **spPowerPivot.msi** on all servers in the SharePoint farm for configuration consistency, including application servers and web-front end servers.</span></span> <span data-ttu-id="847ca-136">El paquete del instalador incluye los proveedores de datos de Analysis Services y la herramienta de configuración de [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="847ca-136">The installer package includes the Analysis Services data providers as well as the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] configuration tool.</span></span> <span data-ttu-id="847ca-137">Al instalar **spPowerPivot.msi** puede personalizar la instalación si excluye componentes individuales.</span><span class="sxs-lookup"><span data-stu-id="847ca-137">When you install **spPowerPivot.msi** you can customize the installation by excluding individual components.</span></span>

 <span data-ttu-id="847ca-138">**Proveedores de datos** : varias tecnologías de SharePoint y SQL Server usan los proveedores de datos de Analysis Services, incluidos Excel Services, PerformancePoint Services y Power View.</span><span class="sxs-lookup"><span data-stu-id="847ca-138">**Data providers:** Several SharePoint and SQL Server technologies use the Analysis Services data providers including Excel Services, PerformancePoint Services, and Power View.</span></span> <span data-ttu-id="847ca-139">La instalación de **spPowerPivot.msi** en todos los servidores de SharePoint asegura que todo el conjunto de proveedores de datos de Analysis Services y la conectividad de PowerPivot están disponibles de forma coherente en toda la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="847ca-139">Installing **spPowerPivot.msi** on all SharePoint servers ensures the full set of Analysis Services data providers and PowerPivot connectivity is consistently available across the farm.</span></span>

> [!NOTE]
>  <span data-ttu-id="847ca-140">Debe instalar los proveedores de datos de Analysis Services en un servidor de SharePoint 2013 mediante **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="847ca-140">You must install the Analysis Services data providers on a SharePoint 2013 server using **spPowerPivot.msi**.</span></span> <span data-ttu-id="847ca-141">No se admiten otros paquetes de instalador disponibles en el Feature Pack de [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] porque estos paquetes no incluyen los archivos auxiliares de SharePoint 2013 que los proveedores de datos necesitan en este entorno.</span><span class="sxs-lookup"><span data-stu-id="847ca-141">Other installer packages available in the [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack are not supported because these packages do not include the SharePoint 2013 support files that the data providers require in this environment.</span></span>

 <span data-ttu-id="847ca-142">**Herramienta de configuración** : la herramienta de configuración de PowerPivot para SharePoint 2013 solo es necesaria en uno de los servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-142">**Configuration Tool:** The PowerPivot for SharePoint 2013 configuration tool is required on only one of the SharePoint servers.</span></span> <span data-ttu-id="847ca-143">Sin embargo, en granjas con varios servidores se recomienda instalar la herramienta de configuración al menos en dos servidores para poder tener acceso a dicha herramienta si uno de los dos servidores está sin conexión.</span><span class="sxs-lookup"><span data-stu-id="847ca-143">However a recommended best practice in multi-server farms is to install the configuration tool on at least two servers so you have access to the configuration tool if one of the two servers is offline.</span></span>

##  <a name="requirements-and-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="847ca-144">Requisitos y requisitos previos</span><span class="sxs-lookup"><span data-stu-id="847ca-144">Requirements and Prerequisites</span></span>

-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="847ca-145">SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="847ca-145">SharePoint Server 2013.</span></span>

-   <span data-ttu-id="847ca-146">**spPowerPivot.msi** solo es de 64 bits, de acuerdo con los requisitos de productos y tecnologías de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-146">**spPowerPivot.msi** is 64-bit only, in accordance with the requirements of SharePoint products and technologies.</span></span>

-   <span data-ttu-id="847ca-147">Servidor de [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] en modo PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="847ca-147">A [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] server in PowerPivot mode.</span></span> <span data-ttu-id="847ca-148">Excel Services usará la instancia de SQL Server Analysis Services como un servidor de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="847ca-148">Excel Services will use the SQL Server Analysis Services instance as a PowerPivot server.</span></span> <span data-ttu-id="847ca-149">Analysis Services se puede ejecutar en un equipo local o remoto.</span><span class="sxs-lookup"><span data-stu-id="847ca-149">Analysis Services can run on the local or a remote computer.</span></span>

-   <span data-ttu-id="847ca-150">**Permisos:** para instalar [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], el usuario actual debe ser administrador del equipo y miembro de un grupo de administradores de la granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-150">**Permissions:** To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], the current user is required to be an administrator on the computer and a SharePoint Farm Administrators group.</span></span>

-   <span data-ttu-id="847ca-151">Para obtener más información sobre [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] los requisitos y los requisitos previos, vaya a [requisitos de hardware y Software para Analysis Services Server en modo de SharePoint &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="847ca-151">For more information on [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requirements and pre-requisites, go to [Hardware and Software Requirements for Analysis Services Server in SharePoint Mode &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span></span>

##  <a name="to-install-powerpivot-for-sharepoint"></a><a name="bkmk_install"></a><span data-ttu-id="847ca-152">Para instalar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="847ca-152">To Install PowerPivot for SharePoint</span></span>
 <span data-ttu-id="847ca-153">El paquete del instalador **spPowerpivot.msi** admite tanto una interfaz gráfica de usuario como un modo de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="847ca-153">The **spPowerpivot.msi** installer package supports both a graphical user interface and a command-line mode.</span></span> <span data-ttu-id="847ca-154">Ambos métodos de instalación necesitan que se ejecute el archivo .msi con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="847ca-154">Both methods of installation require that you run the .msi with administrator privileges.</span></span> <span data-ttu-id="847ca-155">Después de la instalación, vea el tema siguiente para obtener información sobre la herramienta de configuración y las características adicionales, [configurar PowerPivot e implementar soluciones &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="847ca-155">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

### <a name="user-interface-installation"></a><span data-ttu-id="847ca-156">Instalación mediante la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="847ca-156">User interface installation</span></span>
 <span data-ttu-id="847ca-157">Para instalar [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] con la interfaz gráfica de usuario, complete los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="847ca-157">To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] with the graphical user interface, complete the following steps:</span></span>

1.  <span data-ttu-id="847ca-158">Ejecute **SpPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="847ca-158">Run **SpPowerPivot.msi**.</span></span>

2.  <span data-ttu-id="847ca-159">Haga clic en **Siguiente** en la página de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="847ca-159">Click **Next** on the Welcome page.</span></span>

3.  <span data-ttu-id="847ca-160">Examine y acepte el contrato de licencia y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="847ca-160">Review and accept the license agreement, then click **Next**.</span></span>

4.  <span data-ttu-id="847ca-161">En la página **Selección de características** , todas las características están seleccionadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="847ca-161">On the **Feature Selection** page, all of the features are selected by default.</span></span>

5.  <span data-ttu-id="847ca-162">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="847ca-162">Click **Next**.</span></span>

6.  <span data-ttu-id="847ca-163">Haga clic en **Instalar** para finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="847ca-163">Click **Install** to install to finish the installation.</span></span>

### <a name="command-line-installation"></a><span data-ttu-id="847ca-164">Instalación desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="847ca-164">Command Line Installation</span></span>
 <span data-ttu-id="847ca-165">Para realizar una instalación desde la línea de comandos, abra un símbolo del sistema con permisos administrativos y ejecute **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="847ca-165">For a command-line installation, open a command prompt with administrative permissions, and then run the **spPowerPivot.msi**.</span></span> <span data-ttu-id="847ca-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="847ca-166">For example:</span></span>

 <span data-ttu-id="847ca-167">`Msiexec.exe /i SpPowerPivot.msi`.</span><span class="sxs-lookup"><span data-stu-id="847ca-167">`Msiexec.exe /i SpPowerPivot.msi`.</span></span>

 <span data-ttu-id="847ca-168">Para crear un registro de instalación, use los modificadores de registro de MsiExec estándar.</span><span class="sxs-lookup"><span data-stu-id="847ca-168">To create an installation log, use the standard MsiExec logging switches.</span></span> <span data-ttu-id="847ca-169">En el ejemplo siguiente se crea el archivo de registro "Install_Log.txt" mediante el modificador de registro detallado "v".</span><span class="sxs-lookup"><span data-stu-id="847ca-169">The following example creates the log file "Install_Log.txt" using the "v" verbose logging switch.</span></span>

```cmd
Msiexec.exe /i SpPowerPivot.msi /L v c:\test\Install_Log.txt
```

### <a name="quiet-command-line-installation-for-scripting"></a><span data-ttu-id="847ca-170">Instalación silenciosa desde la línea de comandos para scripting</span><span class="sxs-lookup"><span data-stu-id="847ca-170">Quiet Command Line Installation for scripting</span></span>
 <span data-ttu-id="847ca-171">Puede usar los modificadores **/q** o **/Quiet** para una instalación "silenciosa" que no mostrará ningún cuadro de diálogo o advertencia.</span><span class="sxs-lookup"><span data-stu-id="847ca-171">You can use the **/q** or **/quiet** switches for a "quiet" installation that will not display any dialogs or warnings.</span></span> <span data-ttu-id="847ca-172">La instalación silenciosa es útil si desea incluir en el script la instalación del complemento.</span><span class="sxs-lookup"><span data-stu-id="847ca-172">The quiet installation is useful if you want to script the installation of the add-in.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="847ca-173">Si usa el modificador **q** para una instalación silenciosa desde la línea de comandos, el contrato de licencia para el usuario final no se mostrará.</span><span class="sxs-lookup"><span data-stu-id="847ca-173">If you use the **/q** switch for a silent command line installation, the end-user license agreement will not be displayed.</span></span> <span data-ttu-id="847ca-174">Independientemente del método de instalación, el uso de este software se rige por un contrato de licencia y usted es responsable de su cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="847ca-174">Regardless of the installation method, the use of this software is governed by a license agreement and you are responsible for complying with the license agreement.</span></span>

#### <a name="to-perform-a-quiet-installation"></a><span data-ttu-id="847ca-175">Para realizar una instalación silenciosa</span><span class="sxs-lookup"><span data-stu-id="847ca-175">To perform a quiet installation</span></span>

1.  <span data-ttu-id="847ca-176">Abra un símbolo del sistema **con permisos de administrador**.</span><span class="sxs-lookup"><span data-stu-id="847ca-176">Open a command prompt **with administrator permissions**.</span></span>

2.  <span data-ttu-id="847ca-177">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="847ca-177">Run the following command:</span></span>

    ```cmd
    Msiexec.exe /i spPowerPivot.msi /q
    ```

### <a name="command-line-installation-to-include-specific-components"></a><span data-ttu-id="847ca-178">Instalación desde la línea de comandos para incluir componentes específicos</span><span class="sxs-lookup"><span data-stu-id="847ca-178">Command Line Installation to include specific components</span></span>
 <span data-ttu-id="847ca-179">La herramienta de configuración de [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] no se necesita en todos los servidores de SharePoint, pero se recomienda instalarla al menos en dos servidores para que la herramienta de configuración esté disponible cuando se necesite.</span><span class="sxs-lookup"><span data-stu-id="847ca-179">The [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool is not required on every SharePoint server, however it is recommended to install it on at least two servers so the configuration tool is available when you need it.</span></span>

 <span data-ttu-id="847ca-180">Al instalar el paquete spPowerPivot.msi puede usar las opciones de línea de comandos e instalar elementos específicos, como los proveedores de datos y no la herramienta de configuración de [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="847ca-180">When you install the spPowerPivot.msi, you can use the command line options to install specific items, such as the data providers and not the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool.</span></span> <span data-ttu-id="847ca-181">La siguiente línea de comandos es un ejemplo de cómo instalar todos los componentes salvo la herramienta de configuración:</span><span class="sxs-lookup"><span data-stu-id="847ca-181">The following command line is an example of installing all components except the configuration tool:</span></span>

```
Msiexec /i spPowerPivot.msi AGREETOLICENSE="yes" ADDLOCAL=" SQL_OLAPDM,SQL_ADOMD,SQL_AMO,SQLAS_SP_Common"
```

|<span data-ttu-id="847ca-182">Opción</span><span class="sxs-lookup"><span data-stu-id="847ca-182">Option</span></span>|<span data-ttu-id="847ca-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="847ca-183">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="847ca-184">Analysis_Server_SP_addin</span><span class="sxs-lookup"><span data-stu-id="847ca-184">Analysis_Server_SP_addin</span></span>|<span data-ttu-id="847ca-185">Configuración de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="847ca-185">PowerPivot Configuration</span></span>|
|<span data-ttu-id="847ca-186">SQL_OLAPDM</span><span class="sxs-lookup"><span data-stu-id="847ca-186">SQL_OLAPDM</span></span>|<span data-ttu-id="847ca-187">MSOLAP</span><span class="sxs-lookup"><span data-stu-id="847ca-187">MSOLAP</span></span>|
|<span data-ttu-id="847ca-188">SQL_ADOMD</span><span class="sxs-lookup"><span data-stu-id="847ca-188">SQL_ADOMD</span></span>|<span data-ttu-id="847ca-189">Proveedor de ADOMD.net</span><span class="sxs-lookup"><span data-stu-id="847ca-189">ADOMD.net provider</span></span>|
|<span data-ttu-id="847ca-190">SQL_AMO</span><span class="sxs-lookup"><span data-stu-id="847ca-190">SQL_AMO</span></span>|<span data-ttu-id="847ca-191">Proveedor AMO</span><span class="sxs-lookup"><span data-stu-id="847ca-191">AMO provider</span></span>|
|<span data-ttu-id="847ca-192">SQLAS_SP_Common</span><span class="sxs-lookup"><span data-stu-id="847ca-192">SQLAS_SP_Common</span></span>|<span data-ttu-id="847ca-193">Componentes comunes de Analysis Services para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="847ca-193">Analysis Services common components for SharePoint 2013</span></span>|

##  <a name="deploy-the-sharepoint-solution-files-with-the-powerpivot-for-sharepoint-2013-configuration-tool"></a><a name="bkmk_deploy_solution"></a><span data-ttu-id="847ca-194">Implementar los archivos de solución de SharePoint con la herramienta de configuración de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="847ca-194">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>
 <span data-ttu-id="847ca-195">Tres de los archivos copiados al disco duro por spPowerPivot.msi son archivos de solución de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-195">Three of the files copied to the hard drive by spPowerPivot.msi are SharePoint solution files.</span></span> <span data-ttu-id="847ca-196">El ámbito de un archivo de solución es el nivel de aplicación web, mientras que el ámbito de los demás archivos es el nivel de granja.</span><span class="sxs-lookup"><span data-stu-id="847ca-196">The scope of one solution file is the Web application level while the scope of the other files is the farm level.</span></span> <span data-ttu-id="847ca-197">Los archivos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="847ca-197">The files are the following:</span></span>

-   `PowerPivotFarmSolution.wsp`

-   `PowerPivotFarm14Solution.wsp`

-   `PowerPivotWebApplicationSolution.wsp`

 <span data-ttu-id="847ca-198">Los archivos de solución se copian a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="847ca-198">The solution files are copied to the following folder:</span></span>

 `C:\Program Files\Microsoft SQL Server\120\Tools\PowerPivotTools\SPAddinConfiguration\Resources`

 <span data-ttu-id="847ca-199">Después de la instalación .msi, ejecute la Herramienta de configuración de [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] para configurar e implementar las soluciones de la granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="847ca-199">Following the .msi installation, run the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration Tool to configure and deploy the solutions in the SharePoint farm.</span></span>

### <a name="to-start-the-configuration-tool"></a><span data-ttu-id="847ca-200">Para iniciar la herramienta de configuración</span><span class="sxs-lookup"><span data-stu-id="847ca-200">To start the configuration tool</span></span> 

 <span data-ttu-id="847ca-201">En la pantalla de inicio de Windows, escriba "Power" y en los resultados de búsqueda de aplicaciones, haga clic en **configuración de PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="847ca-201">From the Windows Start screen type "power" and in the Apps search results, click **PowerPivot for SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="847ca-202">Tenga en cuenta que los resultados de la búsqueda pueden incluir dos vínculos porque el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instala distintas herramientas de configuración de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint 2010 y SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="847ca-202">Note that the search results may include two links because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup installs separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] configuration tools for SharePoint 2010 and SharePoint 2013.</span></span> <span data-ttu-id="847ca-203">Asegúrese de iniciar la herramienta de configuración de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="847ca-203">Make sure you start the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span>

 <span data-ttu-id="847ca-204">![dos herramientas de configuración de PowerPivot](../../media/as-powerpivot-configtools-bothicons.gif "dos herramientas de configuración de PowerPivot")</span><span class="sxs-lookup"><span data-stu-id="847ca-204">![two powerpivot configuration tools](../../media/as-powerpivot-configtools-bothicons.gif "two powerpivot configuration tools")</span></span>

 <span data-ttu-id="847ca-205">**O**</span><span class="sxs-lookup"><span data-stu-id="847ca-205">**Or**</span></span>

1.  <span data-ttu-id="847ca-206">Vaya a **Iniciar**, **Todos los programas**.</span><span class="sxs-lookup"><span data-stu-id="847ca-206">Go to **Start**, **All Programs**.</span></span>

2.  <span data-ttu-id="847ca-207">Haga clic en **Microsoft SQL Server 2014**.</span><span class="sxs-lookup"><span data-stu-id="847ca-207">Click **Microsoft SQL Server 2014**.</span></span>

3.  <span data-ttu-id="847ca-208">Haga clic en **Herramientas de configuración**.</span><span class="sxs-lookup"><span data-stu-id="847ca-208">Click **Configuration Tools**.</span></span>

4.  <span data-ttu-id="847ca-209">Haga clic en **Configuración de PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="847ca-209">Click **PowerPivot for SharePoint 2013 Configuration**.</span></span>

 <span data-ttu-id="847ca-210">Para obtener más información acerca de la herramienta de configuración, vea [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="847ca-210">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>

##  <a name="uninstall-or-repair-the-add-in"></a><a name="bkmk_remove_addin"></a><span data-ttu-id="847ca-211">Desinstalar o reparar el complemento</span><span class="sxs-lookup"><span data-stu-id="847ca-211">Uninstall or repair the add-in</span></span>

> [!CAUTION]
>  <span data-ttu-id="847ca-212">Si desinstala **spPowerPivot.msi** , se desinstalarán los proveedores de datos y la herramienta de configuración.</span><span class="sxs-lookup"><span data-stu-id="847ca-212">If you uninstall **spPowerPivot.msi** the data providers and the configuration tool are uninstalled.</span></span> <span data-ttu-id="847ca-213">La desinstalación de los proveedores de datos puede hacer que el servidor no pueda conectarse a PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="847ca-213">Uninstalling the data providers will cause the server to be unable to connect to PowerPivot.</span></span>

 <span data-ttu-id="847ca-214">Puede desinstalar o reparar [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="847ca-214">You can uninstall or repair [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] using one of the following methods:</span></span>

1.  <span data-ttu-id="847ca-215">**Panel de control de Windows** : seleccione **Microsoft SQL Server 2012 PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="847ca-215">**Windows control panel:** Select **Microsoft SQL Server 2012 PowerPivot for SharePoint 2013**.</span></span> <span data-ttu-id="847ca-216">Haga clic en **Desinstalar** o en **Reparar**.</span><span class="sxs-lookup"><span data-stu-id="847ca-216">Click either **Uninstall** or **Repair**.</span></span>

2.  <span data-ttu-id="847ca-217">Ejecute el paquete spPowerPivot.msi y seleccione la opción **Quitar** o la opción **Reparar** .</span><span class="sxs-lookup"><span data-stu-id="847ca-217">Run the spPowerPivot.msi and select the **Remove** option or the **Repair** option.</span></span>

 <span data-ttu-id="847ca-218">**Línea de comandos** : para reparar o desinstalar PowerPivot para SharePoint 2013 mediante la línea de comandos, abra un símbolo del sistema **con permisos de administrador** y ejecute uno de los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="847ca-218">**Command Line:** To repair or uninstall PowerPivot for SharePoint 2013 using the command line, open a command prompt **with administrator permissions** and run one of the following commands:</span></span>

-   <span data-ttu-id="847ca-219">Para reparar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="847ca-219">To Repair, run the following command:</span></span>

    ```cmd
    msiexec.exe /f spPowerPivot.msi
    ```

 <span data-ttu-id="847ca-220">O</span><span class="sxs-lookup"><span data-stu-id="847ca-220">OR</span></span>

-   <span data-ttu-id="847ca-221">Para desinstalar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="847ca-221">To uninstall, run the following command:</span></span>

    ```cmd
    msiexec.exe /uninstall spPowerPivot.msi
    ```
