---
title: 'Tutorial: Agregar un gráfico de barras a un informe (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6956ebd6-0217-4087-a4fa-5cc1c3804691
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01708ca548c40118daa03fac34d8a323d628b012
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671356"
---
# <a name="tutorial-add-a-bar-chart-to-your-report-report-builder"></a><span data-ttu-id="0ab9a-102">Tutorial: Agregar un gráfico de barras a un informe (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="0ab9a-102">Tutorial: Add a Bar Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="0ab9a-103">Un gráfico de barras muestra los datos de categoría horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-103">A bar chart displays category data horizontally.</span></span> <span data-ttu-id="0ab9a-104">Esto puede ayudar a:</span><span class="sxs-lookup"><span data-stu-id="0ab9a-104">This can help to:</span></span>  
  
-   <span data-ttu-id="0ab9a-105">Mejorar la legibilidad de los nombres de categoría largos.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-105">Improve readability of long category names.</span></span>  
  
-   <span data-ttu-id="0ab9a-106">Mejorar la comprensión de las fechas u horas representadas mediante valores.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-106">Improve understandability of times plotted as values.</span></span>  
  
-   <span data-ttu-id="0ab9a-107">Comparar el valor relativo de varias series.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-107">Compare the relative value of multiple series.</span></span>  
  
 <span data-ttu-id="0ab9a-108">La siguiente ilustración muestra el gráfico de barras que creará en orden alfabético, con ventas para 2008 y 2009, para los cinco vendedores superiores.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-108">The following illustration shows the bar chart that you will create, with sales for 2008 and 2009 for the top five salespeople, in alphabetical order.</span></span>  
  
 <span data-ttu-id="0ab9a-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span><span class="sxs-lookup"><span data-stu-id="0ab9a-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="0ab9a-110">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="0ab9a-110">What You Will Learn</span></span>  
 <span data-ttu-id="0ab9a-111">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0ab9a-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="0ab9a-112">Crear un gráfico a partir del Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="0ab9a-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="0ab9a-113">Elegir el tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="0ab9a-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="0ab9a-114">Mostrar todos los valores de categoría en el eje vertical</span><span class="sxs-lookup"><span data-stu-id="0ab9a-114">Display all Category Values on the Vertical Axis</span></span>](#AllValues)  
  
4.  [<span data-ttu-id="0ab9a-115">Modificar la presentación de nombres en el eje vertical</span><span class="sxs-lookup"><span data-stu-id="0ab9a-115">Modify the Display of Names on the Vertical Axis</span></span>](#Sort)  
  
5.  [<span data-ttu-id="0ab9a-116">Mover la leyenda</span><span class="sxs-lookup"><span data-stu-id="0ab9a-116">Move the Legend</span></span>](#Legend)  
  
6.  [<span data-ttu-id="0ab9a-117">Mover el título de gráfico</span><span class="sxs-lookup"><span data-stu-id="0ab9a-117">Move the Chart Title</span></span>](#ChartTitle)  
  
7.  [<span data-ttu-id="0ab9a-118">Dar formato al eje horizontal y etiquetarlo</span><span class="sxs-lookup"><span data-stu-id="0ab9a-118">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
8.  [<span data-ttu-id="0ab9a-119">Agregar un filtro para mostrar cinco valores superiores</span><span class="sxs-lookup"><span data-stu-id="0ab9a-119">Add a Filter to Display the Top Five Values</span></span>](#Filter)  
  
9. [<span data-ttu-id="0ab9a-120">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="0ab9a-120">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="0ab9a-121">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="0ab9a-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="0ab9a-122">En este tutorial, los pasos del asistente se encuentran reunidos en un único procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-122">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="0ab9a-123">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, crear un conjunto de datos y elegir un origen de datos, vea el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-123">For step-by-step instructions about how to browse to a report server, create a dataset, and choose a data source, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="0ab9a-124">Tiempo estimado para completar este tutorial: 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-124">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ab9a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ab9a-125">Requirements</span></span>  
 <span data-ttu-id="0ab9a-126">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="0ab9a-127">1. crear un informe de gráfico a partir del Asistente para gráficos</span><span class="sxs-lookup"><span data-stu-id="0ab9a-127">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="0ab9a-128">En el cuadro de diálogo **Introducción** , cree un conjunto de datos incrustado, elija un origen de datos compartido y cree un gráfico de barras con el Asistente para gráficos.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-128">From the **Getting Started** dialog box, create an embedded dataset, choose a shared data source, and create a bar chart by using the Chart Wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ab9a-129">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-129">In this tutorial, the query contains the data values so that it does not need an external data source.</span></span> <span data-ttu-id="0ab9a-130">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-130">This makes the query quite long.</span></span> <span data-ttu-id="0ab9a-131">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="0ab9a-132">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="0ab9a-133">Para crear un informe de gráfico</span><span class="sxs-lookup"><span data-stu-id="0ab9a-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="0ab9a-134">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="0ab9a-135">Aparece el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-135">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0ab9a-136">Si no aparece el cuadro de diálogo **Introducción** , haga clic en el botón generador de informes y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-136">If the **Getting Started** dialog box does not appear, click the Report Builder button, and then click **New**.</span></span>  
  
2.  <span data-ttu-id="0ab9a-137">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="0ab9a-138">En el panel derecho, haga clic en **Asistente para gráficos**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="0ab9a-139">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="0ab9a-140">En la página **Elegir una conexión a un origen de datos** , seleccione un origen de datos existente o vaya al servidor de informes y seleccione un origen de datos, y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="0ab9a-141">Puede que necesite escribir un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0ab9a-142">El origen de datos que elija no importa, con tal de que tenga los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="0ab9a-143">No está recibiendo datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="0ab9a-144">Para obtener más información, consulte [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="0ab9a-145">En la página **Diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-145">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="0ab9a-146">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="0ab9a-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Luis' as FirstName, 'Alverca' as LastName, CAST(170000.00 AS money) AS SalesYear2009, CAST(150000. AS money) AS SalesYear2008  
    UNION SELECT 'Jeffrey' as FirstName, 'Zeng' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(190000. AS money) AS SalesYear2008  
    UNION SELECT 'Houman' as FirstName, 'Pournasseh' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Robin' as FirstName, 'Wood' as LastName, CAST(75000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'Daniela' as FirstName, 'Guaita' as LastName,  CAST(170000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'John' as FirstName, 'Yokim' as LastName, CAST(160000. AS money) AS SalesYear2009, CAST(195000. AS money) AS SalesYear2008  
    UNION SELECT 'Delphine' as FirstName, 'Ribaute' as LastName, CAST(180000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Robert' as FirstName, 'Hernady' as LastName, CAST(140000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Tanja' as FirstName, 'Plate' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(160000. AS money) AS SalesYear2008  
    UNION SELECT 'David' as FirstName, 'Bradley' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Michal' as FirstName, 'Jaworski' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(220000. AS money) AS SalesYear2008  
    UNION SELECT 'Chris' as FirstName, 'Ashton' as LastName, CAST(195000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Pongsiri' as FirstName, 'Hirunyanitiwatna' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(215000. AS money) AS SalesYear2008  
    UNION SELECT 'Brian' as FirstName, 'Burke' as LastName, CAST(187000. AS money) AS SalesYear2009, CAST(207000. AS money) AS SalesYear2008  
    ```  
  
8.  <span data-ttu-id="0ab9a-147">(Opcional) Haga clic en el botón Ejecutar (**!**) para ver los datos en los que se basará su gráfico.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="0ab9a-148">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="0ab9a-149">2. elegir el tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="0ab9a-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="0ab9a-150">Podrá elegir entre varios tipos de gráfico predefinidos.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="0ab9a-151">Para agregar un gráfico de columnas</span><span class="sxs-lookup"><span data-stu-id="0ab9a-151">To add a column chart</span></span>  
  
1.  <span data-ttu-id="0ab9a-152">En la página **Elegir un tipo de gráfico** , el gráfico de columnas es el tipo de gráfico predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-152">On the **Choose a chart type** page, the column chart is the default chart type.</span></span>  
  
2.  <span data-ttu-id="0ab9a-153">Haga clic en **Barras**y después en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-153">Click **Bar**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="0ab9a-154">En la página **organizar campos del gráfico** hay cuatro campos en el panel **campos disponibles** : firstname, LastName, SalesYear2009 y SalesYear2008.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-154">On the **Arrange chart fields** page, there are four fields in the **Available fields** pane: FirstName, LastName, SalesYear2009, and SalesYear2008.</span></span>  
  
3.  <span data-ttu-id="0ab9a-155">Arrastre LastName hasta el panel Categorías.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-155">Drag LastName to the Categories pane.</span></span>  
  
4.  <span data-ttu-id="0ab9a-156">Arrastre SalesYear2009 hasta el panel Valores.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-156">Drag SalesYear2009 to the Values pane.</span></span> <span data-ttu-id="0ab9a-157">SalesYear2009 representa la cantidad de ventas de cada vendedor durante el año 2009.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-157">SalesYear2009 represents the sales amount for each salesperson for the year 2009.</span></span> <span data-ttu-id="0ab9a-158">El panel Valores muestra `[Sum(SalesYear2009)]` porque el gráfico muestra al agregado para cada producto.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-158">The Values pane displays `[Sum(SalesYear2009)]` because the chart displays the aggregate for each product.</span></span>  
  
5.  <span data-ttu-id="0ab9a-159">Arrastre SalesYear2008 hacia el panel Valores bajo SalesYear2009.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-159">Drag SalesYear2008 to the Values pane under SalesYear2009.</span></span> <span data-ttu-id="0ab9a-160">SalesYear2008 representa la cantidad de ventas de cada vendedor durante el año 2008.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-160">SalesYear2008 represents the sales amount for each salesperson for the year 2008.</span></span>  
  
6.  <span data-ttu-id="0ab9a-161">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-161">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="0ab9a-162">En la página **elegir un estilo** , en el panel estilos, seleccione un estilo.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-162">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="0ab9a-163">Un estilo especifica un estilo de fuente, un conjunto de colores y un estilo de borde.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-163">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="0ab9a-164">Al seleccionar un estilo, el panel Vista previa muestra un ejemplo del gráfico con ese estilo.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-164">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
8.  <span data-ttu-id="0ab9a-165">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="0ab9a-165">Click **Finish**.</span></span>  
  
     <span data-ttu-id="0ab9a-166">El gráfico se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-166">The chart is added to the design surface.</span></span>  
  
9. <span data-ttu-id="0ab9a-167">Haga clic en el gráfico para mostrar las asas del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-167">Click the chart to display the chart handles.</span></span> <span data-ttu-id="0ab9a-168">Arrastre la esquina inferior derecha del gráfico para aumentar su tamaño.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-168">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span>  
  
10. <span data-ttu-id="0ab9a-169">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="0ab9a-170">El informe muestra el gráfico de barras de ventas correspondiente a cada vendedor para los años 2008 y 2009.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-170">The report displays the bar chart for sales for each sales person for the years 2008 and 2009.</span></span> <span data-ttu-id="0ab9a-171">La longitud de la barra corresponde al total de ventas.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-171">The length of the bar corresponds to the sales total.</span></span>  
  
##  <a name="3-modify-the-display-of-names-on-the-vertical-axis"></a><a name="AllValues"></a><span data-ttu-id="0ab9a-172">3. modificar la presentación de nombres en el eje vertical</span><span class="sxs-lookup"><span data-stu-id="0ab9a-172">3. Modify the Display of Names on the Vertical Axis</span></span>  
 <span data-ttu-id="0ab9a-173">De forma predeterminada, solo aparecen algunos de los valores del eje vertical.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-173">By default, only some of the values on the vertical axis appear.</span></span> <span data-ttu-id="0ab9a-174">Puede cambiar el gráfico para mostrar todas las categorías.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-174">You can change the chart to display all categories.</span></span>  
  
#### <a name="to-display-all-sales-persons-along-the-category-axis-of-a-bar-chart"></a><span data-ttu-id="0ab9a-175">Mostrar todos los vendedores en el eje de categorías de un gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="0ab9a-175">To display all sales persons along the category axis of a bar chart</span></span>  
  
1.  <span data-ttu-id="0ab9a-176">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-177">Haga clic con el botón secundario en el eje vertical y, a continuación, haga clic en **propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-177">Right-click the vertical axis, and then click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="0ab9a-178">En **Rango e intervalo del eje**, en el cuadro **Intervalo** , escriba **1**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-178">Under **Axis range and interval**, in the **Interval** box, type **1**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="0ab9a-179">Haga clic con el botón secundario en el **título del eje** vertical y desactive la casilla **Mostrar título del eje** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-179">Right-click the vertical **Axis Title** and clear the **Show Axis Title** check box.</span></span>  
  
6.  <span data-ttu-id="0ab9a-180">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-180">Click **Run** to preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ab9a-181">Si no se leen los nombres de vendedor en el eje vertical, puede hacer más alto el gráfico o cambiar las opciones de formato para las etiquetas del eje.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-181">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
###  <a name="display-last-name-and-first-name-on-vertical-axis"></a><a name="CategoryExpression"></a><span data-ttu-id="0ab9a-182">Mostrar los apellidos y el nombre en el eje vertical</span><span class="sxs-lookup"><span data-stu-id="0ab9a-182">Display Last Name and First Name on Vertical Axis</span></span>  
 <span data-ttu-id="0ab9a-183">Puede cambiar la expresión de categoría para incluir para cada vendedor el apellido seguido por el nombre.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-183">You can change the category expression to include last name followed by first name of each sales person.</span></span>  
  
##### <a name="to-change-the-category-expression"></a><span data-ttu-id="0ab9a-184">Para cambiar la expresión de categoría</span><span class="sxs-lookup"><span data-stu-id="0ab9a-184">To change the category expression</span></span>  
  
1.  <span data-ttu-id="0ab9a-185">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-185">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-186">Haga doble clic en el gráfico para mostrar el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-186">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="0ab9a-187">En el área **Grupos de categorías** , haga clic con el botón secundario en [LastName] y, después, haga clic en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-187">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="0ab9a-188">En Etiqueta, haga clic en el botón de expresión (Fx).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-188">In Label, click the expression (Fx) button.</span></span>  
  
5.  <span data-ttu-id="0ab9a-189">Escriba la siguiente expresión: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="0ab9a-189">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
     <span data-ttu-id="0ab9a-190">Esta expresión concatena el apellido, una coma y el nombre.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-190">This expression concatenates the last name, a comma, and the first name.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="0ab9a-191">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-191">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="0ab9a-192">Si los nombres no aparecen al ejecutar el informe, puede actualizar los datos manualmente.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-192">If the first names do not appear when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="0ab9a-193">Estando todavía en modo de vista previa, en la pestaña **Ejecutar** en el grupo **Navegación** , haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-193">While still in preview mode, on the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ab9a-194">Si no se leen los nombres de vendedor en el eje vertical, puede hacer más alto el gráfico o cambiar las opciones de formato para las etiquetas del eje.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-194">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
##  <a name="4-change-the-sort-order-for-names-on-the-vertical-axis"></a><a name="Sort"></a><span data-ttu-id="0ab9a-195">4. cambiar el criterio de ordenación de los nombres en el eje vertical</span><span class="sxs-lookup"><span data-stu-id="0ab9a-195">4. Change the Sort Order for Names on the Vertical Axis</span></span>  
 <span data-ttu-id="0ab9a-196">Al ordenar los datos en un gráfico, está cambiando el orden de valores en el eje de categoría.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-196">When you sort the data on a chart, you are changing the order of values on the category axis.</span></span>  
  
#### <a name="to-sort-the-names-in-alphabetical-order-on-the-bar-chart"></a><span data-ttu-id="0ab9a-197">Ordenar los nombres alfabéticamente en el gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="0ab9a-197">To sort the names in alphabetical order on the bar chart</span></span>  
  
1.  <span data-ttu-id="0ab9a-198">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-198">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-199">Haga doble clic en el gráfico para mostrar el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-199">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="0ab9a-200">En el área **Grupos de categorías** , haga clic con el botón secundario en [LastName] y, después, haga clic en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-200">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="0ab9a-201">Haga clic en **Ordenar**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-201">Click **Sorting**.</span></span> <span data-ttu-id="0ab9a-202">La página **Cambiar opciones de ordenación** muestra una lista de expresiones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-202">The **Change sorting options** page displays a list of sort expressions.</span></span> <span data-ttu-id="0ab9a-203">De forma predeterminada, esta lista tiene una expresión de ordenación que es igual que la expresión de grupo de categorías original.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-203">By default, this list has one sort expression that is the same as the original category group expression.</span></span>  
  
5.  <span data-ttu-id="0ab9a-204">En ordenar por, haga clic en el botón expresión (**FX**).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-204">In Sort by, click the expression (**Fx**) button.</span></span>  
  
6.  <span data-ttu-id="0ab9a-205">Escriba la siguiente expresión: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="0ab9a-205">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
7.  <span data-ttu-id="0ab9a-206">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-206">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="0ab9a-207">De nuevo en la página **propiedades del grupo de categorías** , en la lista desplegable **orden** , seleccione **Z a a**. Esto selecciona el orden alfabético inverso para que los nombres aparezcan en orden de arriba a abajo.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-207">Back on the **Category Group Properties** page, in the **Order** drop-down list, select **Z to A**. This selects reverse alphabetical order so that the names appear in order from top to bottom.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="0ab9a-208">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-208">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="0ab9a-209">Los nombres del eje horizontal se ordenan en orden inverso, con **Alerca** en la parte superior y **Zeng** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-209">The names on the horizontal axis are sorted in reverse order, with **Alerca** at the top and **Zeng** at the bottom.</span></span>  
  
##  <a name="5-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="0ab9a-210">5. Mueva la leyenda</span><span class="sxs-lookup"><span data-stu-id="0ab9a-210">5. Move the Legend</span></span>  
 <span data-ttu-id="0ab9a-211">Para mejorar la legibilidad de los valores del gráfico, es posible que le interese mover la leyenda correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-211">To improve the readability of the chart values, you might want to move the chart legend.</span></span> <span data-ttu-id="0ab9a-212">Por ejemplo, en un gráfico de barras, donde las barras se muestran horizontalmente, puede cambiar la posición de la leyenda para que aparezca debajo o encima del área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-212">For example, in a bar chart where bars are shown horizontally, you can change the position of the legend so that it is above or below the chart area.</span></span> <span data-ttu-id="0ab9a-213">Esto proporciona más espacio horizontal para las barras.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-213">This gives more horizontal space to the bars.</span></span>  
  
#### <a name="to-display-the-legend-below-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="0ab9a-214">Para mostrar la leyenda debajo del área de gráfico de un gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="0ab9a-214">To display the legend below the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="0ab9a-215">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-215">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-216">Haga clic con el botón secundario en la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-216">Right-click the legend on the chart.</span></span>  
  
3.  <span data-ttu-id="0ab9a-217">Seleccione **Propiedades de la leyenda**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-217">Select **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="0ab9a-218">Para **Posición de la leyenda**, seleccione una posición diferente.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-218">For **Legend position**, select a different position.</span></span> <span data-ttu-id="0ab9a-219">Por ejemplo, sitúe la leyenda centrada en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-219">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="0ab9a-220">Cuando la leyenda se coloca en la parte superior o inferior de un gráfico, su diseño cambia de vertical a horizontal.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-220">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="0ab9a-221">Puede seleccionar un diseño diferente en la lista desplegable **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-221">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="0ab9a-222">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-222">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="0ab9a-223">6. título del gráfico</span><span class="sxs-lookup"><span data-stu-id="0ab9a-223">6. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="0ab9a-224">Cambiar el título del gráfico situado por encima del área de gráfico de un gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="0ab9a-224">To change the chart title above the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="0ab9a-225">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-225">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-226">Seleccione las palabras **título del gráfico** en la parte superior del gráfico y, a continuación, escriba el siguiente texto: **ventas de 2008 y 2009**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-226">Select the words **Chart Title** at the top of the chart, and then type the following text: **Sales for 2008 and 2009**.</span></span>  
  
3.  <span data-ttu-id="0ab9a-227">Haga clic en cualquier lugar fuera del texto.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-227">Click anywhere outside the text.</span></span>  
  
4.  <span data-ttu-id="0ab9a-228">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-228">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="0ab9a-229">7. dar formato al eje horizontal y etiquetarlo</span><span class="sxs-lookup"><span data-stu-id="0ab9a-229">7. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="0ab9a-230">De forma predeterminada, el eje horizontal muestra los valores en un formato general que se escala automáticamente para ajustarse al tamaño del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-230">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-the-numbers-on-the-horizontal-axis"></a><span data-ttu-id="0ab9a-231">Dar formato a los números en el eje horizontal</span><span class="sxs-lookup"><span data-stu-id="0ab9a-231">To format the numbers on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="0ab9a-232">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-232">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-233">Haga clic en el eje horizontal a lo largo de la parte inferior del gráfico para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-233">Click the horizontal axis along the bottom of the chart to select it.</span></span>  
  
     <span data-ttu-id="0ab9a-234">En la cinta de opciones, en la pestaña **Inicio** , en el grupo **número** , haga clic en el botón **moneda** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-234">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="0ab9a-235">Las etiquetas del eje horizontal cambian al formato de moneda.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-235">The horizontal axis labels change to currency.</span></span>  
  
3.  <span data-ttu-id="0ab9a-236">(Opcional) Quite los dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-236">(Optional) Remove the decimal digits.</span></span> <span data-ttu-id="0ab9a-237">Cerca del botón **Moneda** , haga clic dos veces en el botón **Disminuir decimales** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-237">Near the **Currency** button, click the **Decrease Decimal** button twice.</span></span>  
  
4.  <span data-ttu-id="0ab9a-238">Haga clic con el botón secundario en el eje horizontal y, después, haga clic en **Propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-238">Right-click the horizontal axis, and click **Horizontal Axis Properties**.</span></span>  
  
5.  <span data-ttu-id="0ab9a-239">En la pestaña **número** , seleccione **Mostrar valores en miles.**</span><span class="sxs-lookup"><span data-stu-id="0ab9a-239">On the **Number** tab, select **Show values in Thousands.**</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="0ab9a-240">Haga clic con el botón derecho en **título del eje** y haga clic en propiedades del **título del eje**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-240">Right-click **Axis Title** and click **Axis Title Properties**.</span></span>  
  
8.  <span data-ttu-id="0ab9a-241">En el cuadro de **texto título** , escriba **ventas en miles** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-241">In the **Title text** box, type **Sales in thousands** and click **OK**.</span></span>  
  
9. <span data-ttu-id="0ab9a-242">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-242">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="0ab9a-243">El informe muestra el importe de ventas en el eje horizontal como moneda en miles y no tiene ningún dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-243">The report displays the sales amount on the horizontal axis as currency in thousands, and has no decimal digits.</span></span>  
  
##  <a name="8-add-a-filter-to-display-the-top-five-values"></a><a name="Filter"></a><span data-ttu-id="0ab9a-244">8. agregar un filtro para mostrar los cinco valores superiores</span><span class="sxs-lookup"><span data-stu-id="0ab9a-244">8. Add a Filter to Display the Top Five Values</span></span>  
 <span data-ttu-id="0ab9a-245">Puede agregar un filtro al gráfico para especificar qué datos del conjunto de datos se van a incluir o excluir del gráfico.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-245">You can add a filter to the chart to specify which data from the dataset to include or exclude in the chart.</span></span>  
  
#### <a name="to-add-a-filter-and-display-the-top-five-values"></a><span data-ttu-id="0ab9a-246">Agregar un filtro para mostrar los cinco valores superiores</span><span class="sxs-lookup"><span data-stu-id="0ab9a-246">To add a filter and display the top five values</span></span>  
  
1.  <span data-ttu-id="0ab9a-247">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-247">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-248">Haga doble clic en el gráfico para mostrar el panel **Datos del gráfico** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-248">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="0ab9a-249">En el área **Grupos de categorías** , haga clic con el botón secundario en el campo [LastName] y, después, haga clic en **Propiedades del grupo de categorías**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-249">In the **Category Groups** area, right-click the [LastName] field, and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="0ab9a-250">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-250">Click **Filters**.</span></span> <span data-ttu-id="0ab9a-251">La página **Cambiar filtros** puede mostrar una lista de expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-251">The **Change filters** page can display a list of filter expressions.</span></span> <span data-ttu-id="0ab9a-252">Esta lista aparece vacía de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-252">By default, this list is empty.</span></span>  
  
5.  <span data-ttu-id="0ab9a-253">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-253">Click **Add**.</span></span> <span data-ttu-id="0ab9a-254">Aparece un nuevo filtro en blanco.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-254">A new blank filter appears.</span></span>  
  
6.  <span data-ttu-id="0ab9a-255">En **expresión**, escriba **[SUM (SalesYear2009)]**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-255">In **Expression**, type **[Sum(SalesYear2009)]**.</span></span> <span data-ttu-id="0ab9a-256">Esto crea la expresión subyacente `=Sum(Fields!SalesYear2009.Value)`, que puede ver si hace clic en el botón **fx** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-256">This creates the underlying expression `=Sum(Fields!SalesYear2009.Value)`, which you can see if you click the **fx** button.</span></span>  
  
7.  <span data-ttu-id="0ab9a-257">Compruebe que el tipo de datos es **Texto**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-257">Verify that the data type is **Text**.</span></span>  
  
8.  <span data-ttu-id="0ab9a-258">En **Operador**, seleccione **Superior N** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-258">In **Operator**, select **Top N** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="0ab9a-259">En **Valor**, escriba la siguiente expresión: **=5**</span><span class="sxs-lookup"><span data-stu-id="0ab9a-259">In **Value**, type the following expression: **=5**</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="0ab9a-260">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-260">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="0ab9a-261">Si no se filtran los resultados al ejecutar el informe, puede actualizar los datos manualmente.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-261">If the results are not filtered when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="0ab9a-262">En la pestaña **Ejecutar** , en el grupo **Navegación** , haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-262">On the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
 <span data-ttu-id="0ab9a-263">El gráfico muestra los nombres de los cinco vendedores superiores del conjunto de datos de ventas de 2009.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-263">The chart shows the top five salesperson names from the 2009 sales data.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="0ab9a-264">9. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="0ab9a-264">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="0ab9a-265">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="0ab9a-265">To add a report title</span></span>  
  
1.  <span data-ttu-id="0ab9a-266">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-266">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="0ab9a-267">Escriba **gráfico de barras de ventas**, presione entrar y, a continuación, escriba **cinco vendedores superiores para 2009, de**modo que tenga este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0ab9a-267">Type **Sales Bar Chart**, press ENTER, and then type **Top Five Sellers for 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="0ab9a-268">**Gráfico de barras de ventas**</span><span class="sxs-lookup"><span data-stu-id="0ab9a-268">**Sales Bar Chart**</span></span>  
  
     <span data-ttu-id="0ab9a-269">**Cinco vendedores superiores de 2009**</span><span class="sxs-lookup"><span data-stu-id="0ab9a-269">**Top Five Sellers for 2009**</span></span>  
  
3.  <span data-ttu-id="0ab9a-270">Seleccione **Gráfico de barras de ventas**y haga clic en el botón **Negrita** .</span><span class="sxs-lookup"><span data-stu-id="0ab9a-270">Select **Sales Bar Chart**, and click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="0ab9a-271">Seleccione **cinco vendedores superiores para 2009**y, en la sección **fuente** de la pestaña **Inicio** , establezca el tamaño de fuente en **10**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-271">Select **Top Five Sellers for 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="0ab9a-272">(Opcional) Es posible que necesite hacer más alto el cuadro de texto Título para que quepan las dos líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-272">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="0ab9a-273">Este título aparecerá en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-273">This title will appear at the top of the report.</span></span> <span data-ttu-id="0ab9a-274">Cuando no hay ningún encabezado de página definido, los elementos de la parte superior del cuerpo del informe son equivalentes a un encabezado de informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-274">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="0ab9a-275">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-275">Click **Run** to preview the report.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="0ab9a-276">10. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="0ab9a-276">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="0ab9a-277">Para guardar el informe</span><span class="sxs-lookup"><span data-stu-id="0ab9a-277">To save the report</span></span>  
  
1.  <span data-ttu-id="0ab9a-278">Cambie a la vista de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-278">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="0ab9a-279">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-279">From the **Report Builder** button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="0ab9a-280">En **Nombre**, escriba **Gráfico de barras de ventas**.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-280">In **Name**, type **Sales Bar Chart**.</span></span>  
  
4.  <span data-ttu-id="0ab9a-281">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-281">Click **Save**.</span></span>  
  
 <span data-ttu-id="0ab9a-282">El informe se guardará en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-282">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0ab9a-283">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0ab9a-283">Next Steps</span></span>  
 <span data-ttu-id="0ab9a-284">Ha completado correctamente el tutorial Agregar un gráfico de barras al informe.</span><span class="sxs-lookup"><span data-stu-id="0ab9a-284">You have successfully completed the Adding a Bar Chart to Your Report tutorial.</span></span> <span data-ttu-id="0ab9a-285">Para obtener más información sobre los gráficos, vea [Gráficos &#40;Generador de informes y SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) y [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0ab9a-285">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab9a-286">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ab9a-286">See Also</span></span>  
 <span data-ttu-id="0ab9a-287">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="0ab9a-287">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="0ab9a-288">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0ab9a-288">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
