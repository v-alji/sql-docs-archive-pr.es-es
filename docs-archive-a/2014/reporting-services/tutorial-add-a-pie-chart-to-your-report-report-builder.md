---
title: 'Tutorial: Agregar un gráfico circular a un informe (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747933"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a><span data-ttu-id="5b6b6-102">Tutorial: Agregar un gráfico circular a un informe (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="5b6b6-102">Tutorial: Add a Pie Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="5b6b6-103">Los gráficos circulares y los gráficos de anillos muestran los datos como una proporción del total.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-103">Pie charts and doughnut charts display data as a proportion of the whole.</span></span> <span data-ttu-id="5b6b6-104">Los gráficos circulares se usan normalmente para realizar comparaciones entre grupos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-104">Pie charts are most commonly used to make comparisons between groups.</span></span> <span data-ttu-id="5b6b6-105">Los gráficos circulares y de anillos, junto con los gráficos piramidales y de embudo, forman un grupo de gráficos conocidos como gráficos de formas.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-105">Pie and doughnut charts, along with pyramid and funnel charts, constitute a group of charts known as shape charts.</span></span> <span data-ttu-id="5b6b6-106">Los gráficos de formas no tienen ejes.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-106">Shape charts have no axes.</span></span> <span data-ttu-id="5b6b6-107">Cuando se coloca un campo numérico en un gráfico de formas, el gráfico calcula el porcentaje de cada valor en relación con el total.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-107">When a numeric field is dropped on a shape chart, the chart calculates the percentage of each value to the total.</span></span>  
  
 <span data-ttu-id="5b6b6-108">Si hay demasiados puntos de datos en un gráfico circular, es posible que las etiquetas de los puntos de datos estén demasiado amontonadas y no puedan leerse.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-108">If there are too many data points on a pie chart, your data point labels might be too crowded to read.</span></span> <span data-ttu-id="5b6b6-109">En ese caso, considere la posibilidad de usar un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-109">In that case, consider using a line chart.</span></span> <span data-ttu-id="5b6b6-110">Considere usar únicamente gráficos circulares después de haber agregado los datos en algunos puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-110">Consider using pie charts only after you have aggregated your data into a few data points.</span></span>  
  
 <span data-ttu-id="5b6b6-111">La siguiente ilustración muestra el gráfico circular que creará.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-111">The following illustration shows the pie chart you will create.</span></span>  
  
 <span data-ttu-id="5b6b6-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span><span class="sxs-lookup"><span data-stu-id="5b6b6-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="5b6b6-113">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="5b6b6-113">What You Will Learn</span></span>  
 <span data-ttu-id="5b6b6-114">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="5b6b6-114">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="5b6b6-115">Crear un gráfico circular a partir del Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="5b6b6-115">Create a Pie Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="5b6b6-116">Elegir el tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="5b6b6-116">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="5b6b6-117">Mostrar porcentajes en cada sector</span><span class="sxs-lookup"><span data-stu-id="5b6b6-117">Display Percentages in Each Slice</span></span>](#Percentages)  
  
4.  [<span data-ttu-id="5b6b6-118">Unir los sectores pequeños en un solo sector</span><span class="sxs-lookup"><span data-stu-id="5b6b6-118">Combine Small Slices into One Slice</span></span>](#CombineSlices)  
  
5.  [<span data-ttu-id="5b6b6-119">Personalizar el efecto de dibujo</span><span class="sxs-lookup"><span data-stu-id="5b6b6-119">Customize the Drawing Effect</span></span>](#DrawingEffect)  
  
6.  [<span data-ttu-id="5b6b6-120">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="5b6b6-120">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="5b6b6-121">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="5b6b6-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="5b6b6-122">En este tutorial, los pasos del asistente se encuentran reunidos en dos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-122">In this tutorial, the steps for the wizard are consolidated into two procedures.</span></span> <span data-ttu-id="5b6b6-123">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, agregar un origen de datos y agregar un conjunto de datos, vea el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5b6b6-123">For step-by-step instructions about how to browse to a report server, add a data source, and add a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="5b6b6-124">Tiempo estimado para completar este tutorial: 10 minutos</span><span class="sxs-lookup"><span data-stu-id="5b6b6-124">Estimated time to complete this tutorial: 10 minutes</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b6b6-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b6b6-125">Requirements</span></span>  
 <span data-ttu-id="5b6b6-126">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="5b6b6-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="5b6b6-127">1. crear un gráfico circular a partir del Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="5b6b6-127">1. Create a Pie Chart from the Chart Wizard</span></span>  
 <span data-ttu-id="5b6b6-128">En el cuadro de diálogo Introducción, use el Asistente para gráficos con el fin de crear un conjunto de datos incrustado, elegir un origen de datos compartido y crear un gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-128">From the Getting Started dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a pie chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b6b6-129">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-129">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="5b6b6-130">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-130">This makes the query quite long.</span></span> <span data-ttu-id="5b6b6-131">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="5b6b6-132">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="5b6b6-133">Para crear un informe de gráfico</span><span class="sxs-lookup"><span data-stu-id="5b6b6-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="5b6b6-134">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="5b6b6-135">Aparecerá el cuadro de diálogo Introducción.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-135">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b6b6-136"> Si el cuadro de diálogo Introducción no aparece, en el botón Generador de informes, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-136">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="5b6b6-137">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="5b6b6-138">En el panel derecho, haga clic en **Asistente para gráficos**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="5b6b6-139">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="5b6b6-140">En la página **Elegir una conexión a un origen de datos** , seleccione un origen de datos existente o vaya al servidor de informes y seleccione un origen de datos, y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="5b6b6-141">Puede que necesite escribir un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b6b6-142">El origen de datos que elija no importa, con tal de que tenga los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="5b6b6-143">No está recibiendo datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="5b6b6-144">Para obtener más información, consulte [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5b6b6-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="5b6b6-145">En la página **diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-145">On the **Design a Query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="5b6b6-146">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="5b6b6-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="5b6b6-147">(Opcional) Haga clic en el botón Ejecutar (**!**) para ver los datos en los que se basará su gráfico.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="5b6b6-148">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="5b6b6-149">2. elegir el tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="5b6b6-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="5b6b6-150">Podrá elegir entre varios tipos de gráfico predefinidos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="5b6b6-151">Para agregar un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="5b6b6-151">To add a pie chart</span></span>  
  
1.  <span data-ttu-id="5b6b6-152">En la página **elegir un tipo de gráfico** , haga clic en **circular**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-152">On the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span> <span data-ttu-id="5b6b6-153">Se abrirá la página **Organizar campos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-153">The **Arrange chart fields** page opens.</span></span>  
  
     <span data-ttu-id="5b6b6-154">En la página **Organizar campos del gráfico** , arrastre el campo Product hasta el panel **Categorías** .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-154">On the **Arrange chart fields** page, drag the Product field to the **Categories** pane.</span></span> <span data-ttu-id="5b6b6-155">Las categorías definen el número de segmentos del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-155">Categories define the number of slices in the pie chart.</span></span> <span data-ttu-id="5b6b6-156">En este ejemplo, habrá ocho segmentos, uno para cada producto.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-156">In this example, there will be eight slices, one for each product.</span></span>  
  
2.  <span data-ttu-id="5b6b6-157">Arrastre el campo Sales hasta el panel **Valores** .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-157">Drag the Sales field to the **Values** pane.</span></span> <span data-ttu-id="5b6b6-158">Sales representa la cantidad de ventas para la subcategoría.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-158">Sales represents the sales amount for the subcategory.</span></span> <span data-ttu-id="5b6b6-159">El panel **Valores** muestra `[Sum(Sales)]` porque el gráfico muestra al agregado para cada producto.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-159">The **Values** pane displays `[Sum(Sales)]` because the chart displays the aggregate for each product.</span></span>  
  
3.  <span data-ttu-id="5b6b6-160">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-160">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="5b6b6-161">En la página **elegir un estilo** , en el panel estilos, seleccione un estilo.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-161">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="5b6b6-162">Un estilo especifica un estilo de fuente, un conjunto de colores y un estilo de borde.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-162">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="5b6b6-163">Al seleccionar un estilo, el panel Vista previa muestra un ejemplo del gráfico con ese estilo.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-163">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
5.  <span data-ttu-id="5b6b6-164">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="5b6b6-164">Click **Finish**.</span></span>  
  
     <span data-ttu-id="5b6b6-165">El gráfico se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-165">The chart is added to the design surface.</span></span>  
  
6.  <span data-ttu-id="5b6b6-166">Haga clic en el gráfico para mostrar las asas del gráfico.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-166">Click the chart to display the chart handles.</span></span> <span data-ttu-id="5b6b6-167">Arrastre la esquina inferior derecha del gráfico para aumentar su tamaño.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-167">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="5b6b6-168">Observe que la superficie de diseño del informe aumenta de tamaño para adaptarse al tamaño del gráfico.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-168">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
7.  <span data-ttu-id="5b6b6-169">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="5b6b6-170">El informe muestra el gráfico circular con ocho segmentos, uno para cada producto.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-170">The report displays the pie chart with eight slices, one for each product.</span></span> <span data-ttu-id="5b6b6-171">El tamaño de cada segmento representa las ventas de ese producto.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-171">The size of each slice represents the sales for that product.</span></span> <span data-ttu-id="5b6b6-172">Tres de los sectores son bastante finos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-172">Three of the slices are quite thin.</span></span>  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a><span data-ttu-id="5b6b6-173">3. Mostrar porcentajes en cada sector</span><span class="sxs-lookup"><span data-stu-id="5b6b6-173">3. Display Percentages in Each Slice</span></span>  
 <span data-ttu-id="5b6b6-174">En cada sector del gráfico circular, puede mostrar un porcentaje de este sector respecto al círculo entero.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-174">On each slice of the pie, you can display a percentage for this slice compared to the whole pie.</span></span>  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a><span data-ttu-id="5b6b6-175">Para mostrar porcentajes en cada sector del gráfico circular</span><span class="sxs-lookup"><span data-stu-id="5b6b6-175">To display percentages in each slice of the pie chart</span></span>  
  
1.  <span data-ttu-id="5b6b6-176">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="5b6b6-177">Haga clic con el botón derecho en el gráfico circular y haga clic en **Mostrar etiquetas de datos**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-177">Right-click the pie chart and click **Show Data Labels**.</span></span> <span data-ttu-id="5b6b6-178">Las etiquetas de datos aparecen en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-178">The data labels appear on the chart.</span></span>  
  
3.  <span data-ttu-id="5b6b6-179">Haga clic con el botón secundario en una etiqueta y, a continuación, en propiedades de la etiqueta de la **serie**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-179">Right-click a label, and then click **Series Label Properties**.</span></span>  
  
4.  <span data-ttu-id="5b6b6-180">En datos de etiqueta, en el cuadro desplegable, seleccione **#PERCENT**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-180">In Label data, from the drop-down box, select **#PERCENT**.</span></span>  
  
     <span data-ttu-id="5b6b6-181">Para mostrar los valores como porcentajes, la propiedad UseValueAsLabel debe ser falsa.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-181">To display values as percentages, the UseValueAsLabel property must be false.</span></span> <span data-ttu-id="5b6b6-182">Si se le pide que establezca este valor en el cuadro de diálogo **Confirmar acción** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-182">If you are prompted to set this value in the **Confirm Action** dialog, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="5b6b6-183">Opta Para especificar el número de posiciones decimales que muestra la etiqueta, escriba, `#PERCENT{Pn}` donde *n* es el número de posiciones decimales que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-183">(Optional) To specify how many decimal places the label shows, type `#PERCENT{Pn}` where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="5b6b6-184">Por ejemplo, para no mostrar ninguna posición decimal, escriba `#PERCENT{P0}` .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-184">For example, to display no decimal places, type `#PERCENT{P0}`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b6b6-185">La opción**Formato de número** del cuadro de diálogo **Propiedades de la etiqueta de la serie** no tiene ningún efecto al dar formato a los porcentajes.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-185">**Number Format** in the **Series Label Properties** dialog box has no effect when you format percentages.</span></span> <span data-ttu-id="5b6b6-186">Esto aplica formato de porcentaje a las etiquetas, pero no calcula el porcentaje del gráfico circular que cada sector representa.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-186">This formats the labels as percentages, but does not calculate the percentage of the pie that each slice represents.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="5b6b6-187">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-187">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="5b6b6-188">El informe muestra el porcentaje de la totalidad para cada sector del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-188">The report displays the percentage of the whole for each pie slice.</span></span>  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a><span data-ttu-id="5b6b6-189">4. combinar sectores pequeños en un solo sector</span><span class="sxs-lookup"><span data-stu-id="5b6b6-189">4. Combine Small Slices into One Slice</span></span>  
 <span data-ttu-id="5b6b6-190">Tres de los sectores del gráfico son bastante pequeños.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-190">Three of the slices in the pie are quite small.</span></span> <span data-ttu-id="5b6b6-191">Puede unir varios sectores pequeños en un sector mayor que represente a todos ellos.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-191">You can combine multiple small slices into one larger slice that represents all of them.</span></span>  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a><span data-ttu-id="5b6b6-192">Para unir los sectores del gráfico circular menores del 5 por ciento en un solo sector</span><span class="sxs-lookup"><span data-stu-id="5b6b6-192">To combine any slices on the pie chart smaller than 5 percent into one slice</span></span>  
  
1.  <span data-ttu-id="5b6b6-193">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-193">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="5b6b6-194">En la pestaña **Ver** , en el grupo **Mostrar u ocultar** , seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-194">On the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5b6b6-195">En la superficie de diseño, haga clic en cualquier sector del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-195">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="5b6b6-196">Las propiedades de la serie se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-196">The properties for the series are displayed in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="5b6b6-197">En la sección **General** , expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-197">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="5b6b6-198">Establezca la propiedad **CollectedStyle** en **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-198">Set the **CollectedStyle** property to **SingleSlice**.</span></span>  
  
6.  <span data-ttu-id="5b6b6-199">Compruebe que la propiedad **CollectedThreshold** esté establecida en 5.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-199">Verify that the **CollectedThreshold** property is set to 5.</span></span>  
  
7.  <span data-ttu-id="5b6b6-200">Compruebe que la propiedad **CollectedThresholdUsePercent** esté establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-200">Verify that the **CollectedThresholdUsePercent** property is set to **True**.</span></span>  
  
8.  <span data-ttu-id="5b6b6-201">En la cinta de opciones, en la pestaña **Inicio** , haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-201">On the Ribbon, on the **Home** tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="5b6b6-202">En la leyenda, ahora existe la categoría "Other".</span><span class="sxs-lookup"><span data-stu-id="5b6b6-202">In the legend, the category "Other" now exists.</span></span> <span data-ttu-id="5b6b6-203">El nuevo sector del gráfico circular combina todos los sectores que estaban por debajo del 5% en un sector que es el 6% de todo el gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-203">The new pie slice combines all the slices that were under 5% into one slice that is 6% of the whole pie.</span></span>  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a><span data-ttu-id="5b6b6-204">5. personalizar el efecto de dibujo</span><span class="sxs-lookup"><span data-stu-id="5b6b6-204">5. Customize the Drawing Effect</span></span>  
 <span data-ttu-id="5b6b6-205">En el Asistente para gráficos, el estilo predeterminado para un gráfico circular es Océano, que tiene un efecto de dibujo Cóncavo.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-205">In the Chart Wizard, the default style for a pie chart is Ocean, which features a Concave drawing effect.</span></span> <span data-ttu-id="5b6b6-206">Puede cambiarlo después de ejecutar el asistente.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-206">You can change that after you run the wizard.</span></span>  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a><span data-ttu-id="5b6b6-207">Para agregar un efecto de dibujo al gráfico circular</span><span class="sxs-lookup"><span data-stu-id="5b6b6-207">To add a drawing effect to the pie chart</span></span>  
  
1.  <span data-ttu-id="5b6b6-208">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="5b6b6-209">Si el panel Propiedades todavía no está abierto, en la pestaña **Ver** , seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-209">If the Properties pane is not already opened, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5b6b6-210">Haga doble clic en el propio gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-210">Double-click the pie chart itself.</span></span> <span data-ttu-id="5b6b6-211">Las propiedades de la serie para el gráfico circular se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-211">The series properties for the pie chart are shown in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="5b6b6-212">En el panel de propiedades, expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="5b6b6-212">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="5b6b6-213">Establezca **PieDrawingStyle** en **SoftEdge**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-213">Set the **PieDrawingStyle** to **SoftEdge**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b6b6-214">Los efectos de dibujo y los efectos tridimensionales son opciones exclusivas.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-214">Drawing effects and three-dimensional effects are exclusive options.</span></span> <span data-ttu-id="5b6b6-215">Si un gráfico tiene aplicados efectos tridimensionales, **PieDrawingStyle** no está disponible en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-215">If a chart has three-dimensional effects applied, **PieDrawingStyle** is not available on the Properties pane.</span></span>  
  
6.  <span data-ttu-id="5b6b6-216">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-216">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="5b6b6-217">La siguiente ilustración muestra el gráfico circular con efecto de borde suave.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-217">The following illustration shows the pie chart with the soft edge effect.</span></span>  
  
 <span data-ttu-id="5b6b6-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span><span class="sxs-lookup"><span data-stu-id="5b6b6-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="5b6b6-219">6. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="5b6b6-219">6. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="5b6b6-220">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="5b6b6-220">To add a report title</span></span>  
  
1.  <span data-ttu-id="5b6b6-221">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-221">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="5b6b6-222">Escriba **Ventas de cámaras y cámaras de vídeo**, pulse ENTRAR y, después, escriba **Como porcentaje de ventas totales**, de modo que tenga este aspecto:</span><span class="sxs-lookup"><span data-stu-id="5b6b6-222">Type **Camera and Camcorder Sales**, press ENTER, and then type **As a Percentage of Total Sales**, so it looks like this:</span></span>  
  
     <span data-ttu-id="5b6b6-223">**Ventas de cámaras y cámaras de vídeo**</span><span class="sxs-lookup"><span data-stu-id="5b6b6-223">**Camera and Camcorder Sales**</span></span>  
  
     <span data-ttu-id="5b6b6-224">**Como porcentaje de ventas totales**</span><span class="sxs-lookup"><span data-stu-id="5b6b6-224">**As a Percentage of Total Sales**</span></span>  
  
3.  <span data-ttu-id="5b6b6-225">Seleccione **ventas de cámara y**videocámara y haga clic en el botón **negrita** de la sección **fuente** de la pestaña **Inicio** de la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-225">Select **Camera and Camcorder Sales**, and click the **Bold** button from the **Font** section of the **Home** tab of the ribbon.</span></span>  
  
4.  <span data-ttu-id="5b6b6-226">Seleccione **como porcentaje de ventas totales**y, en la sección **fuente** de la pestaña **Inicio** , establezca el tamaño de fuente en **10**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-226">Select **As a Percentage of Total Sales**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="5b6b6-227">(Opcional) Es posible que necesite hacer más alto el cuadro de texto Título para que quepan las dos líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-227">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="5b6b6-228">Este título aparecerá en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-228">This title will appear at the top of the report.</span></span> <span data-ttu-id="5b6b6-229">Cuando no hay ningún encabezado de página definido, los elementos de la parte superior del cuerpo del informe son equivalentes a un encabezado de informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-229">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="5b6b6-230">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-230">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="5b6b6-231">7. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="5b6b6-231">7. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="5b6b6-232">Para guardar el informe</span><span class="sxs-lookup"><span data-stu-id="5b6b6-232">To save the report</span></span>  
  
1.  <span data-ttu-id="5b6b6-233">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-233">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="5b6b6-234">En el botón Generador de informes , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-234">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="5b6b6-235">En **Nombre**, escriba **Gráfico circular de ventas**.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-235">In **Name**, type **Sales Pie Chart**.</span></span>  
  
4.  <span data-ttu-id="5b6b6-236">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="5b6b6-236">Click **Save**.</span></span>  
  
 <span data-ttu-id="5b6b6-237">El informe se guardará en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-237">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5b6b6-238">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5b6b6-238">Next Steps</span></span>  
 <span data-ttu-id="5b6b6-239">Ha completado correctamente el tutorial Agregar un gráfico circular al informe.</span><span class="sxs-lookup"><span data-stu-id="5b6b6-239">You have successfully completed the Adding a Pie Chart to Your Report tutorial.</span></span> <span data-ttu-id="5b6b6-240">Para obtener más información sobre los gráficos, vea [Gráficos &#40;Generador de informes y SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) y [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5b6b6-240">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6b6-241">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b6b6-241">See Also</span></span>  
 <span data-ttu-id="5b6b6-242">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="5b6b6-242">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="5b6b6-243">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5b6b6-243">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
