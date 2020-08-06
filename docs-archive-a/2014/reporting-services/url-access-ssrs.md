---
title: Acceso URL (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services]
- links [Reporting Services], URL access
- URL access [Reporting Services], about URL access
- parameters [Reporting Services], URL access
- report servers [Reporting Services], URL access
- hyperlinks [Reporting Services]
ms.assetid: 52c3f2a3-3d6d-4fee-9c46-83f366919398
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf44ea3c15c12f37eebf6e89faf4ff3affd64433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671350"
---
# <a name="url-access-ssrs"></a><span data-ttu-id="18857-102">Acceso URL (SSRS)</span><span class="sxs-lookup"><span data-stu-id="18857-102">URL Access (SSRS)</span></span>
  <span data-ttu-id="18857-103">El acceso URL del servidor de informes de SQL Server Reporting Services (SSRS) permite enviar comandos a un servidor de informes a través de una solicitud URL.</span><span class="sxs-lookup"><span data-stu-id="18857-103">URL access of the report server in SQL Server Reporting Services (SSRS) enables you to send commands to a report server through a URL request.</span></span> <span data-ttu-id="18857-104">Por ejemplo, puede personalizar la representación de un informe en una biblioteca de SharePoint o un servidor de informes en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="18857-104">For example, you can customize the rendering of a report on a native mode report server or in a SharePoint library.</span></span> <span data-ttu-id="18857-105">Es posible que haya visto el informe usando un conjunto específico de valores de parámetro de informe o tal vez haya consultado una determina página de su interés.</span><span class="sxs-lookup"><span data-stu-id="18857-105">You may have viewed the report using a specific set of report parameter values, or you may have been viewing a particular page of interest in the report.</span></span> <span data-ttu-id="18857-106">Puede encapsular esta información en la dirección URL usando los parámetros de acceso URL predefinidos.</span><span class="sxs-lookup"><span data-stu-id="18857-106">You can encapsulate this information in the URL using predefined URL access parameters.</span></span> <span data-ttu-id="18857-107">Puede personalizar más el modo en el que el servidor de informes procesa el informe incorporando parámetros sobre los formatos de representación o sobre la apariencia del visor de informes.</span><span class="sxs-lookup"><span data-stu-id="18857-107">You can further customize how the report server processes the report by embedding parameters for rendering formats or for the look and feel of the report viewer.</span></span> <span data-ttu-id="18857-108">Puede pegar esta dirección URL directamente en un mensaje de correo electrónico o una página web para permitir que otras personas tengan acceso al informe del mismo modo en el explorador.</span><span class="sxs-lookup"><span data-stu-id="18857-108">You can then paste this URL directly into an email or Web page to let others to access your report in the same manner in the browser.</span></span>  
  
 <span data-ttu-id="18857-109">Otras acciones que puede realizar con el acceso URL son:</span><span class="sxs-lookup"><span data-stu-id="18857-109">Other actions you can perform through URL access are:</span></span>  
  
-   <span data-ttu-id="18857-110">Enviar comandos al visor HTML para, por ejemplo, ajustar su apariencia.</span><span class="sxs-lookup"><span data-stu-id="18857-110">Send commands to the HTML viewer, such as adjusting its look and feel</span></span>  
  
-   <span data-ttu-id="18857-111">Mostrar la lista de elementos secundarios de una carpeta de catálogos.</span><span class="sxs-lookup"><span data-stu-id="18857-111">List the children of a catalog folder</span></span>  
  
-   <span data-ttu-id="18857-112">Recuperar la definición XML de un elemento de catálogo.</span><span class="sxs-lookup"><span data-stu-id="18857-112">Retrieve the XML definition of a catalog item</span></span>  
  
-   <span data-ttu-id="18857-113">Representar una instantánea específica del historial de informes.</span><span class="sxs-lookup"><span data-stu-id="18857-113">Render a specific report history snapshot</span></span>  
  
-   <span data-ttu-id="18857-114">Administrar sesiones del informe.</span><span class="sxs-lookup"><span data-stu-id="18857-114">Manage report sessions</span></span>  
  
 <span data-ttu-id="18857-115">Para consultar la lista completa de comandos y opciones de configuración disponibles con el acceso URL, vea [Referencia de parámetros de acceso URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="18857-115">For the complete list of commands and settings available through URL access, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="url-access-concepts"></a><span data-ttu-id="18857-116">Conceptos del acceso URL</span><span class="sxs-lookup"><span data-stu-id="18857-116">URL Access Concepts</span></span>  
 <span data-ttu-id="18857-117">Las solicitudes URL que se dirigen a un servidor de informes contienen parámetros que se procesan en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="18857-117">URL requests to the report server contain parameters that are processed by the report server.</span></span> <span data-ttu-id="18857-118">La manera en la que el servidor de informes administra las solicitudes URL depende de los parámetros, prefijos de parámetro y tipos de elementos que están incluidos en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="18857-118">The way in which the report server handles URL requests depends on the parameters, parameter prefixes, and types of items that are included in the URL.</span></span> <span data-ttu-id="18857-119">Las direcciones URL del servidor de informes se rigen por las instrucciones de formato de dirección URL propuestas por el estándar de borrador W3C/IETF del World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="18857-119">Report server URLs adhere to the URL formatting guidelines as proposed by the joint World Wide Web Consortium W3C/IETF draft standard.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="18857-120">es compatible con la mayor parte de los exploradores de Internet o aplicaciones que admiten el direccionamiento con direcciones URL estándar.</span><span class="sxs-lookup"><span data-stu-id="18857-120">URL functionality is compatible with most Internet browsers or applications that support standard URL addressing.</span></span>  
  
### <a name="url-access-syntax"></a><span data-ttu-id="18857-121">Sintaxis del acceso URL</span><span class="sxs-lookup"><span data-stu-id="18857-121">URL Access Syntax</span></span>  
 <span data-ttu-id="18857-122">Las solicitudes URL pueden contener varios parámetros que se muestran en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="18857-122">URL requests can contain multiple parameters that are listed in any order.</span></span> <span data-ttu-id="18857-123">Los parámetros se separan mediante un símbolo de Y comercial (&), y los pares de nombre y valor se separan con un signo igual (=).</span><span class="sxs-lookup"><span data-stu-id="18857-123">Parameters are separated by an ampersand (&) and name/value pairs are separated by an equal sign (=).</span></span>  
  
```  
  
rswebserviceurl  
?  
reportpath  
      [&prefix:param=value]...n]  
  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="18857-124">Descripción de la sintaxis</span><span class="sxs-lookup"><span data-stu-id="18857-124">Syntax Description</span></span>  
 <span data-ttu-id="18857-125">*rswebserviceurl*</span><span class="sxs-lookup"><span data-stu-id="18857-125">*rswebserviceurl*</span></span>  
 <span data-ttu-id="18857-126">Dirección URL del servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="18857-126">The Web service URL of the report server.</span></span> <span data-ttu-id="18857-127">Para el modo nativo, es la dirección URL del servicio web de la instancia del servidor de informes configurada en el Administrador de configuración de Reporting Services (vea [Configurar las direcciones URL del servidor de informes &#40;Administrador de configuración de SSRS&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span><span class="sxs-lookup"><span data-stu-id="18857-127">For native mode, it is the Web service URL of the report server instance configured in Reporting Services Configuration Manager (see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span></span> <span data-ttu-id="18857-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="18857-128">For example:</span></span>  
  
```  
http://myrshost/reportserver  
https://machine.adventure-works.com/reportserver_MYNAMEDINSTANCE  
```  
  
 <span data-ttu-id="18857-129">En el modo integrado de SharePoint, es la dirección URL del proxy de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] de un sitio de SharePoint integrado con [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18857-129">For SharePoint integrated mode, it is the URL of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] proxy at a SharePoint site integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="18857-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="18857-130">For example:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver  
```  
  
> [!TIP]  
>  <span data-ttu-id="18857-131">Es importante que la dirección URL incluya la sintaxis de proxy de `_vti_bin` para enrutar la solicitud a través de SharePoint y el proxy HTTP de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18857-131">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="18857-132">El proxy agrega algún contexto a la solicitud HTTP, contexto que es necesario para garantizar la correcta ejecución del informe para los servidores de informes de modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="18857-132">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
 <span data-ttu-id="18857-133">*pathinfo*</span><span class="sxs-lookup"><span data-stu-id="18857-133">*pathinfo*</span></span>  
 <span data-ttu-id="18857-134">Nombre de la ruta de acceso relativa del elemento en la base de datos del servidor de informes en modo nativo o dirección URL completa del elemento en un catálogo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="18857-134">The relative path name of the item in the native mode report server database, or the fully qualified URL of the item in a SharePoint catalog.</span></span>  
  
 <span data-ttu-id="18857-135">Ruta de acceso del elemento del catálogo.</span><span class="sxs-lookup"><span data-stu-id="18857-135">The path of the catalog item.</span></span> <span data-ttu-id="18857-136">En modo nativo, es la ruta de acceso relativa del elemento de la base de datos del servidor de informes, que comienza por una barra diagonal (`/`).</span><span class="sxs-lookup"><span data-stu-id="18857-136">For native mode, it is the relative path of the item in the report server database, beginning with a slash (`/`).</span></span> <span data-ttu-id="18857-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="18857-137">For example:</span></span>  
  
```  
/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2  
```  
  
 <span data-ttu-id="18857-138">En el modo integrado de SharePoint, es la dirección URL completa del elemento de la biblioteca de SharePoint, incluida la extensión del elemento.</span><span class="sxs-lookup"><span data-stu-id="18857-138">For SharePoint integrated mode, it is the fully qualified URL of the item in the SharePoint library, including the item extension.</span></span> <span data-ttu-id="18857-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="18857-139">For example:</span></span>  
  
```  
http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl  
```  
  
 `&`  
 <span data-ttu-id="18857-140">Se usa para separar los pares de nombre y valor de los parámetros de acceso URL.</span><span class="sxs-lookup"><span data-stu-id="18857-140">Used to separate name and value pairs of URL access parameters.</span></span>  
  
 <span data-ttu-id="18857-141">**prefijo**</span><span class="sxs-lookup"><span data-stu-id="18857-141">**prefix**</span></span>  
 <span data-ttu-id="18857-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="18857-142">Optional.</span></span> <span data-ttu-id="18857-143">Prefijo del parámetro de acceso URL (por ejemplo, `rs:` o `rc:`) que accede a un proceso concreto que se ejecuta en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="18857-143">A prefix for the URL access parameter (for example, `rs:` or `rc:`) that accesses a specific process running within the report server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18857-144">Si no se incluye un parámetro de acceso URL, el parámetro se procesa en el servidor de informes como un parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="18857-144">If a prefix for a URL access parameter is not included, the parameter is processed by the report server as a report parameter.</span></span> <span data-ttu-id="18857-145">Los parámetros de informe no usan un prefijo de parámetro y distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="18857-145">Report parameters do not use a parameter prefix and are case-sensitive.</span></span>  
  
 <span data-ttu-id="18857-146">**param**</span><span class="sxs-lookup"><span data-stu-id="18857-146">**param**</span></span>  
 <span data-ttu-id="18857-147">El nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="18857-147">The parameter name.</span></span>  
  
 <span data-ttu-id="18857-148">*value*</span><span class="sxs-lookup"><span data-stu-id="18857-148">*value*</span></span>  
 <span data-ttu-id="18857-149">Texto de la dirección URL que corresponde al valor del parámetro que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="18857-149">URL text corresponding to the value of the parameter being used.</span></span>  
  
 <span data-ttu-id="18857-150">**Nota** : para obtener una lista de los parámetros de acceso URL disponibles, vea [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="18857-150">**Note:** For a list of the available URL access parameters, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span> <span data-ttu-id="18857-151">Para obtener ejemplos de cómo pasar parámetros de informe en la dirección URL, vea [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="18857-151">For examples passing report parameters on the URL, see [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="18857-152">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="18857-152">Related Tasks</span></span>  
  
|<span data-ttu-id="18857-153">Descripciones de las tareas</span><span class="sxs-lookup"><span data-stu-id="18857-153">Task Descriptions</span></span>|<span data-ttu-id="18857-154">Vínculos</span><span class="sxs-lookup"><span data-stu-id="18857-154">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="18857-155">Acceder a los elementos del servidor de informes, como informes, orígenes de datos compartidos y recursos.</span><span class="sxs-lookup"><span data-stu-id="18857-155">Access report server items, such as reports, shared data sources, and resources.</span></span>|[<span data-ttu-id="18857-156">Acceso a elementos del servidor de informes mediante el acceso URL</span><span class="sxs-lookup"><span data-stu-id="18857-156">Access Report Server Items Using URL Access</span></span>](access-report-server-items-using-url-access.md)|  
|<span data-ttu-id="18857-157">Pasar parámetros de informe a un informe.</span><span class="sxs-lookup"><span data-stu-id="18857-157">Pass report parameters to a report.</span></span>|[<span data-ttu-id="18857-158">Paso de un parámetro de informe en una dirección URL</span><span class="sxs-lookup"><span data-stu-id="18857-158">Pass a Report Parameter Within a URL</span></span>](pass-a-report-parameter-within-a-url.md)|  
|<span data-ttu-id="18857-159">Establecer la configuración regional de los parámetros de informe de la cadena de acceso URL, que define las interpretaciones de las fechas, divisas, etc. específicas de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="18857-159">Set the locale of the report parameters in the URL access string, which defines the locale-specific interpretations of dates, currencies, and so on.</span></span>|[<span data-ttu-id="18857-160">Establecimiento del idioma para los parámetros de informe en una dirección URL</span><span class="sxs-lookup"><span data-stu-id="18857-160">Set the Language for Report Parameters in a URL</span></span>](set-the-language-for-report-parameters-in-a-url.md)|  
|<span data-ttu-id="18857-161">Enviar valores específicos para la extensión de representación que personalicen cómo se va a representar el informe.</span><span class="sxs-lookup"><span data-stu-id="18857-161">Send rendering extension specific settings that customize how the report is rendered.</span></span>|[<span data-ttu-id="18857-162">Especificación de la configuración de la información del dispositivo en una dirección URL</span><span class="sxs-lookup"><span data-stu-id="18857-162">Specify Device Information Settings in a URL</span></span>](specify-device-information-settings-in-a-url.md)|  
|<span data-ttu-id="18857-163">Exportar un informe directamente a un formato de archivo sin verlo en el explorador.</span><span class="sxs-lookup"><span data-stu-id="18857-163">Export a report directly to a file format without viewing it in the browser.</span></span>|[<span data-ttu-id="18857-164">Exportación de un informe con el acceso URL</span><span class="sxs-lookup"><span data-stu-id="18857-164">Export a Report Using URL Access</span></span>](export-a-report-using-url-access.md)|  
|<span data-ttu-id="18857-165">Abrir un informe y navegar directamente a la ubicación de una cadena.</span><span class="sxs-lookup"><span data-stu-id="18857-165">Open a report and navigate directly to the location of a string.</span></span>|[<span data-ttu-id="18857-166">Búsqueda de un informe con el acceso URL</span><span class="sxs-lookup"><span data-stu-id="18857-166">Search a Report Using URL Access</span></span>](search-a-report-using-url-access.md)|  
|<span data-ttu-id="18857-167">Representar una instantánea específica del historial de informes.</span><span class="sxs-lookup"><span data-stu-id="18857-167">Render a specific report history snapshot.</span></span>|[<span data-ttu-id="18857-168">Representación de una instantánea del historial de informes con el acceso URL</span><span class="sxs-lookup"><span data-stu-id="18857-168">Render a Report History Snapshot Using URL Access</span></span>](render-a-report-history-snapshot-using-url-access.md)|  
  
## <a name="see-also"></a><span data-ttu-id="18857-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18857-169">See Also</span></span>  
 <span data-ttu-id="18857-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span><span class="sxs-lookup"><span data-stu-id="18857-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span></span>  
 <span data-ttu-id="18857-171">[Referencia de parámetros de acceso URL](url-access-parameter-reference.md) </span><span class="sxs-lookup"><span data-stu-id="18857-171">[URL Access Parameter Reference](url-access-parameter-reference.md) </span></span>  
 <span data-ttu-id="18857-172">[Integración de Reporting Services con el acceso URL](application-integration/integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="18857-172">[Integrating Reporting Services Using URL Access](application-integration/integrating-reporting-services-using-url-access.md) </span></span>  
 [<span data-ttu-id="18857-173">Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="18857-173">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
