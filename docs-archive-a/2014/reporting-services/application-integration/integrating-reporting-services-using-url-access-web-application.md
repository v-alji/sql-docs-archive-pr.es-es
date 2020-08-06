---
title: Usar el acceso URL en una aplicación web | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- links [Reporting Services], URL access
- URL access [Reporting Services], Web applications
- POST requests
- direct addressing [Reporting Services]
- Web applications [Reporting Services]
- hyperlinks [Reporting Services]
ms.assetid: 39e7918c-ad2d-4ca6-b099-2dd4dbdb83dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd31f76658f8160cbb2a576debc335588f77e72c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661817"
---
# <a name="using-url-access-in-a-web-application"></a><span data-ttu-id="6b825-102">Usar acceso URL en una aplicación web</span><span class="sxs-lookup"><span data-stu-id="6b825-102">Using URL Access in a Web Application</span></span>
  <span data-ttu-id="6b825-103">El acceso URL en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está diseñado específicamente para habilitar el acceso a informes individuales a través de una red.</span><span class="sxs-lookup"><span data-stu-id="6b825-103">URL access in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is specifically designed to enable access to individual reports over a network.</span></span> <span data-ttu-id="6b825-104">Este tipo de acceso es mejor para integrar la visualización y navegación por los informes en una aplicación web personalizada.</span><span class="sxs-lookup"><span data-stu-id="6b825-104">This type of access is best for integrating report viewing and navigation into a custom Web application.</span></span> <span data-ttu-id="6b825-105">Para utilizar el acceso URL en las aplicaciones web, puede:</span><span class="sxs-lookup"><span data-stu-id="6b825-105">To use URL access in Web applications, you can:</span></span>  
  
-   <span data-ttu-id="6b825-106">Enviar una dirección URL a un servidor de informes concreto desde un sitio web o portal.</span><span class="sxs-lookup"><span data-stu-id="6b825-106">Address a URL to a specific report server from a Web site or portal.</span></span>  
  
-   <span data-ttu-id="6b825-107">Usar un método POST de formulario y pasar parámetros de cadena de consulta a una dirección URL del servidor de informes utilizando campos de formulario.</span><span class="sxs-lookup"><span data-stu-id="6b825-107">Use a form POST method and pass query string parameters to a report server URL using form fields.</span></span>  
  
## <a name="url-access-through-direct-addressing"></a><span data-ttu-id="6b825-108">Acceso URL a través de direccionamiento directo</span><span class="sxs-lookup"><span data-stu-id="6b825-108">URL Access Through Direct Addressing</span></span>  
 <span data-ttu-id="6b825-109">Para obtener acceso a un servidor de informes o a un elemento de base de datos del servidor de informes usando una dirección URL, basta con proporcionar la dirección URL desde un explorador web o aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b825-109">To access a report server or report server database item using a URL, simply provide the URL address from within a Web browser or application.</span></span> <span data-ttu-id="6b825-110">También puede proporcionar los parámetros a la dirección URL que pueda afectar a la apariencia del informe o recurso al que se tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="6b825-110">You can also supply parameters to the URL that can affect the appearance of the report or resource that is being accessed.</span></span> <span data-ttu-id="6b825-111">Una dirección URL puede destinarse a un servidor de informes a través de la barra de direcciones de un explorador web o puede ser el origen de un **IFrame** que forme parte de un portal o una aplicación web mayor.</span><span class="sxs-lookup"><span data-stu-id="6b825-111">A URL can target a report server through the address bar of a Web browser, or a URL can be the source of an **IFrame** that is part of a larger Web application or portal.</span></span> <span data-ttu-id="6b825-112">Puede incluir hipervínculos a los informes en varias páginas web de un portal, así como destinar un marco concreto para el informe o abrir una ventana nueva del explorador en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6b825-112">You can include hyperlinks to reports on various Web pages of your portal, as well as target a specific frame for the report or open a new browser window in the process.</span></span>  
  
 <span data-ttu-id="6b825-113">En el ejemplo siguiente, el hipervínculo se destina a un marco denominado "main", que podría ser diferente del que incluye el hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="6b825-113">In the following example, the hyperlink targets a frame named "main", which might be different from the one that includes the hyperlink.</span></span> <span data-ttu-id="6b825-114">El hipervínculo podría formar parte del portal web.</span><span class="sxs-lookup"><span data-stu-id="6b825-114">The hyperlink might be part of Web portal.</span></span>  
  
```  
<a href="http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main" target="main" >  
   Click here for the Territory Sales Drilldown sample report  
</a>  
```  
  
 <span data-ttu-id="6b825-115">En el ejemplo anterior, la configuración de la información del dispositivo **LinkTarget** se pasa con el valor "main" en la cadena de consulta de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6b825-115">In the previous example, the device information setting **LinkTarget** is passed with a value of "main" in the query string of the URL.</span></span> <span data-ttu-id="6b825-116">De esta forma se asegura de que cualquier hipervínculo de obtención de detalles del informe también estará destinado al marco denominado "main".</span><span class="sxs-lookup"><span data-stu-id="6b825-116">This ensures that any drillthrough hyperlinks in the report also target the frame named "main".</span></span>  
  
 <span data-ttu-id="6b825-117">Para más información sobre la configuración de la información de dispositivos, vea [Pasar la configuración de información de dispositivo a las extensiones de representación](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="6b825-117">For more information about device information settings, see [Passing Device Information Settings to Rendering Extensions](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="6b825-118">Observe que muchos servidores y exploradores limitan el número de caracteres permitidos en una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6b825-118">Note that many servers and browsers limit the number of characters allowed in a URL.</span></span> <span data-ttu-id="6b825-119">En algunos casos, se impone un límite de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6b825-119">In some cases, a 256-character limit is imposed.</span></span> <span data-ttu-id="6b825-120">Para evitar esta limitación, puede utilizar solicitudes POST que usan un envío de formulario.</span><span class="sxs-lookup"><span data-stu-id="6b825-120">To get around this limitation, you can use POST requests using form submission.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b825-121">Internet Explorer tiene una longitud máxima de 2.083 caracteres para la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6b825-121">Internet Explorer has a maximum URL length of 2,083 characters.</span></span> <span data-ttu-id="6b825-122">Este límite se aplica a las direcciones URL de solicitudes POST y GET.</span><span class="sxs-lookup"><span data-stu-id="6b825-122">This limit applies to both POST and GET request URLs.</span></span> <span data-ttu-id="6b825-123">Sin embargo, el tamaño de la dirección URL no limita a POST para enviar pares de nombre y valor como parte de un formulario, porque se transfieren en el encabezado y no en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6b825-123">POST, however, is not limited by the size of the URL for submitting name/value pairs as part of a form, because they are transferred in the header and not the URL.</span></span>  
  
## <a name="url-access-through-a-form-post-method"></a><span data-ttu-id="6b825-124">Acceso URL a través de un método POST de formulario</span><span class="sxs-lookup"><span data-stu-id="6b825-124">URL Access Through a Form POST Method</span></span>  
 <span data-ttu-id="6b825-125">Cuando un usuario solicita los datos de un servidor de informes utilizando el acceso URL, la solicitud HTTP utiliza el método GET.</span><span class="sxs-lookup"><span data-stu-id="6b825-125">When a user requests data from a report server using URL access, the HTTP request uses the GET method.</span></span> <span data-ttu-id="6b825-126">Esto es equivalente al envío de un formulario donde METHOD = "GET".</span><span class="sxs-lookup"><span data-stu-id="6b825-126">This is equivalent to a form submission where METHOD="GET".</span></span> <span data-ttu-id="6b825-127">Las solicitudes URL o los envíos de formularios que utilizan METHOD="GET" están limitadas por el número máximo de caracteres que un servidor o un explorador web pueden procesar.</span><span class="sxs-lookup"><span data-stu-id="6b825-127">URL requests or form submissions that use METHOD="GET" are limited by the maximum number of characters that a server or Web browser can process.</span></span>  
  
 <span data-ttu-id="6b825-128">Con las solicitudes POST (METHOD="POST" y campos de entrada), los pares de nombre y valor se transfieren en el encabezado y no en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6b825-128">With POST requests (METHOD="POST" and input fields), the name/value pairs are transferred in the header and not the URL.</span></span> <span data-ttu-id="6b825-129">Por consiguiente, los pares de nombre y valor de la cadena de consulta no forman parte de la dirección URL, con lo que puede proporcionar listas de parámetros más largas y complejas.</span><span class="sxs-lookup"><span data-stu-id="6b825-129">Therefore, the name/value pairs of the query string are not part of the URL, thus enabling you to provide much longer and more complex parameter lists.</span></span>  
  
 <span data-ttu-id="6b825-130">Con el acceso directo, un usuario puede ver la dirección URL del servidor de informes y quizá pueda modificar la cadena de consulta o anotar la solicitud de dirección URL determinada y los parámetros del servidor de informes para usarlos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="6b825-130">Using direct access, a user can see the URL for the report server, and may be able to modify the  query string or note the particular URL request and report server parameters for later use.</span></span>  
  
 <span data-ttu-id="6b825-131">El siguiente ejemplo HTML demuestra el uso de un formulario que puede utilizar para llegar a un servidor de informes con una dirección URL concreta y pasar parámetros de cadena de la consulta como parte de los campos de entrada del formulario.</span><span class="sxs-lookup"><span data-stu-id="6b825-131">The following sample HTML demonstrates the use of a form that you can use to target a report server with a specific URL and pass query string parameters as part of the form's input fields.</span></span>  
  
```  
<FORM id="frmRender" action="http://server/reportserver?/SampleReports/  
   Territory Sales Drilldown" method="post" target="_self">  
   <INPUT type="hidden" name="rs:Command" value="Render">   
   <INPUT type="hidden" name="rc:LinkTarget" value="main">  
   <INPUT type="hidden" name="rs:Format" value="HTML4.0">  
   <INPUT type="submit" value="Button">  
</FORM>  
```  
  
 <span data-ttu-id="6b825-132">En el ejemplo anterior, si un usuario hace clic en el botón en el formulario, el servidor de informes devuelve el informe objetivo representado por HTML en el marco actual.</span><span class="sxs-lookup"><span data-stu-id="6b825-132">In the previous example, if a user clicks the button on the form, the report server returns an HTML-rendered report targeted at the current frame.</span></span> <span data-ttu-id="6b825-133">Una cadena de acceso URL comparable podría ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b825-133">A comparable URL access string might look like the following:</span></span>  
  
```  
http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main&rs:Format=HTML4.0  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b825-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b825-134">See Also</span></span>  
 <span data-ttu-id="6b825-135">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="6b825-135">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="6b825-136">[Integración de Reporting Services mediante el acceso URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="6b825-136">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="6b825-137">[Usar el acceso URL en una aplicación para Windows](integrating-reporting-services-using-url-access-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="6b825-137">[Using URL Access in a Windows Application](integrating-reporting-services-using-url-access-windows-application.md) </span></span>  
 [<span data-ttu-id="6b825-138">Acceso URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6b825-138">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
