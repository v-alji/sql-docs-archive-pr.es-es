---
title: Pasar la configuración de información de dispositivo a las extensiones de representación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- device information settings [Reporting Services]
- Render method
- Report Server Web service, device information settings
- Web service [Reporting Services], device information settings
- XML Web service [Reporting Services], device information settings
- passing device information [Reporting Services]
- rendering extensions [Reporting Services], device information settings
- rendering [Reporting Services], settings
- device information settings [Reporting Services], about device information settings
- extensions [Reporting Services], device information settings
ms.assetid: fe718939-7efe-4c7f-87cb-5f5b09caeff4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea50de3955ab152cbd92d5fd50ef8b2281a67eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745023"
---
# <a name="passing-device-information-settings-to-rendering-extensions"></a><span data-ttu-id="69399-102">Pasar la configuración de información de dispositivo a las extensiones de representación</span><span class="sxs-lookup"><span data-stu-id="69399-102">Passing Device Information Settings to Rendering Extensions</span></span>
  <span data-ttu-id="69399-103">En [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], la configuración de información de dispositivos se utiliza para pasar los parámetros de representación a una extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="69399-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="69399-104">La configuración en el servicio web del servidor de informes se pasa como un elemento XML **DeviceInfo** y es procesada por el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="69399-104">Settings in the Report Server Web service are passed as a **DeviceInfo** XML element and processed by the report server.</span></span> <span data-ttu-id="69399-105">Dado que la configuración de información de dispositivos tiene valores predeterminados, se consideran como argumentos opcionales en el proceso de representación.</span><span class="sxs-lookup"><span data-stu-id="69399-105">Because device information settings have default values, they are considered optional arguments in the rendering process.</span></span> <span data-ttu-id="69399-106">Sin embargo, puede utilizar la configuración de información de dispositivos para personalizar la representación y anular los valores predeterminados proporcionados por el servidor.</span><span class="sxs-lookup"><span data-stu-id="69399-106">However, you can use device information settings to customize rendering and to override the default values that are supplied by the server.</span></span>  
  
 <span data-ttu-id="69399-107">Puede especificar la configuración de información de dispositivos de distintas maneras.</span><span class="sxs-lookup"><span data-stu-id="69399-107">You can specify device information settings in a variety of ways.</span></span> <span data-ttu-id="69399-108">Mediante programación, puede utilizar el método Render.</span><span class="sxs-lookup"><span data-stu-id="69399-108">Programmatically, you can use the Render method.</span></span> <span data-ttu-id="69399-109">Si está teniendo acceso a un informe a través de su URL, puede especificar la información del dispositivo como parámetros URL.</span><span class="sxs-lookup"><span data-stu-id="69399-109">If you are accessing a report through its URL, you can specify device information as URL parameters.</span></span> <span data-ttu-id="69399-110">También puede modificar la configuración de información de dispositivos en los archivos de configuración de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para especificar globalmente los parámetros de representación.</span><span class="sxs-lookup"><span data-stu-id="69399-110">You can also edit the device information settings in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files to specify rendering parameters globally.</span></span> <span data-ttu-id="69399-111">Para más información sobre cómo especificar parámetros de representación globalmente, vea [Personalizar los parámetros de extensión de representación en RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="69399-111">For more information about specifying rendering parameters globally, see [Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span></span>  
  
## <a name="passing-device-information-using-the-render-method"></a><span data-ttu-id="69399-112">Pasar información del dispositivo utilizando el método Render</span><span class="sxs-lookup"><span data-stu-id="69399-112">Passing Device Information Using the Render Method</span></span>  
 <span data-ttu-id="69399-113">Para pasar la configuración de información de dispositivos a una extensión de representación, utilice el método <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="69399-113">To pass device information settings to a rendering extension, use the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="69399-114">Por ejemplo, la cadena XML siguiente se puede pasar al método <xref:ReportExecution2005.ReportExecutionService.Render%2A> para crear un fragmento HTML al representar en HTML.</span><span class="sxs-lookup"><span data-stu-id="69399-114">For example, the following XML string can be passed to the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method to create an HTML fragment when rendering to HTML.</span></span>  
  
```  
<DeviceInfo>  
   <HTMLFragment>True</HTMLFragment>  
</DeviceInfo>  
```  
  
 <span data-ttu-id="69399-115">Cuando un informe se representa como un fragmento HTML, el contenido del informe se incluye dentro de un elemento TABLE sin el uso del elemento BODY o HTML.</span><span class="sxs-lookup"><span data-stu-id="69399-115">When a report is rendered as an HTML fragment, the content of the report is contained within a TABLE element without the use of an HTML or BODY element.</span></span> <span data-ttu-id="69399-116">Puede utilizar el fragmento HTML para incorporar el informe en un documento HTML existente.</span><span class="sxs-lookup"><span data-stu-id="69399-116">You can use the HTML fragment to incorporate the report into an existing HTML document.</span></span> <span data-ttu-id="69399-117">Para más información sobre la configuración de la información del dispositivo para la salida HTML, vea [Configuración de la información del dispositivo HTML](../../html-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="69399-117">For more information about device information settings for HTML output, see [HTML Device Information Settings](../../html-device-information-settings.md).</span></span>  
  
## <a name="passing-device-information-using-url-access"></a><span data-ttu-id="69399-118">Pasar información del dispositivo mediante acceso URL</span><span class="sxs-lookup"><span data-stu-id="69399-118">Passing Device Information Using URL Access</span></span>  
 <span data-ttu-id="69399-119">También puede pasar la configuración de información de dispositivos a través del acceso URL.</span><span class="sxs-lookup"><span data-stu-id="69399-119">You can also pass device information settings through URL access.</span></span> <span data-ttu-id="69399-120">La configuración de información de dispositivos se pasa como parámetros URL.</span><span class="sxs-lookup"><span data-stu-id="69399-120">Device information settings are passed as URL parameters.</span></span> <span data-ttu-id="69399-121">La cadena de acceso URL siguiente se puede pasar al servidor de informes para generar un informe representado sin la barra de herramientas del Visor HTML.</span><span class="sxs-lookup"><span data-stu-id="69399-121">The following URL access string can be passed to the report server to generate a rendered report without the HTML viewer toolbar.</span></span>  
  
```  
http://<Server Name>/reportserver?/SampleReports/Sales Order Detail&rs:Command=Render&rs:Format=HTML4.0&rc:Toolbar=False  
```  
  
 <span data-ttu-id="69399-122">Para más información, vea [Especificar la configuración de la información del dispositivo en una dirección URL](../../specify-device-information-settings-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="69399-122">For more information, see [Specify Device Information Settings in a URL](../../specify-device-information-settings-in-a-url.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69399-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69399-123">See Also</span></span>  
 <span data-ttu-id="69399-124">[Configuración de la información de dispositivos para las extensiones de representación &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="69399-124">[Device Information Settings for Rendering Extensions &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span></span>  
 <span data-ttu-id="69399-125">[Personalizar los parámetros de extensión de representación en RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="69399-125">[Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="69399-126">Creación de aplicaciones con el servicio web y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69399-126">Building Applications Using the Web Service and the .NET Framework</span></span>](building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
