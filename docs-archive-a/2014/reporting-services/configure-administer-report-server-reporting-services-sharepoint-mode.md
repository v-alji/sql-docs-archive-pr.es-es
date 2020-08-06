---
title: Configuración y administración de un servidor de informes (modo Reporting Services SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 846e86d0-fbbb-426c-97f9-f179cd42b390
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ce7c1f524eec4785ddbc25d95c641d070ecbf408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749183"
---
# <a name="configuration-and-administration-of-a-report-server-reporting-services-sharepoint-mode"></a><span data-ttu-id="f6155-102">Configuración y administración de un servidor de informes (modo de SharePoint de Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="f6155-102">Configuration and Administration of a Report Server (Reporting Services SharePoint Mode)</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="f6155-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] es una plataforma de informes basada en servidor que proporciona una gama completa de herramientas y servicios listos para usar que le ayudarán a crear, implementar y administrar informes para su organización, así como características de programación que le permitirán ampliar y personalizar la funcionalidad de los informes.</span><span class="sxs-lookup"><span data-stu-id="f6155-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is a server-based reporting platform that provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization, as well as programming features that enable you to extend and customize your reporting functionality.</span></span> <span data-ttu-id="f6155-104">Puede integrar su entorno de informes con un producto o tecnología de SharePoint para experimentar las ventajas de usar el entorno colaborativo proporcionado por los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f6155-104">You can integrate your reporting environment with a SharePoint product to experience the benefits of using the collaborative environment provided by SharePoint sites.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6155-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f6155-105">In this section</span></span>  
 <span data-ttu-id="f6155-106">Use las siguientes secciones como ayuda para entender los conceptos, los escenarios de implementación, los procedimientos y otras cuestiones para integrar el entorno de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] con un producto o tecnología de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f6155-106">Use the following sections to help you understand concepts, deployment scenarios, procedures, and more for integrating your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] environment with a SharePoint product or technology:</span></span>  
  
-   <span data-ttu-id="f6155-107">Opciones de menú en una biblioteca de documentos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6155-107">Menu options in a SharePoint document library</span></span>  
  
    -   [<span data-ttu-id="f6155-108">Administrador de alertas de datos para los usuarios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6155-108">Data Alert Manager for SharePoint Users</span></span>](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md)  
  
    -   [<span data-ttu-id="f6155-109">Creación y administración de suscripciones para servidores de informes en modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6155-109">Create and Manage Subscriptions for SharePoint Mode Report Servers</span></span>](subscriptions/create-and-manage-subscriptions-for-sharepoint-mode-report-servers.md)  
  
    -   [<span data-ttu-id="f6155-110">Actualizar credenciales en orígenes de datos de informe desde un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6155-110">Update Credentials in Report Data Sources from a SharePoint Site</span></span>](report-data/update-credentials-in-report-data-sources-from-a-sharepoint-site.md)  
  
    -   [<span data-ttu-id="f6155-111">Administrar conjuntos de datos compartidos</span><span class="sxs-lookup"><span data-stu-id="f6155-111">Manage Shared Datasets</span></span>](report-data/manage-shared-datasets.md)  
  
    -   [<span data-ttu-id="f6155-112">Establecer parámetros en un informe publicado &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-112">Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="f6155-113">Establecer opciones de procesamiento &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-113">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="f6155-114">Opciones de actualización de memoria caché &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-114">Cache Refresh Options &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/cache-refresh-options-report-manager.md)  
  
-   [<span data-ttu-id="f6155-115">Características de la colección de sitios Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f6155-115">Reporting Services Site Collection Features</span></span>](../../2014/reporting-services/reporting-services-site-collection-features.md)  
  
-   [<span data-ttu-id="f6155-116">Activar las características de integración del servidor de informes y Power View en SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6155-116">Activate the Report Server and Power View Integration Features in SharePoint</span></span>](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)  
  
-   [<span data-ttu-id="f6155-117">Valores de configuración del sitio de Reporting Services y características del sitio &#40;modo de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-117">Reporting Services Site Settings and Site Features&#40;SharePoint Mode&#41;</span></span>](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)  
  
-   [<span data-ttu-id="f6155-118">Activar la característica de sincronización de archivos del servidor de informes en Administración central de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6155-118">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
-   [<span data-ttu-id="f6155-119">Agregar tipos de contenido del servidor de informes a una biblioteca &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-119">Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
-   [<span data-ttu-id="f6155-120">Informes en modo local frente al modo local en el Visor de informes &#40;Reporting Services en modo de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-120">Local Mode vs. Connected Mode Reports in the Report Viewer &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/local-vs-connected-mode-report-viewer-reporting-services-sharepoint-mode.md)  
  
-   [<span data-ttu-id="f6155-121">Cargar documentos en una biblioteca de SharePoint &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-121">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
-   [<span data-ttu-id="f6155-122">Establecer opciones de procesamiento &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f6155-122">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="f6155-123">Para obtener información general sobre [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vea [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) en los libros en pantalla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6155-123">For more general information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="f6155-124">Para obtener información sobre otros componentes, herramientas y recursos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vea los [Libros en pantalla de SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="f6155-124">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>  
  
  
