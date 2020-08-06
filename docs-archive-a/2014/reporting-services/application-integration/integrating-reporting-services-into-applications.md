---
title: Integrar Reporting Services en las aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- integrating reports [Reporting Services]
- custom applications [SSRS]
- Reporting Services, application integration
- application integration [Reporting Services]
- reports [Reporting Services], integrating
ms.assetid: 49eb539c-d89b-4291-839a-0ec1a65cd270
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ab92008c5beb4d931e8e781857d766bb56a1efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662681"
---
# <a name="integrating-reporting-services-into-applications"></a><span data-ttu-id="30c63-102">Integrar Reporting Services en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="30c63-102">Integrating Reporting Services into Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="30c63-103">es una plataforma de informe abierta y extensible diseñada para proporcionar un conjunto completo de API a los programadores para desarrollar soluciones.</span><span class="sxs-lookup"><span data-stu-id="30c63-103">is an open and extensible reporting platform designed to provide developers with a comprehensive set of APIs for developing solutions.</span></span>  
  
 <span data-ttu-id="30c63-104">Existen tres opciones para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en aplicaciones personalizadas: el servicio Web del servidor de informes, también conocido como la [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP, los controles ReportViewer para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] y el acceso URL.</span><span class="sxs-lookup"><span data-stu-id="30c63-104">There are three options for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: the Report Server Web service, also known as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API, the ReportViewer controls for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], and URL access.</span></span> <span data-ttu-id="30c63-105">Cada opción proporciona un enfoque diferente para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="30c63-105">Each option provides a different approach for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span>  
  
## <a name="report-server-web-service"></a><span data-ttu-id="30c63-106">servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="30c63-106">Report Server Web Service</span></span>  
 <span data-ttu-id="30c63-107">El servicio web del servidor de informes es la interfaz principal para el desarrollo de soluciones con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30c63-107">The Report Server Web service is the primary interface for developing against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="30c63-108">Si está desarrollando código para administrar un catálogo de informe o representar informes en un formato admitido, el servicio web expone todos los métodos necesarios para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="30c63-108">Whether you are developing code to manage your report catalog or developing code to render reports to a supported format, the Web service exposes all the necessary methods to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span> <span data-ttu-id="30c63-109">Un ejemplo de tal aplicación es el Administrador de informes, que se incluye con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; usa el servicio web para administrar la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="30c63-109">An example of one such application is Report Manager, which is included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; it uses the Web service to manage the report server database.</span></span>  
  
## <a name="reportviewer-controls-for-visual-studio"></a><span data-ttu-id="30c63-110">Controles ReportViewer para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30c63-110">ReportViewer Controls for Visual Studio</span></span>  
 <span data-ttu-id="30c63-111">Los controles ReportViewer incluidos con [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] se utilizan para integrar la vista del informe en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="30c63-111">The ReportViewer controls included with [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] are used for integrating report viewing into your applications.</span></span> <span data-ttu-id="30c63-112">Hay dos controles: uno para las aplicaciones basadas en formularios Windows Forms y otro para las aplicaciones de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="30c63-112">There are two controls: one for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="30c63-113">Cada control permite ver los informes implementados en un servidor de informes así como la capacidad de representar los informes que existen en un entorno donde no se haya instalado un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="30c63-113">Each control provides the capability for viewing reports that have been deployed to a report server as well as the ability to render reports that exist in an environment where a report server has not been installed.</span></span>  
  
## <a name="url-access"></a><span data-ttu-id="30c63-114">Acceso URL</span><span class="sxs-lookup"><span data-stu-id="30c63-114">URL Access</span></span>  
 <span data-ttu-id="30c63-115">El acceso URL es otra opción para integrar la vista del informe en las aplicaciones si los controles ReportViewer no son factibles.</span><span class="sxs-lookup"><span data-stu-id="30c63-115">URL access is another option for integrating report viewing into your applications if the ReportViewer controls are not an option.</span></span> <span data-ttu-id="30c63-116">Además, el acceso URL es útil para enviar vínculos a informes a los usuarios a través de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="30c63-116">In addition, URL access is useful for sending links to reports to users via e-mail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30c63-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="30c63-117">In This Section</span></span>  
 [<span data-ttu-id="30c63-118">Integración de Reporting Services mediante SOAP</span><span class="sxs-lookup"><span data-stu-id="30c63-118">Integrating Reporting Services Using SOAP</span></span>](../application-integration/integrating-reporting-services-using-soap.md)  
 <span data-ttu-id="30c63-119">Describe cómo integrar la navegación en informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y la administración en las aplicaciones empresariales existentes utilizando el servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="30c63-119">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management into your existing business applications using the Report Server Web service.</span></span>  
  
 [<span data-ttu-id="30c63-120">Integrar Reporting Services con los controles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="30c63-120">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
 <span data-ttu-id="30c63-121">Describe cómo integrar la vista del informe en las aplicaciones existentes utilizando controles ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="30c63-121">Describes how to integrate report viewing into your existing applications using the ReportViewer controls.</span></span>  
  
 [<span data-ttu-id="30c63-122">Integración de Reporting Services mediante el acceso URL</span><span class="sxs-lookup"><span data-stu-id="30c63-122">Integrating Reporting Services Using URL Access</span></span>](../application-integration/integrating-reporting-services-using-url-access.md)  
 <span data-ttu-id="30c63-123">Describe cómo integrar la navegación en informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en las aplicaciones empresariales existentes utilizando el acceso URL.</span><span class="sxs-lookup"><span data-stu-id="30c63-123">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation into your existing business applications using URL access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c63-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30c63-124">See Also</span></span>  
 <span data-ttu-id="30c63-125">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="30c63-125">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="30c63-126">[Elegir entre acceso URL y SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span><span class="sxs-lookup"><span data-stu-id="30c63-126">[Choosing Between URL Access and SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span></span>  
 <span data-ttu-id="30c63-127">[Referencia técnica &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30c63-127">[Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="30c63-128">Servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="30c63-128">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
