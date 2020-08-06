---
title: Ver informes de Reporting Services en dispositivos de Microsoft Surface y dispositivos iOS de Apple | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- iPad
- Safari
- SSRS
- Report Viewer [Reporting Services]
- iOS
ms.assetid: 2124bcf5-d60a-475f-a4ae-de6df44d2860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db52ed500559969ae52eb9477caa6b410889c1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675199"
---
# <a name="view-reporting-services-reports-on-microsoft-surface-devices-and--apple-ios-devices"></a><span data-ttu-id="948cd-102">Ver informes de Reporting Services en dispositivos de Microsoft Surface y de Apple iOS</span><span class="sxs-lookup"><span data-stu-id="948cd-102">View Reporting Services Reports on Microsoft Surface Devices and  Apple iOS Devices</span></span>
  <span data-ttu-id="948cd-103">En este artículo se describen las características y los flujos de trabajo de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] admitidos para dispositivos de Microsoft Surface, y para dispositivos con Apple iOS 6 y Apple Safari como el iPad.</span><span class="sxs-lookup"><span data-stu-id="948cd-103">This article describes the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features and workflows supported for Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari such as the iPad.</span></span>

## <a name="view-and-interact-with-reports"></a><span data-ttu-id="948cd-104">Ver e interactuar con informes</span><span class="sxs-lookup"><span data-stu-id="948cd-104">View and Interact With Reports</span></span>
 <span data-ttu-id="948cd-105">A partir de [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] admite la visualización e interactividad básica con informes en dispositivos de Microsoft Surface, y en dispositivos con Apple iOS 6 y con el explorador Apple Safari como el iPad.</span><span class="sxs-lookup"><span data-stu-id="948cd-105">Starting with [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supports viewing and basic interactivity with reports on Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari browser such as the iPad.</span></span> <span data-ttu-id="948cd-106">También puede publicar informes mediante dispositivos de Microsoft Surface.</span><span class="sxs-lookup"><span data-stu-id="948cd-106">You can also publish reports using Microsoft Surface devices.</span></span>

 <span data-ttu-id="948cd-107">![Escritorio de iPad](media/videothumbnail.jpg "Escritorio del IPad") Vea una demostración de cómo ver informes en un iPad.</span><span class="sxs-lookup"><span data-stu-id="948cd-107">![IPad Desktop](media/videothumbnail.jpg "IPad Desktop") Watch a demonstration of viewing reports on an iPad.</span></span>

 <span data-ttu-id="948cd-108">También puede ver informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en un dispositivo de Windows Phone 8.</span><span class="sxs-lookup"><span data-stu-id="948cd-108">You can also view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports on a Windows Phone 8 device.</span></span>

 <span data-ttu-id="948cd-109">Para usar las características descritas en este tema, instale uno de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="948cd-109">To utilize the features described in this topic, install one of the following:</span></span>

-   <span data-ttu-id="948cd-110">Si se trata de un servidor de informes en modo nativo, instale [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="948cd-110">For a native mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later.</span></span>

     [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]<span data-ttu-id="948cd-111">está disponible para su descarga desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=35575).</span><span class="sxs-lookup"><span data-stu-id="948cd-111">is available for download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575).</span></span>

-   <span data-ttu-id="948cd-112">Si es un servidor de informes en modo de SharePoint, instale la versión [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] o posterior del complemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="948cd-112">For a SharePoint mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>

 <span data-ttu-id="948cd-113">**Para ver e interactuar con un informe en un dispositivo iPad o en el dispositivo de Microsoft Surface**</span><span class="sxs-lookup"><span data-stu-id="948cd-113">**To view and interact with a report on an iPad device or Microsoft Surface device**</span></span>

1.  <span data-ttu-id="948cd-114">Asegúrese de que puede conectarse al servidor de informes o al sitio de SharePoint donde reside el informe.</span><span class="sxs-lookup"><span data-stu-id="948cd-114">Make sure that you can connect to the report server or SharePoint site where the report resides.</span></span>

2.  <span data-ttu-id="948cd-115">Abra el informe realizando una de las acciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="948cd-115">Open the report by doing one of the following.</span></span>

    -   <span data-ttu-id="948cd-116">**Desde el correo electrónico:** Desde un correo electrónico creado por una suscripción de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , puntee en la dirección URL del informe.</span><span class="sxs-lookup"><span data-stu-id="948cd-116">**Start from e-mail:** From an e-mail that is created by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] subscription, tap the URL of the report.</span></span> <span data-ttu-id="948cd-117">El informe se abrirá en el explorador.</span><span class="sxs-lookup"><span data-stu-id="948cd-117">The report will open in the browser.</span></span>

    -   <span data-ttu-id="948cd-118">**Iniciar desde el servidor de informes:** Busque el directorio en el servidor de informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y pulse en el nombre del informe para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="948cd-118">**Start from Report Server:** Browse the directory on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server, and then tap the report name to open the report.</span></span>

    -   <span data-ttu-id="948cd-119">**Iniciar desde una biblioteca de documentos de SharePoint:** Vaya a una biblioteca de documentos de SharePoint que contenga informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y después pulse en el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="948cd-119">**Start from a SharePoint document library:** Browse to a SharePoint document library that contains [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports, and then tap the report name.</span></span> <span data-ttu-id="948cd-120">Puede ver e interactuar con el informe.</span><span class="sxs-lookup"><span data-stu-id="948cd-120">You can view and interact with the report.</span></span>

        > [!IMPORTANT]
        >  <span data-ttu-id="948cd-121"> Para el iPad, asegúrese de que la propiedad **Exploración privada** de Safari esté desactivada.</span><span class="sxs-lookup"><span data-stu-id="948cd-121">For the iPad, ensure that the **Private Browsing** property for Safari is turned off.</span></span>

    -   <span data-ttu-id="948cd-122">**Elemento web de SharePoint:** Si el elemento web se agregó a una página de SharePoint, puede ver informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="948cd-122">**SharePoint web part:** If the web part has been added to a SharePoint page, you can view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports.</span></span>

3.  <span data-ttu-id="948cd-123">También puede abrir el informe en el dispositivo de Microsoft Surface utilizando el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="948cd-123">On your Microsoft Surface device, you can also open the report by using Report Manager.</span></span> <span data-ttu-id="948cd-124">Busque el directorio en el Administrador de informes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y, a continuación, puntee en el nombre del informe para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="948cd-124">Browse the directory in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager, and then tap the report name to open the report.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="948cd-125">No se admite ver informes del Administrador de informes en un iPad.</span><span class="sxs-lookup"><span data-stu-id="948cd-125">Viewing reports in Report Manager is not supported on an iPad.</span></span>

4.  <span data-ttu-id="948cd-126">Desplácese y haga zoom haciendo lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="948cd-126">Scroll and zoom by doing the following.</span></span>

    -   <span data-ttu-id="948cd-127">Para desplazar el informe, arrastre el dedo por la pantalla (hacia arriba, hacia abajo, a la izquierda o a la derecha).</span><span class="sxs-lookup"><span data-stu-id="948cd-127">To scroll the report, drag your finger across the screen (up, down, left or right).</span></span> <span data-ttu-id="948cd-128">Este es el gesto de deslizar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="948cd-128">This is the swipe gesture.</span></span>

    -   <span data-ttu-id="948cd-129">Para acercar, coloque dos dedos sobre la pantalla y sepárelos.</span><span class="sxs-lookup"><span data-stu-id="948cd-129">To zoom in, place two fingers on the screen and separate the fingers.</span></span> <span data-ttu-id="948cd-130">Para alejar, coloque dos dedos sobre la pantalla y acérquelos.</span><span class="sxs-lookup"><span data-stu-id="948cd-130">To zoom out, place two fingers on the screen and move the fingers together.</span></span> <span data-ttu-id="948cd-131">Este es el gesto de alejar.</span><span class="sxs-lookup"><span data-stu-id="948cd-131">This is the pinch gesture.</span></span>

5.  <span data-ttu-id="948cd-132">Navegue e interactúe con el informe haciendo lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="948cd-132">Navigate and interact with the report by doing the following.</span></span>

    -   <span data-ttu-id="948cd-133">Contraiga y expanda elementos de informe, y filas y columnas asociadas a grupos, punteando en el signo más (+) para contraer y en el signo menos (-) para expandir.</span><span class="sxs-lookup"><span data-stu-id="948cd-133">Collapse and expand report items, and rows and columns that are associated with groups, by taping the plus (+) sign to collapse and the minus (-) sign to expand.</span></span>

    -   <span data-ttu-id="948cd-134">Alterne entre orden ascendente y descendente para las filas de una tabla o para las filas y columnas de una matriz punteando en el botón de ordenación.</span><span class="sxs-lookup"><span data-stu-id="948cd-134">Toggle between ascending and descending order for rows in a table or for rows and columns in a matrix, by tapping the sort button.</span></span> <span data-ttu-id="948cd-135">El botón de ordenación se encuentra normalmente en el encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="948cd-135">The sort button is usually located in the column header.</span></span>

    -   <span data-ttu-id="948cd-136">Expanda y contraiga el panel de parámetros punteando en el botón de flecha situado cerca de la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="948cd-136">Expand and collapse the parameter pane, by tapping the arrow button near the top of the report.</span></span>

    -   <span data-ttu-id="948cd-137">Seleccione un valor de parámetro punteando en el cuadro o el control situado junto al parámetro.</span><span class="sxs-lookup"><span data-stu-id="948cd-137">Select a parameter value by tapping the box or control next to the parameter.</span></span> <span data-ttu-id="948cd-138">Puntee en **Ver informe** para aplicar el valor del parámetro al informe.</span><span class="sxs-lookup"><span data-stu-id="948cd-138">Tap **View Report** to apply the parameter value to the report.</span></span>

    -   <span data-ttu-id="948cd-139">Busque en el contenido del informe punteando en el cuadro situado junto a **Buscar**, escribiendo un término de búsqueda y, a continuación, punteando en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="948cd-139">Search the report content by taping the box next to **Find**, typing a search term, and then taping **Find**.</span></span>

    -   <span data-ttu-id="948cd-140">Navegue por las páginas del informe punteando en los botones de navegación o punteando en el cuadro de texto situado junto a los botones y escribiendo el número de página.</span><span class="sxs-lookup"><span data-stu-id="948cd-140">Navigate the report pages by tapping the navigation buttons, or tapping the text box next to the buttons and typing the page number.</span></span>

    -   <span data-ttu-id="948cd-141">Navegue a direcciones URL punteando en los hipervínculos que se han agregado a elementos de informe como cuadros de texto, imágenes, gráficos y medidores.</span><span class="sxs-lookup"><span data-stu-id="948cd-141">Navigate to URLs by taping hyperlinks that have been added to report items such as text boxes, images, charts, and gauges.</span></span>

    -   <span data-ttu-id="948cd-142">Exporte el informe punteando en el icono del **menú desplegable Exportar** y punteando después en un formato de archivo.</span><span class="sxs-lookup"><span data-stu-id="948cd-142">Export the report by tapping the icon for the **Export drop down menu** and then tapping a file format.</span></span>

        -   <span data-ttu-id="948cd-143">Si está viendo el informe en un dispositivo de Microsoft Surface, puede exportar el informe a uno de los siguientes formatos.</span><span class="sxs-lookup"><span data-stu-id="948cd-143">If you're viewing the report on a Microsoft Surface device, you can export the report to one of the following formats.</span></span>

            -   <span data-ttu-id="948cd-144">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="948cd-144">XML file with report data</span></span>

            -   <span data-ttu-id="948cd-145">CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="948cd-145">CSV (comma delimited)</span></span>

            -   <span data-ttu-id="948cd-146">PDF</span><span class="sxs-lookup"><span data-stu-id="948cd-146">PDF</span></span>

            -   <span data-ttu-id="948cd-147">MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="948cd-147">MHTML (web archive)</span></span>

            -   <span data-ttu-id="948cd-148">Excel</span><span class="sxs-lookup"><span data-stu-id="948cd-148">Excel</span></span>

            -   <span data-ttu-id="948cd-149">TIFF</span><span class="sxs-lookup"><span data-stu-id="948cd-149">TIFF</span></span>

            -   <span data-ttu-id="948cd-150">Word</span><span class="sxs-lookup"><span data-stu-id="948cd-150">Word</span></span>

        -   <span data-ttu-id="948cd-151">Si está viendo el informe en un iPad, puede exportarlo como un archivo TIFF o PDF.</span><span class="sxs-lookup"><span data-stu-id="948cd-151">If you're viewing the report on an iPad, you can export the report as a TIFF or PDF file.</span></span>

## <a name="authentication"></a><span data-ttu-id="948cd-152">Authentication</span><span class="sxs-lookup"><span data-stu-id="948cd-152">Authentication</span></span>
 <span data-ttu-id="948cd-153">La autenticación RSWindowsNTLM y la autenticación RSWindowsBasic funcionan con [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en modo nativo y el iPad.</span><span class="sxs-lookup"><span data-stu-id="948cd-153">RSWindowsNTLM authentication and RSWindowsBasic authentication work with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode and the iPad.</span></span>

 <span data-ttu-id="948cd-154">En general, se recomienda no utilizar RSWindowsBasic en entornos sin conexión https, porque este tipo de autenticación no proporciona confidencialidad para las credenciales transmitidas.</span><span class="sxs-lookup"><span data-stu-id="948cd-154">In general, it is recommended that RSWindowsBasic is not used in non-https environments because this type of authentication provides no confidentiality for the transmitted credentials.</span></span>

 <span data-ttu-id="948cd-155">Para obtener más información sobre las autenticaciones RSWindowsNTLM y RSWindowsBasic, vea [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="948cd-155">For more information about RSWindowsNTLM and RSWindowsBasic authentication, see [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span></span>

## <a name="uploading-reports"></a><span data-ttu-id="948cd-156">Cargar informes</span><span class="sxs-lookup"><span data-stu-id="948cd-156">Uploading Reports</span></span>
 <span data-ttu-id="948cd-157">Puede publicar informes desde un dispositivo de Microsoft Surface mediante uno de los métodos siguientes si dispone de los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="948cd-157">You can publish reports from a Microsoft Surface device using one of the following methods, if you have the appropriate permissions.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="948cd-158">Estos métodos no se admiten en el iPad.</span><span class="sxs-lookup"><span data-stu-id="948cd-158">These methods are not supported on the iPad.</span></span>

-   <span data-ttu-id="948cd-159">Cargar un archivo de definición de informe (.rdl) en una biblioteca de documentos de SharePoint abriendo la biblioteca y punteando en **Cargar documento**.</span><span class="sxs-lookup"><span data-stu-id="948cd-159">Upload a report definition file (.rdl) to a SharePoint document library by opening the library and tapping **Upload Document**.</span></span>

-   <span data-ttu-id="948cd-160">Cargar un archivo de definición de informe en la base de datos del servidor de informes abriendo el Administrador de informes y punteando en **Cargar archivo**.</span><span class="sxs-lookup"><span data-stu-id="948cd-160">Upload a report definition file to the report server database by opening Report Manager and tapping **Upload File**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="948cd-161">Información adicional</span><span class="sxs-lookup"><span data-stu-id="948cd-161">Additional Information</span></span>
 <span data-ttu-id="948cd-162">Para obtener más información acerca de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y los exploradores admitidos, vea:</span><span class="sxs-lookup"><span data-stu-id="948cd-162">For more information on [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and supported browsers, see:</span></span>

-   [<span data-ttu-id="948cd-163">Planeación de la compatibilidad con exploradores de Reporting Services y Power View &#40;Reporting Services 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="948cd-163">Planning for Reporting Services and Power View Browser Support &#40;Reporting Services 2014&#41;</span></span>](../../2014/reporting-services/browser-support-for-reporting-services-and-power-view.md)

 <span data-ttu-id="948cd-164">Para obtener más información acerca de Microsoft Business Intelligence y los dispositivos móviles, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="948cd-164">For more information on Microsoft Business Intelligence and Mobile devices, see the following:</span></span>

-   <span data-ttu-id="948cd-165">[Información general de los dispositivos móviles y SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161351(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="948cd-165">[Overview of mobile devices and SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161351(v=office.15).aspx).</span></span>

-   <span data-ttu-id="948cd-166">[Exploradores de dispositivos móviles admitidos en SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161353(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="948cd-166">[Supported mobile device browsers in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161353(v=office.15).aspx).</span></span>

-   <span data-ttu-id="948cd-167">[Ver informes y cuadros de mandos en dispositivos iPad de Apple (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) ( https://technet.microsoft.com/library/hh697482.aspx) .</span><span class="sxs-lookup"><span data-stu-id="948cd-167">[Viewing reports and scorecards on Apple iPad devices (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) (https://technet.microsoft.com/library/hh697482.aspx).</span></span>

-   <span data-ttu-id="948cd-168">[Ver informes de Reporting Services en un iPad (vídeo)](https://technet.microsoft.com/sqlserver/jj873792.aspx) ( https://technet.microsoft.com/sqlserver/jj873792.aspx) .</span><span class="sxs-lookup"><span data-stu-id="948cd-168">[Viewing Reporting Services Reports on an iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) (https://technet.microsoft.com/sqlserver/jj873792.aspx).</span></span>

-   [<span data-ttu-id="948cd-169">Ver informes de Reporting Services en un dispositivo Microsoft Surface RT (vídeo)</span><span class="sxs-lookup"><span data-stu-id="948cd-169">Viewing Reporting Services Reports on a Microsoft Surface RT Device (video)</span></span>](https://technet.microsoft.com/sqlserver/dn146017)


