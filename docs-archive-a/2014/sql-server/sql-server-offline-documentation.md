---
title: Documentos sin conexión para SQL Server 2014
description: Obtenga información sobre cómo instalar la documentación sin conexión para SQL Server 2014. Utilice SQL Server Management Studio (SSMS) para ver el contenido sin conexión.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672367"
---
# <a name="install-sql-server-2014-offline-documentation"></a><span data-ttu-id="a9956-104">Instalación de la documentación sin conexión de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a9956-104">Install SQL Server 2014 offline documentation</span></span>

<span data-ttu-id="a9956-105">En este artículo se describe cómo descargar y ver el contenido de SQL Server 2014 sin conexión.</span><span class="sxs-lookup"><span data-stu-id="a9956-105">This article describes how to download and view offline SQL Server 2014 content.</span></span> <span data-ttu-id="a9956-106">El contenido sin conexión le permite acceder a la documentación sin conexión a Internet (aunque se necesita una conexión a Internet para descargarla).</span><span class="sxs-lookup"><span data-stu-id="a9956-106">Offline content enables you to access the documentation without an internet connection (although an internet connection is initially required to download it).</span></span>

<span data-ttu-id="a9956-107">La técnica implica el uso del menú **ayuda** de SQL Server Management Studio (SSMS) para tener acceso a la utilidad del visor de ayuda (HlpViewer.exe).</span><span class="sxs-lookup"><span data-stu-id="a9956-107">The technique involves using the **Help** menu of SQL Server Management Studio (SSMS), to access the Help Viewer utility (HlpViewer.exe).</span></span>

<span data-ttu-id="a9956-108">La documentación sin conexión está disponible para las versiones de SQL Server en el intervalo de 2012-2019 y quizás también para versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a9956-108">Offline documentation is available for versions of SQL Server in the range of 2012-2019, and perhaps for additional later versions too.</span></span> <span data-ttu-id="a9956-109">Aunque puede ver el contenido de las [versiones anteriores en línea](https://docs.microsoft.com/previous-versions/sql/), una opción sin conexión proporciona una manera cómoda de acceder al contenido anterior.</span><span class="sxs-lookup"><span data-stu-id="a9956-109">Although you can view content for [previous versions online](https://docs.microsoft.com/previous-versions/sql/), an offline option provides a convenient way to access the older content.</span></span>

- [<span data-ttu-id="a9956-110">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a9956-110">SQL Server 2014</span></span>](#sql-server-2014-offline-content)
- [<span data-ttu-id="a9956-111">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a9956-111">SQL Server 2012</span></span>](#sql-server-2012-offline-content)

<span data-ttu-id="a9956-112">Para SQL Server 2016 y versiones posteriores, consulte su documentación específica de la versión para obtener información sobre cómo esas versiones controlan su documentación sin conexión.</span><span class="sxs-lookup"><span data-stu-id="a9956-112">For SQL Server 2016 and later versions, see their version-specific documentation to learn how those versions handle their offline documentation.</span></span>

## <a name="sql-server-2014-offline-content"></a><span data-ttu-id="a9956-113">Contenido sin conexión de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a9956-113">SQL Server 2014 offline content</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9956-114">El contenido de Transact-SQL de SQL 2014 solo está disponible sin conexión.</span><span class="sxs-lookup"><span data-stu-id="a9956-114">SQL 2014 Transact-SQL content is only available offline.</span></span>

<span data-ttu-id="a9956-115">Con los siguientes pasos se explica cómo cargar contenido sin conexión en SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="a9956-115">The following steps explain how to load offline content for SQL Server 2014.</span></span>

1. <span data-ttu-id="a9956-116">Descargue el contenido de la [Documentación del producto de Microsoft SQL Server 2014 para los entornos restringidos de firewall y proxy](https://www.microsoft.com/download/details.aspx?id=42557) del centro de descarga y guárdelo en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="a9956-116">Download the [Product Documentation for Microsoft SQL Server 2014 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=42557) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="a9956-117">Descomprima el archivo para ver el archivo *. MSHA* .</span><span class="sxs-lookup"><span data-stu-id="a9956-117">Unzip the file to view the *.msha* file.</span></span>

   ![Archivo de instalación de la documentación de Ayuda de SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. <span data-ttu-id="a9956-119">En SSMS, seleccione **Agregar y quitar contenido de la Ayuda** en el menú Ayuda.</span><span class="sxs-lookup"><span data-stu-id="a9956-119">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Agregar y quitar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="a9956-121">El Visor de Ayuda se abre en la pestaña Administrar contenido.</span><span class="sxs-lookup"><span data-stu-id="a9956-121">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="a9956-122">Para instalar el último contenido de Ayuda, seleccione **Disco** en Origen de la instalación y, después, haga clic en los puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="a9956-122">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Origen del disco de Administrar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="a9956-124">En Ruta de acceso del almacén local de la pestaña Administrar contenido, se muestra dónde se encuentra el contenido en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a9956-124">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="a9956-125">Para cambiar la ubicación, seleccione **Mover**, especifique otra ruta de carpeta en el campo **A** y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a9956-125">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="a9956-126">Si se produce un error en la instalación de la Ayuda después de cambiar la ruta de acceso del almacén local, cierre y vuelva a abrir el Visor de ayuda.</span><span class="sxs-lookup"><span data-stu-id="a9956-126">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="a9956-127">Compruebe que la nueva ubicación aparece en la ruta de acceso del almacén local y vuelva a intentar realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="a9956-127">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="a9956-128">Encuentre la carpeta donde se descomprimió el contenido.</span><span class="sxs-lookup"><span data-stu-id="a9956-128">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="a9956-129">Seleccione el archivo **HelpContentSetup.msha** en la carpeta y, después, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a9956-129">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Abrir el archivo Setup.msha del contenido de Ayuda de SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. <span data-ttu-id="a9956-131">Escriba *sql server 2014* en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a9956-131">Type in *sql server 2014* in the search bar.</span></span> <span data-ttu-id="a9956-132">Una vez que vea el contenido disponible de 2014, seleccione **Agregar** junto a cada paquete de contenido (libro) que desee instalar en el Visor de Ayuda y, a continuación, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a9956-132">Once you see the 2014 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Búsqueda de libros de SQL Server 2014 en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Libros de SQL Server 2014 sobre adición y actualización en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="a9956-135">Si el visor de ayuda se bloquea (se bloquea) mientras agrega contenido, cambie la línea de la caché de LastRefreshed = " \<mm/dd/yyyy> 00:00:00" en el archivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings en una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="a9956-135">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="a9956-136">Para obtener más información sobre este problema, vea [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio)(El Visor de Ayuda de Visual Studio se bloquea).</span><span class="sxs-lookup"><span data-stu-id="a9956-136">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="a9956-137">Puede comprobar si el contenido de SQL Server 2014 está instalado; para ello, busque *sql server 2014* en el panel de contenido de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a9956-137">You can verify that the SQL Server 2014 content installed by searching under the content pane on the left for *sql server 2014*.</span></span>

   ![Libros de SQL Server 2014 actualizados automáticamente](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a><span data-ttu-id="a9956-139">Contenido sin conexión de SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a9956-139">SQL Server 2012 offline content</span></span>

<span data-ttu-id="a9956-140">Con los siguientes pasos se explica cómo cargar contenido sin conexión en SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a9956-140">The following steps explain how to load offline content for SQL Server 2012</span></span>

1. <span data-ttu-id="a9956-141">Descargue el contenido de la [Documentación del producto de Microsoft SQL Server 2012 para los entornos restringidos de firewall y proxy](https://www.microsoft.com/download/details.aspx?id=35750) del centro de descarga y guárdelo en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="a9956-141">Download the [Product Documentation for Microsoft SQL Server 2012 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=35750) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="a9956-142">Descomprima el archivo para ver el archivo *. MSHA* .</span><span class="sxs-lookup"><span data-stu-id="a9956-142">Unzip the file to view the *.msha* file.</span></span>

   ![Archivo de instalación del contenido de Ayuda de SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. <span data-ttu-id="a9956-144">En SSMS, seleccione **Agregar y quitar contenido de la Ayuda** en el menú Ayuda.</span><span class="sxs-lookup"><span data-stu-id="a9956-144">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Agregar y quitar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="a9956-146">El Visor de Ayuda se abre en la pestaña Administrar contenido.</span><span class="sxs-lookup"><span data-stu-id="a9956-146">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="a9956-147">Para instalar el último contenido de Ayuda, seleccione **Disco** en Origen de la instalación y, después, haga clic en los puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="a9956-147">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Origen del disco de Administrar contenido en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="a9956-149">En Ruta de acceso del almacén local de la pestaña Administrar contenido, se muestra dónde se encuentra el contenido en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a9956-149">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="a9956-150">Para cambiar la ubicación, seleccione **Mover**, especifique otra ruta de carpeta en el campo **A** y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a9956-150">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="a9956-151">Si se produce un error en la instalación de la Ayuda después de cambiar la ruta de acceso del almacén local, cierre y vuelva a abrir el Visor de ayuda.</span><span class="sxs-lookup"><span data-stu-id="a9956-151">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="a9956-152">Compruebe que la nueva ubicación aparece en la ruta de acceso del almacén local y vuelva a intentar realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="a9956-152">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="a9956-153">Encuentre la carpeta donde se descomprimió el contenido.</span><span class="sxs-lookup"><span data-stu-id="a9956-153">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="a9956-154">Seleccione el archivo **HelpContentSetup.msha** en la carpeta y, después, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a9956-154">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Abrir el archivo Setup.msha del contenido de Ayuda de SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. <span data-ttu-id="a9956-156">Escriba *sql server 2012* en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a9956-156">Type in *sql server 2012* in the search bar.</span></span> <span data-ttu-id="a9956-157">Una vez que vea el contenido disponible de 2012, seleccione **Agregar** junto a cada paquete de contenido (libro) que desee instalar en el Visor de Ayuda y, a continuación, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a9956-157">Once you see the 2012 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Búsqueda de libros de SQL Server 2012 en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Libros de SQL Server 2012 sobre adición y actualización en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="a9956-160">Si el visor de ayuda se bloquea (se bloquea) mientras agrega contenido, cambie la línea de la caché de LastRefreshed = " \<mm/dd/yyyy> 00:00:00" en el archivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings o HlpViewer_VisualStudiox_en-US. Settings en una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="a9956-160">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="a9956-161">Para obtener más información sobre este problema, vea [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio)(El Visor de Ayuda de Visual Studio se bloquea).</span><span class="sxs-lookup"><span data-stu-id="a9956-161">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="a9956-162">Puede comprobar si el contenido de SQL Server 2012 está cargado; para ello, busque *sql server 2012* en el panel de contenido de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a9956-162">You can verify that the SQL Server 2012 content is loaded by searching under the content pane on the left for *sql server 2012*.</span></span>

   ![Documentación de SQL Server 2012 actualizada automáticamente](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a><span data-ttu-id="a9956-164">Visualización de la documentación sin conexión</span><span class="sxs-lookup"><span data-stu-id="a9956-164">View offline documentation</span></span>

<span data-ttu-id="a9956-165">Puede ver SQL Server contenido de la ayuda mediante el menú **ayuda** de la versión más reciente de SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a9956-165">You can view SQL Server help content using the **HELP** menu in the latest version of SQL Server Management Studio (SSMS).</span></span>

### <a name="view-offline-help-content-in-ssms"></a><span data-ttu-id="a9956-166">Visualización del contenido de la Ayuda sin conexión en SSMS</span><span class="sxs-lookup"><span data-stu-id="a9956-166">View offline help content in SSMS</span></span>

<span data-ttu-id="a9956-167">Para ver la Ayuda instalada en SSMS, seleccione **Iniciar en el Visor de Ayuda** en el menú Ayuda para iniciar el Visor de Ayuda.</span><span class="sxs-lookup"><span data-stu-id="a9956-167">To view the installed help in SSMS, select **Launch in Help Viewer** from the Help menu, to launch the Help Viewer.</span></span>

   ![Iniciar en el Visor de Ayuda](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

<span data-ttu-id="a9956-169">Este se abrirá en la pestaña Administrar contenido, con la tabla de contenido de la Ayuda instalada en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a9956-169">Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane.</span></span> <span data-ttu-id="a9956-170">Seleccione los artículos de la tabla de contenido para que se muestren en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="a9956-170">select articles in the table of contents to display them in the right pane.</span></span>

> [!Important]
> <span data-ttu-id="a9956-171">Si el panel de contenido no está visible, seleccione Contenido en el margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a9956-171">If the contents pane is not visible, select Contents on the left margin.</span></span> <span data-ttu-id="a9956-172">Seleccione el icono de marcador para mantener abierto el panel de contenido.</span><span class="sxs-lookup"><span data-stu-id="a9956-172">select the pushpin icon to keep the contents pane open.</span></span>  

   ![Visor de Ayuda con contenido](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
