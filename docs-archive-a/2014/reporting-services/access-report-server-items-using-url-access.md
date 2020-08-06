---
title: Acceder a elementos del servidor de informes mediante el acceso URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- referencing URL items for report server access
- URL access [Reporting Services], report servers
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6693419490c1b3770ccb41b2645cbdba8996630a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674662"
---
# <a name="access-report-server-items-using-url-access"></a><span data-ttu-id="6c467-102">Acceder a elementos del servidor de informes mediante el acceso URL</span><span class="sxs-lookup"><span data-stu-id="6c467-102">Access Report Server Items Using URL Access</span></span>
  <span data-ttu-id="6c467-103">En este tema se explica cómo acceder a los elementos del catálogo de diferentes tipos en una base de datos del servidor de informes o en un sitio de SharePoint con *rs:Command*=*Value*.</span><span class="sxs-lookup"><span data-stu-id="6c467-103">This topic describes how to access catalog items of different types in a report server data base or in a SharePoint site using *rs:Command*=*Value*.</span></span>  
  
 <span data-ttu-id="6c467-104">No es necesario agregar esta cadena de parámetro.</span><span class="sxs-lookup"><span data-stu-id="6c467-104">It is not necessary to add this parameter string.</span></span> <span data-ttu-id="6c467-105">Si la omite, el servidor de informes evalúa el tipo de elemento y selecciona el valor de parámetro apropiado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6c467-105">If you omit it, the report server evaluates the item type and selects the appropriate parameter value automatically.</span></span> <span data-ttu-id="6c467-106">Pero, si se usa la cadena *rs:Command*=*Value* en la dirección URL, mejora el rendimiento del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6c467-106">However, using the *rs:Command*=*Value* string in the URL improves the performance of the report server.</span></span>  
  
 <span data-ttu-id="6c467-107">Observe la sintaxis del proxy `_vti_bin` en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6c467-107">Note the `_vti_bin` proxy syntax in the examples below.</span></span> <span data-ttu-id="6c467-108">Para obtener más información acerca de cómo usar la sintaxis de proxy, vea [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6c467-108">For more information about using the proxy syntax, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="access-a-report"></a><span data-ttu-id="6c467-109">Acceder a un informe</span><span class="sxs-lookup"><span data-stu-id="6c467-109">Access a Report</span></span>  
 <span data-ttu-id="6c467-110">Para ver un informe en el explorador, use el parámetro *RS: Command* = *Render* .</span><span class="sxs-lookup"><span data-stu-id="6c467-110">To view a report in the browser, use the *rs:Command*=*Render* parameter.</span></span> <span data-ttu-id="6c467-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c467-111">For example:</span></span>  
  
 <span data-ttu-id="6c467-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="6c467-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
 <span data-ttu-id="6c467-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="6c467-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="6c467-114">Es importante que la dirección URL incluya la sintaxis de proxy de `_vti_bin` para enrutar la solicitud a través de SharePoint y el proxy HTTP de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c467-114">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="6c467-115">El proxy agrega algún contexto a la solicitud HTTP, contexto que es necesario para garantizar la correcta ejecución del informe para los servidores de informes de modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6c467-115">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
## <a name="access-a-resource"></a><span data-ttu-id="6c467-116">Acceder a un recurso</span><span class="sxs-lookup"><span data-stu-id="6c467-116">Access a Resource</span></span>  
 <span data-ttu-id="6c467-117">Para tener acceso a un recurso, use el parámetro *RS: Command* = *GetResourceContents* . Si el recurso es compatible con el explorador, como una imagen, se abre en el explorador.</span><span class="sxs-lookup"><span data-stu-id="6c467-117">To access a resource, use the *rs:Command*=*GetResourceContents* parameter.If the resource is compatible with the browser, such as an image, it is opened in the browser.</span></span> <span data-ttu-id="6c467-118">De lo contrario, le preguntarán si desea abrir o guardar el archivo o recurso en el disco.</span><span class="sxs-lookup"><span data-stu-id="6c467-118">Otherwise, you are prompted to open or save the file or resource to disk.</span></span>  
  
 <span data-ttu-id="6c467-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="6c467-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span></span>  
  
 <span data-ttu-id="6c467-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="6c467-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span></span>  
  
## <a name="access-a-data-source"></a><span data-ttu-id="6c467-121">Acceder a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="6c467-121">Access a Data Source</span></span>  
 <span data-ttu-id="6c467-122">Para tener acceso a un origen de datos, use el parámetro *RS: Command* = *GetDataSourceContents* .</span><span class="sxs-lookup"><span data-stu-id="6c467-122">To access a data source, use the *rs:Command*=*GetDataSourceContents* parameter.</span></span> <span data-ttu-id="6c467-123">Si el explorador admite código XML, aparecerá la definición del origen de datos si es un usuario autenticado con el permiso `Read Contents` en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6c467-123">If your browser supports XML, the data source definition is displayed if you are an authenticated user with `Read Contents` permission on the data source.</span></span> <span data-ttu-id="6c467-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c467-124">For example:</span></span>  
  
 <span data-ttu-id="6c467-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="6c467-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="6c467-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="6c467-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="6c467-127">La estructura XML se parecería al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c467-127">The XML structure might look similar to the following example:</span></span>  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 <span data-ttu-id="6c467-128">Se devuelve la cadena de conexión según el valor **SecureConnectionLevel** del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6c467-128">The connection string is returned based on the **SecureConnectionLevel** setting of the report server.</span></span> <span data-ttu-id="6c467-129">Para obtener más información acerca de la configuración **SecureConnectionLevel** , vea [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="6c467-129">For more information about the **SecureConnectionLevel** setting, see [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span></span>  
  
## <a name="access-the-contents-of-a-folder"></a><span data-ttu-id="6c467-130">Acceder al contenido de una carpeta</span><span class="sxs-lookup"><span data-stu-id="6c467-130">Access the Contents of a Folder</span></span>  
 <span data-ttu-id="6c467-131">Para tener acceso al contenido de una carpeta, use el parámetro *RS: Command* = *GetChildren* .</span><span class="sxs-lookup"><span data-stu-id="6c467-131">To access the contents of a folder, use the *rs:Command*=*GetChildren* parameter.</span></span> <span data-ttu-id="6c467-132">Se devuelve una página de navegación por carpetas genérica que contiene vínculos a las subcarpetas, informes, orígenes de datos y recursos en la carpeta solicitada.</span><span class="sxs-lookup"><span data-stu-id="6c467-132">A generic folder-navigation page is returned that contains links to the subfolders, reports, data sources, and resources in the requested folder.</span></span> <span data-ttu-id="6c467-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c467-133">For example:</span></span>  
  
 <span data-ttu-id="6c467-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="6c467-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="6c467-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="6c467-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="6c467-136">La interfaz de usuario que se ve es similar al modo de exploración de directorios que usa [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="6c467-136">The user interface you see is similar to the directory browsing mode used by [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span></span> <span data-ttu-id="6c467-137">El número de versión, incluido el número de compilación, del servidor de informes también se muestra debajo de la lista de carpetas.</span><span class="sxs-lookup"><span data-stu-id="6c467-137">The version number, including the build number, of the report server is also displayed below the folder listing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c467-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c467-138">See Also</span></span>  
 <span data-ttu-id="6c467-139">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6c467-139">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="6c467-140">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="6c467-140">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
