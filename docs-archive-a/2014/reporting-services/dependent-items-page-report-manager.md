---
title: Página de elementos dependientes (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dcfb311-e9c3-4c5d-b2e0-018d79f37d2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488b10d7d7985972274340897ee3975618a12639
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669527"
---
# <a name="dependent-items-page-report-manager"></a><span data-ttu-id="d7e4f-102">Página de elementos dependientes (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="d7e4f-102">Dependent Items Page (Report Manager)</span></span>
  <span data-ttu-id="d7e4f-103">Use la página Elementos dependientes para ver una lista de informes y modelos que hacen referencia a un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-103">Use the Dependent Items page to view a list of reports and models that reference a shared data source.</span></span> <span data-ttu-id="d7e4f-104">El icono de cada tipo de elemento indica si se trata de un informe o de un modelo.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-104">The icon for each item type indicates whether it is a report or a model.</span></span> <span data-ttu-id="d7e4f-105">Esta página puede mostrarse en la vista de lista o en la vista Detalles.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-105">This page can be viewed in list view or details view.</span></span> <span data-ttu-id="d7e4f-106">Use la vista Detalles para mostrar más información sobre cada elemento.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-106">Use details view to show more information about each item.</span></span> <span data-ttu-id="d7e4f-107">Esta vista también incluye opciones de página adicionales.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-107">Additional page options are available in details view.</span></span> <span data-ttu-id="d7e4f-108">Para ayudarle a administrar el origen de datos compartido, esta página proporciona vínculos a los informes y modelos que usan el origen de datos, las métricas sobre cuándo se ejecutó o modificó el informe o el modelo por última vez, y los botones Eliminar y Mover de manera que pueda quitar los informes y modelos con facilidad que ya no se usan, o moverlos a una ubicación diferente mientras determina si todavía son necesarios.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-108">To help you manage the shared data source, this page provides links to reports and models that use the data source, metrics on when the report or model was last run or modified, and Delete and Move buttons so that you can easily remove reports and models that are no longer used, or move them to a different location while you determine whether they are still needed.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="d7e4f-109">Navegación</span><span class="sxs-lookup"><span data-stu-id="d7e4f-109">Navigation</span></span>  
 <span data-ttu-id="d7e4f-110">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="d7e4f-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-dependent-items-page"></a><span data-ttu-id="d7e4f-111">Para abrir la página Elementos dependientes</span><span class="sxs-lookup"><span data-stu-id="d7e4f-111">To open the Dependent Items page</span></span>  
  
1.  <span data-ttu-id="d7e4f-112">Abra el Administrador de informes y busque el origen de datos compartido del que desea ver los elementos dependientes.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-112">Open Report Manager, and locate the shared data source for which you want to view dependent items.</span></span>  
  
2.  <span data-ttu-id="d7e4f-113">Mantenga el mouse sobre el elemento y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-113">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="d7e4f-114">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="d7e4f-115">Esto abre la página de propiedades General del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-115">This opens the General properties page for the data source.</span></span>  
  
4.  <span data-ttu-id="d7e4f-116">Seleccione la pestaña **Elementos dependientes** .</span><span class="sxs-lookup"><span data-stu-id="d7e4f-116">Select the **Dependent Items** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7e4f-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="d7e4f-117">Options</span></span>  
 <span data-ttu-id="d7e4f-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-118">**Name**</span></span>  
 <span data-ttu-id="d7e4f-119">Muestra el nombre del informe o del modelo.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-119">Shows the name of the report or model.</span></span> <span data-ttu-id="d7e4f-120">Haga clic en el nombre del informe para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-120">Click the name of the report to open it.</span></span> <span data-ttu-id="d7e4f-121">Haga clic en el nombre del modelo para abrir sus páginas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-121">Click the name of the model to open its property pages.</span></span>  
  
 <span data-ttu-id="d7e4f-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-122">**Description**</span></span>  
 <span data-ttu-id="d7e4f-123">Muestra la descripción del informe o del modelo.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-123">Shows the description of the report or model.</span></span>  
  
 <span data-ttu-id="d7e4f-124">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-124">**Delete**</span></span>  
 <span data-ttu-id="d7e4f-125">Haga clic para eliminar el informe o el modelo de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-125">Click to delete the report or model from the report server database.</span></span> <span data-ttu-id="d7e4f-126">Antes de hacer clic en **Eliminar**, active la casilla situada junto a cada elemento que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-126">Before clicking **Delete**, select the check box next to each item that you want to delete.</span></span>  
  
 <span data-ttu-id="d7e4f-127">**Mover**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-127">**Move**</span></span>  
 <span data-ttu-id="d7e4f-128">Haga clic para cambiar de posición un informe o un modelo dentro de la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-128">Click to relocate a report or model within the folder hierarchy.</span></span> <span data-ttu-id="d7e4f-129">Antes de hacer clic en **Mover**, active la casilla situada junto a cada elemento que desee mover.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-129">Before clicking **Move**, select the check box next to each item that you want to move.</span></span> <span data-ttu-id="d7e4f-130">Al hacerlo, se abre la página para mover elementos, en la que puede examinar las carpetas para seleccionar una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-130">This opens the Move Items page, where you can browse through folders to select a new location.</span></span>  
  
 <span data-ttu-id="d7e4f-131">**Edición**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-131">**Edit**</span></span>  
 <span data-ttu-id="d7e4f-132">Haga clic en el icono de propiedades para obtener acceso a las páginas de propiedades de un informe o un modelo.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-132">Click the Property icon to access the property pages of a report, or model.</span></span>  
  
 <span data-ttu-id="d7e4f-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-133">**Type**</span></span>  
 <span data-ttu-id="d7e4f-134">Muestra el icono del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-134">Shows the icon of the item type.</span></span>  
  
 <span data-ttu-id="d7e4f-135">**Fecha de modificación**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-135">**Modified Date**</span></span>  
 <span data-ttu-id="d7e4f-136">Muestra la fecha y la hora en que se modificó el informe o el modelo por última vez.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-136">Shows the date and time when the report or model was last modified.</span></span>  
  
 <span data-ttu-id="d7e4f-137">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-137">**Modified By**</span></span>  
 <span data-ttu-id="d7e4f-138">Muestra el nombre del usuario que modificó las propiedades del elemento por última vez.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-138">Shows the name of the user who last modified the item properties.</span></span>  
  
 <span data-ttu-id="d7e4f-139">**Cuando se ejecuta**</span><span class="sxs-lookup"><span data-stu-id="d7e4f-139">**When Run**</span></span>  
 <span data-ttu-id="d7e4f-140">Para los informes que se ejecutan como instantáneas de ejecución de informes, muestra la fecha y la hora en que se actualizó el informe por última vez.</span><span class="sxs-lookup"><span data-stu-id="d7e4f-140">For reports that run as report execution snapshots, displays the date and time at which the report was last refreshed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e4f-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7e4f-141">See Also</span></span>  
 <span data-ttu-id="d7e4f-142">[Administrador de informes la ayuda F1](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d7e4f-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="d7e4f-143">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d7e4f-143">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="d7e4f-144">[Administrador de informes de &#40;de página de contenido&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d7e4f-144">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="d7e4f-145">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="d7e4f-145">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
