---
title: Especificar la configuración de la información del dispositivo en una dirección URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], URLs
- URL access [Reporting Services], device information settings
ms.assetid: cb7f7577-c6a8-4e6f-8e60-5ec0760f29c3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00cd1fdc3b5fbe129ae4d51b220a11bc48b4744c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747427"
---
# <a name="specify-device-information-settings-in-a-url"></a><span data-ttu-id="30e67-102">Especificar la configuración de la información del dispositivo en una dirección URL</span><span class="sxs-lookup"><span data-stu-id="30e67-102">Specify Device Information Settings in a URL</span></span>
  <span data-ttu-id="30e67-103">Los valores de configuración de información de dispositivos son los parámetros que se pasan a una extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="30e67-103">Device information settings are parameters that are passed to a rendering extension.</span></span> <span data-ttu-id="30e67-104">Si utiliza los métodos del servicio web del servidor de informes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para representar un informe, como parámetro de entrada se pasa un elemento XML `DeviceInfo`.</span><span class="sxs-lookup"><span data-stu-id="30e67-104">If you use the methods of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service to render a report, a `DeviceInfo` XML element is passed as an input parameter.</span></span> <span data-ttu-id="30e67-105">Los elementos secundarios del elemento `DeviceInfo` son específicos de la configuración de información de dispositivos de diferentes extensiones de representación.</span><span class="sxs-lookup"><span data-stu-id="30e67-105">Child elements of the `DeviceInfo` element are specific to the device information settings of different rendering extensions.</span></span> <span data-ttu-id="30e67-106">Puede incluir la configuración de información de dispositivos en una dirección URL mediante la cadena de parámetro *rc:tag=value* , donde *tag* es el nombre del elemento de configuración de la información de dispositivos al que se accede.</span><span class="sxs-lookup"><span data-stu-id="30e67-106">You can include device information settings in a URL by using the *rc:tag=value* parameter string, where *tag* is the name of the device information settings element being accessed.</span></span> <span data-ttu-id="30e67-107">Para más información sobre la configuración de la información de dispositivos en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vea [Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="30e67-107">For more information about device information settings in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30e67-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30e67-108">Example</span></span>  
 <span data-ttu-id="30e67-109">En el ejemplo siguiente se establece el formato del informe especificado en JPEG mediante la configuración de información de dispositivos *OutputFormat* de la extensión de representación de la imagen (los saltos de línea se han agregado por legibilidad):</span><span class="sxs-lookup"><span data-stu-id="30e67-109">The following example sets the format of the specified report to JPEG by using the *OutputFormat* device information setting of the image rendering extension (the line breaks have been added for legibility):</span></span>  
  
```  
http://servername/reportserver?/SampleReports  
/Employee Sales Summary&EmployeeID=38&rs:  
Command=Render&rs:Format=IMAGE&rc:OutputFormat=JPEG  
```  
  
## <a name="see-also"></a><span data-ttu-id="30e67-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30e67-110">See Also</span></span>  
 <span data-ttu-id="30e67-111">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30e67-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="30e67-112">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="30e67-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
