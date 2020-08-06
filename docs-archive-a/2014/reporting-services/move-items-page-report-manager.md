---
title: Página de movimiento de elementos (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fc83b8d2-bc79-4b56-8970-34a1cbbcc176
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98ff306caf634a5f0478e2eba03c2313b24be274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749172"
---
# <a name="move-items-page-report-manager"></a><span data-ttu-id="37fec-102">Mover elementos (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="37fec-102">Move Items Page (Report Manager)</span></span>
  <span data-ttu-id="37fec-103">Use la página Mover elementos para mover un informe, una carpeta u otro elemento a una nueva ubicación del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="37fec-103">Use the Move Items page to move a report, folder, or other item to a new location on the report server.</span></span> <span data-ttu-id="37fec-104">Puede escribir la ruta de acceso a la nueva ubicación o utilizar la vista de árbol para desplazarse hasta la nueva ubicación en el espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="37fec-104">You can type the path of the new location or use a tree view to browse to a new location in the report server namespace.</span></span> <span data-ttu-id="37fec-105">Solo puede mover los elementos para los que tenga permiso para mover y que estén almacenados en el servidor de informes actual.</span><span class="sxs-lookup"><span data-stu-id="37fec-105">You can only move items that you have permission to move and that are stored on the current report server.</span></span>  
  
 <span data-ttu-id="37fec-106">Cuando se mueve un elemento al que hace referencia otro elemento (por ejemplo, un modelo u origen de datos compartido al que hacen referencia muchos informes), la información de la ruta de acceso del elemento se actualiza de forma automática.</span><span class="sxs-lookup"><span data-stu-id="37fec-106">When you move an item that is referenced by another item (for example, a shared data source or model that is referenced by many reports), the path information for that item is updated automatically.</span></span> <span data-ttu-id="37fec-107">Mover un origen de datos compartidos no afecta una conexión de origen de datos a los informes y los modelos que lo usan.</span><span class="sxs-lookup"><span data-stu-id="37fec-107">Moving a shared data source does not disrupt a data source connection to the reports and models that use it.</span></span> <span data-ttu-id="37fec-108">Si mueve un modelo u origen de datos compartido a una carpeta para la que los usuarios no tienen permiso, todavía podrán ejecutar cualquier informe que haga referencia al modelo u origen de datos. Sin embargo, el modelo no estará visible para ellos en la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="37fec-108">If you move a shared data source or model to a folder for which users do not have permission, they will still be able to run any report that references the data source or model, however the item will not be visible to them in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="37fec-109">Para **Ubicación**, especifique la ruta de acceso completa a la carpeta, empezando por el nombre de la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="37fec-109">For **Location**, specify the full path to folder, beginning with the root folder name.</span></span> <span data-ttu-id="37fec-110">Puede escribir el nombre de la ruta de acceso o utilizar la vista de árbol para navegar hasta la carpeta que desee.</span><span class="sxs-lookup"><span data-stu-id="37fec-110">You can type the path name or use the tree view to navigate to the folder you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37fec-111">No todos los elementos pueden moverse.</span><span class="sxs-lookup"><span data-stu-id="37fec-111">Not all items are movable.</span></span> <span data-ttu-id="37fec-112">Las carpetas reservadas, como Inicio, Mis informes o Carpetas de usuarios, no se pueden mover.</span><span class="sxs-lookup"><span data-stu-id="37fec-112">You cannot move reserved folders such as Home, My Reports, or Users Folders.</span></span> <span data-ttu-id="37fec-113">Los historiales de informe y las instantáneas no se pueden mover a otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="37fec-113">You cannot move report history or snapshots to different locations.</span></span> <span data-ttu-id="37fec-114">El historial y las instantáneas siempre se encuentran en la misma ubicación que el informe en el que se basan, y se obtiene acceso a ellos a través de dicho informe.</span><span class="sxs-lookup"><span data-stu-id="37fec-114">History and snapshots are always located with, and accessed through, the report on which they are based.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="37fec-115">Navegación</span><span class="sxs-lookup"><span data-stu-id="37fec-115">Navigation</span></span>  
 <span data-ttu-id="37fec-116">Utilice los procedimientos siguientes para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="37fec-116">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-details-view"></a><span data-ttu-id="37fec-117">Para abrir la página Mover elementos desde la página Contenido de la vista Detalles</span><span class="sxs-lookup"><span data-stu-id="37fec-117">To open the Move Items page from the Contents page in Details View</span></span>  
  
1.  <span data-ttu-id="37fec-118">Abra el Administrador de informes y navegue a la carpeta que contenga un elemento que desee mover.</span><span class="sxs-lookup"><span data-stu-id="37fec-118">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="37fec-119">También puede mover elementos desde la página principal del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="37fec-119">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="37fec-120">En la barra de herramientas, haga clic en **Vista Detalles**.</span><span class="sxs-lookup"><span data-stu-id="37fec-120">In the toolbar, click **Details View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37fec-121"> Si únicamente aparece la **Vista en mosaico**, significa que ya se encuentra en la **Vista Detalles**.</span><span class="sxs-lookup"><span data-stu-id="37fec-121">If you see only **Tiles View**, you are already in **Details View**.</span></span>  
  
3.  <span data-ttu-id="37fec-122">Active la casilla situada junto a un elemento y, a continuación, haga clic en **Mover** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="37fec-122">Select the box next to an item, and then click **Move** in the toolbar.</span></span> <span data-ttu-id="37fec-123">Puede seleccionar más de una casilla si desea mover varios elementos a la misma nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="37fec-123">You can select more than one box if you want to move multiple items to the same new location.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-tiles-view"></a><span data-ttu-id="37fec-124">Para abrir la página Mover elementos desde la página Contenido en la Vista en mosaico</span><span class="sxs-lookup"><span data-stu-id="37fec-124">To open the Move Items page from the Contents page in Tiles View</span></span>  
  
1.  <span data-ttu-id="37fec-125">Abra el Administrador de informes y navegue a la carpeta que contenga un elemento que desee mover.</span><span class="sxs-lookup"><span data-stu-id="37fec-125">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="37fec-126">También puede mover elementos desde la página principal del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="37fec-126">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="37fec-127">En la barra de herramientas, haga clic en **Vista en mosaico**.</span><span class="sxs-lookup"><span data-stu-id="37fec-127">In the toolbar, click **Tiles View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37fec-128"> Si únicamente aparece la **Vista Detalles**, significa que ya se encuentra en la **Vista en mosaico**.</span><span class="sxs-lookup"><span data-stu-id="37fec-128">If you see only **Details View**, you are already in **Tiles View**.</span></span>  
  
3.  <span data-ttu-id="37fec-129">Mantenga el mouse sobre un elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="37fec-129">Hover over an item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="37fec-130">En el menú desplegable, haga clic en **Mover**.</span><span class="sxs-lookup"><span data-stu-id="37fec-130">In the drop-down menu, click **Move**.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-general-properties-page-of-an-item"></a><span data-ttu-id="37fec-131">Para abrir la página Mover elementos desde la página Propiedades generales de un elemento</span><span class="sxs-lookup"><span data-stu-id="37fec-131">To open the Move Items page from the General Properties page of an item</span></span>  
  
1.  <span data-ttu-id="37fec-132">Abra el Administrador de informes y navegue a la carpeta que contenga un elemento que desee mover.</span><span class="sxs-lookup"><span data-stu-id="37fec-132">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="37fec-133">También puede mover elementos desde la página principal del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="37fec-133">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="37fec-134">Mantenga el mouse sobre un elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="37fec-134">Hover over an item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="37fec-135">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="37fec-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="37fec-136">Se abrirá la página Propiedades generales de un elemento.</span><span class="sxs-lookup"><span data-stu-id="37fec-136">This opens the General properties page for an item.</span></span>  
  
4.  <span data-ttu-id="37fec-137">En la barra de herramientas del elemento, haga clic en **Mover**.</span><span class="sxs-lookup"><span data-stu-id="37fec-137">In the item toolbar, click **Move**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37fec-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37fec-138">See Also</span></span>  
 <span data-ttu-id="37fec-139">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="37fec-139">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="37fec-140">[Página de propiedades generales, carpetas &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="37fec-140">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="37fec-141">[Página de propiedades generales, informes &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="37fec-141">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="37fec-142">[Página de propiedades generales, recursos &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="37fec-142">[General Properties Page, Resources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span></span>  
 <span data-ttu-id="37fec-143">[Página de propiedades generales, orígenes de datos compartidos &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="37fec-143">[General Properties Page, Shared Data Sources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span></span>  
 [<span data-ttu-id="37fec-144">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="37fec-144">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
