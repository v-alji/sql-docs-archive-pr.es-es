---
title: Implementar la interfaz IRenderingExtension | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IRenderingExtension interface
- rendering extensions [Reporting Services], IRenderingExtension interface
ms.assetid: 74b2f2b7-6796-42da-ab7d-b05891ad4001
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f57c4aa41ccfed165b69581cbf3917e4dfbb4960
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673525"
---
# <a name="implementing-the-irenderingextension-interface"></a><span data-ttu-id="e1798-102">Implementar la interfaz IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="e1798-102">Implementing the IRenderingExtension Interface</span></span>
  <span data-ttu-id="e1798-103">La extensión de representación toma los resultados de una definición de informe que se combina con los datos reales y representa los datos resultantes en un formato que se puede usar.</span><span class="sxs-lookup"><span data-stu-id="e1798-103">The rendering extension takes the results from a report definition that is combined with the actual data and renders the resulting data to a format that is useable.</span></span> <span data-ttu-id="e1798-104">La transformación de los datos combinados y el formato se efectúan utilizando una clase de Common Language Runtime (CLR) que implementa <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span><span class="sxs-lookup"><span data-stu-id="e1798-104">The transformation of the combined data and formatting is done by using a common language runtime (CLR) class that implements <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span></span> <span data-ttu-id="e1798-105">De esta forma se transforma el modelo de objetos en un formato de salida que puede usar un visor, impresora u otro destino de salida.</span><span class="sxs-lookup"><span data-stu-id="e1798-105">This transforms the object model into an output format that is consumable by a viewer, printer, or other output target.</span></span>  
  
 <span data-ttu-id="e1798-106"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> tiene tres métodos que deben estar codificados:</span><span class="sxs-lookup"><span data-stu-id="e1798-106">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> has three methods that must be coded:</span></span>  
  
-   <span data-ttu-id="e1798-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A>: representa el informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renders the report.</span></span>  
  
-   <span data-ttu-id="e1798-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A>: representa un flujo concreto del informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renders a specific stream from the report.</span></span>  
  
-   <span data-ttu-id="e1798-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>: obtiene la información adicional, como iconos, necesaria para el informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> - gets additional information, such as icons, that are required for the report.</span></span>  
  
 <span data-ttu-id="e1798-110">En las siguientes secciones se describen los métodos con más detalle.</span><span class="sxs-lookup"><span data-stu-id="e1798-110">The following sections discuss these methods in more detail.</span></span>  
  
## <a name="render-method"></a><span data-ttu-id="e1798-111">Método Render</span><span class="sxs-lookup"><span data-stu-id="e1798-111">Render Method</span></span>  
 <span data-ttu-id="e1798-112">El método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> contiene argumentos que representan los objetos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1798-112">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> method contains arguments that represent the following objects:</span></span>  
  
-   <span data-ttu-id="e1798-113">El elemento *report* que quiere representar.</span><span class="sxs-lookup"><span data-stu-id="e1798-113">The *report* that you want to render.</span></span> <span data-ttu-id="e1798-114">Este objeto contiene propiedades, datos e información de presentación para el informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-114">This object contains properties, data, and layout information for the report.</span></span> <span data-ttu-id="e1798-115">El informe es la raíz del árbol del modelo de objetos de informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-115">The report is the root of the report object model tree.</span></span>  
  
-   <span data-ttu-id="e1798-116">El parámetro *ServerParameters* que contiene el objeto de diccionario de cadena, con los parámetros para el servidor de informes, si los hubiera.</span><span class="sxs-lookup"><span data-stu-id="e1798-116">The *ServerParameters* that contain the string dictionary object, with the parameters for the report server, if any.</span></span>  
  
-   <span data-ttu-id="e1798-117">El parámetro *deviceInfo* que contiene la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1798-117">The *deviceInfo* parameter that contain the device settings.</span></span> <span data-ttu-id="e1798-118">Para más información, vea [Pasar la configuración de información de dispositivo a las extensiones de representación](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="e1798-118">For more information, see [Passing Device Information Settings to Rendering Extensions](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
-   <span data-ttu-id="e1798-119">El parámetro *clientCapabilities* que contiene un objeto de diccionario <xref:System.Collections.Specialized.NameValueCollection> que tiene información sobre el cliente al que está representando.</span><span class="sxs-lookup"><span data-stu-id="e1798-119">The *clientCapabilities* parameter that contains a <xref:System.Collections.Specialized.NameValueCollection> dictionary object that has information about the client to which you are rendering.</span></span>  
  
-   <span data-ttu-id="e1798-120">Parámetro *RenderProperties* que contiene información sobre el resultado de la representación.</span><span class="sxs-lookup"><span data-stu-id="e1798-120">The *RenderProperties* that contains information about the rendering result.</span></span>  
  
-   <span data-ttu-id="e1798-121">*createAndRegisterStream* es una función delegada a la que se va a llamar para obtener una secuencia en la que representar.</span><span class="sxs-lookup"><span data-stu-id="e1798-121">The *createAndRegisterStream* is a delegate function to be called to get a stream to render into.</span></span>  
  
### <a name="deviceinfo-parameter"></a><span data-ttu-id="e1798-122">Parámetro de deviceInfo</span><span class="sxs-lookup"><span data-stu-id="e1798-122">deviceInfo Parameter</span></span>  
 <span data-ttu-id="e1798-123">El parámetro *deviceInfo* contiene los parámetros de representación, no los parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-123">The *deviceInfo* parameter contains rendering parameters, not report parameters.</span></span> <span data-ttu-id="e1798-124">Estos parámetros de representación se pasan a la extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="e1798-124">These rendering parameters are passed to the rendering extension.</span></span> <span data-ttu-id="e1798-125">El servidor de informes convierte los valores de *deviceInfo* en un objeto <xref:System.Collections.Specialized.NameValueCollection>.</span><span class="sxs-lookup"><span data-stu-id="e1798-125">The *deviceInfo* values are converted into a <xref:System.Collections.Specialized.NameValueCollection> object by the report server.</span></span> <span data-ttu-id="e1798-126">Los elementos del parámetro *deviceInfo* se tratan como valores que no distinguen mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e1798-126">Items in the *deviceInfo* parameter are treated as case-insensitive values.</span></span> <span data-ttu-id="e1798-127">Si la solicitud de representación se ha producido como resultado de un acceso URL, los parámetros de dirección URL con el formato `rc:key=value` se convierten en pares de clave-valor en el objeto de diccionario *deviceInfo*.</span><span class="sxs-lookup"><span data-stu-id="e1798-127">If the render request came as a result of URL access, the URL parameters in the form `rc:key=value` are converted to key/value pairs in the *deviceInfo* dictionary object.</span></span> <span data-ttu-id="e1798-128">El código de detección de explorador también proporciona los elementos siguientes en el diccionario *clientCapabilities*: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type y AcceptLanguage.</span><span class="sxs-lookup"><span data-stu-id="e1798-128">The browser detection code also provides the following items in the *clientCapabilities* dictionary: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type, and AcceptLanguage.</span></span> <span data-ttu-id="e1798-129">Se omite cualquier par de nombre-valor del parámetro *deviceInfo* que la extensión de representación no entienda.</span><span class="sxs-lookup"><span data-stu-id="e1798-129">Any name/value pair in the *deviceInfo* parameter that is not understood by the rendering extension is ignored.</span></span> <span data-ttu-id="e1798-130">La muestra de código siguiente muestra un método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> de muestra que recupera los iconos.</span><span class="sxs-lookup"><span data-stu-id="e1798-130">The following code sample shows a sample <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method that retrieves icons:</span></span>  
  
```csharp  
public void GetRenderingResource (CreateStream createStreamCallback, NameValueCollection deviceInfo)  
{  
    string[] iconTagValues = deviceInfo.GetValues("Icon");  
    if ((iconTagValues != null) && (iconTagValues.Length > 0) )  
    {  
        // Create a stream to output to.  
        Stream outputStream = createStreamCallback(m_iconResourceName, "gif", null, "image/gif", false);  
        // Get the GIF image for one of the buttons on the toolbar  
        Image requiredImage = (Image) m_resourcemanager.GetObject(m_iconResourceName  
        // Write the image to the output stream  
        requiredImage.Save(outputStream, requiredImage.RawFormat);  
    }  
    return;  
}  
```  
  
## <a name="renderstream-method"></a><span data-ttu-id="e1798-131">Método RenderStream</span><span class="sxs-lookup"><span data-stu-id="e1798-131">RenderStream Method</span></span>  
 <span data-ttu-id="e1798-132">El método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> representa un flujo determinado del informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-132">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> method renders a particular stream from the report.</span></span> <span data-ttu-id="e1798-133">Todos los flujos se crean durante la llamada de <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> inicial, pero los flujos no se devuelven inicialmente al cliente.</span><span class="sxs-lookup"><span data-stu-id="e1798-133">All streams are created during the initial <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> call, but the streams are not returned to the client initially.</span></span> <span data-ttu-id="e1798-134">Este método se utiliza para flujos secundarios (similares a las imágenes en la representación HTML) o páginas adicionales de una extensión de representación de varias páginas (similar a Image/EMF).</span><span class="sxs-lookup"><span data-stu-id="e1798-134">This method is used for secondary streams, such as images in HTML rendering, or additional pages of a multi-page rendering extension, such as Image/EMF.</span></span>  
  
## <a name="getrenderingresource-method"></a><span data-ttu-id="e1798-135">Método GetRenderingResource</span><span class="sxs-lookup"><span data-stu-id="e1798-135">GetRenderingResource Method</span></span>  
 <span data-ttu-id="e1798-136">El método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> recupera la información sin ejecutar una representación completa del informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-136">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method retrieves the information without executing an entire rendering of the report.</span></span> <span data-ttu-id="e1798-137">Hay ocasiones en que el informe requiere información que no requiere representar el propio informe.</span><span class="sxs-lookup"><span data-stu-id="e1798-137">There are times when the report requires information that does not require the report itself to be rendered.</span></span> <span data-ttu-id="e1798-138">Por ejemplo, si necesita el icono asociado a la extensión de representación, utilice el parámetro *deviceInfo* que contiene la etiqueta única **\<Icon>** .</span><span class="sxs-lookup"><span data-stu-id="e1798-138">For example, if you need the icon associated with the rendering extension, use the *deviceInfo* parameter containing the single tag **\<Icon>**.</span></span> <span data-ttu-id="e1798-139">En estos casos, puede usar el método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1798-139">In these cases, you can use the <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1798-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1798-140">See Also</span></span>  
 <span data-ttu-id="e1798-141">[Implementar una extensión de representación](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="e1798-141">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 [<span data-ttu-id="e1798-142">Información general de las extensiones de representación</span><span class="sxs-lookup"><span data-stu-id="e1798-142">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
  
  
