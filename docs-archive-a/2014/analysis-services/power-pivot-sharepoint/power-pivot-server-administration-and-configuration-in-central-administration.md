---
title: Administración y configuración del servidor de PowerPivot en administración central | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2cdbfdc5-45a9-4000-a03d-318cc7ac8fe9
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce5c06eda86fb8e8ac03803513c8767988a728eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673318"
---
# <a name="powerpivot-server-administration-and-configuration-in-central-administration"></a><span data-ttu-id="90b7b-102">Administración y configuración del servidor PowerPivot en Administración central</span><span class="sxs-lookup"><span data-stu-id="90b7b-102">PowerPivot Server Administration and Configuration in Central Administration</span></span>
  <span data-ttu-id="90b7b-103">Los administradores de aplicaciones de servicios de SharePoint llevan a cabo la administración y configuración de servidores PowerPivot mediante Administración central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="90b7b-103">PowerPivot server administration and configuration is performed by SharePoint service application administrators, using SharePoint Central Administration.</span></span>  
  
 <span data-ttu-id="90b7b-104">Para poder utilizar PowerPivot para SharePoint, debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="90b7b-104">PowerPivot for SharePoint must be configured before it can be used.</span></span> <span data-ttu-id="90b7b-105">Después de instalar PowerPivot para SharePoint mediante el programa de instalación de SQL Server, puede configurarlo con cualquiera de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="90b7b-105">After you install PowerPivot for SharePoint using SQL Server Setup, you can configure it using any of the following approaches:</span></span>  
  
-   <span data-ttu-id="90b7b-106">Herramienta de configuración de PowerPivot o herramienta de configuración de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="90b7b-106">PowerPivot Configuration Tool or PowerPivot for SharePoint 2013 Configuration tool</span></span>  
  
-   <span data-ttu-id="90b7b-107">Administración central de SharePoint</span><span class="sxs-lookup"><span data-stu-id="90b7b-107">SharePoint Central Administration</span></span>  
  
-   <span data-ttu-id="90b7b-108">Cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="90b7b-108">PowerShell cmdlets</span></span>  
  
 <span data-ttu-id="90b7b-109">Los tres métodos proporcionan un servidor totalmente configurado.</span><span class="sxs-lookup"><span data-stu-id="90b7b-109">All three approaches deliver a fully configured server.</span></span>  
  
 <span data-ttu-id="90b7b-110">Esta sección incluye las tareas para configurar el software utilizando Administración central.</span><span class="sxs-lookup"><span data-stu-id="90b7b-110">This section includes tasks for configuring the software using Central Administration.</span></span> <span data-ttu-id="90b7b-111">Como mínimo, debe realizar las tres tareas de configuración necesarias indicadas en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="90b7b-111">At a minimum, you must perform all three of the required configuration tasks noted in the list below.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90b7b-112">En el caso de SharePoint 2010, debe instalarse SharePoint 2010 Service Pack 1 (SP1) antes de configurar PowerPivot para SharePoint o una granja de SharePoint que use un servidor de bases de datos de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90b7b-112">For SharePoint 2010, SharePoint 2010 Service Pack 1 (SP1) must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="90b7b-113">Si no ha instalado todavía el Service Pack, hágalo ahora antes de empezar la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="90b7b-113">If you have not yet installed the service pack, do so now before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-central-administration"></a><span data-ttu-id="90b7b-114">Ventajas de configurar PowerPivot para SharePoint utilizando Administración central</span><span class="sxs-lookup"><span data-stu-id="90b7b-114">Benefits of Configuring PowerPivot for SharePoint Using Central Administration</span></span>  
 <span data-ttu-id="90b7b-115">Administración central de SharePoint es la aplicación administrativa de una granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="90b7b-115">SharePoint Central Administration is the administrative application of a SharePoint farm.</span></span> <span data-ttu-id="90b7b-116">Si es administrador de la granja, quizá prefiera utilizar una herramienta familiar al agregar una instancia de PowerPivot para SharePoint a la granja.</span><span class="sxs-lookup"><span data-stu-id="90b7b-116">If you are farm administrator, you might prefer to use a familiar tool when adding a PowerPivot for SharePoint instance to your farm.</span></span>  
  
 <span data-ttu-id="90b7b-117">A diferencia de las Herramientas de configuración de PowerPivot o de los cmdlets de PowerShell, Administración central proporciona las páginas que especifican completamente todas las opciones que puede establecer al configurar una aplicación o un servidor.</span><span class="sxs-lookup"><span data-stu-id="90b7b-117">In contrast with the PowerPivot Configuration Tools or PowerShell cmdlets, Central Administration provides pages that fully specify all of the options you might set when configuring an application or server.</span></span> <span data-ttu-id="90b7b-118">Otros métodos condensan el flujo de trabajo de configuración en un menor número de pasos, o requieren conocimientos previos de cómo configurar un servidor de SharePoint mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90b7b-118">Other approaches either condense the configuration workflow into a fewer number of steps, or require prior knowledge of how to configure a SharePoint server using PowerShell.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="90b7b-119">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="90b7b-119">Related Content</span></span>  
 [<span data-ttu-id="90b7b-120">Configuración de PowerPivot mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90b7b-120">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
  
 [<span data-ttu-id="90b7b-121">Herramientas de configuración de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="90b7b-121">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="90b7b-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="90b7b-122">Related Tasks</span></span>  
  
|<span data-ttu-id="90b7b-123">Vínculo</span><span class="sxs-lookup"><span data-stu-id="90b7b-123">Link</span></span>|<span data-ttu-id="90b7b-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="90b7b-124">Type</span></span>|<span data-ttu-id="90b7b-125">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="90b7b-125">Task Description</span></span>|  
|----------|----------|----------------------|  
|[<span data-ttu-id="90b7b-126">Implementar las soluciones de PowerPivot en SharePoint</span><span class="sxs-lookup"><span data-stu-id="90b7b-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)|<span data-ttu-id="90b7b-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="90b7b-127">Required</span></span>|<span data-ttu-id="90b7b-128">Este paso instala los archivos de solución que agregan archivos de programa y páginas de aplicación en la granja y a las colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="90b7b-128">This step installs the solution files that add program files and application pages to the farm and to site collections.</span></span>|  
|[<span data-ttu-id="90b7b-129">Crear y configurar una aplicación de servicio PowerPivot en Administración central</span><span class="sxs-lookup"><span data-stu-id="90b7b-129">Create and Configure a PowerPivot Service Application in Central Administration</span></span>](create-and-configure-power-pivot-service-application-in-ca.md)|<span data-ttu-id="90b7b-130">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="90b7b-130">Required</span></span>|<span data-ttu-id="90b7b-131">Este paso proporciona el Servicio de sistema de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="90b7b-131">This step provisions the PowerPivot System Service.</span></span>|  
|[<span data-ttu-id="90b7b-132">Activar la integración de características de PowerPivot para colecciones de sitios en Administración central</span><span class="sxs-lookup"><span data-stu-id="90b7b-132">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>](activate-power-pivot-integration-for-site-collections-in-ca.md)|<span data-ttu-id="90b7b-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="90b7b-133">Required</span></span>|<span data-ttu-id="90b7b-134">Este paso activa las características de PowerPivot en el nivel de colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="90b7b-134">This step turns on PowerPivot features at the site collection level.</span></span>|  
|[<span data-ttu-id="90b7b-135">Adición de MSOLAP.5 como proveedor de datos de confianza en Excel Services</span><span class="sxs-lookup"><span data-stu-id="90b7b-135">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>](add-msolap-5-as-a-trusted-data-provider-in-excel-services.md)|<span data-ttu-id="90b7b-136">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="90b7b-136">Required</span></span>|<span data-ttu-id="90b7b-137">Este paso agrega el proveedor OLE DB de Analysis Services como proveedor de confianza en Excel Services.</span><span class="sxs-lookup"><span data-stu-id="90b7b-137">This step adds the Analysis Services OLE DB provider as a trusted provider in Excel Services.</span></span>|  
|[<span data-ttu-id="90b7b-138">Actualización de datos PowerPivot con SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="90b7b-138">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)|<span data-ttu-id="90b7b-139">Recomendado</span><span class="sxs-lookup"><span data-stu-id="90b7b-139">Recommended</span></span>|<span data-ttu-id="90b7b-140">La actualización de datos es opcional, pero se recomienda.</span><span class="sxs-lookup"><span data-stu-id="90b7b-140">Data refresh is optional but recommended.</span></span> <span data-ttu-id="90b7b-141">Permite programar actualizaciones desatendidas de los datos de PowerPivot en los libros de Excel publicados.</span><span class="sxs-lookup"><span data-stu-id="90b7b-141">It allows you to schedule unattended updates to the PowerPivot data in published Excel workbooks.</span></span>|  
|[<span data-ttu-id="90b7b-142">Configurar la cuenta de actualización de datos desatendida de PowerPivot &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="90b7b-142">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)|<span data-ttu-id="90b7b-143">Recomendado</span><span class="sxs-lookup"><span data-stu-id="90b7b-143">Recommended</span></span>|<span data-ttu-id="90b7b-144">Este paso proporciona una cuenta especial que se puede utilizar para ejecutar trabajos de actualización de datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="90b7b-144">This step provisions a special-purpose account that can be used to run data refresh jobs on the server.</span></span>|  
|[<span data-ttu-id="90b7b-145">Configurar la recopilación de datos de uso para &#40;PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="90b7b-145">Configure Usage Data Collection for &#40;PowerPivot for SharePoint</span></span>](configure-usage-data-collection-for-power-pivot-for-sharepoint.md)|<span data-ttu-id="90b7b-146">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-146">Optional</span></span>|<span data-ttu-id="90b7b-147">La recopilación de datos de uso está configurada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90b7b-147">Usage data collection is configured by default.</span></span> <span data-ttu-id="90b7b-148">Puede utilizar estos pasos para modificar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90b7b-148">You can use these steps to modify the default settings.</span></span>|  
|[<span data-ttu-id="90b7b-149">Configurar la actualización de datos dedicada o el procesamiento de solo consultas &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="90b7b-149">Configure Dedicated Data Refresh or Query-Only Processing &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-dedicated-data-refresh-query-only-processing-powerpivot-sharepoint.md)|<span data-ttu-id="90b7b-150">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-150">Optional</span></span>|<span data-ttu-id="90b7b-151">Una instancia de PowerPivot se puede destinar solo a los trabajos o a las consultas de actualización de datos.</span><span class="sxs-lookup"><span data-stu-id="90b7b-151">A PowerPivot instance can be dedicated to just data refresh jobs or queries.</span></span> <span data-ttu-id="90b7b-152">Además, puede modificar la configuración predeterminada de los trabajos paralelos de actualización de datos.</span><span class="sxs-lookup"><span data-stu-id="90b7b-152">In addition, you can modify default settings for parallel data refresh jobs.</span></span>|  
|[<span data-ttu-id="90b7b-153">Configurar las cuentas de servicio PowerPivot</span><span class="sxs-lookup"><span data-stu-id="90b7b-153">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)|<span data-ttu-id="90b7b-154">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-154">Optional</span></span>|<span data-ttu-id="90b7b-155">Explica cómo actualizar las contraseñas o cambiar las cuentas de servicio.</span><span class="sxs-lookup"><span data-stu-id="90b7b-155">Explains how to update passwords or change service accounts.</span></span>|  
|[<span data-ttu-id="90b7b-156">Conectar una aplicación de servicio PowerPivot a una aplicación Web de SharePoint en administración central</span><span class="sxs-lookup"><span data-stu-id="90b7b-156">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>](connect-power-pivot-service-app-to-sharepoint-web-app-in-ca.md)|<span data-ttu-id="90b7b-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-157">Optional</span></span>|<span data-ttu-id="90b7b-158">Explica cómo modificar las asociaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="90b7b-158">Explains how to modify service associations.</span></span>|  
|[<span data-ttu-id="90b7b-159">Crear una ubicación de confianza para los sitios PowerPivot en Administración central</span><span class="sxs-lookup"><span data-stu-id="90b7b-159">Create a trusted location for PowerPivot sites in Central Administration</span></span>](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md)|<span data-ttu-id="90b7b-160">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-160">Optional</span></span>|<span data-ttu-id="90b7b-161">Describe cómo agregar la galería de PowerPivot como una ubicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="90b7b-161">Explains how to add the PowerPivot Gallery as a trusted location.</span></span>|  
|[<span data-ttu-id="90b7b-162">Configurar y ver los archivos de registro de SharePoint y el registro de diagnósticos &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="90b7b-162">Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;</span></span>](configure-and-view-sharepoint-and-diagnostic-logging.md)|<span data-ttu-id="90b7b-163">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-163">Optional</span></span>|<span data-ttu-id="90b7b-164">El registro de eventos está configurado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90b7b-164">Event logging is configured by default.</span></span> <span data-ttu-id="90b7b-165">Puede utilizar estos pasos para modificar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90b7b-165">You can use these steps to modify the default settings.</span></span>|  
|[<span data-ttu-id="90b7b-166">Reglas de mantenimiento de PowerPivot - Configurar</span><span class="sxs-lookup"><span data-stu-id="90b7b-166">PowerPivot Health Rules - Configure</span></span>](configure-power-pivot-health-rules.md)|<span data-ttu-id="90b7b-167">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-167">Optional</span></span>|<span data-ttu-id="90b7b-168">Las reglas de estado de servidor están configuradas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90b7b-168">Server health rules are configured by default.</span></span> <span data-ttu-id="90b7b-169">Puede utilizar estos pasos para modificar algunas de las configuraciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="90b7b-169">You can use these steps to modify some of the default settings.</span></span>|  
|[<span data-ttu-id="90b7b-170">Crear y personalizar la Galería de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="90b7b-170">Create and Customize PowerPivot Gallery</span></span>](create-and-customize-power-pivot-gallery.md)|<span data-ttu-id="90b7b-171">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-171">Optional</span></span>|<span data-ttu-id="90b7b-172">Para las instalaciones que configure manualmente, este procedimiento explica cómo crear una biblioteca de la Galería de PowerPivot que muestre imágenes en miniatura de los libros PowerPivot que contiene.</span><span class="sxs-lookup"><span data-stu-id="90b7b-172">For installations that you are configuring manually, this procedure explains how to create a PowerPivot Gallery library that shows image thumbnails of the PowerPivot workbooks it contains.</span></span>|  
|[<span data-ttu-id="90b7b-173">Agregar un tipo de contenido de conexión de modelo semántico de BI a una biblioteca &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="90b7b-173">Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;</span></span>](add-bi-semantic-model-connection-content-type-to-library.md)|<span data-ttu-id="90b7b-174">Opcional</span><span class="sxs-lookup"><span data-stu-id="90b7b-174">Optional</span></span>|<span data-ttu-id="90b7b-175">Explica cómo ampliar una biblioteca de documentos para admitir la creación de archivos de conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="90b7b-175">Explains how to extend a document library to support the creation of BI semantic model connection files.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90b7b-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90b7b-176">See Also</span></span>  
 <span data-ttu-id="90b7b-177">[Instalación de PowerPivot para SharePoint 2010](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md) </span><span class="sxs-lookup"><span data-stu-id="90b7b-177">[PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md) </span></span>  
 <span data-ttu-id="90b7b-178">[&#40;de referencia de configuración de configuración PowerPivot para SharePoint&#41;](configuration-setting-reference-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="90b7b-178">[Configuration Setting Reference &#40;PowerPivot for SharePoint&#41;](configuration-setting-reference-power-pivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="90b7b-179">Recuperación antes desastres de PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="90b7b-179">Disaster Recovery for PowerPivot for SharePoint</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389570)  
  
  