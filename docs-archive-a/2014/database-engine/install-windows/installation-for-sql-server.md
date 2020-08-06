---
title: Instalación de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 09/09/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
f1_keywords:
- sql12.portal.Installation.f1
helpviewer_keywords:
- installing SQL Server, initial installation
- installation [SQL Server]
- initial installation [SQL Server]
ms.assetid: edd75f68-dc62-4479-a596-57ce8ad632e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 62630400f276b00de8acfa875244558cdb39e47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744832"
---
# <a name="installation-for-sql-server-2014"></a><span data-ttu-id="94371-102">Instalación de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94371-102">Installation for SQL Server 2014</span></span>
 ## <a name="download-sql-server-2014-express"></a>[<span data-ttu-id="94371-103">Descargar SQL Server 2014 Express</span><span class="sxs-lookup"><span data-stu-id="94371-103">Download SQL Server 2014 Express</span></span>](http://www.hanselman.com/blog/DownloadSQLServerExpress.aspx)
  <span data-ttu-id="94371-104">**Gracias a [Scott Hanselman](http://www.hanselman.com/) por recopilar todos los vínculos de paquete del instalador en un solo lugar.**</span><span class="sxs-lookup"><span data-stu-id="94371-104">**Thank you to [Scott Hanselman](http://www.hanselman.com/) for collecting all of the installer package links in one place!**</span></span>
  
  <span data-ttu-id="94371-105">El Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona un único árbol de características para instalar todos los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="94371-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard provides a single feature tree to install all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]  
  
-   [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]  
  
-   <span data-ttu-id="94371-106">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="94371-106">Management tools</span></span>  
  
-   <span data-ttu-id="94371-107">Componentes de conectividad</span><span class="sxs-lookup"><span data-stu-id="94371-107">Connectivity components</span></span>  
  
 <span data-ttu-id="94371-108">Puede instalar cada componente individualmente o seleccionar una combinación de los componentes enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="94371-108">You can install each component individually or select a combination of the components listed above.</span></span> <span data-ttu-id="94371-109">Para elegir la mejor opción entre las ediciones y los componentes disponibles en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [ediciones y componentes de SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) y [características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="94371-109">To make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) and [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="94371-110">está disponible en las ediciones de 32 bits y de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="94371-110">is available in 32-bit and 64-bit editions.</span></span>
 
 <span data-ttu-id="94371-111">**Pruébelo:**</span><span class="sxs-lookup"><span data-stu-id="94371-111">**Try it out:**</span></span>  
  
-   <span data-ttu-id="94371-112">¿Tiene una cuenta de Azure?</span><span class="sxs-lookup"><span data-stu-id="94371-112">Have an Azure account?</span></span>  <span data-ttu-id="94371-113">Después, vaya **[aquí](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** para poner en marcha una máquina Virtual con SQL Server 2014 Service Pack 1 (SP1) ya instalado.</span><span class="sxs-lookup"><span data-stu-id="94371-113">Then go **[Here](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** to spin up a Virtual Machine with SQL Server 2014 Service Pack 1 (SP1) already installed.</span></span> <span data-ttu-id="94371-114">Para obtener más información sobre SQL Server 2014 (SP1), consulte la información sobre la [versión de SQL Server 2014 Service Pack 1](https://support.microsoft.com/kb/3058865).</span><span class="sxs-lookup"><span data-stu-id="94371-114">For more information on SQL Server 2014 (SP1), see [SQL Server 2014 Service Pack 1 release information](https://support.microsoft.com/kb/3058865).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94371-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="94371-115">In This Section</span></span>  
 <span data-ttu-id="94371-116">Independientemente de si utiliza el Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el símbolo del sistema para instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el programa de instalación incluirá los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="94371-116">Regardless of whether you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or the command prompt to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Setup involves the following steps:</span></span>  
  
 [<span data-ttu-id="94371-117">Planear una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="94371-117">Planning a SQL Server Installation</span></span>](../../sql-server/install/planning-a-sql-server-installation.md)  
 <span data-ttu-id="94371-118">Describe cómo preparar el equipo para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94371-118">Describes how to prepare your computer for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="94371-119">Requisitos de hardware y software</span><span class="sxs-lookup"><span data-stu-id="94371-119">Hardware and software requirements.</span></span>  
  
-   <span data-ttu-id="94371-120">Requisitos del Comprobador de configuración del sistema y problemas de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94371-120">System Configuration Checker requirements and blocking issues.</span></span>  
  
-   <span data-ttu-id="94371-121">Consideraciones relativas a la seguridad</span><span class="sxs-lookup"><span data-stu-id="94371-121">Security considerations.</span></span>  
  
 [<span data-ttu-id="94371-122">Instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94371-122">Install SQL Server 2014</span></span>](install-sql-server.md)  
 <span data-ttu-id="94371-123">Describe las opciones de instalación para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94371-123">Describes installation options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="94371-124">Actualizar a SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94371-124">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
 <span data-ttu-id="94371-125">Describe las opciones para actualizar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94371-125">Describes options for upgrading to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="94371-126">Desinstalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94371-126">Uninstall SQL Server 2014</span></span>](../../sql-server/install/uninstall-sql-server.md)  
 <span data-ttu-id="94371-127">Describe los procedimientos para desinstalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94371-127">Describes procedures to uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span></span>  
  
 [<span data-ttu-id="94371-128">Instalación de clúster de conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="94371-128">SQL Server Failover Cluster Installation</span></span>](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="94371-129">Esta sección de la documentación del programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explica cómo instalar y configurar el clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94371-129">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
 [<span data-ttu-id="94371-130">Instalar las características de SQL Server 2014 BI</span><span class="sxs-lookup"><span data-stu-id="94371-130">Install SQL Server 2014 BI Features</span></span>](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="94371-131">características que son parte de la plataforma Microsoft BI incluyen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]y varias aplicaciones cliente que se usan para crear datos analíticos o para trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="94371-131">features that are part of the Microsoft BI platform include [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and several client applications used for creating or working with analytical data.</span></span> <span data-ttu-id="94371-132">Esta sección de la documentación del programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explica cómo instalar [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94371-132">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="94371-133">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="94371-133">Related Sections</span></span>  
 [<span data-ttu-id="94371-134">Temas de procedimientos de instalación</span><span class="sxs-lookup"><span data-stu-id="94371-134">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
 <span data-ttu-id="94371-135">Proporciona vínculos a temas de procedimientos para instalar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] con el Asistente para la instalación, desde el símbolo del sistema, utilizando los archivos de configuración y usando SysPrep.</span><span class="sxs-lookup"><span data-stu-id="94371-135">Provides links to procedural topics for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from the installation wizard, from the command prompt, by using configuration files, and by using SysPrep.</span></span>  
  
 [<span data-ttu-id="94371-136">Instalar características de SQL Server BI con SharePoint &#40;PowerPivot y Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="94371-136">Install SQL Server BI Features with SharePoint &#40;PowerPivot and Reporting Services&#41;</span></span>](../../sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md)  
 <span data-ttu-id="94371-137">En esta sección se explica cómo instalar las características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un entorno de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94371-137">This section explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features in a SharePoint environment.</span></span> <span data-ttu-id="94371-138">Identifica qué características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están disponibles para una versión y edición concreta de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94371-138">It identifies which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features are available given a specific version and edition of SharePoint.</span></span> <span data-ttu-id="94371-139">También incluye los procedimientos de instalación de PowerPivot para SharePoint y Reporting Services en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94371-139">It also includes installation procedures for PowerPivot for SharePoint and Reporting Services in SharePoint mode.</span></span>  
  
 [<span data-ttu-id="94371-140">Instalación de los ejemplos y las bases de datos de ejemplo de SQL Server</span><span class="sxs-lookup"><span data-stu-id="94371-140">Installing SQL Server Samples and Sample Databases</span></span>](https://sqlserversamples.codeplex.com/)  
 <span data-ttu-id="94371-141">Describe cómo instalar y configurar ejemplos y bases de datos de ejemplo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94371-141">Describes how to install and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples and sample databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94371-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94371-142">See Also</span></span>  
 <span data-ttu-id="94371-143">[Novedades de SQL Server instalación](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="94371-143">[What's New in SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="94371-144">Requisitos de hardware y software para instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94371-144">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
