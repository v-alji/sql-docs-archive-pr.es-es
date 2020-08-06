---
title: Configurar un servidor de informes para la entrega de correo electrónico (SSRS Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], distributing
- report servers [Reporting Services], e-mail delivery
- remote SMTP service [Reporting Services]
- distributing reports [Reporting Services], e-mail
- CDO
- Collaboration Data Objects
- SMTP settings [Reporting Services]
- e-mail [Reporting Services]
- sending reports
- mail [Reporting Services]
- local SMTP service [Reporting Services]
ms.assetid: b838f970-d11a-4239-b164-8d11f4581d83
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3122dbbb5debc90afa73ca0f8ab0d8e23d38a0ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674558"
---
# <a name="configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager"></a><span data-ttu-id="5dd73-102">Configurar un servidor de informes para la entrega de correo electrónico (Administrador de configuración de SSRS)</span><span class="sxs-lookup"><span data-stu-id="5dd73-102">Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)</span></span>


  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5dd73-103">incluye una extensión de entrega por correo electrónico para distribuir informes mediante el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5dd73-103">includes an e-mail delivery extension so that you can distribute reports through e-mail.</span></span> <span data-ttu-id="5dd73-104">Según cómo defina la suscripción del correo electrónico, una entrega podría estar compuesta de una notificación, un vínculo, datos adjuntos o un informe incrustado.</span><span class="sxs-lookup"><span data-stu-id="5dd73-104">Depending on how you define the e-mail subscription, a delivery might consist of a notification, link, attachment, or embedded report.</span></span> <span data-ttu-id="5dd73-105">La extensión de entrega por correo electrónico funciona con la tecnología de servidor de correo existente.</span><span class="sxs-lookup"><span data-stu-id="5dd73-105">The e-mail delivery extension works with your existing mail server technology.</span></span> <span data-ttu-id="5dd73-106">El servidor de correo debe ser un servidor SMTP o un reenviador.</span><span class="sxs-lookup"><span data-stu-id="5dd73-106">The mail server must be an SMTP server or forwarder.</span></span> <span data-ttu-id="5dd73-107">El servidor de informes se conecta a un servidor SMTP a través de bibliotecas de Collaboration Data Objects (CDO), cdosys.dll, que el sistema operativo proporciona.</span><span class="sxs-lookup"><span data-stu-id="5dd73-107">The report server connects to an SMTP server through Collaboration Data Objects (CDO) libraries (cdosys.dll) that are provided by the operating system.</span></span>  
  
 <span data-ttu-id="5dd73-108">La extensión de entrega por correo electrónico del servidor de informes no está configurada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5dd73-108">The report server e-mail delivery extension is not configured by default.</span></span> <span data-ttu-id="5dd73-109">Debe utilizar el Administrador de configuración de Reporting Services para configurar dicha extensión mínimamente.</span><span class="sxs-lookup"><span data-stu-id="5dd73-109">You must use the Reporting Services Configuration Manager to minimally configure the extension.</span></span> <span data-ttu-id="5dd73-110">Para establecer propiedades avanzadas, debe editar el archivo `RSReportServer.config` .</span><span class="sxs-lookup"><span data-stu-id="5dd73-110">To set advanced properties, you must edit the `RSReportServer.config` file.</span></span> <span data-ttu-id="5dd73-111">Si no puede configurar el servidor de informes para que utilice esta extensión, puede entregar los informes en una carpeta compartida.</span><span class="sxs-lookup"><span data-stu-id="5dd73-111">If you cannot configure the report server to use this extension, you can deliver reports to a shared folder instead.</span></span> <span data-ttu-id="5dd73-112">Para obtener más información, vea [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5dd73-112">For more information, see [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="5dd73-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo</span><span class="sxs-lookup"><span data-stu-id="5dd73-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 
  
##  <a name="configuration-requirements"></a><a name="bkmk_configuration_requirements"></a><span data-ttu-id="5dd73-114">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="5dd73-114">Configuration Requirements</span></span>  
  
-   <span data-ttu-id="5dd73-115">La entrega por correo electrónico del servidor de informes se implementa en Collaboration Data Objects (CDO) y requiere un servidor del Protocolo simple de transferencia de correo (SMTP) local o remoto, o bien un reenviador SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-115">Report server e-mail delivery is implemented on Collaboration Data Objects (CDO) and requires a local or remote Simple Mail Transfer Protocol (SMTP) server or SMTP forwarder.</span></span> <span data-ttu-id="5dd73-116">SMTP no se admite en todos los sistemas operativos Windows.</span><span class="sxs-lookup"><span data-stu-id="5dd73-116">SMTP is not supported on all Windows operating systems.</span></span> <span data-ttu-id="5dd73-117">Si usa la edición basada en Itanium de Windows Server 2008, no se admite SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-117">If you are using the Itanium-based edition of Windows Server 2008, SMTP is not supported.</span></span> <span data-ttu-id="5dd73-118">Para obtener más información sobre las opciones de configuración que se proporcionan a través de CDO, vea [el tema sobre la coclase Configuration](https://go.microsoft.com/fwlink/?LinkId=98237) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="5dd73-118">For more information about configuration options provided through CDO, see [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) on MSDN.</span></span>  
  
-   <span data-ttu-id="5dd73-119">La cuenta del servicio Servidor de informes debe tener permiso para enviar correo electrónico en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-119">The Report Server service account must have permission on the SMTP server to send mail.</span></span>  
  
-   <span data-ttu-id="5dd73-120">La extensión de entrega por correo electrónico utiliza la codificación UTF-8 en los datos adjuntos del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5dd73-120">The e-mail delivery extension uses UTF-8 encoding in e-mail attachments.</span></span> <span data-ttu-id="5dd73-121">La codificación no se puede modificar; la extensión de representación en HTML solo admite UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5dd73-121">You cannot modify the encoding; the HTML rendering extension only supports UTF-8.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dd73-122">La extensión de entrega por correo electrónico predeterminada no es compatible con la firma digital ni el cifrado de mensajes de correo salientes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-122">The default e-mail delivery extension does not provide support for digitally signing or encrypting outgoing mail messages.</span></span>  
  
 
  
##  <a name="configuring-a-report-server-for-local-or-remote-smtp-service"></a><a name="bkmk_configure_for_local_or_remote_SMTP"></a><span data-ttu-id="5dd73-123">Configurar un servidor de informes para el servicio SMTP local o remoto</span><span class="sxs-lookup"><span data-stu-id="5dd73-123">Configuring a Report Server for Local or Remote SMTP Service</span></span>  
 <span data-ttu-id="5dd73-124">Puede utilizar un servicio SMTP local o un servidor o reenviador SMTP remoto para admitir la entrega por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5dd73-124">You can use a local SMTP service or a remote SMTP server or forwarder to support e-mail delivery.</span></span> <span data-ttu-id="5dd73-125">Si tiene acceso a un servidor SMTP remoto existente, debería plantearse utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-125">If you have access to an existing remote SMTP server, you should consider using it.</span></span> <span data-ttu-id="5dd73-126">Si no hay ningún servidor SMTP disponible o si después encuentra errores de entrega de informes que pueden atribuirse a errores en la conexión del equipo, debería pasar a utilizar un servicio SMTP local.</span><span class="sxs-lookup"><span data-stu-id="5dd73-126">If there is no SMTP server available or if you subsequently encounter report delivery errors that can be attributed to computer connection failures, you should switch to using a local SMTP service.</span></span> <span data-ttu-id="5dd73-127">Más adelante en este tema se proporcionan detalles sobre cómo configurar un servidor de informes para un servicio local o remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-127">Details about how to configure a report server for local or remote service are provided further on in this topic.</span></span>  
  
  
  
##  <a name="setting-configuration-options-for-e-mail-delivery"></a><a name="bkmk_setting_email_delivery"></a><span data-ttu-id="5dd73-128">Establecer opciones de configuración para la entrega por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5dd73-128">Setting Configuration Options for E-Mail Delivery</span></span>  
 <span data-ttu-id="5dd73-129">Para poder utilizar la entrega por correo electrónico del servidor de informes, debe establecer valores de configuración que proporcionen información sobre qué servidor SMTP se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="5dd73-129">Before you can use Report Server e-mail delivery, you must set configuration values that provide information about which SMTP server to use.</span></span>  
  
 <span data-ttu-id="5dd73-130">Para configurar un servidor de informes para la entrega por correo electrónico, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="5dd73-130">To configure a report server for e-mail delivery, do the following:</span></span>  
  
-   <span data-ttu-id="5dd73-131">Use el Administrador de configuración de Reporting Services si solo va a especificar un servidor SMTP y una cuenta de usuario que tenga permiso para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5dd73-131">Use the Reporting Services Configuration Manager if you are specifying just an SMTP server and a user account that has permission to send e-mail.</span></span> <span data-ttu-id="5dd73-132">Ésta es la configuración mínima necesaria para configurar la extensión de entrega por correo electrónico del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-132">These are the minimum settings that are required for configuring the Report Server e-mail delivery extension.</span></span> <span data-ttu-id="5dd73-133">Para obtener más información, consulte [configuración de correo electrónico: Configuration Manager &#40;modo nativo de SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) y [entrega por correo electrónico en Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5dd73-133">For more information, see [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) and [E-Mail Delivery in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="5dd73-134">(Opcionalmente) Utilice un procesador de texto para especificar valores adicionales en el archivo RSreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="5dd73-134">(Optionally) Use a text editor to specify additional settings in the RSreportserver.config file.</span></span> <span data-ttu-id="5dd73-135">Este archivo contiene toda la configuración para la distribución del correo electrónico del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-135">This file contains all of the configuration settings for Report Server e-mail delivery.</span></span> <span data-ttu-id="5dd73-136">Si utiliza un servidor SMTP adicional o limita la entrega de correo electrónico a hosts específicos, debe configurar opciones adicionales en estos archivos.</span><span class="sxs-lookup"><span data-stu-id="5dd73-136">Specifying additional settings in these files is required if you are using a local SMTP server or if you are restricting e-mail delivery to specific hosts.</span></span> <span data-ttu-id="5dd73-137">Para obtener más información sobre cómo buscar y modificar archivos de configuración, vea [modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) en libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5dd73-137">For more information about finding and modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dd73-138">Las opciones de correo electrónico del servidor de informes se basan en CDO.</span><span class="sxs-lookup"><span data-stu-id="5dd73-138">Report server e-mail settings are based on CDO.</span></span> <span data-ttu-id="5dd73-139">Si desea obtener más detalles acerca de opciones específicas, puede consultar la documentación de producción de CDO.</span><span class="sxs-lookup"><span data-stu-id="5dd73-139">If you want more detail about specific settings, you can refer to the CDO production documentation.</span></span>  
  

  
##  <a name="example-report-server-e-mail-configuration"></a><a name="bkmk_example_config_file"></a><span data-ttu-id="5dd73-140">Ejemplo de configuración de correo electrónico del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5dd73-140">Example Report Server E-Mail Configuration</span></span>  
 <span data-ttu-id="5dd73-141">El ejemplo siguiente muestra las opciones de configuración del archivo RSreportserver.config para un servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-141">The following example illustrates the settings in the RSreportserver.config file for a remote SMTP server.</span></span> <span data-ttu-id="5dd73-142">Para leer en los Libros en pantalla deformación acerca de las descripciones de las opciones y los valores válidos, vea [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlen los Libros en pantalla dee or the CDO product documentation.</span><span class="sxs-lookup"><span data-stu-id="5dd73-142">To read about the setting descriptions and valid values, see [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or the CDO product documentation.</span></span>  
  
```  
<RSEmailDPConfiguration>  
     <SMTPServer>mySMTPServer.Adventure-Works.com</SMTPServer>  
     <SMTPServerPort></SMTPServerPort>  
     <SMTPAccountName></SMTPAccountName>  
     <SMTPConnectionTimeout></SMTPConnectionTimeout>  
     <SMTPServerPickupDirectory></SMTPServerPickupDirectory>  
     <SMTPUseSSL></SMTPUseSSL>  
     <SendUsing>2</SendUsing>  
     <SMTPAuthenticate></SMTPAuthenticate>  
     <From>my-rs-email-account@Adventure-Works.com</From>  
     <EmbeddedRenderFormats>  
          <RenderingExtension>MHTML</RenderingExtension>  
     </EmbeddedRenderFormats>  
     <PrivilegedUserRenderFormats></PrivilegedUserRenderFormats>  
     <ExcludedRenderFormats>  
          <RenderingExtension>HTMLOWC</RenderingExtension>  
          <RenderingExtension>NULL</RenderingExtension>  
     </ExcludedRenderFormats>  
     <SendEmailToUserAlias>True</SendEmailToUserAlias>  
     <DefaultHostName></DefaultHostName>  
     <PermittedHosts>  
          <HostName>Adventure-Works.com</HostName>  
          <HostName>hotmail.com</HostName>  
     </PermittedHosts>  
</RSEmailDPConfiguration>  
```  
  

  
##  <a name="configuration-options-for-setting-the-to-field-in-a-message"></a><a name="bkmk_setting_TO_field"></a><span data-ttu-id="5dd73-143">Opciones de configuración para establecer el campo para: en un mensaje</span><span class="sxs-lookup"><span data-stu-id="5dd73-143">Configuration Options for Setting the To: Field in a Message</span></span>  
 <span data-ttu-id="5dd73-144">Las suscripciones definidas por el usuario que se crean según los permisos concedidos por la tarea **administrar suscripciones individuales** contienen un nombre de usuario preconfigurado que se basa en la cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="5dd73-144">User-defined subscriptions that are created according to the permissions granted by the **Manage individual subscriptions** task contain a pre-set user name that is based on the domain user account.</span></span> <span data-ttu-id="5dd73-145">Cuando el usuario crea la suscripción, el nombre del destinatario del campo **Para:** se rellena automáticamente a partir de la cuenta de usuario de dominio de la persona que está creando la suscripción.</span><span class="sxs-lookup"><span data-stu-id="5dd73-145">When the user creates the subscription, the recipient name in the **To:** field is self-addressed using the domain user account of the person creating the subscription.</span></span>  
  
 <span data-ttu-id="5dd73-146">Si está utilizando un servidor SMTP o reenviador que emplee cuentas de correo electrónico distintas a la cuenta de usuario de dominio, la entrega del informe generará un error cuando el servidor SMTP intente entregar el informe al usuario.</span><span class="sxs-lookup"><span data-stu-id="5dd73-146">If you are using an SMTP server or forwarder that uses e-mail accounts that are different from the domain user account, the report delivery will fail when the SMTP server tries to deliver the report to that user.</span></span>  
  
 <span data-ttu-id="5dd73-147">Para solucionar este problema, puede modificar la configuración para permitir a los usuarios escribir un nombre en el campo **Para:** :</span><span class="sxs-lookup"><span data-stu-id="5dd73-147">To workaround this issue, you can modify configuration settings that allow users to enter a name in the **To:** field:</span></span>  
  
1.  <span data-ttu-id="5dd73-148">Abra RSReportServer.config en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-148">Open RSReportServer.config with a text editor.</span></span>  
  
2.  <span data-ttu-id="5dd73-149">Establezca `SendEmailToUserAlias` en `False`.</span><span class="sxs-lookup"><span data-stu-id="5dd73-149">Set `SendEmailToUserAlias` to `False`.</span></span>  
  
3.  <span data-ttu-id="5dd73-150">Establezca `DefaultHostName` en el nombre del Sistema de nombres de dominio (DNS) o la dirección IP del servidor SMTP o reenviador.</span><span class="sxs-lookup"><span data-stu-id="5dd73-150">Set `DefaultHostName` to the Domain Name System (DNS) name or IP address of the SMTP server or forwarder.</span></span>  
  
4.  <span data-ttu-id="5dd73-151">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-151">Save the file.</span></span>  
  
  
  
##  <a name="configuration-options-for-remote-smtp-service"></a><a name="bkmk_options_remote_SMTP"></a><span data-ttu-id="5dd73-152">Opciones de configuración para el servicio SMTP remoto</span><span class="sxs-lookup"><span data-stu-id="5dd73-152">Configuration Options for Remote SMTP Service</span></span>  
 <span data-ttu-id="5dd73-153">La conexión entre el servidor de informes y un servidor o reenviador SMTP viene determinada por las opciones de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="5dd73-153">The connection between the report server and an SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="5dd73-154">`SendUsing` especifica un método para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-154">`SendUsing` specifies a method for sending messages.</span></span> <span data-ttu-id="5dd73-155">Se puede elegir entre un servicio SMTP de red o un directorio de recogida del servicio SMTP local.</span><span class="sxs-lookup"><span data-stu-id="5dd73-155">You can choose between a network SMTP service or a local SMTP service pickup directory.</span></span> <span data-ttu-id="5dd73-156">Para utilizar un servicio SMTP remoto, este valor debe establecerse en **2** en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="5dd73-156">To use a remote SMTP service, this value must be set to **2** in the RSReportServer.config file.</span></span>  
  
-   <span data-ttu-id="5dd73-157">`SMTPServer` especifica el servidor o reenviador SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-157">`SMTPServer` specifies the remote SMTP server or forwarder.</span></span> <span data-ttu-id="5dd73-158">Se trata de un valor necesario si utiliza un servidor o reenviador SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-158">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
-   <span data-ttu-id="5dd73-159">`From` establece el valor que se muestra en la línea **De:** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5dd73-159">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="5dd73-160">Se trata de un valor necesario si utiliza un servidor o reenviador SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-160">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
 <span data-ttu-id="5dd73-161">Entre los demás valores que se utilizan para un servicio SMTP remoto se incluyen los siguientes (tenga en cuenta que no es necesario especificarlos a menos que desee reemplazar los valores predeterminados).</span><span class="sxs-lookup"><span data-stu-id="5dd73-161">Other values that are used for remote SMTP service include the following (note that you do not need to specify these values unless you want to override the default values).</span></span>  
  
-   <span data-ttu-id="5dd73-162">**SMTPServerPort** se configura para el puerto 25.</span><span class="sxs-lookup"><span data-stu-id="5dd73-162">**SMTPServerPort** is configured for port 25.</span></span>  
  
-   <span data-ttu-id="5dd73-163">**SMTPAuthenticate** especifica cómo se conecta el servidor de informes al servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-163">**SMTPAuthenticate** specifies how the report server connects to the remote SMTP server.</span></span> <span data-ttu-id="5dd73-164">El valor predeterminado es 0 (o sin autenticación).</span><span class="sxs-lookup"><span data-stu-id="5dd73-164">The default value is 0 (or no authentication).</span></span> <span data-ttu-id="5dd73-165">En tal caso, la conexión se realiza a través de un acceso anónimo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-165">In this case, the connection is made through Anonymous access.</span></span> <span data-ttu-id="5dd73-166">En función de su configuración de dominio, es posible que el servidor de informes y el servidor SMTP tengan que ser miembros del mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="5dd73-166">Depending on your domain configuration, the report server and the SMTP server may need to be members of the same domain.</span></span>  
  
     <span data-ttu-id="5dd73-167">Para enviar correo electrónico a listas de distribución restringidas (por ejemplo, listas de distribución que acepten mensajes entrantes solo de cuentas autenticadas), establezca **SMTPAuthenticate** en **2**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-167">To send e-mail to restricted distribution lists (for example, distribution lists that accept incoming messages only from authenticated accounts), set **SMTPAuthenticate** to **2**.</span></span>  
  

  
##  <a name="configuration-options-for-local-smtp-service"></a><a name="bkmk_options_local_SMTP"></a><span data-ttu-id="5dd73-168">Opciones de configuración para el servicio SMTP local</span><span class="sxs-lookup"><span data-stu-id="5dd73-168">Configuration Options for Local SMTP Service</span></span>  
 <span data-ttu-id="5dd73-169">Configurar un servicio SMTP local resulta útil si se está probando o solucionando problemas de la entrega por correo electrónico del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-169">Configuring a local SMTP service is useful if you are testing or troubleshooting report server e-mail delivery.</span></span> <span data-ttu-id="5dd73-170">El servicio SMTP local no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5dd73-170">The local SMTP service is not enabled by default.</span></span> <span data-ttu-id="5dd73-171">Para obtener instrucciones sobre cómo habilitarlo, vea [configurar un servidor de informes para la entrega de correo electrónico (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) y [configuración de correo electrónico: Configuration Manager &#40;modo nativo de SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5dd73-171">For instructions on how to enable it, see [Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="5dd73-172">La conexión entre el servidor de informes y un servidor o reenviador SMTP local viene determinada por las opciones de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="5dd73-172">The connection between the report server and a local SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="5dd73-173">`SendUsing` se establece en **1**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-173">`SendUsing` is set to **1**.</span></span>  
  
-   <span data-ttu-id="5dd73-174">**SMTPServerPickupDirectory** se establece en una carpeta de la unidad local.</span><span class="sxs-lookup"><span data-stu-id="5dd73-174">**SMTPServerPickupDirectory** is set to a folder on the local drive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5dd73-175">Asegúrese de que no establece `SMTPServer` si usa un servidor SMTP local.</span><span class="sxs-lookup"><span data-stu-id="5dd73-175">Be sure that you do not set `SMTPServer` if you are using a local SMTP server.</span></span>  
  
-   <span data-ttu-id="5dd73-176">`From` establece el valor que se muestra en la línea **De:** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5dd73-176">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="5dd73-177">Este valor es necesario.</span><span class="sxs-lookup"><span data-stu-id="5dd73-177">This value is required.</span></span>  
  
 
  
##  <a name="to-configure-report-server-e-mail-using-the-reporting-services-configuration-manager"></a><a name="bkmk_use_configuration_manager"></a><span data-ttu-id="5dd73-178">Para configurar el correo electrónico del servidor de informes mediante el Administrador de configuración de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5dd73-178">To configure report server e-mail using the Reporting Services Configuration Manager</span></span>  
  
1.  <span data-ttu-id="5dd73-179">Compruebe que el servicio Servidor de informes de Windows disponga de permisos `Send As` para el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-179">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="5dd73-180">Inicie el Administrador de configuración de Reporting Services y conéctese a la instancia del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5dd73-180">Start the Reporting Services Configuration Manager and connect to the report server instance.</span></span>  
  
3.  <span data-ttu-id="5dd73-181">En la página Configuración de correo electrónico, escriba el nombre del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-181">On the Email Settings page, enter the name of the SMTP server.</span></span> <span data-ttu-id="5dd73-182">Este valor puede ser una dirección IP, un nombre UNC de un equipo de la intranet corporativa o un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-182">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
4.  <span data-ttu-id="5dd73-183">En **Dirección del remitente**, escriba el nombre de una cuenta que tenga permiso para enviar correo electrónico desde el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-183">In **Sender Address**, enter the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
5.  <span data-ttu-id="5dd73-184">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-184">Click **Apply**.</span></span>  
  

  
##  <a name="to-configure-a-remote-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_remote_SMTP"></a><span data-ttu-id="5dd73-185">Para configurar un servicio SMTP remoto para el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5dd73-185">To configure a remote SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="5dd73-186">Compruebe que el servicio Servidor de informes de Windows disponga de permisos `Send As` para el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-186">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="5dd73-187">Abra el archivo RSReportServer.config en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-187">Open the RSReportServer.config file in a text editor.</span></span>  
  
3.  <span data-ttu-id="5dd73-188">Compruebe que <`UrlRoot`> está establecido en la dirección URL del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-188">Verify that <`UrlRoot`> is set to the report server URL address.</span></span> <span data-ttu-id="5dd73-189">Este valor se establece al configurar el servidor de informes y debe mostrar la dirección.</span><span class="sxs-lookup"><span data-stu-id="5dd73-189">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="5dd73-190">Si no es así, escriba la dirección URL del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-190">If it is not set, type the report server URL address.</span></span>  
  
4.  <span data-ttu-id="5dd73-191">En la sección entrega, busque <`ReportServerEmail`>.</span><span class="sxs-lookup"><span data-stu-id="5dd73-191">In the Delivery section, find <`ReportServerEmail`>.</span></span>  
  
5.  <span data-ttu-id="5dd73-192">En <`SMTPServer`>, escriba el nombre del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-192">In <`SMTPServer`>, type the name of the SMTP server.</span></span> <span data-ttu-id="5dd73-193">Este valor puede ser una dirección IP, un nombre UNC de un equipo de la intranet corporativa o un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-193">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
6.  <span data-ttu-id="5dd73-194">Compruebe que <`SendUsing`> está establecido en 2.</span><span class="sxs-lookup"><span data-stu-id="5dd73-194">Verify that <`SendUsing`> is set to 2.</span></span> <span data-ttu-id="5dd73-195">Si se especifica otro valor, el servidor de informes no se habrá configurado para utilizar un servicio SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-195">If it is set another value, the report server is not configured to use a remote SMTP service.</span></span>  
  
7.  <span data-ttu-id="5dd73-196">En <`From`>, escriba el nombre de una cuenta que tenga permiso para enviar correo electrónico desde el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-196">In <`From`>, type the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
8.  <span data-ttu-id="5dd73-197">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-197">Save the file.</span></span>  
  
     <span data-ttu-id="5dd73-198">El servidor de informes utilizará la nueva configuración de forma automática, por lo que no necesita reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5dd73-198">The report server will use the new settings automatically; you do not need to restart the service.</span></span> <span data-ttu-id="5dd73-199">Puede especificar valores adicionales para SMTP con el fin de configurar cómo se utilizará el servidor para la entrega por correo electrónico del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-199">You can specify additional SMTP settings to further configure how the SMTP server is used for report server e-mail delivery.</span></span> <span data-ttu-id="5dd73-200">Para más en los Libros en pantalla deformación, consulte [Configuren los Libros en pantalla deg a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) y [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlen los Libros en pantalla dee.</span><span class="sxs-lookup"><span data-stu-id="5dd73-200">For more information, see [Configuring a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  

  
##  <a name="to-configure-a-local-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_local_SMTP"></a><span data-ttu-id="5dd73-201">Para configurar un servicio SMTP local para el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5dd73-201">To configure a local SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="5dd73-202">En el Panel de control, haga clic en **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-202">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="5dd73-203">Haga clic en **Agregar o quitar componentes de Windows** para iniciar el Asistente para componentes de Windows.</span><span class="sxs-lookup"><span data-stu-id="5dd73-203">Click **Add/Remove Windows Components** to start the Windows Component Wizard.</span></span>  
  
3.  <span data-ttu-id="5dd73-204">Seleccione **Servidor de aplicaciones** y haga clic en **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-204">Select **Application Server** and click **Details**.</span></span>  
  
4.  <span data-ttu-id="5dd73-205">Seleccione **Internet Information Services (IIS)** y haga clic en **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-205">Select **Internet Information Services (IIS)** and click **Details**.</span></span>  
  
5.  <span data-ttu-id="5dd73-206">Active la casilla **Servicio SMTP** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-206">Select the **SMTP Service** checkbox and click **OK**.</span></span>  
  
6.  <span data-ttu-id="5dd73-207">En el Asistente para componentes de Windows, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5dd73-207">On the Windows Component Wizard, click **Next**.</span></span> <span data-ttu-id="5dd73-208">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="5dd73-208">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="5dd73-209">Compruebe que el servicio esté ejecutándose en la consola **Servicios** .</span><span class="sxs-lookup"><span data-stu-id="5dd73-209">Verify that the service is running in the **Services** console.</span></span>  
  
8.  <span data-ttu-id="5dd73-210">Abra el archivo de **RSReportServer.config** en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5dd73-210">Open the **RSReportServer.config** file in a text editor.</span></span>  
  
9. <span data-ttu-id="5dd73-211">Compruebe que `<UrlRoot>` se haya establecido en la dirección URL del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-211">Verify that `<UrlRoot>` is set to the report server URL address.</span></span> <span data-ttu-id="5dd73-212">Este valor se establece al configurar el servidor de informes y debe mostrar la dirección.</span><span class="sxs-lookup"><span data-stu-id="5dd73-212">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="5dd73-213">Si no es así, escriba la dirección URL del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5dd73-213">If it is not set, type the report server URL address.</span></span>  
  
10. <span data-ttu-id="5dd73-214">En la sección Entrega, busque `<ReportServerEmail>.`.</span><span class="sxs-lookup"><span data-stu-id="5dd73-214">In the Delivery section, find `<ReportServerEmail>.`</span></span>  
  
11. <span data-ttu-id="5dd73-215">En `<SMTPServer>`, borre todos los valores de esta configuración, pero no elimine las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="5dd73-215">In `<SMTPServer>`, clear any values for this setting, but do not delete the tags.</span></span>  
  
12. <span data-ttu-id="5dd73-216">Establezca `<SendUsing>` en 1.</span><span class="sxs-lookup"><span data-stu-id="5dd73-216">Set `<SendUsing>` to 1.</span></span> <span data-ttu-id="5dd73-217">Si se especifica otro valor, el servidor de informes no se habrá configurado para utilizar un servicio SMTP local.</span><span class="sxs-lookup"><span data-stu-id="5dd73-217">If it is set another value, the report server is not configured to use a local SMTP service.</span></span>  
  
13. <span data-ttu-id="5dd73-218">Establezca `<SMTPServerPickupDirectory>` en una carpeta de la unidad local.</span><span class="sxs-lookup"><span data-stu-id="5dd73-218">Set `<SMTPServerPickupDirectory>` to a folder on the local drive.</span></span>  
  
14. <span data-ttu-id="5dd73-219">Establezca `<From>` en una cuenta con permiso para enviar correo electrónico desde el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5dd73-219">Set `<From>` to an account that has permission to send e-mail from the SMTP server.</span></span>  
  
15. <span data-ttu-id="5dd73-220">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="5dd73-220">Save the file.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="5dd73-221">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5dd73-221">See Also</span></span>  
 [<span data-ttu-id="5dd73-222">Administrador de configuración de Reporting Services &#40;modo nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="5dd73-222">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
