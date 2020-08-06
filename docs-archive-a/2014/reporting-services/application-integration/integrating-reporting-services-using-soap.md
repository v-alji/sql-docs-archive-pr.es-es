---
title: Integrar Reporting Services con SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, application integration
- SOAP [Reporting Services]
- SOAP [Reporting Services], about report integration
- integrating reports [Reporting Services]
- Web service [Reporting Services], application integration
ms.assetid: 6bc17af5-883c-4bfa-87d9-48cd7056d145
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7b6fffd65b22900d7c505c4b50ec290b95fe9ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662675"
---
# <a name="integrating-reporting-services-using-soap"></a><span data-ttu-id="ff92b-102">Integrar Reporting Services con SOAP</span><span class="sxs-lookup"><span data-stu-id="ff92b-102">Integrating Reporting Services Using SOAP</span></span>
  <span data-ttu-id="ff92b-103">La [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API de SOAP proporciona varios puntos de conexión de servicio web para desarrollar soluciones de informes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ff92b-103">The [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API provides several Web service endpoints for developing custom reporting solutions.</span></span> <span data-ttu-id="ff92b-104">Actualmente, los extremos pertenecen a dos categorías: administración y ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff92b-104">The endpoints currently fall into two categories: management and execution.</span></span> <span data-ttu-id="ff92b-105">La funcionalidad de administración se expone a través de los extremos <xref:ReportService2005>, <xref:ReportService2006> y <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="ff92b-105">The management functionality is exposed through the <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010> endpoints.</span></span> <span data-ttu-id="ff92b-106">El extremo <xref:ReportService2005> se utiliza para administrar un servidor de informes que se configura en modo nativo y el extremo <xref:ReportService2006> se utiliza para administrar un servidor de informes que se configura para el modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff92b-106">The <xref:ReportService2005> endpoint is used for managing a report server that is configured in native mode and the <xref:ReportService2006> endpoint is used for managing a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="ff92b-107"><xref:ReportService2010> combina las funcionalidades de <xref:ReportService2005> y <xref:ReportService2006>, y puede administrar o un servidor de informes que esté configurado para el modo nativo o integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff92b-107">The <xref:ReportService2010> merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage a report server that is configured for either native or SharePoint integrated mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff92b-108">Los tipos de datos <xref:ReportService2005> y <xref:ReportService2006> están desusados en [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff92b-108">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="ff92b-109">El extremo <xref:ReportService2010> incluye las funcionalidades de ambos extremos y contiene características de administración adicionales.</span><span class="sxs-lookup"><span data-stu-id="ff92b-109">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="ff92b-110">La funcionalidad de ejecución se expone a través del extremo <xref:ReportExecution2005> y se utiliza cuando el servidor de informes se configura en modo integrado de SharePoint o nativo.</span><span class="sxs-lookup"><span data-stu-id="ff92b-110">The execution functionality is exposed through the <xref:ReportExecution2005> endpoint and it is used when the report server is configured in native or SharePoint integrated mode.</span></span> <span data-ttu-id="ff92b-111">En los siguientes temas se muestra cómo pueden utilizarse estos extremos para desarrollar soluciones de informes en las aplicaciones web, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff92b-111">The following topics show how these endpoints can be used for developing reporting solutions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint, and Web applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff92b-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff92b-112">In This Section</span></span>  
 [<span data-ttu-id="ff92b-113">Usar la API SOAP en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="ff92b-113">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
 <span data-ttu-id="ff92b-114">Describe cómo usar la API SOAP para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un entorno de Windows.</span><span class="sxs-lookup"><span data-stu-id="ff92b-114">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Windows environment.</span></span>  
  
 [<span data-ttu-id="ff92b-115">Usar la API SOAP en una aplicación web</span><span class="sxs-lookup"><span data-stu-id="ff92b-115">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
 <span data-ttu-id="ff92b-116">Describe cómo utilizar la API SOAP para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un entorno web.</span><span class="sxs-lookup"><span data-stu-id="ff92b-116">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff92b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff92b-117">See Also</span></span>  
 <span data-ttu-id="ff92b-118">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ff92b-118">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="ff92b-119">[Servicio web del servidor de informes](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="ff92b-119">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 [<span data-ttu-id="ff92b-120">Creación de aplicaciones con el servicio web y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ff92b-120">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
