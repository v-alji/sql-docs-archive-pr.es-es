---
title: Mover o eliminar un elemento (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a61ad56ea9e20e7fdf38d5acf05529b685ee896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743920"
---
# <a name="move-or-delete-an-item-report-manager"></a><span data-ttu-id="e8ac7-102">Mover o eliminar un elemento (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="e8ac7-102">Move or Delete an Item (Report Manager)</span></span>
  <span data-ttu-id="e8ac7-103">Los informes y los elementos relacionados con los informes que se publican en un servidor de informes se almacenan en carpetas.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-103">Reports and report-related items that you publish to a report server are stored in folders.</span></span> <span data-ttu-id="e8ac7-104">Puede mover los elementos a una carpeta diferente, y el servidor de informes se ocupará de mantener las referencias a ellos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-104">You can move items to a different folder and references to those items are maintained automatically by the report server.</span></span> <span data-ttu-id="e8ac7-105">Antes de eliminar un elemento, piense si otros elementos dependen de él.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-105">Before you delete an item, consider whether other items depend on it.</span></span>  
  
## <a name="move-an-item"></a><span data-ttu-id="e8ac7-106">Mover un elemento</span><span class="sxs-lookup"><span data-stu-id="e8ac7-106">Move an Item</span></span>  
 <span data-ttu-id="e8ac7-107">Puede mover elementos del servidor de informes a diversas ubicaciones de carpeta en la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-107">You can move report server items to different folder locations in the report server folder hierarchy.</span></span> <span data-ttu-id="e8ac7-108">Al mover un elemento, también se mueven todas las propiedades (incluida la configuración de seguridad) a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-108">When you move an item, all properties (including security settings) move with the item to the new location.</span></span> <span data-ttu-id="e8ac7-109">Cuando mueve una carpeta, se mueven todos los elementos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-109">When you move a folder, all the items in the folder move with it.</span></span>  
  
 <span data-ttu-id="e8ac7-110">En el Administrador de informes, los elementos que se pueden mover aparecen indicados en la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-110">In Report Manager, the items that you can move are indicated in the folder hierarchy.</span></span> <span data-ttu-id="e8ac7-111">La siguiente tabla muestra el icono correspondiente a cada uno de los elementos que se pueden mover.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-111">The following table shows the icon for each movable item.</span></span>  
  
|<span data-ttu-id="e8ac7-112">Icono</span><span class="sxs-lookup"><span data-stu-id="e8ac7-112">Icon</span></span>|<span data-ttu-id="e8ac7-113">Elemento que puede moverse</span><span class="sxs-lookup"><span data-stu-id="e8ac7-113">Moveable item</span></span>|  
|----------|-------------------|  
|<span data-ttu-id="e8ac7-114">![Report icon](../media/hlp-16doc.gif "Icono de informe")</span><span class="sxs-lookup"><span data-stu-id="e8ac7-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>|<span data-ttu-id="e8ac7-115">Informe</span><span class="sxs-lookup"><span data-stu-id="e8ac7-115">Report</span></span>|  
|<span data-ttu-id="e8ac7-116">![Icono de informe vinculado](../media/hlp-16linked.gif "Icono de informe vinculado")</span><span class="sxs-lookup"><span data-stu-id="e8ac7-116">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>|<span data-ttu-id="e8ac7-117">Informe vinculado</span><span class="sxs-lookup"><span data-stu-id="e8ac7-117">Linked report</span></span>|  
|<span data-ttu-id="e8ac7-118">![Icono de carpeta](../media/hlp-16folder.gif "Icono de carpeta")</span><span class="sxs-lookup"><span data-stu-id="e8ac7-118">![Folder icon](../media/hlp-16folder.gif "Folder icon")</span></span>|<span data-ttu-id="e8ac7-119">Carpeta</span><span class="sxs-lookup"><span data-stu-id="e8ac7-119">Folder</span></span>|  
|<span data-ttu-id="e8ac7-120">![Icono de recurso genérico](../media/hlp-16file.gif "Icono de recurso genérico")</span><span class="sxs-lookup"><span data-stu-id="e8ac7-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon")</span></span>|<span data-ttu-id="e8ac7-121">Recurso genérico</span><span class="sxs-lookup"><span data-stu-id="e8ac7-121">Generic resource</span></span>|  
|<span data-ttu-id="e8ac7-122">![Shared data source icon](../media/hlp-16datasource.png "Icono de origen de datos compartido")</span><span class="sxs-lookup"><span data-stu-id="e8ac7-122">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>|<span data-ttu-id="e8ac7-123">Origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="e8ac7-123">Shared data source</span></span>|  
||<span data-ttu-id="e8ac7-124">Conjunto de datos compartidos</span><span class="sxs-lookup"><span data-stu-id="e8ac7-124">Shared dataset</span></span>|  
  
 <span data-ttu-id="e8ac7-125">No todos los elementos se pueden mover.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-125">Not all items that you work with can be moved.</span></span> <span data-ttu-id="e8ac7-126">Por ejemplo, los elementos asociados a un informe, tales como las suscripciones o el historial del informe, no pueden moverse.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-126">You cannot move items that are associated with a report, such as subscriptions or report history.</span></span> <span data-ttu-id="e8ac7-127">Estos elementos se mueven con los informes asociados.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-127">Those items move with their associated reports.</span></span> <span data-ttu-id="e8ac7-128">Asimismo, tampoco pueden moverse elementos como las programaciones compartidas que existen fuera de la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-128">Similarly, you cannot move items, such as shared schedules, that exist outside of the folder hierarchy.</span></span> <span data-ttu-id="e8ac7-129">No pueden moverse elementos para los que no se tienen los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-129">You cannot move items if you lack permission to do so.</span></span> <span data-ttu-id="e8ac7-130">Este permiso se concede mediante la selección de las siguientes tareas durante la asignación de roles del elemento en cuestión: "Administrar informes", "Administrar modelos", "Administrar carpetas" y "Administrar orígenes de datos".</span><span class="sxs-lookup"><span data-stu-id="e8ac7-130">Permission to move an item is conveyed when the following tasks are selected in your role assignment for the item in question: "Manage reports," "Manage models", "Manage folders," and "Manage data sources."</span></span>  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a><span data-ttu-id="e8ac7-131">Para mover un elemento de la página Contenido</span><span class="sxs-lookup"><span data-stu-id="e8ac7-131">To move an item from within the Contents page</span></span>  
  
1.  <span data-ttu-id="e8ac7-132">Iniciar [Administrador de informes &#40;modo nativo de SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e8ac7-132">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e8ac7-133">En el Administrador de informes, navegue a la página **Contenido** y localice el elemento que desee mover.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-133">In Report Manager, navigate to the **Contents** page, and locate the item that you want to move.</span></span>  
  
3.  <span data-ttu-id="e8ac7-134">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-134">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="e8ac7-135">En el menú desplegable, haga clic en **Mover**.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-135">In the drop-down menu, click **Move**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="e8ac7-136">Para **Ubicación**, especifique la carpeta a la que desea mover el elemento.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-136">For **Location**, specify the folder you want to move the item to.</span></span> <span data-ttu-id="e8ac7-137">Puede escribir el nombre completo de la carpeta o utilizar el control de árbol para navegar hasta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-137">You can type the fully qualified folder name or use the tree control to navigate to the folder.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="e8ac7-138">O bien puede navegar hasta el objeto que desea mover, hacer clic en **Propiedades**y, a continuación, en **Mover** al principio de la página.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-138">Alternatively, you can navigate to the object you want to move, click **Properties**, and then click **Move** at the top of the page.</span></span>  
  
## <a name="delete-an-item"></a><span data-ttu-id="e8ac7-139">Eliminación de un elemento</span><span class="sxs-lookup"><span data-stu-id="e8ac7-139">Delete an item</span></span>  
 <span data-ttu-id="e8ac7-140">Antes de eliminar un elemento, piense si lo utilizan otros elementos.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-140">Before you delete an item, determine if it is used by other items.</span></span> <span data-ttu-id="e8ac7-141">Por ejemplo, si elimina un origen de datos compartido, ya no se ejecutarán los informes y los modelos que usan dicho origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-141">For example, if you delete a shared data source, reports and models that use that data source will no longer run.</span></span> <span data-ttu-id="e8ac7-142">Si elimina un informe, también se eliminarán las suscripciones y el historial de informes asociado a dicho informe.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-142">If you delete a report, subscriptions and report history associated with that report are also deleted.</span></span> <span data-ttu-id="e8ac7-143">Para buscar elementos dependientes de un elemento, vea [Página de elementos dependientes &#40;Administrador de informes&#41;].. /dependent-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e8ac7-143">To find dependent items for an item, see [Dependent Items Page &#40;Report Manager&#41;]../dependent-items-page-report-manager.md).</span></span>  
  
#### <a name="to-delete-a-report-or-item"></a><span data-ttu-id="e8ac7-144">Para eliminar un informe o un elemento</span><span class="sxs-lookup"><span data-stu-id="e8ac7-144">To delete a report or item</span></span>  
  
1.  <span data-ttu-id="e8ac7-145">Iniciar [Administrador de informes &#40;modo nativo de SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e8ac7-145">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e8ac7-146">En el Administrador de informes, navegue a la página **Contenido** y localice el elemento que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-146">In Report Manager, navigate to the **Contents** page, and locate the item that you want to delete.</span></span>  
  
3.  <span data-ttu-id="e8ac7-147">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-147">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="e8ac7-148">En el menú desplegable, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-148">In the drop-down menu, click **Delete**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8ac7-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8ac7-149">See Also</span></span>  
 <span data-ttu-id="e8ac7-150">[Página de contenido &#40;Administrador de informes&#41;].. /contents-page-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e8ac7-150">[Contents Page &#40;Report Manager&#41;]../contents-page-report-manager.md)</span></span>   
 [<span data-ttu-id="e8ac7-151">Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ac7-151">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
