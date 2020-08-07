---
title: Introducción al control de excepciones en Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 091b1f40d293515617e369b750a5f18dfe12951b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745668"
---
# <a name="introducing-exception-handling-in-reporting-services"></a><span data-ttu-id="52881-102">Introducción a la administración de excepciones en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="52881-102">Introducing Exception Handling in Reporting Services</span></span>
  <span data-ttu-id="52881-103">Si una aplicación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] envía una solicitud al servicio web del servidor de informes que el servicio no puede procesar, este devuelve una excepción SOAP al cliente.</span><span class="sxs-lookup"><span data-stu-id="52881-103">If your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application sends a request to the Report Server Web service that the service is unable to process, the service returns a SOAP exception to the client.</span></span> <span data-ttu-id="52881-104">La administración de las excepciones iniciadas por el servicio web del servidor de informes constituye una parte importante de las aplicaciones que se desarrollan porque se puede devolver información útil a los usuarios cuando se producen errores.</span><span class="sxs-lookup"><span data-stu-id="52881-104">Handling exceptions thrown by the Report Server Web service is an important part of the applications that you develop because you can return useful information to users when errors occur.</span></span>  
  
 <span data-ttu-id="52881-105">Esta sección contiene información concreta sobre cómo administrar las excepciones, evitar los datos proporcionados por el usuario que no sean válidos y devolver información de errores significativa para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="52881-105">This section contains specific information about handling exceptions, preventing user input that is not valid, and returning meaningful error information to users.</span></span> <span data-ttu-id="52881-106">Para obtener información general sobre el control de excepciones, vea "controlar y producir excepciones" en la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentación del SDK de.</span><span class="sxs-lookup"><span data-stu-id="52881-106">For general information about exception handling, see "Handling and Throwing Exceptions" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52881-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="52881-107">In This Section</span></span>  
  
|<span data-ttu-id="52881-108">Tema</span><span class="sxs-lookup"><span data-stu-id="52881-108">Topic</span></span>|<span data-ttu-id="52881-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="52881-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="52881-110">Administrar las excepciones en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="52881-110">Handling Exceptions in Reporting Services</span></span>](handling-exceptions-in-reporting-services.md)|<span data-ttu-id="52881-111">Proporciona información general sobre las excepciones en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y el rol de SOAP para devolver los errores de un servicio web.</span><span class="sxs-lookup"><span data-stu-id="52881-111">Provides an overview of exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and the role of SOAP in returning errors from a Web service.</span></span>|  
|[<span data-ttu-id="52881-112">Prácticas recomendadas para la administración de excepciones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="52881-112">Best Practices for Reporting Services Exception Handling</span></span>](best-practices/best-practices-for-reporting-services-exception-handling.md)|<span data-ttu-id="52881-113">Proporciona recomendaciones sobre cómo administrar las excepciones en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52881-113">Provides recommendations on how to handle exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="52881-114">Clase SoapException de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="52881-114">Reporting Services SoapException Class</span></span>](soapexception-class/reporting-services-soapexception-class.md)|<span data-ttu-id="52881-115">Describe la clase **SoapException** en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52881-115">Describes the **SoapException** class in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52881-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52881-116">See Also</span></span>  
 [<span data-ttu-id="52881-117">Creación de aplicaciones con el servicio web y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="52881-117">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
