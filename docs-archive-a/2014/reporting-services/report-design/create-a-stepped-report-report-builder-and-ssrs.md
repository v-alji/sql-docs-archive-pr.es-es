---
title: Crear un informe escalonado (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5933c4f0-c713-4ecb-b521-ff46c9c63fff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d845993ac1462cef2d39638101e5c7b9fc314b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671417"
---
# <a name="create-a-stepped-report-report-builder-and-ssrs"></a><span data-ttu-id="c7a24-102">Crear un informe escalonado (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c7a24-102">Create a Stepped Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c7a24-103">Un informe escalonado muestra las filas de detalles o los grupos secundarios con una sangría debajo de un grupo primario en la misma columna, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7a24-103">A stepped report shows detail rows or child groups indented under a parent group in the same column, as shown in the example below:</span></span>  
  
 <span data-ttu-id="c7a24-104">![Informe escalonado representado](../media/steppedreportrendered.gif "Informe escalonado representado")</span><span class="sxs-lookup"><span data-stu-id="c7a24-104">![Rendered stepped report](../media/steppedreportrendered.gif "Rendered stepped report")</span></span>  
  
 <span data-ttu-id="c7a24-105">Los informes de tabla tradicionales sitúan el grupo primario en una columna adyacente del informe.</span><span class="sxs-lookup"><span data-stu-id="c7a24-105">Traditional table reports place the parent group in an adjacent column on the report.</span></span> <span data-ttu-id="c7a24-106">La nueva región de datos tablix permite agregar un grupo y filas de detalles o grupos secundarios a la misma columna.</span><span class="sxs-lookup"><span data-stu-id="c7a24-106">The new tablix data region enables you to add a group and detail rows or child groups to the same column.</span></span> <span data-ttu-id="c7a24-107">Para diferenciar las filas de grupos de las filas de detalles o grupos secundarios, puede aplicar un formato, como el color de fuente, o puede aplicar una sangría a las filas de detalles.</span><span class="sxs-lookup"><span data-stu-id="c7a24-107">To differentiate the group rows from the detail or child group rows, you can apply formatting such as font color, or you can indent the detail rows.</span></span>  
  
 <span data-ttu-id="c7a24-108">Los procedimientos de este tema le muestran cómo crear manualmente un informe escalonado, pero también puede usar el asistente para nuevas tablas y matrices.</span><span class="sxs-lookup"><span data-stu-id="c7a24-108">The procedures in this topic show you how to manually create a stepped report, but you can also use the New Table and Matrix Wizard.</span></span> <span data-ttu-id="c7a24-109">Proporciona el diseño para los informes escalonados, haciendo fácil crearlos.</span><span class="sxs-lookup"><span data-stu-id="c7a24-109">It provides the layout for stepped reports, making it easy to create them.</span></span> <span data-ttu-id="c7a24-110">Después de completar el asistente, puede mejorar aún más el informe.</span><span class="sxs-lookup"><span data-stu-id="c7a24-110">After you complete the wizard, you can further enhance the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7a24-111">El asistente solamente está disponible en el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="c7a24-111">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-stepped-report"></a><span data-ttu-id="c7a24-112">Para crear un informe escalonado</span><span class="sxs-lookup"><span data-stu-id="c7a24-112">To create a stepped report</span></span>  
  
1.  <span data-ttu-id="c7a24-113">Cree un informe de tabla.</span><span class="sxs-lookup"><span data-stu-id="c7a24-113">Create a table report.</span></span> <span data-ttu-id="c7a24-114">Por ejemplo, inserte una región de datos tablix y agregue campos a la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="c7a24-114">For example, insert a tablix data region and add fields to the Data row.</span></span>  
  
2.  <span data-ttu-id="c7a24-115">Agregue un grupo primario al informe.</span><span class="sxs-lookup"><span data-stu-id="c7a24-115">Add a parent group to your report.</span></span>  
  
    1.  <span data-ttu-id="c7a24-116">Haga clic en cualquier lugar de la tabla para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="c7a24-116">Click anywhere in the table to select it.</span></span> <span data-ttu-id="c7a24-117">El panel Agrupación muestra el grupo de detalles en el panel Grupos de fila.</span><span class="sxs-lookup"><span data-stu-id="c7a24-117">The Grouping pane displays the Details group in the Row Groups pane.</span></span>  
  
    2.  <span data-ttu-id="c7a24-118">En el panel de agrupación, haga clic con el botón derecho en el grupo de detalles, seleccione **Agregar grupo**y, después, haga clic en **Grupo primario**.</span><span class="sxs-lookup"><span data-stu-id="c7a24-118">In the Grouping Pane, right-click the Details Group, point to **Add Group**, and then click **Parent Group**.</span></span>  
  
    3.  <span data-ttu-id="c7a24-119">En el cuadro de diálogo **Grupo de Tablix** , especifique un nombre para el grupo y escriba o seleccione una expresión de grupo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c7a24-119">In the **Tablix Group** dialog box, provide a name for the group and type or select a group expression from the drop-down list.</span></span> <span data-ttu-id="c7a24-120">La lista desplegable muestra las expresiones de campo simples que están disponibles en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="c7a24-120">The drop-down list displays the simple field expressions that are available in the Report Data pane.</span></span> <span data-ttu-id="c7a24-121">Por ejemplo, [PostalCode] es una expresión de campo simple para el campo PostalCode en un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="c7a24-121">For example, [PostalCode] is a simple field expression for the PostalCode field in a dataset.</span></span>  
  
    4.  <span data-ttu-id="c7a24-122">Seleccione **Agregar encabezado de grupo**.</span><span class="sxs-lookup"><span data-stu-id="c7a24-122">Select **Add group header**.</span></span> <span data-ttu-id="c7a24-123">Esta opción agrega una fila estática encima del grupo para la etiqueta y los totales de grupo.</span><span class="sxs-lookup"><span data-stu-id="c7a24-123">This option adds a static row above the group for the group label and group totals.</span></span> <span data-ttu-id="c7a24-124">Del mismo modo, puede seleccionar **Agregar pie de grupo** para agregar una fila estática debajo del grupo.</span><span class="sxs-lookup"><span data-stu-id="c7a24-124">Likewise, you can select **Add group footer** to add a static row below the group.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c7a24-125">Ahora ya tiene un informe tabular básico.</span><span class="sxs-lookup"><span data-stu-id="c7a24-125">You now have a basic tabular report.</span></span> <span data-ttu-id="c7a24-126">Cuando se represente, verá una columna con el valor de instancia de grupo y una o varias columnas con datos de detalles agrupados.</span><span class="sxs-lookup"><span data-stu-id="c7a24-126">When it is rendered, you see one column with the group instance value, and one or more columns with grouped detail data.</span></span> <span data-ttu-id="c7a24-127">En la siguiente ilustración se muestra el aspecto que podría tener la región de datos en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="c7a24-127">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="c7a24-128">![Región de datos de tabla con grupo](../media/tabledataregionwithgroup.gif "Región de datos de tabla con grupo")</span><span class="sxs-lookup"><span data-stu-id="c7a24-128">![Table data region with group](../media/tabledataregionwithgroup.gif "Table data region with group")</span></span>  
  
     <span data-ttu-id="c7a24-129">En la siguiente ilustración se muestra el aspecto que podría tener la región de datos representada al visualizar el informe.</span><span class="sxs-lookup"><span data-stu-id="c7a24-129">The following figure shows how the rendered data region might look when you view the report.</span></span>  
  
     <span data-ttu-id="c7a24-130">![Informe agrupado representado](../media/tablereportrendered.gif "Informe agrupado representado")</span><span class="sxs-lookup"><span data-stu-id="c7a24-130">![Rendered grouped report](../media/tablereportrendered.gif "Rendered grouped report")</span></span>  
  
3.  <span data-ttu-id="c7a24-131">En un informe escalonado, no es necesaria la primera columna que muestra la instancia de grupo.</span><span class="sxs-lookup"><span data-stu-id="c7a24-131">For a stepped report, you do not need the first column that shows the group instance.</span></span> <span data-ttu-id="c7a24-132">En su lugar, copie el valor en la celda de encabezado de grupo, elimine la columna de grupo y pegue el primer cuadro de texto en la fila de encabezado de grupo.</span><span class="sxs-lookup"><span data-stu-id="c7a24-132">Instead, copy the value in the group header cell, delete the group column, and paste in the first text box in the group header row.</span></span> <span data-ttu-id="c7a24-133">Para quitar la columna de grupo, haga clic con el botón derecho en la columna o celda de grupo y, después, haga clic en **Eliminar columnas**.</span><span class="sxs-lookup"><span data-stu-id="c7a24-133">To remove the group column, right-click the group column or cell, and click **Delete Columns**.</span></span> <span data-ttu-id="c7a24-134">En la siguiente ilustración se muestra el aspecto que podría tener la región de datos en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="c7a24-134">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="c7a24-135">![Región de datos con fila de encabezado de grupo](../media/tabledataregiongroupheader.gif "Región de datos con fila de encabezado de grupo")</span><span class="sxs-lookup"><span data-stu-id="c7a24-135">![Data region with group header row](../media/tabledataregiongroupheader.gif "Data region with group header row")</span></span>  
  
4.  <span data-ttu-id="c7a24-136">Para aplicar una sangría a las filas de detalles situadas debajo de la fila de encabezado de grupo en la misma columna, cambie el relleno de la celda de datos de detalles.</span><span class="sxs-lookup"><span data-stu-id="c7a24-136">To indent the detail rows under the group header row in the same column, change the padding of the detail data cell.</span></span>  
  
    1.  <span data-ttu-id="c7a24-137">Seleccione la celda con el campo detallado a la que desea aplicar la sangría.</span><span class="sxs-lookup"><span data-stu-id="c7a24-137">Select the cell with the detail field that you want to indent.</span></span> <span data-ttu-id="c7a24-138">Aparecerán las propiedades del cuadro de texto para dicha celda en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="c7a24-138">The text box properties for that cell appear in the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="c7a24-139">En el panel de propiedades, debajo de **Alineación**, expanda las propiedades para **Relleno**.</span><span class="sxs-lookup"><span data-stu-id="c7a24-139">In the Properties pane, under **Alignment**, expand the properties for **Padding**.</span></span>  
  
    3.  <span data-ttu-id="c7a24-140">A la **izquierda**, escriba un nuevo valor de relleno, como `.5in` .</span><span class="sxs-lookup"><span data-stu-id="c7a24-140">For **Left**, type a new padding value, such as `.5in`.</span></span> <span data-ttu-id="c7a24-141">El relleno aplica una sangría al texto de la celda según el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="c7a24-141">Padding indents the text in the cell by the value you specify.</span></span> <span data-ttu-id="c7a24-142">El valor de relleno predeterminado es 2 puntos.</span><span class="sxs-lookup"><span data-stu-id="c7a24-142">The default padding is 2 points.</span></span> <span data-ttu-id="c7a24-143">Los valores válidos para las propiedades de relleno son cero o un número positivo, seguido de un designador de tamaño.</span><span class="sxs-lookup"><span data-stu-id="c7a24-143">Valid values for the Padding properties are zero or a positive number, followed by a size designator.</span></span>  
  
         <span data-ttu-id="c7a24-144">Los designadores de tamaño son:</span><span class="sxs-lookup"><span data-stu-id="c7a24-144">Size designators are:</span></span>  
  
        |||  
        |-|-|  
        |`in`|<span data-ttu-id="c7a24-145">Pulgadas (1 pulgada = 2,54 centímetros)</span><span class="sxs-lookup"><span data-stu-id="c7a24-145">Inches (1 inch = 2.54 centimeters)</span></span>|  
        |`cm`|<span data-ttu-id="c7a24-146">Centímetros</span><span class="sxs-lookup"><span data-stu-id="c7a24-146">Centimeters</span></span>|  
        |`mm`|<span data-ttu-id="c7a24-147">Milímetros</span><span class="sxs-lookup"><span data-stu-id="c7a24-147">Millimeters</span></span>|  
        |`pt`|<span data-ttu-id="c7a24-148">Puntos (1 punto = 1/72 pulgada)</span><span class="sxs-lookup"><span data-stu-id="c7a24-148">Points (1 point = 1/72 inch)</span></span>|  
        |`pc`|<span data-ttu-id="c7a24-149">Picas (1 pica = 12 puntos)</span><span class="sxs-lookup"><span data-stu-id="c7a24-149">Picas (1 pica = 12 points)</span></span>|  
  
     <span data-ttu-id="c7a24-150">La región de datos tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7a24-150">Your data region will look similar to the following example.</span></span>  
  
     <span data-ttu-id="c7a24-151">![Región de datos para informe escalonado](../media/steppedreportdataregion.gif "Región de datos para informe escalonado")</span><span class="sxs-lookup"><span data-stu-id="c7a24-151">![Data region for stepped report](../media/steppedreportdataregion.gif "Data region for stepped report")</span></span>  
  
     <span data-ttu-id="c7a24-152">**Región de datos para el diseño del informe escalonado**</span><span class="sxs-lookup"><span data-stu-id="c7a24-152">**Data Region for Stepped Report Layout**</span></span>  
  
     <span data-ttu-id="c7a24-153">En la pestaña **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c7a24-153">On the **Home** tab Click **Run**.</span></span> <span data-ttu-id="c7a24-154">El informe muestra el grupo con niveles de sangría para los valores de grupo secundario.</span><span class="sxs-lookup"><span data-stu-id="c7a24-154">The report displays the group with indented levels for the child group values.</span></span>  
  
### <a name="to-create-a-stepped-report-with-multiple-groups"></a><span data-ttu-id="c7a24-155">Para crear un informe escalonado con varios grupos</span><span class="sxs-lookup"><span data-stu-id="c7a24-155">To create a stepped report with multiple groups</span></span>  
  
1.  <span data-ttu-id="c7a24-156">Cree un informe tal y como se describe en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="c7a24-156">Create a report as described in the previous procedure.</span></span>  
  
2.  <span data-ttu-id="c7a24-157">Agregue grupos adicionales al informe.</span><span class="sxs-lookup"><span data-stu-id="c7a24-157">Add additional groups to your report.</span></span>  
  
    1.  <span data-ttu-id="c7a24-158">En el panel Grupos de filas, haga clic con el botón derecho en el grupo, haga clic en **Agregar grupo**y, después, elija el tipo de grupo que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="c7a24-158">In the Row Groups pane, right-click the group, click **Add Group**, and then choose the type of group you want to add.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c7a24-159">Existen varias formas de agregar grupos a una región de datos.</span><span class="sxs-lookup"><span data-stu-id="c7a24-159">There are several ways to add groups to a data region.</span></span> <span data-ttu-id="c7a24-160">Para obtener más información, vea [Agregar o eliminar un grupo en una región de datos &#40;generador de informes y SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c7a24-160">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
    2.  <span data-ttu-id="c7a24-161">En el cuadro de diálogo **Grupo de Tablix** , escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="c7a24-161">In the **Tablix Group** dialog box, type a name.</span></span>  
  
    3.  <span data-ttu-id="c7a24-162">En **Expresión de grupo**, escriba una expresión o seleccione un campo de conjunto de datos por el que realizar la agrupación.</span><span class="sxs-lookup"><span data-stu-id="c7a24-162">In **Group expression**, type an expression or select a dataset field to group on.</span></span> <span data-ttu-id="c7a24-163">Para crear una expresión, haga clic en el botón de expresión (**fx**) para abrir el cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="c7a24-163">To create an expression, click the expression (**fx**) button to open the **Expression** dialog box.</span></span>  
  
    4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="c7a24-164">Cambie el relleno para la celda que muestra los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="c7a24-164">Change the padding for the cell that displays the group data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a24-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7a24-165">See Also</span></span>  
 <span data-ttu-id="c7a24-166">[Encabezados y pies de página &#40;Generador de informes y SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7a24-166">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c7a24-167">[Aplicar formato a los elementos de informe &#40;Generador de informes y SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7a24-167">[Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c7a24-168">[&#40;de la región de datos Tablix Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7a24-168">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c7a24-169">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7a24-169">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c7a24-170">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7a24-170">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c7a24-171">[Enumera &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7a24-171">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c7a24-172">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c7a24-172">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
