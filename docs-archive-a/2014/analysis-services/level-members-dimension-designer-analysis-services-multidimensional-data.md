---
title: Nivel y miembros (pestaña explorador, diseñador de dimensiones) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.browsertab.levelsandmembers.f1
ms.assetid: 3f61e384-5b4e-4480-a7ed-b408de2fdea7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21680f00b82b5410e2c7a67122fdcfeb78c999dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752482"
---
# <a name="level-and-members-browser-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="67a65-102">Nivel y miembros (pestaña Explorador, Diseñador de dimensiones) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="67a65-102">Level and Members (Browser Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="67a65-103">Use este panel para examinar los miembros del idioma y la jerarquía seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="67a65-103">Use this pane to browse the members of the currently selected hierarchy and language.</span></span> <span data-ttu-id="67a65-104">Para seleccionar el idioma o la jerarquía que se examinará, use las opciones **Jerarquía** e **Idioma** del panel **Barra de herramientas** .</span><span class="sxs-lookup"><span data-stu-id="67a65-104">To select a hierarchy or language to browse, use the **Hierarchy** and **Language** options on the **Toolbar** pane.</span></span> <span data-ttu-id="67a65-105">Para obtener más información sobre el panel Barra de herramientas, vea [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="67a65-105">For more information about the Toolbar pane, see [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="writeback-mode"></a><span data-ttu-id="67a65-106">Modo de reescritura</span><span class="sxs-lookup"><span data-stu-id="67a65-106">Writeback Mode</span></span>  
 <span data-ttu-id="67a65-107">La funcionalidad de este panel cambia si el modo de reescritura está habilitado.</span><span class="sxs-lookup"><span data-stu-id="67a65-107">The functionality of this pane changes if writeback mode is enabled.</span></span> <span data-ttu-id="67a65-108">La dimensión seleccionada debe permitir la escritura (es decir, la propiedad `WriteEnabled` de la dimensión debe establecerse en True) y la dimensión debe implementarse en una instantánea de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para habilitar el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-108">The selected dimension must be write-enabled (in other words, the `WriteEnabled` property of the dimension must be set to true) and the dimension must be deployed to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance in order to enable writeback mode.</span></span>  
  
 <span data-ttu-id="67a65-109">Para habilitar el modo de reescritura, puede seleccionar **Reescritura** en el panel **Barra de herramientas** , o hacer clic con el botón derecho en el panel **Nivel y miembros** y seleccionar **Reescritura** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="67a65-109">To enable writeback mode, you can either select **Writeback** from the **Toolbar** pane, or right-click the **Level and Members** pane and select **Writeback** from the context menu.</span></span>  
  
 <span data-ttu-id="67a65-110">Si el modo de reescritura está habilitado, puede realizar las siguientes acciones adicionales en el panel **Nivel y miembros** :</span><span class="sxs-lookup"><span data-stu-id="67a65-110">If writeback mode is enabled, you can perform the following additional actions in the **Level and Members** pane:</span></span>  
  
|<span data-ttu-id="67a65-111">Tareas pendientes</span><span class="sxs-lookup"><span data-stu-id="67a65-111">To do</span></span>|<span data-ttu-id="67a65-112">Acciones</span><span class="sxs-lookup"><span data-stu-id="67a65-112">Perform</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="67a65-113">Crear miembros del mismo nivel y miembros secundarios en la jerarquía seleccionada</span><span class="sxs-lookup"><span data-stu-id="67a65-113">Create sibling and child members within the selected hierarchy.</span></span>|<span data-ttu-id="67a65-114">Haga clic con el botón derecho en el miembro seleccionado y, en el menú contextual, seleccione **Crear igual**para crear un miembro del mismo nivel o **Crear secundario**para crear un miembro secundario.</span><span class="sxs-lookup"><span data-stu-id="67a65-114">Right-click the selected member and select either **Create Sibling**, to create a sibling member, or **Create Child**, to create a child member, from the context menu.</span></span>|  
|<span data-ttu-id="67a65-115">Mover un miembro seleccionado hacia arriba o hacia abajo en la jerarquía</span><span class="sxs-lookup"><span data-stu-id="67a65-115">Move a selected member up or down the hierarchy.</span></span>|<span data-ttu-id="67a65-116">Arrastre el miembro seleccionado al miembro primario o secundario adecuado o haga clic en **Aumentar sangría** o **Disminuir sangría** en el panel **Barra de herramientas** para mover el miembro seleccionado hacia arriba o hacia abajo en los niveles de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="67a65-116">Either drag the selected member to the appropriate parent or child member, or click **Increase Indent** or **Decrease Indent** on the **Toolbar** pane to move the selected member up or down the levels of the hierarchy.</span></span>|  
|<span data-ttu-id="67a65-117">Cambiar el nombre del miembro seleccionado</span><span class="sxs-lookup"><span data-stu-id="67a65-117">Rename a selected member.</span></span>|<span data-ttu-id="67a65-118">Haga clic con el botón derecho en el miembro seleccionado y seleccione **Cambiar nombre**o haga clic en un miembro ya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="67a65-118">Either right-click the selected member and select **Rename**, or click an already-selected member.</span></span>|  
|<span data-ttu-id="67a65-119">Editar valores de propiedad del miembro</span><span class="sxs-lookup"><span data-stu-id="67a65-119">Edit member property values</span></span>|<span data-ttu-id="67a65-120">Haga doble clic en el valor de la propiedad del miembro seleccionado para editar el valor.</span><span class="sxs-lookup"><span data-stu-id="67a65-120">Double-click the value in the selected member property for the selected member to edit the value.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="67a65-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="67a65-121">Options</span></span>  
 <span data-ttu-id="67a65-122">**Nivel actual**</span><span class="sxs-lookup"><span data-stu-id="67a65-122">**Current level**</span></span>  
 <span data-ttu-id="67a65-123">Muestra el nivel al que pertenece el miembro seleccionado actualmente en **Árbol** .</span><span class="sxs-lookup"><span data-stu-id="67a65-123">Displays the level to which the currently selected member in **Tree** belongs.</span></span>  
  
 <span data-ttu-id="67a65-124">**Palmera**</span><span class="sxs-lookup"><span data-stu-id="67a65-124">**Tree**</span></span>  
 <span data-ttu-id="67a65-125">Muestra los miembros del idioma y la jerarquía seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="67a65-125">Displays the members of the currently selected hierarchy and language.</span></span>  
  
 <span data-ttu-id="67a65-126">Si están seleccionadas las propiedades del miembro en la opción **Propiedades del miembro** del panel Barra de herramientas, cada propiedad del miembro se muestra como una columna.</span><span class="sxs-lookup"><span data-stu-id="67a65-126">If member properties are selected from the **Member Properties** option of the Toolbar pane, each member property is displayed as a column.</span></span>  
  
 <span data-ttu-id="67a65-127">Si el modo de reescritura está habilitado, se muestra una columna por cada columna de clave asociada con el atributo clave de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="67a65-127">If writeback mode is enabled, one column for each key column associated with the key attribute in the dimension is displayed.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="67a65-128">Menú contextual</span><span class="sxs-lookup"><span data-stu-id="67a65-128">Context Menu</span></span>  
 <span data-ttu-id="67a65-129">Las siguientes opciones están disponibles en el menú contextual que se muestra al hacer clic con el botón derecho en cualquier parte del panel **Nivel y miembros** del miembro seleccionado:</span><span class="sxs-lookup"><span data-stu-id="67a65-129">The following options are available in the context menu displayed by right-clicking any part of the **Level and Members** pane for the selected member:</span></span>  
  
 <span data-ttu-id="67a65-130">**Crear igual**</span><span class="sxs-lookup"><span data-stu-id="67a65-130">**Create sibling**</span></span>  
 <span data-ttu-id="67a65-131">Crea un nuevo miembro en el mismo nivel que el miembro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="67a65-131">Creates a new member at the same level as the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-132">Esta opción solo está habilitada si se ha seleccionado un miembro en un nivel distinto de (Todos).</span><span class="sxs-lookup"><span data-stu-id="67a65-132">This option is enabled only if a member at a level other than the (All) level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-133">Esta opción solo se muestra si se ha habilitado el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-133">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="67a65-134">**Crear secundario**</span><span class="sxs-lookup"><span data-stu-id="67a65-134">**Create child**</span></span>  
 <span data-ttu-id="67a65-135">Crea un nuevo miembro en el nivel inmediatamente inferior que el miembro seleccionado, como un miembro secundario del miembro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="67a65-135">Creates a new member at the next lower level as the selected member, as a child of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-136">Esta opción solo está habilitada si se ha seleccionado un miembro en un nivel distinto del nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="67a65-136">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-137">Esta opción solo se muestra si se ha habilitado el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-137">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="67a65-138">**Cortar**</span><span class="sxs-lookup"><span data-stu-id="67a65-138">**Cut**</span></span>  
 <span data-ttu-id="67a65-139">Copia los miembros seleccionados en el portapapeles y los quita de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="67a65-139">Copies the selected members to the clipboard and removes them from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-140">Esta opción solo está habilitada si se ha seleccionado un miembro distinto del miembro Todos.</span><span class="sxs-lookup"><span data-stu-id="67a65-140">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-141">Esta opción solo se muestra si se ha habilitado el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-141">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="67a65-142">**Pegar**</span><span class="sxs-lookup"><span data-stu-id="67a65-142">**Paste**</span></span>  
 <span data-ttu-id="67a65-143">Pega los miembros quitados anteriormente usando **Cortar** inmediatamente después del miembro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="67a65-143">Pastes members previously removed using **Cut** immediately after the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-144">Esta opción solo se muestra si se ha habilitado el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-144">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="67a65-145">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="67a65-145">**Delete**</span></span>  
 <span data-ttu-id="67a65-146">Quita los miembros seleccionados de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="67a65-146">Removes the selected members from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-147">Esta opción solo está habilitada si se ha seleccionado un miembro distinto del miembro Todos.</span><span class="sxs-lookup"><span data-stu-id="67a65-147">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-148">Esta opción solo se muestra si se ha habilitado el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-148">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="67a65-149">**Cambiar el nombre**</span><span class="sxs-lookup"><span data-stu-id="67a65-149">**Rename**</span></span>  
 <span data-ttu-id="67a65-150">Seleccione esta opción para modificar el nombre del miembro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="67a65-150">Select to edit the name of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-151">Esta opción solo está habilitada si se ha seleccionado un miembro distinto del miembro Todos.</span><span class="sxs-lookup"><span data-stu-id="67a65-151">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-152">Esta opción solo se muestra si se ha habilitado el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-152">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="67a65-153">**Filtrar miembros**</span><span class="sxs-lookup"><span data-stu-id="67a65-153">**Filter Members**</span></span>  
 <span data-ttu-id="67a65-154">Muestra el cuadro de diálogo **Filtrar miembros** para filtrar los miembros mostrados en **Nivel y miembros** para la jerarquía seleccionada.</span><span class="sxs-lookup"><span data-stu-id="67a65-154">Displays the **Filter Members** dialog box to filter members displayed in **Level and Members** for the selected hierarchy.</span></span> <span data-ttu-id="67a65-155">Para más información sobre el cuadro de diálogo **Filtrar miembros**, vea [Cuadro de diálogo Filtrar miembros &#40;Analysis Services - Datos multidimensionales&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="67a65-155">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="67a65-156">**Expandir todo**</span><span class="sxs-lookup"><span data-stu-id="67a65-156">**Expand All**</span></span>  
 <span data-ttu-id="67a65-157">Expande todos los miembros del **Árbol**.</span><span class="sxs-lookup"><span data-stu-id="67a65-157">Expands all members in **Tree**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67a65-158">Esta opción solo está habilitada si se ha seleccionado un miembro en un nivel distinto del nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="67a65-158">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
 <span data-ttu-id="67a65-159">**Contraer todo**</span><span class="sxs-lookup"><span data-stu-id="67a65-159">**Collapse All**</span></span>  
 <span data-ttu-id="67a65-160">Contrae todos los miembros del **Árbol**.</span><span class="sxs-lookup"><span data-stu-id="67a65-160">Collapse all members in **Tree**.</span></span>  
  
 <span data-ttu-id="67a65-161">**Expandir miembro**</span><span class="sxs-lookup"><span data-stu-id="67a65-161">**Expand Member**</span></span>  
 <span data-ttu-id="67a65-162">Expande el miembro seleccionado en el **Árbol**.</span><span class="sxs-lookup"><span data-stu-id="67a65-162">Expand the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="67a65-163">**Contraer miembro**</span><span class="sxs-lookup"><span data-stu-id="67a65-163">**Collapse Member**</span></span>  
 <span data-ttu-id="67a65-164">Contrae el miembro seleccionado en el **Árbol**.</span><span class="sxs-lookup"><span data-stu-id="67a65-164">Collapse the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="67a65-165">**Reescritura**</span><span class="sxs-lookup"><span data-stu-id="67a65-165">**Writeback**</span></span>  
 <span data-ttu-id="67a65-166">Seleccione esta opción para habilitar el modo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="67a65-166">Select to enable writeback mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a65-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67a65-167">See Also</span></span>  
 <span data-ttu-id="67a65-168">[Barra de herramientas &#40;pestaña explorador, diseñador de dimensiones&#41; &#40;Analysis Services-datos multidimensionales&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="67a65-168">[Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="67a65-169">Explorador &#40;diseñador de dimensiones&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="67a65-169">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
