---
title: 'Tutorial: Informe de asignaciones (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8d831356-7efa-40cc-ae95-383b3eecf833
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b737bb3fe74eb3524f2944a7458cb4837b1aeedf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748592"
---
# <a name="tutorial-map-report-report-builder"></a><span data-ttu-id="385ba-102">Tutorial: Informe de asignaciones (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="385ba-102">Tutorial: Map Report (Report Builder)</span></span>
  <span data-ttu-id="385ba-103">Este tutorial le ayudará a obtener información sobre las características de mapa que puede utilizar para mostrar los datos de informe sobre un fondo geográfico.</span><span class="sxs-lookup"><span data-stu-id="385ba-103">This tutorial is designed to help you learn about the map features you can use to display report data against a geographic background.</span></span>  
  
 <span data-ttu-id="385ba-104">Los mapas están basados en datos espaciales que normalmente está compuestos de puntos, líneas y polígonos.</span><span class="sxs-lookup"><span data-stu-id="385ba-104">Maps are based on spatial data that typically consists of points, lines, and polygons.</span></span> <span data-ttu-id="385ba-105">Por ejemplo, un polígono puede representar el perfil de un condado, una línea puede representar una carretera y un punto puede representar la ubicación de una ciudad.</span><span class="sxs-lookup"><span data-stu-id="385ba-105">For example, a polygon can represent the outline of a county, a line can represent a road, and a point can represent the location of a city.</span></span> <span data-ttu-id="385ba-106">Cada tipo de datos espaciales se muestra en una capa de mapa independiente, como un conjunto de elementos de mapa.</span><span class="sxs-lookup"><span data-stu-id="385ba-106">Each type of spatial data is displayed on a separate map layer as a set of map elements.</span></span>  
  
 <span data-ttu-id="385ba-107">Para variar la apariencia de los elementos de mapa, especifique un campo que tenga valores que hagan coincidir los elementos de mapa con los datos analíticos de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="385ba-107">To vary the appearance of map elements, you specify a field that has values that match the map elements with analytical data from a dataset.</span></span> <span data-ttu-id="385ba-108">También puede definir las reglas que varían el color, tamaño u otras propiedades basadas en rangos de datos.</span><span class="sxs-lookup"><span data-stu-id="385ba-108">You can also define rules that vary color, size, or other properties based on ranges of data.</span></span>  
  
 <span data-ttu-id="385ba-109">En este tutorial, compilará un informe de mapa que muestre ubicaciones de almacenes en los condados del Estado de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="385ba-109">In this tutorial, you will build a map report that displays store locations in New York state counties.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="385ba-110">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="385ba-110">What You Will Learn</span></span>  
 <span data-ttu-id="385ba-111">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="385ba-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="385ba-112">Crear un mapa con una capa de polígono desde el Asistente para mapas</span><span class="sxs-lookup"><span data-stu-id="385ba-112">Create a Map with a Polygon Layer from the Map Wizard</span></span>](#Map)  
  
2.  [<span data-ttu-id="385ba-113">Agregar una capa de punto de mapa para mostrar las ubicaciones del almacén</span><span class="sxs-lookup"><span data-stu-id="385ba-113">Add a Map Point Layer to Display Store Locations</span></span>](#PointLayer)  
  
3.  [<span data-ttu-id="385ba-114">Agregar una capa de línea de mapa para mostrar una ruta</span><span class="sxs-lookup"><span data-stu-id="385ba-114">Add a Map Line Layer to Display a Route</span></span>](#LineLayer)  
  
4.  [<span data-ttu-id="385ba-115">Agregar un fondo de mosaico de Bing Maps</span><span class="sxs-lookup"><span data-stu-id="385ba-115">Add a Bing Maps Tile Background</span></span>](#TileLayer)  
  
5.  [<span data-ttu-id="385ba-116">Hacer una capa transparente</span><span class="sxs-lookup"><span data-stu-id="385ba-116">Make a Layer Transparent</span></span>](#Transparent)  
  
6.  [<span data-ttu-id="385ba-117">Variar los colores de condado de acuerdo con las ventas</span><span class="sxs-lookup"><span data-stu-id="385ba-117">Vary County Color Based on Sales</span></span>](#Vary)  
  
    1.  [<span data-ttu-id="385ba-118">Compilar una relación entre los datos espaciales y los datos analíticos</span><span class="sxs-lookup"><span data-stu-id="385ba-118">Build a Relationship between Spatial and Analytical Data</span></span>](#Relationship)  
  
    2.  [<span data-ttu-id="385ba-119">Especificar las reglas de color para polígonos</span><span class="sxs-lookup"><span data-stu-id="385ba-119">Specify Color Rules for Polygons</span></span>](#ColorRules)  
  
    3.  [<span data-ttu-id="385ba-120">Dar formato a los datos en la escala de color como moneda</span><span class="sxs-lookup"><span data-stu-id="385ba-120">Format the Data in the Color Scale as Currency</span></span>](#ColorScale)  
  
    4.  [<span data-ttu-id="385ba-121">Crear una nueva leyenda</span><span class="sxs-lookup"><span data-stu-id="385ba-121">Create a New Legend</span></span>](#NewLegend)  
  
    5.  [<span data-ttu-id="385ba-122">Asociar la leyenda y las reglas de color</span><span class="sxs-lookup"><span data-stu-id="385ba-122">Associate Legend and Color Rules</span></span>](#Associate)  
  
    6.  [<span data-ttu-id="385ba-123">Borrar el color en los condados sin datos</span><span class="sxs-lookup"><span data-stu-id="385ba-123">Clear Color from Counties with No Data</span></span>](#NoData)  
  
7.  [<span data-ttu-id="385ba-124">Agregar un punto personalizado</span><span class="sxs-lookup"><span data-stu-id="385ba-124">Add a Custom Point</span></span>](#CustomPoint)  
  
8.  [<span data-ttu-id="385ba-125">Centrar la vista de mapa</span><span class="sxs-lookup"><span data-stu-id="385ba-125">Center the Map View</span></span>](#CenterView)  
  
9. [<span data-ttu-id="385ba-126">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="385ba-126">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="385ba-127">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="385ba-127">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="385ba-128">En este tutorial, los pasos del asistente se fusionan en dos procedimientos: uno para crear el conjunto de datos y otro para crear una tabla.</span><span class="sxs-lookup"><span data-stu-id="385ba-128">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="385ba-129">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, elegir un origen de datos, crear un conjunto de datos y ejecutar el asistente, vea el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="385ba-129">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="385ba-130">Tiempo estimado para completar este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="385ba-130">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="385ba-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="385ba-131">Requirements</span></span>  
 <span data-ttu-id="385ba-132">Para obtener información sobre los requisitos, vea [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="385ba-132">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-map-with-a-polygon-layer-from-the-map-wizard"></a><a name="Map"></a><span data-ttu-id="385ba-133">1. crear un mapa con una capa de polígono desde el Asistente para mapas</span><span class="sxs-lookup"><span data-stu-id="385ba-133">1. Create a Map with a Polygon Layer from the Map Wizard</span></span>  
 <span data-ttu-id="385ba-134">Agregar un mapa al informe desde la galería de mapas.</span><span class="sxs-lookup"><span data-stu-id="385ba-134">Add a map to your report from the map gallery.</span></span> <span data-ttu-id="385ba-135">El mapa tiene una capa que muestra los condados del Estado de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="385ba-135">The map has one layer that displays the counties in New York state.</span></span> <span data-ttu-id="385ba-136">La forma de cada condado es un polígono basado en los datos espaciales que se incrustan en el mapa desde la galería de mapas.</span><span class="sxs-lookup"><span data-stu-id="385ba-136">The shape of each county is a polygon based on spatial data that is embedded in the map from the map gallery.</span></span>  
  
#### <a name="to-add-a-map-with-the-map-wizard-in-a-new-report"></a><span data-ttu-id="385ba-137">Para agregar un mapa con el Asistente para mapas en un informe nuevo</span><span class="sxs-lookup"><span data-stu-id="385ba-137">To add a map with the map wizard in a new report</span></span>  
  
1.  <span data-ttu-id="385ba-138">Haga clic en **Inicio**, seleccione **Programas**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Generador de informes**y luego haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="385ba-138">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="385ba-139">Aparecerá el cuadro de diálogo Introducción.</span><span class="sxs-lookup"><span data-stu-id="385ba-139">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="385ba-140"> Si el cuadro de diálogo Introducción no aparece, en el botón Generador de informes, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="385ba-140">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="385ba-141">En el panel de la izquierda, compruebe que está seleccionada la opción **Informe** .</span><span class="sxs-lookup"><span data-stu-id="385ba-141">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="385ba-142">En el panel derecho, haga clic en **Asistente para mapas**.</span><span class="sxs-lookup"><span data-stu-id="385ba-142">In the right pane, click **Map Wizard**.</span></span>  
  
4.  <span data-ttu-id="385ba-143">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="385ba-143">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="385ba-144">En la página**Elegir un origen de datos espaciales** , compruebe que **Galería de mapas** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="385ba-144">**Choose a source of spatial data** page, verify that **Map gallery** is selected.</span></span>  
  
6.  <span data-ttu-id="385ba-145">En el panel Galería de mapas, expanda **Estados por condado** en **EE.UU.** y haga clic en **Nueva York**.</span><span class="sxs-lookup"><span data-stu-id="385ba-145">In the Map Gallery pane, expand **States by County** under **USA**, and click **New York**.</span></span>  
  
     <span data-ttu-id="385ba-146">El panel Vista previa del mapa muestra el mapa del condado de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="385ba-146">The Map Preview pane displays the New York county map.</span></span>  
  
7.  <span data-ttu-id="385ba-147">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-147">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="385ba-148">En **Elegir opciones de datos espaciales y vista de mapa** , acepte los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="385ba-148">On the **Choose spatial data and map view options** page, accept the defaults.</span></span> <span data-ttu-id="385ba-149">De forma predeterminada, los elementos de mapa de una galería de mapas se incrustarán automáticamente en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-149">By default, map elements from a map gallery will automatically be embedded in the report definition.</span></span>  
  
9. <span data-ttu-id="385ba-150">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-150">Click **Next**.</span></span>  
  
10. <span data-ttu-id="385ba-151">En la página **Elegir visualización de mapa** , compruebe que la opción **Mapa básico** está seleccionada y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-151">On the **Choose map visualization** page, verify **Basic Map** is selected, and click **Next**.</span></span>  
  
11. <span data-ttu-id="385ba-152">En la página **Elegir tema de color y visualización de datos** , seleccione la opción **Mostrar etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="385ba-152">On the **Choose color theme and data visualization** page, select the **Display labels** option.</span></span>  
  
12. <span data-ttu-id="385ba-153">Si está seleccionada, desactive la opción **Mapa de un color** .</span><span class="sxs-lookup"><span data-stu-id="385ba-153">If it is selected, clear the **Single color map** option.</span></span>  
  
13. <span data-ttu-id="385ba-154">En la lista desplegable **campo de datos** , haga clic en #COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="385ba-154">From the **Data field** drop-down list, click #COUNTYNAME.</span></span> <span data-ttu-id="385ba-155">El panel Vista previa del mapa del asistente muestra los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="385ba-155">The Map Preview pane in the wizard displays the following items:</span></span>  
  
    -   <span data-ttu-id="385ba-156">Un título con el texto **Título del mapa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-156">A title with the text **Map Title**.</span></span>  
  
    -   <span data-ttu-id="385ba-157">Un mapa que muestra los condados de Nueva York, donde cada condado es de un color diferente y su nombre aparece siempre que se pasa el puntero sobre el área del condado.</span><span class="sxs-lookup"><span data-stu-id="385ba-157">A map that displays counties in New York where each county is a different color and the county name appears wherever it fits over the county area.</span></span>  
  
    -   <span data-ttu-id="385ba-158">Una leyenda que contiene un título y una lista de los elementos 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="385ba-158">A legend that contains a title and a list of items 1 through 5.</span></span>  
  
    -   <span data-ttu-id="385ba-159">Una escala de colores que contiene los valores 0 a 160 y ningún color.</span><span class="sxs-lookup"><span data-stu-id="385ba-159">A color scale that contains values 0 to 160 and no color.</span></span>  
  
    -   <span data-ttu-id="385ba-160">Una escala de distancia que muestra kilómetros (km) y millas (mi).</span><span class="sxs-lookup"><span data-stu-id="385ba-160">A distance scale that displays kilometers (km) and miles (mi).</span></span>  
  
14. <span data-ttu-id="385ba-161">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="385ba-161">Click **Finish**.</span></span>  
  
     <span data-ttu-id="385ba-162">Se agrega el mapa a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-162">The map is added to the design surface.</span></span>  
  
15. <span data-ttu-id="385ba-163">Haga clic en el mapa para seleccionarlo y mostrar el panel **Capas de mapa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-163">Click the map to select it and display the **Map Layers Pane**.</span></span> <span data-ttu-id="385ba-164">El panel **Capas de mapa** muestra una capa de polígono del tipo **Incrustado**.</span><span class="sxs-lookup"><span data-stu-id="385ba-164">The **Map Layers Pane** shows one polygon layer of layer type **Embedded**.</span></span> <span data-ttu-id="385ba-165">Cada condado es un elemento de mapa incrustado en esta capa.</span><span class="sxs-lookup"><span data-stu-id="385ba-165">Each county is an embedded map element on this layer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="385ba-166">Si no ve el panel **Capas de mapa** , quizá se esté mostrando fuera de su vista actual.</span><span class="sxs-lookup"><span data-stu-id="385ba-166">If you do not see the **Map Layers** pane, it might be displayed outside your current view.</span></span> <span data-ttu-id="385ba-167">Use la barra de desplazamiento de la parte inferior de la ventana de la vista Diseño para cambiar la vista.</span><span class="sxs-lookup"><span data-stu-id="385ba-167">Use the scroll bar at the bottom of the Design view window to change your view.</span></span> <span data-ttu-id="385ba-168">O bien, en la pestaña **Ver** , desactive la opción **Propiedades** o **Datos del informe** para proporcionar una mayor área de diseño expuesta.</span><span class="sxs-lookup"><span data-stu-id="385ba-168">Alternatively, in the **View** tab, clear the **Properties** or the **Report Data** option to provide more design surface area.</span></span>  
  
16. <span data-ttu-id="385ba-169">Haga clic con el botón secundario en el título del mapa y, a continuación, haga clic en **Propiedades del título**.</span><span class="sxs-lookup"><span data-stu-id="385ba-169">Right-click the map title, and then click **Title Properties**.</span></span>  
  
17. <span data-ttu-id="385ba-170">Reemplace el texto de título con **Ventas por almacén**.</span><span class="sxs-lookup"><span data-stu-id="385ba-170">Replace the title text with **Sales by Store**.</span></span>  
  
18. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
19. <span data-ttu-id="385ba-171">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-171">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-172">El informe representado muestra el título del mapa, el mapa y la escala de distancia.</span><span class="sxs-lookup"><span data-stu-id="385ba-172">The rendered report displays the map title, the map, and the distance scale.</span></span> <span data-ttu-id="385ba-173">Los condados están en una capa de polígono de mapa.</span><span class="sxs-lookup"><span data-stu-id="385ba-173">The counties are on a map polygon layer.</span></span> <span data-ttu-id="385ba-174">Cada condado es un polígono que varía según el color de una paleta de colores, pero los colores no están asociados a ningún dato.</span><span class="sxs-lookup"><span data-stu-id="385ba-174">Each county is a polygon that varies by color from a color palette, but the colors are not associated with any data.</span></span> <span data-ttu-id="385ba-175">La escala de distancia muestra las distancias en kilómetros y millas.</span><span class="sxs-lookup"><span data-stu-id="385ba-175">The distance scale displays distances in both kilometers and miles.</span></span>  
  
 <span data-ttu-id="385ba-176">La leyenda de mapa y la escala del color no aparecen todavía, porque no hay datos analíticos asociados a cada condado.</span><span class="sxs-lookup"><span data-stu-id="385ba-176">The map legend and color scale do not yet appear because there is no analytical data associated with each county.</span></span> <span data-ttu-id="385ba-177">Agregará los datos analíticos posteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="385ba-177">You will add analytical data later in this tutorial.</span></span>  
  
##  <a name="2-add-a-map-point-layer-to-display-store-locations"></a><a name="PointLayer"></a><span data-ttu-id="385ba-178">2. agregar una capa de punto de mapa para mostrar las ubicaciones del almacén</span><span class="sxs-lookup"><span data-stu-id="385ba-178">2. Add a Map Point Layer to Display Store Locations</span></span>  
 <span data-ttu-id="385ba-179">Utilice el asistente para capas de mapa para agregar una capa de punto que muestre las ubicaciones de almacenes.</span><span class="sxs-lookup"><span data-stu-id="385ba-179">Use the map layer wizard to add a point layer that displays the locations of stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="385ba-180">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="385ba-180">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="385ba-181">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="385ba-181">This makes the query quite long.</span></span> <span data-ttu-id="385ba-182">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="385ba-182">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="385ba-183">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="385ba-183">This is for learning purposes only.</span></span>  
  
#### <a name="to-add-a-point-layer-based-on-a-sql-server-spatial-query"></a><span data-ttu-id="385ba-184">Para agregar una capa de punto según una consulta espacial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="385ba-184">To add a point layer based on a SQL Server spatial query</span></span>  
  
1.  <span data-ttu-id="385ba-185">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-185">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-186">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-186">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="385ba-187">En la barra de herramientas, haga clic en el botón **Asistente para nueva capa**![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span><span class="sxs-lookup"><span data-stu-id="385ba-187">On the toolbar, click the **New layer wizard** button ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span></span>  
  
3.  <span data-ttu-id="385ba-188">En la página **elegir un origen de datos espaciales** , seleccione **SQL Server consulta espacial**y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-188">On the **Choose a source of spatial data** page, select **SQL Server spatial query**, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="385ba-189">En la página **Elija un conjunto de datos con datos espaciales de SQL Server** , haga clic en **Agregar un nuevo conjunto de datos con datos espaciales de SQL Server**y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-189">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="385ba-190">En la página **Elegir una conexión con un origen de datos espaciales de SQL Server** , seleccione un origen de datos existente o vaya al servidor de informes y seleccione un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="385ba-190">On the **Choose a connection to a SQL Server spatial data source** page, select an existing data source or browse to the report server and select a data source.</span></span>  
  
6.  <span data-ttu-id="385ba-191">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-191">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="385ba-192">En la página diseñar una consulta, haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="385ba-192">On the Design a Query page, click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="385ba-193">Pegue el texto siguiente en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="385ba-193">Paste the following text in the query pane:</span></span>  
  
    ```  
    Select 114 as StoreKey, 'Contoso Albany Store' as StoreName, 1125 as SellingArea, 'Albany' as City, 'Albany' as County,   
     CAST(1000000 as money) as Sales, CAST('POINT(-73.7472924218681 42.6564617079878)' as geography) AS SpatialLocation  
    UNION ALL SELECT 115 AS StoreKey, 'Contoso New York No.1 Store' AS  StoreName, 500 as SellingArea, 'New York' AS City, 'New York City' as County,  
     CAST('2000000' as money) as Sales, CAST('POINT(-73.9922069374483 40.7549638237402)' as geography) AS SpatialLocation  
    UNION ALL Select 116 as StoreKey, 'Contoso Rochester No.1 Store' as StoreName, 462 as SellingArea, 'Rochester' as City,  'Monroe' as County,    
     CAST(3000000 as money) as Sales, CAST('POINT(-77.624041566786 43.1547066024338)' as geography)  AS SpatialLocation  
    UNION ALL Select 117 as StoreKey, 'Contoso New York No.2 Store' as StoreName, 700 as SellingArea, 'New York' as City,'New York City' as County,    
      CAST(4000000 as money) as Sales, CAST('POINT(-73.9712488 40.7830603)' as geography) AS SpatialLocation  
    UNION ALL Select 118 as StoreKey, 'Contoso Syracuse Store' as StoreName, 680 as SellingArea, 'Syracuse' as City, 'Onondaga' as County,  
     CAST(5000000 as money) as Sales, CAST('POINT(-76.1349120532546 43.0610223535974)' as geography) AS SpatialLocation  
    UNION ALL Select 120 as StoreKey, 'Contoso Plattsburgh Store' as StoreName, 560 as SellingArea, 'Plattsburgh' as City,  'Clinton' as County,  
     CAST(6000000 as money) as Sales, CAST('POINT(-73.4728622833178 44.7028831413324)' as geography) AS SpatialLocation  
    UNION ALL Select 121 as StoreKey, 'Contoso Brooklyn Store' as StoreName, 1125 as SellingArea, 'Brooklyn' as City, 'New York City' as County,  
     CAST(7000000 as money) as Sales, CAST('POINT (-73.9638533447143 40.6785123489351)' as geography) AS SpatialLocation  
    UNION ALL Select 122 as StoreKey, 'Contoso Oswego Store' as StoreName, 500 as SellingArea, 'Oswego' as City, 'Oswego' as County,    
     CAST(8000000 as money) as Sales, CAST('POINT(-76.4602850815536 43.4353224527794)' as geography) AS SpatialLocation  
    UNION ALL Select 123 as StoreKey, 'Contoso Ithaca Store' as StoreName, 460 as SellingArea, 'Ithaca' as City, 'Tompkins' as County,  
     CAST(9000000 as money) as Sales, CAST('POINT(-76.5001866085881 42.4310489934743)' as geography) AS SpatialLocation  
    UNION ALL Select 124 as StoreKey, 'Contoso Rochester No.2 Store' as StoreName, 700 as SellingArea, 'Rochester' as City, 'Monroe' as County,    
     CAST(100000 as money) as Sales, CAST('POINT(-77.6240415667866 43.1547066024338)' as geography) AS SpatialLocation  
    UNION ALL Select 125 as StoreKey, 'Contoso Queens Store' as StoreName, 700 as SellingArea,'Queens' as City, 'New York City' as County,  
     CAST(500000 as money) as Sales, CAST('POINT(-73.7930979029883 40.7152781765927)' as geography) AS SpatialLocation  
    UNION ALL Select 126 as StoreKey, 'Contoso Elmira Store' as StoreName, 680 as SellingArea, 'Elmira' as City, 'Chemung' as County,  
     CAST(800000 as money) as Sales, CAST('POINT(-76.7397414783301 42.0736492742663)' as geography) AS SpatialLocation  
    UNION ALL Select 127 as StoreKey, 'Contoso Poestenkill Store' as StoreName, 455 as SellingArea, 'Poestenkill' as City, 'Rensselaer' as County,    
    CAST(1500000 as money) as Sales, CAST('POINT(-73.5626737425063 42.6940551238618)' as geography) AS SpatialLocation  
    ```  
  
9. <span data-ttu-id="385ba-194">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="385ba-194">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="385ba-195">El conjunto de resultados muestra siete columnas: StoreKey, StoreName, SellingArea, City, County, Sales y SpatialLocation.</span><span class="sxs-lookup"><span data-stu-id="385ba-195">The result set displays seven columns: StoreKey, StoreName, SellingArea, City, County, Sales, and SpatialLocation.</span></span> <span data-ttu-id="385ba-196">Estos datos representan un conjunto de almacenes del Estado de Nueva York que venden bienes de consumo.</span><span class="sxs-lookup"><span data-stu-id="385ba-196">This data represents a set of stores in New York State that sell consumer goods.</span></span> <span data-ttu-id="385ba-197">Cada fila del conjunto de resultados contiene un identificador de almacén, un nombre de almacén, el área disponible para la exhibición del producto, la ciudad y el condado donde se encuentra el almacén, el total de ventas y la ubicación espacial en longitud y latitud.</span><span class="sxs-lookup"><span data-stu-id="385ba-197">Each row in the result set contains a store identifier, store name, the area available for product display, the city and county where the store is located, the sales total, and the spatial location in longitude and latitude.</span></span> <span data-ttu-id="385ba-198">El área de exhibición va de 455 a 1.125 pies cuadrados.</span><span class="sxs-lookup"><span data-stu-id="385ba-198">The display area ranges from 455 square feet to 1125 square feet.</span></span>  
  
10. <span data-ttu-id="385ba-199">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-199">Click **Next**.</span></span>  
  
     <span data-ttu-id="385ba-200">Se ha creado el conjunto de datos de informe denominado DataSet1.</span><span class="sxs-lookup"><span data-stu-id="385ba-200">The report dataset named DataSet1 is created for you.</span></span> <span data-ttu-id="385ba-201">Después de completar el asistente, puede usar el panel Datos de informe para ver esta colección de campos.</span><span class="sxs-lookup"><span data-stu-id="385ba-201">After you complete the wizard, you can use the Report Data to its field collection.</span></span>  
  
11. <span data-ttu-id="385ba-202">En la página **elegir opciones de datos espaciales y vista de mapa** , compruebe que el **campo espacial** es `SpatialLocation` y que el **tipo de capa** es **punto**.</span><span class="sxs-lookup"><span data-stu-id="385ba-202">On the **Choose a spatial data and map view options** page, verify that the **Spatial field** is `SpatialLocation` and that the **Layer type** is **Point**.</span></span> <span data-ttu-id="385ba-203">Acepte los demás valores predeterminados de esta página.</span><span class="sxs-lookup"><span data-stu-id="385ba-203">Accept the other defaults on this page.</span></span>  
  
     <span data-ttu-id="385ba-204">La vista de mapa muestra círculos que marcan la ubicación de cada almacén.</span><span class="sxs-lookup"><span data-stu-id="385ba-204">The map view displays circles that mark the location of each store.</span></span>  
  
12. <span data-ttu-id="385ba-205">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-205">Click **Next**.</span></span>  
  
13. <span data-ttu-id="385ba-206">Especifique un tipo de mapa que muestre los marcadores que varían según los datos analíticos.</span><span class="sxs-lookup"><span data-stu-id="385ba-206">Specify a map type that displays markers that vary by analytic data.</span></span> <span data-ttu-id="385ba-207">En la página Elegir visualización de mapa, haga clic en **Mapa de marcadores analítico**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-207">On the Choose map visualization page, click **Analytical Marker Map**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="385ba-208">En la página **Elegir el conjunto de datos analíticos** , haga clic en DataSet1.</span><span class="sxs-lookup"><span data-stu-id="385ba-208">On the **Choose the analytical dataset** page, click DataSet1.</span></span> <span data-ttu-id="385ba-209">Este conjunto de datos contiene datos analíticos y datos espaciales que se mostrarán en la nueva capa de punto.</span><span class="sxs-lookup"><span data-stu-id="385ba-209">This dataset contains both analytical data and spatial data that will be displayed on the new point layer.</span></span>  
  
15. <span data-ttu-id="385ba-210">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-210">Click **Next**.</span></span>  
  
16. <span data-ttu-id="385ba-211">En la página **Elegir tema de color y visualización de datos** , desactive la opción **Usar colores de marcador para visualizar datos** y después seleccione la opción **Usar tipos de marcador para visualizar datos**.</span><span class="sxs-lookup"><span data-stu-id="385ba-211">On the **Choose color theme and data visualization** page, clear the **Use marker colors to visualize data** option, and then select the option **Use marker types to visualize data**.</span></span>  
  
17. <span data-ttu-id="385ba-212">En **Campo de datos**, seleccione `[Sum(SellingArea)]` para variar los tipos de marcador de acuerdo con el tamaño del área que un almacén separa para mostrar productos.</span><span class="sxs-lookup"><span data-stu-id="385ba-212">In **Data field**, select `[Sum(SellingArea)]` to vary marker types by the size of the area a store sets aside to display the products.</span></span>  
  
18. <span data-ttu-id="385ba-213">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="385ba-213">Click **Finish**.</span></span>  
  
     <span data-ttu-id="385ba-214">La capa de mapa se agrega al informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-214">The map layer is added to the report.</span></span> <span data-ttu-id="385ba-215">La leyenda muestra los tipos de marcador según los valores de SellingArea.</span><span class="sxs-lookup"><span data-stu-id="385ba-215">The legend displays marker types based on SellingArea values.</span></span>  
  
     <span data-ttu-id="385ba-216">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-216">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="385ba-217">El panel **Capa de mapa** muestra una nueva capa, PointLayer1, con el tipo de origen de datos espaciales **DataRegion**.</span><span class="sxs-lookup"><span data-stu-id="385ba-217">The **Map Layer** pane displays a new layer, PointLayer1, with spatial data source type **DataRegion**.</span></span>  
  
19. <span data-ttu-id="385ba-218">Agregue un título a la leyenda.</span><span class="sxs-lookup"><span data-stu-id="385ba-218">Add a legend title.</span></span> <span data-ttu-id="385ba-219">Haga clic con el botón secundario en el título de la leyenda y, a continuación, haga clic en **Propiedades del título de la leyenda**.</span><span class="sxs-lookup"><span data-stu-id="385ba-219">Right-click the legend title, and then click **Legend Title Properties**.</span></span>  
  
20. <span data-ttu-id="385ba-220">Elimine el título y escriba **Área de presentación (pies cuadrados)**.</span><span class="sxs-lookup"><span data-stu-id="385ba-220">Delete the title, and type **Display Area (Square Feet)**.</span></span>  
  
21. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
22. <span data-ttu-id="385ba-221">Vea los valores predeterminados que fueron establecidos por el asistente.</span><span class="sxs-lookup"><span data-stu-id="385ba-221">View the default values that were set by the wizard.</span></span> <span data-ttu-id="385ba-222">En el panel **Capas de mapa**, haga clic con el botón secundario en la capa de punto y, a continuación, haga clic en **Regla de tipo de marcador**.</span><span class="sxs-lookup"><span data-stu-id="385ba-222">In the **Map Layers Pane**, right-click the point layer, and then click **Marker Type Rule**.</span></span>  
  
     <span data-ttu-id="385ba-223">En la pestaña **General** , los marcadores se enumeran en el orden en el que aparecen en la leyenda.</span><span class="sxs-lookup"><span data-stu-id="385ba-223">On the **General** tab, the markers are listed in the order in which they appear in the legend.</span></span> <span data-ttu-id="385ba-224">En la pestaña **Distribución** , el número de subrango es 5.</span><span class="sxs-lookup"><span data-stu-id="385ba-224">On the **Distribution** tab, the number of subranges is 5.</span></span> <span data-ttu-id="385ba-225">En la pestaña **Leyenda** , el texto de la leyenda se establece para mostrar el valor de inicio y el valor final de cada rango.</span><span class="sxs-lookup"><span data-stu-id="385ba-225">On the **Legend** tab, the legend text is set to display the start and end value in each range.</span></span>  
  
23. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
24. <span data-ttu-id="385ba-226">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-226">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-227">El mapa muestra las ubicaciones de los almacenes del Estado de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="385ba-227">The map displays the locations of stores in New York state.</span></span> <span data-ttu-id="385ba-228">El tipo de marcador para cada almacén está basado en el área de presentación.</span><span class="sxs-lookup"><span data-stu-id="385ba-228">The marker type for each store is based on the display area.</span></span> <span data-ttu-id="385ba-229">Se calcularon automáticamente para usted cinco rangos de área de presentación.</span><span class="sxs-lookup"><span data-stu-id="385ba-229">Five ranges of display area were automatically calculated for you.</span></span>  
  
##  <a name="3-add-a-map-line-layer-to-display-a-route"></a><a name="LineLayer"></a><span data-ttu-id="385ba-230">3. agregar una capa de línea de mapa para mostrar una ruta</span><span class="sxs-lookup"><span data-stu-id="385ba-230">3. Add a Map Line Layer to Display a Route</span></span>  
 <span data-ttu-id="385ba-231">Use el Asistente para capas de mapa para agregar una capa de mapa que muestre una ruta entre dos almacenes.</span><span class="sxs-lookup"><span data-stu-id="385ba-231">Use the map layer wizard to add a map layer that displays a route between two stores.</span></span> <span data-ttu-id="385ba-232">En este tutorial, la ruta de acceso se crea a partir de tres ubicaciones de almacén.</span><span class="sxs-lookup"><span data-stu-id="385ba-232">In this tutorial, the path is created from three store locations.</span></span> <span data-ttu-id="385ba-233">En una aplicación empresarial, la ruta podría ser la ruta mejor entre los almacenes.</span><span class="sxs-lookup"><span data-stu-id="385ba-233">In a business application, the path might be the best route between stores.</span></span>  
  
#### <a name="to-add-a-line-layer-to-map"></a><span data-ttu-id="385ba-234">Para agregar una capa de línea al mapa</span><span class="sxs-lookup"><span data-stu-id="385ba-234">To add a line layer to map</span></span>  
  
1.  <span data-ttu-id="385ba-235">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-235">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-236">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-236">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="385ba-237">En la barra de herramientas, haga clic en **Asistente para nueva capa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-237">On the toolbar, click **New layer wizard**.</span></span>  
  
3.  <span data-ttu-id="385ba-238">En la página **Elegir un origen de datos espaciales** , seleccione **Consulta espacial de SQL Server** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-238">On the **Choose a source of spatial data** page, select **SQL Server spatial query** and click **Next**.</span></span>  
  
4.  <span data-ttu-id="385ba-239">En la página **Elija un conjunto de datos con datos espaciales de SQL Server** , haga clic en **Agregar un nuevo conjunto de datos con datos espaciales de SQL Server** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-239">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data** and click **Next**.</span></span>  
  
5.  <span data-ttu-id="385ba-240">En **Elegir una conexión con un origen de datos espaciales de SQL Server**, seleccione DataSource1, el origen de datos que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="385ba-240">On the **Choose a connection to a SQL Server spatial data source**, select DataSource1, the data source that you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="385ba-241">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-241">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="385ba-242">En la página **diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="385ba-242">On the **Design a Query** page, click **Edit as Text**.</span></span> <span data-ttu-id="385ba-243">El diseñador de consultas cambia al modo basado en texto.</span><span class="sxs-lookup"><span data-stu-id="385ba-243">The query designer switches to text-based mode.</span></span>  
  
8.  <span data-ttu-id="385ba-244">Pegue el texto siguiente en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="385ba-244">Paste the following text in the query pane:</span></span>  
  
    ```  
    SELECT N'Path' AS Name, CAST('LINESTRING(  
       -76.5001866085881 42.4310489934743,  
       -76.4602850815536 43.4353224527794,  
       -73.4728622833178 44.7028831413324)' AS geography) as Route  
    ```  
  
9. <span data-ttu-id="385ba-245">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-245">Click **Next**.</span></span>  
  
     <span data-ttu-id="385ba-246">En el mapa aparece una ruta de acceso que conecta tres almacenes.</span><span class="sxs-lookup"><span data-stu-id="385ba-246">A path appears on the map that connects three stores.</span></span>  
  
10. <span data-ttu-id="385ba-247">En la página **Elegir opciones de datos espaciales y vista de mapa** , compruebe que el **Campo espacial** es **Route** y que el **Tipo de capa** es **Línea**.</span><span class="sxs-lookup"><span data-stu-id="385ba-247">On the **Choose spatial data and map view options** page, verify that the **Spatial field** is **Route** and that the **Layer type** is **Line**.</span></span> <span data-ttu-id="385ba-248">Acepte los otros valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="385ba-248">Accept the other defaults.</span></span>  
  
     <span data-ttu-id="385ba-249">La vista de mapa muestra una ruta desde un almacén de la parte septentrional del Estado de Nueva York a otro de la parte meridional.</span><span class="sxs-lookup"><span data-stu-id="385ba-249">The map view displays a path from a store in the northern part of New York state to a store in the southern part of New York state.</span></span>  
  
11. <span data-ttu-id="385ba-250">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ba-250">Click **Next**.</span></span>  
  
12. <span data-ttu-id="385ba-251">En la página **Elegir visualización de mapa** , haga clic en **Mapa de líneas básico**y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="385ba-251">On the **Choose map visualization** page, click **Basic Line Map**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="385ba-252">En **Elegir tema de color y visualización de datos**, seleccione la opción **Mapa de un color**.</span><span class="sxs-lookup"><span data-stu-id="385ba-252">On the **Choose color theme and data visualization**, select the option **Single color map**.</span></span> <span data-ttu-id="385ba-253">La ruta aparece en un color basado en el tema seleccionado.</span><span class="sxs-lookup"><span data-stu-id="385ba-253">The path appears as a single color based on the selected theme.</span></span>  
  
14. <span data-ttu-id="385ba-254">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="385ba-254">Click **Finish**.</span></span>  
  
 <span data-ttu-id="385ba-255">El mapa muestra una nueva capa de línea con el tipo de origen de datos espaciales **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="385ba-255">The map displays a new line layer with spatial data source type **DataSet**.</span></span> <span data-ttu-id="385ba-256">En este ejemplo, los datos espaciales proceden de un conjunto de datos, pero ningún dato analítico se asocia a la línea.</span><span class="sxs-lookup"><span data-stu-id="385ba-256">In this example, the spatial data comes from a dataset but no analytical data is associated with the line.</span></span>  
  
##  <a name="4-add-a-bing-maps-tile-background"></a><a name="TileLayer"></a><span data-ttu-id="385ba-257">4. agregar un fondo de mosaico de Bing Maps</span><span class="sxs-lookup"><span data-stu-id="385ba-257">4. Add a Bing Maps Tile Background</span></span>  
 <span data-ttu-id="385ba-258">Agregue una capa de mapa que muestre un fondo de mosaico de Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="385ba-258">Add a map layer that displays a Bing Maps tile background.</span></span>  
  
#### <a name="to-add-a-virtual-earth-tile-background"></a><span data-ttu-id="385ba-259">Para agregar un fondo de mosaico Virtual Earth</span><span class="sxs-lookup"><span data-stu-id="385ba-259">To add a Virtual Earth tile background</span></span>  
  
1.  <span data-ttu-id="385ba-260">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-260">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-261">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-261">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="385ba-262">En la barra de herramientas, haga clic en **Agregar capa**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span><span class="sxs-lookup"><span data-stu-id="385ba-262">On the toolbar, click **Add Layer**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span></span>  
  
3.  <span data-ttu-id="385ba-263">En la lista desplegable, haga clic en **Capa de mosaico**.</span><span class="sxs-lookup"><span data-stu-id="385ba-263">From the drop-down list, click **Tile Layer**.</span></span>  
  
     <span data-ttu-id="385ba-264">La última capa del panel **Capa de mapa** es TileLayer1.</span><span class="sxs-lookup"><span data-stu-id="385ba-264">The last layer in the **Map Layer** pane is TileLayer1.</span></span> <span data-ttu-id="385ba-265">De forma predeterminada, la capa de mosaico muestra el estilo de mapa de carreteras.</span><span class="sxs-lookup"><span data-stu-id="385ba-265">By default, the tile layer displays the road map style.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="385ba-266">En el asistente, también puede agregar una capa de mosaico en la página **Elegir opciones de datos espaciales y vista de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-266">In the wizard, you can also add a tile layer on the **Choose spatial data and map view options** page.</span></span> <span data-ttu-id="385ba-267">Para ello, seleccione **Agregar un fondo de Bing Maps a esta vista de mapa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-267">To do this, select **Add a Bing Maps background for this map view**.</span></span> <span data-ttu-id="385ba-268">En un informe representado, el fondo de mosaico muestra mosaicos de Bing Maps en el centro de la ventanilla del mapa actual y en el nivel de zoom.</span><span class="sxs-lookup"><span data-stu-id="385ba-268">In a rendered report, the tile background displays Bing Maps tiles for the current map viewport center and zoom level.</span></span>  
  
4.  <span data-ttu-id="385ba-269">Haga clic en la flecha abajo en TileLayer1 y, a continuación, haga clic en **Propiedades del mosaico**.</span><span class="sxs-lookup"><span data-stu-id="385ba-269">Click the down arrow on TileLayer1, and then click **Tile Properties**.</span></span>  
  
5.  <span data-ttu-id="385ba-270">En **Tipo**, seleccione **Aéreo**.</span><span class="sxs-lookup"><span data-stu-id="385ba-270">In **Type**, select **Aerial**.</span></span> <span data-ttu-id="385ba-271">La vista aérea no contiene texto.</span><span class="sxs-lookup"><span data-stu-id="385ba-271">The aerial view does not contain text.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="5-make-a-layer-transparent"></a><a name="Transparent"></a><span data-ttu-id="385ba-272">5. hacer una capa transparente</span><span class="sxs-lookup"><span data-stu-id="385ba-272">5. Make a Layer Transparent</span></span>  
 <span data-ttu-id="385ba-273">Para permitir que los elementos de una capa se muestren a través de otra capa, puede ajustar el orden de las capas y la transparencia de cada una para obtener el efecto que desea.</span><span class="sxs-lookup"><span data-stu-id="385ba-273">To let the items on one layer show through another layer, you can adjust the order of layers and the transparency of each layer to get the effect that you want.</span></span>  
  
#### <a name="to-set-the-transparency-of-a-layer"></a><span data-ttu-id="385ba-274">Para establecer la transparencia de una capa</span><span class="sxs-lookup"><span data-stu-id="385ba-274">To set the transparency of a layer</span></span>  
  
1.  <span data-ttu-id="385ba-275">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-275">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-276">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-276">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="385ba-277">Haga clic en la flecha abajo en PolygonLayer1 y, a continuación, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-277">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="385ba-278">Se abre el cuadro de diálogo **Propiedades de capa de polígono de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-278">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="385ba-279">Haga clic en **Visibilidad**.</span><span class="sxs-lookup"><span data-stu-id="385ba-279">Click **Visibility**.</span></span>  
  
5.  <span data-ttu-id="385ba-280">En **Transparencia (%)**, escriba **30**.</span><span class="sxs-lookup"><span data-stu-id="385ba-280">In **Transparency (%)**, type **30**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="385ba-281">La superficie de diseño muestra los condados como semitransparentes.</span><span class="sxs-lookup"><span data-stu-id="385ba-281">The design surface displays the counties as semi-transparent.</span></span>  
  
##  <a name="6-vary-county-color-based-on-sales"></a><a name="Vary"></a><span data-ttu-id="385ba-282">6. variar el color del condado en función de las ventas</span><span class="sxs-lookup"><span data-stu-id="385ba-282">6. Vary County Color Based on Sales</span></span>  
 <span data-ttu-id="385ba-283">Cada condado de la capa de polígono tiene un color diferente porque el procesador de informes asigna automáticamente un valor de color de la paleta de colores en función del tema que eligió en la última página del Asistente para mapas.</span><span class="sxs-lookup"><span data-stu-id="385ba-283">Each county on the polygon layer has a different color because the report processor automatically assigns a color value from the color palette based on the theme that you chose on the last page of the map wizard.</span></span>  
  
 <span data-ttu-id="385ba-284">En los pasos siguientes, especifique una regla de color para asociar colores concretos a un rango de valores de almacén para cada condado.</span><span class="sxs-lookup"><span data-stu-id="385ba-284">In the following steps, specify a color rule to associate specific colors with a range of store sales for each county.</span></span> <span data-ttu-id="385ba-285">Los colores rojo, verde y amarillo indican unas ventas anuales altas, medias o bajas relativas.</span><span class="sxs-lookup"><span data-stu-id="385ba-285">The colors red-yellow-green indicate relative high-middle-low sales.</span></span> <span data-ttu-id="385ba-286">Dé formato a la escala de colores para mostrar la moneda.</span><span class="sxs-lookup"><span data-stu-id="385ba-286">Format the color scale to show currency.</span></span> <span data-ttu-id="385ba-287">Muestre los rangos de ventas anuales en una nueva leyenda.</span><span class="sxs-lookup"><span data-stu-id="385ba-287">Display the annual sales ranges in a new legend.</span></span> <span data-ttu-id="385ba-288">En los condados que no contengan almacenes, no use ningún color para mostrar que no hay ningún dato asociado.</span><span class="sxs-lookup"><span data-stu-id="385ba-288">For counties that do not contain stores, use no color to show that there is no associated data.</span></span>  
  
###  <a name="6a-build-a-relationship-between-spatial-and-analytical-data"></a><a name="Relationship"></a><span data-ttu-id="385ba-289">6.</span><span class="sxs-lookup"><span data-stu-id="385ba-289">6a.</span></span> <span data-ttu-id="385ba-290">Compilar una relación entre los datos espaciales y los datos analíticos</span><span class="sxs-lookup"><span data-stu-id="385ba-290">Build a Relationship between Spatial and Analytical Data</span></span>  
 <span data-ttu-id="385ba-291">Para variar las formas del condado por el color según los datos analíticos, debe asociar primero los datos analíticos a los datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="385ba-291">To vary the county shapes by color based on analytical data, you first must associate the analytical data with the spatial data.</span></span> <span data-ttu-id="385ba-292">En este tutorial, utilizará el nombre del condado para la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="385ba-292">In this tutorial, you will use the county name to match on.</span></span>  
  
##### <a name="to-build-a-relationship-between-spatial-data-and-analytical-data"></a><span data-ttu-id="385ba-293">Para generar una relación entre los datos espaciales y los datos analíticos</span><span class="sxs-lookup"><span data-stu-id="385ba-293">To build a relationship between spatial data and analytical data</span></span>  
  
1.  <span data-ttu-id="385ba-294">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-294">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-295">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-295">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="385ba-296">Haga clic en la flecha abajo en PolygonLayer1 y, a continuación, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-296">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="385ba-297">Se abre el cuadro de diálogo **Propiedades de capa de polígono de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-297">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="385ba-298">Haga clic en **Datos analíticos**.</span><span class="sxs-lookup"><span data-stu-id="385ba-298">Click **Analytical data**.</span></span>  
  
5.  <span data-ttu-id="385ba-299">En la lista desplegable, seleccione DataSet1.</span><span class="sxs-lookup"><span data-stu-id="385ba-299">From the drop-down list, select DataSet1.</span></span> <span data-ttu-id="385ba-300">El asistente creó este conjunto de datos cuando se especificó la consulta de datos espaciales para los condados.</span><span class="sxs-lookup"><span data-stu-id="385ba-300">This dataset was created by the wizard when you specified the spatial data query for the counties.</span></span>  
  
6.  <span data-ttu-id="385ba-301">En **Campos en los que establecer coincidencias**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="385ba-301">In **Fields to match on**, click **Add**.</span></span> <span data-ttu-id="385ba-302">Se agrega una nueva fila.</span><span class="sxs-lookup"><span data-stu-id="385ba-302">A new row is added.</span></span>  
  
7.  <span data-ttu-id="385ba-303">En **Desde el conjunto de datos espaciales**, en la lista desplegable, haga clic en COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="385ba-303">In **From spatial dataset**, from the drop-down list, click COUNTYNAME.</span></span>  
  
8.  <span data-ttu-id="385ba-304">En **Desde el conjunto de datos analíticos**, en la lista desplegable, haga clic en [County].</span><span class="sxs-lookup"><span data-stu-id="385ba-304">In **From analytical dataset**, from the drop-down list, click [County].</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="385ba-305">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-305">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-306">Al especificar un campo coincidente del origen de datos espaciales y el conjunto de datos analíticos, el procesador de informes puede agrupar los datos analíticos según los elementos de mapa.</span><span class="sxs-lookup"><span data-stu-id="385ba-306">By specifying a match field from the spatial data source and from the analytical dataset, you enable the report processor to group analytical data based on the map elements.</span></span> <span data-ttu-id="385ba-307">Un elemento de mapa enlazado a datos tiene una coincidencia correcta para los valores que especificó.</span><span class="sxs-lookup"><span data-stu-id="385ba-307">A data-bound map element has a successful match for the values that you specified.</span></span>  
  
 <span data-ttu-id="385ba-308">Cada condado que contiene un almacén tiene un color que está basado en la paleta de colores correspondiente el estilo que eligió en el asistente.</span><span class="sxs-lookup"><span data-stu-id="385ba-308">Each county that contains a store has a color that is based on the color palette for the style that you chose in the wizard.</span></span>  
  
###  <a name="6b-specify-color-rules-for-polygons"></a><a name="ColorRules"></a><span data-ttu-id="385ba-309">6.</span><span class="sxs-lookup"><span data-stu-id="385ba-309">6b.</span></span> <span data-ttu-id="385ba-310">Especificar las reglas de color para polígonos</span><span class="sxs-lookup"><span data-stu-id="385ba-310">Specify Color Rules for Polygons</span></span>  
 <span data-ttu-id="385ba-311">Para crear una regla que varía el color de cada condado basándose en las ventas por almacén, debe especificar los valores de rango, el número de divisiones dentro de ese rango que desea mostrar y los colores que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="385ba-311">To create a rule that varies the color of each county based store sales, you must specify the range values, the number of divisions within that range that you want to display, and the colors to use.</span></span>  
  
##### <a name="to-specify-color-rules-for-all-polygons-that-have-associated-data"></a><span data-ttu-id="385ba-312">Especificar las reglas de color para todos los polígonos que tienen datos asociados</span><span class="sxs-lookup"><span data-stu-id="385ba-312">To specify color rules for all polygons that have associated data</span></span>  
  
1.  <span data-ttu-id="385ba-313">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-313">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-314">Haga clic en la flecha abajo en PolygonLayer1 y, a continuación, haga clic en **Regla de color de polígono**.</span><span class="sxs-lookup"><span data-stu-id="385ba-314">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="385ba-315">El cuadro de diálogo **Propiedades de reglas de color de mapa** se abre.</span><span class="sxs-lookup"><span data-stu-id="385ba-315">The **Map Color Rules Properties** dialog box opens.</span></span> <span data-ttu-id="385ba-316">Observe que la opción de la regla de color **Visualizar datos mediante la paleta de colores** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="385ba-316">Notice that the color rule option **Visualize data by using color palette** is selected.</span></span> <span data-ttu-id="385ba-317">Esta opción se estableció en el asistente.</span><span class="sxs-lookup"><span data-stu-id="385ba-317">This option was set by the wizard.</span></span>  
  
3.  <span data-ttu-id="385ba-318">Seleccione **Visualizar datos mediante los rangos de colores**.</span><span class="sxs-lookup"><span data-stu-id="385ba-318">Select **Visualize data by using color ranges**.</span></span> <span data-ttu-id="385ba-319">La opción de la paleta se reemplaza con las opciones de color inicial, color intermedio y color final.</span><span class="sxs-lookup"><span data-stu-id="385ba-319">The palette option is replaced by start color, middle color, and end color options.</span></span>  
  
4.  <span data-ttu-id="385ba-320">Defina los valores de rango para las ventas de cada condado.</span><span class="sxs-lookup"><span data-stu-id="385ba-320">Define range values for sales per county.</span></span> <span data-ttu-id="385ba-321">En **Campo de datos**, en la lista desplegable, seleccione `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="385ba-321">In **Data field**, from the drop-down list, select `[Sum(Sales)]`.</span></span>  
  
5.  <span data-ttu-id="385ba-322">Para cambiar el formato para mostrar la moneda en millares, cambie la expresión a la siguiente: `=Sum(Fields!Sales.Value)/1000`</span><span class="sxs-lookup"><span data-stu-id="385ba-322">To change the format to display currency in thousands, change the expression to the following: `=Sum(Fields!Sales.Value)/1000`</span></span>  
  
6.  <span data-ttu-id="385ba-323">Cambie **Color inicial** a **Rojo**.</span><span class="sxs-lookup"><span data-stu-id="385ba-323">Change **Start color** to **Red**.</span></span>  
  
7.  <span data-ttu-id="385ba-324">Cambie **Color final** a **Verde**.</span><span class="sxs-lookup"><span data-stu-id="385ba-324">Change **End color** to **Green**.</span></span>  
  
     <span data-ttu-id="385ba-325">**Rojo** representa valores de ventas bajos, **Amarillo** representa valores de ventas intermedios y **Verde** representa valores de ventas altos.</span><span class="sxs-lookup"><span data-stu-id="385ba-325">**Red** represents low sales values, **Yellow** represents middle sales values, and **Green** represents high sales values.</span></span> <span data-ttu-id="385ba-326">El procesador de informes calcula un rango de colores según estos valores y las opciones que elija en la página **Distribución** .</span><span class="sxs-lookup"><span data-stu-id="385ba-326">The report processor calculates a range of colors based on these values and the options that you choose on the **Distribution** page.</span></span>  
  
8.  <span data-ttu-id="385ba-327">Haga clic en **Distribución**.</span><span class="sxs-lookup"><span data-stu-id="385ba-327">Click **Distribution**.</span></span>  
  
9. <span data-ttu-id="385ba-328">Compruebe que el tipo de distribución es **Óptimo**.</span><span class="sxs-lookup"><span data-stu-id="385ba-328">Verify that the distribution type is **Optimal**.</span></span> <span data-ttu-id="385ba-329">Para la expresión del paso 5, la distribución óptima divide los valores en subrangos que equilibren el número de elementos y la amplitud de cada rango.</span><span class="sxs-lookup"><span data-stu-id="385ba-329">For the expression from step 5, optimal distribution divides the values into subranges that balance the number of items in each range and the span for each range.</span></span>  
  
10. <span data-ttu-id="385ba-330">Acepte los valores predeterminados de las demás opciones de esta página.</span><span class="sxs-lookup"><span data-stu-id="385ba-330">Accept the default values for other options on this page.</span></span> <span data-ttu-id="385ba-331">Al seleccionar el tipo de distribución óptimo, el número de subrangos se calcula cuando se ejecuta el informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-331">When you select the optimal distribution type, the number of subranges are calculated when the report runs.</span></span>  
  
11. <span data-ttu-id="385ba-332">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="385ba-332">Click **Legend**.</span></span>  
  
12. <span data-ttu-id="385ba-333">En **Opciones de escala de colores**, compruebe que la opción **Mostrar en escala de colores** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="385ba-333">In **Color scale options**, verify that **Show in color scale** is selected.</span></span>  
  
13. <span data-ttu-id="385ba-334">En **Mostrar en esta leyenda**, en la lista desplegable, seleccione la línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="385ba-334">In **Show in this legend**, from the drop-down list, select the blank line.</span></span> <span data-ttu-id="385ba-335">Por ahora, mostrará los rangos de colores solo en la escala de colores.</span><span class="sxs-lookup"><span data-stu-id="385ba-335">For now, you will show the color ranges only in the color scale.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="385ba-336">La escala de colores muestra cinco colores: rojo, naranja, amarillo, verde amarillento y verde.</span><span class="sxs-lookup"><span data-stu-id="385ba-336">The color scale displays five colors: red, orange, yellow, yellow green, and green.</span></span> <span data-ttu-id="385ba-337">Cada color representa un rango de ventas que se calcula automáticamente de acuerdo con las ventas por condado.</span><span class="sxs-lookup"><span data-stu-id="385ba-337">Each color represents a sales range that is automatically calculated based on the sales by county.</span></span>  
  
###  <a name="6c-format-the-data-in-the-color-scale-as-currency"></a><a name="ColorScale"></a><span data-ttu-id="385ba-338">6C.</span><span class="sxs-lookup"><span data-stu-id="385ba-338">6c.</span></span> <span data-ttu-id="385ba-339">Dar formato a los datos en la escala de color como moneda</span><span class="sxs-lookup"><span data-stu-id="385ba-339">Format the Data in the Color Scale as Currency</span></span>  
 <span data-ttu-id="385ba-340">De forma predeterminada, los datos tienen un formato general.</span><span class="sxs-lookup"><span data-stu-id="385ba-340">By default, data has a general format.</span></span> <span data-ttu-id="385ba-341">Puede aplicar formatos personalizados.</span><span class="sxs-lookup"><span data-stu-id="385ba-341">You can apply custom formats.</span></span>  
  
##### <a name="to-set-the-format-for-the-color-scale"></a><span data-ttu-id="385ba-342">Establecer el formato de la escala de colores</span><span class="sxs-lookup"><span data-stu-id="385ba-342">To set the format for the color scale</span></span>  
  
1.  <span data-ttu-id="385ba-343">Haga clic con el botón secundario en la escala de colores y, a continuación, haga clic en **Propiedades de escala de colores**.</span><span class="sxs-lookup"><span data-stu-id="385ba-343">Right-click the color scale, and then click **Color Scale Properties**.</span></span>  
  
2.  <span data-ttu-id="385ba-344">Haga clic en **Número**.</span><span class="sxs-lookup"><span data-stu-id="385ba-344">Click **Number**.</span></span>  
  
3.  <span data-ttu-id="385ba-345">En **Categoría**, haga clic en **Moneda**.</span><span class="sxs-lookup"><span data-stu-id="385ba-345">In **Category**, click **Currency**.</span></span>  
  
4.  <span data-ttu-id="385ba-346">En **Posiciones decimales**, escriba **0**.</span><span class="sxs-lookup"><span data-stu-id="385ba-346">In **Decimal places**, type **0**.</span></span> <span data-ttu-id="385ba-347">Este formato no especifica ninguna posición decimal para la moneda.</span><span class="sxs-lookup"><span data-stu-id="385ba-347">This format specifies no decimal places for currency.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="385ba-348">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-348">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-349">La escala de colores muestra las ventas anuales en el formato de moneda para cada rango.</span><span class="sxs-lookup"><span data-stu-id="385ba-349">The color scale displays annual sales in currency format for each range.</span></span>  
  
###  <a name="6d-create-a-new-legend"></a><a name="NewLegend"></a><span data-ttu-id="385ba-350">6D.</span><span class="sxs-lookup"><span data-stu-id="385ba-350">6d.</span></span> <span data-ttu-id="385ba-351">Crear una nueva leyenda</span><span class="sxs-lookup"><span data-stu-id="385ba-351">Create a New Legend</span></span>  
 <span data-ttu-id="385ba-352">De forma predeterminada, todas las reglas se muestran en la primera leyenda.</span><span class="sxs-lookup"><span data-stu-id="385ba-352">By default, all rules display in the first legend.</span></span> <span data-ttu-id="385ba-353">Para mejorar la presentación de un mapa, puede agregar leyendas.</span><span class="sxs-lookup"><span data-stu-id="385ba-353">To improve the display for a map, you can add legends.</span></span>  
  
 <span data-ttu-id="385ba-354">Cambiar la presentación predeterminada requiere dos pasos: crear una nueva leyenda y, a continuación, asociar los resultados de la regla para una capa de mapa con la nueva leyenda.</span><span class="sxs-lookup"><span data-stu-id="385ba-354">To change the default display, there are two steps: create a new legend and then associate the rule results for a map layer with the new legend.</span></span>  
  
##### <a name="to-create-a-new-legend"></a><span data-ttu-id="385ba-355">Crear una nueva leyenda</span><span class="sxs-lookup"><span data-stu-id="385ba-355">To create a new legend</span></span>  
  
1.  <span data-ttu-id="385ba-356">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-356">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-357">Haga clic con el botón secundario en el mapa fuera de la ventanilla y, a continuación, haga clic en **Agregar leyenda**.</span><span class="sxs-lookup"><span data-stu-id="385ba-357">Right-click the map outside the viewport, and then click **Add Legend**.</span></span> <span data-ttu-id="385ba-358">Una leyenda nueva se agrega al mapa en una ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="385ba-358">A new legend is added to the map at a default location.</span></span>  
  
3.  <span data-ttu-id="385ba-359">Haga clic con el botón secundario en la leyenda y, después, haga clic en **Propiedades de la leyenda**.</span><span class="sxs-lookup"><span data-stu-id="385ba-359">Right-click the legend, and then click **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="385ba-360">En **Opciones de posición**, haga clic en la ubicación que especifica dónde desea que la leyenda aparezca en relación con la ventanilla.</span><span class="sxs-lookup"><span data-stu-id="385ba-360">In **Position options**, click the location that specifies where you want the legend to appear relative to the viewport.</span></span> <span data-ttu-id="385ba-361">El mapa de la superficie del diseño cambia para mostrar el efecto de las selecciones.</span><span class="sxs-lookup"><span data-stu-id="385ba-361">The map on the design surface changes to show the effect of your selections.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="385ba-362">Haga clic en **Título** en la leyenda para seleccionar el título de la misma.</span><span class="sxs-lookup"><span data-stu-id="385ba-362">Click **Title** on the legend to select the legend title.</span></span>  
  
7.  <span data-ttu-id="385ba-363">Haga clic de nuevo en **Título** para especificar el modo de inserción para el texto.</span><span class="sxs-lookup"><span data-stu-id="385ba-363">Click **Title** again to enter insert mode for the text.</span></span> <span data-ttu-id="385ba-364">Reemplace **Título** por **Ventas (miles)** y, a continuación, haga clic fuera del texto.</span><span class="sxs-lookup"><span data-stu-id="385ba-364">Replace **Title** by **Sales (Thousands)**, and then click outside the text.</span></span>  
  
 <span data-ttu-id="385ba-365">La leyenda se expande para mostrar el título.</span><span class="sxs-lookup"><span data-stu-id="385ba-365">The legend expands to display the title.</span></span>  
  
###  <a name="6e-associate-legend-and-color-rules"></a><a name="Associate"></a><span data-ttu-id="385ba-366">6e.</span><span class="sxs-lookup"><span data-stu-id="385ba-366">6e.</span></span> <span data-ttu-id="385ba-367">Asociar la leyenda y las reglas de color</span><span class="sxs-lookup"><span data-stu-id="385ba-367">Associate Legend and Color Rules</span></span>  
 <span data-ttu-id="385ba-368">Cada leyenda puede mostrar uno o más conjuntos de resultados de la regla.</span><span class="sxs-lookup"><span data-stu-id="385ba-368">Each legend can display one or more sets of rule results.</span></span>  
  
##### <a name="to-associate-a-legend-with-color-rules"></a><span data-ttu-id="385ba-369">Asociar una leyenda a reglas de color</span><span class="sxs-lookup"><span data-stu-id="385ba-369">To associate a legend with color rules</span></span>  
  
1.  <span data-ttu-id="385ba-370">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-370">Double-click the map to display the **Map Layer** pane.</span></span>  
  
2.  <span data-ttu-id="385ba-371">Haga clic en la flecha abajo en PolygonLayer1 y, a continuación, haga clic en **Regla de color de polígono**.</span><span class="sxs-lookup"><span data-stu-id="385ba-371">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="385ba-372">El cuadro de diálogo **Propiedades de reglas de color de mapa** se abre.</span><span class="sxs-lookup"><span data-stu-id="385ba-372">The **Map Color Rules Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="385ba-373">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="385ba-373">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="385ba-374">En **Opciones de escala de colores**, desactive **Mostrar en escala de colores**.</span><span class="sxs-lookup"><span data-stu-id="385ba-374">In **Color scale options**, clear **Show in color scale**.</span></span>  
  
5.  <span data-ttu-id="385ba-375">En **Opciones de leyenda**, en la lista desplegable, seleccione Legend2.</span><span class="sxs-lookup"><span data-stu-id="385ba-375">In **Legend options**, from the drop-down list, select Legend2.</span></span> <span data-ttu-id="385ba-376">Aparece la opción de texto de la leyenda.</span><span class="sxs-lookup"><span data-stu-id="385ba-376">The legend text option appears.</span></span> <span data-ttu-id="385ba-377">De forma predeterminada, se da formato al texto de la leyenda con una cadena de formato [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] general.</span><span class="sxs-lookup"><span data-stu-id="385ba-377">By default, legend text is formatted with a general [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] format string.</span></span> <span data-ttu-id="385ba-378">Los 0 en N0 no especifican dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="385ba-378">The 0 in N0 specifies no decimal digits.</span></span>  
  
6.  <span data-ttu-id="385ba-379">En **texto de leyenda**, use el siguiente formato para especificar la moneda sin dígitos decimales:`#FROMVALUE {C0} - #TOVALUE {C0}`</span><span class="sxs-lookup"><span data-stu-id="385ba-379">In **Legend text**, use the following format to specify currency with no decimal digits: `#FROMVALUE {C0} - #TOVALUE {C0}`</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="385ba-380">En la superficie de diseño, la leyenda muestra los rangos de color con datos de ejemplo con formato de moneda.</span><span class="sxs-lookup"><span data-stu-id="385ba-380">On the design surface, the legend displays the color ranges with sample data formatted as currency.</span></span>  
  
8.  <span data-ttu-id="385ba-381">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-381">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-382">Los condados que tienen asociados almacenes y ventas se muestran e acuerdo con las reglas de color.</span><span class="sxs-lookup"><span data-stu-id="385ba-382">The counties that have associated stores and sales display according to the color rules.</span></span> <span data-ttu-id="385ba-383">Los condados que no tienen ventas tampoco tienen un color.</span><span class="sxs-lookup"><span data-stu-id="385ba-383">Counties that have no sales have no color.</span></span>  
  
###  <a name="6f-change-color-for-counties-with-no-data"></a><a name="NoData"></a><span data-ttu-id="385ba-384">6F.</span><span class="sxs-lookup"><span data-stu-id="385ba-384">6f.</span></span> <span data-ttu-id="385ba-385">Cambiar el color en los condados sin datos</span><span class="sxs-lookup"><span data-stu-id="385ba-385">Change Color for Counties with No Data</span></span>  
 <span data-ttu-id="385ba-386">Puede configurar las opciones de presentación predeterminadas para todos los elementos de mapa de una capa.</span><span class="sxs-lookup"><span data-stu-id="385ba-386">You can set the default display options for all map elements on a layer.</span></span> <span data-ttu-id="385ba-387">Las reglas de color tienen prioridad sobre estas opciones de presentación.</span><span class="sxs-lookup"><span data-stu-id="385ba-387">Color rules take precedence over these display options.</span></span>  
  
##### <a name="to-set-the-display-properties-for-all-elements-on-a-layer"></a><span data-ttu-id="385ba-388">Para establecer las propiedades de presentación de todos los elementos de una capa</span><span class="sxs-lookup"><span data-stu-id="385ba-388">To set the display properties for all elements on a layer</span></span>  
  
1.  <span data-ttu-id="385ba-389">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-389">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-390">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-390">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="385ba-391">Haga clic en la flecha abajo en PolygonLayer1 y, a continuación, haga clic en **Propiedades del polígono**.</span><span class="sxs-lookup"><span data-stu-id="385ba-391">Click the down arrow on PolygonLayer1, and then click **Polygon Properties**.</span></span> <span data-ttu-id="385ba-392">El cuadro de diálogo **Propiedades de polígono de mapa** se abre.</span><span class="sxs-lookup"><span data-stu-id="385ba-392">The **Map Polygon Properties** dialog box opens.</span></span> <span data-ttu-id="385ba-393">Las opciones de presentación configuradas en este cuadro de diálogo se aplican a todos los polígonos de la capa antes de que se apliquen las opciones de presentación basadas en reglas.</span><span class="sxs-lookup"><span data-stu-id="385ba-393">Display options set in this dialog box apply to all polygons on the layer before rule-based display options are applied.</span></span>  
  
4.  <span data-ttu-id="385ba-394">Haga clic en **Relleno**.</span><span class="sxs-lookup"><span data-stu-id="385ba-394">Click **Fill**.</span></span>  
  
5.  <span data-ttu-id="385ba-395">Compruebe que el estilo de relleno es **Sólido.**</span><span class="sxs-lookup"><span data-stu-id="385ba-395">Verify that the fill style is **Solid.**</span></span> <span data-ttu-id="385ba-396">Los degradados y patrones se aplican a todos los colores.</span><span class="sxs-lookup"><span data-stu-id="385ba-396">Gradients and patterns apply to all colors.</span></span>  
  
6.  <span data-ttu-id="385ba-397">En **Color**, haga clic en la flecha abajo y, a continuación, haga clic en **Azul acero claro**.</span><span class="sxs-lookup"><span data-stu-id="385ba-397">In **Color**, click the down arrow, and then click **Light Steel Blue**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="385ba-398">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-398">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-399">Los condados que no tienen datos asociados se presentan como azul.</span><span class="sxs-lookup"><span data-stu-id="385ba-399">Counties that have no associated data display as blue.</span></span> <span data-ttu-id="385ba-400">Solo los condados que tienen datos analíticos asociados aparecen en los colores **Rojo** a **Verde** de las reglas de color que especificó.</span><span class="sxs-lookup"><span data-stu-id="385ba-400">Only counties that have associated analytical data appear in the **Red** through **Green** colors from the color rules that you specified.</span></span>  
  
##  <a name="7-add-a-custom-point"></a><a name="CustomPoint"></a><span data-ttu-id="385ba-401">7. agregar un punto personalizado</span><span class="sxs-lookup"><span data-stu-id="385ba-401">7. Add a Custom Point</span></span>  
 <span data-ttu-id="385ba-402">Para representar un nuevo almacén que no se ha generado todavía, especifique un punto y utilice el tipo de marcador **Pin** .</span><span class="sxs-lookup"><span data-stu-id="385ba-402">To represent a new store that has not yet been built, specify a point and use the **PushPin** marker type.</span></span>  
  
#### <a name="to-add-a-custom-point"></a><span data-ttu-id="385ba-403">Para agregar un punto personalizado</span><span class="sxs-lookup"><span data-stu-id="385ba-403">To add a custom point</span></span>  
  
1.  <span data-ttu-id="385ba-404">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-404">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-405">Haga doble clic en el mapa para mostrar el panel **Capa de mapa** .</span><span class="sxs-lookup"><span data-stu-id="385ba-405">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="385ba-406">En la barra de herramientas, haga clic en **Agregar capa**y, a continuación, haga clic en **Capa de punto**.</span><span class="sxs-lookup"><span data-stu-id="385ba-406">On the toolbar, click **Add Layer**, and then click **Point Layer**.</span></span>  
  
     <span data-ttu-id="385ba-407">Una nueva capa de punto se agrega al mapa.</span><span class="sxs-lookup"><span data-stu-id="385ba-407">A new point layer is added to the map.</span></span> <span data-ttu-id="385ba-408">De forma predeterminada, la capa de punto tiene el tipo de datos espaciales **Incrustado**.</span><span class="sxs-lookup"><span data-stu-id="385ba-408">By default, the point layer has spatial data type **Embedded**.</span></span>  
  
3.  <span data-ttu-id="385ba-409">Haga clic en la flecha abajo en PointLayer2 y, a continuación, haga clic en **Agregar punto**.</span><span class="sxs-lookup"><span data-stu-id="385ba-409">Click the down arrow on PointLayer2, and then click **Add Point**.</span></span>  
  
4.  <span data-ttu-id="385ba-410">Mueva el puntero sobre la ventanilla del mapa.</span><span class="sxs-lookup"><span data-stu-id="385ba-410">Move the pointer over the map viewport.</span></span> <span data-ttu-id="385ba-411">El cursor cambia a la forma de cruz.</span><span class="sxs-lookup"><span data-stu-id="385ba-411">The cursor changes to crosshairs.</span></span>  
  
5.  <span data-ttu-id="385ba-412">Haga clic en la ubicación del mapa donde desee agregar un punto.</span><span class="sxs-lookup"><span data-stu-id="385ba-412">Click the location on the map where you want to add a point.</span></span> <span data-ttu-id="385ba-413">En este tutorial, haga clic en una ubicación de un condado próxima al inicio de la ruta.</span><span class="sxs-lookup"><span data-stu-id="385ba-413">In this tutorial, click a location in a county next to the start of the route.</span></span> <span data-ttu-id="385ba-414">Un punto marcado por un círculo se agrega a la capa en la ubicación donde hizo clic.</span><span class="sxs-lookup"><span data-stu-id="385ba-414">A point marked by a circle is added to the layer at the location where you clicked.</span></span> <span data-ttu-id="385ba-415">De forma predeterminada, el punto se selecciona.</span><span class="sxs-lookup"><span data-stu-id="385ba-415">By default, the point is selected.</span></span>  
  
6.  <span data-ttu-id="385ba-416">Haga clic con el botón derecho en el punto que ha agregado y, después, haga clic en **Propiedades de punto incrustado**.</span><span class="sxs-lookup"><span data-stu-id="385ba-416">Right-click the point you added, and then click **Embedded Point Properties**.</span></span>  
  
7.  <span data-ttu-id="385ba-417">Seleccione la opción **Invalidar opciones de punto para esta capa**.</span><span class="sxs-lookup"><span data-stu-id="385ba-417">Select the option **Override point options for this layer**.</span></span> <span data-ttu-id="385ba-418">Aparecen páginas adicionales en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="385ba-418">Additional pages appear in the dialog box.</span></span> <span data-ttu-id="385ba-419">Los valores que establece aquí tienen prioridad sobre las opciones de presentación de la capa o sobre las reglas de color.</span><span class="sxs-lookup"><span data-stu-id="385ba-419">Values that you set here take precedence over display options for the layer or for color rules.</span></span>  
  
8.  <span data-ttu-id="385ba-420">Haga clic en **Marcador**.</span><span class="sxs-lookup"><span data-stu-id="385ba-420">Click **Marker**.</span></span>  
  
9. <span data-ttu-id="385ba-421">En **Tipo de marcador**, seleccione **Estrella**.</span><span class="sxs-lookup"><span data-stu-id="385ba-421">For **Marker type**, select **Star**.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="385ba-422">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-422">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-423">El nuevo punto que agregó aparece como una **Estrella**.</span><span class="sxs-lookup"><span data-stu-id="385ba-423">The new point you added appears as a **Star**.</span></span>  
  
#### <a name="to-add-a-label-for-the-custom-point"></a><span data-ttu-id="385ba-424">Para agregar una etiqueta para el punto personalizado</span><span class="sxs-lookup"><span data-stu-id="385ba-424">To add a label for the custom point</span></span>  
  
1.  <span data-ttu-id="385ba-425">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-425">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-426">Haga clic con el botón secundario en el punto recién agregado y, a continuación, haga clic en **Propiedades de punto incrustado**.</span><span class="sxs-lookup"><span data-stu-id="385ba-426">Right-click the point you just added, and then click **Embedded Point Properties**.</span></span>  
  
3.  <span data-ttu-id="385ba-427">Haga clic en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="385ba-427">Click **Labels**.</span></span>  
  
4.  <span data-ttu-id="385ba-428">En **Texto de etiqueta**, escriba **Nuevo almacén**.</span><span class="sxs-lookup"><span data-stu-id="385ba-428">In **Label text**, type **New Store**.</span></span>  
  
5.  <span data-ttu-id="385ba-429">En **Colocación**, haga clic en **Superior**.</span><span class="sxs-lookup"><span data-stu-id="385ba-429">In **Placement**, click **Top**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="385ba-430">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-430">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-431">Aparece la etiqueta sobre la ubicación del almacén.</span><span class="sxs-lookup"><span data-stu-id="385ba-431">The label appears above the store location.</span></span>  
  
##  <a name="center-the-map-view"></a><a name="CenterView"></a><span data-ttu-id="385ba-432">Centrar la vista del mapa</span><span class="sxs-lookup"><span data-stu-id="385ba-432">Center the Map View</span></span>  
 <span data-ttu-id="385ba-433">Cambie el centro de la ventanilla de mapas y la capa de zoom.</span><span class="sxs-lookup"><span data-stu-id="385ba-433">Change the map viewport center and zoom level.</span></span>  
  
#### <a name="to-change-the-viewport"></a><span data-ttu-id="385ba-434">Para cambiar la ventanilla</span><span class="sxs-lookup"><span data-stu-id="385ba-434">To change the viewport</span></span>  
  
1.  <span data-ttu-id="385ba-435">Haga clic con el botón secundario en la ventanilla del mapa y, a continuación, haga clic en **Propiedades de ventanilla**.</span><span class="sxs-lookup"><span data-stu-id="385ba-435">Right-click the map viewport, and then click **Viewport Properties**.</span></span>  
  
2.  <span data-ttu-id="385ba-436">Haga clic en **Centrar y hacer zoom**.</span><span class="sxs-lookup"><span data-stu-id="385ba-436">Click **Center and Zoom**.</span></span>  
  
3.  <span data-ttu-id="385ba-437">Compruebe que está seleccionada la opción **Establecer un nivel para centrar y hacer zoom de la vista** .</span><span class="sxs-lookup"><span data-stu-id="385ba-437">Verify that the option **Set a view center and zoom level** is selected.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="385ba-438">Haga clic con el botón primario en la ventanilla de mapas y arrastre el centro de la ventanilla hacia la ubicación que desea.</span><span class="sxs-lookup"><span data-stu-id="385ba-438">Left-click the map viewport, and drag the center of the viewport to the location that you want.</span></span>  
  
6.  <span data-ttu-id="385ba-439">Utilice la rueda del mouse para cambiar el nivel de zoom de la ventanilla.</span><span class="sxs-lookup"><span data-stu-id="385ba-439">Use the mouse wheel to change the zoom level of the viewport.</span></span>  
  
7.  <span data-ttu-id="385ba-440">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-440">Preview the report.</span></span>  
  
 <span data-ttu-id="385ba-441">En la vista Diseño, el mapa de la superficie de presentación y la vista se basan en los datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="385ba-441">In Design view, the map on the display surface and the view is based on sample data.</span></span> <span data-ttu-id="385ba-442">En el informe representado, la vista del mapa se centra en la vista que especificó.</span><span class="sxs-lookup"><span data-stu-id="385ba-442">In the rendered report, the map view is centered on the view that you specified.</span></span>  
  
##  <a name="add-a-report-title"></a><a name="Title"></a><span data-ttu-id="385ba-443">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="385ba-443">Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="385ba-444">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="385ba-444">To add a report title</span></span>  
  
1.  <span data-ttu-id="385ba-445">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="385ba-445">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="385ba-446">Escriba **Ventas en almacenes de Nueva York** y, a continuación, haga clic fuera del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="385ba-446">Type **Sales in New York Stores** and then click outside the text box.</span></span>  
  
 <span data-ttu-id="385ba-447">Este título aparecerá en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-447">This title will appear at the top of the report.</span></span> <span data-ttu-id="385ba-448">Cuando no hay ningún encabezado de página definido, los elementos de la parte superior del cuerpo del informe son el equivalente a un encabezado de informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-448">Items at the top of the report body when there is no page header defined are the equivalent of a report header.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="385ba-449">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="385ba-449">Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="385ba-450">Para guardar el informe</span><span class="sxs-lookup"><span data-stu-id="385ba-450">To save the report</span></span>  
  
1.  <span data-ttu-id="385ba-451">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="385ba-451">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="385ba-452">En el botón Generador de informes , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="385ba-452">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="385ba-453">En **Nombre**, escriba **Ventas de almacenes en Nueva York**.</span><span class="sxs-lookup"><span data-stu-id="385ba-453">In **Name**, type **Store Sales in New York**.</span></span>  
  
 <span data-ttu-id="385ba-454">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="385ba-454">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="385ba-455">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="385ba-455">Next Steps</span></span>  
 <span data-ttu-id="385ba-456">De esta forma se concluye el tutorial sobre cómo agregar un mapa a un informe.</span><span class="sxs-lookup"><span data-stu-id="385ba-456">This concludes the walkthrough for how to add a map to your report.</span></span>  
  
 <span data-ttu-id="385ba-457">Para obtener más información, consulte [Maps &#40;generador de informes and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) y la entrada de blog sobre el [ajuste de datos espaciales para SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="385ba-457">For more information, see [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) and the blog entry [Cartographic Adjustment of Spatial Data for SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) on blogs.msdn.com.</span></span>  
  
 <span data-ttu-id="385ba-458">Para obtener más tutoriales, vea [tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="385ba-458">For more tutorials, see [Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385ba-459">Consulte también</span><span class="sxs-lookup"><span data-stu-id="385ba-459">See Also</span></span>  
 <span data-ttu-id="385ba-460">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="385ba-460">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="385ba-461">[Generador de informes en SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="385ba-461">[Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="385ba-462">[Asistente para mapas y Asistente para capas de mapa &#40;Generador de informes y SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="385ba-462">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="385ba-463">Variar la presentación de polígonos, líneas y puntos usando reglas y datos analíticos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="385ba-463">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
