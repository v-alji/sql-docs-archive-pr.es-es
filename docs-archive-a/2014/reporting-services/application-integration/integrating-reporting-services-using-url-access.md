---
title: Integrar Reporting Services utilizando un acceso URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- URL access [Reporting Services], about URL access
- integrating reports [Reporting Services]
ms.assetid: f1014f7d-fafa-4aa8-8bd2-5bdba835d9b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fedf4ce3011d9caae9d673acf354265537115057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747520"
---
# <a name="integrating-reporting-services-using-url-access"></a><span data-ttu-id="fb0c4-102">Integrar Reporting Services utilizando un acceso URL</span><span class="sxs-lookup"><span data-stu-id="fb0c4-102">Integrating Reporting Services Using URL Access</span></span>
  <span data-ttu-id="fb0c4-103">Con el acceso URL, el acceso a los informes se realiza a través de una dirección URL del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-103">With URL access, you access reports through a report server URL.</span></span> <span data-ttu-id="fb0c4-104">Una solicitud URL permite tener acceso a un servidor de informes concreto así como a los informes, recursos y otros elementos en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-104">A URL request enables you to access a specific report server as well as the reports, resources, and other items in the report server database.</span></span> <span data-ttu-id="fb0c4-105">También puede personalizar la experiencia de visualización y navegación en los informes para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-105">You can also customize the report viewing and navigation experience for your users.</span></span> <span data-ttu-id="fb0c4-106">La cadena de consulta de la dirección URL contiene la configuración de la información de los dispositivos, así como los parámetros de informe de destino del informe y la salida de representación elegida.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-106">The query string of the URL contains device information settings, as well as report parameters targeted at your report and the chosen rendering output.</span></span> <span data-ttu-id="fb0c4-107">La manera en el servidor de informes administra las solicitudes URL depende de los parámetros, los prefijos de parámetro y el tipo de elemento al que está teniendo acceso a través de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-107">The way the report server handles URL requests depends on the parameters, parameter prefixes, and type of item that you are accessing through the URL.</span></span>  
  
 <span data-ttu-id="fb0c4-108">Puede utilizar el acceso URL para incrustar hipervínculos a los informes y otros elementos del servidor de informes en las aplicaciones que desarrolle, ya sea en un entorno web o de Windows.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-108">You can use URL access to embed hyperlinks to reports and other report server items in the applications that you develop, whether in a Windows or Web environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb0c4-109">Los temas de la sección proporcionan algunas ideas básicas para la integración.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-109">The topics in the section provide you with some basic ideas for integration.</span></span> <span data-ttu-id="fb0c4-110">Puede usar la información para empezar a diseñar y desarrollar sus propios escenarios de integración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb0c4-110">You can use the information to begin to design and develop your own [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integration scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb0c4-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fb0c4-111">In This Section</span></span>  
 [<span data-ttu-id="fb0c4-112">Usar acceso URL en una aplicación web</span><span class="sxs-lookup"><span data-stu-id="fb0c4-112">Using URL Access in a Web Application</span></span>](integrating-reporting-services-using-url-access-web-application.md)  
 <span data-ttu-id="fb0c4-113">Describe cómo usar el acceso URL para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un entorno web.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-113">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
 [<span data-ttu-id="fb0c4-114">Usar el acceso URL en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="fb0c4-114">Using URL Access in a Windows Application</span></span>](integrating-reporting-services-using-url-access-windows-application.md)  
 <span data-ttu-id="fb0c4-115">Describe cómo utilizar el acceso URL para integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un entorno [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="fb0c4-115">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0c4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb0c4-116">See Also</span></span>  
 <span data-ttu-id="fb0c4-117">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fb0c4-117">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="fb0c4-118">Acceso URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fb0c4-118">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
