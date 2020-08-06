---
title: Agregar, cambiar o eliminar un mapa o una capa de mapa (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10526"
- sql12.rtp.rptdesigner.maptilelayerproperties.general.f1
- "10529"
- "10525"
- "10535"
- sql12.rtp.rptdesigner.mappolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layervisibility.f1
- sql12.rtp.rptdesigner.mappointlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layerfilters.f1
- "10524"
- sql12.rtp.rptdesigner.maplayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.general.f1
- "10532"
- "10528"
- "10527"
- sql12.rtp.rptdesigner.maplayerproperties.analyticaldata.f1
ms.assetid: 6e89815e-187e-45bf-bf63-3d5c4a246360
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4e9fd178d36ee3322c0bd94dd44d621439139b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672761"
---
# <a name="add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="8d21a-102">Agregar, cambiar o eliminar un mapa o una capa de mapa (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="8d21a-102">Add, Change, or Delete a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8d21a-103">Un mapa es una colección de capas.</span><span class="sxs-lookup"><span data-stu-id="8d21a-103">A map is a collection of layers.</span></span> <span data-ttu-id="8d21a-104">Al agregar un mapa a un informe, define la primera capa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-104">When you add a map to a report, you define the first layer.</span></span> <span data-ttu-id="8d21a-105">Puede crear capas adicionales con el Asistente para capas de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-105">You can create additional layers by using the map layer wizard.</span></span>  
  
 <span data-ttu-id="8d21a-106">La manera más fácil de agregar, quitar o cambiar las opciones de una capa es utilizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="8d21a-106">The easiest way to add, remove, or change options for a layer is to use the map layer wizard.</span></span> <span data-ttu-id="8d21a-107">También puede cambiar manualmente las opciones del panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-107">You can also change options manually from the Map pane.</span></span> <span data-ttu-id="8d21a-108">Para mostrar el panel **Mapa** , haga clic en el mapa en la superficie de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="8d21a-108">To display the **Map** pane, click in the map on the report design surface.</span></span> <span data-ttu-id="8d21a-109">La figura siguiente muestra las partes del panel:</span><span class="sxs-lookup"><span data-stu-id="8d21a-109">The following figure displays the parts of the pane:</span></span>  
  
 <span data-ttu-id="8d21a-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span><span class="sxs-lookup"><span data-stu-id="8d21a-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span></span>  
  
 <span data-ttu-id="8d21a-111">Las capas de mapa se dibujan desde la parte inferior a la superior en el orden en que aparecen en el panel Capa de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-111">Map layers are drawn from bottom to top in the order that they appear in the Map pane.</span></span> <span data-ttu-id="8d21a-112">En la figura anterior, la capa de mosaico se dibuja primero y en último lugar se dibuja la capa de polígono.</span><span class="sxs-lookup"><span data-stu-id="8d21a-112">In the previous figure, the tile layer is drawn first and the polygon layer is drawn last.</span></span> <span data-ttu-id="8d21a-113">Las capas que se dibujen después podrían ocultar los elementos de mapa de las capas que se dibujaron anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8d21a-113">Layers that are drawn later might hide map elements on layers that are drawn earlier.</span></span> <span data-ttu-id="8d21a-114">Puede cambiar el orden de las capas utilizando las teclas de dirección de la barra de herramientas del panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-114">You can change the order of layers by using the arrow keys on the Map pane toolbar.</span></span> <span data-ttu-id="8d21a-115">Para mostrar u ocultar las capas, alterne el icono de visibilidad.</span><span class="sxs-lookup"><span data-stu-id="8d21a-115">To show or hide layers, toggle the visibility icon.</span></span> <span data-ttu-id="8d21a-116">Puede cambiar la transparencia de una capa en la `Visibility` página del cuadro de diálogo Propiedades de **datos de capa** .</span><span class="sxs-lookup"><span data-stu-id="8d21a-116">You can change the transparency of a layer on the `Visibility` page of the **Layer Data** properties dialog box.</span></span>  
  
 <span data-ttu-id="8d21a-117">En la tabla siguiente se muestran los iconos de la barra de herramientas del panel **Mapa** .</span><span class="sxs-lookup"><span data-stu-id="8d21a-117">The following table displays the toolbar icons for the **Map** pane.</span></span>  
  
|<span data-ttu-id="8d21a-118">Símbolo</span><span class="sxs-lookup"><span data-stu-id="8d21a-118">Symbol</span></span>|<span data-ttu-id="8d21a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d21a-119">Description</span></span>|<span data-ttu-id="8d21a-120">Cuándo se usa</span><span class="sxs-lookup"><span data-stu-id="8d21a-120">When to use</span></span>|  
|------------|-----------------|-----------------|  
|<span data-ttu-id="8d21a-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span><span class="sxs-lookup"><span data-stu-id="8d21a-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span></span>|<span data-ttu-id="8d21a-122">Asistente para capas de mapa</span><span class="sxs-lookup"><span data-stu-id="8d21a-122">Map Layer Wizard</span></span>|<span data-ttu-id="8d21a-123">Para agregar una capa con un asistente, haga clic en **Asistente para nueva capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-123">To add a layer by using a wizard, click **New layer wizard**.</span></span>|  
|<span data-ttu-id="8d21a-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span><span class="sxs-lookup"><span data-stu-id="8d21a-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span></span>|<span data-ttu-id="8d21a-125">Agregar capa</span><span class="sxs-lookup"><span data-stu-id="8d21a-125">Add Layer</span></span>|<span data-ttu-id="8d21a-126">Para agregar una capa manualmente, haga clic en **Agregar capa**y, a continuación, haga clic en el tipo de capa de mapa que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="8d21a-126">To manually add a layer, click **Add Layer**, and then click the type of map layer to add.</span></span>|  
|<span data-ttu-id="8d21a-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span><span class="sxs-lookup"><span data-stu-id="8d21a-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span></span>|<span data-ttu-id="8d21a-128">Capa de polígono</span><span class="sxs-lookup"><span data-stu-id="8d21a-128">Polygon Layer</span></span>|<span data-ttu-id="8d21a-129">Agregue una capa de mapa que muestre áreas o formas basadas en conjuntos de coordenadas de un polígono.</span><span class="sxs-lookup"><span data-stu-id="8d21a-129">Add a map layer that displays areas or shapes that are based sets of polygon coordinates.</span></span>|  
|<span data-ttu-id="8d21a-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span><span class="sxs-lookup"><span data-stu-id="8d21a-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span></span>|<span data-ttu-id="8d21a-131">Capa de línea</span><span class="sxs-lookup"><span data-stu-id="8d21a-131">Line Layer</span></span>|<span data-ttu-id="8d21a-132">Agregue una capa de mapa que muestre los trazados o rutas basados en conjuntos de coordenadas de una línea.</span><span class="sxs-lookup"><span data-stu-id="8d21a-132">Add a map layer that displays paths or routes that are based on sets of line coordinates.</span></span>|  
|<span data-ttu-id="8d21a-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span><span class="sxs-lookup"><span data-stu-id="8d21a-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span></span>|<span data-ttu-id="8d21a-134">Capa de punto</span><span class="sxs-lookup"><span data-stu-id="8d21a-134">Point Layer</span></span>|<span data-ttu-id="8d21a-135">Agregue una capa de mapa que muestre las ubicaciones basadas en los conjuntos de coordenadas de un punto.</span><span class="sxs-lookup"><span data-stu-id="8d21a-135">Add a map layer that displays locations that are based on sets of point coordinates.</span></span>|  
|<span data-ttu-id="8d21a-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span><span class="sxs-lookup"><span data-stu-id="8d21a-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span></span>|<span data-ttu-id="8d21a-137">Capa de mosaico</span><span class="sxs-lookup"><span data-stu-id="8d21a-137">Tile Layer</span></span>|<span data-ttu-id="8d21a-138">Agregue una capa de mapa que muestre los mosaicos de Bing Maps que correspondan al área de la vista del mapa actual que se define en la ventanilla.</span><span class="sxs-lookup"><span data-stu-id="8d21a-138">Add a map layer that displays Bing Map tiles that correspond to the current map view area that is defined by the viewport.</span></span>|  
  
 <span data-ttu-id="8d21a-139">En la parte inferior del panel Mapa es el área de la vista Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-139">At the bottom of the Map pane is the Map view area.</span></span> <span data-ttu-id="8d21a-140">Para cambiar las opciones de centro o zoom del mapa, utilice las teclas de dirección para ajustar el centro de la vista y el control deslizante para ajustar el nivel de zoom.</span><span class="sxs-lookup"><span data-stu-id="8d21a-140">To change the center or zoom options for the map, use the arrow keys to adjust the view center and the slider to adjust the zoom level.</span></span>  
  
 <span data-ttu-id="8d21a-141">Para obtener más información sobre las capas, vea [Mapas &#40;Generador de informes y SSRS&#41;](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8d21a-141">For more information about layers, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-add-a-layer-from-the-map-layer-wizard"></a><a name="AddLayer"></a> <span data-ttu-id="8d21a-142">Agregar una capa con el Asistente para capas de mapa</span><span class="sxs-lookup"><span data-stu-id="8d21a-142">To add a layer from the map layer wizard</span></span>  
  
-   <span data-ttu-id="8d21a-143">De la Cinta de opciones, en el menú **Insertar** , haga clic en **Mapa**y, a continuación, haga clic en **Mapa Wizard.**</span><span class="sxs-lookup"><span data-stu-id="8d21a-143">From the Ribbon, on the **Insert** menu, click **Map**, and then click **Map Wizard.**</span></span> <span data-ttu-id="8d21a-144">. El asistente le permite agregar una capa al mapa existente.</span><span class="sxs-lookup"><span data-stu-id="8d21a-144">The wizard enables you to add a layer to the existing map.</span></span> <span data-ttu-id="8d21a-145">La mayor parte de las páginas son idénticas en el Asistente para mapas y el Asistente para capas de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-145">Most wizard pages are identical between the map wizard and the map layer wizard.</span></span>  
  
     <span data-ttu-id="8d21a-146">Para obtener más información, vea [Asistente para mapas y Asistente para capas de mapa &#40;Generador de informes y SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8d21a-146">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-change-options-for-a-layer-by-using-the-map-layer-wizard"></a><a name="ChangeLayer"></a> <span data-ttu-id="8d21a-147">Cambiar las opciones de una capa con el Asistente para capas de mapa</span><span class="sxs-lookup"><span data-stu-id="8d21a-147">To change options for a layer by using the map layer wizard</span></span>  
  
-   <span data-ttu-id="8d21a-148">Ejecute el Asistente para capas de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-148">Run the map layer wizard.</span></span> <span data-ttu-id="8d21a-149">Este asistente le permite cambiar las opciones de una capa que creó utilizando el Asistente para capas de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-149">This wizard enables you to change options for a layer that you created by using the map layer wizard.</span></span> <span data-ttu-id="8d21a-150">En el panel Mapa, haga clic con el botón derecho en la capa y, en la barra de herramientas, haga clic en el botón del Asistente para capas (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="8d21a-150">In the Map pane, right-click the layer, and on the toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
     <span data-ttu-id="8d21a-151">Para obtener más información, vea [Asistente para mapas y Asistente para capas de mapa &#40;Generador de informes y SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8d21a-151">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-add-a-point-line-or-polygon-layer-from-the-map-pane-toolbar"></a><a name="AddVectorLayer"></a> <span data-ttu-id="8d21a-152">Agregar una capa de punto, línea o polígono desde la barra de herramientas del panel Mapa</span><span class="sxs-lookup"><span data-stu-id="8d21a-152">To add a point, line, or polygon layer from the Map pane toolbar</span></span>  
  
1.  <span data-ttu-id="8d21a-153">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-153">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-154">En la barra de herramientas, haga clic en el botón **Agregar capa** y, en la lista desplegable, haga clic en el tipo de capa que quiere agregar: **Punto**, **Línea** o **Polígono**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-154">On the toolbar, click the **Add Layer** button, and from the drop-down list, click the type of layer that you want to add: **Point**, **Line**, or **Polygon**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d21a-155">Aunque puede agregar una capa de mapa y configurarla manualmente, recomendamos utilizar el Asistente para capas de mapa si desea agregar capas nuevas.</span><span class="sxs-lookup"><span data-stu-id="8d21a-155">Although you can add a map layer and configure it manually, we recommend that you use the map layer wizard to add new layers.</span></span> <span data-ttu-id="8d21a-156">Para iniciar el asistente desde la barra de herramientas del panel Mapa, haga clic en el botón del Asistente para capas (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="8d21a-156">To launch the wizard from the Map pane toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
3.  <span data-ttu-id="8d21a-157">Haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-157">Right-click the layer, and then click **Layer Data**.</span></span>  
  
4.  <span data-ttu-id="8d21a-158">En **Usar datos espaciales de**, seleccione el origen de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="8d21a-158">In **Use spatial data from**, select the source of spatial data.</span></span> <span data-ttu-id="8d21a-159">Las opciones varían en función de la selección.</span><span class="sxs-lookup"><span data-stu-id="8d21a-159">Options vary based on your selection.</span></span>  
  
     <span data-ttu-id="8d21a-160">Si desea ver los datos analíticos del informe en esta capa, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d21a-160">If you want to visualize analytical from your report on this layer, do the following:</span></span>  
  
    1.  <span data-ttu-id="8d21a-161">Haga clic en **Datos analíticos**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-161">Click **Analytical data**.</span></span>  
  
    2.  <span data-ttu-id="8d21a-162">En **Conjunto de datos analíticos**, haga clic en el nombre del conjunto de datos que contenga los datos analíticos y en los campos coincidentes para generar una relación entre datos analíticos y datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="8d21a-162">In **Analytical dataset**, click the name of the dataset that contains analytical data and the match fields to build a relationship between analytical and spatial data.</span></span>  
  
    3.  <span data-ttu-id="8d21a-163">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-163">Click **Add**.</span></span>  
  
    4.  <span data-ttu-id="8d21a-164">Escriba el nombre del campo coincidente desde el conjunto de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="8d21a-164">Type the name of the match field from the spatial dataset.</span></span>  
  
    5.  <span data-ttu-id="8d21a-165">Escriba el nombre del campo coincidente desde el conjunto de datos analíticos.</span><span class="sxs-lookup"><span data-stu-id="8d21a-165">Type the name of the match field from the analytical dataset.</span></span>  
  
     <span data-ttu-id="8d21a-166">Para obtener más información sobre cómo vincular datos espaciales y analíticos, vea [Personalizar los datos y la presentación de un mapa o una capa de mapa &#40;Generador de informes y SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8d21a-166">For more information about linking spatial and analytical data, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-filter-analytical-data-for-the-layer"></a><a name="FilterAnalyticalData"></a> <span data-ttu-id="8d21a-167">Para filtrar datos analíticos de la capa</span><span class="sxs-lookup"><span data-stu-id="8d21a-167">To filter analytical data for the layer</span></span>  
  
1.  <span data-ttu-id="8d21a-168">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-168">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-169">Haga clic con el botón derecho en el panel Mapa y, después, haga clic en  **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-169">Right-click the layer in the Map pane, and then click  **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="8d21a-170">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-170">Click **Filters**.</span></span>  
  
4.  <span data-ttu-id="8d21a-171">Defina una ecuación de filtro para limitar los datos analíticos que se usan en la presentación del mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-171">Define a filter equation to limit the analytical data that is used in the map display.</span></span> <span data-ttu-id="8d21a-172">Para más información, vea [Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8d21a-172">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-control-point-properties-for-a-point-layer-or-for-polygon-center-points"></a><a name="PointProperties"></a> <span data-ttu-id="8d21a-173">Para controlar las propiedades del punto para una capa de punto o para puntos centrales de polígonos</span><span class="sxs-lookup"><span data-stu-id="8d21a-173">To control point properties for a point layer or for polygon center points</span></span>  
  
1.  <span data-ttu-id="8d21a-174">Seleccione **General** en el cuadro de diálogo **Propiedades de punto de mapa** para cambiar las opciones de etiqueta, información sobre herramientas y tipo de marcador de los elementos de mapa siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d21a-174">Select **General** on the **Map Point Properties** dialog box to change label, tooltip, and marker type options for the following map elements:</span></span>  
  
    -   <span data-ttu-id="8d21a-175">Todos los puntos dinámicos o incrustados de una capa de punto.</span><span class="sxs-lookup"><span data-stu-id="8d21a-175">All dynamic or embedded points on a point layer.</span></span> <span data-ttu-id="8d21a-176">Las reglas de color, reglas de tamaño y reglas de tipo de marcador de los puntos invalidan estas opciones.</span><span class="sxs-lookup"><span data-stu-id="8d21a-176">Color rules, size rules, and marker type rules for points override these options.</span></span> <span data-ttu-id="8d21a-177">Para invalidar las opciones de un punto incrustado concreto, utilice la página [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="8d21a-177">To override options for a specific embedded point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  
  
    -   <span data-ttu-id="8d21a-178">El punto central de todos los polígonos dinámicos o incrustados de una capa de polígono.</span><span class="sxs-lookup"><span data-stu-id="8d21a-178">The center point for all dynamic or embedded polygons on a polygon layer.</span></span> <span data-ttu-id="8d21a-179">Las reglas de color, reglas de tamaño y reglas de tipo de marcador de los puntos centrales invalidan estas opciones.</span><span class="sxs-lookup"><span data-stu-id="8d21a-179">Color rules, size rules, and marker type rules for center points override these options.</span></span> <span data-ttu-id="8d21a-180">Para invalidar las opciones de un punto central concreto, use la página [Cuadro de diálogo de Propiedades de punto incrustado de mapa, Marcador](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="8d21a-180">To override options for a specific center point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  

##  <a name="to-specify-embedded-data-as-a-source-of-spatial-data"></a><a name="Embedded"></a> <span data-ttu-id="8d21a-181">Para especificar datos incrustados como un origen de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="8d21a-181">To specify embedded data as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="8d21a-182">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-182">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-183">Haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-183">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="8d21a-184">En **Usar datos espaciales de**, seleccione **Datos incrustado en informe**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-184">In **Use spatial data from**, select **Data embedded in report**.</span></span>  
  
4.  <span data-ttu-id="8d21a-185">Para cargar los elementos de mapa de un informe existente o crearlos según un archivo ESRI, haga clic en **Examinar**, señale el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-185">To load map elements from an existing report or to create map elements based on an ESRI file, click **Browse**, point to the file, and then click **Open**.</span></span> <span data-ttu-id="8d21a-186">Los elementos de mapa se incrustan en esta definición de informe.</span><span class="sxs-lookup"><span data-stu-id="8d21a-186">The map elements are embedded in this report definition.</span></span> <span data-ttu-id="8d21a-187">Los datos espaciales que señale deben coincidir con el tipo de capa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-187">The spatial data that you point to must match the layer type.</span></span> <span data-ttu-id="8d21a-188">Por ejemplo, para una capa de punto, debe señalar datos espaciales que especifiquen conjuntos de coordenadas de punto.</span><span class="sxs-lookup"><span data-stu-id="8d21a-188">For example, for a point layer, you must point to spatial data that specifies sets of point coordinates.</span></span>  
  
5.  <span data-ttu-id="8d21a-189">En **Campo espacial**, especifique el nombre del campo que contenga los datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="8d21a-189">In **Spatial field**, specify the name of the field that contains spatial data.</span></span> <span data-ttu-id="8d21a-190">Puede que tenga que determinar este nombre desde el origen de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="8d21a-190">You might need to determine this name from the source of spatial data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d21a-191">Si no sabe el nombre del campo y buscó un archivo de forma ESRI, use la opción **Vínculo a archivo de forma ESRI** en lugar de esta.</span><span class="sxs-lookup"><span data-stu-id="8d21a-191">If you do not know the name of the field and you browsed to an ESRI Shapefile, use the **Link to ESRI shape file option** instead of this option.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-an-esri-shapefile-as-a-source-of-spatial-data"></a><a name="ESRI"></a> <span data-ttu-id="8d21a-192">Especificar un archivo de forma ESRI como un origen de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="8d21a-192">To specify an ESRI Shapefile as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="8d21a-193">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-193">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-194">Haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-194">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="8d21a-195">En **Usar datos espaciales de**, seleccione **Vínculo a archivo de forma ESRI**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-195">In **Use spatial data from**, select **Link to ESRI Shapefile**.</span></span>  
  
4.  <span data-ttu-id="8d21a-196">En **Nombre de archivo**, escriba la ubicación del archivo de forma ESRI o haga clic en **Examinar** para seleccionar un archivo de forma ESRI.</span><span class="sxs-lookup"><span data-stu-id="8d21a-196">In **File name**, type the location of an ESRI Shapefile, or click **Browse** to select an ESRI Shapefile.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d21a-197">Si el archivo de forma está en el equipo local, los datos espaciales se incrustan en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="8d21a-197">If the Shapefile is on your local computer, the spatial data is embedded in the report definition.</span></span> <span data-ttu-id="8d21a-198">Para recuperar los datos dinámicamente cuando se procesa el informe, debe cargar el archivo de forma ESRI .shp y su archivo auxiliar .dbf en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8d21a-198">To retrieve the data dynamically when the report is processed, you must upload the ESRI .shp file and its .dbf support file to the report server.</span></span> <span data-ttu-id="8d21a-199">Para obtener más información, vea cómo cargar un archivo o informe (Administrador de informes) en la [documentación de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) , en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d21a-199">For more information, see " How to: Upload a File or Report (Report Manager)" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-report-dataset-field-as-a-source-of-spatial-data"></a><a name="DatasetField"></a> <span data-ttu-id="8d21a-200">Especificar un campo de conjunto de datos de informe como un origen de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="8d21a-200">To specify a report dataset field as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="8d21a-201">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-201">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-202">Haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-202">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="8d21a-203">En **Usar los datos espaciales de**, seleccione **Campo espacial en un conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-203">In **Use spatial data from**, select **Spatial field in a dataset**.</span></span>  
  
4.  <span data-ttu-id="8d21a-204">En **Nombre del conjunto de datos**, haga clic en el nombre de un conjunto de datos en el informe que contenga los datos espaciales que desea.</span><span class="sxs-lookup"><span data-stu-id="8d21a-204">In **Dataset name**, click the name of a dataset in the report that contains that spatial data that you want.</span></span>  
  
5.  <span data-ttu-id="8d21a-205">En **Nombre de campo espacial**, haga clic en el nombre del campo en el conjunto de datos que contenga los datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="8d21a-205">In **Spatial field name**, click the name of the field in the dataset that contains spatial data.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-add-a-tile-layer"></a><a name="TileLayer"></a> <span data-ttu-id="8d21a-206">Agregar una capa de mosaico</span><span class="sxs-lookup"><span data-stu-id="8d21a-206">To add a tile layer</span></span>  
  
1.  <span data-ttu-id="8d21a-207">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-207">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-208">En la barra de herramientas, haga clic en el botón **Agregar capa** y, en la lista desplegable, haga clic en **Capa de mosaico**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-208">On the toolbar, click the **Add Layer** button, and from the drop-down list, click **Tile Layer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d21a-209"> Para obtener más información sobre el uso de mosaicos de Bing Maps en un informe, vea [Condiciones adicionales de uso](https://go.microsoft.com/fwlink/?LinkId=151371) y [Declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=151372).</span><span class="sxs-lookup"><span data-stu-id="8d21a-209">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
3.  <span data-ttu-id="8d21a-210">Haga clic con el botón derecho en la capa de mosaico en el panel Mapa y, después, haga clic en **Propiedades del mosaico**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-210">Right-click the tile layer in the Map pane, and then click **Tile Properties**.</span></span>  
  
4.  <span data-ttu-id="8d21a-211">En **Opciones de mosaico**, seleccione un estilo de mosaico.</span><span class="sxs-lookup"><span data-stu-id="8d21a-211">In **Tile options**, select a tile style.</span></span> <span data-ttu-id="8d21a-212">Si los mosaicos de Bing Maps están disponibles, la capa de la superficie de diseño se actualizará con el estilo que seleccione.</span><span class="sxs-lookup"><span data-stu-id="8d21a-212">If the Bing map tiles are available, the layer on the design surface updates with the style that you select.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d21a-213">Se puede agregar también una capa de mosaico al agregar una capa de polígono, línea o punto en el Asistente para mapas o en el Asistente para capas de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-213">A tile layer can also be added when you add a polygon, line, or point layer in the Map or Map Layer wizard.</span></span> <span data-ttu-id="8d21a-214">En la página **Elegir opciones de datos espaciales y vista de mapa** , seleccione la opción **Agregar un fondo de Bing Maps a esta vista del mapa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-214">On the **Choose spatial data and map view options** page, select the option **Add a Bing Maps background for this map view**.</span></span>  

##  <a name="to-change-the-drawing-order-of-a-layer"></a><a name="DrawingOrder"></a> <span data-ttu-id="8d21a-215">Cambiar el orden del dibujo de una capa</span><span class="sxs-lookup"><span data-stu-id="8d21a-215">To change the drawing order of a layer</span></span>  
  
1.  <span data-ttu-id="8d21a-216">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-216">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-217">Haga clic en la capa en el panel Mapa para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="8d21a-217">Click the layer in the Map pane to select it.</span></span>  
  
3.  <span data-ttu-id="8d21a-218">En la barra de herramientas del panel Mapa, haga clic en la flecha arriba o abajo para cambiar el orden de dibujo de cada capa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-218">On the Map pane toolbar, click the up or down arrow to change the drawing order of each layer.</span></span>  

##  <a name="to-change-the-transparency-of-a-polygon-line-or-point-layer"></a><a name="Transparency"></a> <span data-ttu-id="8d21a-219">Cambiar la transparencia de una capa de polígono, línea o punto</span><span class="sxs-lookup"><span data-stu-id="8d21a-219">To change the transparency of a polygon, line, or point layer</span></span>  
  
1.  <span data-ttu-id="8d21a-220">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-220">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-221">Haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-221">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="8d21a-222">Haga clic en `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="8d21a-222">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="8d21a-223">En **Opciones de transparencia**, escriba un valor que represente la transparencia en porcentaje, por ejemplo **40**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-223">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span> <span data-ttu-id="8d21a-224">Un transparencia de cero (0)% significa que la capa es opaca.</span><span class="sxs-lookup"><span data-stu-id="8d21a-224">Zero (0) % transparency means that the layer is opaque.</span></span> <span data-ttu-id="8d21a-225">Una transparencia de 100% significa que la capa no se verá en el informe.</span><span class="sxs-lookup"><span data-stu-id="8d21a-225">100% transparency means that you will not see the layer in the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-change-the-transparency-of-a-tile-layer"></a><a name="TileTransparency"></a> <span data-ttu-id="8d21a-226">Cambiar la transparencia de una capa de mosaico</span><span class="sxs-lookup"><span data-stu-id="8d21a-226">To change the transparency of a tile layer</span></span>  
  
1.  <span data-ttu-id="8d21a-227">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-227">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-228">Haga clic con el botón derecho en la capa y, después, haga clic en **Propiedades del mosaico**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-228">Right-click the layer, and then click **Tile Properties**.</span></span>  
  
3.  <span data-ttu-id="8d21a-229">Haga clic en `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="8d21a-229">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="8d21a-230">En **Opciones de transparencia**, escriba un valor que represente la transparencia en porcentaje, por ejemplo **40**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-230">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-secure-connection-for-a-tile-layer"></a><a name="Secure"></a> <span data-ttu-id="8d21a-231">Especificar una conexión segura para una capa de mosaico</span><span class="sxs-lookup"><span data-stu-id="8d21a-231">To specify a secure connection for a tile layer</span></span>  
  
1.  <span data-ttu-id="8d21a-232">Haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-232">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="8d21a-233">En el panel Mapa, haga clic en la capa de mosaico para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="8d21a-233">In the Map pane, click the tile layer to select it.</span></span> <span data-ttu-id="8d21a-234">El panel Propiedades muestra las propiedades de la capa de mosaico.</span><span class="sxs-lookup"><span data-stu-id="8d21a-234">The Properties pane displays the tile layer properties.</span></span>  
  
3.  <span data-ttu-id="8d21a-235">En el panel Propiedades, establezca UseSecureConnection en **True**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-235">In the Properties pane, set UseSecureConnection to **True**.</span></span>  
  
 <span data-ttu-id="8d21a-236">La conexión para el servicio web de Bing Maps utilizará el servicio SSL (Capa de sockets seguros) de HTTP para recuperar mosaicos de Bing Maps para esta capa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-236">The connection for the Bing Maps Web service will use the HTTP SSL (Secure Sockets Layer) service to retrieve Bing map tiles for this layer.</span></span>  

##  <a name="to-specify-the-language-for-tile-labels"></a><a name="Language"></a> <span data-ttu-id="8d21a-237">Especificar el idioma de las etiquetas de mosaico</span><span class="sxs-lookup"><span data-stu-id="8d21a-237">To specify the language for tile labels</span></span>  
  
1.  <span data-ttu-id="8d21a-238">De forma predeterminada, en los estilos de mosaico que muestran etiquetas, el idioma se determina con la configuración regional predeterminada para el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="8d21a-238">By default, for tile styles that display labels, the language is determined from the default locale for Report Builder.</span></span> <span data-ttu-id="8d21a-239">Puede personalizar la configuración de idioma para las etiquetas de mosaico de las maneras siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d21a-239">You can customize the language setting for tile labels in the following ways.</span></span>  
  
    -   <span data-ttu-id="8d21a-240">Haga clic en el mapa fuera de la ventanilla para seleccionar el mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-240">Click the map outside the viewport to select the map.</span></span> <span data-ttu-id="8d21a-241">En el panel Propiedades, para la propiedad TileLanguage seleccione un valor de referencia cultural en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d21a-241">In the Properties pane, for the TileLanguage property, select a culture value from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="8d21a-242">Haga clic en el fondo del informe para seleccionar el informe.</span><span class="sxs-lookup"><span data-stu-id="8d21a-242">Click the report background to select the report.</span></span> <span data-ttu-id="8d21a-243">En el panel Propiedades, para la propiedad Language seleccione un valor de referencia cultural en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d21a-243">In the Properties pane, from for the Language property, select a culture value from the drop-down list.</span></span>  
  
     <span data-ttu-id="8d21a-244">El orden de prioridad para establecer el idioma de la etiqueta de mosaico es la propiedad de informe Language, la configuración regional predeterminada del Generador de informes y la propiedad de mapa TileLanguage.</span><span class="sxs-lookup"><span data-stu-id="8d21a-244">The order of precedence for setting the tile label language is: report property Language, default locale for Report Builder, and map property TileLanguage.</span></span>  

##  <a name="to-conditionally-hide-a-layer-based-on-viewport-zoom-level"></a><a name="ConditionalHide"></a> <span data-ttu-id="8d21a-245">Para ocultar una capa de forma condicional según el nivel de zoom de la ventanilla</span><span class="sxs-lookup"><span data-stu-id="8d21a-245">To conditionally hide a layer based on viewport zoom level</span></span>  
  
1.  <span data-ttu-id="8d21a-246">Establecer `Visibility` opciones para controlar la presentación de una capa de mapa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-246">Set `Visibility` options to control the display for a map layer.</span></span>  
  
    -   <span data-ttu-id="8d21a-247">En el panel Capas de mapa, haga clic con el botón derecho en una capa para seleccionarla y, después, en la barra de herramientas Capas de mapa, haga clic en Propiedades para abrir **Propiedades de capa de mapa**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-247">In the Map Layers pane, right-click a layer to select it, and on the Map Layers toolbar, click Properties to open **Map Layer Properties**.</span></span>  
  
    -   <span data-ttu-id="8d21a-248">Haga clic en `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="8d21a-248">Click `Visibility`.</span></span>  
  
    -   <span data-ttu-id="8d21a-249">En Visibilidad de capas, seleccione **Mostrar u ocultar en función del valor de zoom**.</span><span class="sxs-lookup"><span data-stu-id="8d21a-249">In Layer visibility, select **Show or hide based on zoom value**.</span></span>  
  
    -   <span data-ttu-id="8d21a-250">Escriba los valores mínimo y máximo de zoom para cuando se muestre la capa.</span><span class="sxs-lookup"><span data-stu-id="8d21a-250">Enter minimum and maximum zoom values for when display the layer.</span></span>  
  
    -   <span data-ttu-id="8d21a-251">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8d21a-251">Optional.</span></span> <span data-ttu-id="8d21a-252">Escriba un valor para la transparencia.</span><span class="sxs-lookup"><span data-stu-id="8d21a-252">Enter a value for transparency.</span></span>  
  
     <span data-ttu-id="8d21a-253">También puede ocultar la capa de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="8d21a-253">You can also conditionally hide the layer.</span></span> <span data-ttu-id="8d21a-254">Para obtener más información, vea [Ocultar un elemento &#40;Generador de informes y SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8d21a-254">For more information, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="8d21a-255">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d21a-255">See Also</span></span>  
 <span data-ttu-id="8d21a-256">[Mapas &#40;Generador de informes y SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d21a-256">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8d21a-257">Solucionar problemas de los informes: informes de mapa &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8d21a-257">Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;</span></span>](troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
