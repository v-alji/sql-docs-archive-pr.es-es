---
title: Agregar tipos de contenido del servidor de informes a una biblioteca (Reporting Services en el modo integrado de SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ac9136c8-9ef4-484c-8e9d-05008a186db5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e0ee56c235a54920fba5389a61f300eeaa65329
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749198"
---
# <a name="add-report-server-content-types-to-a-library-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="6c04b-102">Agregar tipos de contenido del servidor de informes a una biblioteca (Reporting Services en el modo integrado de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6c04b-102">Add Report Server Content Types to a Library (Reporting Services in SharePoint Integrated Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="6c04b-103">proporciona tipos de contenido de SharePoint predefinidos que se usan para administrar archivos de orígenes de datos compartidos (.rsds), modelos de informe (.smdl) y archivos de definición de informe (.rdl) del Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="6c04b-103">provides predefined SharePoint content types that are used to manage shared data source (.rsds) files, report models (.smdl), and Report Builder report definition (.rdl) files.</span></span> <span data-ttu-id="6c04b-104">Al agregar un tipo de contenido **Informe del Generador de informes**, **Modelo de informe**y **Origen de datos de informe** a una biblioteca se habilita el comando **Nuevo** para que pueda crear nuevos documentos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="6c04b-104">Adding a **Report Builder Report**, **Report Model**, and **Report Data Source** content type to a library enables the **New** command so that you can create new documents of that type.</span></span>  
  
 <span data-ttu-id="6c04b-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="6c04b-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>  
  
 <span data-ttu-id="6c04b-106">Para agregar tipos de contenido a una biblioteca, debe ser administrador del sitio o disponer del nivel de permiso Control total.</span><span class="sxs-lookup"><span data-stu-id="6c04b-106">To add content types to a library, you must be a site administrator or have Full Control level of permission.</span></span>  
  
 <span data-ttu-id="6c04b-107">Los tipos de contenido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y su administración se habilitarán automáticamente en todas las bibliotecas de documentos de las colecciones de sitios existentes creadas a partir de las siguientes plantillas de sitio de **Centro de Business Intelligence** .</span><span class="sxs-lookup"><span data-stu-id="6c04b-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types and content type management will automatically be enabled in all document libraries for existing site collections created from the following **Business Intelligence Center** site template.</span></span>  
  
 <span data-ttu-id="6c04b-108">Los sitios creados después de la integración de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] no tendrán habilitados los tipos de contenido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c04b-108">Sites created after the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration will not have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types enabled.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="6c04b-109">Si **no** ha configurado previamente los tipos de contenido de una biblioteca, habilite primero la administración de tipos de contenido y, a continuación, habilite los tipos de contenido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c04b-109">If you have **not** previously configured content types for a library, first enable management of content types, then enable the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="6c04b-110">Vea los procedimientos para habilitar la administración de tipos de contenido en una única biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="6c04b-110">See the procedures on enabling content type management in a single document library.</span></span>  
  
 <span data-ttu-id="6c04b-111">**Vídeo corto:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w) (Habilitación de tipos de contenido en SharePoint2010.wmv).</span><span class="sxs-lookup"><span data-stu-id="6c04b-111">**Short video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span></span>  
  
 <span data-ttu-id="6c04b-112">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="6c04b-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="6c04b-113">Habilitar tipos de contenido en todas las bibliotecas de documentos de un centro de inteligencia empresarial existente</span><span class="sxs-lookup"><span data-stu-id="6c04b-113">Enable content types in all document libraries in an existing BI center</span></span>](#bkmk_enable_all)  
  
-   [<span data-ttu-id="6c04b-114">Para habilitar la administración de tipos de contenido para una sola biblioteca de documentos (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6c04b-114">To enable content type management for a single document library (SharePoint 2013)</span></span>](#bkmk_enable_content_management)  
  
-   [<span data-ttu-id="6c04b-115">Para agregar tipos de contenido de Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6c04b-115">To add Reporting Services content types (SharePoint 2013)</span></span>](#bkmk_add_single)  
  
-   [<span data-ttu-id="6c04b-116">Para habilitar la administración de tipos de contenido para una sola biblioteca de documentos (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6c04b-116">To enable content type management for a single document library (SharePoint 2010)</span></span>](#bkmk_enable_content_management_2010)  
  
-   [<span data-ttu-id="6c04b-117">Para agregar tipos de contenido del servidor de informes (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6c04b-117">To add report server content types (SharePoint 2010)</span></span>](#bkmk_add_single_2010)  
  
-   [<span data-ttu-id="6c04b-118">Para habilitar los tipos de contenido y la administración de contenido para varios sitios de BI</span><span class="sxs-lookup"><span data-stu-id="6c04b-118">To enable Content types and content management for multiple BI sites</span></span>](#bkmk_enable_multiple_sites)  
  
##  <a name="enable-content-types-in-all-document-libraries-in-an-existing-bi-center"></a><a name="bkmk_enable_all"></a> <span data-ttu-id="6c04b-119">Habilitar tipos de contenido en todas las bibliotecas de documentos de un Centro de inteligencia empresarial</span><span class="sxs-lookup"><span data-stu-id="6c04b-119">Enable content types in all document libraries in an existing BI center</span></span>  
  
1.  <span data-ttu-id="6c04b-120">Para habilitar los tipos de contenido y la administración de contenido en todas las bibliotecas de documentos de un sitio de un **Centro de inteligencia empresarial** existente, puede alternar la característica de integración de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c04b-120">To enable the content types and content management in all document libraries in an existing **Business Intelligence Center** site, you can toggle the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration feature.</span></span>  
  
2.  <span data-ttu-id="6c04b-121">Vaya a **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-121">Go to **Site settings**.</span></span>  
  
    -   <span data-ttu-id="6c04b-122">En SharePoint 2013, haga clic en el icono de **Configuración** .</span><span class="sxs-lookup"><span data-stu-id="6c04b-122">In SharePoint 2013, click the **Settings** icon.</span></span> <span data-ttu-id="6c04b-123">![Configuración de SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Configuración de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="6c04b-123">![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings")</span></span>  
  
    -   <span data-ttu-id="6c04b-124">En SharePoint 2010, haga clic en **Acciones del sitio**y, a continuación, haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-124">In SharePoint 2010, click **Site Actions**, then click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="6c04b-125">Haga clic en características de la **colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-125">Click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="6c04b-126">Busque la **Característica de integración del servidor de informes** y haga clic en **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-126">Find the **Report Server Integration Feature** and click **Deactivate**.</span></span>  
  
     <span data-ttu-id="6c04b-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span><span class="sxs-lookup"><span data-stu-id="6c04b-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span></span>  
  
5.  <span data-ttu-id="6c04b-128">Actualice el explorador y haga clic en **Activar** junto a la **Característica de integración del servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-128">Refresh the browser then click **Activate** for the **Report Server Integration Feature**.</span></span>  
  
    <span data-ttu-id="6c04b-129">![Desactivación](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span><span class="sxs-lookup"><span data-stu-id="6c04b-129">![Deactivate](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2013"></a><a name="bkmk_enable_content_management"></a><span data-ttu-id="6c04b-130">Para habilitar la administración de tipos de contenido para una sola biblioteca de documentos (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6c04b-130">To enable content type management for a single document library (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="6c04b-131">Abra la biblioteca para la que desee habilitar varios tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="6c04b-131">Open the library for which you want to enable multiple content types.</span></span>  
  
2.  <span data-ttu-id="6c04b-132">Haga clic en **Biblioteca** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="6c04b-132">Click **Library** in the ribbon.</span></span>  
  
     <span data-ttu-id="6c04b-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="6c04b-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="6c04b-134">En la cinta **Biblioteca** , haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-134">On the **Library** ribbon, click **Library Settings**.</span></span> <span data-ttu-id="6c04b-135">Si no ve **Configuración de la biblioteca** o si el botón está deshabilitado, significa que no tiene permiso para configurar la biblioteca, incluidos los tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="6c04b-135">If you do not see **Library Settings** or the button is disabled, you do not have permission to configure library settings, including content types.</span></span>  
  
     <span data-ttu-id="6c04b-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span><span class="sxs-lookup"><span data-stu-id="6c04b-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span></span>  
  
4.  <span data-ttu-id="6c04b-137">En la sección **Configuración general** , haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-137">In the **General Settings** section, click **Advanced settings**.</span></span>  
  
     <span data-ttu-id="6c04b-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span><span class="sxs-lookup"><span data-stu-id="6c04b-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span></span>  
  
5.  <span data-ttu-id="6c04b-139">En la sección **Tipos de contenido** , seleccione **Sí** para permitir la administración de tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="6c04b-139">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="6c04b-140">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-140">Click **OK**.</span></span>  
  
##  <a name="to-add-reporting-services-content-types-sharepoint-2013"></a><a name="bkmk_add_single"></a> <span data-ttu-id="6c04b-141">Para agregar tipos de contenido de Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6c04b-141">To add Reporting Services content types (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="6c04b-142">Abra la biblioteca para la que desee agregar tipos de contenido de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="6c04b-142">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="6c04b-143">En la cinta de opciones, haga clic en **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-143">On the ribbon, click **Library**.</span></span>  
  
3.  <span data-ttu-id="6c04b-144">Haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-144">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="6c04b-145">En **Tipos de contenido**, haga clic en **Agregar a partir de tipos de contenido de sitio**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-145">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="6c04b-146">En **Seleccionar tipos de contenido de sitio**, seleccione **Tipos de contenido de SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-146">In **Select site content types from**, select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="6c04b-147">En la lista **Tipos de contenido de sitio disponibles** , haga clic en **Generador de informes**y, a continuación, haga clic en **Agregar** para mover el tipo de contenido seleccionado a la lista **Tipos de contenido que agregar** .</span><span class="sxs-lookup"><span data-stu-id="6c04b-147">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="6c04b-148">Para agregar los tipos de contenido **Modelo de informe** y **Origen de datos de informe** , repita el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="6c04b-148">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="6c04b-149">Cuando termine de agregar tipos de contenido, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-149">When you finish adding content types, click **OK**.</span></span>  
  
9. > [!NOTE]  
    >  <span data-ttu-id="6c04b-150"> Si el [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] grupo de tipos de contenido **Tipos de contenido de SQL Server Reporting Services** de no está visible en la página **Agregar tipos de contenido** , se cumple una de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c04b-150">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content type group **SQL Server Reporting Services Content Types** is not visible on the **Add Content Types** page, one of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="6c04b-151">No se ha instalado el complemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6c04b-151">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products has not been installed.</span></span> <span data-ttu-id="6c04b-152">Para obtener más información, vea [instalar o desinstalar el complemento de Reporting Services para sharepoint &#40;sharepoint 2010 y sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="6c04b-152">For more information, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span> <span data-ttu-id="6c04b-153">El tema contiene información sobre la instalación del complemento y la ejecución paso a paso en una instalación solo de archivos del complemento para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="6c04b-153">The topic includes information on installing the add-in and stepping through a files only installation of the add-in to work around issues.</span></span>  
  
    -   <span data-ttu-id="6c04b-154">Se instala el complemento, pero la característica de colección de sitios **Característica de integración del servidor de informes** no está activa.</span><span class="sxs-lookup"><span data-stu-id="6c04b-154">The add-in is installed but the site collection feature **Report Server Integration Feature** is not active.</span></span> <span data-ttu-id="6c04b-155">Compruebe la característica de colección de sitios en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-155">Verify the site collection feature in **Site Settings**.</span></span>  
  
    -   <span data-ttu-id="6c04b-156">Ya se han agregado a la biblioteca todos los tipos de contenido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c04b-156">All of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types have already been added to the library.</span></span> <span data-ttu-id="6c04b-157">Si todos los tipos de contenido forman parte de una biblioteca, el grupo se quita de la página **Agregar tipos de contenido** .</span><span class="sxs-lookup"><span data-stu-id="6c04b-157">If all the content types are part of a library, then the group is removed from the **Add Content Types** page.</span></span> <span data-ttu-id="6c04b-158">Si elimina uno o varios de los tipos de contenido de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , el grupo **Tipos de contenido de SQL Server Reporting Services** será visible en la página **Agregar tipos de contenido** .</span><span class="sxs-lookup"><span data-stu-id="6c04b-158">If you delete one or more of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types, then the group **SQL Server Reporting Services Content Types** will be visible on the **Add Content Types** page.</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2010"></a><a name="bkmk_enable_content_management_2010"></a><span data-ttu-id="6c04b-159">Para habilitar la administración de tipos de contenido para una sola biblioteca de documentos (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6c04b-159">To enable content type management for a single document library (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="6c04b-160">Abra la biblioteca para la que desee habilitar varios tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="6c04b-160">Open the library for which you want to enable multiple content types.</span></span> <span data-ttu-id="6c04b-161">En la barra de menús de la biblioteca, debería ver los siguientes menús: **Nuevo**, **Cargar**, **Acciones**y **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-161">On the library menu bar, you should see the following menus: **New**, **Upload**, **Actions**, and **Settings**.</span></span> <span data-ttu-id="6c04b-162">Si no ve **Configuración**, significa que no tiene permiso para agregar un tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="6c04b-162">If you do not see **Settings**, you do not have permission to add a content type.</span></span>  
  
2.  <span data-ttu-id="6c04b-163">En la cinta **Herramientas de bibliotecas** , haga clic en **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-163">On the **Library Tools** ribbon, click **Library**.</span></span>  
  
     <span data-ttu-id="6c04b-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="6c04b-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="6c04b-165">En el grupo de la cinta de opciones de **Configuración** , haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-165">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="6c04b-166">En **Configuración general**, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-166">Under **General Settings**, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="6c04b-167">En la sección **Tipos de contenido** , seleccione **Sí** para permitir la administración de tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="6c04b-167">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="6c04b-168">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-168">Click **OK**.</span></span>  
  
##  <a name="to-add-report-server-content-types-sharepoint-2010"></a><a name="bkmk_add_single_2010"></a><span data-ttu-id="6c04b-169">Para agregar tipos de contenido del servidor de informes (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="6c04b-169">To add report server content types (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="6c04b-170">Abra la biblioteca para la que desee agregar tipos de contenido de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="6c04b-170">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="6c04b-171">En las pestañas de la cinta de opciones de **Herramientas de biblioteca** , haga clic en la pestaña **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-171">On the **Library Tools** ribbon tabs, click the **Library tab**.</span></span>  
  
3.  <span data-ttu-id="6c04b-172">En el grupo de la cinta de opciones de **Configuración** , haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-172">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="6c04b-173">En **Tipos de contenido**, haga clic en **Agregar a partir de tipos de contenido de sitio**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-173">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="6c04b-174">En la sección **Seleccionar tipos de contenido** , en **Seleccionar tipos de contenido de sitio**, haga clic en la flecha para seleccionar **Tipos de contenido de SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-174">In the **Select Content Types** section, in **Select site content types from**, click the arrow to select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="6c04b-175">En la lista **Tipos de contenido de sitio disponibles** , haga clic en **Generador de informes**y, a continuación, haga clic en **Agregar** para mover el tipo de contenido seleccionado a la lista **Tipos de contenido que agregar** .</span><span class="sxs-lookup"><span data-stu-id="6c04b-175">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="6c04b-176">Para agregar los tipos de contenido **Modelo de informe** y **Origen de datos de informe** , repita el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="6c04b-176">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="6c04b-177">Cuando termine de agregar tipos de contenido, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-177">When you finish adding content types, click **OK**.</span></span>  
  
##  <a name="to-enable-content-types-and-content-management-for-multiple-bi-sites"></a><a name="bkmk_enable_multiple_sites"></a><span data-ttu-id="6c04b-178">Para habilitar los tipos de contenido y la administración de contenido para varios sitios de BI</span><span class="sxs-lookup"><span data-stu-id="6c04b-178">To enable Content types and content management for multiple BI sites</span></span>  
  
1.  <span data-ttu-id="6c04b-179">En los servidores de informes de SQL Server Reporting Services 2008 y 2008 R2, puede habilitar los tipos de contenido y la administración de contenido para varios sitios de Centro de inteligencia empresarial:</span><span class="sxs-lookup"><span data-stu-id="6c04b-179">For SQL Server Reporting Services 2008 and 2008 R2 report servers, you can enable content types and content management for multiple Business Intelligence Center sites:</span></span>  
  
2.  <span data-ttu-id="6c04b-180">En Administración central de SharePoint, haga clic en la **Configuración de aplicaciones generales**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-180">In SharePoint Central Administration, click **General Applications settings**.</span></span> <span data-ttu-id="6c04b-181">En la sección **SQL Server Reporting Services (2008 y 2008 R2)** , haga clic en **Integración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-181">In the **SQL Server Reporting Services (2008 and 2008 R2)** section, click **Reporting Services Integration**.</span></span>  
  
     <span data-ttu-id="6c04b-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span><span class="sxs-lookup"><span data-stu-id="6c04b-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span></span>  
  
3.  <span data-ttu-id="6c04b-183">Haga clic en **Activar características en todas las colecciones de sitios existentes**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-183">Click **Activate feature in all exciting site collections**.</span></span>  
  
     <span data-ttu-id="6c04b-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span><span class="sxs-lookup"><span data-stu-id="6c04b-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span></span>  
  
4.  <span data-ttu-id="6c04b-185">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c04b-185">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c04b-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c04b-186">See Also</span></span>  
 <span data-ttu-id="6c04b-187">[Referencia de permisos de sitio y lista de SharePoint para los elementos del servidor de informes](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="6c04b-187">[SharePoint Site and List Permission Reference for Report Server Items](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="6c04b-188">Iniciar Generador de informes &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="6c04b-188">Start Report Builder &#40;Report Builder&#41;</span></span>](report-builder/start-report-builder.md)  
  
  
