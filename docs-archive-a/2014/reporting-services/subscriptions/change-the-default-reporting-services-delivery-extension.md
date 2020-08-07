---
title: Cambiar la extensión de entrega predeterminada de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], default delivery extension
ms.assetid: 5f6fee72-01bf-4f6c-85d2-7863c46c136b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cc1b3af2a4fe3038b761d0b48030062da06d354e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747418"
---
# <a name="change-the-default-reporting-services-delivery-extension"></a><span data-ttu-id="74547-102">Cambiar la extensión de entrega predeterminada de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="74547-102">Change the Default Reporting Services Delivery Extension</span></span>
  <span data-ttu-id="74547-103">Puede modificar las opciones de configuración de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para cambiar la extensión de entrega predeterminada que aparece en la lista **Entregado por** de una página de definición de suscripción.</span><span class="sxs-lookup"><span data-stu-id="74547-103">You can modify [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration settings to change the default delivery extension that appears in the **Delivered by** list of a subscription definition page.</span></span> <span data-ttu-id="74547-104">Por ejemplo, puede modificar la configuración de modo que cuando los usuarios creen una nueva suscripción, la entrega de recurso compartido de archivos se seleccione de forma predeterminada en lugar de la entrega por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="74547-104">For example you can modify the configuration so that when users create a new subscription, file share delivery is selected by default instead of e-mail delivery.</span></span> <span data-ttu-id="74547-105">También puede cambiar el orden en que se muestran las extensiones de entrega en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="74547-105">You can also change the order the delivery extensions are listed in the user interface.</span></span>

 <span data-ttu-id="74547-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] | Modo de SharePoint de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74547-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="74547-107">incluye las extensiones de entrega Correo electrónico y Recurso compartido de archivos de Windows.</span><span class="sxs-lookup"><span data-stu-id="74547-107">includes E-mail and Windows File Share delivery are extensions.</span></span> <span data-ttu-id="74547-108">El servidor de informes puede tener extensiones de entrega adicionales si ha implementado extensiones personalizadas o de otros fabricantes para admitir la entrega personalizada.</span><span class="sxs-lookup"><span data-stu-id="74547-108">Your report server might have additional delivery extensions if you have deployed custom or third-party extensions to support custom delivery.</span></span> <span data-ttu-id="74547-109">La disponibilidad de una extensión de entrega depende de si está implementada en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="74547-109">The availability of a delivery extension depends on whether it is deployed on a report server.</span></span>

## <a name="default-native-mode-report-server-configuration"></a><span data-ttu-id="74547-110">Configuración predeterminada del servidor de informes de modo nativo</span><span class="sxs-lookup"><span data-stu-id="74547-110">Default Native mode report server configuration</span></span>
 <span data-ttu-id="74547-111">El orden en el que una extensión de entrega aparece en el Administrador de informes en la lista **Entregado por** se basa en el orden de las entradas de extensión de entrega del archivo **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="74547-111">The order of a delivery extension appears in Report Manager in the **Delivered by** list is based on the order of the delivery extension entries in the **RSReportServer.config** file.</span></span> <span data-ttu-id="74547-112">Por ejemplo, la siguiente imagen muestra el correo electrónico primero en la lista y está seleccionado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="74547-112">For example the following image shows e-mail first in the list and it is selected by default.</span></span>

 <span data-ttu-id="74547-113">![lista predeterminada de extensiones de entrega](../media/ssrs-default-delivery.png "lista predeterminada de extensiones de entrega")</span><span class="sxs-lookup"><span data-stu-id="74547-113">![default list of delivery extensions](../media/ssrs-default-delivery.png "default list of delivery extensions")</span></span>

 <span data-ttu-id="74547-114">La siguiente es la sección predeterminada de **RSReportServer.config** que controla la extensión de entrega predeterminada y el orden en que se muestran en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="74547-114">The following is the default section of **RSReportServer.config** that controls the default delivery extension and the order they are displayed in Report Manager.</span></span> <span data-ttu-id="74547-115">Tenga en cuenta que el correo electrónico aparece en primer lugar en el archivo y se establece como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74547-115">Note that email appears first in the file and it is set as the default.</span></span>

```xml
<DeliveryUI>
     <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
          <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
               <Configuration>
               <RSEmailDPConfiguration>
                    <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
               </RSEmailDPConfiguration>
               </Configuration>
     </Extension>
     <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider"/>
</DeliveryUI>
```

#### <a name="configure-file-share-delivery-as-the-default-delivery-extension-in-report-manager"></a><span data-ttu-id="74547-116">Configure la entrega de recurso compartido de archivos como la extensión de entrega predeterminada en el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="74547-116">Configure File Share Delivery as the default delivery extension in Report Manager</span></span>

1.  <span data-ttu-id="74547-117">Los pasos de este procedimiento modifican la configuración para que la entrega de recurso compartido aparece como la primera opción en la interfaz de usuario y es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="74547-117">The steps in this procedure modify the configuration so that file share delivery is listed as the first option in the UI and it is the default selection.</span></span>

     <span data-ttu-id="74547-118">Abra el archivo RSReportServer.config en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="74547-118">Open the RSReportServer.config file in a text editor.</span></span> <span data-ttu-id="74547-119">Para obtener más información acerca del archivo de configuración, consulte [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="74547-119">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="74547-120">Después de que cambie la configuración, la interfaz de usuario será similar a la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="74547-120">After the configuration changes, the UI will look like the following image:</span></span>

     <span data-ttu-id="74547-121">![lista de extensiones de entrega modificada](../media/ssrs-modified-delivery.png "lista de extensiones de entrega modificada")</span><span class="sxs-lookup"><span data-stu-id="74547-121">![modified list of delivery extensions](../media/ssrs-modified-delivery.png "modified list of delivery extensions")</span></span>

2.  <span data-ttu-id="74547-122">Modifique la sección DeliveryUI para que el aspecto sea como en el ejemplo siguiente y tenga en cuenta los cambios clave de:</span><span class="sxs-lookup"><span data-stu-id="74547-122">Modify the DeliveryUI section to look like the following sample and note the key changes of:</span></span>

    1.  <span data-ttu-id="74547-123">La extensión de recurso compartido de archivos está antes de la extensión de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="74547-123">The FileShare extension is before the email extension.</span></span> <span data-ttu-id="74547-124">Esto cambiará el orden en que las extensiones aparecen en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="74547-124">This will change the order the extensions are listed in Report Manager.</span></span>

    2.  <span data-ttu-id="74547-125">La extensión de recurso compartido de archivos contiene la etiqueta DefaultExtension `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` y se agregó la etiqueta de cierre de extensión `</Extension>`.</span><span class="sxs-lookup"><span data-stu-id="74547-125">The File share extension contains DefaultExtension tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` and the extension end tag was added `</Extension>`.</span></span>

    3.  <span data-ttu-id="74547-126">La extensión de correo electrónico ya no está configurada como el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74547-126">The email extension is no longer configured as the default.</span></span> `<DefaultDeliveryExtension>False</DefaultDeliveryExtension>`

    ```
    <DeliveryUI>
         <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider">
              <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
         </Extension>
         <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
         <DefaultDeliveryExtension>False</DefaultDeliveryExtension>
         <Configuration>
              <RSEmailDPConfiguration>
                   <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
              </RSEmailDPConfiguration>
         </Configuration>
         </Extension>
    </DeliveryUI>
    ```

3.  <span data-ttu-id="74547-127">Guarde el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="74547-127">Save the configuration file.</span></span>

4.  <span data-ttu-id="74547-128">En pocos minutos el servidor de informes volverá a cargar el archivo de configuración y la nueva configuración surtirá efecto.</span><span class="sxs-lookup"><span data-stu-id="74547-128">Within a few minutes the report server will reload the configuration file and the new settings will take effect.</span></span> <span data-ttu-id="74547-129">Puede reiniciar el servicio del servidor de informes para forzar la carga del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="74547-129">You can restart the report server service to force the loading of the configuration file.</span></span>

     <span data-ttu-id="74547-130">Cuando se lee la configuración, se escribe el siguiente evento en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="74547-130">The following event is written to the windows event log when the configuration is read.</span></span>

     <span data-ttu-id="74547-131">**Id. de evento**: 109</span><span class="sxs-lookup"><span data-stu-id="74547-131">**Event ID:** 109</span></span>

     <span data-ttu-id="74547-132">**Origen**: Servicio Servidor de informes de Windows (nombre de instancia)</span><span class="sxs-lookup"><span data-stu-id="74547-132">**Source:** Report Server Windows Service (instance name)</span></span>

     <span data-ttu-id="74547-133">Se ha modificado el archivo RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="74547-133">The RSReportServer.config file has been modified</span></span>

## <a name="sharepoint-mode-report-servers"></a><span data-ttu-id="74547-134">Servidores de informes en modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="74547-134">SharePoint mode report servers</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="74547-135">El modo de SharePoint almacena la información de las extensiones en las bases de datos de aplicación de servicio de SharePoint y no en el archivo RsrReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="74547-135">SharePoint mode stores extensions information in the SharePoint service application databases and not in the RsrReportServer.config file.</span></span> <span data-ttu-id="74547-136">En el modo de SharePoint, la configuración de la extensión de entrega se modifica con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74547-136">In SharePoint mode, delivery extension configuration is modified using PowerShell.</span></span>

#### <a name="configure-the-default-delivery-extension"></a><span data-ttu-id="74547-137">Configurar la extensión de entrega predeterminada</span><span class="sxs-lookup"><span data-stu-id="74547-137">Configure the default delivery extension</span></span>

1.  <span data-ttu-id="74547-138">Abra el **Shell de administración de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="74547-138">Open the **SharePoint Management Shell**.</span></span>

2.  <span data-ttu-id="74547-139">Puede omitir este paso si ya conoce el nombre de su aplicación de servicio de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74547-139">You can skip this step if you already know the name of your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="74547-140">Use el PowerShell siguiente a la lista de las aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en la granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="74547-140">Use the following PowerShell to list the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service applications in your SharePoint farm.</span></span>

    ```powershell
    Get-SPRSServiceApplication | Format-List *
    ```

3.  <span data-ttu-id="74547-141">Ejecute el PowerShell siguiente para comprobar la extensión de entrega predeterminada actual para la aplicación de servicio "ssrsapp" de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74547-141">Run the following PowerShell to verify the current default delivery extension for the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application "ssrsapp".</span></span>

    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -Like "ssrsapp*"};
    Get-SPRSExtension -Identity $app | Where {$_.ServerDirectivesXML -Like "<DefaultDelivery*"} | Format-List *
    ```

## <a name="see-also"></a><span data-ttu-id="74547-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74547-142">See Also</span></span>
 <span data-ttu-id="74547-143">[Archivo de configuración](../report-server/rsreportserver-config-configuration-file.md) RSReportServer [distribución del recurso compartido de archivos de configuración del archivo de configuración en Reporting Services](file-share-delivery-in-reporting-services.md) [entrega de correo electrónico en Reporting Services](e-mail-delivery-in-reporting-services.md) [configurar un servidor de informes para la entrega de correo electrónico &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md)</span><span class="sxs-lookup"><span data-stu-id="74547-143">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [File Share Delivery in Reporting Services](file-share-delivery-in-reporting-services.md) [E-Mail Delivery in Reporting Services](e-mail-delivery-in-reporting-services.md) [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span></span>
