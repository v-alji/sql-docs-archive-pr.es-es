---
title: Editor de formulario de acción de obtención de detalles (pestaña acciones, diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.drillthroughaction.f1
ms.assetid: 225fd818-b5ea-494f-b67b-66e09798274a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 546448bd05f3af45b7093acb2dbb9d1e1a8f1bd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676240"
---
# <a name="drillthrough-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="cdf36-102">Editor de Formulario de acción de obtención de detalles (pestaña Acciones, Diseñador de cubos) (Analysis Services -  Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="cdf36-102">Drillthrough Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="cdf36-103">Use el panel **Editor de Formulario de acción de obtención de detalles** de la pestaña **Acciones** del Diseñador de cubos para modificar la acción de obtención de detalles seleccionada en el panel **Organizador de acciones** .</span><span class="sxs-lookup"><span data-stu-id="cdf36-103">Use the **Drillthrough Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the drillthrough action selected in the **Action Organizer** pane.</span></span> <span data-ttu-id="cdf36-104">Para obtener más información sobre las acciones de obtención de detalles, vea [Acciones &#40;Analysis Services - Datos multidimensionales&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="cdf36-104">For more information about drillthrough actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdf36-105">Las acciones de obtención de detalles ya no obtienen detalles del almacén de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-105">Drillthrough actions no longer drill down to the underlying data store.</span></span> <span data-ttu-id="cdf36-106">La información a la que tienen acceso las acciones de obtención de detalles debe modelarse en el cubo utilizando miembros de jerarquía o dimensión.</span><span class="sxs-lookup"><span data-stu-id="cdf36-106">The information that drillthrough actions access must be modeled within the cube by using dimension or hierarchy members.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cdf36-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="cdf36-107">Options</span></span>  
 <span data-ttu-id="cdf36-108">**name**</span><span class="sxs-lookup"><span data-stu-id="cdf36-108">**name**</span></span>  
 <span data-ttu-id="cdf36-109">Escriba el nombre de la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-109">Type the name of the action.</span></span>  
  
 <span data-ttu-id="cdf36-110">**Destino de la acción**</span><span class="sxs-lookup"><span data-stu-id="cdf36-110">**Action Target**</span></span>  
 <span data-ttu-id="cdf36-111">Expanda esta opción para ver la opción **Miembros de grupo de medida** .</span><span class="sxs-lookup"><span data-stu-id="cdf36-111">Expand to view the **Measure group members** option.</span></span>  
  
 <span data-ttu-id="cdf36-112">**Miembros de grupo de medida**</span><span class="sxs-lookup"><span data-stu-id="cdf36-112">**Measure group members**</span></span>  
 <span data-ttu-id="cdf36-113">Seleccione el grupo de medida al que se asociará la acción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="cdf36-113">Select the measure group to which the drillthrough action is to be associated.</span></span>  
  
 <span data-ttu-id="cdf36-114">**Condición (opcional)**</span><span class="sxs-lookup"><span data-stu-id="cdf36-114">**Condition (Optional)**</span></span>  
 <span data-ttu-id="cdf36-115">Escriba la expresión MDX (Expresiones multidimensionales) que describe una condición opcional, que se usa junto con **Miembros de grupo de medida**, con lo que restringe aún más el momento de disponibilidad de la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-115">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Measure group members**, which further restricts when the action is available.</span></span> <span data-ttu-id="cdf36-116">La expresión devuelve un valor booleano que, si es verdadero, indica que la acción se encuentra disponible.</span><span class="sxs-lookup"><span data-stu-id="cdf36-116">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="cdf36-117">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="cdf36-117">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="cdf36-118">**Columnas de obtención de detalles**</span><span class="sxs-lookup"><span data-stu-id="cdf36-118">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="cdf36-119">Expanda esta opción para mostrar una cuadrícula en la que indicar los atributos que se devuelven cuando el usuario ejecuta esta acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-119">Expand to display a grid in which to indicate the attributes that are returned when the user runs this action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdf36-120">Puede seleccionar más de una dimensión, pero no se puede utilizar la misma dimensión más de una vez en una acción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="cdf36-120">You can select more than one dimension, but no dimension can be used more than once in a drillthrough action.</span></span>  
  
 <span data-ttu-id="cdf36-121">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cdf36-121">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="cdf36-122">Columna</span><span class="sxs-lookup"><span data-stu-id="cdf36-122">Column</span></span>|<span data-ttu-id="cdf36-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdf36-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cdf36-124">**Dimensiones**</span><span class="sxs-lookup"><span data-stu-id="cdf36-124">**Dimensions**</span></span>|<span data-ttu-id="cdf36-125">Seleccione la dimensión de la que se deriva el atributo devuelto.</span><span class="sxs-lookup"><span data-stu-id="cdf36-125">Select the dimension from which the returned attribute is derived.</span></span> <span data-ttu-id="cdf36-126">Seleccione MEASURES para obtener detalles de medidas.</span><span class="sxs-lookup"><span data-stu-id="cdf36-126">Select MEASURES to drillthrough on measures.</span></span>|  
|<span data-ttu-id="cdf36-127">**Columnas devueltas**</span><span class="sxs-lookup"><span data-stu-id="cdf36-127">**Return Columns**</span></span>|<span data-ttu-id="cdf36-128">Seleccione el atributo o la medida de las dimensiones seleccionadas que se van a devolver cuando se ejecute la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-128">Select the attribute or measure from the selected dimension to be returned when the action is run.</span></span>|  
  
 <span data-ttu-id="cdf36-129">**Propiedades adicionales**</span><span class="sxs-lookup"><span data-stu-id="cdf36-129">**Additional Properties**</span></span>  
 <span data-ttu-id="cdf36-130">Expanda esta opción para ver las opciones **Predeterminado**, **Número máximo de filas**, **Invocación**, **Aplicación**, **Descripción**, **Título**y **El título es MDX** .</span><span class="sxs-lookup"><span data-stu-id="cdf36-130">Expand to view the **Default**, **Maximum rows**, **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="cdf36-131">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="cdf36-131">**Default**</span></span>  
 <span data-ttu-id="cdf36-132">Seleccione **True** para incluir esta acción de obtención de detalles como la acción de obtención de detalles predeterminada; en caso contrario, seleccione **False**.</span><span class="sxs-lookup"><span data-stu-id="cdf36-132">Select **True** to include this drillthrough action as a default drillthrough action, otherwise, select **False**.</span></span>  
  
 <span data-ttu-id="cdf36-133">Si `RETURN` se omite la cláusula en una `DRILLTHROUGH` instrucción MDX ejecutada por una aplicación cliente, la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instancia de evalúa todas las acciones de obtención de detalles predeterminadas y ejecuta la primera acción de obtención de detalles predeterminada que devuelve un conjunto no vacío.</span><span class="sxs-lookup"><span data-stu-id="cdf36-133">If the `RETURN` clause is omitted from an MDX `DRILLTHROUGH` statement executed by a client application, the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance evaluates all default drillthrough actions and runs the first default drillthrough action that returns a non-empty set.</span></span> <span data-ttu-id="cdf36-134">Para obtener más información acerca de la `DRILLTHROUGH` instrucción MDX, vea [instrucción DRILLTHROUGH &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="cdf36-134">For more information about the MDX `DRILLTHROUGH` statement, see [DRILLTHROUGH Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdf36-135">Esta opción se utiliza por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cdf36-135">This option is used for backwards compatibility purposes.</span></span>  
  
 <span data-ttu-id="cdf36-136">**Número máximo de filas**</span><span class="sxs-lookup"><span data-stu-id="cdf36-136">**Maximum rows**</span></span>  
 <span data-ttu-id="cdf36-137">Escriba el número máximo de filas que devolverá la acción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="cdf36-137">Type the maximum number of rows to be returned by the drillthrough action.</span></span> <span data-ttu-id="cdf36-138">Al establecer esta opción en cero o en un valor vacío se indica que la acción de obtención de detalles devolverá todas las filas recuperadas por la acción a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-138">Setting this option to zero or an empty value indicates that the drillthrough action returns all rows retrieved by the action to the client application.</span></span>  
  
 <span data-ttu-id="cdf36-139">**Invocación**</span><span class="sxs-lookup"><span data-stu-id="cdf36-139">**Invocation**</span></span>  
 <span data-ttu-id="cdf36-140">Seleccione la configuración que indica cuándo debe realizarse la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-140">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdf36-141">Esta opción solo ofrece una recomendación a una aplicación cliente sobre cuándo ejecutar una acción, pero no controla directamente la invocación de la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-141">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="cdf36-142">En la siguiente tabla se describen las configuraciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="cdf36-142">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="cdf36-143">Value</span><span class="sxs-lookup"><span data-stu-id="cdf36-143">Value</span></span>|<span data-ttu-id="cdf36-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdf36-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cdf36-145">Batch</span><span class="sxs-lookup"><span data-stu-id="cdf36-145">Batch</span></span>|<span data-ttu-id="cdf36-146">La acción debe ejecutarse como parte de una operación de lote o una tarea de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cdf36-146">The action should run as part of a batch operation or an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="cdf36-147">Interactive</span><span class="sxs-lookup"><span data-stu-id="cdf36-147">Interactive</span></span>|<span data-ttu-id="cdf36-148">La acción se ejecuta cuando el usuario invoca la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-148">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="cdf36-149">Al abrir</span><span class="sxs-lookup"><span data-stu-id="cdf36-149">On Open</span></span>|<span data-ttu-id="cdf36-150">La acción se ejecuta cuando se abre el cubo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="cdf36-150">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="cdf36-151">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="cdf36-151">**Application**</span></span>  
 <span data-ttu-id="cdf36-152">Escriba el nombre de la aplicación que puede ejecutar la acción de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="cdf36-152">Type the name of the application that can execute the drillthrough action.</span></span>  
  
 <span data-ttu-id="cdf36-153">También puede utilizar esta opción para identificar qué aplicación cliente utiliza con más frecuencia esta acción, así como para mostrar los iconos adecuados junto a la acción en un menú emergente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-153">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdf36-154">Esta opción solo ofrece una recomendación a una aplicación cliente sobre qué aplicación debe ejecutar una acción, pero no controla directamente el acceso a la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-154">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="cdf36-155">Las aplicaciones cliente deben ocultar las acciones asociadas a otras aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-155">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="cdf36-156">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cdf36-156">**Description**</span></span>  
 <span data-ttu-id="cdf36-157">Escriba la descripción opcional de la acción.</span><span class="sxs-lookup"><span data-stu-id="cdf36-157">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="cdf36-158">**Caption**</span><span class="sxs-lookup"><span data-stu-id="cdf36-158">**Caption**</span></span>  
 <span data-ttu-id="cdf36-159">Escriba el título que se mostrará para la acción en la aplicación cliente si establece **El título es MDX** en **False**.</span><span class="sxs-lookup"><span data-stu-id="cdf36-159">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="cdf36-160">Escriba la expresión de Expresiones multidimensionales (MDX) que devuelve una cadena para el título si establece **El título es MDX** en **True**.</span><span class="sxs-lookup"><span data-stu-id="cdf36-160">Type the Multidimensional Expressions (MDX) expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="cdf36-161">**El título es MDX**</span><span class="sxs-lookup"><span data-stu-id="cdf36-161">**Caption Is MDX**</span></span>  
 <span data-ttu-id="cdf36-162">Seleccione **False** para indicar que **Título** contiene una cadena literal que representa un título que se mostrará para la acción en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-162">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="cdf36-163">Seleccione **True** para indicar que **Título** contiene una expresión MDX que devuelve una cadena que representa un título que se mostrará para la acción en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-163">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="cdf36-164">La expresión MDX debe resolverse antes de devolver la acción a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cdf36-164">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdf36-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cdf36-165">See Also</span></span>  
 <span data-ttu-id="cdf36-166">[Expresiones multidimensionales &#40;referencia de&#41; MDX](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="cdf36-166">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="cdf36-167">[Acciones &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cdf36-167">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="cdf36-168">[Barra de herramientas &#40;pestaña acciones, diseñador de cubos&#41; &#40;Analysis Services-datos multidimensionales&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cdf36-168">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="cdf36-169">[Organizador de acciones &#40;pestaña acciones, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cdf36-169">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="cdf36-170">[Herramientas de cálculo &#40;pestaña acciones, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cdf36-170">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="cdf36-171">[Editor de formulario de acción &#40;pestaña acciones, diseñador de cubos&#41; &#40;Analysis Services-datos multidimensionales&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cdf36-171">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="cdf36-172">Editor de formulario de acción de informe &#40;pestaña acciones, diseñador de cubos&#41; &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="cdf36-172">Report Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](report-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  
