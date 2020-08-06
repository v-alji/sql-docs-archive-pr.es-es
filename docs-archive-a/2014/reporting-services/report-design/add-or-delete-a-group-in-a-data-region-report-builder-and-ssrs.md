---
title: Agregar o eliminar un grupo en una región de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4de53c3c-c6fc-49ce-b692-3609fc0b3ec5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c355ca87db578d47181935e1ca6bc48e75bf8b8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747481"
---
# <a name="add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="c059b-102">Agregar o eliminar un grupo en una región de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c059b-102">Add or Delete a Group in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c059b-103">Agregue un grupo a una región de datos cuando desee organizar los datos según un valor o un conjunto de expresiones determinado, para la presentación y los cálculos.</span><span class="sxs-lookup"><span data-stu-id="c059b-103">Add a group to a data region when you want to organize data by a specific value or set of expressions, for display and calculations.</span></span> <span data-ttu-id="c059b-104">Un grupo tiene un nombre y una expresión que identifica qué datos de un conjunto de datos pertenecen al grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-104">A group has a name and an expression that identifies which data from a dataset belongs to the group.</span></span> <span data-ttu-id="c059b-105">Para obtener más información sobre los grupos, vea [Descripción de los grupos &#40;Generador de informes y SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c059b-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c059b-106">En una región de datos Tablix, haga clic en la tabla, la matriz o la lista para mostrar el panel Agrupación.</span><span class="sxs-lookup"><span data-stu-id="c059b-106">In a tablix data region, click in the table, matrix, or list to display the Grouping pane.</span></span> <span data-ttu-id="c059b-107">Arrastre campos del conjunto de datos al panel Grupo de filas y Grupo de columnas para crear grupos primarios o secundarios.</span><span class="sxs-lookup"><span data-stu-id="c059b-107">Drag dataset fields to the Row Group and Column Group pane to create parent or child groups.</span></span> <span data-ttu-id="c059b-108">Haga clic con el botón secundario en un grupo existente para agregar un grupo adyacente.</span><span class="sxs-lookup"><span data-stu-id="c059b-108">Right-click an existing group to add an adjacent group.</span></span> <span data-ttu-id="c059b-109">Por definición, el grupo de detalles es el grupo más interior y solo se puede agregar como grupo secundario.</span><span class="sxs-lookup"><span data-stu-id="c059b-109">By definition, the details group is the innermost group and can only be added as a child group.</span></span> <span data-ttu-id="c059b-110">Haga clic con el botón secundario en un grupo existente para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c059b-110">Right-click an existing group to delete it.</span></span> <span data-ttu-id="c059b-111">Las filas y columnas en que se visualizarán los valores del grupo se agregan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c059b-111">Rows and columns on which to display group values are automatically added for you.</span></span> <span data-ttu-id="c059b-112">Para más información, vea [Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c059b-112">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c059b-113">En una región de datos Gráfico, haga clic en el gráfico para mostrar las zonas de colocación.</span><span class="sxs-lookup"><span data-stu-id="c059b-113">In a Chart data region, click in the chart to display the drop-zones.</span></span> <span data-ttu-id="c059b-114">Cree grupos arrastrando campos de conjunto de datos a las zonas de colocación de categorías y de series.</span><span class="sxs-lookup"><span data-stu-id="c059b-114">Create groups by dragging dataset fields to the category and series drop zones.</span></span> <span data-ttu-id="c059b-115">Para agregar grupos anidados, agregue varios campos a la zona de colocación.</span><span class="sxs-lookup"><span data-stu-id="c059b-115">To add nested groups, add multiple fields to the drop-zone.</span></span>  
  
 <span data-ttu-id="c059b-116">De forma predeterminada, no se definen grupos en un medidor.</span><span class="sxs-lookup"><span data-stu-id="c059b-116">Groups are not defined in a gauge by default.</span></span> <span data-ttu-id="c059b-117">El comportamiento predeterminado para el medidor consiste en agregar todos los valores del campo especificado en un valor que se muestra en el medidor.</span><span class="sxs-lookup"><span data-stu-id="c059b-117">The default behavior for the gauge is to aggregate all values in the specified field into one value that is displayed on the gauge.</span></span> <span data-ttu-id="c059b-118">Para obtener más información, vea [Medidores &#40;Generador de informes y SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c059b-118">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="c059b-119">Para agregar un grupo de filas o de columnas primario o secundario a una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c059b-119">To add a parent or child row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="c059b-120">Arrastre un campo desde el panel **Datos de informe** hasta el panel **Grupos de filas** o el panel **Grupos de columnas** .</span><span class="sxs-lookup"><span data-stu-id="c059b-120">Drag a field from the **Report Data** pane to the **Row Groups** pane or the **Column Groups** pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c059b-121">Si no ve el panel de agrupación, en la pestaña Vista, haga clic en **Agrupación**.</span><span class="sxs-lookup"><span data-stu-id="c059b-121">If you do not see the Grouping pane, on the View tab, click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="c059b-122">Coloque el campo por encima o por debajo de la jerarquía de grupos usando la barra de guía para situar el grupo como grupo primario o grupo secundario de un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="c059b-122">Drop the field above or below the group hierarchy using the guide bar to place the group as a parent group or a child group to an existing group.</span></span>  
  
     <span data-ttu-id="c059b-123">El grupo se agrega con un nombre, una expresión de grupo y una expresión de ordenación predeterminados que se basan en el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="c059b-123">The group is added with a default name, group expression, and sort expression that is based on the field name.</span></span>  
  
### <a name="to-add-an-adjacent-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="c059b-124">Para agregar un grupo de filas o de columnas adyacente a una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c059b-124">To add an adjacent row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="c059b-125">En el panel Agrupación, haga clic con el botón secundario en un grupo del mismo nivel que el grupo que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="c059b-125">In the Grouping pane, right-click a group that is a peer to the group that you want to add.</span></span> <span data-ttu-id="c059b-126">Haga clic en **Agregar grupo**y, a continuación, en **Adyacente anterior** o en **Adyacente posterior** para especificar dónde se debe agregar el grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-126">Click **Add Group**, and then click **Adjacent Before** or **Adjacent After** to specify where to add the group.</span></span> <span data-ttu-id="c059b-127">Se abre el cuadro de diálogo **Grupo de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="c059b-127">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c059b-128">En **Nombre**, escriba un nombre para el grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-128">In **Name**, type a name for the group.</span></span>  
  
3.  <span data-ttu-id="c059b-129">En **Expresión de grupo**, escriba una expresión o haga clic en el botón Expresión (**fx**) para crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="c059b-129">In **Group expression**, type an expression or click the expression button (**fx**) to create an expression.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c059b-130">Se agrega un nuevo grupo al panel Agrupación y también se agrega una fila o columna en que mostrar los valores del grupo a la región de datos Tablix de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="c059b-130">A new group is added to the Grouping pane and a row or column on which to display group values is added to the tablix data region on the design surface.</span></span>  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="c059b-131">Para agregar un grupo de detalles a una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c059b-131">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="c059b-132">En el panel de agrupación, haga clic con el botón derecho en un grupo que sea el grupo secundario más interno, pero no el grupo **Detalles** .</span><span class="sxs-lookup"><span data-stu-id="c059b-132">In the Grouping pane, right-click a group that is the innermost child group, but not the **Details** group.</span></span> <span data-ttu-id="c059b-133">Haga clic en **Agregar grupo**y, a continuación, haga clic en **Grupo secundario**.</span><span class="sxs-lookup"><span data-stu-id="c059b-133">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="c059b-134">Se abre el cuadro de diálogo **Grupo de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="c059b-134">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c059b-135">En **Expresión de grupo**, deje en blanco la expresión.</span><span class="sxs-lookup"><span data-stu-id="c059b-135">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="c059b-136">Los grupos de detalles no tienen ninguna expresión.</span><span class="sxs-lookup"><span data-stu-id="c059b-136">A details group has no expression.</span></span>  
  
3.  <span data-ttu-id="c059b-137">Seleccione **Mostrar datos detallados**.</span><span class="sxs-lookup"><span data-stu-id="c059b-137">Select **Show detail data**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c059b-138">Se agrega un nuevo grupo de detalles como un grupo secundario en el panel Agrupación, y el identificador de fila para el grupo seleccionado en el paso 1 muestra el icono de grupo de detalles.</span><span class="sxs-lookup"><span data-stu-id="c059b-138">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="c059b-139">Para obtener más información sobre los identificadores, vea [Celdas, filas y columnas de la región de datos Tablix &#40;Generador de informes y SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c059b-139">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-edit-a-row-or-column-group-in-a-tablix-data-region"></a><span data-ttu-id="c059b-140">Para editar un grupo de filas o de columnas de una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c059b-140">To edit a row or column group in a tablix data region</span></span>  
  
1.  <span data-ttu-id="c059b-141">En la superficie de diseño del informe, haga clic en cualquier lugar de la región de datos Tablix para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="c059b-141">On the report design surface, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c059b-142">El Panel de agrupación muestra los grupos de filas y de columnas.</span><span class="sxs-lookup"><span data-stu-id="c059b-142">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="c059b-143">Haga clic con el botón derecho en el grupo y, después, haga clic en **Propiedades de grupo**.</span><span class="sxs-lookup"><span data-stu-id="c059b-143">Right-click the group, and then click **Group Properties**.</span></span>  
  
3.  <span data-ttu-id="c059b-144">En **Nombre**, escriba el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-144">In **Name**, type the name of the group.</span></span>  
  
4.  <span data-ttu-id="c059b-145">En **Expresiones de grupo**, escriba o seleccione una expresión simple, o bien haga clic en el botón Expresión (**fx**) para crear una expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-145">In **Group expressions**, type or select a simple expression, or click the Expression (**fx**) button to create a group expression.</span></span>  
  
5.  <span data-ttu-id="c059b-146">Haga clic en **Agregar** para crear expresiones adicionales.</span><span class="sxs-lookup"><span data-stu-id="c059b-146">Click **Add** to create additional expressions.</span></span> <span data-ttu-id="c059b-147">Todas las expresiones que especifique se combinan utilizando un AND lógico para especificar los datos para este grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-147">All expressions you specify are combined using a logical AND to specify data for this group.</span></span>  
  
6.  <span data-ttu-id="c059b-148">(Opcional) Haga clic en **Saltos de página** para establecer las opciones de salto de página.</span><span class="sxs-lookup"><span data-stu-id="c059b-148">(Optional) Click **Page Breaks** to set page break options.</span></span>  
  
7.  <span data-ttu-id="c059b-149">(Opcional) Haga clic en **Ordenar** para seleccionar o escribir expresiones que especifiquen el criterio de ordenación de los valores del grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-149">(Optional) Click **Sorting** to select or type expressions that specify the sort order for values in the group.</span></span>  
  
8.  <span data-ttu-id="c059b-150">(Opcional) Haga clic en **Visibilidad** para seleccionar las opciones de visibilidad del elemento.</span><span class="sxs-lookup"><span data-stu-id="c059b-150">(Optional) Click **Visibility** to select the visibility options for the item.</span></span>  
  
9. <span data-ttu-id="c059b-151">(Opcional) Haga clic en **Filtros** para establecer filtros para este grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-151">(Optional) Click **Filters** to set filters for this group.</span></span>  
  
10. <span data-ttu-id="c059b-152">(Opcional) Haga clic en **Variables** para definir variables en el ámbito de este grupo a las que se puede tener acceso desde cualquier grupo secundario.</span><span class="sxs-lookup"><span data-stu-id="c059b-152">(Optional) Click **Variables** to define variables scoped to this group and accessible from any child groups.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-tablix-data-region"></a><span data-ttu-id="c059b-153">Para eliminar un grupo de una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c059b-153">To delete a group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="c059b-154">En el panel de agrupación, haga clic con el botón derecho en el grupo y, después, haga clic en **Eliminar grupo**.</span><span class="sxs-lookup"><span data-stu-id="c059b-154">In the Grouping pane, right-click the group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="c059b-155">En el cuadro de diálogo **Eliminar grupo** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c059b-155">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="c059b-156">**Eliminar el grupo y las filas y columnas relacionadas** : elija esta opción para eliminar la definición del grupo y todas las filas relacionadas que muestran datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-156">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="c059b-157">Para el grupo de detalles, si la misma fila pertenece a los datos del grupo y de detalles, solo se eliminan las filas de los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="c059b-157">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="c059b-158">**Eliminar solo el grupo** : elija esta opción para mantener la estructura de la región de datos Tablix y eliminar solo la definición del grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-158">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-details-group-from-a-tablix-data-region"></a><span data-ttu-id="c059b-159">Para eliminar un grupo de detalles de una región de datos Tablix</span><span class="sxs-lookup"><span data-stu-id="c059b-159">To delete a details group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="c059b-160">En el panel de agrupación, haga clic con el botón derecho en el grupo de detalles y, después, haga clic en **Eliminar grupo**.</span><span class="sxs-lookup"><span data-stu-id="c059b-160">In the Grouping pane, right-click the details group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="c059b-161">En el cuadro de diálogo **Eliminar grupo** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c059b-161">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="c059b-162">**Eliminar el grupo y las filas y columnas relacionadas** : elija esta opción para eliminar la definición del grupo y todas las filas relacionadas que muestran datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-162">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="c059b-163">Para el grupo de detalles, si la misma fila pertenece a los datos del grupo y de detalles, solo se eliminan las filas de los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="c059b-163">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="c059b-164">**Eliminar solo el grupo** : elija esta opción para mantener la estructura de la región de datos Tablix y eliminar solo la definición del grupo.</span><span class="sxs-lookup"><span data-stu-id="c059b-164">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c059b-165">Se elimina el grupo de detalles.</span><span class="sxs-lookup"><span data-stu-id="c059b-165">The details group is deleted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c059b-166">Compruebe que, después de quitar una fila de detalles, la expresión de cada celda especifica una expresión de agregado donde corresponda.</span><span class="sxs-lookup"><span data-stu-id="c059b-166">Verify that after you remove a details row, the expression in each cell specifies an aggregate expression where appropriate.</span></span> <span data-ttu-id="c059b-167">Si es necesario, edite la expresión para especificar las funciones de agregado que se requieran.</span><span class="sxs-lookup"><span data-stu-id="c059b-167">If necessary, edit the expression to specify aggregate functions as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c059b-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c059b-168">See Also</span></span>  
 <span data-ttu-id="c059b-169">[Referencias a las colecciones de variables de informe y de grupo &#40;Generador de informes y SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-169">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 <span data-ttu-id="c059b-170">[Ejemplos de expresión de grupo &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-170">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c059b-171">[Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-171">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c059b-172">[Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-172">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c059b-173">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-173">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c059b-174">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-174">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c059b-175">[Listas &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c059b-175">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c059b-176">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c059b-176">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
