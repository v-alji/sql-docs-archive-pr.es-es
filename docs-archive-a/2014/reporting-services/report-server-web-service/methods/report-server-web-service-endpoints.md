---
title: Puntos de conexión de servicios web del servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70281c5171eb37d9888d663542a7850820c81bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746732"
---
# <a name="report-server-web-service-endpoints"></a><span data-ttu-id="120d3-102">Extremos de servicios web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="120d3-102">Report Server Web Service Endpoints</span></span>
  <span data-ttu-id="120d3-103">El servicio web del servidor de informes proporciona varios extremos para administrar un servidor de informes además de ejecutar los informes y navegar por ellos.</span><span class="sxs-lookup"><span data-stu-id="120d3-103">The Report Server Web service provides several endpoints for managing a report server as well as executing and navigating reports.</span></span>  
  
## <a name="the-management-endpoints"></a><span data-ttu-id="120d3-104">Extremos de administración</span><span class="sxs-lookup"><span data-stu-id="120d3-104">The Management Endpoints</span></span>  
 <span data-ttu-id="120d3-105">Hay tres extremos disponibles para administrar objetos en un servidor de informes: <xref:ReportService2005>, <xref:ReportService2006> y <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="120d3-105">There are three endpoints available for managing objects on a report server, <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010>.</span></span> <span data-ttu-id="120d3-106">El extremo <xref:ReportService2005> se utiliza para administrar los objetos en un servidor de informes que esté configurado para el modo nativo.</span><span class="sxs-lookup"><span data-stu-id="120d3-106">The <xref:ReportService2005> endpoint is used for managing objects on a report server that is configured for native mode.</span></span> <span data-ttu-id="120d3-107">El extremo <xref:ReportService2006> se utiliza para administrar los objetos en un servidor de informes que esté configurado para el modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-107">The <xref:ReportService2006> endpoint is used for managing objects on a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="120d3-108">El punto de conexión <xref:ReportService2010> combina las funcionalidades de <xref:ReportService2005> y <xref:ReportService2006>, y puede administrar los objetos en un servidor de informes que esté configurado para el modo nativo o para el modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-108">The <xref:ReportService2010> endpoint merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage objects on a report server that are configured for either native or SharePoint integrated mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="120d3-109">Cuando un servidor de informes se configura para el modo integrado de SharePoint, las API <xref:ReportService2005> devuelven un error `rsOperationNotSupportedSharePointMode`.</span><span class="sxs-lookup"><span data-stu-id="120d3-109">When a report server is configured for SharePoint integrated mode, the <xref:ReportService2005> APIs will return an `rsOperationNotSupportedSharePointMode` error.</span></span> <span data-ttu-id="120d3-110">Si el servidor de informes se configura para el modo nativo, las API de <xref:ReportService2006> devolverán un error `rsOperationNotSupportedNativeMode`.</span><span class="sxs-lookup"><span data-stu-id="120d3-110">If the report server is configured for native mode, the <xref:ReportService2006> APIs will return an `rsOperationNotSupportedNativeMode` error.</span></span> <span data-ttu-id="120d3-111">De igual forma, cuando las API específicas del modo en <xref:ReportService2010> se utilizan en modos imprevistos, las API devolverán los errores respectivos.</span><span class="sxs-lookup"><span data-stu-id="120d3-111">Similarly, when mode-specific APIs in <xref:ReportService2010> are used on unintended modes, the APIs will return the respective errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="120d3-112">Los tipos de datos <xref:ReportService2005> y <xref:ReportService2006> están desusados en [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120d3-112">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="120d3-113">El extremo <xref:ReportService2010> incluye las funcionalidades de ambos extremos y contiene características de administración adicionales.</span><span class="sxs-lookup"><span data-stu-id="120d3-113">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="120d3-114">Si el servidor de informes está configurado para el modo nativo o para el modo integrado de SharePoint, se puede tener acceso al WSDL para el extremo de administración utilizando una de las direcciones URL siguientes:</span><span class="sxs-lookup"><span data-stu-id="120d3-114">If the report server is configured for native mode or SharePoint integrate mode, the WSDL for the management endpoint can be accessed using one of the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="120d3-115">Para más información, vea [Acceso a la API de SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="120d3-115">For more information, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="the-execution-endpoint"></a><span data-ttu-id="120d3-116">Extremo de ejecución</span><span class="sxs-lookup"><span data-stu-id="120d3-116">The Execution Endpoint</span></span>  
 <span data-ttu-id="120d3-117">El extremo <xref:ReportExecution2005> facilita a los programadores la personalización del procesamiento y la representación de los informes desde un servidor de informes tanto en modo nativo como en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-117">The <xref:ReportExecution2005> endpoint makes it easy for developers to customize report processing and rendering from a report server in both native and SharePoint integrated modes.</span></span> <span data-ttu-id="120d3-118">El extremo incluye las clases y métodos que existían en las versiones anteriores del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="120d3-118">The endpoint includes classes and methods that existed in earlier versions of the Report Server Web service.</span></span> <span data-ttu-id="120d3-119">Además, se han agregado muchas clases y métodos nuevos al servicio web del servidor de informes que se exponen a través del extremo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="120d3-119">In addition, many new classes and methods have been added to the Report Server Web service that are exposed through the execution endpoint.</span></span>  
  
 <span data-ttu-id="120d3-120">Se puede tener acceso al WSDL para el extremo de administración utilizando la dirección URL siguiente:</span><span class="sxs-lookup"><span data-stu-id="120d3-120">The WSDL for the management endpoint can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="120d3-121">Si el servidor de informes está configurado para el modo integrado de SharePoint, se puede tener acceso al WSDL utilizando la dirección URL siguiente:</span><span class="sxs-lookup"><span data-stu-id="120d3-121">If the report server is configured for SharePoint integrate mode, the WSDL can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="120d3-122">Para más información, vea [Acceso a la API de SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="120d3-122">For more information, please see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="sharepoint-proxy-endpoints"></a><span data-ttu-id="120d3-123">Extremos proxy de SharePoint</span><span class="sxs-lookup"><span data-stu-id="120d3-123">SharePoint Proxy Endpoints</span></span>  
 <span data-ttu-id="120d3-124">Cuando un servidor de informes se configura para el modo integrado de SharePoint y se ha instalado el Complemento de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], un conjunto de extremos proxy se instala en el servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-124">When a report server is configured for SharePoint integrated mode and the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in has been installed, a set of proxy endpoints are installed on the SharePoint server.</span></span> <span data-ttu-id="120d3-125">Los extremos proxy constituyen la API principal para desarrollar soluciones de informe cuando un servidor de informes se configura en el modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-125">The proxy endpoints are the primary API for developing report solutions when a report server is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="120d3-126">Al desarrollar con los extremos del proxy, el Complemento de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] administra el intercambio de las credenciales entre el servidor de SharePoint y el servidor de informes en el modo de autenticación de cuentas de confianza.</span><span class="sxs-lookup"><span data-stu-id="120d3-126">When developing against the proxy endpoints, the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in manages the exchange of credentials between the SharePoint server and the report server in Trusted account authentication mode.</span></span> <span data-ttu-id="120d3-127">Al desarrollar con los extremos del servidor de informes, la aplicación que realiza la llamada tendrá que administrar el intercambio de credenciales en el modo de autenticación de cuentas de confianza.</span><span class="sxs-lookup"><span data-stu-id="120d3-127">When developing against the report server endpoints, the calling application will have to manage the credential exchange in Trusted account authentication mode.</span></span> <span data-ttu-id="120d3-128">En la tabla siguiente se enumeran los extremos que se instalan con el Complemento de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120d3-128">The following table lists the endpoints that are installed with the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
|<span data-ttu-id="120d3-129">Extremo proxy</span><span class="sxs-lookup"><span data-stu-id="120d3-129">Proxy Endpoint</span></span>|<span data-ttu-id="120d3-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="120d3-130">Description</span></span>|  
|--------------------|-----------------|  
|<xref:ReportService2006>|<span data-ttu-id="120d3-131">Proporciona las API para administrar un servidor de informes que se configura para el modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-131">Provides the APIs for managing a report server that is configured for SharePoint integrate mode.</span></span> <span data-ttu-id="120d3-132">**Nota:**  Este punto de conexión está en desuso en [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="120d3-132">**Note:**  This endpoint is deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span>|  
|<xref:ReportService2010>|<span data-ttu-id="120d3-133">Proporciona las API para administrar un servidor de informes que se configura para el modo nativo o para el modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-133">Provides the APIs for managing a report server that is configured for either native or SharePoint integrated mode.</span></span>|  
|<xref:ReportExecution2005>|<span data-ttu-id="120d3-134">Proporciona las API para ejecutar los informes y navegar por ellos.</span><span class="sxs-lookup"><span data-stu-id="120d3-134">Provides the APIs for running and navigating reports.</span></span>|  
|<xref:ReportServiceAuthentication>|<span data-ttu-id="120d3-135">Proporciona las API para autenticar a los usuarios con un servidor de informes cuando la aplicación web de SharePoint se configura para la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="120d3-135">Provides the APIs for authenticating users against a report server when the SharePoint Web application is configured for Forms Authentication.</span></span>|  
  
 <span data-ttu-id="120d3-136">Las siguientes son direcciones URL de ejemplo para hacer referencia a los extremos proxy en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="120d3-136">The following are example URLs for referencing the proxy endpoints on a SharePoint site.</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a><span data-ttu-id="120d3-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="120d3-137">See Also</span></span>  
 [<span data-ttu-id="120d3-138">Creación de aplicaciones con el servicio web y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="120d3-138">Building Applications Using the Web Service and the .NET Framework</span></span>](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
