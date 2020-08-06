---
title: Acceso a la API de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- XML Web service [Reporting Services], WSDL
- Web service [Reporting Services], SOAP
- calling Web service
- SOAP [Reporting Services], accessing
- Report Server Web service, SOAP
- Web service [Reporting Services], WSDL
- WSDL [Reporting Services]
- XML Web service [Reporting Services], SOAP
- Report Server Web service, WSDL
- referencing WSDL
ms.assetid: 63bb870a-4dbf-46bd-8921-78f8ebe5fd75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e8a0c21bb53deff746cfd916b6ae2c96fa0de19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676328"
---
# <a name="accessing-the-soap-api"></a><span data-ttu-id="5c967-102">Acceso a la API SOAP</span><span class="sxs-lookup"><span data-stu-id="5c967-102">Accessing the SOAP API</span></span>
  <span data-ttu-id="5c967-103">El servicio web del servidor de informes utiliza el Protocolo simple de acceso a objetos (SOAP) sobre HTTP y actúa como interfaz de comunicaciones entre los programas clientes y el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5c967-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="5c967-104">El servicio web proporciona dos extremos, uno para la ejecución y otro para la administración de informes, y está compuesto de métodos y de un conjunto de objetos de tipo complejo que puede utilizar para tener acceso a la funcionalidad completa de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c967-104">The Web service provides two endpoints - one for report execution and one for report management - and consists of methods and a set of complex type objects that you can use to access the complete functionality of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5c967-105">Para llamar al servicio, debe hacer referencia al Lenguaje de descripción de servicios web (WSDL) de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5c967-105">To call the service, you must reference the Reporting Services Web Services Description Language (WSDL).</span></span>  
  
## <a name="referencing-the-reporting-services-wsdl"></a><span data-ttu-id="5c967-106">Referencia a WSDL de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5c967-106">Referencing the Reporting Services WSDL</span></span>  
 <span data-ttu-id="5c967-107">Para llamar correctamente a un servicio web, debe saber cómo tener acceso al mismo, qué operaciones admite, qué parámetros espera y lo que devuelve.</span><span class="sxs-lookup"><span data-stu-id="5c967-107">To call a Web service successfully, you must know how to access the service, what operations the service supports, what parameters the service expects, and what the service returns.</span></span> <span data-ttu-id="5c967-108">WSDL proporciona esta información en un documento XML que un equipo puede leer o procesar.</span><span class="sxs-lookup"><span data-stu-id="5c967-108">WSDL provides this information in an XML document that can be read or processed by a computer.</span></span>  
  
 <span data-ttu-id="5c967-109">Los servicios web del servidor de informes se exponen en tres extremos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5c967-109">The Report Server Web services are exposed in three different endpoints.</span></span> <span data-ttu-id="5c967-110">El nombre del archivo WSDL es diferente para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="5c967-110">The name of the WSDL file is different for each endpoint.</span></span> <span data-ttu-id="5c967-111">El extremo <xref:ReportService2010> contiene métodos para administrar los objetos en un servidor de informes en modo nativo o en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c967-111">The <xref:ReportService2010> endpoint contains methods for managing objects in a Report Server in either native or SharePoint integrated mode.</span></span> <span data-ttu-id="5c967-112">El acceso a WSDL para este extremo se realiza a través de `ReportService2010.asmx?wsdl.`.</span><span class="sxs-lookup"><span data-stu-id="5c967-112">The WSDL for this endpoint is accessed through `ReportService2010.asmx?wsdl.`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c967-113">Los tipos de datos <xref:ReportService2005> y <xref:ReportService2006> están desusados en [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c967-113">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="5c967-114">El extremo <xref:ReportService2010> incluye las funcionalidades de ambos extremos y contiene características de administración adicionales.</span><span class="sxs-lookup"><span data-stu-id="5c967-114">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
-   <span data-ttu-id="5c967-115">El extremo <xref:ReportExecution2005> permite a los desarrolladores procesar y representar mediante programación los informes en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5c967-115">The <xref:ReportExecution2005> endpoint allows developers to programmatically process and render reports in a Report Server.</span></span> <span data-ttu-id="5c967-116">El acceso a WSDL para este punto de conexión se realiza a través de `ReportExecution2005.asmx?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="5c967-116">The WSDL for this endpoint is accessed through `ReportExecution2005.asmx?wsdl`.</span></span>  
  
 <span data-ttu-id="5c967-117">WSDL puede ser utilizado por los kits de desarrollo que admiten SOAP y servicios Web, como el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="5c967-117">WSDL can be consumed by development kits that support SOAP and Web services, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="5c967-118">En el siguiente ejemplo se muestra el formato de la dirección URL del archivo WSDL de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c967-118">The following example shows the format of the URL to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] management WSDL file:</span></span>  
  
```  
http://server/reportserver/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="5c967-119">En la tabla siguiente se describe cada elemento de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5c967-119">The following table describes each element in the URL.</span></span>  
  
|<span data-ttu-id="5c967-120">Elemento de dirección URL</span><span class="sxs-lookup"><span data-stu-id="5c967-120">URL element</span></span>|<span data-ttu-id="5c967-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c967-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5c967-122">*servidor*</span><span class="sxs-lookup"><span data-stu-id="5c967-122">*server*</span></span>|<span data-ttu-id="5c967-123">Nombre del servidor donde se implementa el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5c967-123">The name of the server on which the report server is deployed.</span></span>|  
|<span data-ttu-id="5c967-124">*ReportServer*</span><span class="sxs-lookup"><span data-stu-id="5c967-124">*reportserver*</span></span>|<span data-ttu-id="5c967-125">Nombre de la carpeta que contiene el servicio web XML.</span><span class="sxs-lookup"><span data-stu-id="5c967-125">The name of the folder that contains the XML Web service.</span></span> <span data-ttu-id="5c967-126">Se configura durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="5c967-126">This is configured during setup.</span></span>|  
|<span data-ttu-id="5c967-127">*\<endpoint name>. asmx*</span><span class="sxs-lookup"><span data-stu-id="5c967-127">*\<endpoint name>.asmx*</span></span>|<span data-ttu-id="5c967-128">Nombre del extremo de servicios web.</span><span class="sxs-lookup"><span data-stu-id="5c967-128">The name of the web service endpoint.</span></span>|  
  
 <span data-ttu-id="5c967-129">Para más información acerca del formato de WSDL, consulte la especificación de WSDL del World Wide Web Consortium (W3C) en http://www.w3.org/TR/wsdl.</span><span class="sxs-lookup"><span data-stu-id="5c967-129">For more information about the WSDL format, see the World Wide Web Consortium (W3C) WSDL specification at http://www.w3.org/TR/wsdl.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c967-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c967-130">See Also</span></span>  
 <span data-ttu-id="5c967-131">[Creación de aplicaciones con el servicio web y .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="5c967-131">[Building Applications Using the Web Service and the .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="5c967-132">Servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5c967-132">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
