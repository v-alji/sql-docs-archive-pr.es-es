---
title: Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services]
- SSRS
- reports [Reporting Services], about reports
- Reporting Services
- SQL Server Reporting Services
ms.assetid: b8d18d3d-9db0-43e7-8286-7b46cc3a37ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0418acaab54032148f4bc6d42d06c97070b89e1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744000"
---
# <a name="reporting-services-ssrs"></a><span data-ttu-id="78d29-102">Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="78d29-102">Reporting Services (SSRS)</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="78d29-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]proporciona una gama completa de herramientas y servicios listos para usar que le ayudarán a crear, implementar y administrar informes para su organización.</span><span class="sxs-lookup"><span data-stu-id="78d29-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="78d29-104">incluye características de programación que le permitirán ampliar y personalizar la funcionalidad de informes.</span><span class="sxs-lookup"><span data-stu-id="78d29-104">includes programming features that enable you to extend and customize your reporting functionality.</span></span>

 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="78d29-105">es una plataforma de informes basada en servidor que proporciona una funcionalidad de informes completa para una variedad de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="78d29-105">is a server-based reporting platform that provides comprehensive reporting functionality for a variety of data sources.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="78d29-106">incluye un conjunto completo de herramientas para crear, administrar y proporcionar informes, así como API que permiten a los desarrolladores integrar o ampliar el procesamiento de datos e informes en aplicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="78d29-106">includes a complete set of tools for you to create, manage, and deliver reports, and APIs that enable developers to integrate or extend data and report processing in custom applications.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="78d29-107">las herramientas de funcionan en el [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] entorno de y están totalmente integradas con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] herramientas y componentes de.</span><span class="sxs-lookup"><span data-stu-id="78d29-107">tools work within the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environment and are fully integrated with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tools and components.</span></span>

 <span data-ttu-id="78d29-108">Con [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], puede crear informes interactivos, tabulares, gráficos o de forma libre a partir de orígenes de datos relacionales, multidimensionales o basados en XML.</span><span class="sxs-lookup"><span data-stu-id="78d29-108">With [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], you can create interactive, tabular, graphical, or free-form reports from relational, multidimensional, or XML-based data sources.</span></span> <span data-ttu-id="78d29-109">Los informes pueden incluir visualización de datos avanzada, como diagramas, mapas y minigráficos.</span><span class="sxs-lookup"><span data-stu-id="78d29-109">Reports can include rich data visualization, including charts, maps, and sparklines.</span></span> <span data-ttu-id="78d29-110">Puede publicar informes, programar el procesamiento de los informes o acceder a informes a petición.</span><span class="sxs-lookup"><span data-stu-id="78d29-110">You can publish reports, schedule report processing, or access reports on-demand.</span></span> <span data-ttu-id="78d29-111">Puede elegir entre varios formatos de visualización, exportar informes a otras aplicaciones, como [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], y suscribirse a los informes publicados.</span><span class="sxs-lookup"><span data-stu-id="78d29-111">You can select from a variety of viewing formats, export reports to other applications such as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], and subscribe to published reports.</span></span> <span data-ttu-id="78d29-112">Los informes creados se pueden ver mediante una conexión basada en web o como parte de una aplicación de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows o un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="78d29-112">The reports that you create can be viewed over a Web-based connection or as part of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application or SharePoint site.</span></span> <span data-ttu-id="78d29-113">Puede crear también alertas de datos en los informes publicados en un sitio de SharePoint y recibir mensajes de correo electrónico cuando cambien los datos del informe.</span><span class="sxs-lookup"><span data-stu-id="78d29-113">You can also create data alerts on reports published to a SharePoint site and receive email messages when report data changes.</span></span>

 <span data-ttu-id="78d29-114">Para obtener más información acerca de las características nuevas de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , consulte [novedades &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="78d29-114">For more information about features new in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [What's New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span></span>

 <span data-ttu-id="78d29-115">Para obtener información sobre otros componentes, herramientas y recursos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vea los [Libros en pantalla de SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="78d29-115">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>

 <span data-ttu-id="78d29-116">Icono **Examinar contenido por carpeta de área** ![Folder icon](media/hlp-16folder.gif "Icono de carpeta") [Reporting Services servidor de informes](../../2014/reporting-services/reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-116">**Browse Content by Area** ![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Report Server](../../2014/reporting-services/reporting-services-report-server.md)</span></span>

 <span data-ttu-id="78d29-117">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [Reporting Services informes &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-117">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Reports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span></span>

 <span data-ttu-id="78d29-118">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [datos de informe &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-118">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Data &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span></span>

 <span data-ttu-id="78d29-119">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [parámetros de informe &#40;Generador de informes y diseñador de informes&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-119">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span></span>

 <span data-ttu-id="78d29-120">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [elementos de informe en Diseñador de informes &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-120">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parts in Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span></span>

 <span data-ttu-id="78d29-121">![Folder icon](media/hlp-16folder.gif "Icono de carpeta") [Programas](subscriptions/schedules.md) de iconos de carpeta</span><span class="sxs-lookup"><span data-stu-id="78d29-121">![Folder icon](media/hlp-16folder.gif "Folder icon") [Schedules](subscriptions/schedules.md)</span></span>

 <span data-ttu-id="78d29-122">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [suscripciones y entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-122">![Folder icon](media/hlp-16folder.gif "Folder icon") [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span></span>

 <span data-ttu-id="78d29-123">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [Reporting Services alertas de datos](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-123">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>

 <span data-ttu-id="78d29-124">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span><span class="sxs-lookup"><span data-stu-id="78d29-124">![Folder icon](media/hlp-16folder.gif "Folder icon") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span></span>

 <span data-ttu-id="78d29-125">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [Reporting Services seguridad y protección](security/reporting-services-security-and-protection.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-125">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Security and Protection](security/reporting-services-security-and-protection.md)</span></span>

 <span data-ttu-id="78d29-126">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [acceso URL &#40;SSRS&#41;](url-access-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-126">![Folder icon](media/hlp-16folder.gif "Folder icon") [URL Access &#40;SSRS&#41;](url-access-ssrs.md)</span></span>

 <span data-ttu-id="78d29-127">Extensiones de ![iconos de carpeta](media/hlp-16folder.gif "Icono de carpeta") [&#40;SSRS&#41;](extensions-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-127">![Folder icon](media/hlp-16folder.gif "Folder icon") [Extensions &#40;SSRS&#41;](extensions-ssrs.md)</span></span>

 <span data-ttu-id="78d29-128">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [Reporting Services herramientas](tools/reporting-services-tools.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-128">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Tools](tools/reporting-services-tools.md)</span></span>

 <span data-ttu-id="78d29-129">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [errores y referencia de eventos &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-129">![Folder icon](media/hlp-16folder.gif "Folder icon") [Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span></span>

 <span data-ttu-id="78d29-130">![Icono de carpeta](media/hlp-16folder.gif "Icono de carpeta") [&#40;de referencia de características Reporting Services&#41;](feature-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="78d29-130">![Folder icon](media/hlp-16folder.gif "Folder icon") [Feature Reference &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="78d29-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78d29-131">See Also</span></span>
 [<span data-ttu-id="78d29-132">Centro de recursos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="78d29-132">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?linkID=219676)


