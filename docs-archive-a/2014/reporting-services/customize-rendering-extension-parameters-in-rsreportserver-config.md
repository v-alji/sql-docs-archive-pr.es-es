---
title: Personalizar los parámetros de extensión de representación en RSReportServer.Config | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- configuration options [Reporting Services]
- DeviceInfo settings
- rendering extensions [Reporting Services], overriding behaviors
- parameters [Reporting Services], report rendering
- overriding report rendering behavior
- extensions [Reporting Services], rendering
ms.assetid: 3bf7ab2b-70bb-41c8-acda-227994d15aed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35a01e12fa4016d03717b008e4241c3be5e55236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750534"
---
# <a name="customize-rendering-extension-parameters-in-rsreportserverconfig"></a><span data-ttu-id="a164c-102">Personalizar los parámetros de extensión de representación en RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="a164c-102">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>
  <span data-ttu-id="a164c-103">Es posible especificar parámetros de extensión de representación en el archivo de configuración RSReportServer para invalidar el comportamiento predeterminado de la representación de los informes que se ejecutan en un servidor de informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a164c-103">You can specify rendering extension parameters in the RSReportServer configuration file to override default report rendering behavior for reports that run on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="a164c-104">Los parámetros de extensión de representación se pueden modificar para lograr los siguientes objetivos:</span><span class="sxs-lookup"><span data-stu-id="a164c-104">You can modify rendering extension parameters to achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="a164c-105">Cambiar la manera en que aparece el nombre de la extensión de representación en la lista Exportar de la barra de herramientas de informe (por ejemplo, para cambiar "Archivo web" a "MHTML") o traducir el nombre a un idioma diferente.</span><span class="sxs-lookup"><span data-stu-id="a164c-105">Change how the rendering extension name appears in the Export list of the report toolbar (for example, to change "Web archive" to "MHTML"), or localize the name to a different language.</span></span>  
  
-   <span data-ttu-id="a164c-106">Crear varias instancias de la misma extensión de representación para admitir distintas opciones de presentación de informes (por ejemplo, una versión en modo horizontal y vertical de la extensión de representación en imágenes).</span><span class="sxs-lookup"><span data-stu-id="a164c-106">Create multiple instances of the same rendering extension to support different report presentation options (for example, a portrait and landscape mode version of the Image rendering extension).</span></span>  
  
-   <span data-ttu-id="a164c-107">Cambiar los parámetros de la extensión de representación predeterminada para que utilicen valores diferentes (por ejemplo, la extensión de representación en imágenes utiliza TIFF como el formato de salida predeterminado; se pueden modificar los parámetros de la extensión de manera que se utilice EMF).</span><span class="sxs-lookup"><span data-stu-id="a164c-107">Change the default rendering extension parameters to use different values (for example, the Image rendering extension uses TIFF as the default output format; you can modify the extension parameters to use EMF instead).</span></span>  
  
 <span data-ttu-id="a164c-108">La modificación de los parámetros de extensión de representación solo afecta a las operaciones de representación del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a164c-108">Changing the rendering extension parameters only affects rendering operations on the report server.</span></span> <span data-ttu-id="a164c-109">La configuración de la extensión de representación no se puede reemplazar en la vista previa del informe del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="a164c-109">You cannot override rendering extension settings in report preview in Report Designer.</span></span>  
  
 <span data-ttu-id="a164c-110">Cuando se especifican parámetros de extensión de representación en los archivos de configuración, las extensiones de representación se ven afectadas globalmente.</span><span class="sxs-lookup"><span data-stu-id="a164c-110">Specifying rendering extension parameters in the configuration files affects rendering extensions globally.</span></span> <span data-ttu-id="a164c-111">Los valores de los archivos de configuración se usarán en lugar de los valores predeterminados siempre que se utilice una extensión de representación determinada.</span><span class="sxs-lookup"><span data-stu-id="a164c-111">The settings in the configuration files are used in place of default values whenever a particular rendering extension is used.</span></span> <span data-ttu-id="a164c-112">Si se quiere establecer parámetros de extensión de representación para un informe o una operación de representación específicos, debe especificarse la información de dispositivo mediante programación, usando el método <xref:ReportExecution2005.ReportExecutionService.Render%2A> o especificando la configuración de información de dispositivo en una dirección URL de informe.</span><span class="sxs-lookup"><span data-stu-id="a164c-112">If you want to set rendering extension parameters for a specific report or render operation, you must specify device information programmatically using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method or by specifying device information settings on a report URL.</span></span> <span data-ttu-id="a164c-113">Para obtener más información sobre cómo especificar los valores de información de dispositivo para una operación de representación, y ver la lista completa de valores de información de dispositivo, vea [Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="a164c-113">For more information about specifying device information settings for a render operation, and to view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="finding-and-modifying-rsreportserverconfig"></a><span data-ttu-id="a164c-114">Buscar y modificar RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="a164c-114">Finding and Modifying RSReportServer.config</span></span>  
 <span data-ttu-id="a164c-115">Los ajustes de configuración para los formatos de la salida de informes se especifican como parámetros de extensión de representación en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a164c-115">Configuration settings for report output formats are specified as rendering extension parameters in the RSReportServer.config file.</span></span> <span data-ttu-id="a164c-116">Para especificar parámetros de extensión de representación en los archivos de configuración, es necesario saber cómo se definen las estructuras XML que establecen los parámetros de representación.</span><span class="sxs-lookup"><span data-stu-id="a164c-116">To specify rendering extension parameters in the configuration files, you must know how to define the XML structures that set rendering parameters.</span></span> <span data-ttu-id="a164c-117">Hay dos estructuras XML que se pueden modificar:</span><span class="sxs-lookup"><span data-stu-id="a164c-117">There are two XML structures that you can modify:</span></span>  
  
-   <span data-ttu-id="a164c-118">El elemento `OverrideNames` define el nombre para mostrar y el idioma de la extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="a164c-118">The `OverrideNames` element defines the display name and language of the rendering extension.</span></span>  
  
-   <span data-ttu-id="a164c-119">La estructura XML `DeviceInfo` define la configuración de información de dispositivo que utiliza una extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="a164c-119">The `DeviceInfo` XML structure defines the device information settings that are used by a rendering extension.</span></span> <span data-ttu-id="a164c-120">La mayoría de los parámetros de extensión de representación se especifican como valores de información de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a164c-120">Most rendering extension parameters are specified as device information settings.</span></span>  
  
 <span data-ttu-id="a164c-121">Para modificarlo, se puede usar un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a164c-121">You can use a text editor to modify the file.</span></span> <span data-ttu-id="a164c-122">El archivo RSReportServer.config se encuentra en la carpeta \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="a164c-122">The RSReportServer.config file can be found in the \Reporting Services\Report Server\Bin folder.</span></span> <span data-ttu-id="a164c-123">Para más información sobre cómo modificar archivos de configuración, vea [Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="a164c-123">For more information about modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span>  
  
## <a name="changing-the-display-name"></a><span data-ttu-id="a164c-124">Cambiar el nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="a164c-124">Changing the Display Name</span></span>  
 <span data-ttu-id="a164c-125">El nombre para mostrar de una extensión de representación aparece en la lista Exportar de la barra de herramientas de informe.</span><span class="sxs-lookup"><span data-stu-id="a164c-125">The display name for a rendering extension appears in the Export list of the report toolbar.</span></span> <span data-ttu-id="a164c-126">Algunos ejemplos de nombres para mostrar predeterminados son Archivo web, Archivo TIFF y Archivo PDF de Acrobat.</span><span class="sxs-lookup"><span data-stu-id="a164c-126">Examples of default display names include Web archive, TIFF file, and Acrobat (PDF) file.</span></span> <span data-ttu-id="a164c-127">El nombre para mostrar predeterminado se puede sustituir por un valor personalizado especificando el elemento `OverrideNames` en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a164c-127">You can replace the default display name with a custom value by specifying the `OverrideNames` element in the configuration files.</span></span> <span data-ttu-id="a164c-128">Además, si se van a definir dos instancias de una extensión de representación, se puede utilizar el elemento `OverrideNames` para distinguirlas en la lista Exportar.</span><span class="sxs-lookup"><span data-stu-id="a164c-128">In addition, if you are defining two instances of a single rendering extension, you can use the `OverrideNames` element to distinguish each instance in the Export list.</span></span>  
  
 <span data-ttu-id="a164c-129">Dado que los nombres para mostrar se traducen, será necesario establecer el atributo `Language` si se va a sustituir el nombre para mostrar predeterminado por un valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="a164c-129">Because display names are localized, you must set the `Language` attribute if you are replacing the default display name with a custom value.</span></span> <span data-ttu-id="a164c-130">Si no, se pasará por alto cualquier nombre que se especifique.</span><span class="sxs-lookup"><span data-stu-id="a164c-130">Otherwise, any name that you specify will be ignored.</span></span> <span data-ttu-id="a164c-131">El valor de idioma que se establezca debe ser válido en el equipo del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a164c-131">The language value that you set must be valid for the report server computer.</span></span> <span data-ttu-id="a164c-132">Por ejemplo, si el servidor de informes se ejecuta en un sistema operativo en francés, deberá especificarse "fr-FR" como valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="a164c-132">For example, if the report server is running on a French operating system, you should specify "fr-FR" as the attribute value.</span></span>  
  
 <span data-ttu-id="a164c-133">En el ejemplo siguiente se muestra cómo especificar un nombre personalizado en un servidor de informes en inglés:</span><span class="sxs-lookup"><span data-stu-id="a164c-133">The following example illustrates how to provide a custom name on an English report server:</span></span>  
  
```  
<Extension Name="XML" Type="Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport,Microsoft.ReportingServices.DataRendering">  
   <OverrideNames>  
     <Name Language="en-US">My Custom Display Name for XML Rendering</Name>  
   </OverrideNames>  
</Extension>  
```  
  
## <a name="changing-device-information-settings"></a><span data-ttu-id="a164c-134">Cambiar la configuración de la información del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a164c-134">Changing Device Information Settings</span></span>  
 <span data-ttu-id="a164c-135">Para modificar la configuración predeterminada de la información del dispositivo que utiliza una extensión de representación ya implementada en el servidor de informes, debe incluirse la estructura XML `DeviceInfo` en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a164c-135">To modify default device information settings that are used by a rendering extension that is already deployed on your report server, you must type the `DeviceInfo` XML structure into the configuration files.</span></span> <span data-ttu-id="a164c-136">Cada extensión de representación admite valores de información de dispositivo exclusivos para esa extensión.</span><span class="sxs-lookup"><span data-stu-id="a164c-136">Every rendering extension supports device information settings that are unique to that extension.</span></span> <span data-ttu-id="a164c-137">Para ver la lista completa de la configuración de la información de dispositivos, vea [Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="a164c-137">To view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="a164c-138">En el ejemplo siguiente se muestran la estructura XML y la sintaxis que modifica la configuración predeterminada de la extensión de representación en imágenes:</span><span class="sxs-lookup"><span data-stu-id="a164c-138">The following example provides an illustration of the XML structure and syntax that modifies the default settings of the Image rendering extension:</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">Image (EMF)</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <ColorDepth>32</ColorDepth>  
                <DpiX>300</DpiX>  
                <DpiY>300</DpiY>  
                <OutputFormat>EMF</OutputFormat>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="configuring-multiple-entries-for-a-rendering-extension"></a><span data-ttu-id="a164c-139">Configurar varias entradas para una extensión de representación</span><span class="sxs-lookup"><span data-stu-id="a164c-139">Configuring Multiple Entries for a Rendering Extension</span></span>  
 <span data-ttu-id="a164c-140">Se pueden crear varias instancias de la misma extensión de representación para admitir diferentes opciones de presentación de informes.</span><span class="sxs-lookup"><span data-stu-id="a164c-140">You can create multiple instances of the same rendering extension to support different report presentation options.</span></span> <span data-ttu-id="a164c-141">Cada instancia que se defina puede tener una combinación distinta de valores de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a164c-141">Each instance that you define can have a different combination of parameter values.</span></span> <span data-ttu-id="a164c-142">Cuando defina nuevas instancias de una extensión de representación existente, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a164c-142">When defining new instances of an existing rendering extension, be sure to do the following:</span></span>  
  
-   <span data-ttu-id="a164c-143">Especifique un nombre único para la extensión.</span><span class="sxs-lookup"><span data-stu-id="a164c-143">Specify a unique name for the extension.</span></span>  
  
     <span data-ttu-id="a164c-144">Cada instancia debe tener un valor único para el atributo `Name`.</span><span class="sxs-lookup"><span data-stu-id="a164c-144">Each instance must have a unique value for the `Name` attribute.</span></span> <span data-ttu-id="a164c-145">En el ejemplo siguiente se utilizan los nombres "IMAGE (EMF Landscape)" e "IMAGE (EMF Portrait)" para distinguir las dos instancias.</span><span class="sxs-lookup"><span data-stu-id="a164c-145">The following example uses the names "IMAGE (EMF Landscape)" and "IMAGE (EMF Portrait)" to distinguish between the two instances.</span></span>  
  
     <span data-ttu-id="a164c-146">Tenga cuidado al cambiar el nombre de una extensión de representación ya implementada.</span><span class="sxs-lookup"><span data-stu-id="a164c-146">Use caution when changing the name of a rendering extension that is already deployed.</span></span> <span data-ttu-id="a164c-147">Los programadores que especifican extensiones de representación mediante programación usan el nombre de la extensión para identificar la instancia que se va a utilizar en una operación de representación determinada.</span><span class="sxs-lookup"><span data-stu-id="a164c-147">Developers who specify rendering extensions programmatically use the extension name to identify which instance to use for a particular render operation.</span></span> <span data-ttu-id="a164c-148">Si se ejecutan aplicaciones de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] personalizadas en el servidor de informes, asegúrese de que el programador sabe que ha modificado un nombre de extensión existente o ha agregado uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="a164c-148">If you are running custom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applications on your report server, make sure that the developer knows if you modify an existing extension name or add a new one.</span></span>  
  
-   <span data-ttu-id="a164c-149">Especifique un nombre para mostrar único de manera que los usuarios entiendan las diferencias de cada formato de salida.</span><span class="sxs-lookup"><span data-stu-id="a164c-149">Specify a unique display name so that users can understand the differences for each output format.</span></span>  
  
     <span data-ttu-id="a164c-150">Si configura varias versiones de la misma extensión, puede asignar a cada versión un nombre único, proporcionando un valor para `OverrideNames`.</span><span class="sxs-lookup"><span data-stu-id="a164c-150">If you are configuring multiple versions of the same extension, you can give each version a unique name by providing a value for `OverrideNames`.</span></span> <span data-ttu-id="a164c-151">En caso contrario, todas las versiones de la extensión aparentemente tendrán el mismo nombre en la lista de opciones de exportación de la barra de herramientas de informe.</span><span class="sxs-lookup"><span data-stu-id="a164c-151">Otherwise, all versions of the extension will appear to have the same name in the Export options list on the report toolbar.</span></span>  
  
 <span data-ttu-id="a164c-152">En el siguiente ejemplo se muestra cómo utilizar la extensión de representación en imágenes predeterminada (que genera salida TIFF) para generar salida EMF en modo vertical, junto con una segunda instancia que genera informes en formato EMF en modo horizontal.</span><span class="sxs-lookup"><span data-stu-id="a164c-152">The following example illustrates how to use the default Image rendering extension (which produces TIFF output) to output EMF in Portrait mode alongside a second instance that outputs reports in EMF in Landscape mode.</span></span> <span data-ttu-id="a164c-153">Observe cómo el nombre de cada extensión es único.</span><span class="sxs-lookup"><span data-stu-id="a164c-153">Notice that each extension name is unique.</span></span> <span data-ttu-id="a164c-154">Cuando pruebe este ejemplo, no olvide elegir informes que no contengan funciones interactivas, como opciones de mostrar u ocultar, matrices o vínculos de obtención de detalles (las funciones interactivas no funcionan en la extensión de representación en imágenes):</span><span class="sxs-lookup"><span data-stu-id="a164c-154">When testing this example, remember to choose reports that do not contain interactive features such as show/hide options, matrices, or drillthrough links (interactive features do not work in the Image rendering extension):</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF Landscape)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Landscape Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>8.5in</PageHeight>  
                <PageWidth>11in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
    <Extension Name="IMAGE (EMF Portrait)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Portait Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>11in</PageHeight>  
                <PageWidth>8.5in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a164c-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a164c-155">See Also</span></span>  
 <span data-ttu-id="a164c-156">[Archivo de configuración RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-156">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="a164c-157">[Archivo de configuración RSReportDesigner](report-server/rsreportdesigner-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-157">[RSReportDesigner Configuration File](report-server/rsreportdesigner-configuration-file.md) </span></span>  
 <span data-ttu-id="a164c-158">[Configuración de la información del dispositivo CSV](csv-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-158">[CSV Device Information Settings](csv-device-information-settings.md) </span></span>  
 <span data-ttu-id="a164c-159">[Configuración de la información del dispositivo Excel](excel-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-159">[Excel Device Information Settings](excel-device-information-settings.md) </span></span>  
 <span data-ttu-id="a164c-160">[Configuración de la información del dispositivo HTML](html-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-160">[HTML Device Information Settings](html-device-information-settings.md) </span></span>  
 <span data-ttu-id="a164c-161">[Configuración de la información del dispositivo de imagen](image-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-161">[Image Device Information Settings](image-device-information-settings.md) </span></span>  
 <span data-ttu-id="a164c-162">[Configuración de la información del dispositivo MHTML](mhtml-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-162">[MHTML Device Information Settings](mhtml-device-information-settings.md) </span></span>  
 <span data-ttu-id="a164c-163">[Configuración de la información del dispositivo PDF](pdf-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a164c-163">[PDF Device Information Settings](pdf-device-information-settings.md) </span></span>  
 [<span data-ttu-id="a164c-164">Configuración de la información del dispositivo XML</span><span class="sxs-lookup"><span data-stu-id="a164c-164">XML Device Information Settings</span></span>](xml-device-information-settings.md)  
  
  
