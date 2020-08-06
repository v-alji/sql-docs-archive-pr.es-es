---
title: Agregar el elemento Web visor de informes a una página web (Reporting Services en el modo integrado de SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
ms.assetid: cac75345-2380-467d-a394-0a2140908a5a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d9b933fad8bc566b3cb0ef04303a85c5f034e620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747980"
---
# <a name="add-the-report-viewer-web-part-to-a-web-page-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="0b0be-102">Agregar el elemento web Visor de informes a una página web (Reporting Services en el modo integrado de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="0b0be-102">Add the Report Viewer Web Part to a Web Page (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="0b0be-103">Puede usar el elemento web Visor de informes para ver informes que se ejecutan en un servidor de informes configurado para ejecutarse en el modo integrado con SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0b0be-103">You can use the Report Viewer Web Part to view reports that run on report server that is configured to run in SharePoint integrated mode.</span></span> <span data-ttu-id="0b0be-104">Puede usar el elemento web para mostrar archivos de definición de informe (.rdl) que haya creado en el Generador de informes o el Diseñador de informes y cargado en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0b0be-104">You can use the Web Part to display report definition (.rdl) files that you created in Report Builder or Report Designer and uploaded to a library.</span></span>  
  
 <span data-ttu-id="0b0be-105">Puede agregar el elemento web Visor de informes a una página web si desea incrustar el informe en la página.</span><span class="sxs-lookup"><span data-stu-id="0b0be-105">You can add the Report Viewer Web Part to a Web page if you want to embed a report on that page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b0be-106">Aunque tienen nombres idénticos, el elemento web Visor de informes instalado con el complemento [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] difiere del incluido en el archivo RSWebParts.cab.</span><span class="sxs-lookup"><span data-stu-id="0b0be-106">Although they have identical names, the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in is different from the Report Viewer Web Part that is included in the RSWebParts.cab file.</span></span> <span data-ttu-id="0b0be-107">Las instrucciones de este tema son específicas para el elemento web Visor de informes que se instala con el complemento [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b0be-107">The instructions in this topic are specifically for the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
 <span data-ttu-id="0b0be-108">Para agregar un elemento web a una página web, debe tener el permiso Agregar y personalizar páginas en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="0b0be-108">To add a Web Part to a Web page, you must have the Add and Customize Pages permission at the site level.</span></span> <span data-ttu-id="0b0be-109">Si va a usar la configuración de seguridad predeterminada, este permiso se concede a los miembros del grupo **Propietarios** que tienen el nivel de permiso Control total.</span><span class="sxs-lookup"><span data-stu-id="0b0be-109">If you are using default security settings, this permission is granted to members of the **Owners** group who have the Full Control level of permission.</span></span>  
  
### <a name="to-embed-a-report-in-a-web-page"></a><span data-ttu-id="0b0be-110">Para incrustar un informe en una página web</span><span class="sxs-lookup"><span data-stu-id="0b0be-110">To embed a report in a Web page</span></span>  
  
1.  <span data-ttu-id="0b0be-111">Abra o cree un panel o una página de elementos web.</span><span class="sxs-lookup"><span data-stu-id="0b0be-111">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="0b0be-112">En el menú **Acciones del sitio**, haga clic en **Editar página**.</span><span class="sxs-lookup"><span data-stu-id="0b0be-112">On **Site Actions**, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="0b0be-113">Haga clic en **Agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="0b0be-113">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="0b0be-114">En la lista de categorías de elementos web, seleccione la categoría **Varios** y, a continuación, seleccione **Visor de informes de SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="0b0be-114">In the list of web part categories, select the **Miscellaneous** category, and then select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="0b0be-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0b0be-115">Click **Add**.</span></span> <span data-ttu-id="0b0be-116">El elemento web se agregará a la parte superior de la zona.</span><span class="sxs-lookup"><span data-stu-id="0b0be-116">The Web Part is added at the top of the zone.</span></span> <span data-ttu-id="0b0be-117">Puede arrastrarlo a otra ubicación en la zona.</span><span class="sxs-lookup"><span data-stu-id="0b0be-117">You can drag it to a different location in the zone.</span></span>  
  
6.  <span data-ttu-id="0b0be-118">Dentro del visor, haga clic en **Haga clic aquí para abrir el panel de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="0b0be-118">Within the viewer, click **Click here to open the tool pane**.</span></span>  
  
7.  <span data-ttu-id="0b0be-119">Para seleccionar un informe desde cualquier biblioteca de la colección de sitios actual, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="0b0be-119">Select a report from any library in the current site collection by clicking the browse (**...**) button.</span></span> <span data-ttu-id="0b0be-120">Además, puede escribir la dirección URL del informe.</span><span class="sxs-lookup"><span data-stu-id="0b0be-120">You can also type the report URL.</span></span> <span data-ttu-id="0b0be-121">Para determinar la dirección URL de cualquier informe, haga clic con el botón derecho en el informe y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b0be-121">To determine the URL for any report, right-click the report and select **Properties**.</span></span> <span data-ttu-id="0b0be-122">No haga clic en la flecha hacia abajo junto al informe; la dirección URL del informe no se indica en la página Ver propiedades del elemento.</span><span class="sxs-lookup"><span data-stu-id="0b0be-122">Do not click the down arrow next to the report; the report URL is not indicated in the View Properties page of the item.</span></span> <span data-ttu-id="0b0be-123">Si copia y pega la dirección URL del cuadro de diálogo **Propiedades** , reemplace la codificación "%20" de la dirección URL por un espacio (por ejemplo, "Company%20Sales" debe ser "Company Sales").</span><span class="sxs-lookup"><span data-stu-id="0b0be-123">If you copy and paste the URL from the **Properties** dialog box, replace the "%20" URL encoding with a space (for example, "Company%20Sales" should be "Company Sales").</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b0be-124">Cada elemento web Visor de informes contiene un solo informe.</span><span class="sxs-lookup"><span data-stu-id="0b0be-124">Each Report Viewer Web Part contains a single report.</span></span> <span data-ttu-id="0b0be-125">La dirección URL debe ser una ruta de acceso completa a un informe que esté en el sitio de SharePoint actual o en un sitio dentro de la misma aplicación o granja de servidores web.</span><span class="sxs-lookup"><span data-stu-id="0b0be-125">The URL must be the fully qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="0b0be-126">La dirección URL debe resolverse como una biblioteca de documentos o una carpeta dentro de una biblioteca de documentos que contenga el informe.</span><span class="sxs-lookup"><span data-stu-id="0b0be-126">The URL must resolve to a document library or to a folder within a document library that contains the report.</span></span> <span data-ttu-id="0b0be-127">La dirección URL del informe debe incluir la extensión de archivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="0b0be-127">The report URL must include the .rdl file extension.</span></span> <span data-ttu-id="0b0be-128">Si el informe depende de un modelo o de archivos de orígenes de datos compartidos, no necesita especificar esos archivos en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0b0be-128">If the report depends on a model or shared data source files, you do not need to specify those files in the URL.</span></span> <span data-ttu-id="0b0be-129">El informe contiene referencias a los archivos que necesita.</span><span class="sxs-lookup"><span data-stu-id="0b0be-129">The report contains references to the files it needs.</span></span>  
  
8.  <span data-ttu-id="0b0be-130">Cuando el panel de herramientas está abierto, puede establecer propiedades para modificar la apariencia y el diseño predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0b0be-130">While the tool pane is open, you can set properties to modify the default appearance and layout.</span></span>  
  
9. <span data-ttu-id="0b0be-131">Haga clic en **Aplicar** en la parte inferior del panel de herramientas y, a continuación, haga clic en **Aceptar** para cerrar el panel.</span><span class="sxs-lookup"><span data-stu-id="0b0be-131">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0be-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b0be-132">See Also</span></span>  
 <span data-ttu-id="0b0be-133">[Elemento Web visor de informes en un sitio de SharePoint](../report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="0b0be-133">[Report Viewer Web Part on a SharePoint Site](../report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 <span data-ttu-id="0b0be-134">[Personalizar el elemento Web visor de informes](../customize-the-report-viewer-web-part.md) </span><span class="sxs-lookup"><span data-stu-id="0b0be-134">[Customize the Report Viewer Web Part](../customize-the-report-viewer-web-part.md) </span></span>  
 <span data-ttu-id="0b0be-135">[Conceder permisos para elementos del servidor de informes en un sitio de SharePoint](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="0b0be-135">[Granting Permissions on Report Server Items on a SharePoint Site](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="0b0be-136">Instalar o desinstalar el complemento de Reporting Services para SharePoint &#40;SharePoint 2010 y SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="0b0be-136">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](../install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
