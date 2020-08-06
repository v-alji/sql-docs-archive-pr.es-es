---
title: Instalación en modo de Reporting Services SharePoint (SharePoint 2010 y SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- default configuration [Reporting Services]
- installing Reporting Services, SharePoint integrated mode
- installation options [Reporting Services]
ms.assetid: ac6cba68-2665-4a39-8fa3-cb7d7e6723c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c27b6f9fbeebcc896b1a6097cb51e8d2e15924bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663301"
---
# <a name="reporting-services-sharepoint-mode-installation-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="e85a4-102">Instalación del modo de SharePoint de Reporting Services (SharePoint 2010 y SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="e85a4-102">Reporting Services SharePoint Mode Installation (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="e85a4-103">en modo de SharePoint es una colección de componentes de servidor que proporcionan generación y entrega de informes basada en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y [!INCLUDE[msCoName](../../includes/msconame-md.md)] productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e85a4-103">in SharePoint mode is a collection of server components that provide report generation and delivery, based on [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint products.</span></span>  
  
 <span data-ttu-id="e85a4-104">La ejecución de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en modo de SharePoint proporciona las características de [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] y de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="e85a4-104">Running [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode provides the [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] and data alerting features.</span></span> <span data-ttu-id="e85a4-105">Para obtener más información sobre las características del modo de SharePoint, vea la sección "diferencias de compatibilidad de características y comportamiento por modo de servidor" en [Reporting Services servidor de informes](../reporting-services-report-server.md) .</span><span class="sxs-lookup"><span data-stu-id="e85a4-105">For more information regarding features in SharePoint mode, see the section "Feature Support and Behavior Differences by Server Mode" in [Reporting Services Report Server](../reporting-services-report-server.md)</span></span>  
  
 <span data-ttu-id="e85a4-106">Hay dos instalaciones fundamentales necesarias para [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en modo de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e85a4-106">There are two fundamental installations needed for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode:</span></span>  
  
|<span data-ttu-id="e85a4-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="e85a4-107">Installation</span></span>|<span data-ttu-id="e85a4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e85a4-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="e85a4-109">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] complemento para productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e85a4-109">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>|<span data-ttu-id="e85a4-110">El complemento instala las características y las páginas de la interfaz de usuario (IU) de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un servidor front-end web de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e85a4-110">The add-in installs the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] user interface (UI) pages and features on a SharePoint web front-end server.</span></span> <span data-ttu-id="e85a4-111">Entre las características de la interfaz de usuario se encuentran [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], páginas de administración en Administración central de SharePoint, páginas de características utilizadas en las bibliotecas de documentos de SharePoint y páginas de alertas de datos de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e85a4-111">The UI features include [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], administration pages in SharePoint Central Administration, feature pages used within SharePoint document libraries, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Data Alerting pages.</span></span>|  
|<span data-ttu-id="e85a4-112">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servidor de informes instalado en modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e85a4-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server installed in SharePoint Mode</span></span>|<span data-ttu-id="e85a4-113">El servidor de informes administra el procesamiento y la representación de datos e informes así como la suscripción y el procesamiento de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="e85a4-113">The report server handles the data and report processing and rendering as well subscription and Data Alert processing.</span></span> <span data-ttu-id="e85a4-114">El servidor de informes en modo de SharePoint se configura e instala como un servicio compartido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e85a4-114">The SharePoint mode report server is architected and installed as a SharePoint Shared Service.</span></span>|  
  
 <span data-ttu-id="e85a4-115">Para instalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], utilice el disco de instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e85a4-115">To install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media.</span></span>  
  
 <span data-ttu-id="e85a4-116">Para obtener instrucciones sobre escenarios de implementación avanzada, consulte lista de comprobación de la [implementación: Reporting Services, Power View y PowerPivot para SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) y lista de comprobación de la [implementación: instalar Reporting Services en una granja de servidores de SharePoint existente](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span><span class="sxs-lookup"><span data-stu-id="e85a4-116">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Install Reporting Services into an Existing SharePoint Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e85a4-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e85a4-117">In This Section</span></span>  
 [<span data-ttu-id="e85a4-118">Combinaciones admitidas de SharePoint y Reporting Services Server y el complemento &#40;SQL Server 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="e85a4-118">Supported Combinations of SharePoint and Reporting Services Server and Add-in &#40;SQL Server 2014&#41;</span></span>](supported-combinations-of-sharepoint-and-reporting-services-server.md)  
  
 [<span data-ttu-id="e85a4-119">Instalar el modo de SharePoint de Reporting Services para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e85a4-119">Install Reporting Services SharePoint Mode for SharePoint 2013</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md)  
  
 [<span data-ttu-id="e85a4-120">Instalar el modo de SharePoint de Reporting Services para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="e85a4-120">Install Reporting Services SharePoint Mode for SharePoint 2010</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="e85a4-121">Instalar o desinstalar el complemento de Reporting Services para SharePoint &#40;SharePoint 2010 y SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="e85a4-121">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
 [<span data-ttu-id="e85a4-122">Dónde encontrar el complemento Reporting Services para Productos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e85a4-122">Where to find the Reporting Services add-in for SharePoint Products</span></span>](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)  
  
 [<span data-ttu-id="e85a4-123">Agregar un servidor de informes adicional a una granja de servidores &#40;escalado horizontal de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e85a4-123">Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;</span></span>](add-an-additional-report-server-to-a-farm-ssrs-scale-out.md)  
  
 [<span data-ttu-id="e85a4-124">Agregar un front-end web adicional de Reporting Services a una granja de servidores</span><span class="sxs-lookup"><span data-stu-id="e85a4-124">Add an Additional Reporting Services Web Front-end to a Farm</span></span>](add-an-additional-reporting-services-web-front-end-to-a-farm.md)  
  
 [<span data-ttu-id="e85a4-125">Configurar el correo electrónico para una aplicación de servicio de Reporting Services &#40;SharePoint 2010 y SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="e85a4-125">Configure E-mail for a Reporting Services Service Application &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](configure-e-mail-for-a-reporting-services-service-application.md)  
  
 [<span data-ttu-id="e85a4-126">Aprovisionar Subscripciones y alertas para aplicaciones de servicio SSRS</span><span class="sxs-lookup"><span data-stu-id="e85a4-126">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>](provision-subscriptions-and-alerts-for-ssrs-service-applications.md)  
  
 [<span data-ttu-id="e85a4-127">Notificaciones del servicio de token de Windows &#40;C2WTS&#41; y Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e85a4-127">Claims to Windows Token Service &#40;C2WTS&#41; and Reporting Services</span></span>](../../sql-server/install/claims-to-windows-token-service-c2wts-and-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="e85a4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e85a4-128">See Also</span></span>  
 <span data-ttu-id="e85a4-129">[Arquitectura y flujo de trabajo de alertas de datos](../reporting-services-data-alerts.md#AlertingWF) </span><span class="sxs-lookup"><span data-stu-id="e85a4-129">[Data Alerts Architecture and Workflow](../reporting-services-data-alerts.md#AlertingWF) </span></span>  
 [<span data-ttu-id="e85a4-130">Administrador de alertas de datos para administradores de alertas</span><span class="sxs-lookup"><span data-stu-id="e85a4-130">Data Alert Manager for Alerting Administrators</span></span>](../data-alert-manager-for-alerting-administrators.md)  
  
  
