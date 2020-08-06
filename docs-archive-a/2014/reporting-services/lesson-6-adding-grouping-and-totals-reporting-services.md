---
title: 'Lección 6: Agregar grupos y totales (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e3d61228-2aa4-42cc-955e-602dbf3406a7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b98798005a984edf00aff469d4c1b09aa2e34d98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676866"
---
# <a name="lesson-6-adding-grouping-and-totals-reporting-services"></a><span data-ttu-id="23966-102">Lección 6: Agregar grupos y totales (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="23966-102">Lesson 6: Adding Grouping and Totals (Reporting Services)</span></span>
  <span data-ttu-id="23966-103">Agregue grupos y totales al informe para organizar y resumir los datos.</span><span class="sxs-lookup"><span data-stu-id="23966-103">Add grouping and totals to your report to organize and summarize your data.</span></span>  
  
 <span data-ttu-id="23966-104">Para obtener información sobre cómo agregar totales acumulados a informes, vea: [Agregar totales a informes de Reporting Services (SSRs)](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span><span class="sxs-lookup"><span data-stu-id="23966-104">For information about adding running totals to reports, see: [Adding totals to Reporting Services (SSRS) reports](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span></span>  
  
 <span data-ttu-id="23966-105">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="23966-105">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="23966-106">Para agrupar los datos de un informe</span><span class="sxs-lookup"><span data-stu-id="23966-106">To group data in a report</span></span>](#bkmk_groupdata)  
  
-   [<span data-ttu-id="23966-107">Para agregar totales a un informe</span><span class="sxs-lookup"><span data-stu-id="23966-107">To add totals to a report</span></span>](#bkmk_addtotals)  
  
-   [<span data-ttu-id="23966-108">Para agregar un total diario a un informe</span><span class="sxs-lookup"><span data-stu-id="23966-108">To add a daily total to a report</span></span>](#bkmk_adddailytotal)  
  
-   [<span data-ttu-id="23966-109">Para agregar un total general a un informe</span><span class="sxs-lookup"><span data-stu-id="23966-109">To add a grand total to a report</span></span>](#bkmk_addgrandtotal)  
  
-   [<span data-ttu-id="23966-110">Para publicar el informe en el servidor de informes (opcional)</span><span class="sxs-lookup"><span data-stu-id="23966-110">To Publish the Report to the Report Server (Optional)</span></span>](#bkmk_publishreport)  
  
##  <a name="to-group-data-in-a-report"></a><a name="bkmk_groupdata"></a><span data-ttu-id="23966-111">Para agrupar los datos de un informe</span><span class="sxs-lookup"><span data-stu-id="23966-111">To group data in a report</span></span>  
  
1.  <span data-ttu-id="23966-112">Haga clic en la pestaña **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="23966-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="23966-113">Si no ve el panel **Grupos de filas** , haga clic con el botón secundario en la superficie de diseño y haga clic en **ver** y en **Agrupar**.</span><span class="sxs-lookup"><span data-stu-id="23966-113">If you do not see the **Row Groups** pane , right-click the design surface and click **view** and then click **Grouping**.</span></span>  
  
3.  <span data-ttu-id="23966-114">En el panel **Datos de informe**, arrastre el campo `Date` hasta el panel **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="23966-114">From the **Report Data** pane, drag the `Date` field to the **Row Groups** pane.</span></span> <span data-ttu-id="23966-115">Sitúelo encima de la fila denominada **(Details)**.</span><span class="sxs-lookup"><span data-stu-id="23966-115">Place it above the row called **(Details)**.</span></span>  
  
     <span data-ttu-id="23966-116">Observe que el identificador de fila ahora tiene un corchete para mostrar un grupo.</span><span class="sxs-lookup"><span data-stu-id="23966-116">Note that the row handle now has a bracket in it, to show a group.</span></span> <span data-ttu-id="23966-117">Ahora, la tabla también tiene dos columnas Date, una de ellas en uno de los dos extremos de una línea de puntos vertical.</span><span class="sxs-lookup"><span data-stu-id="23966-117">The table now also has two Date columns -- one on either side of a vertical dotted line.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablegroups1design.gif "rs_BasicTableGroups1Design")  
  
4.  <span data-ttu-id="23966-118">En el panel **Datos de informe**, arrastre el campo `Order` hasta el panel **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="23966-118">From the **Report Data** pane, drag the `Order` field to the **Row Groups** pane.</span></span> <span data-ttu-id="23966-119">Sitúelo debajo de Date y encima de **(Details)**.</span><span class="sxs-lookup"><span data-stu-id="23966-119">Place it below Date and above **(Details)**.</span></span>  
  
     <span data-ttu-id="23966-120">Observe que el identificador de fila ahora tiene dos corchetes para mostrar dos grupos.</span><span class="sxs-lookup"><span data-stu-id="23966-120">Note that the row handle now has two brackets in it, to show two groups.</span></span> <span data-ttu-id="23966-121">La tabla ahora también tiene dos `Order` columnas.</span><span class="sxs-lookup"><span data-stu-id="23966-121">The table now has two `Order` columns, too.</span></span>  
  
5.  <span data-ttu-id="23966-122">Elimine las columnas Date y Order originales situadas a la **derecha** de la línea doble.</span><span class="sxs-lookup"><span data-stu-id="23966-122">Delete the original Date and Order columns to the **right** of the double line.</span></span> <span data-ttu-id="23966-123">Esta acción quita los valores de este registro para que solo se muestre el valor de grupo.</span><span class="sxs-lookup"><span data-stu-id="23966-123">This removes this individual record values so that only the group value is displayed.</span></span> <span data-ttu-id="23966-124">Seleccione los identificadores de las dos columnas y haga clic con el botón derecho en **Eliminar columnas**.</span><span class="sxs-lookup"><span data-stu-id="23966-124">Select the column handles for the two columns, right-click and click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="23966-125">![Seleccionar columnas para eliminar](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Seleccionar columnas para eliminar")</span><span class="sxs-lookup"><span data-stu-id="23966-125">![Select columns to delete](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Select columns to delete")</span></span>  
  
     <span data-ttu-id="23966-126">Puede volver a dar formato a los encabezados de columna y a la fecha.</span><span class="sxs-lookup"><span data-stu-id="23966-126">You can format the column headers and date again.</span></span>  
  
6.  <span data-ttu-id="23966-127">Cambie a la pestaña **Vista previa** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="23966-127">Switch to the **Preview** tab to preview the report.</span></span> <span data-ttu-id="23966-128">El aspecto deberá ser parecido al de la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="23966-128">It should look similar to the following illustration:</span></span>  
  
     <span data-ttu-id="23966-129">![Tabla agrupada por fecha y después por pedido](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Tabla agrupada por fecha y después por pedido")</span><span class="sxs-lookup"><span data-stu-id="23966-129">![Table grouped by date and then order](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table grouped by date and then order")</span></span>  
  
##  <a name="to-add-totals-to-a-report"></a><a name="bkmk_addtotals"></a><span data-ttu-id="23966-130">Para agregar totales a un informe</span><span class="sxs-lookup"><span data-stu-id="23966-130">To add totals to a report</span></span>  
  
1.  <span data-ttu-id="23966-131">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="23966-131">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="23966-132">Haga clic con el botón derecho en la celda de la región de datos que contiene el campo `[LineTotal]`y haga clic en **Agregar total**.</span><span class="sxs-lookup"><span data-stu-id="23966-132">Right-click the data region cell that contains the field `[LineTotal]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="23966-133">Esto agrega una fila con la suma de los importes de los pedidos.</span><span class="sxs-lookup"><span data-stu-id="23966-133">This adds a row with a sum of the dollar amount for each order.</span></span>  
  
3.  <span data-ttu-id="23966-134">Haga clic con el botón derecho en la celda que contiene el campo `[Qty]`y haga clic en **Agregar total**.</span><span class="sxs-lookup"><span data-stu-id="23966-134">Right-click the cell that contains the field `[Qty]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="23966-135">Esto agrega la suma de los importes de los pedidos a la fila de totales.</span><span class="sxs-lookup"><span data-stu-id="23966-135">This adds a sum of the quantity for each order to the totals row.</span></span>  
  
4.  <span data-ttu-id="23966-136">En la celda vacía situada a la izquierda de `Sum[Qty]`, escriba la etiqueta "**Order Total**".</span><span class="sxs-lookup"><span data-stu-id="23966-136">In the empty cell to the left of `Sum[Qty]`, type the label "**Order Total"**.</span></span>  
  
5.  <span data-ttu-id="23966-137">Puede agregar un color de fondo a la fila de totales.</span><span class="sxs-lookup"><span data-stu-id="23966-137">You can add a background color to the totals row.</span></span> <span data-ttu-id="23966-138">Seleccione las dos celdas que contienen las sumas y la celda con la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="23966-138">Select the two sum cells and the label cell.</span></span>  
  
6.  <span data-ttu-id="23966-139">En el menú **Formato** , haga clic en **Color de fondo**y, a continuación, haga clic en **Gris claro**y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="23966-139">On the **Format** menu, click **Background Color**, click **Light Gray**, and click **OK**.</span></span>  
  
     <span data-ttu-id="23966-140">![Vista Diseño: tabla básica con total de pedidos](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Vista Diseño: tabla básica con total de pedidos")</span><span class="sxs-lookup"><span data-stu-id="23966-140">![Design view: Basic table with order total](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Design view: Basic table with order total")</span></span>  
  
##  <a name="to-add-a-daily-total-to-a-report"></a><a name="bkmk_adddailytotal"></a><span data-ttu-id="23966-141">Para agregar un total diario a un informe</span><span class="sxs-lookup"><span data-stu-id="23966-141">To add a daily total to a report</span></span>  
  
1.  <span data-ttu-id="23966-142">Haga clic con el botón derecho en la celda Order , seleccione **Agregar total**y, luego, haga clic en **Después**.</span><span class="sxs-lookup"><span data-stu-id="23966-142">Right-click the Order cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="23966-143">Esto agrega una nueva fila que contiene las sumas de la cantidad y la cantidad en dólares para cada día, y la etiqueta "**total**" en la columna orden.</span><span class="sxs-lookup"><span data-stu-id="23966-143">This adds a new row containing sums of the quantity and dollar amount for each day, and the label "**Total**" in the Order column.</span></span>  
  
2.  <span data-ttu-id="23966-144">Escriba la palabra **Daily** delante de la palabra **Total** en la misma celda, de modo que se lea **Daily Total**.</span><span class="sxs-lookup"><span data-stu-id="23966-144">Type the word **Daily** before the word **Total** in the same cell, so it reads **Daily Total**.</span></span>  
  
3.  <span data-ttu-id="23966-145">Seleccione la celda **Daily Total** , las dos celdas **Sum** y la celda que queda vacía entre ellas.</span><span class="sxs-lookup"><span data-stu-id="23966-145">Select the **Daily Total** cell, the two **Sum** cells and the empty cell between them.</span></span>  
  
4.  <span data-ttu-id="23966-146">En el menú **Formato** , haga clic en **Color de fondo**, en **Anaranjado**y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="23966-146">On the **Format** menu, click **Background Color**, click **Orange**, and click **OK**.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablesumdaytotaldesign.gif "rs_BasicTableSumDayTotalDesign")  
  
##  <a name="to-add-a-grand-total-to-a-report"></a><a name="bkmk_addgrandtotal"></a><span data-ttu-id="23966-147">Para agregar un total general a un informe</span><span class="sxs-lookup"><span data-stu-id="23966-147">To add a grand total to a report</span></span>  
  
1.  <span data-ttu-id="23966-148">Haga clic con el botón derecho en la celda Date, seleccione **Agregar total**y, luego, haga clic en **Después**.</span><span class="sxs-lookup"><span data-stu-id="23966-148">Right-click the Date cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="23966-149">Esto agrega una nueva fila que contiene las sumas de la cantidad y la cantidad en dólares para el informe completo, así como la etiqueta **total** en la `Date` columna.</span><span class="sxs-lookup"><span data-stu-id="23966-149">This adds a new row containing sums of the quantity and dollar amount for the entire report, and the **Total** label in the `Date` column.</span></span>  
  
2.  <span data-ttu-id="23966-150">Escriba la palabra **Grand** delante de la palabra **Total** en la misma celda, de modo que se lea **Grand Total**.</span><span class="sxs-lookup"><span data-stu-id="23966-150">Type the word **Grand** before the word **Total** in the same cell, so it reads **Grand Total**.</span></span>  
  
3.  <span data-ttu-id="23966-151">Seleccione la celda **Grand Total** , las dos celdas **Sum** y las celdas que quedan vacías entre ellas.</span><span class="sxs-lookup"><span data-stu-id="23966-151">Select the **Grand Total** cell, the two **Sum** cells and the empty cells between them.</span></span>  
  
4.  <span data-ttu-id="23966-152">En el menú **Formato** , haga clic en **Color de fondo**y, a continuación, haga clic en **Azul claro**y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="23966-152">On the **Format** menu, click **Background Color**, click **Light Blue**, and click **OK**.</span></span>  
  
     <span data-ttu-id="23966-153">![Vista Diseño: total general en tabla básica](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Vista Diseño: total general en tabla básica")</span><span class="sxs-lookup"><span data-stu-id="23966-153">![Design view: Grand total in basic table](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Design view: Grand total in basic table")</span></span>  
  
5.  <span data-ttu-id="23966-154">Haga clic en Vista previa.</span><span class="sxs-lookup"><span data-stu-id="23966-154">Click Preview.</span></span>  
  
     <span data-ttu-id="23966-155">La última página debe tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="23966-155">The last page should look something like this:</span></span>  
  
     <span data-ttu-id="23966-156">![Vista previa: tabla básica con total general](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Vista previa: tabla básica con total general")</span><span class="sxs-lookup"><span data-stu-id="23966-156">![Preview: Basic table with grand total](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Preview: Basic table with grand total")</span></span>  
  
##  <a name="to-publish-the-report-to-the-report-server-optional"></a><a name="bkmk_publishreport"></a><span data-ttu-id="23966-157">Para publicar el informe en el servidor de informes (opcional)</span><span class="sxs-lookup"><span data-stu-id="23966-157">To Publish the Report to the Report Server (Optional)</span></span>  
  
1.  <span data-ttu-id="23966-158">Un paso opcional es publicar el informe completado en el servidor de informes en modo nativo de modo que pueda ver el informe en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="23966-158">An optional step is to publish the completed report to the native mode report server so you can view the report from Report Manager.</span></span>  
  
2.  <span data-ttu-id="23966-159">En la barra de herramientas, haga clic en **Proyecto** y, a continuación, haga clic en **tutorial Propiedades...**.</span><span class="sxs-lookup"><span data-stu-id="23966-159">On the toolbar click **Project** and then click **tutorial Properties...**</span></span>  
  
3.  <span data-ttu-id="23966-160">En **TargetServerURL** , escriba el nombre del nombre del servidor de informes, por ejemplo, **http:// \<servername> /ReportServer**</span><span class="sxs-lookup"><span data-stu-id="23966-160">In the **TargetServerURL** type the name of the name of your report server, for example **http://\<servername>/reportserver**</span></span>  
  
4.  <span data-ttu-id="23966-161">Haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="23966-161">Click **OK**</span></span>  
  
5.  <span data-ttu-id="23966-162">En la barra de herramientas, haga clic en **Generar** y, a continuación, haga clic en **Tutorial de implementación**.</span><span class="sxs-lookup"><span data-stu-id="23966-162">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>  
  
     <span data-ttu-id="23966-163">Si ve un mensaje similar al siguiente en la ventana de salida, indica que la implementación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="23966-163">If you see a message similar to the following in the output window, it indicates a successful deployment.</span></span>  
  
    > <span data-ttu-id="23966-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span><span class="sxs-lookup"><span data-stu-id="23966-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span></span> <span data-ttu-id="23966-165">El elemento está actualizado. Compilación completa--0 errores, 0 ADVERTENCIAS------implementación iniciada: proyecto: tutorial, configuración: depurar------implementar en el informe de http:// \<server name> /reportserverDeploying '/tutorial/sales Orders '. Implementación completa--0 errores, 0 ADVERTENCIAS = = = = = = = = = = compilación: 1 correcto o actualizado, 0 error, 0 omitido = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =</span><span class="sxs-lookup"><span data-stu-id="23966-165">Item is up to date.Build complete -- 0 errors, 0 warnings------ Deploy started: Project: tutorial, Configuration: Debug ------Deploying to http://\<server name>/reportserverDeploying report '/tutorial/Sales Orders'.Deploy complete -- 0 errors, 0 warnings========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==================== Deploy: 1 succeeded, 0 failed, 0 skipped ==========</span></span>  
  
     <span data-ttu-id="23966-166">Si aparece un mensaje de error similar al siguiente, compruebe que dispone de permisos en el servidor de informes y que ha iniciado [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="23966-166">If you see an error message similar to the following, verify you have permissions on the report server and you have started [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] with administrator privileges.</span></span>  
  
    > <span data-ttu-id="23966-167">"Los permisos concedidos al usuario ' XXXXXXXX \\<su nombre \> de usuario ' son insuficientes para realizar esta operación".</span><span class="sxs-lookup"><span data-stu-id="23966-167">"The permissions granted to user 'XXXXXXXX\\<your user name\>' are insufficient for performing this operation"</span></span>  
  
6.  <span data-ttu-id="23966-168">Inicie el Administrador de informes con privilegios de administrador, por ejemplo, haga clic con el botón secundario en el icono para Internet Explorer y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="23966-168">Start Report Manager with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>  
  
     <span data-ttu-id="23966-169">Busque la dirección URL del Administrador de informes, por ejemplo: `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="23966-169">Browse to the Report Manager URL, for example: `http://<server name>/reports`.</span></span>  
  
7.  <span data-ttu-id="23966-170">Busque la carpeta que contiene el informe y haga clic en el nombre del informe `Sales Orders` para verlo representado en el explorador.</span><span class="sxs-lookup"><span data-stu-id="23966-170">Browse to the folder that contains the report and click the name of the report `Sales Orders` to view the rendered report in the browser.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="23966-171">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="23966-171">Next Steps</span></span>  
 <span data-ttu-id="23966-172">Ha completado correctamente el tutorial Crear un informe de tabla básico.</span><span class="sxs-lookup"><span data-stu-id="23966-172">You have successfully completed the Creating a Basic Table Report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23966-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23966-173">See Also</span></span>  
 [<span data-ttu-id="23966-174">Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="23966-174">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
