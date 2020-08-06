---
title: 'Tutorial: Agregar un KPI a un informe (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1bf77859-0b33-4f40-abaf-ebeeb6ebb1f8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 405978721068583597adf5c4257978a222121078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747926"
---
# <a name="tutorial-adding-a-kpi-to-your-report-report-builder"></a><span data-ttu-id="14a47-102">Tutorial: Agregar un KPI a un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="14a47-102">Tutorial: Adding a KPI to Your Report (Report Builder)</span></span>
  <span data-ttu-id="14a47-103">Un indicador clave de rendimiento (KPI) es un valor medible que tiene importancia para la empresa.</span><span class="sxs-lookup"><span data-stu-id="14a47-103">A key performance indicator (KPI) is a measurable value that has business significance.</span></span> <span data-ttu-id="14a47-104">Este tutorial lo enseñará a incluir un KPI en un informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-104">This tutorial teaches you how to include a (KPI) in a report.</span></span> <span data-ttu-id="14a47-105">En este escenario, el resumen de ventas por subcategorías de producto es el KPI.</span><span class="sxs-lookup"><span data-stu-id="14a47-105">In this scenario, the sales summary by product subcategories is the KPI.</span></span> <span data-ttu-id="14a47-106">El estado actual del KPI se muestra mediante colores, medidores e indicadores.</span><span class="sxs-lookup"><span data-stu-id="14a47-106">The current state of the KPI is shown by using colors, gauges, and indicators.</span></span>  
  
 <span data-ttu-id="14a47-107">En la siguiente ilustración se muestra el informe que creará.</span><span class="sxs-lookup"><span data-stu-id="14a47-107">The following illustration shows the report that you will create.</span></span>  
  
 <span data-ttu-id="14a47-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span><span class="sxs-lookup"><span data-stu-id="14a47-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="14a47-109">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="14a47-109">What You Will Learn</span></span>  
 <span data-ttu-id="14a47-110">En este tutorial, aprenderá agregar un KPI estableciendo el color de fondo de las celdas de la tabla en función del valor de celda, así como a agregar y configurar un medidor y un indicador.</span><span class="sxs-lookup"><span data-stu-id="14a47-110">In this tutorial, you will learn to add a KPI by setting the background color of table cells based on cell value and add and configure a gauge and an indicator.</span></span> <span data-ttu-id="14a47-111">También aprenderá a escribir la expresión que establece el color de fondo de las celdas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-111">You also learn to write the expression that sets the background color of the table cells.</span></span>  
  
 <span data-ttu-id="14a47-112">Este tutorial contiene los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="14a47-112">This tutorial contains the following procedures:</span></span>  
  
1.  [<span data-ttu-id="14a47-113">Crear un informe de tabla y un conjunto de datos con el asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="14a47-113">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Table)  
  
2.  [<span data-ttu-id="14a47-114">Organizar datos, elegir el diseño y el estilo con el asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="14a47-114">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="14a47-115">Utilizar los colores de fondo para mostrar un KPI</span><span class="sxs-lookup"><span data-stu-id="14a47-115">Use Background Colors to Display a KPI</span></span>](#BackgroundColors)  
  
4.  [<span data-ttu-id="14a47-116">Mostrar un KPI usando un medidor</span><span class="sxs-lookup"><span data-stu-id="14a47-116">Display a KPI by Using a Gauge</span></span>](#Gauge)  
  
5.  [<span data-ttu-id="14a47-117">Mostrar un KPI usando un indicador</span><span class="sxs-lookup"><span data-stu-id="14a47-117">Display a KPI by Using an Indicator</span></span>](#Indicator)  
  
6.  [<span data-ttu-id="14a47-118">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="14a47-118">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="14a47-119">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="14a47-119">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="14a47-120">En este tutorial, los pasos del asistente se fusionan en dos procedimientos: uno para crear el conjunto de datos y otro para crear una tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-120">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="14a47-121">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, elegir un origen de datos, crear un conjunto de datos y ejecutar el asistente, vea el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-121">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="14a47-122">Tiempo estimado para completar este tutorial: 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="14a47-122">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14a47-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14a47-123">Requirements</span></span>  
 <span data-ttu-id="14a47-124">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Table"></a><span data-ttu-id="14a47-125">1. crear un informe de tabla y un conjunto de informes desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="14a47-125">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="14a47-126">En el cuadro de diálogo **Introducción** , elija un origen de datos compartido, cree un conjunto de datos incrustado y muestre los datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-126">From the **Getting Started** dialog box, choose a shared data source, create an embedded dataset, and display the data in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14a47-127">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="14a47-127">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="14a47-128">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="14a47-128">This makes the query quite long.</span></span> <span data-ttu-id="14a47-129">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="14a47-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="14a47-130">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="14a47-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-table"></a><span data-ttu-id="14a47-131">Para crear una tabla</span><span class="sxs-lookup"><span data-stu-id="14a47-131">To create a new table</span></span>  
  
1.  <span data-ttu-id="14a47-132">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="14a47-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="14a47-133">Aparece el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="14a47-133">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14a47-134">Si el cuadro de diálogo **Introducción** no aparece, en el botón generador de informes, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="14a47-134">If the **Getting Started** dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="14a47-135">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="14a47-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="14a47-136">En el panel de la derecha, haga clic en **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="14a47-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="14a47-137">En la página Elegir un conjunto de datos , haga clic en **Crear un conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="14a47-137">On the Choose a dataset page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="14a47-138">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="14a47-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="14a47-139">En la página **elegir una conexión a un origen de datos** , seleccione un origen de datos existente o vaya al servidor de informes y seleccione un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="14a47-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source.</span></span> <span data-ttu-id="14a47-140">Si no está disponible ningún origen de datos o no tiene acceso a un servidor de informes, puede utilizar un origen del datos incrustados en su lugar.</span><span class="sxs-lookup"><span data-stu-id="14a47-140">If there no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="14a47-141">Para más información, vea [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-141">For more information, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="14a47-142">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="14a47-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="14a47-143">En la página **Diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="14a47-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="14a47-144">Copie y pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="14a47-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
10. <span data-ttu-id="14a47-145">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="14a47-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="14a47-146">2. organizar datos, elegir el diseño y el estilo desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="14a47-146">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="14a47-147">Utilice el asistente para proporcionar un diseño inicial en el que mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="14a47-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="14a47-148">El panel de vista previa del asistente le ayudará a visualizar el resultado de las agrupaciones de datos antes de completar la tabla o el diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="14a47-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-choose-a-layout-and-a-style"></a><span data-ttu-id="14a47-149">Para organizar los datos en grupos, elija un diseño y un estilo</span><span class="sxs-lookup"><span data-stu-id="14a47-149">To organize data into groups, choose a layout and a style</span></span>  
  
1.  <span data-ttu-id="14a47-150">En la página Organizar campos, arrastre Product hasta **Valores**.</span><span class="sxs-lookup"><span data-stu-id="14a47-150">On the Arrange fields page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="14a47-151">Arrastre Quantity hasta **Valores** y colóquelo debajo de Product.</span><span class="sxs-lookup"><span data-stu-id="14a47-151">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="14a47-152">El campo Quantity se resume con la función Sum, que es la función predeterminada para resumir campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="14a47-152">Quantity is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
3.  <span data-ttu-id="14a47-153">Arrastre Sales hasta **Valores** y colóquelo debajo de Quantity.</span><span class="sxs-lookup"><span data-stu-id="14a47-153">Drag Sales to **Values** and place below Quantity.</span></span>  
  
     <span data-ttu-id="14a47-154">Los pasos 1, 2 y 3 especifican los datos que deben mostrarse en la tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-154">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="14a47-155">Arrastre SalesDate hasta **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="14a47-155">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="14a47-156">Arrastre Subcategory hasta **Grupos de filas** y colóquelo debajo de SalesDate.</span><span class="sxs-lookup"><span data-stu-id="14a47-156">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="14a47-157">Los pasos 4 y 5 organizan los valores de los campos por fecha primeramente y, después, por todas las ventas de esa fecha.</span><span class="sxs-lookup"><span data-stu-id="14a47-157">Steps 4 and 5 organize the values for the fields first by date, and then by all sales for that date.</span></span>  
  
6.  <span data-ttu-id="14a47-158">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="14a47-158">Click **Next**.</span></span>  
  
     <span data-ttu-id="14a47-159">Al ejecutar el informe, la tabla muestra cada fecha, todos los pedidos de cada fecha, y todos los productos, cantidades y totales de ventas de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="14a47-159">When you run the report, the table displays each date, all orders for each date, and all products, quantities, and sales totals for each order.</span></span>  
  
7.  <span data-ttu-id="14a47-160">En la página elegir el diseño, en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="14a47-160">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
8.  <span data-ttu-id="14a47-161">Compruebe que esté seleccionada la opción **Bloqueado, subtotal abajo** .</span><span class="sxs-lookup"><span data-stu-id="14a47-161">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
9. <span data-ttu-id="14a47-162">Desactive la opción **Expandir o contraer grupos**.</span><span class="sxs-lookup"><span data-stu-id="14a47-162">Clear the option **Expand/collapse groups**.</span></span>  
  
     <span data-ttu-id="14a47-163">En este tutorial, el informe creado no usa la característica de obtención de detalles que permite a un usuario expandir una jerarquía de grupos primarios para mostrar filas de grupos secundarios y filas de detalles.</span><span class="sxs-lookup"><span data-stu-id="14a47-163">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
10. <span data-ttu-id="14a47-164">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="14a47-164">Click **Next**.</span></span>  
  
11. <span data-ttu-id="14a47-165">En la página Elegir un estilo, en el panel Estilos, seleccione un estilo.</span><span class="sxs-lookup"><span data-stu-id="14a47-165">On the Choose a Style page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="14a47-166">En la ilustración del informe completado se muestra el informe con el estilo Ocean.</span><span class="sxs-lookup"><span data-stu-id="14a47-166">The illustration of the completed report shows the report using the Ocean style.</span></span>  
  
12. <span data-ttu-id="14a47-167">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="14a47-167">Click **Finish**.</span></span>  
  
     <span data-ttu-id="14a47-168">La tabla se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="14a47-168">The table is added to the design surface.</span></span> <span data-ttu-id="14a47-169">La tabla tiene cinco columnas y cinco filas.</span><span class="sxs-lookup"><span data-stu-id="14a47-169">The table has five columns and five rows.</span></span> <span data-ttu-id="14a47-170">El panel Grupos de filas muestra tres grupos de filas: SalesDate, Subcategory y Details.</span><span class="sxs-lookup"><span data-stu-id="14a47-170">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="14a47-171">Los datos detallados son todos los datos recuperados por la consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="14a47-171">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
13. <span data-ttu-id="14a47-172">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-172">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="14a47-173">Para cada producto vendido en una fecha concreta, la tabla muestra el nombre del producto, la cantidad vendida y el total de ventas.</span><span class="sxs-lookup"><span data-stu-id="14a47-173">For each product that is sold on a specific date, the table displays the product name, the quantity sold, and the sales total.</span></span> <span data-ttu-id="14a47-174">Los datos se organizan primero por fecha de ventas y, a continuación, por subcategoría.</span><span class="sxs-lookup"><span data-stu-id="14a47-174">The data is organized first by sales date and then by subcategory.</span></span>  
  
##  <a name="3-use-background-colors-to-display-a-kpi"></a><a name="BackgroundColors"></a><span data-ttu-id="14a47-175">3. usar colores de fondo para mostrar un KPI</span><span class="sxs-lookup"><span data-stu-id="14a47-175">3. Use Background Colors to Display a KPI</span></span>  
 <span data-ttu-id="14a47-176">Los colores de fondo se pueden establecer en una expresión que se evalúe al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-176">Background colors can be set to an expression that is evaluated when you run the report.</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-by-using-background-colors"></a><span data-ttu-id="14a47-177">Para mostrar el estado actual de un KPI mediante colores de fondo</span><span class="sxs-lookup"><span data-stu-id="14a47-177">To display the present state of a KPI by using background colors</span></span>  
  
1.  <span data-ttu-id="14a47-178">En la tabla, haga clic con el botón secundario en dos celdas hacia abajo en la `[Sum(Sales)]` celda (la fila de subtotal que muestra las ventas de una subcategoría) y, a continuación, haga clic en **propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="14a47-178">In the table, right-click two cells down from the `[Sum(Sales)]` cell (the subtotal row that displays the sales for a subcategory), and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="14a47-179">En **relleno**, haga clic en el botón **FX** situado junto a la opción **color de relleno** y escriba la siguiente expresión en el campo **establecer expresión para: BackgroundColor** :</span><span class="sxs-lookup"><span data-stu-id="14a47-179">In **Fill**, click the **fx** button next to the **Fill color** option and enter the following expression in the **Set expression for: BackgroundColor** field:</span></span>  
  
 `=IIF(Sum(Fields!Sales.Value) >= 5000 ,"Lime", IIF(Sum(Fields!Sales.Value) < 2500, "Red","Yellow"))`  
  
 <span data-ttu-id="14a47-180">Esto cambia a verde el color del fondo, utilizando la tonalidad de verde denominada "Lima", para cada celda que contiene una suma agregada para `[Sum(Sales)]` igual o superior a 5000.</span><span class="sxs-lookup"><span data-stu-id="14a47-180">This changes the background color to green, using the shade of green named "Lime", for each cell that contains an aggregated sum for `[Sum(Sales)]` that is greater than or equal to 5000.</span></span> <span data-ttu-id="14a47-181">Los valores de `[Sum(Sales)]` entre 2500 y 5000 están coloreados en amarillo.</span><span class="sxs-lookup"><span data-stu-id="14a47-181">Values of `[Sum(Sales)]` between 2500 and 5000 are colored yellow.</span></span> <span data-ttu-id="14a47-182">Los valores inferiores a 2500 están coloreados en rojo.</span><span class="sxs-lookup"><span data-stu-id="14a47-182">Values less than 2500 are colored red.</span></span>  
  
1.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="14a47-183">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-183">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="14a47-184">En la fila de subtotal que muestra las ventas de una subcategoría, el color de fondo de la celda será rojo, amarillo o verde en función del valor de la suma de ventas.</span><span class="sxs-lookup"><span data-stu-id="14a47-184">In the subtotal row that displays the sales for a subcategory, the background color of the cell is red, yellow, or green depending on value of the sales sum.</span></span>  
  
##  <a name="4-display-a-kpi-by-using-a-gauge"></a><a name="Gauge"></a><span data-ttu-id="14a47-185">4. mostrar un KPI usando un medidor</span><span class="sxs-lookup"><span data-stu-id="14a47-185">4. Display a KPI by Using a Gauge</span></span>  
 <span data-ttu-id="14a47-186">Un medidor muestra un valor único de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="14a47-186">A gauge depicts a single value in a dataset.</span></span> <span data-ttu-id="14a47-187">En este tutorial se utiliza un medidor lineal horizontal porque su forma y simplicidad hacen que resulte fácil leerlo, incluso cuando tiene un tamaño pequeño y se usa dentro de la celda de una tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-187">This tutorial uses a horizontal linear gauge because its shape and simplicity makes it easy to read, even in when it is a small size and used within a table cell.</span></span> <span data-ttu-id="14a47-188">Para obtener más información, vea [Medidores &#40;Generador de informes y SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-188">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-a-gauge"></a><span data-ttu-id="14a47-189">Para mostrar el estado actual de un KPI usando un medidor</span><span class="sxs-lookup"><span data-stu-id="14a47-189">To display the present state of a KPI using a gauge</span></span>  
  
1.  <span data-ttu-id="14a47-190">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="14a47-190">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="14a47-191">En la tabla, haga clic con el botón secundario en el controlador de columna de la celda que ha cambiado en el procedimiento anterior, elija **Insertar columna**y, a continuación, haga clic en **derecha**.</span><span class="sxs-lookup"><span data-stu-id="14a47-191">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="14a47-192">Se agregará una nueva columna a la tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-192">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="14a47-193">Escriba **KPI** en el encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="14a47-193">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="14a47-194">En la pestaña **Insertar** , en el grupo **regiones de datos** , haga clic en **medidor**y, a continuación, haga clic en la superficie de diseño fuera de la tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-194">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click the design surface outside the table.</span></span> <span data-ttu-id="14a47-195">Aparece el cuadro de diálogo **Seleccionar tipo de medidor** .</span><span class="sxs-lookup"><span data-stu-id="14a47-195">The **Select Gauge Type** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="14a47-196">Haga clic en **lineal**.</span><span class="sxs-lookup"><span data-stu-id="14a47-196">Click **Linear**.</span></span> <span data-ttu-id="14a47-197">Se selecciona el primer tipo de medidor lineal, **horizontal**.</span><span class="sxs-lookup"><span data-stu-id="14a47-197">The first linear gauge type, **Horizontal**, is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="14a47-198">Se agregará un medidor a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="14a47-198">A gauge is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="14a47-199">En el panel Datos de informe, arrastre el campo Sales hasta el medidor.</span><span class="sxs-lookup"><span data-stu-id="14a47-199">From the Report Data pane, drag Sales to the gauge.</span></span> <span data-ttu-id="14a47-200">Al arrastrar Sales al medidor, se abrirá el panel de datos del medidor.</span><span class="sxs-lookup"><span data-stu-id="14a47-200">When you drag Sales across the gauge, the Gauge Data pane opens.</span></span>  
  
8.  <span data-ttu-id="14a47-201">Coloque las ventas en la lista **valores** .</span><span class="sxs-lookup"><span data-stu-id="14a47-201">Drop Sales in the **Values** list.</span></span>  
  
     <span data-ttu-id="14a47-202">Al arrastrar el campo al medidor, el campo se agrega usando la función integrada Sum.</span><span class="sxs-lookup"><span data-stu-id="14a47-202">When you drop the field onto the gauge, the field is aggregated by using the built-in Sum function.</span></span>  
  
9. <span data-ttu-id="14a47-203">Haga clic con el botón derecho en el puntero en el medidor y haga clic en **propiedades del puntero**.</span><span class="sxs-lookup"><span data-stu-id="14a47-203">Right-click the pointer in the gauge and click **Pointer Properties**.</span></span>  
  
10. <span data-ttu-id="14a47-204">En **tipo de puntero**, seleccione **barra**.</span><span class="sxs-lookup"><span data-stu-id="14a47-204">In **Pointer Type**, select **Bar**.</span></span> <span data-ttu-id="14a47-205">Esto cambia el puntero de un marcador a una barra que estará más visible cuando el medidor se agregue a la tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-205">This changes the pointer from a marker to a bar that will be more visible when the gauge is added to the table.</span></span>  
  
11. <span data-ttu-id="14a47-206">Haga clic en el **relleno del puntero**.</span><span class="sxs-lookup"><span data-stu-id="14a47-206">Click **Pointer Fill**.</span></span> <span data-ttu-id="14a47-207">En **color secundario,** elija **amarillo**.</span><span class="sxs-lookup"><span data-stu-id="14a47-207">In **Secondary Color,** pick **Yellow**.</span></span> <span data-ttu-id="14a47-208">El modelo de relleno de degradado cambiará de blanco a amarillo.</span><span class="sxs-lookup"><span data-stu-id="14a47-208">The gradient fill pattern will change from white to yellow.</span></span>  
  
12. <span data-ttu-id="14a47-209">Haga clic con el botón derecho en la escala del medidor y haga clic en **Propiedades de escala**.</span><span class="sxs-lookup"><span data-stu-id="14a47-209">Right-click the scale in the gauge and click **Scale Properties**.</span></span>  
  
13. <span data-ttu-id="14a47-210">Establezca la opción **máximo** en 25000.</span><span class="sxs-lookup"><span data-stu-id="14a47-210">Set the **Maximum** option to 25000.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14a47-211">En lugar de una constante como 25 000, puede usar una expresión para calcular dinámicamente el valor de la opción **Máximo** .</span><span class="sxs-lookup"><span data-stu-id="14a47-211">Instead of a constant such as 25000, you can use an expression to dynamically calculate the value of the **Maximum** option.</span></span> <span data-ttu-id="14a47-212">La expresión usaría el agregado de la característica de agregados y es similar a la expresión `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span><span class="sxs-lookup"><span data-stu-id="14a47-212">The expression would use the aggregate of aggregate feature and look similar to the expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span></span>  
  
14. <span data-ttu-id="14a47-213">Arrastre el medidor dentro de la tabla a la tercera celda en la fila de subtotal que muestra las ventas para una subcategoría de la columna que insertó.</span><span class="sxs-lookup"><span data-stu-id="14a47-213">Drag the gauge inside the table into the third cell in the subtotal row that displays the sales for a subcategory of the column that you inserted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14a47-214">Puede que tenga que cambiar el tamaño de la columna para que el medidor lineal horizontal quepa en la celda.</span><span class="sxs-lookup"><span data-stu-id="14a47-214">You might have to resize the column so that the horizontal linear gauge fits into the cell.</span></span> <span data-ttu-id="14a47-215">Para cambiar el tamaño de la columna, haga clic en el encabezado de columna y use los controladores de tamaño para cambiar el tamaño de las celdas horizontal y verticalmente.</span><span class="sxs-lookup"><span data-stu-id="14a47-215">To resize the column, click a column header and use the handles to resize the cells horizontally and vertically.</span></span>  
  
15. <span data-ttu-id="14a47-216">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-216">Click **Run** to preview the report.</span></span>  
  
     <span data-ttu-id="14a47-217">La longitud horizontal de la barra en el medidor cambia en función del valor del KPI.</span><span class="sxs-lookup"><span data-stu-id="14a47-217">The horizontal length of the bar in the gauge changes depending on the value of the KPI.</span></span>  
  
16. <span data-ttu-id="14a47-218">(Opcional) Agregue un tope máximo para controlar el desbordamiento, de modo que cualquier valor que supere el máximo de la escala siempre señale al tope máximo:</span><span class="sxs-lookup"><span data-stu-id="14a47-218">(Optional) Add a maximum pin to handle overflow so that any value over the scale maximum always points to the maximum pin:</span></span>  
  
    1.  <span data-ttu-id="14a47-219">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="14a47-219">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="14a47-220">Haga clic en la escala.</span><span class="sxs-lookup"><span data-stu-id="14a47-220">Click the scale.</span></span> <span data-ttu-id="14a47-221">Las propiedades de la escala lineal se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="14a47-221">The properties for the linear scale are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="14a47-222">En la categoría **PIN de escala** , expanda el nodo **MaximumPin** .</span><span class="sxs-lookup"><span data-stu-id="14a47-222">In the **Scale Pins** category, expand the **MaximumPin** node.</span></span>  
  
    4.  <span data-ttu-id="14a47-223">Establezca la propiedad **Habilitar** en `True` .</span><span class="sxs-lookup"><span data-stu-id="14a47-223">Set the **Enable** property to `True`.</span></span> <span data-ttu-id="14a47-224">Aparece un tope después del valor máximo en la escala.</span><span class="sxs-lookup"><span data-stu-id="14a47-224">A pin appears after the maximum value on the scale.</span></span>  
  
    5.  <span data-ttu-id="14a47-225">Establezca **BorderColor** en `Lime` .</span><span class="sxs-lookup"><span data-stu-id="14a47-225">Set **BorderColor** to `Lime`.</span></span>  
  
17. <span data-ttu-id="14a47-226">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-display-a-kpi-by-using-an-indicator"></a><a name="Indicator"></a><span data-ttu-id="14a47-227">5. mostrar un KPI usando un indicador</span><span class="sxs-lookup"><span data-stu-id="14a47-227">5. Display a KPI by Using an Indicator</span></span>  
 <span data-ttu-id="14a47-228">Los indicadores son medidores pequeños y simples que comunican los valores de datos de un vistazo.</span><span class="sxs-lookup"><span data-stu-id="14a47-228">Indicators are small simple gauges that communicate data values at a glance.</span></span> <span data-ttu-id="14a47-229">Debido a su tamaño y simplicidad, los indicadores se utilizan a menudo en tablas y matrices.</span><span class="sxs-lookup"><span data-stu-id="14a47-229">Because of their size and simplicity, indicators are often used in tables and matrices.</span></span> <span data-ttu-id="14a47-230">Para más información, vea [Indicadores &#40;Generador de informes y SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-230">For more information, see [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-an-indicator"></a><span data-ttu-id="14a47-231">Para mostrar el estado actual de un KPI usando un indicador</span><span class="sxs-lookup"><span data-stu-id="14a47-231">To display the present state of a KPI using an indicator</span></span>  
  
1.  <span data-ttu-id="14a47-232">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="14a47-232">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="14a47-233">En la tabla, haga clic con el botón secundario en el controlador de columna de la celda que ha cambiado en el procedimiento anterior, elija **Insertar columna**y, a continuación, haga clic en **derecha**.</span><span class="sxs-lookup"><span data-stu-id="14a47-233">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="14a47-234">Se agregará una nueva columna a la tabla.</span><span class="sxs-lookup"><span data-stu-id="14a47-234">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="14a47-235">Escriba **KPI** en el encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="14a47-235">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="14a47-236">Haga clic en la celda del subtotal de la subcategoría.</span><span class="sxs-lookup"><span data-stu-id="14a47-236">Click the cell for the subcategory subtotal.</span></span>  
  
5.  <span data-ttu-id="14a47-237">En la pestaña **Insertar** , en el grupo **regiones de datos** , haga doble clic en **indicador.**</span><span class="sxs-lookup"><span data-stu-id="14a47-237">On the **Insert** tab, in the **Data Regions** group, double-click **Indicator.**</span></span>  
  
     <span data-ttu-id="14a47-238">Se abrirá el cuadro de diálogo **Seleccionar tipo de indicador** .</span><span class="sxs-lookup"><span data-stu-id="14a47-238">The **Select Indicator Type** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="14a47-239">Haga clic en **formas**.</span><span class="sxs-lookup"><span data-stu-id="14a47-239">Click **Shapes**.</span></span> <span data-ttu-id="14a47-240">Se selecciona el primer tipo de forma, 3 semáforos (sin marco **)** .</span><span class="sxs-lookup"><span data-stu-id="14a47-240">The first shape type, **3 Traffic Lights (Unrimmed),** is selected.</span></span>  
  
     <span data-ttu-id="14a47-241">Utilice este indicador en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="14a47-241">You will use this indicator in the tutorial.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="14a47-242">El indicador se agregará a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="14a47-242">The indicator is added to the design surface.</span></span>  
  
8.  <span data-ttu-id="14a47-243">Haga clic con el botón derecho en el indicador y, después, haga clic en **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="14a47-243">Right-click the indicator and click **Indicator Properties**.</span></span>  
  
9. <span data-ttu-id="14a47-244">Haga clic en **valores y Estados**.</span><span class="sxs-lookup"><span data-stu-id="14a47-244">Click **Values and States**.</span></span>  
  
10. <span data-ttu-id="14a47-245">En la lista desplegable valor, seleccione **[SUM (sales)]**, pero no cambie ninguna otra opción.</span><span class="sxs-lookup"><span data-stu-id="14a47-245">In the Value drop-down list, select **[Sum(Sales)]**, but do not change any other options.</span></span>  
  
     <span data-ttu-id="14a47-246">De manera predeterminada, la sincronización de datos se produce en la región de datos y podrá ver el valor **Tablix1**, el nombre de la región de datos de la tabla del informe, en el cuadro **Ámbito de sincronización** .</span><span class="sxs-lookup"><span data-stu-id="14a47-246">By default, data synchronization occurs across the data region and you see the value **Tablix1**, the name of the table data region in the report, in the **Synchronization scope** box.</span></span>  
  
     <span data-ttu-id="14a47-247">En este informe, podrá cambiar también el ámbito de un indicador colocado en la celda del subtotal de la subcategoría para realizar la sincronización en el campo SalesDate.</span><span class="sxs-lookup"><span data-stu-id="14a47-247">In this report, you can also change the scope of an indicator placed in the cell of the subcategory subtotal to synchronize across the SalesDate field.</span></span>  
  
11. <span data-ttu-id="14a47-248">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-248">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="14a47-249">6. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="14a47-249">6. Add a Report Title</span></span>  
 <span data-ttu-id="14a47-250">Los títulos de informe aparecen en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="14a47-250">A report title appears at the top of the report.</span></span> <span data-ttu-id="14a47-251">Puede situar el título del informe en un encabezado de informe o, si el informe no lo utiliza, en un cuadro de texto en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-251">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="14a47-252">Deberá utilizar el cuadro de texto que se coloca automáticamente en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-252">You will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="14a47-253">El texto se puede mejorar aún más aplicando estilos de fuente, tamaños y colores diferentes a las frases y caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="14a47-253">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="14a47-254">Para obtener más información, vea [Dar formato al texto en un cuadro de texto &#40;Generador de informes y SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-254">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="14a47-255">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="14a47-255">To add a report title</span></span>  
  
1.  <span data-ttu-id="14a47-256">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="14a47-256">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="14a47-257">Escriba **KPI de ventas del producto**y, a continuación, haga clic fuera del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="14a47-257">Type **Product Sales KPI**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="14a47-258">Opcionalmente, haga clic con el botón secundario en el cuadro de texto que contiene **KPI de ventas de productos**, haga clic en propiedades de cuadro de **texto**y, a continuación, en la pestaña fuente, seleccione los diferentes estilos de fuente, tamaños y colores.</span><span class="sxs-lookup"><span data-stu-id="14a47-258">Optionally, right-click the text box that contains **Product Sales KPI**, click **Text Box Properties**, and then on the Font tab select the different font styles, sizes and colors.</span></span>  
  
4.  <span data-ttu-id="14a47-259">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-259">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="14a47-260">7. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="14a47-260">7. Save the Report</span></span>  
 <span data-ttu-id="14a47-261">Guarde el informe un servidor de informes o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="14a47-261">Save the report to a report server or your computer.</span></span> <span data-ttu-id="14a47-262">Si no guarda el informe en el servidor de informes, varias características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como los elementos de informe y los subinformes, no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="14a47-262">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="14a47-263">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="14a47-263">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="14a47-264">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="14a47-264">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="14a47-265">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="14a47-265">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="14a47-266">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="14a47-266">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="14a47-267">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="14a47-267">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="14a47-268">Una vez completada la conexión, se mostrará el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="14a47-268">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="14a47-269">En **Nombre**, reemplace el nombre predeterminado por **KPI de ventas del producto**.</span><span class="sxs-lookup"><span data-stu-id="14a47-269">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
5.  <span data-ttu-id="14a47-270">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="14a47-270">Click **Save**.</span></span>  
  
 <span data-ttu-id="14a47-271">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="14a47-271">The report is saved to the report server.</span></span> <span data-ttu-id="14a47-272">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="14a47-272">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="14a47-273">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="14a47-273">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="14a47-274">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="14a47-274">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="14a47-275">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde quiere guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-275">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14a47-276">Si no tiene acceso a un servidor de informes, haga clic en **Escritorio**, **Mis documentos**o **Mi PC** y guarde el informe en su equipo.</span><span class="sxs-lookup"><span data-stu-id="14a47-276">If you do not have access to a report server, click **Desktop**, **My Documents**, or **My computer** and save the report to your computer.</span></span>  
  
1.  <span data-ttu-id="14a47-277">En **Nombre**, reemplace el nombre predeterminado por **KPI de ventas del producto**.</span><span class="sxs-lookup"><span data-stu-id="14a47-277">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
2.  <span data-ttu-id="14a47-278">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="14a47-278">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="14a47-279">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="14a47-279">Next Steps</span></span>  
 <span data-ttu-id="14a47-280">Ha completado correctamente el tutorial Agregar un KPI a un informe.</span><span class="sxs-lookup"><span data-stu-id="14a47-280">You have successfully completed the Adding a KPI to Your Report tutorial.</span></span> <span data-ttu-id="14a47-281">Para obtener más información, consulte indicadores de medidores (Generador de informes) [&#40;generador de informes y SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a47-281">For more information, see Gauges (Report Builder) [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a47-282">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14a47-282">See Also</span></span>  
 <span data-ttu-id="14a47-283">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="14a47-283">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="14a47-284">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="14a47-284">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
