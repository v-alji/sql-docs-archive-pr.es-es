---
title: Buscar y ver informes con un explorador (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: edf4843a-2a0a-486f-be25-14a3c1c6bc72
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b864188fc5152a11ad66ac9cd986891b88849a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749145"
---
# <a name="finding-and-viewing-reports-with-a-browser-report-builder-and-ssrs"></a><span data-ttu-id="9106a-102">Buscar y ver informes con un explorador (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="9106a-102">Finding and Viewing Reports with a Browser (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9106a-103">Puede utilizar cualquier explorador web compatible para ver un informe mediante una conexión directa a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9106a-103">You can use any supported Web browser to view a report through a direct connection to a report server.</span></span> <span data-ttu-id="9106a-104">Cada informe dispone de una dirección URL en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9106a-104">Every report has a URL address on a report server.</span></span> <span data-ttu-id="9106a-105">Puede escribir la dirección web de un informe para abrirlo por sí solo en una ventana del explorador de una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="9106a-105">You can enter the Web address of a report to open it in a browser window independently of a Web application.</span></span> <span data-ttu-id="9106a-106">El informe se abre en formato HTML e incluye la barra de herramientas de informe para que pueda navegar por las páginas o buscar valores de datos dentro del informe.</span><span class="sxs-lookup"><span data-stu-id="9106a-106">The report opens in HTML format and includes the report toolbar so that you can navigate pages or search on data values within the report.</span></span> <span data-ttu-id="9106a-107">Puede establecer parámetros en la dirección URL para ocultar la barra de herramientas o para seleccionar el formato de salida del informe.</span><span class="sxs-lookup"><span data-stu-id="9106a-107">You can set parameters on the URL to hide the toolbar or select the output format of the report.</span></span>  
  
 <span data-ttu-id="9106a-108">La apertura de un informe a través de su dirección web es adecuada para verlo, pero no para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="9106a-108">Opening a report through its Web address is suitable for viewing a report, but not managing a report.</span></span> <span data-ttu-id="9106a-109">No se puede tener acceso a las páginas de propiedades de un elemento ni a las páginas de definición de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="9106a-109">You cannot access an item's property pages or subscription definition pages.</span></span> <span data-ttu-id="9106a-110">Debe utilizar el Administrador de informes o un sitio de SharePoint para esas tareas.</span><span class="sxs-lookup"><span data-stu-id="9106a-110">You must use Report Manager or a SharePoint site for those tasks.</span></span>  
  
 <span data-ttu-id="9106a-111">Si no conoce la dirección web de un informe, puede abrir la dirección web del servidor de informes y, a continuación, examinar la jerarquía de carpetas del servidor de informes para seleccionar el informe desea ver.</span><span class="sxs-lookup"><span data-stu-id="9106a-111">If you do not know the Web address of a report, you can open the Web address of the report server and then browse the report server folder hierarchy to select the report you want to view.</span></span> <span data-ttu-id="9106a-112">El siguiente diagrama muestra una jerarquía de carpetas tal como aparecería en una ventana de explorador.</span><span class="sxs-lookup"><span data-stu-id="9106a-112">The following diagram illustrates a folder hierarchy as it appears in a browser window.</span></span>  
  
 <span data-ttu-id="9106a-113">![Carpetas en un explorador](../media/rs-browserfolder.GIF "Carpetas en un explorador")</span><span class="sxs-lookup"><span data-stu-id="9106a-113">![Folders in a browser](../media/rs-browserfolder.GIF "Folders in a browser")</span></span>  
<span data-ttu-id="9106a-114">Carpetas en un explorador</span><span class="sxs-lookup"><span data-stu-id="9106a-114">Folders in a browser</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9106a-115">Si obtiene acceso a un informe desde un dispositivo de mano, deberá utilizar el explorador para abrir los informes.</span><span class="sxs-lookup"><span data-stu-id="9106a-115">If you are accessing a report from a handheld device, you must use a browser to open a report.</span></span> <span data-ttu-id="9106a-116">El Administrador de informes todavía no ofrece compatibilidad con este tipo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9106a-116">Report Manager is not scaled for handheld devices.</span></span>  
  
 <span data-ttu-id="9106a-117">Para obtener más información acerca de los tipos de exploradores que puede usar, vea el tema relativo a los tipos de exploradores admitidos por Reporting Services en la [documentación de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9106a-117">For more information about types of browsers that you can use, see "Browser Types Supported by Reporting Services" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="navigating-report-server-folders-in-a-web-browser"></a><span data-ttu-id="9106a-118">Navegar por las carpetas del servidor de informes en un explorador web</span><span class="sxs-lookup"><span data-stu-id="9106a-118">Navigating Report Server Folders in a Web Browser</span></span>  
 <span data-ttu-id="9106a-119">Puede utilizar un explorador web para navegar por las carpetas del servidor de informes y ejecutar informes.</span><span class="sxs-lookup"><span data-stu-id="9106a-119">You can use a Web browser to navigate report server folders and run reports.</span></span> <span data-ttu-id="9106a-120">Los informes y los elementos se muestran en forma de vínculos en la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="9106a-120">Reports and items are displayed as links in the folder hierarchy.</span></span> <span data-ttu-id="9106a-121">Para abrir un informe, un recurso o una carpeta, o ver el contenido de un origen de datos compartido, haga clic en estos vínculos.</span><span class="sxs-lookup"><span data-stu-id="9106a-121">You can click links to open a report, resource, or folder, or view the contents of a shared data source.</span></span> <span data-ttu-id="9106a-122">La navegación por la jerarquía de carpetas puede resultarle útil si desconoce la dirección URL de un informe.</span><span class="sxs-lookup"><span data-stu-id="9106a-122">Navigating the folder hierarchy is useful if you do not know the URL of a report.</span></span> <span data-ttu-id="9106a-123">Para abrir una conexión con el explorador en el nodo raíz de la jerarquía de carpetas, solo tiene que especificar la dirección web del servidor de informes; a continuación, puede hacer clic en los vínculos de las carpetas para navegar por la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="9106a-123">You can specify the report server Web address to open a browser connection at the root node of the folder hierarchy, and then click folder links to navigate through the hierarchy.</span></span>  
  
 <span data-ttu-id="9106a-124">Al tener acceso a un directorio virtual de un servidor de informes, solo se visualizan las carpetas, los informes y los elementos cargados para los que se tiene permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="9106a-124">When you access a report server virtual directory, you see only the folders, reports, and uploaded items to which you have access.</span></span> <span data-ttu-id="9106a-125">La interfaz de usuario muestra únicamente la jerarquía de carpetas e información básica como, por ejemplo, la fecha de creación o modificación, el tamaño del archivo o el tipo de elemento de cada elemento:</span><span class="sxs-lookup"><span data-stu-id="9106a-125">The user interface shows only the folder hierarchy and basic information, such as creation or modification date, file size, and item type for individual items:</span></span>  
  
-   <span data-ttu-id="9106a-126">Un vínculo sin ningún otro indicador es un informe o un modelo.</span><span class="sxs-lookup"><span data-stu-id="9106a-126">A link with no other indicator is a report or a model.</span></span>  
  
-   <span data-ttu-id="9106a-127">La etiqueta \<ds> indica un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="9106a-127">The tag \<ds> indicates a shared data source.</span></span>  
  
-   <span data-ttu-id="9106a-128">La etiqueta \<dir> indica un elemento de carpeta.</span><span class="sxs-lookup"><span data-stu-id="9106a-128">The tag \<dir> indicates a folder item.</span></span>  
  
-   <span data-ttu-id="9106a-129">Una extensión de nombre de archivo indica que se trata de un recurso.</span><span class="sxs-lookup"><span data-stu-id="9106a-129">A file name extension indicates a resource.</span></span> <span data-ttu-id="9106a-130">La extensión del nombre del archivo identifica el tipo MIME del recurso.</span><span class="sxs-lookup"><span data-stu-id="9106a-130">The file name extension identifies the MIME type of the resource.</span></span> <span data-ttu-id="9106a-131">Por ejemplo, .jpg indica que se trata de una imagen en formato JPEG.</span><span class="sxs-lookup"><span data-stu-id="9106a-131">For example, .jpg indicates an image in JPEG format.</span></span>  
  
## <a name="typing-the-url-address-of-a-report"></a><span data-ttu-id="9106a-132">Escribir la dirección URL de un informe</span><span class="sxs-lookup"><span data-stu-id="9106a-132">Typing the URL Address of a Report</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="9106a-133">admite el acceso con direcciones URL a determinados elementos de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9106a-133">supports URL access to specific items on a report server.</span></span> <span data-ttu-id="9106a-134">La dirección URL debe incluir una ruta de acceso completa al informe y comandos para representarlo.</span><span class="sxs-lookup"><span data-stu-id="9106a-134">The URL must include a fully qualified path to the report and commands to render the report.</span></span> <span data-ttu-id="9106a-135">Si el informe incluye parámetros, también debe especificar cualquier valor necesario para abrir el informe.</span><span class="sxs-lookup"><span data-stu-id="9106a-135">If the report includes parameters, you must also specify any values that are required to open the report.</span></span> <span data-ttu-id="9106a-136">Si escribe una dirección URL para un informe que incluya espacios en la ruta de acceso, valores de parámetros o una extensión de representación, incluya en la dirección URL caracteres con codificación URL para obtener el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="9106a-136">If you are typing a URL for a report that includes spaces in the path, parameter values, or a rendering extension, you must incorporate URL encoded characters into the URL to get the results you expect.</span></span> <span data-ttu-id="9106a-137">El siguiente ejemplo corresponde a una dirección URL de informe que incluye codificación para los espacios del nombre de la ruta de acceso, los parámetros y la extensión de representación:</span><span class="sxs-lookup"><span data-stu-id="9106a-137">The following example illustrates a report URL that includes encoding for spaces in the path name, parameters, and a rendering extension:</span></span>  
  
 `http://<Webservername>/reportserver?/<reportfolder>/employee+sales+summary&ReportYear=2004&ReportMonth=06&EmpID=24&rs:Command=Render&rs:Format=HTML4.0`  
  
 <span data-ttu-id="9106a-138">El límite máximo para una dirección URL en Internet Explorer es de 2.083 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9106a-138">The maximum limit for a URL in Internet Explorer is 2,083 characters.</span></span> <span data-ttu-id="9106a-139">Para obtener más información, vea [La longitud máxima de la dirección URL es de 2083 caracteres en Internet Explorer](https://support.microsoft.com/kb/208427).</span><span class="sxs-lookup"><span data-stu-id="9106a-139">For more information, see [Maximum URL length in Internet Explorer](https://support.microsoft.com/kb/208427).</span></span>  
  
 <span data-ttu-id="9106a-140">Para obtener más información acerca de cómo obtener acceso a un informe a través de una URL, incluida la información acerca de cómo está construida una URL, vea el artículo sobre acceso a URL en la [documentación de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9106a-140">For more information about how to access a report through a URL, including information on how a URL is constructed, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9106a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9106a-141">See Also</span></span>  
 [<span data-ttu-id="9106a-142">Buscar y ver informes en el Administrador de informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9106a-142">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  