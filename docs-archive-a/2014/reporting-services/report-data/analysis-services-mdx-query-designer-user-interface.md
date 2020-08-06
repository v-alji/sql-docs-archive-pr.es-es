---
title: Interfaz de usuario del Diseñador de consultas MDX de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10012"
- sql12.rtp.rptdesigner.dataview.asquerydesigner.f1
helpviewer_keywords:
- MDX [Reporting Services], creating datasets
- query designers [Reporting Services]
ms.assetid: d9c7c0b3-fce4-4a65-b679-408273e6a925
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 163a48497b073ddee9aad64b998594b12e8cad23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745066"
---
# <a name="analysis-services-mdx-query-designer-user-interface"></a><span data-ttu-id="2fe12-102">Interfaz de usuario del Diseñador de consultas MDX de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2fe12-102">Analysis Services MDX Query Designer User Interface</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2fe12-103">proporciona diseñadores gráficos de consultas para crear consultas MDX (Expresiones multidimensionales) y consultas DMX (Expresiones de minería de datos) para un origen de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2fe12-103">provides graphical query designers for building Multidimensional Expression (MDX) queries and Data Mining Expression (DMX) queries for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data source.</span></span> <span data-ttu-id="2fe12-104">En este tema se describe el diseñador de consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-104">This topic describes the MDX query designer.</span></span> <span data-ttu-id="2fe12-105">Para más información sobre el diseñador de consultas DMX, vea [Tipo de conexión de Analysis Services para DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fe12-105">For more information about the DMX query designer, see [Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md).</span></span>

 <span data-ttu-id="2fe12-106">El diseñador gráfico de consultas MDX tiene dos modos: modo de diseño y modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-106">The MDX graphical query designer has two modes: design mode and query mode.</span></span> <span data-ttu-id="2fe12-107">Cada modo proporciona un panel de metadatos desde el que puede arrastrar miembros de los cubos seleccionados para crear una consulta MDX; ésta recupera datos al procesarse el informe.</span><span class="sxs-lookup"><span data-stu-id="2fe12-107">Each mode provides a metadata pane from which you can drag members from the selected cubes to build an MDX query that retrieves data when the report is processed.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="2fe12-108">Los usuarios tienen acceso a los orígenes de datos cuando crean y ejecutan las consultas.</span><span class="sxs-lookup"><span data-stu-id="2fe12-108">Users access data sources when they create and run queries.</span></span> <span data-ttu-id="2fe12-109">Debe conceder permisos mínimos para los orígenes de datos, por ejemplo permisos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="2fe12-109">You should grant minimal permissions on the data sources, such as read-only permissions.</span></span>

## <a name="graphical-mdx-query-designer-in-design-mode"></a><span data-ttu-id="2fe12-110">Diseñador gráfico de consultas MDX en modo de diseño</span><span class="sxs-lookup"><span data-stu-id="2fe12-110">Graphical MDX Query Designer in Design Mode</span></span>
 <span data-ttu-id="2fe12-111">Al editar una consulta MDX para un conjunto de datos de informe, el diseñador gráfico de consultas MDX se abre en modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2fe12-111">When you edit an MDX query for a report dataset, the graphical MDX query designer opens in Design mode.</span></span>

 <span data-ttu-id="2fe12-112">En la siguiente ilustración se indican los nombres de los paneles del modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2fe12-112">The following figure labels the panes for Design mode.</span></span>

 <span data-ttu-id="2fe12-113">![Diseñador de consultas MDX de Analysis Services, vista de diseño](../../analysis-services/media/rsqd-dsawas-mdx-designmode.gif "Diseñador de consultas MDX de Analysis Services, vista de diseño")</span><span class="sxs-lookup"><span data-stu-id="2fe12-113">![Analysis Services MDX query designer, design view](../../analysis-services/media/rsqd-dsawas-mdx-designmode.gif "Analysis Services MDX query designer, design view")</span></span>

 <span data-ttu-id="2fe12-114">En la tabla siguiente aparecen los paneles de este modo:</span><span class="sxs-lookup"><span data-stu-id="2fe12-114">The following table lists the panes in this mode:</span></span>

|<span data-ttu-id="2fe12-115">Panel</span><span class="sxs-lookup"><span data-stu-id="2fe12-115">Pane</span></span>|<span data-ttu-id="2fe12-116">Función</span><span class="sxs-lookup"><span data-stu-id="2fe12-116">Function</span></span>|
|----------|--------------|
|<span data-ttu-id="2fe12-117">Botón Selección de cubo (**...**)</span><span class="sxs-lookup"><span data-stu-id="2fe12-117">Select Cube button (**...**)</span></span>|<span data-ttu-id="2fe12-118">Muestra el cubo seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="2fe12-118">Displays the currently selected cube.</span></span>|
|<span data-ttu-id="2fe12-119">Panel Metadatos</span><span class="sxs-lookup"><span data-stu-id="2fe12-119">Metadata pane</span></span>|<span data-ttu-id="2fe12-120">Muestra una lista jerárquica de medidas, indicadores clave de rendimiento (KPI) y dimensiones definidas en el cubo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2fe12-120">Displays a hierarchical list of measures, Key Performance Indicators (KPIs), and dimensions defined on the selected cube.</span></span>|
|<span data-ttu-id="2fe12-121">Panel Miembros calculados</span><span class="sxs-lookup"><span data-stu-id="2fe12-121">Calculated Members pane</span></span>|<span data-ttu-id="2fe12-122">Muestra los miembros calculados definidos actualmente que se encuentran disponibles para utilizarse en la consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-122">Displays the currently defined calculated members available for use in the query.</span></span>|
|<span data-ttu-id="2fe12-123">Panel Filtro</span><span class="sxs-lookup"><span data-stu-id="2fe12-123">Filter pane</span></span>|<span data-ttu-id="2fe12-124">Se utiliza a fin de elegir dimensiones y jerarquías relacionadas para filtrar datos en el origen y limitar datos devueltos al informe.</span><span class="sxs-lookup"><span data-stu-id="2fe12-124">Use to choose dimensions and related hierarchies to filter data at the source and limit data returned to the report.</span></span>|
|<span data-ttu-id="2fe12-125">Panel Datos</span><span class="sxs-lookup"><span data-stu-id="2fe12-125">Data pane</span></span>|<span data-ttu-id="2fe12-126">Muestra los encabezados de columna del conjunto de resultados mientras arrastra elementos de los paneles Metadatos y Miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="2fe12-126">Displays the column headings for the result set as you drag items from the Metadata pane and the Calculated Members pane.</span></span> <span data-ttu-id="2fe12-127">Actualiza automáticamente el conjunto de resultados si el botón **Ejecución automática** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2fe12-127">Automatically updates the result set if the **AutoExecute** button is selected.</span></span> <span data-ttu-id="2fe12-128">.</span><span class="sxs-lookup"><span data-stu-id="2fe12-128">.</span></span>|

 <span data-ttu-id="2fe12-129">Puede arrastrar dimensiones, medidas y KPI desde el panel Metadatos, y los miembros calculados desde el panel Miembros calculados al panel Datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-129">You can drag dimensions, measures, and KPIs from the Metadata pane, and calculated members from the Calculated Member pane, onto the Data pane.</span></span> <span data-ttu-id="2fe12-130">En el panel Filtro, puede seleccionar dimensiones y jerarquías relacionadas, y establecer expresiones de filtro para limitar los datos disponibles en la consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-130">In the Filter pane, you can select dimensions and related hierarchies, and set filter expressions to limit the data available to query.</span></span> <span data-ttu-id="2fe12-131">Si el botón de alternancia **Ejecución automática** (![Ejecutar la consulta automáticamente](../../analysis-services/media/rsqdicon-autoexecute.gif "Ejecutar la consulta automáticamente")) de la barra de herramientas está seleccionado, el diseñador de consultas ejecuta la consulta cada vez que coloque un objeto de metadatos en el panel Datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-131">If the **AutoExecute** (![AutoExecute the query](../../analysis-services/media/rsqdicon-autoexecute.gif "AutoExecute the query")) toggle button on the toolbar is selected, the query designer runs the query every time that you drop a metadata object onto the Data pane.</span></span> <span data-ttu-id="2fe12-132">Puede ejecutar la consulta manualmente con el botón **Ejecutar** (![Ejecutar la consulta](../../analysis-services/media/rsqdicon-run.gif "Ejecución de la consulta")) de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2fe12-132">You can manually run the query using the **Run** (![Run the query](../../analysis-services/media/rsqdicon-run.gif "Run the query")) button on the toolbar.</span></span>

 <span data-ttu-id="2fe12-133">Al crear una consulta MDX en este modo, se incluyen automáticamente en la consulta las propiedades adicionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="2fe12-133">When you create an MDX query in this mode, the following additional properties are automatically included in the query:</span></span>

 <span data-ttu-id="2fe12-134">**Propiedades de miembro** MEMBER_CAPTION, MEMBER_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fe12-134">**Member Properties** MEMBER_CAPTION, MEMBER_UNIQUE_NAME</span></span>

 <span data-ttu-id="2fe12-135">**Propiedades de la celda** VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2fe12-135">**Cell Properties** VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS</span></span>

 <span data-ttu-id="2fe12-136">Si desea especificar sus propias propiedades adicionales, debe modificar manualmente la consulta MDX en el modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-136">To specify your own additional properties, you must manually edit the MDX query in Query mode.</span></span>

### <a name="graphical-mdx-query-designer-toolbar-in-design-mode"></a><span data-ttu-id="2fe12-137">Barra de herramientas del diseñador gráfico de consultas MDX en modo de diseño</span><span class="sxs-lookup"><span data-stu-id="2fe12-137">Graphical MDX Query Designer Toolbar in Design Mode</span></span>
 <span data-ttu-id="2fe12-138">La barra de herramientas del diseñador de consultas proporciona botones que le ayudan a diseñar consultas MDX mediante la interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="2fe12-138">The query designer toolbar provides buttons to help you design MDX queries using the graphical interface.</span></span> <span data-ttu-id="2fe12-139">En la tabla siguiente se describen los botones y sus funciones.</span><span class="sxs-lookup"><span data-stu-id="2fe12-139">The following table lists the buttons and their functions.</span></span>

|<span data-ttu-id="2fe12-140">Botón</span><span class="sxs-lookup"><span data-stu-id="2fe12-140">Button</span></span>|<span data-ttu-id="2fe12-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="2fe12-141">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="2fe12-142">**Editar como texto**</span><span class="sxs-lookup"><span data-stu-id="2fe12-142">**Edit As Text**</span></span>|<span data-ttu-id="2fe12-143">No está habilitado para este tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-143">Not enabled for this data source type.</span></span>|
|<span data-ttu-id="2fe12-144">**Importar**</span><span class="sxs-lookup"><span data-stu-id="2fe12-144">**Import**</span></span>|<span data-ttu-id="2fe12-145">Importa una consulta existente desde un archivo de definición de informe (.rdl) del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-145">Import an existing query from a report definition (.rdl) file on the file system.</span></span> <span data-ttu-id="2fe12-146">Para más información, vea [Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fe12-146">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>|
|<span data-ttu-id="2fe12-147">![Cambiar a la vista de la consulta MDX](../../analysis-services/media/rsqdicon-commandtypemdx.gif "Cambiar a la vista de la consulta MDX")</span><span class="sxs-lookup"><span data-stu-id="2fe12-147">![Change to MDX query view](../../analysis-services/media/rsqdicon-commandtypemdx.gif "Change to MDX query view")</span></span>|<span data-ttu-id="2fe12-148">Cambia al tipo de comando MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-148">Switch to Command Type MDX.</span></span>|
|<span data-ttu-id="2fe12-149">![Cambiar a la vista del lenguaje de consultas DMX](../media/rsqdicon-commandtypedmx.gif "Cambiar a la vista del lenguaje de consultas DMX")</span><span class="sxs-lookup"><span data-stu-id="2fe12-149">![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")</span></span>|<span data-ttu-id="2fe12-150">Cambia al tipo de comando DMX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-150">Switch to Command Type DMX.</span></span>|
|<span data-ttu-id="2fe12-151">![Actualizar datos de resultados](../../analysis-services/media/rsqdicon-refresh.gif "Actualizar datos de resultados")</span><span class="sxs-lookup"><span data-stu-id="2fe12-151">![Refresh result data](../../analysis-services/media/rsqdicon-refresh.gif "Refresh result data")</span></span>|<span data-ttu-id="2fe12-152">Actualiza los metadatos desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-152">Refresh metadata from the data source.</span></span>|
|<span data-ttu-id="2fe12-153">![Agregar miembro calculado](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Agregar miembro calculado")</span><span class="sxs-lookup"><span data-stu-id="2fe12-153">![Add calculated member](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Add calculated member")</span></span>|<span data-ttu-id="2fe12-154">Muestra el cuadro de diálogo **Generador de miembros calculados** .</span><span class="sxs-lookup"><span data-stu-id="2fe12-154">Display the **Calculated Member Builder** dialog box.</span></span>|
|<span data-ttu-id="2fe12-155">![Alternar para mostrar celdas vacías](../../analysis-services/media/rsqdicon-showemptycells.gif "Alternar para mostrar celdas vacías")</span><span class="sxs-lookup"><span data-stu-id="2fe12-155">![Toggle for show empty cells](../../analysis-services/media/rsqdicon-showemptycells.gif "Toggle for show empty cells")</span></span>|<span data-ttu-id="2fe12-156">Muestra y oculta las celdas vacías del panel Datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-156">Toggle between showing and not showing empty cells in the Data pane.</span></span> <span data-ttu-id="2fe12-157">Esto equivale a utilizar la cláusula NON EMPTY en MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-157">(This is the equivalent to using the NON EMPTY clause in MDX).</span></span>|
|<span data-ttu-id="2fe12-158">![Ejecutar la consulta automáticamente](../../analysis-services/media/rsqdicon-autoexecute.gif "Ejecutar la consulta automáticamente")</span><span class="sxs-lookup"><span data-stu-id="2fe12-158">![AutoExecute the query](../../analysis-services/media/rsqdicon-autoexecute.gif "AutoExecute the query")</span></span>|<span data-ttu-id="2fe12-159">Ejecuta automáticamente la consulta y muestra el resultado cada vez que se realiza un cambio.</span><span class="sxs-lookup"><span data-stu-id="2fe12-159">Automatically run the query and show the result every time a change is made.</span></span> <span data-ttu-id="2fe12-160">Los resultados se mostrarán en el panel Datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-160">Results are shown in the Data pane.</span></span>|
|<span data-ttu-id="2fe12-161">![Botón Mostrar agregaciones](../../analysis-services/media/rsqdicon-showaggregations.gif "Botón Mostrar agregaciones")</span><span class="sxs-lookup"><span data-stu-id="2fe12-161">![Show Aggregations button](../../analysis-services/media/rsqdicon-showaggregations.gif "Show Aggregations button")</span></span>|<span data-ttu-id="2fe12-162">Muestra agregaciones en el panel Datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-162">Show aggregations in the Data pane.</span></span>|
|<span data-ttu-id="2fe12-163">![Eliminar](../../analysis-services/media/rsqdicon-delete.gif "Eliminar")</span><span class="sxs-lookup"><span data-stu-id="2fe12-163">![Delete](../../analysis-services/media/rsqdicon-delete.gif "Delete")</span></span>|<span data-ttu-id="2fe12-164">Elimina la columna seleccionada en el panel Datos de la consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-164">Delete the selected column in the Data pane from the query.</span></span>|
|<span data-ttu-id="2fe12-165">![Icono del cuadro de diálogo Parámetros de consulta](../../analysis-services/media/iconqueryparameter.gif "Icono del cuadro de diálogo Parámetros de consulta")</span><span class="sxs-lookup"><span data-stu-id="2fe12-165">![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")</span></span>|<span data-ttu-id="2fe12-166">Muestra el cuadro de diálogo **Parámetros de consulta** .</span><span class="sxs-lookup"><span data-stu-id="2fe12-166">Display the **Query Parameters** dialog box.</span></span> <span data-ttu-id="2fe12-167">Al especificar valores para un parámetro de consulta, se crea automáticamente un parámetro de informe con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2fe12-167">When you specify values for a query parameter, a report parameter with the same name is automatically created.</span></span> <span data-ttu-id="2fe12-168">El valor del parámetro de consulta se establece en una expresión que hace referencia al parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="2fe12-168">The value of the query parameter is set to an expression that references the report parameter.</span></span>|
|<span data-ttu-id="2fe12-169">![Botón Preparar consulta](../../analysis-services/media/rsqdicon-preparequery.gif "Botón Preparar consulta")</span><span class="sxs-lookup"><span data-stu-id="2fe12-169">![Prepare Query button](../../analysis-services/media/rsqdicon-preparequery.gif "Prepare Query button")</span></span>|<span data-ttu-id="2fe12-170">Prepara la consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-170">Prepare the query.</span></span>|
|<span data-ttu-id="2fe12-171">![Ejecución de la consulta](../../analysis-services/media/rsqdicon-run.gif "Ejecución de la consulta")</span><span class="sxs-lookup"><span data-stu-id="2fe12-171">![Run the query](../../analysis-services/media/rsqdicon-run.gif "Run the query")</span></span>|<span data-ttu-id="2fe12-172">Ejecuta la consulta y muestra los resultados en el panel Datos.</span><span class="sxs-lookup"><span data-stu-id="2fe12-172">Run the query and display the results in the Data pane.</span></span>|
|<span data-ttu-id="2fe12-173">![Cancelar la consulta](../../analysis-services/media/rsqdicon-cancel.gif "Cancelar la consulta")</span><span class="sxs-lookup"><span data-stu-id="2fe12-173">![Cancel the query](../../analysis-services/media/rsqdicon-cancel.gif "Cancel the query")</span></span>|<span data-ttu-id="2fe12-174">Cancela la consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-174">Cancel the query.</span></span>|
|<span data-ttu-id="2fe12-175">![Cambiar al modo de diseño](../../analysis-services/media/rsqdicon-designmode.gif "Cambiar al modo de diseño")</span><span class="sxs-lookup"><span data-stu-id="2fe12-175">![Switch to Design mode](../../analysis-services/media/rsqdicon-designmode.gif "Switch to Design mode")</span></span>|<span data-ttu-id="2fe12-176">Alterna el modo de diseño y el modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-176">Toggle between Design mode and Query mode.</span></span>|

## <a name="graphical-mdx-query-designer-in-query-mode"></a><span data-ttu-id="2fe12-177">Diseñador gráfico de consultas MDX en modo de consulta</span><span class="sxs-lookup"><span data-stu-id="2fe12-177">Graphical MDX Query Designer in Query Mode</span></span>
 <span data-ttu-id="2fe12-178">Para cambiar el diseñador gráfico de consultas al modo **Consulta** , haga clic en el botón **Modo de diseño** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2fe12-178">To change the graphical query designer to **Query** mode, click the **Design Mode** button on the toolbar.</span></span>

 <span data-ttu-id="2fe12-179">En la ilustración siguiente se indican los nombres de los paneles del modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-179">The following figure labels the panes for Query mode.</span></span>

 <span data-ttu-id="2fe12-180">![Diseñador de consultas MDX de Analysis Services, vista de consulta](../../analysis-services/media/rsqd-dsawas-mdx-querymode.gif "Diseñador de consultas MDX de Analysis Services, vista de consulta")</span><span class="sxs-lookup"><span data-stu-id="2fe12-180">![Analysis Services MDX query designer, query view](../../analysis-services/media/rsqd-dsawas-mdx-querymode.gif "Analysis Services MDX query designer, query view")</span></span>

 <span data-ttu-id="2fe12-181">En la tabla siguiente aparecen los paneles de este modo:</span><span class="sxs-lookup"><span data-stu-id="2fe12-181">The following table lists the panes in this mode:</span></span>

|<span data-ttu-id="2fe12-182">Panel</span><span class="sxs-lookup"><span data-stu-id="2fe12-182">Pane</span></span>|<span data-ttu-id="2fe12-183">Función</span><span class="sxs-lookup"><span data-stu-id="2fe12-183">Function</span></span>|
|----------|--------------|
|<span data-ttu-id="2fe12-184">Botón Selección de cubo (**...**)</span><span class="sxs-lookup"><span data-stu-id="2fe12-184">Select Cube button (**...**)</span></span>|<span data-ttu-id="2fe12-185">Muestra el cubo seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="2fe12-185">Displays the currently selected cube.</span></span>|
|<span data-ttu-id="2fe12-186">Panel Metadatos/Funciones/Plantillas</span><span class="sxs-lookup"><span data-stu-id="2fe12-186">Metadata/Functions/Templates pane</span></span>|<span data-ttu-id="2fe12-187">Muestra una lista jerárquica de medidas, KPI y dimensiones definidas en el cubo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2fe12-187">Displays a hierarchical list of measures, KPIs, and dimensions defined on the selected cube.</span></span>|
|<span data-ttu-id="2fe12-188">Panel de consulta</span><span class="sxs-lookup"><span data-stu-id="2fe12-188">Query pane</span></span>|<span data-ttu-id="2fe12-189">Muestra el texto de consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-189">Displays the query text.</span></span>|
|<span data-ttu-id="2fe12-190">Panel Resultado</span><span class="sxs-lookup"><span data-stu-id="2fe12-190">Result pane</span></span>|<span data-ttu-id="2fe12-191">Muestra los resultados de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="2fe12-191">Displays the results of running the query.</span></span>|

 <span data-ttu-id="2fe12-192">El panel Metadatos muestra pestañas de **Metadatos**, **Funciones**y **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="2fe12-192">The Metadata pane displays tabs for **Metadata**, **Functions**, and **Templates**.</span></span> <span data-ttu-id="2fe12-193">Desde la pestaña **Metadatos** , puede arrastrar dimensiones, jerarquías, KPI y medidas al panel Consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-193">From the **Metadata** tab, you can drag dimensions, hierarchies, KPIs, and measures onto the MDX Query pane.</span></span> <span data-ttu-id="2fe12-194">Desde la pestaña **Funciones** , puede arrastrar funciones hasta el panel Consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-194">From the **Functions** tab, you can drag functions onto the MDX Query pane.</span></span> <span data-ttu-id="2fe12-195">Desde la pestaña **Plantillas** , puede agregar plantillas MDX al panel Consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-195">From the **Templates** tab, you can add MDX templates to the MDX Query pane.</span></span> <span data-ttu-id="2fe12-196">Cuando ejecute la consulta, en el panel Resultado se mostrarán los resultados de la consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="2fe12-196">When you execute the query, the Result pane displays the results for the MDX query.</span></span>

 <span data-ttu-id="2fe12-197">Puede ampliar la consulta MDX predeterminada generada en modo de diseño para que incluya propiedades de miembro y de celda adicionales.</span><span class="sxs-lookup"><span data-stu-id="2fe12-197">You can extend the default MDX query generated in Design mode to include additional member properties and cell properties.</span></span> <span data-ttu-id="2fe12-198">Al ejecutar la consulta, estos valores no aparecen en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2fe12-198">When you run the query, these values do not appear in the result set.</span></span> <span data-ttu-id="2fe12-199">Sin embargo, se devuelven a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] y puede usarlos en un informe.</span><span class="sxs-lookup"><span data-stu-id="2fe12-199">However, they are passed back to [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] and you can use these values in a report.</span></span> <span data-ttu-id="2fe12-200">Para obtener más información, vea Propiedades de campo extendidas para una base de datos de Analysis Services (SSRS).</span><span class="sxs-lookup"><span data-stu-id="2fe12-200">For more information, see Extended Field Properties for an Analysis Services Database (SSRS).</span></span>

### <a name="graphical-query-designer-toolbar-in-query-mode"></a><span data-ttu-id="2fe12-201">Barra de herramientas del diseñador gráfico de consultas en modo de consulta</span><span class="sxs-lookup"><span data-stu-id="2fe12-201">Graphical Query Designer Toolbar in Query Mode</span></span>
 <span data-ttu-id="2fe12-202">La barra de herramientas del diseñador de consultas proporciona botones que le ayudan a diseñar consultas MDX mediante la interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="2fe12-202">The query designer toolbar provides buttons to help you design MDX queries using the graphical interface.</span></span>

 <span data-ttu-id="2fe12-203">Los botones de la barra de herramientas son idénticos en los modos de diseño y de consulta. Sin embargo, los siguientes botones no están habilitados para el modo de consulta:</span><span class="sxs-lookup"><span data-stu-id="2fe12-203">The toolbar buttons are identical between Design mode and Query mode, but the following buttons are not enabled for Query mode:</span></span>

-   <span data-ttu-id="2fe12-204">**Editar como texto**</span><span class="sxs-lookup"><span data-stu-id="2fe12-204">**Edit As Text**</span></span>

-   <span data-ttu-id="2fe12-205">**Agregar miembro calculado** (![Agregar miembro calculado](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Agregar miembro calculado"))</span><span class="sxs-lookup"><span data-stu-id="2fe12-205">**Add Calculated Member** (![Add calculated member](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Add calculated member"))</span></span>

-   <span data-ttu-id="2fe12-206">**Mostrar celdas vacías** (![Alternar para mostrar celdas vacías](../../analysis-services/media/rsqdicon-showemptycells.gif "Alternar para mostrar celdas vacías"))</span><span class="sxs-lookup"><span data-stu-id="2fe12-206">**Show Empty Cells** (![Toggle for show empty cells](../../analysis-services/media/rsqdicon-showemptycells.gif "Toggle for show empty cells"))</span></span>

-   <span data-ttu-id="2fe12-207">**Ejecutar automáticamente** (![Ejecutar la consulta automáticamente](../../analysis-services/media/rsqdicon-autoexecute.gif "Ejecutar la consulta automáticamente"))</span><span class="sxs-lookup"><span data-stu-id="2fe12-207">**AutoExecute** (![AutoExecute the query](../../analysis-services/media/rsqdicon-autoexecute.gif "AutoExecute the query"))</span></span>

-   <span data-ttu-id="2fe12-208">**Mostrar agregaciones** (![Botón Mostrar agregaciones](../../analysis-services/media/rsqdicon-showaggregations.gif "Botón Mostrar agregaciones"))</span><span class="sxs-lookup"><span data-stu-id="2fe12-208">**Show Aggregations** (![Show Aggregations button](../../analysis-services/media/rsqdicon-showaggregations.gif "Show Aggregations button"))</span></span>

## <a name="see-also"></a><span data-ttu-id="2fe12-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fe12-209">See Also</span></span>
 <span data-ttu-id="2fe12-210">[Defina los parámetros en el diseñador de consultas MDX para Analysis Services &#40;generador de informes y ssrs&#41;](define-parameters-in-the-mdx-query-designer-for-analysis-services.md) [crear un conjunto de DataSet compartido o un conjunto de archivos incrustado &#40;Generador de informes y SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) [tipo de conexión Analysis Services para DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) el [archivo de configuración RSReportDesigner](../report-server/rsreportdesigner-configuration-file.md) [Analysis Services tipo de conexión para MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="2fe12-210">[Define Parameters in the MDX Query Designer for Analysis Services &#40;Report Builder and SSRS&#41;](define-parameters-in-the-mdx-query-designer-for-analysis-services.md) [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) [Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) [RSReportDesigner Configuration File](../report-server/rsreportdesigner-configuration-file.md) [Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md)</span></span>

