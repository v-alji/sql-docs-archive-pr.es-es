---
title: Agregar una acción de expandir y contraer a un elemento (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 49f07ad6-242b-4861-8fc1-91ca78c36d6c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 331c6a14a4a898ffcdf86f274c00e7ad3c801ec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744489"
---
# <a name="add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs"></a><span data-ttu-id="7a020-102">Agregar una acción de expandir y contraer a un elemento (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="7a020-102">Add an Expand or Collapse Action to an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7a020-103">Podrá permitir a los usuarios expandir o contraer interactivamente elementos de informe o expandir o contraer las filas y columnas asociadas a un grupo para una tabla o una matriz.</span><span class="sxs-lookup"><span data-stu-id="7a020-103">You can enable a user to interactively expand or collapse report items, or expand or collapse rows and columns associated with a group for a table or matrix.</span></span> <span data-ttu-id="7a020-104">Para permitir a los usuarios expandir o contraer un elemento, debe establecer las propiedades de visibilidad del elemento.</span><span class="sxs-lookup"><span data-stu-id="7a020-104">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span> <span data-ttu-id="7a020-105">El establecimiento de la visibilidad funciona en un visor de informes HTML y en ocasiones se denomina acción *de obtención de detalles* .</span><span class="sxs-lookup"><span data-stu-id="7a020-105">Setting visibility works in an HTML report viewer, and is sometimes called a *drilldown* action.</span></span>  
  
 <span data-ttu-id="7a020-106">En la vista de diseño del informe, especifique el nombre del cuadro de texto donde desea mostrar los iconos de alternancia de expandir y contraer.</span><span class="sxs-lookup"><span data-stu-id="7a020-106">In report design view, you specify the name of the text box where you want to display the expand and collapse toggle icons.</span></span> <span data-ttu-id="7a020-107">En el informe representado, el cuadro de texto mostrará un signo más (+) o menos (-), además de su contenido.</span><span class="sxs-lookup"><span data-stu-id="7a020-107">In the rendered report, the text box displays a plus (+) or minus (-) sign in addition to its contents.</span></span> <span data-ttu-id="7a020-108">Cuando el usuario haga clic en el control de visibilidad, la presentación del informe se actualizará para mostrar u ocultar el elemento de informe en función de los valores de visibilidad actuales para los elementos del informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-108">When the user clicks the toggle, the report display is refreshed to show or hide the report item, based on the current visibility settings for items in the report.</span></span>  
  
 <span data-ttu-id="7a020-109">Normalmente, la acción de expandir y contraer se usa para mostrar inicialmente solo datos de resumen y permitir a los usuarios hacer clic en el signo más para mostrar los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="7a020-109">Typically, the expand and collapse action is used to initially display only summary data and to enable the user to click the plus sign to show detail data.</span></span> <span data-ttu-id="7a020-110">Por ejemplo, puede ocultar inicialmente una tabla que muestre los valores usados en un gráfico u ocultar los grupos secundarios de una tabla con grupos de filas o de columnas anidadas, como en un informe detallado.</span><span class="sxs-lookup"><span data-stu-id="7a020-110">For example, you can initially hide a table that displays values for a chart, or hide child groups for a table with nested row or column groups, as in a drilldown report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-expand-and-collapse-action-to-a-group"></a><span data-ttu-id="7a020-111">Para agregar una acción de expandir y contraer a un grupo</span><span class="sxs-lookup"><span data-stu-id="7a020-111">To add expand and collapse action to a group</span></span>  
  
1.  <span data-ttu-id="7a020-112">En la vista de diseño del informe, haga clic en la tabla o la matriz para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="7a020-112">In report design view, click the table or matrix to select it.</span></span> <span data-ttu-id="7a020-113">El Panel de agrupación muestra los grupos de filas y de columnas.</span><span class="sxs-lookup"><span data-stu-id="7a020-113">The Grouping pane displays the row and column groups.</span></span>  
  
     <span data-ttu-id="7a020-114">![Panel de agrupación](../media/groupingpane.png "Panel de agrupación")</span><span class="sxs-lookup"><span data-stu-id="7a020-114">![Grouping Pane](../media/groupingpane.png "Grouping Pane")</span></span>  
  
     <span data-ttu-id="7a020-115">Si el panel de agrupación no aparece, haga clic en el menú **Ver** y después en **Agrupación**.</span><span class="sxs-lookup"><span data-stu-id="7a020-115">If the Grouping pane does not appear, click the **View** menu and then click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="7a020-116">Haga clic con el botón derecho en cualquier parte en la barra de título del panel Agrupación y, después, haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="7a020-116">Right-click anywhere in the title bar of the Grouping pane, and then click **Advanced**.</span></span> <span data-ttu-id="7a020-117">El modo del panel Agrupación alterna para mostrar la estructura de presentación subyacente para las filas y columnas en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="7a020-117">The Grouping pane mode toggles to show the underlying display structure for rows and columns on the design surface.</span></span>  
  
     <span data-ttu-id="7a020-118">![Panel de agrupación con menú Modo avanzado](../media/groupingpane-advancedmode.png "Panel de agrupación con menú Modo avanzado")</span><span class="sxs-lookup"><span data-stu-id="7a020-118">![Grouping Pane with Advanced Mode menu](../media/groupingpane-advancedmode.png "Grouping Pane with Advanced Mode menu")</span></span>  
  
3.  <span data-ttu-id="7a020-119">En panel de grupo adecuado, haga clic en el nombre del grupo de filas o del grupo de columnas cuyas filas o columnas asociadas desea ocultar.</span><span class="sxs-lookup"><span data-stu-id="7a020-119">In the appropriate group pane, click the name of the row group or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="7a020-120">El grupo queda seleccionado y el panel de propiedades muestra las propiedades de **Miembro de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="7a020-120">The group is selected and the Properties pane shows the **Tablix Member** properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a020-121"> Si el panel Propiedades no está visible, haga clic en **Ver** en la cinta de opciones y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a020-121">If you do not see the Properties pane, click **View** on the Ribbon and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7a020-122">En `Hidden` , elija una de las siguientes opciones para establecer la visibilidad de este elemento de informe la primera vez que ejecute un informe:</span><span class="sxs-lookup"><span data-stu-id="7a020-122">In `Hidden`, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="7a020-123">Seleccione `False` esta opción para mostrar el elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-123">Select `False` to display the report item.</span></span>  
  
    -   <span data-ttu-id="7a020-124">Seleccione `True` esta opción para ocultar el elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-124">Select `True` to hide the report item.</span></span>  
  
    -   <span data-ttu-id="7a020-125">Seleccione **\<Expression>** esta casilla para abrir el cuadro de diálogo **expresión** y crear una expresión que se evalúa en tiempo de ejecución para determinar la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="7a020-125">Select **\<Expression>** to open the **Expression** dialog box to create an expression that is evaluated at run time to determine the visibility.</span></span>  
  
5.  <span data-ttu-id="7a020-126">En **ToggleItem**, en la lista desplegable, seleccione el nombre de un cuadro de texto al que quiera agregar la imagen de alternancia.</span><span class="sxs-lookup"><span data-stu-id="7a020-126">In **ToggleItem**, from the drop-down box, select the name of a text box to which to add the toggle image.</span></span>  
  
     <span data-ttu-id="7a020-127">En la siguiente imagen, el grupo de filas Color está configurado para permitir a los usuarios expandir y contraer las filas asociadas.</span><span class="sxs-lookup"><span data-stu-id="7a020-127">In the following image, the Color row group is configured enable users to expand and collapse associated rows.</span></span>  
  
     <span data-ttu-id="7a020-128">![Configuración de un grupo de filas que debe expandirse](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configuración de un grupo de filas que debe expandirse")</span><span class="sxs-lookup"><span data-stu-id="7a020-128">![Configuring a row group to be expanded](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configuring a row group to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a020-129">El cuadro de texto con la imagen de alternancia no puede ser el grupo de filas o columnas para el que desee ocultar las filas o columnas asociadas.</span><span class="sxs-lookup"><span data-stu-id="7a020-129">The text box with the toggle image cannot be the row or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="7a020-130">Debe estar en el mismo grupo que el elemento que se va a ocultar o en otro grupo antecesor.</span><span class="sxs-lookup"><span data-stu-id="7a020-130">It must either be in the same group as the item that is being hidden or in an ancestor group.</span></span> <span data-ttu-id="7a020-131">Por ejemplo, para alternar la visibilidad de las filas asociadas a un grupo secundario, seleccione un cuadro de texto de una fila asociada al grupo primario.</span><span class="sxs-lookup"><span data-stu-id="7a020-131">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span>  
  
6.  <span data-ttu-id="7a020-132">Para probar el control de alternancia, ejecute el informe y haga clic en el cuadro de texto que contiene la imagen de alternancia.</span><span class="sxs-lookup"><span data-stu-id="7a020-132">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="7a020-133">La presentación del informe se actualiza para mostrar los grupos de filas y los grupos de columnas con su visibilidad alternada.</span><span class="sxs-lookup"><span data-stu-id="7a020-133">The report display refreshes to show row groups and column groups with their toggled visibility.</span></span>  
  
     <span data-ttu-id="7a020-134">![Informe en ejecución con un grupo de filas que se pueden expandir](../media/expandcollapse-runreport-rowgroup.png "Informe en ejecución con un grupo de filas que se pueden expandir")</span><span class="sxs-lookup"><span data-stu-id="7a020-134">![Running report with expandable row group](../media/expandcollapse-runreport-rowgroup.png "Running report with expandable row group")</span></span>  
  
### <a name="to-add-expand-and-collapse-action-to-a-report-item"></a><span data-ttu-id="7a020-135">Para agregar una acción de expandir y contraer a un elemento de informe</span><span class="sxs-lookup"><span data-stu-id="7a020-135">To add expand and collapse action to a report item</span></span>  
  
1.  <span data-ttu-id="7a020-136">En la vista de diseño del informe, haga clic con el botón secundario en el elemento de informe que desee mostrar u ocultar y, a continuación, haga clic en *\<report item>* **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a020-136">In report design view, right-click the report item to show or hide, and then click *\<report item>* **Properties**.</span></span> <span data-ttu-id="7a020-137">*\<report item>* Se abrirá el cuadro de diálogo **propiedades** del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-137">The *\<report item>* **Properties** dialog box for the report item opens.</span></span>  
  
2.  <span data-ttu-id="7a020-138">Haga clic en **Visibilidad**.</span><span class="sxs-lookup"><span data-stu-id="7a020-138">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="7a020-139">En **Cuando se ejecute inicialmente el informe**, elija una de las opciones siguientes para establecer la visibilidad de este elemento de informe la primera vez que se ejecute el informe:</span><span class="sxs-lookup"><span data-stu-id="7a020-139">In **When the report is initially run**, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="7a020-140">Seleccione **Mostrar** para mostrar el elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-140">Select **Show** to display the report item.</span></span>  
  
    -   <span data-ttu-id="7a020-141">Seleccione **Ocultar** para ocultar el elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-141">Select **Hide** to hide the report item.</span></span>  
  
    -   <span data-ttu-id="7a020-142">Seleccione **Mostrar u ocultar en función de una expresión** para determinar la visibilidad mediante una expresión que se evalúa en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a020-142">Select **Show or hide based on an expression** to use an expression evaluated at run time to determine the visibility.</span></span> <span data-ttu-id="7a020-143">Haga clic en (**FX**) para abrir el cuadro de diálogo **expresión** y crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="7a020-143">Click (**fx**) to open the **Expression** dialog box to create an expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="7a020-144">Al especificar una expresión para la visibilidad, está estableciendo la propiedad Hidden del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-144">When you specify an expression for visibility, you are setting the Hidden property of the report item.</span></span> <span data-ttu-id="7a020-145">La expresión se evalúa como un valor `Boolean``True` para ocultar el elemento y `False` para mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="7a020-145">The expression evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span>  
  
4.  <span data-ttu-id="7a020-146">En **La visualización se puede activar o desactivar para este elemento de informe**, en la lista desplegable, escriba o seleccione el nombre de un cuadro de texto del informe en el que quiera mostrar la imagen de alternancia; por ejemplo, Cuadrodetexto1.</span><span class="sxs-lookup"><span data-stu-id="7a020-146">In **Display can be toggled by this report item**, from the drop-down box, type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span>  
  
     <span data-ttu-id="7a020-147">En la siguiente imagen, la tabla está configurada para permitir a los usuarios expandirla y contraerla.</span><span class="sxs-lookup"><span data-stu-id="7a020-147">In the following image, the table is configured to enable users to expand and collapse it.</span></span> <span data-ttu-id="7a020-148">La visualización de la tabla se alterna mediante el cuadro de texto de la tabla Products.</span><span class="sxs-lookup"><span data-stu-id="7a020-148">The display of the table is toggled by the Products Table text box.</span></span>  
  
     <span data-ttu-id="7a020-149">![Configuración de una tabla de informes que debe expandirse](../media/expandcollapse-reporttable.png "Configuración de una tabla de informes que debe expandirse")</span><span class="sxs-lookup"><span data-stu-id="7a020-149">![Configure a report table to be expanded](../media/expandcollapse-reporttable.png "Configure a report table to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a020-150">El cuadro de texto que elija debe estar en el ámbito contenedor o actual de este elemento de informe (hasta el cuerpo del informe, inclusive).</span><span class="sxs-lookup"><span data-stu-id="7a020-150">The text box that you choose must be in the current or containing scope for this report item (up to and including the report body).</span></span> <span data-ttu-id="7a020-151">Por ejemplo, para alternar la visibilidad de un gráfico, seleccione un cuadro de texto que esté en el mismo ámbito contenedor que el gráfico; por ejemplo, un rectángulo o el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="7a020-151">For example, to toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span> <span data-ttu-id="7a020-152">El cuadro de texto debe estar en la misma jerarquía contenedora o superior.</span><span class="sxs-lookup"><span data-stu-id="7a020-152">The text box must be in the same container hierarchy or higher.</span></span>  
  
5.  <span data-ttu-id="7a020-153">Para probar el control de alternancia, ejecute el informe y haga clic en el cuadro de texto que contiene la imagen de alternancia.</span><span class="sxs-lookup"><span data-stu-id="7a020-153">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="7a020-154">La presentación del informe se actualiza para mostrar los elementos de informe con su visibilidad alternada.</span><span class="sxs-lookup"><span data-stu-id="7a020-154">The report display refreshes to show report items with their toggled visibility.</span></span>  
  
     <span data-ttu-id="7a020-155">![Informe en ejecución con una tabla expandida](../media/expandcollapse-runreport-reporttable.png "Informe en ejecución con una tabla expandida")</span><span class="sxs-lookup"><span data-stu-id="7a020-155">![Running report with an expanding table](../media/expandcollapse-runreport-reporttable.png "Running report with an expanding table")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a020-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a020-156">See Also</span></span>  
 <span data-ttu-id="7a020-157">[Acción de obtención de detalles &#40;Generador de informes y SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a020-157">[Drilldown Action &#40;Report Builder and SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7a020-158">Ocultar un elemento &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7a020-158">Hide an Item &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/hide-an-item-report-builder-and-ssrs.md)  
  
  
