---
title: Crear o personalizar una biblioteca de fuentes de distribución de datos (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feed library
- data feeds [Analysis Services with SharePoint]
ms.assetid: 699fbeb9-42ab-436b-beba-214db51ea3dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: b86f63c1af094ea9e8a2a1149debeac387bccbf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745422"
---
# <a name="create-or-customize-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="6cbe0-102">Crear o personalizar una biblioteca de fuentes de datos (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6cbe0-102">Create or Customize a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="6cbe0-103">Una *biblioteca de fuentes de distribución de datos* es una biblioteca de SharePoint especial que le permite registrarse y compartir los documentos (.atomsvc) de servicio de datos de Atom.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-103">A *data feed library* is a special-purpose SharePoint library that enables you to register and share Atom data service documents (.atomsvc).</span></span> <span data-ttu-id="6cbe0-104">En estos documentos se proporcionan fuentes de distribución de datos XML para libros [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] u otras aplicaciones cliente que admitan el formato de distribución de datos Atom.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-104">These documents provide XML data feeds to [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks or other client applications that support the Atom data feed format.</span></span> <span data-ttu-id="6cbe0-105">Una biblioteca de fuentes de distribución de datos es diferente de otras bibliotecas de SharePoint porque permite:</span><span class="sxs-lookup"><span data-stu-id="6cbe0-105">A data feed library is different from other SharePoint libraries because it gives you the ability to:</span></span>

-   <span data-ttu-id="6cbe0-106">Crear o modificar un *documento de servicio de datos*, que se usa para especificar una conexión HTTP a una fuente concreta.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-106">Create or edit a *data service document*, used to specify an HTTP connection to a specific feed.</span></span>

-   <span data-ttu-id="6cbe0-107">Compartir y administrar los documentos de servicio de datos en una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-107">Share and manage data service documents in a central location.</span></span>

-   <span data-ttu-id="6cbe0-108">Identifique visualmente los documentos de servicio de datos mediante un icono, para que pueda distinguir fácilmente los documentos de servicio de otros documentos almacenados en la misma biblioteca: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span><span class="sxs-lookup"><span data-stu-id="6cbe0-108">Visually identify data service documents by an icon, so that you can easily distinguish service documents from other documents stored in the same library: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span></span>

 <span data-ttu-id="6cbe0-109">Una biblioteca de fuentes de distribución de datos siempre contiene archivos de documentos de servicio de datos (.atomsvc) y nunca las propias fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-109">A data feed library always contains data service document (.atomsvc) files, and never the data feed itself.</span></span> <span data-ttu-id="6cbe0-110">A diferencia de una fuente de distribución de datos, que consta de datos XML estáticos, el documento de servicio de datos especifica una dirección URL para un servicio o aplicación que genera una fuente tras la solicitud, proporcionando información de conexión reutilizable para las operaciones de importación repetibles.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-110">Unlike a data feed, which consists of static XML data, the data service document specifies a URL to a service or application that generates a feed upon request, providing reusable connection information for repeatable import operations.</span></span>

 <span data-ttu-id="6cbe0-111">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="6cbe0-111">This topic contains the following sections:</span></span>

 [<span data-ttu-id="6cbe0-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6cbe0-112">Prerequisites</span></span>](#prereq)

 [<span data-ttu-id="6cbe0-113">Crear una nueva biblioteca de fuentes de distribución de datos</span><span class="sxs-lookup"><span data-stu-id="6cbe0-113">Create a New Data Feed Library</span></span>](#createlib)

 [<span data-ttu-id="6cbe0-114">Agregar el tipo de contenido de la fuente de distribución de datos a cualquier biblioteca</span><span class="sxs-lookup"><span data-stu-id="6cbe0-114">Add the Data Feed Content Type to Any Library</span></span>](#addtolib)

##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="6cbe0-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6cbe0-115">Prerequisites</span></span>
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="6cbe0-116">se debe activar para los sitios para los que vaya a crear la biblioteca de fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-116">feature integration must be activated for the sites for which you are creating the data feed library.</span></span> <span data-ttu-id="6cbe0-117">Si el tipo de plantilla de biblioteca de fuentes de distribución de datos no está disponible, probablemente se deba a que no se ha cumplido este requisito previo.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-117">If the data feed library template type is not available, the most likely cause is that this prerequisite has not been met.</span></span> <span data-ttu-id="6cbe0-118">Para obtener más información, vea [activar la integración de características de PowerPivot para colecciones de sitios en administración central](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="6cbe0-118">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>

 <span data-ttu-id="6cbe0-119">Debe ser propietario del sitio para crear la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-119">You must be a site owner to create the library.</span></span>

##  <a name="create-a-new-data-feed-library"></a><a name="createlib"></a> <span data-ttu-id="6cbe0-120">Crear una nueva biblioteca de fuentes de distribución de datos</span><span class="sxs-lookup"><span data-stu-id="6cbe0-120">Create a New Data Feed Library</span></span>
 <span data-ttu-id="6cbe0-121">Crear una biblioteca de fuentes de distribución de datos es el primer paso si se desea habilitar fuentes de distribución de datos para los libros de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cbe0-121">Creating a data feed library is the first step to enabling data feeds for [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span> <span data-ttu-id="6cbe0-122">Dado que una biblioteca de fuentes de distribución de datos proporciona las páginas de aplicación y administración para los documentos de servicio de datos, debe disponer de una para poder crear un documento nuevo.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-122">Because a data feed library provides application and management pages for data service documents, you must have this library in place before you can create a new document.</span></span>

 <span data-ttu-id="6cbe0-123">Una biblioteca de fuentes de distribución de datos se basa en una plantilla integrada y en un *tipo de contenido del documento de servicio de datos* preconfigurado que define las propiedades y comportamientos para un documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-123">A data feed library is based on a built-in template and a preconfigured *data service document content type* that defines properties and behaviors for a data service document.</span></span>

1.  <span data-ttu-id="6cbe0-124">Haga clic en **Acciones de sitio** en la esquina superior izquierda de la página.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-124">Click **Site Actions** at the top left corner of the page.</span></span>

2.  <span data-ttu-id="6cbe0-125">Haga clic en **más opciones**...</span><span class="sxs-lookup"><span data-stu-id="6cbe0-125">Click **More Options**...</span></span>

3.  <span data-ttu-id="6cbe0-126">En Bibliotecas, haga clic en **Biblioteca de fuentes de distribución de datos**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-126">Under Libraries, click **Data Feed Library**.</span></span>

4.  <span data-ttu-id="6cbe0-127">Escriba el nombre, la descripción y las preferencias de la versión e inicio.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-127">Type the name, description, launch, and version preferences.</span></span> <span data-ttu-id="6cbe0-128">Incluya información descriptiva que ayude a los usuarios a identificar esta biblioteca como almacenamiento para los documentos de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-128">Include descriptive information to help users identify this library as storage for data service documents.</span></span>

5.  <span data-ttu-id="6cbe0-129">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-129">Click **Create**.</span></span>

 <span data-ttu-id="6cbe0-130">Un vínculo a la biblioteca de fuentes de distribución de datos aparecerá en el panel Inicio rápido de navegación para el sitio actual.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-130">A link to the data feed library will appear in the navigation Quick Launch pane for the current site.</span></span>

 <span data-ttu-id="6cbe0-131">Después de crear una biblioteca, puede utilizarla para crear documentos de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-131">After you create a library, you can use it to create data service documents.</span></span> <span data-ttu-id="6cbe0-132">Para obtener más información, vea [usar fuentes de datos &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="6cbe0-132">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>

##  <a name="add-the-data-feed-content-type-to-any-library"></a><a name="addtolib"></a> <span data-ttu-id="6cbe0-133">Agregar el tipo de contenido de la fuente de distribución de datos a una biblioteca</span><span class="sxs-lookup"><span data-stu-id="6cbe0-133">Add the Data Feed Content Type to Any Library</span></span>
 <span data-ttu-id="6cbe0-134">Si no desea crear una biblioteca de fuentes de distribución de datos dedicada, pero sigue deseando crear y administrar los documentos de servicio de datos desde un sitio de SharePoint, puede agregar y configurar manualmente el tipo de contenido del documento de servicio de datos para cualquier biblioteca que use para compartir los archivos de documento de servicio de datos (.atomsvc).</span><span class="sxs-lookup"><span data-stu-id="6cbe0-134">If you do not want to create a dedicated data feed library, but you still want to create and manage data service documents from a SharePoint site, you can manually add and configure the data service document content type for any library that you will use to share data service document (.atomsvc) files.</span></span>

 <span data-ttu-id="6cbe0-135">Para agregar y configurar un tipo de contenido, debe tener al menos el permiso Administrar listas.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-135">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="6cbe0-136">Este permiso se integra en el nivel de permisos de diseño y superiores.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-136">This permission is built into the Design permission level and above.</span></span>

 <span data-ttu-id="6cbe0-137">Los siguientes pasos se deben repetir para cada biblioteca en la que desee crear o modificar los documentos de registro de fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-137">The following steps must be repeated for each library in which you want to create or edit data feed registration documents.</span></span>

#### <a name="step-1-enable-content-type-management"></a><span data-ttu-id="6cbe0-138">Paso 1: habilitar la administración de tipos de contenido</span><span class="sxs-lookup"><span data-stu-id="6cbe0-138">Step 1: Enable Content Type Management</span></span>

1.  <span data-ttu-id="6cbe0-139">Abra la biblioteca de documentos para la que desee habilitar varios tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-139">Open the document library for which you want to enable multiple content types.</span></span>

2.  <span data-ttu-id="6cbe0-140">En la cinta de opciones de SharePoint, en Herramientas de biblioteca, haga clic en **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-140">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>

3.  <span data-ttu-id="6cbe0-141">Haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-141">Click **Settings**.</span></span>

4.  <span data-ttu-id="6cbe0-142">Haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-142">Click **Library Settings**.</span></span>

5.  <span data-ttu-id="6cbe0-143">En Configuración general, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-143">In General Settings, click **Advanced settings**.</span></span>

6.  <span data-ttu-id="6cbe0-144">En Tipos de contenido, en la sección "¿Desea permitir la administración de tipos de contenido?"</span><span class="sxs-lookup"><span data-stu-id="6cbe0-144">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="6cbe0-145">haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-145">section, click **Yes**.</span></span>

7.  <span data-ttu-id="6cbe0-146">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-146">Click **OK**.</span></span>

#### <a name="step-2-add-the-data-service-document-content-type"></a><span data-ttu-id="6cbe0-147">Paso 2: agregar el tipo de contenido de documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="6cbe0-147">Step 2: Add the Data Service Document Content Type</span></span>

1.  <span data-ttu-id="6cbe0-148">En la sección Tipos de contenido, haga clic en **Agregar a partir de tipos de contenido de sitio**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-148">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="6cbe0-149">Si no ve esta página, regrese al sitio, haga clic en **Biblioteca** en Herramientas de biblioteca y, a continuación, haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-149">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>

2.  <span data-ttu-id="6cbe0-150">En Tipos de contenido, haga clic en **Agregar a partir de tipos de contenido de sitio**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-150">In Content Types, click **Add from existing site content types**.</span></span>

3.  <span data-ttu-id="6cbe0-151">En Seleccionar tipos de contenido de sitio de:, seleccione **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-151">In Select site content types from:, select **Business Intelligence**.</span></span>

4.  <span data-ttu-id="6cbe0-152">En la lista Tipos de contenido de sitio disponibles, haga clic en **Documento de servicio de datos**y, a continuación, haga clic en **Agregar** para mover el tipo de contenido seleccionado a la lista Tipos de contenido que agregar.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-152">In Available Site Content Types, click **Data Service Document**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>

5.  <span data-ttu-id="6cbe0-153">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-153">Click **OK**.</span></span>

#### <a name="step-3-verify-data-service-document-configuration"></a><span data-ttu-id="6cbe0-154">Paso 3: comprobar la configuración del documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="6cbe0-154">Step 3: Verify Data Service Document Configuration</span></span>

1.  <span data-ttu-id="6cbe0-155">Abra la página principal del sitio.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-155">Open the site home page.</span></span>

2.  <span data-ttu-id="6cbe0-156">Abra la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-156">Open the library.</span></span>

3.  <span data-ttu-id="6cbe0-157">En la cinta de opciones de SharePoint, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-157">On the SharePoint ribbon, click **Documents**.</span></span>

4.  <span data-ttu-id="6cbe0-158">Haga clic en la flecha abajo en Nuevo documento y seleccione **Documento de servicio de datos**.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-158">Click the down arrow on New Document, and select **Data Service Document**.</span></span> <span data-ttu-id="6cbe0-159">Debería aparecer la página Nuevo documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbe0-159">The New Data Service Document page should appear.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cbe0-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6cbe0-160">See Also</span></span>
 <span data-ttu-id="6cbe0-161">[Usar fuentes de distribución de datos &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [eliminar una biblioteca de fuentes](delete-a-power-pivot-data-feed-library.md) de distribución de datos PowerPivot [Administración y configuración del servidor PowerPivot en administración central fuentes de distribución de](power-pivot-server-administration-and-configuration-in-central-administration.md) [datos PowerPivot](power-pivot-data-feeds.md)</span><span class="sxs-lookup"><span data-stu-id="6cbe0-161">[Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Delete a PowerPivot Data Feed Library](delete-a-power-pivot-data-feed-library.md) [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span></span>


