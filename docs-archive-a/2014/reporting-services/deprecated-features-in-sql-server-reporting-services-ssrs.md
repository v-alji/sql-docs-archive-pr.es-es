---
title: Características en desuso en SQL Server Reporting Services en SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- deprecated features [Reporting Services]
- HTML OWC rendering extension [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: 3876c01e-f81d-4cce-9104-5106a8c369e6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af858ae94bf5ea3d9f0cfe0b99759442dabd6629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673533"
---
# <a name="deprecated-features-in-sql-server-reporting-services-in-sql-server-2014"></a><span data-ttu-id="00430-102">Características desusadas de SQL Server Reporting Services en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="00430-102">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>
  <span data-ttu-id="00430-103">En este tema se describen las características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] desusadas.</span><span class="sxs-lookup"><span data-stu-id="00430-103">This topic describes the deprecated [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="00430-104">Las características siguen estando disponibles en la versión en que están desusadas; no obstante, las características están programadas para quitarlas en una versión futura de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00430-104">The features are still available in the release in which they are deprecated; however the features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00430-105">Las características en desuso no se deben usar en nuevas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="00430-105">Deprecated features should not be used in new applications.</span></span>  
  
 <span data-ttu-id="00430-106">En este tema:</span><span class="sxs-lookup"><span data-stu-id="00430-106">In this topic:</span></span>  
  
-   [<span data-ttu-id="00430-107">Características desusadas de SQL Server 2014 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="00430-107">SQL Server 2014 Reporting Services Deprecated Features</span></span>](#bkmk_2014)  
  
-   [<span data-ttu-id="00430-108">Características desusadas de SQL Server 2012 SP1 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="00430-108">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>](#bkmk_2012sp1)  
  
-   [<span data-ttu-id="00430-109">Características desusadas de SQL Server 2012 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="00430-109">SQL Server 2012 Reporting Services Deprecated Features</span></span>](#bkmk_2012)  
  
-   [<span data-ttu-id="00430-110">Características desusadas de SQL Server 2008 R2 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="00430-110">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>](#bkmk_kj)  
  
##  <a name="sql-server-2014-reporting-services-deprecated-features"></a><a name="bkmk_2014"></a><span data-ttu-id="00430-111">SQL Server 2014 Reporting Services características desusadas</span><span class="sxs-lookup"><span data-stu-id="00430-111">SQL Server 2014 Reporting Services Deprecated Features</span></span>  
  
### <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="00430-112">Características no admitidas en la siguiente versión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="00430-112">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="00430-113">Las siguientes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] características no se admitirán en la **siguiente** versión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00430-113">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features will not be supported in the **next** version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00430-114">No utilice estas características en nuevos trabajos de desarrollo y modifique lo antes posible las aplicaciones que las utilizan actualmente.</span><span class="sxs-lookup"><span data-stu-id="00430-114">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
#### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="00430-115">Configuración de información de dispositivo de extensión de representación HTML</span><span class="sxs-lookup"><span data-stu-id="00430-115">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="00430-116">La siguiente configuración de información de dispositivo para la extensión de representación de HTML está desusada.</span><span class="sxs-lookup"><span data-stu-id="00430-116">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="00430-117">ActionScript</span><span class="sxs-lookup"><span data-stu-id="00430-117">ActionScript</span></span>  
  
-   <span data-ttu-id="00430-118">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="00430-118">ActiveXControls</span></span>  
  
-   <span data-ttu-id="00430-119">GetImage</span><span class="sxs-lookup"><span data-stu-id="00430-119">GetImage</span></span>  
  
-   <span data-ttu-id="00430-120">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="00430-120">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="00430-121">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="00430-121">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="00430-122">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="00430-122">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="00430-123">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="00430-123">StreamRoot</span></span>  
  
-   <span data-ttu-id="00430-124">UsePx</span><span class="sxs-lookup"><span data-stu-id="00430-124">UsePx</span></span>  
  
-   <span data-ttu-id="00430-125">Zoom</span><span class="sxs-lookup"><span data-stu-id="00430-125">Zoom</span></span>  
  
 <span data-ttu-id="00430-126">Para obtener más información sobre la extensión de representación HTML, vea [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="00430-126">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
#### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="00430-127">Representación de Microsoft Word y Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="00430-127">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="00430-128">Extensiones de representación BIFF8 de[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para el formato de archivo de intercambio binario de [!INCLUDE[msCoName](../includes/msconame-md.md)] Word y [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="00430-128">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="00430-129">incluye extensiones que se representan en el [!INCLUDE[msCoName](../includes/msconame-md.md)] formato XML abierto de Office 2007-2010.</span><span class="sxs-lookup"><span data-stu-id="00430-129">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
#### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="00430-130">Lenguaje RDL 2005 y anterior</span><span class="sxs-lookup"><span data-stu-id="00430-130">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="00430-131">Lenguaje RDL 2005 y anterior está desusado.</span><span class="sxs-lookup"><span data-stu-id="00430-131">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="00430-132">Para obtener más información acerca de RDL, vea [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="00430-132">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="00430-133">Para obtener más información acerca de la actualización de informes, vea [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="00430-133">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
#### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="00430-134">SQL Server 2005 y elementos de informe personalizados anteriores</span><span class="sxs-lookup"><span data-stu-id="00430-134">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="00430-135">Los elementos de informe personalizados (CRI) compilados para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 y versiones anteriores están en desuso.</span><span class="sxs-lookup"><span data-stu-id="00430-135">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="00430-136">Instantáneas de Reporting Services 2005 y anterior</span><span class="sxs-lookup"><span data-stu-id="00430-136">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="00430-137">las instantáneas representadas con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 y versiones anteriores están en desuso.</span><span class="sxs-lookup"><span data-stu-id="00430-137">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="report-models"></a><span data-ttu-id="00430-138">Modelos de informe</span><span class="sxs-lookup"><span data-stu-id="00430-138">Report Models</span></span>  
 <span data-ttu-id="00430-139">Los modelos de informe del lenguaje semántico modelado (SMDL) han quedado desusados.</span><span class="sxs-lookup"><span data-stu-id="00430-139">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="00430-140">Aunque puede seguir usando modelos de informe existentes como orígenes de datos en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] los informes, debe considerar la posibilidad de actualizar los informes para quitar su dependencia de los modelos de informe.</span><span class="sxs-lookup"><span data-stu-id="00430-140">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="00430-141">no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] incluye herramientas para crear o actualizar modelos de informe.</span><span class="sxs-lookup"><span data-stu-id="00430-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="00430-142">Para obtener más información, vea [cambios importantes en SQL Server Reporting Services en SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="00430-142">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
#### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="00430-143">Métodos desusados en el extremo del servicio web</span><span class="sxs-lookup"><span data-stu-id="00430-143">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="00430-144">Las operaciones siguientes han quedado en desuso en el extremo de servicios web de <xref:ReportService2010.ReportingService2010>:</span><span class="sxs-lookup"><span data-stu-id="00430-144">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
#### <a name="sharepoint-web-parts"></a><span data-ttu-id="00430-145">Elementos web de SharePoint</span><span class="sxs-lookup"><span data-stu-id="00430-145">SharePoint Web Parts</span></span>  
 <span data-ttu-id="00430-146">El archivo contenedor de instalación **RSWebParts.cab** y los elementos web de SharePoint que se pueden extraer del archivo .cab, están en desuso.</span><span class="sxs-lookup"><span data-stu-id="00430-146">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="00430-147">Los elementos web en desuso son el Explorador de informes (**SPExplorer.dwp**) y el Visor de informes (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="00430-147">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="00430-148">Para obtener más información sobre los elementos web en desuso, vea [Ver y explorar los informes en modo nativo usando elementos web de SharePoint (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="00430-148">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
### <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="00430-149">Características no admitidas en una versión futura de SQL Server</span><span class="sxs-lookup"><span data-stu-id="00430-149">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="00430-150">Las características del [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] siguientes se admiten en la próxima versión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], pero se quitarán en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="00430-150">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="00430-151">No se ha determinado la versión específica de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00430-151">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
 <span data-ttu-id="00430-152">Ninguna característica de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ha quedado en desuso en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00430-152">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features were deprecated in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="sql-server-2012-sp1-reporting-services-deprecated-features"></a><a name="bkmk_2012sp1"></a><span data-ttu-id="00430-153">SQL Server 2012 SP1 Reporting Services características desusadas</span><span class="sxs-lookup"><span data-stu-id="00430-153">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="00430-154">En esta sección se describen las características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] desusadas en [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00430-154">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span></span> <span data-ttu-id="00430-155">Las características del [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] siguientes se admiten en la próxima versión de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], pero se quitarán en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="00430-155">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="00430-156">No se ha determinado la versión específica de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00430-156">The specific version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] has not been determined.</span></span>  
  
### <a name="sharepoint-web-parts"></a><span data-ttu-id="00430-157">Elementos web de SharePoint</span><span class="sxs-lookup"><span data-stu-id="00430-157">SharePoint Web Parts</span></span>  
 <span data-ttu-id="00430-158">El archivo contenedor de instalación **RSWebParts.cab** y los elementos web de SharePoint que se pueden extraer del archivo .cab, están en desuso.</span><span class="sxs-lookup"><span data-stu-id="00430-158">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="00430-159">Los elementos web en desuso son el Explorador de informes (**SPExplorer.dwp**) y el Visor de informes (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="00430-159">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="00430-160">Para obtener más información sobre los elementos web en desuso, vea [Ver y explorar los informes en modo nativo usando elementos web de SharePoint (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="00430-160">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
##  <a name="sql-server-2012-reporting-services-deprecated-features"></a><a name="bkmk_2012"></a><span data-ttu-id="00430-161">SQL Server 2012 Reporting Services características desusadas</span><span class="sxs-lookup"><span data-stu-id="00430-161">SQL Server 2012 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="00430-162">En esta sección se describen las características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] desusadas en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00430-162">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="00430-163">Configuración de información de dispositivo de extensión de representación HTML</span><span class="sxs-lookup"><span data-stu-id="00430-163">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="00430-164">La siguiente configuración de información de dispositivo para la extensión de representación de HTML está desusada.</span><span class="sxs-lookup"><span data-stu-id="00430-164">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="00430-165">ActionScript</span><span class="sxs-lookup"><span data-stu-id="00430-165">ActionScript</span></span>  
  
-   <span data-ttu-id="00430-166">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="00430-166">ActiveXControls</span></span>  
  
-   <span data-ttu-id="00430-167">GetImage</span><span class="sxs-lookup"><span data-stu-id="00430-167">GetImage</span></span>  
  
-   <span data-ttu-id="00430-168">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="00430-168">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="00430-169">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="00430-169">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="00430-170">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="00430-170">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="00430-171">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="00430-171">StreamRoot</span></span>  
  
-   <span data-ttu-id="00430-172">UsePx</span><span class="sxs-lookup"><span data-stu-id="00430-172">UsePx</span></span>  
  
-   <span data-ttu-id="00430-173">Zoom</span><span class="sxs-lookup"><span data-stu-id="00430-173">Zoom</span></span>  
  
 <span data-ttu-id="00430-174">Para obtener más información sobre la extensión de representación HTML, vea [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="00430-174">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="00430-175">Representación de Microsoft Word y Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="00430-175">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="00430-176">Extensiones de representación BIFF8 de[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para el formato de archivo de intercambio binario de [!INCLUDE[msCoName](../includes/msconame-md.md)] Word y [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="00430-176">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="00430-177">incluye extensiones que se representan en el [!INCLUDE[msCoName](../includes/msconame-md.md)] formato XML abierto de Office 2007-2010.</span><span class="sxs-lookup"><span data-stu-id="00430-177">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="00430-178">Lenguaje RDL 2005 y anterior</span><span class="sxs-lookup"><span data-stu-id="00430-178">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="00430-179">Lenguaje RDL 2005 y anterior está desusado.</span><span class="sxs-lookup"><span data-stu-id="00430-179">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="00430-180">Para obtener más información acerca de RDL, vea [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="00430-180">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="00430-181">Para obtener más información acerca de la actualización de informes, vea [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="00430-181">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="00430-182">SQL Server 2005 y elementos de informe personalizados anteriores</span><span class="sxs-lookup"><span data-stu-id="00430-182">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="00430-183">Los elementos de informe personalizados (CRI) compilados para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 y versiones anteriores están en desuso.</span><span class="sxs-lookup"><span data-stu-id="00430-183">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="00430-184">Instantáneas de Reporting Services 2005 y anterior</span><span class="sxs-lookup"><span data-stu-id="00430-184">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="00430-185">las instantáneas representadas con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 y versiones anteriores están en desuso.</span><span class="sxs-lookup"><span data-stu-id="00430-185">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="report-models"></a><span data-ttu-id="00430-186">Modelos de informe</span><span class="sxs-lookup"><span data-stu-id="00430-186">Report Models</span></span>  
 <span data-ttu-id="00430-187">Los modelos de informe del lenguaje semántico modelado (SMDL) han quedado desusados.</span><span class="sxs-lookup"><span data-stu-id="00430-187">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="00430-188">Aunque puede seguir usando modelos de informe existentes como orígenes de datos en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] los informes, debe considerar la posibilidad de actualizar los informes para quitar su dependencia de los modelos de informe.</span><span class="sxs-lookup"><span data-stu-id="00430-188">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="00430-189">no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] incluye herramientas para crear o actualizar modelos de informe.</span><span class="sxs-lookup"><span data-stu-id="00430-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="00430-190">Para obtener más información, vea [cambios importantes en SQL Server Reporting Services en SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="00430-190">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="00430-191">Métodos desusados en el extremo del servicio web</span><span class="sxs-lookup"><span data-stu-id="00430-191">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="00430-192">Las operaciones siguientes han quedado en desuso en el extremo de servicios web de <xref:ReportService2010.ReportingService2010>:</span><span class="sxs-lookup"><span data-stu-id="00430-192">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
##  <a name="sql-server-2008-r2-reporting-services-deprecated-features"></a><a name="bkmk_kj"></a><span data-ttu-id="00430-193">SQL Server 2008 R2 Reporting Services características desusadas</span><span class="sxs-lookup"><span data-stu-id="00430-193">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00430-194">Dado que SQL Server 2008 R2 es una actualización de versión menor de SQL Server 2008, recomendamos también revisar el contenido en la sección de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="00430-194">Because SQL Server 2008 R2 is a minor version upgrade of SQL Server 2008, we recommend that you also review the content in the SQL Server 2008 section.</span></span>  
  
### <a name="report-server-web-service-endpoints"></a><span data-ttu-id="00430-195">Extremos de servicios web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="00430-195">Report Server Web Service Endpoints</span></span>  
 <span data-ttu-id="00430-196">Los servicios web <xref:ReportService2005.ReportingService2005> y <xref:ReportService2006.ReportingService2006> están obsoletos en esta versión.</span><span class="sxs-lookup"><span data-stu-id="00430-196">The Web services <xref:ReportService2005.ReportingService2005> and <xref:ReportService2006.ReportingService2006> have been deprecated in this release.</span></span> <span data-ttu-id="00430-197">Un nuevo extremo ha reemplazado estos extremos: <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="00430-197">These endpoints have been replaced by a new endpoint: <xref:ReportService2010.ReportingService2010>.</span></span>  
  
 <span data-ttu-id="00430-198">El nuevo extremo incluye toda la funcionalidad disponible en los extremos desusados y las nuevas características introducidas en SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="00430-198">The new endpoint includes all the functionality available in the deprecated endpoints and the new features introduced in SQL Server 2008 R2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00430-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00430-199">See Also</span></span>  
 <span data-ttu-id="00430-200">[Novedades &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="00430-200">[What's New &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span></span>  
 <span data-ttu-id="00430-201">[Compatibilidad con versiones anteriores](../getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="00430-201">[Backward Compatibility](../getting-started/backward-compatibility.md) </span></span>  
 <span data-ttu-id="00430-202">[Cambios de comportamiento en SQL Server Reporting Services en SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="00430-202">[Behavior Changes to SQL Server Reporting Services  in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span></span>  
 [<span data-ttu-id="00430-203">Funcionalidad de SQL Server Reporting Services descontinuada en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="00430-203">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  
  
  
