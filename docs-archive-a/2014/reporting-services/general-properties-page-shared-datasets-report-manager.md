---
title: Página de propiedades generales, conjuntos de recursos compartidos (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10798e41-24c3-4e69-893b-7ee6af7fc958
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 31825e61cb40505e9167cc2b930a5b79e5aaa013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678058"
---
# <a name="general-properties-page-shared-datasets-report-manager"></a><span data-ttu-id="92978-102">Página de propiedades generales, conjuntos de datos compartidos (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="92978-102">General Properties Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="92978-103">Utilice la página Conjunto de datos compartido para ver y administrar las propiedades de un elemento de conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="92978-103">Use the Shared Dataset page to view and manage properties for a shared dataset item.</span></span>  
  
 <span data-ttu-id="92978-104">En el Administrador de informes no puede ver ni cambiar la definición del conjunto de datos compartido, incluida la consulta.</span><span class="sxs-lookup"><span data-stu-id="92978-104">From Report Manager, you cannot view or change the shared dataset definition, including the query.</span></span> <span data-ttu-id="92978-105">Para cambiar la definición, debe utilizar una herramienta de creación para abrir y modificar la definición, y después guardarla en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="92978-105">To change the definition, you must use an authoring tool to open and modify the definition and then save it to the report server.</span></span>  
  
 <span data-ttu-id="92978-106">Con un conjunto de datos compartido, puede administrar los valores para un conjunto de datos de forma independiente de los informes, componentes y otros elementos de catálogo que lo utilizan.</span><span class="sxs-lookup"><span data-stu-id="92978-106">With a shared dataset, you can manage the settings for a dataset separately from reports, components, and other catalog items that use it.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="92978-107">Navegación</span><span class="sxs-lookup"><span data-stu-id="92978-107">Navigation</span></span>  
 <span data-ttu-id="92978-108">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="92978-108">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-shared-dataset-properties-page-for-a-shared-dataset"></a><span data-ttu-id="92978-109">Para abrir la página de propiedades de Conjunto de datos compartidos para un conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="92978-109">To open the Shared Dataset properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="92978-110">Abra el Administrador de informes y busque el conjunto de datos compartido para el que desea configurar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="92978-110">Open Report Manager, and locate shared dataset for which you want to configure properties.</span></span>  
  
2.  <span data-ttu-id="92978-111">Mantenga el mouse sobre el conjunto de datos compartido y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="92978-111">Hover over the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="92978-112">En la lista desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="92978-112">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="92978-113">Se abre la página de propiedades General.</span><span class="sxs-lookup"><span data-stu-id="92978-113">The General properties page opens.</span></span>  
  
## <a name="options"></a><span data-ttu-id="92978-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="92978-114">Options</span></span>  
 <span data-ttu-id="92978-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="92978-115">**Name**</span></span>  
 <span data-ttu-id="92978-116">Escriba un nombre para el conjunto de datos compartido, que se usa para identificar el elemento en la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="92978-116">Type a name for the shared dataset that is used to identify the item within the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="92978-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="92978-117">**Description**</span></span>  
 <span data-ttu-id="92978-118">Proporcione información sobre el conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="92978-118">Provide information about the shared dataset.</span></span> <span data-ttu-id="92978-119">Esta descripción aparecerá en la página Contenido.</span><span class="sxs-lookup"><span data-stu-id="92978-119">This description appears on the Contents page.</span></span>  
  
 <span data-ttu-id="92978-120">**Ocultar en la vista de lista**</span><span class="sxs-lookup"><span data-stu-id="92978-120">**Hide in list view**</span></span>  
 <span data-ttu-id="92978-121">Oculte el conjunto de datos compartido de los usuarios que están utilizando el modo de vista de lista en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="92978-121">Hide the shared dataset from users who are using list view mode in Report Manager.</span></span> <span data-ttu-id="92978-122">El modo de vista de lista es el formato de vista predeterminado al explorar la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="92978-122">List view mode is the default view format when browsing the report server folder hierarchy.</span></span> <span data-ttu-id="92978-123">En la vista de lista, los nombres y descripciones de elementos se presentan en formato horizontal.</span><span class="sxs-lookup"><span data-stu-id="92978-123">In list view, item names and descriptions flow across the page.</span></span> <span data-ttu-id="92978-124">El formato alternativo es la vista Detalles.</span><span class="sxs-lookup"><span data-stu-id="92978-124">The alternative format is details view.</span></span> <span data-ttu-id="92978-125">La vista Detalles no incluye descripciones, pero sí otra información acerca del elemento.</span><span class="sxs-lookup"><span data-stu-id="92978-125">Details view omits descriptions, but includes other information about the item.</span></span> <span data-ttu-id="92978-126">Aunque se puede ocultar un elemento en la vista de lista, no se puede ocultar en la vista Detalles.</span><span class="sxs-lookup"><span data-stu-id="92978-126">Although you can hide an item in list view, you cannot hide an item in details view.</span></span> <span data-ttu-id="92978-127">Si desea restringir el acceso a un elemento, deberá crear una asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="92978-127">If you want to restrict access to an item, you must create a role assignment.</span></span>  
  
 <span data-ttu-id="92978-128">**Tiempo de espera de ejecución de la consulta**</span><span class="sxs-lookup"><span data-stu-id="92978-128">**Query execution timeout**</span></span>  
 <span data-ttu-id="92978-129">Escriba el número de segundos hasta que se agote el tiempo de espera de la consulta. Si es 0, no se agota el tiempo de espera de la consulta.</span><span class="sxs-lookup"><span data-stu-id="92978-129">Type the number of seconds until the query times out. If it is 0, the query does not time out.</span></span>  
  
 <span data-ttu-id="92978-130">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="92978-130">**Apply**</span></span>  
 <span data-ttu-id="92978-131">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="92978-131">Save your changes.</span></span>  
  
 <span data-ttu-id="92978-132">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="92978-132">**Delete**</span></span>  
 <span data-ttu-id="92978-133">Quite el conjunto compartido de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="92978-133">Remove the shared dataset from the report server database.</span></span> <span data-ttu-id="92978-134">Al eliminar un conjunto de datos compartido desactiva los informes o las versiones en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="92978-134">Deleting a shared dataset deactivates any reports or cached versions.</span></span> <span data-ttu-id="92978-135">Para reactivar un informe, debe abrir uno por uno en una herramienta de creación de informes y especificar un conjunto de datos con el mismo nombre y la misma colección de campos.</span><span class="sxs-lookup"><span data-stu-id="92978-135">To reactivate a report, you must open each one in a report authoring tool, and specify a dataset with the same name and the same field collection.</span></span> <span data-ttu-id="92978-136">O bien, puede actualizar cada referencia a la región de datos para utilizar un conjunto de datos diferente con la misma colección de campos.</span><span class="sxs-lookup"><span data-stu-id="92978-136">Alternatively, you can update each data region reference to use a different dataset with the same field collection.</span></span>  
  
 <span data-ttu-id="92978-137">**Mover**</span><span class="sxs-lookup"><span data-stu-id="92978-137">**Move**</span></span>  
 <span data-ttu-id="92978-138">Cambie la posición de un conjunto de datos compartido en la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="92978-138">Relocate a shared dataset within the report server folder hierarchy.</span></span> <span data-ttu-id="92978-139">Si hace clic en este botón, se abre la página Mover elementos, en la que puede examinar las carpetas para buscar una nueva ubicación de carpeta.</span><span class="sxs-lookup"><span data-stu-id="92978-139">Clicking this button opens the Move Items page, on which you can browse through folders for a new folder location.</span></span> <span data-ttu-id="92978-140">Para obtener más información, vea [Página de elementos de movimiento &#40;Administrador de informes&#41;](../../2014/reporting-services/move-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="92978-140">For more information, see [Move Items Page &#40;Report Manager&#41;](../../2014/reporting-services/move-items-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="92978-141">**Descargar**</span><span class="sxs-lookup"><span data-stu-id="92978-141">**Download**</span></span>  
 <span data-ttu-id="92978-142">Extraiga una copia de la definición del conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="92978-142">Extract a copy of the shared dataset definition.</span></span> <span data-ttu-id="92978-143">En función de las asociaciones de archivos definidas en su equipo, el archivo se abrirá en Visual Studio o en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="92978-143">Depending on the file associations defined on your computer, the file will open in Visual Studio or a different application.</span></span> <span data-ttu-id="92978-144">En la mayoría de los casos, el conjunto de datos compartido se abre como un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="92978-144">In most cases, the shared dataset opens as an XML file.</span></span>  
  
 <span data-ttu-id="92978-145">**Sustituya**</span><span class="sxs-lookup"><span data-stu-id="92978-145">**Replace**</span></span>  
 <span data-ttu-id="92978-146">Reemplace la definición del conjunto de datos compartido por otra diferente de un archivo .rsd que se encuentra en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="92978-146">Replace the shared dataset definition with a different one from an .rsd file located on the file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92978-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92978-147">See Also</span></span>  
 <span data-ttu-id="92978-148">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="92978-148">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="92978-149">[Administrador de informes de &#40;de página de contenido&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="92978-149">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="92978-150">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="92978-150">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="92978-151">[Opciones de actualización de caché &#40;Administrador de informes&#41;](../../2014/reporting-services/cache-refresh-options-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="92978-151">[Cache Refresh Options &#40;Report Manager&#41;](../../2014/reporting-services/cache-refresh-options-report-manager.md) </span></span>  
 <span data-ttu-id="92978-152">[Página de almacenamiento en caché, conjuntos de recursos compartidos &#40;Administrador de informes&#41;](../../2014/reporting-services/caching-page-shared-datasets-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="92978-152">[Caching Page, Shared Datasets &#40;Report Manager&#41;](../../2014/reporting-services/caching-page-shared-datasets-report-manager.md) </span></span>  
 <span data-ttu-id="92978-153">[Administrar conjuntos de recursos compartidos](report-data/manage-shared-datasets.md) </span><span class="sxs-lookup"><span data-stu-id="92978-153">[Manage Shared Datasets](report-data/manage-shared-datasets.md) </span></span>  
 [<span data-ttu-id="92978-154">Almacenar en caché conjuntos de datos compartidos &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="92978-154">Cache Shared Datasets &#40;SSRS&#41;</span></span>](report-server/cache-shared-datasets-ssrs.md)  
  
  
