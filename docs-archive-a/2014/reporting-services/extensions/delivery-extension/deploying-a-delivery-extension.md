---
title: Implementar una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: 4436ce48-397d-42c7-9b5d-2a267e2a1b2c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4a4e33266c8d3a27ce2a4ab5f568bdee349720f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678085"
---
# <a name="deploying-a-delivery-extension"></a><span data-ttu-id="b8953-102">Implementar una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="b8953-102">Deploying a Delivery Extension</span></span>
  <span data-ttu-id="b8953-103">Las extensiones de entrega proporcionan su información de configuración en forma de archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="b8953-103">Delivery extensions supply their configuration information in the form of an XML configuration file.</span></span> <span data-ttu-id="b8953-104">El archivo XML cumple el esquema XML definido para las extensiones de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-104">The XML file conforms to the XML schema defined for delivery extensions.</span></span> <span data-ttu-id="b8953-105">Las extensiones de entrega proporcionan la infraestructura para establecer y modificar el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8953-105">Delivery extensions provide infrastructure for setting and modifying the configuration file.</span></span>  
  
 <span data-ttu-id="b8953-106">Si una extensión de entrega se reemplaza o actualiza, todas las suscripciones que hacen referencia a la misma siguen siendo válidas.</span><span class="sxs-lookup"><span data-stu-id="b8953-106">If a delivery extension is replaced or upgraded, all subscriptions that reference the delivery extension remain valid.</span></span>  
  
 <span data-ttu-id="b8953-107">Una vez escrita y compilada la extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en una biblioteca de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], debe copiar la extensión en el directorio adecuado y agregar una entrada al archivo de configuración de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] correcto de modo que el servidor de informes pueda localizarla.</span><span class="sxs-lookup"><span data-stu-id="b8953-107">After you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you must copy the extension to the appropriate directory and add an entry to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration file so the report server can locate it.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="b8953-108">Elemento de extension de archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b8953-108">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="b8953-109">Las extensiones de entrega que implemente para el servidor de informes tienen que escribirse como elementos `Extension` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8953-109">Delivery extensions that you deploy to the report server need to be entered as `Extension` elements in the configuration file.</span></span> <span data-ttu-id="b8953-110">El archivo de configuración para el servidor de informes es RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b8953-110">The configuration file for the report server is RSReportServer.config.</span></span>  
  
 <span data-ttu-id="b8953-111">En la tabla siguiente se describen los atributos para el elemento `Extension` correspondiente a las extensiones de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-111">The following table describes the attributes for the `Extension` element for delivery extensions.</span></span>  
  
|<span data-ttu-id="b8953-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b8953-112">Attribute</span></span>|<span data-ttu-id="b8953-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8953-113">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="b8953-114">Un nombre único para la extensión (por ejemplo, "Correo electrónico del servidor de informes", para la extensión de entrega por correo electrónico, o "Recurso compartido de archivos del servidor de informes", para la extensión de entrega en recursos compartidos de archivos).</span><span class="sxs-lookup"><span data-stu-id="b8953-114">A unique name for the extension (for example, "Report Server E-Mail" for the e-mail delivery extension or "Report Server FileShare" for the file share delivery extension).</span></span> <span data-ttu-id="b8953-115">La longitud máxima para el atributo `Name` es de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8953-115">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="b8953-116">El nombre debe ser único entre todas las entradas en el elemento `Extension` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8953-116">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="b8953-117">Si hay un nombre duplicado, el servidor de informes devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="b8953-117">If a duplicate name is present, the report server returns an error.</span></span>|  
|`Type`|<span data-ttu-id="b8953-118">Lista separada por comas que incluye el espacio de nombres completo junto con el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b8953-118">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="b8953-119">El valor `false` indica que la extensión de entrega no debería estar visible en las interfaces de usuario.</span><span class="sxs-lookup"><span data-stu-id="b8953-119">A value of `false` indicates that the delivery extension should not be visible in user interfaces.</span></span> <span data-ttu-id="b8953-120">Si el atributo no está incluido, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b8953-120">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="b8953-121">Para más información sobre el archivo RSReportServer.config, vea [Archivos de configuración de Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="b8953-121">For more information about the RSReportServer.config file, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="deploying-the-extension-to-the-report-server"></a><span data-ttu-id="b8953-122">Implementar la extensión para el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="b8953-122">Deploying the Extension to the Report Server</span></span>  
 <span data-ttu-id="b8953-123">El servidor de informes utiliza las extensiones de entrega para procesar y entregar notificaciones o informes.</span><span class="sxs-lookup"><span data-stu-id="b8953-123">The report server uses delivery extensions for processing and delivering notifications or reports.</span></span> <span data-ttu-id="b8953-124">Debería implementar el ensamblado de extensión de entrega para el servidor de informes como un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="b8953-124">You should deploy your delivery extension assembly to the report server as a private assembly.</span></span> <span data-ttu-id="b8953-125">También tiene que realizar una entrada en el archivo de configuración del servidor de informes, RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b8953-125">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-a-report-server"></a><span data-ttu-id="b8953-126">Para implementar un ensamblado de extensión de entrega en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="b8953-126">To deploy a deliver extension assembly to a report server</span></span>  
  
1.  <span data-ttu-id="b8953-127">Copie el ensamblado desde la ubicación provisional al directorio bin del servidor de informes en el que desea utilizar la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-127">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the delivery extension.</span></span> <span data-ttu-id="b8953-128">La ubicación predeterminada del directorio bin del servidor de informes es%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="b8953-128">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b8953-129">Si está intentando sobrescribir un ensamblado de extensión de entrega existente, primero debe detener el servicio del servidor de informes antes de copiar el ensamblado actualizado.</span><span class="sxs-lookup"><span data-stu-id="b8953-129">If you are attempting to overwrite an existing delivery extension assembly, you must first stop the Report Server service before copying the updated assembly.</span></span> <span data-ttu-id="b8953-130">Reinicie el servicio después de que el ensamblado termine la copia.</span><span class="sxs-lookup"><span data-stu-id="b8953-130">Restart your service after the assembly is through copying.</span></span>  
  
2.  <span data-ttu-id="b8953-131">Una vez copiado el archivo de ensamblado, abra el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b8953-131">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="b8953-132">El archivo de RSReportServer.config se encuentra en la carpeta% archivos de programa%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Directorio \Reporting Services\ReportServer</span><span class="sxs-lookup"><span data-stu-id="b8953-132">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="b8953-133">Tiene que realizar una entrada en el archivo de configuración para el archivo de ensamblado de extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-133">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="b8953-134">Puede abrir el archivo de configuración con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un editor de texto simple, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="b8953-134">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="b8953-135">Busque el elemento `Delivery` en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b8953-135">Locate the `Delivery` element in the RSReportServer.config file.</span></span> <span data-ttu-id="b8953-136">En la ubicación siguiente se debería realizar una extensión de entrega creada recientemente:</span><span class="sxs-lookup"><span data-stu-id="b8953-136">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Delivery>  
          <Your extension configuration information goes here>  
       </Delivery>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="b8953-137">Agregue una entrada para la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-137">Add an entry for your delivery extension.</span></span> <span data-ttu-id="b8953-138">La entrada debería incluir un elemento `Extension` con valores para `Name` y `Type`, y podría ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8953-138">Your entry should include an `Extension` element with values for `Name` and `Type`, and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="b8953-139">El valor de `Name` es el nombre único de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-139">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="b8953-140">El valor de `Type` es una lista separada por comas que incluye una entrada para el espacio de nombres completo de la clase que implementa la interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>, seguido del nombre del ensamblado (sin incluir la extensión de archivo .dll).</span><span class="sxs-lookup"><span data-stu-id="b8953-140">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="b8953-141">De forma predeterminada, las extensiones de entrega están visibles.</span><span class="sxs-lookup"><span data-stu-id="b8953-141">By default, delivery extensions are visible.</span></span> <span data-ttu-id="b8953-142">Para ocultar una extensión de las interfaces de usuario, como el Administrador de informes, agregue un atributo `Visible` al elemento `Extension` y establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="b8953-142">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="b8953-143">Finalmente, agregue un grupo de código para el ensamblado personalizado que conceda el permiso  `FullTrust` para la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-143">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="b8953-144">Para ello, agregue el grupo de código al archivo rssrvpolicy.config que se encuentra de forma predeterminada en%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="b8953-144">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="b8953-145">El grupo de código podría tener la apariencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8953-145">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="b8953-146">La pertenencia de dirección URL es solo una de las muchas condiciones de pertenencia que podría elegir para la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-146">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="b8953-147">Para más información sobre la seguridad de acceso del código de [!INCLUDE[ssRS](../../../includes/ssrs.md)], vea [Desarrollo seguro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b8953-147">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see.[Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="deploying-the-extension-to-report-manager"></a><span data-ttu-id="b8953-148">Implementar la extensión en el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="b8953-148">Deploying the Extension to Report Manager</span></span>  
 <span data-ttu-id="b8953-149">Si la extensión de entrega implementa la interfaz <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, se puede utilizar con la página de Suscripción del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="b8953-149">If your delivery extension implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, your delivery extension can be used with the Report Manager Subscription page.</span></span> <span data-ttu-id="b8953-150">Si desea que la interfaz de usuario de la suscripción esté disponible, necesita implementar la extensión para el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="b8953-150">To make the subscription user interface available, you need to deploy your extension to Report Manager.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-report-manager"></a><span data-ttu-id="b8953-151">Para implementar un ensamblado de extensión de entrega en el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="b8953-151">To deploy a deliver extension assembly to Report Manager</span></span>  
  
1.  <span data-ttu-id="b8953-152">Copie el ensamblado desde la ubicación de almacenamiento provisional al directorio bin del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="b8953-152">Copy your assembly from your staging location to the bin directory of Report Manager.</span></span> <span data-ttu-id="b8953-153">La ubicación predeterminada del directorio Administrador de informes bin es%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportManager\bin.</span><span class="sxs-lookup"><span data-stu-id="b8953-153">The default location of the Report Manager bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager\bin.</span></span>  
  
2.  <span data-ttu-id="b8953-154">Una vez copiado el archivo de ensamblado, abra el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b8953-154">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="b8953-155">El archivo de RSReportServer.config se encuentra en la carpeta% archivos de programa%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Directorio \Reporting Services\ReportServer</span><span class="sxs-lookup"><span data-stu-id="b8953-155">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="b8953-156">Tiene que realizar una entrada en el archivo de configuración para el archivo de ensamblado de extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-156">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="b8953-157">Puede abrir el archivo de configuración con Visual Studio .NET o con un procesador de texto sencillo como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="b8953-157">You can open the configuration file with Visual Studio .NET or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="b8953-158">Busque el elemento `DeliveryUI` en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b8953-158">Locate the `DeliveryUI` element in the RSReportServer.config file.</span></span> <span data-ttu-id="b8953-159">En la ubicación siguiente se debería realizar una extensión de entrega creada recientemente:</span><span class="sxs-lookup"><span data-stu-id="b8953-159">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <DeliveryUI>  
          <Your extension configuration information goes here>  
       </DeliveryUI>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="b8953-160">Agregue una entrada para la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-160">Add an entry for your delivery extension.</span></span> <span data-ttu-id="b8953-161">La entrada debe incluir un `Extension` elemento con valores para `Name` y `Type` y podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8953-161">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryUIExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="b8953-162">El valor de `Name` es el nombre único de la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-162">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="b8953-163">El valor de `Type` es una lista separada por comas que incluye una entrada para el espacio de nombres completo de la clase que implementa la interfaz <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, seguido del nombre del ensamblado (sin incluir la extensión de archivo .dll).</span><span class="sxs-lookup"><span data-stu-id="b8953-163">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, followed by the name of your assembly (not including the .dll file extension).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b8953-164">El valor del atributo `Name` debe ser idéntico para el servidor de informes y para las entradas de los archivos de configuración del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="b8953-164">The value of the `Name` attribute must be identical for both the Report Server and Report Manager configuration file entries.</span></span> <span data-ttu-id="b8953-165">Si no son idénticos, la configuración del servidor no es válida.</span><span class="sxs-lookup"><span data-stu-id="b8953-165">If they are not identical, your server configuration is not valid.</span></span>  
  
     <span data-ttu-id="b8953-166">Finalmente, agregue un grupo de código para el ensamblado personalizado que conceda el permiso  `FullTrust` para la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-166">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="b8953-167">Para ello, agregue el grupo de código al archivo RSmgrpolicy.config que se encuentra de forma predeterminada en C:\Archivos de Programa\microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="b8953-167">You do this by adding the code group to the RSmgrpolicy.config file located by default in C:\Program Files\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager.</span></span> <span data-ttu-id="b8953-168">El grupo de código podría tener la apariencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8953-168">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery UI extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportManager\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="b8953-169">La pertenencia de dirección URL es solo una de las muchas condiciones de pertenencia que podría elegir para la extensión de entrega.</span><span class="sxs-lookup"><span data-stu-id="b8953-169">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="b8953-170">Para obtener más información sobre la seguridad de acceso del código en [!INCLUDE[ssRS](../../../includes/ssrs.md)] , vea [&#40;de desarrollo seguro Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="b8953-170">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="b8953-171">Comprobación de la implementación</span><span class="sxs-lookup"><span data-stu-id="b8953-171">Verifying the Deployment</span></span>  
 <span data-ttu-id="b8953-172">Puede comprobar si la extensión de entrega se implementó correctamente en el servidor de informes utilizando el método <xref:ReportService2010.ReportingService2010.ListExtensions%2A> del servicio web.</span><span class="sxs-lookup"><span data-stu-id="b8953-172">You can verify whether your delivery extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="b8953-173">También puede abrir el Administrador de informes y comprobar que la extensión está incluida en la lista de extensiones de entrega disponibles para una suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8953-173">You can also open Report Manager and verify that your extension is included in the list of available delivery extensions for a subscription.</span></span> <span data-ttu-id="b8953-174">Para obtener más información sobre Administrador de informes y suscripciones, consulte [suscripciones y entrega &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b8953-174">For more information about Report Manager and subscriptions, see [Subscriptions and Delivery &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8953-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8953-175">See Also</span></span>  
 <span data-ttu-id="b8953-176">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="b8953-176">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="b8953-177">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b8953-177">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
