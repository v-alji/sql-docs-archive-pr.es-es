---
title: 'Tutorial: Agregar un gráfico de columnas a un informe (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ef3b3f2872c2f8181296bb05337ca18975ac2f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748617"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a><span data-ttu-id="1cb4d-102">Tutorial: Agregar un gráfico de columnas a un informe (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="1cb4d-102">Tutorial: Add a Column Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="1cb4d-103">Un gráfico de columnas muestra una serie como un conjunto de barras verticales agrupadas por categorías.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-103">A column chart displays a series as a set of vertical bars that are grouped by category.</span></span> <span data-ttu-id="1cb4d-104">Un gráfico de columnas puede ser útil para:</span><span class="sxs-lookup"><span data-stu-id="1cb4d-104">A column chart can be useful to:</span></span>  
  
-   <span data-ttu-id="1cb4d-105">Mostrar los cambios realizados en los datos a lo largo de un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-105">Show data changes over a period of time.</span></span>  
  
-   <span data-ttu-id="1cb4d-106">Comparar el valor relativo de varias series.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-106">Compare the relative value of multiple series.</span></span>  
  
-   <span data-ttu-id="1cb4d-107">Mostrar una media móvil para mostrar tendencias.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-107">Display a moving average to show trends.</span></span>  
  
 <span data-ttu-id="1cb4d-108">En la ilustración siguiente se muestra el gráfico de columnas que creará, con una media móvil.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-108">The following illustration shows the column chart you will create, with a moving average.</span></span>  
  
 <span data-ttu-id="1cb4d-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span><span class="sxs-lookup"><span data-stu-id="1cb4d-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="1cb4d-110">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="1cb4d-110">What You Will Learn</span></span>  
 <span data-ttu-id="1cb4d-111">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="1cb4d-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="1cb4d-112">Crear un gráfico a partir del Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="1cb4d-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="1cb4d-113">Elegir el tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="1cb4d-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="1cb4d-114">Dar formato al eje horizontal y etiquetarlo</span><span class="sxs-lookup"><span data-stu-id="1cb4d-114">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
4.  [<span data-ttu-id="1cb4d-115">Mover la leyenda</span><span class="sxs-lookup"><span data-stu-id="1cb4d-115">Move the Legend</span></span>](#Legend)  
  
5.  [<span data-ttu-id="1cb4d-116">Titular el gráfico</span><span class="sxs-lookup"><span data-stu-id="1cb4d-116">Title the Chart</span></span>](#ChartTitle)  
  
6.  [<span data-ttu-id="1cb4d-117">Dar formato al eje vertical y etiquetarlo</span><span class="sxs-lookup"><span data-stu-id="1cb4d-117">Format and Label the Vertical Axis</span></span>](#Vertical)  
  
7.  [<span data-ttu-id="1cb4d-118">Agregar una media móvil</span><span class="sxs-lookup"><span data-stu-id="1cb4d-118">Add a Moving Average</span></span>](#Average)  
  
8.  [<span data-ttu-id="1cb4d-119">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="1cb4d-119">Add a Report Title</span></span>](#Title)  
  
9. [<span data-ttu-id="1cb4d-120">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="1cb4d-120">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="1cb4d-121">En este tutorial, los pasos del asistente se encuentran reunidos en un único procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-121">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="1cb4d-122">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, elegir un origen de datos y crear un conjunto de datos, consulte el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4d-122">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="1cb4d-123">Tiempo estimado para completar este tutorial: 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-123">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cb4d-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cb4d-124">Requirements</span></span>  
 <span data-ttu-id="1cb4d-125">Para obtener información sobre los requisitos, vea [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4d-125">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="1cb4d-126">1. crear un informe de gráfico a partir del Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="1cb4d-126">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="1cb4d-127">En el cuadro de diálogo **Introducción** , use el Asistente para gráficos con el fin de crear un conjunto de datos incrustado, elegir un origen de datos compartido y crear un gráfico de columnas.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-127">From the **Getting Started** dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a column chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cb4d-128">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-128">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="1cb4d-129">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-129">This makes the query quite long.</span></span> <span data-ttu-id="1cb4d-130">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-130">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="1cb4d-131">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-131">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="1cb4d-132">Para crear un informe de gráfico</span><span class="sxs-lookup"><span data-stu-id="1cb4d-132">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="1cb4d-133">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-133">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="1cb4d-134">Aparece el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="1cb4d-134">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cb4d-135">Si el cuadro de diálogo **Introducción** no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-135">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="1cb4d-136">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="1cb4d-136">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="1cb4d-137">En el panel derecho, haga clic en **Asistente para gráficos**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-137">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="1cb4d-138">En la **Página elegir un conjunto**de los, haga clic en **crear un conjunto**de los y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-138">On the **Choose a dataset page**, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1cb4d-139">En la página **Elegir una conexión a un origen de datos** , seleccione un origen de datos existente o vaya al servidor de informes y seleccione un origen de datos, y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="1cb4d-140">Puede que necesite escribir un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-140">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cb4d-141">El origen de datos que elija no importa, con tal de que tenga los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-141">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="1cb4d-142">No está recibiendo datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-142">You will not be getting data from the data source.</span></span> <span data-ttu-id="1cb4d-143">Para obtener más información, consulte [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4d-143">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="1cb4d-144">En la página **Diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-144">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="1cb4d-145">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="1cb4d-145">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="1cb4d-146">(Opcional) Haga clic en el botón Ejecutar (**!**) para ver los datos en los que se basará su gráfico.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="1cb4d-147">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-147">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="1cb4d-148">2. elegir el tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="1cb4d-148">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="1cb4d-149">Podrá elegir entre varios tipos de gráfico predefinidos.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-149">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="1cb4d-150">Para agregar un gráfico de columnas</span><span class="sxs-lookup"><span data-stu-id="1cb4d-150">To add a column chart</span></span>  
  
1.  <span data-ttu-id="1cb4d-151">En la página **Elegir un tipo de gráfico** , el gráfico de columnas es el tipo de gráfico predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-151">On the **Choose a chart type** page, the column chart is the default chart type.</span></span> <span data-ttu-id="1cb4d-152">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-152">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="1cb4d-153">En la página **Organizar campos del gráfico** , arrastre el campo SalesDate hasta **Categorías**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-153">On the **Arrange chart fields** page, drag the SalesDate field to **Categories**.</span></span> <span data-ttu-id="1cb4d-154">Categorías se muestra en el eje horizontal.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-154">Categories display on the horizontal axis.</span></span>  
  
3.  <span data-ttu-id="1cb4d-155">Arrastre el campo Sales hasta **Valores**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-155">Drag the Sales field to **Values**.</span></span> <span data-ttu-id="1cb4d-156">El cuadro **Valores** muestra Sum(Sales), porque la suma del valor total de ventas se agrega para cada fecha.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-156">The **Values** box displays Sum(Sales) because the sum of the sales total value is aggregated for each date.</span></span> <span data-ttu-id="1cb4d-157">Valores se muestra en el eje vertical.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-157">Values display on the vertical axis.</span></span>  
  
4.  <span data-ttu-id="1cb4d-158">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-158">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="1cb4d-159">En la página **elegir un estilo** , en el cuadro estilos, seleccione un estilo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-159">On the **Choose a Style** page, in the Styles box, select a style.</span></span>  
  
     <span data-ttu-id="1cb4d-160">Un estilo especifica un estilo de fuente, un conjunto de colores y un estilo de borde.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-160">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="1cb4d-161">Al seleccionar un estilo, el panel Vista previa muestra un ejemplo del gráfico con ese estilo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-161">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
6.  <span data-ttu-id="1cb4d-162">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="1cb4d-162">Click **Finish**.</span></span>  
  
     <span data-ttu-id="1cb4d-163">El gráfico se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-163">The chart is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="1cb4d-164">Haga clic en el gráfico para mostrar las asas del gráfico.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-164">Click the chart to display the chart handles.</span></span> <span data-ttu-id="1cb4d-165">Arrastre la esquina inferior derecha del gráfico para aumentar su tamaño.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-165">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="1cb4d-166">Observe que la superficie de diseño del informe aumenta de tamaño para adaptarse al tamaño del gráfico.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-166">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
8.  <span data-ttu-id="1cb4d-167">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-167">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="1cb4d-168">3. dar formato al eje horizontal y etiquetarlo</span><span class="sxs-lookup"><span data-stu-id="1cb4d-168">3. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="1cb4d-169">De forma predeterminada, el eje horizontal muestra los valores en un formato general que se escala automáticamente para ajustarse al tamaño del gráfico.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-169">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a><span data-ttu-id="1cb4d-170">Para dar formato a una fecha en el eje horizontal</span><span class="sxs-lookup"><span data-stu-id="1cb4d-170">To format a date on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="1cb4d-171">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-171">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-172">Haga clic con el botón secundario en el eje horizontal y, a continuación, haga clic en **propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-172">Right-click the horizontal axis, and then click **Horizontal Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="1cb4d-173">Haga clic en **Número**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-173">Click **Number**.</span></span>  
  
4.  <span data-ttu-id="1cb4d-174">En **categoría**, seleccione **fecha**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-174">In **Category**, select **Date**.</span></span>  
  
5.  <span data-ttu-id="1cb4d-175">En el cuadro **Tipo** , seleccione **31 Ene 2000**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-175">In the **Type** box, select **31 Jan 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="1cb4d-176">En la pestaña Inicio, haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-176">On the Home tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1cb4d-177">La fecha se mostrará en el formato de fecha que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-177">The date displays in the date format that you selected.</span></span> <span data-ttu-id="1cb4d-178">Tenga en cuenta que el gráfico no etiqueta todas las categorías del eje horizontal.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-178">Notice that the chart does not label every category on the horizontal axis.</span></span> <span data-ttu-id="1cb4d-179">De forma predeterminada, solo se incluyen las etiquetas que caben a lo largo del eje.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-179">By default, only labels that fit next to the axis are included.</span></span>  
  
 <span data-ttu-id="1cb4d-180">Puede personalizar la presentación de las etiquetas girándolas y especificando el intervalo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-180">You can customize the label display by rotating the labels and specifying the interval.</span></span>  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a><span data-ttu-id="1cb4d-181">Para girar las etiquetas del eje y cambiar el intervalo de presentación a lo largo del eje horizontal</span><span class="sxs-lookup"><span data-stu-id="1cb4d-181">To rotate the axis labels and change the display interval along the horizontal axis</span></span>  
  
1.  <span data-ttu-id="1cb4d-182">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-182">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-183">Haga clic con el botón secundario en el título del eje horizontal y, a continuación, haga clic en **Mostrar título del eje** para quitar el título.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-183">Right-click the horizontal axis title, and then click **Show Axis Title** to remove the title.</span></span> <span data-ttu-id="1cb4d-184">Dado que el eje horizontal muestra las fechas, no es necesario el título.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-184">Because the horizontal axis displays dates, the title is not needed.</span></span>  
  
3.  <span data-ttu-id="1cb4d-185">Haga clic con el botón secundario en el eje horizontal y, a continuación, haga clic en **propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-185">Right-click the horizontal axis and then click **Horizontal Axis Properties**.</span></span>  
  
4.  <span data-ttu-id="1cb4d-186">En la página **Opciones del eje** , en **rango e**intervalo del eje, escriba **3** para **intervalo**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-186">In the **Axis Options** page under **Axis range and interval**, type **3** for **Interval**.</span></span> <span data-ttu-id="1cb4d-187">El gráfico mostrará una fecha de cada tres.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-187">The chart will display every third date.</span></span>  
  
5.  <span data-ttu-id="1cb4d-188">Haga clic en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-188">Click **Labels**.</span></span>  
  
6.  <span data-ttu-id="1cb4d-189">En **cambiar las opciones de ajuste automático de las etiquetas de eje**, seleccione **deshabilitar ajuste automático**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-189">In **Change axis label auto-fit options**, select **Disable auto-fit**.</span></span>  
  
7.  <span data-ttu-id="1cb4d-190">En **Ángulo de giro de etiqueta**, seleccione **-90**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-190">In **Label rotation angle**, select **-90**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="1cb4d-191">El texto de ejemplo del eje horizontal girará 90 grados.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-191">The sample text for the horizontal axis rotates by 90 degrees.</span></span>  
  
9. <span data-ttu-id="1cb4d-192">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-192">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1cb4d-193">En el gráfico, las etiquetas se giran y se muestra la etiqueta de cada tercera fecha.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-193">On the chart, the labels are rotated and the label for every third date is shown.</span></span>  
  
##  <a name="4-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="1cb4d-194">4. Mueva la leyenda</span><span class="sxs-lookup"><span data-stu-id="1cb4d-194">4. Move the Legend</span></span>  
 <span data-ttu-id="1cb4d-195">La leyenda se crea automáticamente a partir de los datos de las categorías y las series.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-195">The legend is automatically created from category and series data.</span></span>  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a><span data-ttu-id="1cb4d-196">Para mover la leyenda debajo del área de gráfico de un gráfico de columnas</span><span class="sxs-lookup"><span data-stu-id="1cb4d-196">To move the legend below the chart area of a column chart</span></span>  
  
1.  <span data-ttu-id="1cb4d-197">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-197">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-198">Haga clic con el botón secundario en la leyenda del gráfico y, a continuación, haga clic en propiedades de la **leyenda**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-198">Right-click the legend on the chart, and then click **Legend Properties**.</span></span>  
  
3.  <span data-ttu-id="1cb4d-199">En **diseño y posición**, seleccione una posición diferente.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-199">For **Layout and Position**, select a different position.</span></span> <span data-ttu-id="1cb4d-200">Por ejemplo, sitúe la leyenda centrada en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-200">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="1cb4d-201">Cuando la leyenda se coloca en la parte superior o inferior de un gráfico, su diseño cambia de vertical a horizontal.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-201">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="1cb4d-202">Puede seleccionar un diseño diferente en la lista desplegable **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="1cb4d-202">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="1cb4d-203">(Opcional) Dado que solo hay una categoría en este tutorial, no es necesaria la leyenda.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-203">(Optional) Because there is only one category in this tutorial, the legend is not needed.</span></span> <span data-ttu-id="1cb4d-204">Para quitar la leyenda, haga clic con el botón secundario en la leyenda y, a continuación, haga clic en **eliminar leyenda**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-204">To remove the legend, right-click the legend and then click **Delete Legend**.</span></span>  
  
6.  <span data-ttu-id="1cb4d-205">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-205">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="1cb4d-206">5. título del gráfico</span><span class="sxs-lookup"><span data-stu-id="1cb4d-206">5. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a><span data-ttu-id="1cb4d-207">Para cambiar el título del gráfico encima del área de gráfico</span><span class="sxs-lookup"><span data-stu-id="1cb4d-207">To change the chart title above the chart area</span></span>  
  
1.  <span data-ttu-id="1cb4d-208">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-209">Seleccione las palabras **título del gráfico** en la parte superior del gráfico y, a continuación, escriba el siguiente texto: **total de pedidos de venta de tiendas**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-209">Select the words **Chart Title** at the top of the chart, and then type the following text: **Store Sales Order Totals**.</span></span>  
  
3.  <span data-ttu-id="1cb4d-210">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-210">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-format-and-label-the-vertical-axis"></a><a name="Vertical"></a><span data-ttu-id="1cb4d-211">6. dar formato al eje vertical y etiquetarlo</span><span class="sxs-lookup"><span data-stu-id="1cb4d-211">6. Format and Label the Vertical Axis</span></span>  
 <span data-ttu-id="1cb4d-212">De forma predeterminada, el eje vertical muestra los valores en un formato general que se escala automáticamente para ajustarse al tamaño del gráfico.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-212">By default, the vertical axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a><span data-ttu-id="1cb4d-213">Para dar formato de moneda a los números del eje vertical</span><span class="sxs-lookup"><span data-stu-id="1cb4d-213">To format as currency the numbers on the vertical axis</span></span>  
  
1.  <span data-ttu-id="1cb4d-214">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-214">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-215">Haga doble clic en las etiquetas del eje vertical a lo largo del lateral del gráfico para seleccionarlas.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-215">Double-click the labels on the vertical axis along the side of the chart to select them.</span></span>  
  
3.  <span data-ttu-id="1cb4d-216">En la cinta de opciones, en la pestaña **Inicio** , en el grupo **número** , haga clic en el botón **moneda** .</span><span class="sxs-lookup"><span data-stu-id="1cb4d-216">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="1cb4d-217">Las etiquetas del eje cambiarán para mostrar el formato de moneda.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-217">The axis labels change to show the currency format.</span></span>  
  
4.  <span data-ttu-id="1cb4d-218">En la cinta de opciones, en la pestaña **Inicio** , en el grupo **número** , haga clic dos veces en el botón **disminuir decimales** para mostrar el número redondeado al dólar más próximo.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-218">On the ribbon, on the **Home** tab, in the **Number** group, click the **Decrease Decimal** button two times, to show the number rounded to the nearest dollar.</span></span>  
  
5.  <span data-ttu-id="1cb4d-219">Haga clic con el botón secundario en el eje vertical y haga clic en **propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-219">Right-click the vertical axis and click **Vertical Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="1cb4d-220">Haga clic en **Número**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-220">Click **Number**.</span></span> <span data-ttu-id="1cb4d-221">Tenga en cuenta que **moneda** ya está seleccionado en el cuadro **categoría** y **posiciones decimales** ya es **0** (cero).</span><span class="sxs-lookup"><span data-stu-id="1cb4d-221">Note that **Currency** is already selected in the **Category** box, and **Decimal places** is already **0** (zero).</span></span>  
  
7.  <span data-ttu-id="1cb4d-222">En el cuadro **Mostrar valores en** , haga clic en **miles**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-222">In the **Show Values in** box, click **Thousands**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="1cb4d-223">Haga clic con el botón secundario en el título del eje vertical a lo largo del lateral del gráfico y haga clic en **propiedades del título del eje**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-223">Right-click the vertical axis title along the side of the chart and click **Axis Title Properties**.</span></span>  
  
10. <span data-ttu-id="1cb4d-224">Reemplace el texto del campo **texto del título** con el siguiente texto: **total de ventas (en miles)**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-224">Replace the text in the **Title text** field with the following text: **Sales Total (in Thousands)**.</span></span> <span data-ttu-id="1cb4d-225">También puede especificar una gran variedad de opciones de formato para el título.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-225">You can also specify a variety of options related to how the title is formatted.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="1cb4d-226">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-add-a-moving-average"></a><a name="Average"></a><span data-ttu-id="1cb4d-227">7. agregar una media móvil</span><span class="sxs-lookup"><span data-stu-id="1cb4d-227">7. Add a Moving Average</span></span>  
  
#### <a name="to-add-a-moving-average"></a><span data-ttu-id="1cb4d-228">Para agregar una media móvil</span><span class="sxs-lookup"><span data-stu-id="1cb4d-228">To add a moving average</span></span>  
  
1.  <span data-ttu-id="1cb4d-229">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-229">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-230">Haga doble clic en el gráfico para mostrar el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="1cb4d-230">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="1cb4d-231">Haga clic con el botón secundario en el campo **[SUM (sales)]** que se encuentra en el área **valores** y, a continuación, haga clic en **Agregar serie calculada**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-231">Right-click the **[Sum(Sales)]** field that is in the **Values** area, and then click **Add Calculated Series**.</span></span>  
  
4.  <span data-ttu-id="1cb4d-232">En **Fórmula**, compruebe que esté seleccionada la opción **Media móvil** .</span><span class="sxs-lookup"><span data-stu-id="1cb4d-232">In **Formula**, verify that **Moving average** is selected.</span></span>  
  
5.  <span data-ttu-id="1cb4d-233">En **Establecer parámetros de fórmula**, para **Período**, seleccione **4**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-233">In **Set Formula Parameters**, for **Period**, select **4**.</span></span>  
  
6.  <span data-ttu-id="1cb4d-234">Haga clic en **borde**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-234">Click **Border**.</span></span>  
  
7.  <span data-ttu-id="1cb4d-235">En **ancho de línea**, seleccione **3 PT**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-235">In **Line width**, select **3pt**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="1cb4d-236">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-236">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1cb4d-237">El gráfico muestra una línea que muestra la media móvil del total de ventas por fecha, promediado cada cuatro fechas.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-237">The chart displays a line that shows the moving average for total sales by date, averaged over every four dates.</span></span>  
  
##  <a name="8-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="1cb4d-238">8. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="1cb4d-238">8. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="1cb4d-239">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="1cb4d-239">To add a report title</span></span>  
  
1.  <span data-ttu-id="1cb4d-240">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-240">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-241">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-241">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="1cb4d-242">Escriba **gráfico de ventas**, presione entrar y, a continuación, escriba **enero a diciembre de 2009**, de modo que tenga este aspecto:</span><span class="sxs-lookup"><span data-stu-id="1cb4d-242">Type **Sales Chart**, press ENTER, and then type **January to December 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="1cb4d-243">**Gráfico de ventas**</span><span class="sxs-lookup"><span data-stu-id="1cb4d-243">**Sales Chart**</span></span>  
  
     <span data-ttu-id="1cb4d-244">**Enero a diciembre de 2009**</span><span class="sxs-lookup"><span data-stu-id="1cb4d-244">**January to December 2009**</span></span>  
  
4.  <span data-ttu-id="1cb4d-245">Seleccione **gráfico de ventas**y haga clic en el botón **negrita** en la sección **fuente** de la pestaña **Inicio** de la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-245">Select **Sales Chart**, and click the **Bold** button in the **Font** section on the **Home** tab of the ribbon.</span></span>  
  
5.  <span data-ttu-id="1cb4d-246">Seleccione **enero a diciembre 2009**y, en la sección **fuente** de la pestaña **Inicio** , establezca el tamaño de fuente en **10**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-246">Select **January to December 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
6.  <span data-ttu-id="1cb4d-247">Opta Es posible que tenga que hacer que el cuadro de texto del **título** sea más alto para dar cabida a las dos líneas de texto al hacer clic en el centro del borde inferior.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-247">(Optional) You may need to make the **Title** text box taller to accommodate the two lines of text by pulling down on the double-headed arrows when you click in the middle of the bottom edge.</span></span>  
  
     <span data-ttu-id="1cb4d-248">Este título aparecerá en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-248">This title will appear at the top of the report.</span></span> <span data-ttu-id="1cb4d-249">Cuando no hay ningún encabezado de página definido, los elementos de la parte superior del cuerpo del informe son equivalentes a un encabezado de informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-249">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
7.  <span data-ttu-id="1cb4d-250">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-250">Click **Run** to preview the report.</span></span>  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="1cb4d-251">9. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="1cb4d-251">9. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="1cb4d-252">Para guardar el informe</span><span class="sxs-lookup"><span data-stu-id="1cb4d-252">To save the report</span></span>  
  
1.  <span data-ttu-id="1cb4d-253">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-253">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1cb4d-254">En el botón Generador de informes , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-254">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="1cb4d-255">En **Nombre**, escriba **Gráfico de columnas de pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-255">In **Name**, type **Sales Order Column Chart**.</span></span>  
  
4.  <span data-ttu-id="1cb4d-256">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="1cb4d-256">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1cb4d-257">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1cb4d-257">Next Steps</span></span>  
 <span data-ttu-id="1cb4d-258">Ha completado correctamente el tutorial Agregar un gráfico de columnas al informe.</span><span class="sxs-lookup"><span data-stu-id="1cb4d-258">You have successfully completed the Adding a Column Chart to Your Report tutorial.</span></span> <span data-ttu-id="1cb4d-259">Para obtener más información sobre los gráficos, vea [Gráficos &#40;Generador de informes y SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) y [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4d-259">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb4d-260">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1cb4d-260">See Also</span></span>  
 <span data-ttu-id="1cb4d-261">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="1cb4d-261">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="1cb4d-262">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1cb4d-262">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
