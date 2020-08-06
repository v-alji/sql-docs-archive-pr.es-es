---
title: Cambiar leyendas de mapa, escala de colores y reglas asociadas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.maprulesdistribution.f1
- "10512"
- "10539"
- "10533"
- sql12.rtp.rptdesigner.mappointlayerproperties.typerules.f1
- "10534"
- sql12.rtp.rptdesigner.maplegendproperties.general.f1
- sql12.rtp.rptdesigner.mapdistancescaleproperties.general.f1
- "10516"
- sql12.rtp.rptdesigner.mapcolorscaleproperties.labels.f1
- sql12.rtp.rptdesigner.maplegendtitleproperties.general.f1
- "10514"
- sql12.rtp.rptdesigner.shared.mapruleslegend.f1
- sql12.rtp.rptdesigner.mapcolorscaleproperties.general.f1
- sql12.rtp.rptdesigner.shared.embeddedlabels.f1
- "10513"
- sql12.rtp.rptdesigner.mappointlayerproperties.sizerules.f1
- sql12.rtp.rptdesigner.mapcolorscaletitleproperties.general.f1
- "10510"
- "10509"
- "10540"
- "10517"
ms.assetid: a1d691b2-c5ae-420f-af60-b7c54a7385a4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 17220c12e672ce49d3c5b1023f2a00db04e7613e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670798"
---
# <a name="change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs"></a><span data-ttu-id="9c02e-102">Cambiar leyendas de mapa, escala de colores y reglas asociadas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="9c02e-102">Change Map Legends, Color Scale, and Associated Rules (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9c02e-103">Un mapa puede contener leyendas de mapa, una escala de colores y una escala de distancia.</span><span class="sxs-lookup"><span data-stu-id="9c02e-103">A map can contain map legends, a color scale, and a distance scale.</span></span> <span data-ttu-id="9c02e-104">Estas partes de un mapa ayudan a los usuarios a interpretar la visualización de los datos del mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-104">These parts of a map help users interpret the data visualization on the map.</span></span>  
  
 <span data-ttu-id="9c02e-105">Las leyendas incluyen las siguientes partes de un mapa:</span><span class="sxs-lookup"><span data-stu-id="9c02e-105">Legends include the following parts of a map:</span></span>  
  
-   <span data-ttu-id="9c02e-106">**Leyenda del mapa:** muestra una guía para ayudar a interpretar los datos analíticos que varían la presentación de los elementos de mapa en una capa de mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-106">**Map legend** Displays a guide to help interpret the analytical data that varies the display of a map elements on a map layer.</span></span> <span data-ttu-id="9c02e-107">Un mapa puede tener varias leyendas.</span><span class="sxs-lookup"><span data-stu-id="9c02e-107">A map can have multiple legends.</span></span> <span data-ttu-id="9c02e-108">En cada capa de mapa, especifique qué leyenda se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="9c02e-108">For each map layer, you A specify which legend to use.</span></span> <span data-ttu-id="9c02e-109">Una leyenda puede proporcionar una guía a más de una capa de mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-109">A legend can provide a guide to more than one map layer.</span></span>  
  
-   <span data-ttu-id="9c02e-110">**Escala de color:** Muestra una guía para ayudar a interpretar los colores del mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-110">**Color scale** Displays a guide to help interpret colors on the map.</span></span> <span data-ttu-id="9c02e-111">Un mapa tiene una escala del color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-111">A map has one color scale.</span></span> <span data-ttu-id="9c02e-112">Varios capas pueden proporcionar los datos de la escala de color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-112">Multiple layers can provide the data for the color scale.</span></span>  
  
-   <span data-ttu-id="9c02e-113">**Escala de distancia:** Muestra una guía para ayudar a interpretar la escala del mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-113">**Distance scale** Displays a guide to help interpret the scale of the map.</span></span> <span data-ttu-id="9c02e-114">Un mapa tiene una escala de distancia.</span><span class="sxs-lookup"><span data-stu-id="9c02e-114">A map has one distance scale.</span></span> <span data-ttu-id="9c02e-115">El valor de zoom de la ventanilla central del mapa actual determina la escala de distancia.</span><span class="sxs-lookup"><span data-stu-id="9c02e-115">The current map viewport zoom value determines the distance scale.</span></span>  
  
 <span data-ttu-id="9c02e-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span><span class="sxs-lookup"><span data-stu-id="9c02e-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="9c02e-117">Para cambiar la posición de una leyenda con respecto a la ventanilla</span><span class="sxs-lookup"><span data-stu-id="9c02e-117">To change the position of a legend relative to the viewport</span></span>  
  
#### <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><span data-ttu-id="9c02e-118">Para cambiar la posición de una leyenda con respecto a la ventanilla</span><span class="sxs-lookup"><span data-stu-id="9c02e-118">To change the position of a legend relative to the viewport</span></span>  
  
1.  <span data-ttu-id="9c02e-119">En Vista de diseño, haga clic con el botón secundario en la leyenda y abra la _\<report item->_ página **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="9c02e-119">In Design view, right-click the legend and open the _\<report item->_**Properties** page.</span></span>  
  
2.  <span data-ttu-id="9c02e-120">En **Posición**, haga clic en la ubicación que especifica dónde desea mostrar la leyenda con respecto a la ventanilla.</span><span class="sxs-lookup"><span data-stu-id="9c02e-120">In **Position**, click the location that specifies where to display the legend relative to the viewport.</span></span>  
  
3.  <span data-ttu-id="9c02e-121">Para mostrar la leyenda fuera de la ventanilla, seleccione **Mostrar \<report item> fuera**de la ventanilla.</span><span class="sxs-lookup"><span data-stu-id="9c02e-121">To display the legend outside the viewport, select **Show \<report item> outside viewport**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c02e-122">En la vista previa, las leyendas de mapa y la escala de colores solo aparecen cuando hay resultados de las reglas relacionadas con esa leyenda.</span><span class="sxs-lookup"><span data-stu-id="9c02e-122">In preview, map legends and the color scale appear only when there are results from the rules related to that legend.</span></span> <span data-ttu-id="9c02e-123">Si no hay ningún elemento que mostrarse, la leyenda no aparece en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="9c02e-123">If there are no items to display, the legend does not appear in the rendered report.</span></span>  
  
  
  
##  <a name="to-change-the-layout-of-a-map-legend"></a><a name="MapLegend"></a> <span data-ttu-id="9c02e-124">Cambiar el diseño de la leyenda de un mapa</span><span class="sxs-lookup"><span data-stu-id="9c02e-124">To change the layout of a map legend</span></span>  
  
#### <a name="to-change-the-layout-of-a-map-legend"></a><span data-ttu-id="9c02e-125">Cambiar el diseño de la leyenda de un mapa</span><span class="sxs-lookup"><span data-stu-id="9c02e-125">To change the layout of a map legend</span></span>  
  
1.  <span data-ttu-id="9c02e-126">En la vista Diseño, haga clic con el botón derecho en la leyenda y, después, abra la página **Propiedades de la leyenda** .</span><span class="sxs-lookup"><span data-stu-id="9c02e-126">In Design view, right-click the legend and open the **Legend Properties** page.</span></span>  
  
2.  <span data-ttu-id="9c02e-127">En **Diseño de la leyenda**, haga clic en el diseño de la tabla que desea utilizar para la leyenda.</span><span class="sxs-lookup"><span data-stu-id="9c02e-127">In **Legend layout**, click the table layout that you want to use for the legend.</span></span> <span data-ttu-id="9c02e-128">Según haga clic en las diferentes opciones, cambiará la disposición de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="9c02e-128">As you click different options, the layout on the design surface changes.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-show-or-hide-a-map-legend-title"></a><a name="MapLegendTitle"></a> <span data-ttu-id="9c02e-129">Mostrar u ocultar el título de una leyenda de mapa</span><span class="sxs-lookup"><span data-stu-id="9c02e-129">To show or hide a map legend title</span></span>  
  
#### <a name="to-show-or-hide-a-map-legend-title"></a><span data-ttu-id="9c02e-130">Mostrar u ocultar el título de una leyenda de mapa</span><span class="sxs-lookup"><span data-stu-id="9c02e-130">To show or hide a map legend title</span></span>  
  
-   <span data-ttu-id="9c02e-131">Haga clic con el botón derecho en la leyenda de mapa en la superficie de diseño y, después, haga clic en **Mostrar título de leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-131">Right-click the map legend on the design surface, and then click **Show Legend Title**.</span></span>  
  
  
  
##  <a name="to-show-or-hide-a-color-scale-title"></a><a name="ColorScaleTitle"></a> <span data-ttu-id="9c02e-132">Mostrar u ocultar el título de una escala de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-132">To show or hide a color scale title</span></span>  
  
#### <a name="to-show-or-hide-a-color-scale-title"></a><span data-ttu-id="9c02e-133">Mostrar u ocultar el título de una escala de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-133">To show or hide a color scale title</span></span>  
  
-   <span data-ttu-id="9c02e-134">Haga clic con el botón derecho en la escala de colores en la superficie de diseño y, después, haga clic en **Mostrar título de escala de colores**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-134">Right-click the color scale on the design surface, and then click **Show Color Scale Title**.</span></span>  
  
  
  
##  <a name="to-move-items-out-of-the-first-legend"></a><a name="MoveItems"></a> <span data-ttu-id="9c02e-135">Sacar elementos de la primera leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-135">To move items out of the first legend</span></span>  
 <span data-ttu-id="9c02e-136">Cree tantas leyendas adicionales cuando necesite y, a continuación, actualice las reglas para cada capa de mapa especificando qué leyenda muestran los resultados de la regla.</span><span class="sxs-lookup"><span data-stu-id="9c02e-136">Create as many additional legends as you need and then update the rules for each map layer specify which legend to display the rule results in.</span></span>  
  
#### <a name="to-create-a-new-legend"></a><span data-ttu-id="9c02e-137">Crear una nueva leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-137">To create a new legend</span></span>  
  
-   <span data-ttu-id="9c02e-138">En la vista Diseño, haga clic con el botón derecho fuera de la ventanilla del mapa y, después, haga clic en **Agregar leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-138">In Design view, right-click the map outside the map viewport, and then click **Add Legend**.</span></span>  
  
     <span data-ttu-id="9c02e-139">Una nueva leyenda aparece en el mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-139">A new legend appears on the map.</span></span>  
  
#### <a name="to-display-rule-results-in-a-legend"></a><span data-ttu-id="9c02e-140">Mostrar los resultados de la regla en una leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-140">To display rule results in a legend</span></span>  
  
1.  <span data-ttu-id="9c02e-141">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-141">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-142">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-142">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-143">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-143">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="9c02e-144">En la lista desplegable **Mostrar en esta leyenda** , haga clic en el nombre de la leyenda para mostrar los resultados de la regla.</span><span class="sxs-lookup"><span data-stu-id="9c02e-144">In the **Show in this legend** drop-down list, click the name of the legend to display the rule results in.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-a-template-style"></a><a name="TemplateStyle"></a> <span data-ttu-id="9c02e-145">Variar los colores del elemento de mapa según un estilo de plantilla</span><span class="sxs-lookup"><span data-stu-id="9c02e-145">To vary map element colors based on a template style</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-a-template-style"></a><span data-ttu-id="9c02e-146">Variar los colores del elemento de mapa según un estilo de plantilla</span><span class="sxs-lookup"><span data-stu-id="9c02e-146">To vary map element colors based on a template style</span></span>  
  
1.  <span data-ttu-id="9c02e-147">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-147">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-148">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-148">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-149">Haga clic en **Aplicar estilo de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-149">Click **Apply template style**.</span></span>  
  
     <span data-ttu-id="9c02e-150">Un estilo de plantilla especifica una fuente, un estilo de borde y una paleta de colores.</span><span class="sxs-lookup"><span data-stu-id="9c02e-150">A template style specifies font, border style, and color palette.</span></span> <span data-ttu-id="9c02e-151">Cada elemento de mapa tiene asignado un color diferente de la paleta de colores para el tema que se especificó en el Asistente para mapas o en el Asistente para capas de mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-151">Each map element is assigned a different color from the color palette for the theme that was specified in the Map Wizard or Map Layer Wizard.</span></span> <span data-ttu-id="9c02e-152">Esta es la única opción que se aplica a las capas que no tienen asociados datos analíticos.</span><span class="sxs-lookup"><span data-stu-id="9c02e-152">This is the only option that applies to layers that do not have associated analytical data.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-palette"></a><a name="ColorPalette"></a> <span data-ttu-id="9c02e-153">Variar los colores del elemento de mapa según la paleta de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-153">To vary map element colors based on color palette</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-palette"></a><span data-ttu-id="9c02e-154">Variar los colores del elemento de mapa según la paleta de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-154">To vary map element colors based on color palette</span></span>  
  
1.  <span data-ttu-id="9c02e-155">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-155">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-156">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-156">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-157">Haga clic en **Visualizar datos mediante la paleta de colores**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-157">Click **Visualize data by using color palette**.</span></span>  
  
     <span data-ttu-id="9c02e-158">Esta opción usa una paleta integrada o personalizada que especifique.</span><span class="sxs-lookup"><span data-stu-id="9c02e-158">This option uses a built-in or custom palette that you specify.</span></span> <span data-ttu-id="9c02e-159">Según los datos analíticos relacionados, a cada elemento de mapa se le asigna un color o tonalidad de color diferente de la paleta.</span><span class="sxs-lookup"><span data-stu-id="9c02e-159">Based on related analytical data, each map element is assigned a different color or shade of color from the palette.</span></span>  
  
4.  <span data-ttu-id="9c02e-160">En **Campo de datos**, escriba el nombre del campo que contenga los datos analíticos que desea visualizar por color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-160">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="9c02e-161">En **Paleta**, en la lista desplegable, seleccione el nombre de la paleta que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="9c02e-161">In **Palette**, from the drop-down list, select the name of the palette to use.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-ranges"></a><a name="ColorRanges"></a> <span data-ttu-id="9c02e-162">Variar los colores del elemento de mapa según las gamas de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-162">To vary map element colors based on color ranges</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-ranges"></a><span data-ttu-id="9c02e-163">Variar los colores del elemento de mapa según las gamas de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-163">To vary map element colors based on color ranges</span></span>  
  
1.  <span data-ttu-id="9c02e-164">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-164">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-165">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-165">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-166">Haga clic en **Visualizar datos mediante los rangos de colores**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-166">Click **Visualize data by using color ranges**.</span></span>  
  
     <span data-ttu-id="9c02e-167">Esta opción, combinada con los colores inicial, intermedio y final que especifique en esta página y las opciones que especifique en la página **Distribución** , divide los datos analíticos relacionados en rangos.</span><span class="sxs-lookup"><span data-stu-id="9c02e-167">This option, combined with the start, middle, and end colors that you specify on this page and the options that you specify on the **Distribution** page, divide the related analytical data into ranges.</span></span> <span data-ttu-id="9c02e-168">El procesador de informes asigna el color adecuado a cada elemento de mapa en función de sus datos asociados y del intervalo en el que están englobados.</span><span class="sxs-lookup"><span data-stu-id="9c02e-168">The report processor assigns the appropriate color to each map element based on the its associated data and the range that it falls into.</span></span>  
  
4.  <span data-ttu-id="9c02e-169">En **Campo de datos**, escriba el nombre del campo que contenga los datos analíticos que desea visualizar por color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-169">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="9c02e-170">En **Color inicial**, especifique el color que desea utilizar para el intervalo inferior.</span><span class="sxs-lookup"><span data-stu-id="9c02e-170">In **Start color**, specify the color to use for the lowest range.</span></span>  
  
6.  <span data-ttu-id="9c02e-171">En **Color intermedio**, especifique el color que desea utilizar para el intervalo intermedio.</span><span class="sxs-lookup"><span data-stu-id="9c02e-171">In **Middle color**, specify the color to use for the middle range.</span></span>  
  
7.  <span data-ttu-id="9c02e-172">En **Color final**, especifique el color que desea utilizar para el intervalo superior.</span><span class="sxs-lookup"><span data-stu-id="9c02e-172">In **End color**, specify the color to use for the highest range.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-custom-colors"></a><a name="CustomColors"></a> <span data-ttu-id="9c02e-173">Variar los colores del elemento de mapa según los colores personalizados</span><span class="sxs-lookup"><span data-stu-id="9c02e-173">To vary map element colors based on custom colors</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-custom-colors"></a><span data-ttu-id="9c02e-174">Variar los colores del elemento de mapa según los colores personalizados</span><span class="sxs-lookup"><span data-stu-id="9c02e-174">To vary map element colors based on custom colors</span></span>  
  
1.  <span data-ttu-id="9c02e-175">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-175">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-176">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-176">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-177">Haga clic en **Visualizar datos mediante los colores personalizados**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-177">Click **Visualize data by using custom colors**.</span></span>  
  
     <span data-ttu-id="9c02e-178">Esta opción usa la lista de colores que especifique.</span><span class="sxs-lookup"><span data-stu-id="9c02e-178">This option uses the list of colors that you specify.</span></span> <span data-ttu-id="9c02e-179">Según los datos analíticos relacionados, a cada elemento de mapa se le asigna un color de la lista.</span><span class="sxs-lookup"><span data-stu-id="9c02e-179">Based on related analytical data, each map element is assigned a color from the list.</span></span> <span data-ttu-id="9c02e-180">Si hay más elementos de mapa que colores, no se asigna ningún color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-180">If there are more map elements than colors, no color is assigned.</span></span>  
  
4.  <span data-ttu-id="9c02e-181">En **Campo de datos**, escriba el nombre del campo que contenga los datos analíticos que desea visualizar por color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-181">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="9c02e-182">En **Colores personalizados**, haga clic en **Agregar** para especificar cada color personalizado.</span><span class="sxs-lookup"><span data-stu-id="9c02e-182">In **Custom colors**, click **Add** to specify each custom color.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-set-distribution-options-for-a-legend"></a><a name="DistributionOptions"></a> <span data-ttu-id="9c02e-183">Establecer las opciones de distribución de una leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-183">To set distribution options for a legend</span></span>  
  
#### <a name="to-set-distribution-options-for-a-legend"></a><span data-ttu-id="9c02e-184">Establecer las opciones de distribución de una leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-184">To set distribution options for a legend</span></span>  
  
1.  <span data-ttu-id="9c02e-185">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-185">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-186">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-186">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-187">Seleccione la opción **visualizar datos mediante el uso** de \<rule type\> .</span><span class="sxs-lookup"><span data-stu-id="9c02e-187">Select the **Visualize data by using** \<rule type\> option.</span></span> <span data-ttu-id="9c02e-188">Para utilizar las opciones de distribución, debe crear intervalos en la página **Distribución** según los datos analíticos asociados a la capa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-188">To use distribution options, you must create ranges on the **Distribution** page based on analytical data that is associated with the layer.</span></span>  
  
4.  <span data-ttu-id="9c02e-189">Haga clic en **Distribución**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-189">Click **Distribution**.</span></span>  
  
5.  <span data-ttu-id="9c02e-190">Seleccione uno de los tipos de distribución siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c02e-190">Select one of the following distribution types:</span></span>  
  
    -   <span data-ttu-id="9c02e-191">**EqualInterval**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-191">**EqualInterval**.</span></span> <span data-ttu-id="9c02e-192">Especifica intervalos que dividen los datos en subintervalos iguales.</span><span class="sxs-lookup"><span data-stu-id="9c02e-192">Specifies ranges that divide the data into equal range intervals.</span></span>  
  
    -   <span data-ttu-id="9c02e-193">**EqualDistribution**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-193">**EqualDistribution**.</span></span> <span data-ttu-id="9c02e-194">Especifica intervalos que dividen los datos de modo que cada intervalo tenga un número igual de elementos.</span><span class="sxs-lookup"><span data-stu-id="9c02e-194">Specifies ranges that divide that data so that each range has an equal number of items.</span></span>  
  
    -   <span data-ttu-id="9c02e-195">**Óptimo**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-195">**Optimal**.</span></span> <span data-ttu-id="9c02e-196">Especifica intervalos que ajustan automáticamente la distribución para crear subintervalos equilibrados.</span><span class="sxs-lookup"><span data-stu-id="9c02e-196">Specifies ranges that automatically adjust distribution to create balanced subranges.</span></span>  
  
    -   <span data-ttu-id="9c02e-197">**Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-197">**Custom**.</span></span> <span data-ttu-id="9c02e-198">Especifique su propio número de intervalos para controlar la distribución de valores.</span><span class="sxs-lookup"><span data-stu-id="9c02e-198">Specify your own number of ranges to control the distribution of values.</span></span>  
  
     <span data-ttu-id="9c02e-199">Para obtener más información sobre las opciones de distribución, vea [Variar la presentación de polígonos, líneas y puntos usando reglas y datos analíticos &#40;Generador de informes y SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="9c02e-199">For more information about distribution options, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
6.  <span data-ttu-id="9c02e-200">En **Número de subrangos**, escriba el número de subrangos que va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="9c02e-200">In **Number of subranges**, type the number of subranges to use.</span></span> <span data-ttu-id="9c02e-201">Cuando el tipo de distribución es **Óptimo**, el número de subrangos se calcula automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9c02e-201">When the distribution type is **Optimal**, the number of subranges is automatically calculated.</span></span>  
  
7.  <span data-ttu-id="9c02e-202">En **Inicio de intervalo**, escriba el valor mínimo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="9c02e-202">In **Range start**, type a minimum range value.</span></span> <span data-ttu-id="9c02e-203">Todos los valores menores que este número son el mismo que el mínimo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="9c02e-203">All values less than this number are the same as the range minimum.</span></span>  
  
8.  <span data-ttu-id="9c02e-204">En **Final de intervalo**, escriba el valor máximo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="9c02e-204">In **Range end**, type a maximum range value.</span></span> <span data-ttu-id="9c02e-205">Todos los valores mayores que este número son el mismo que el máximo del rango.</span><span class="sxs-lookup"><span data-stu-id="9c02e-205">All values larger than this number are the same as the range maximum.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-a-rule-legend"></a><a name="RuleLegend"></a> <span data-ttu-id="9c02e-206">Cambiar el contenido de una leyenda de la regla</span><span class="sxs-lookup"><span data-stu-id="9c02e-206">To change the contents of a rule legend</span></span>  
  
#### <a name="to-change-the-contents-of-a-color-size-width-or-marker-type-legend"></a><span data-ttu-id="9c02e-207">Cambiar el contenido de una leyenda de tipo de color, tamaño, ancho o marcador</span><span class="sxs-lookup"><span data-stu-id="9c02e-207">To change the contents of a color, size, width, or marker type legend</span></span>  
  
1.  <span data-ttu-id="9c02e-208">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-208">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-209">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-209">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-210">Compruebe que se ha seleccionado **visualizar datos mediante el uso de** \<*rule type*> .</span><span class="sxs-lookup"><span data-stu-id="9c02e-210">Verify that **Visualize data by using** \<*rule type*> is selected.</span></span>  
  
4.  <span data-ttu-id="9c02e-211">En **Campo de datos**, compruebe que los datos analíticos que está visualizando en la capa están seleccionados.</span><span class="sxs-lookup"><span data-stu-id="9c02e-211">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c02e-212">Si no aparece ningún campo en la lista desplegable, haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa** para abrir la página Datos analíticos del cuadro de diálogo Propiedades de datos de capa de mapa y comprobar que ha especificado los datos analíticos para esta capa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-212">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="9c02e-213">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-213">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="9c02e-214">En **Mostrar en esta leyenda**, seleccione la leyenda de mapa que desea utilizar para mostrar los resultados de la regla.</span><span class="sxs-lookup"><span data-stu-id="9c02e-214">In **Show in this legend**, select the map legend to use to display the rule results.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-the-color-scale"></a><a name="ColorScale"></a> <span data-ttu-id="9c02e-215">Cambiar los contenidos de la escala de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-215">To change the contents of the color scale</span></span>  
  
#### <a name="to-change-the-contents-of-the-color-scale-or-a-color-legend"></a><span data-ttu-id="9c02e-216">Para cambiar el contenido de la escala de colores o una leyenda de regla de colores</span><span class="sxs-lookup"><span data-stu-id="9c02e-216">To change the contents of the color scale or a color legend</span></span>  
  
1.  <span data-ttu-id="9c02e-217">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-217">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-218">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla de color**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-218">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-219">Seleccione la opción de regla de color que desee usar.</span><span class="sxs-lookup"><span data-stu-id="9c02e-219">Select the color rule option to use.</span></span> <span data-ttu-id="9c02e-220">Para mostrar los elementos en una leyenda de mapa o escala de colores, debe seleccionar una de las opciones de **visualizar datos mediante** \<rule type> .</span><span class="sxs-lookup"><span data-stu-id="9c02e-220">To display items in a map legend or color scale, you must select one of the **Visualize data by using** \<rule type> options.</span></span>  
  
4.  <span data-ttu-id="9c02e-221">En **Campo de datos**, compruebe que los datos analíticos que está visualizando en la capa están seleccionados.</span><span class="sxs-lookup"><span data-stu-id="9c02e-221">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c02e-222">Si no aparece ningún campo en la lista desplegable, haga clic con el botón derecho en la capa y, después, haga clic en **Datos de la capa** para abrir la página Datos analíticos del cuadro de diálogo Propiedades de datos de capa de mapa y comprobar que ha especificado los datos analíticos para esta capa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-222">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="9c02e-223">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-223">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="9c02e-224">En **Opciones de escala de colores**, seleccione **Mostrar en escala de colores** para mostrar los resultados de la regla en la escala de colores.</span><span class="sxs-lookup"><span data-stu-id="9c02e-224">In **Color scale options**, select **Show in color scale** to display the rule results in the color scale.</span></span> <span data-ttu-id="9c02e-225">Puede especificar esta opción para más de una regla de color.</span><span class="sxs-lookup"><span data-stu-id="9c02e-225">You can specify this option for more than one color rule.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-remove-all-items-from-a-legend"></a><a name="HideItems"></a> <span data-ttu-id="9c02e-226">Quitar todos los elementos de una leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-226">To remove all items from a legend</span></span>  
  
#### <a name="to-hide-items-based-on-a-rule"></a><span data-ttu-id="9c02e-227">Ocultar elementos basados en una regla</span><span class="sxs-lookup"><span data-stu-id="9c02e-227">To hide items based on a rule</span></span>  
  
1.  <span data-ttu-id="9c02e-228">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-228">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-229">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-229">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-230">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-230">Click **Legend**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-format-of-content-in-a-legend"></a><a name="ChangeFormatItems"></a> <span data-ttu-id="9c02e-231">Cambiar el formato del contenido de una leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-231">To change the format of content in a legend</span></span>  
 <span data-ttu-id="9c02e-232">Establezca las opciones de leyenda para la regla que está asociada a la leyenda de mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-232">Set legend options for the rule that is associated with the map legend.</span></span>  
  
#### <a name="to-change-the-format-of-content-in-a-legend"></a><span data-ttu-id="9c02e-233">Cambiar el formato del contenido de una leyenda</span><span class="sxs-lookup"><span data-stu-id="9c02e-233">To change the format of content in a legend</span></span>  
  
1.  <span data-ttu-id="9c02e-234">En la vista Diseño, haga clic en el mapa hasta que aparezca el panel Mapa.</span><span class="sxs-lookup"><span data-stu-id="9c02e-234">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="9c02e-235">Haga clic con el botón secundario en la capa que tenga los datos que desee y, a continuación, haga clic en _\<map element type\>_ **regla**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-235">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="9c02e-236">Haga clic en **Leyenda**.</span><span class="sxs-lookup"><span data-stu-id="9c02e-236">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="9c02e-237">**Texto de leyenda** muestra las palabras clave que especifican qué datos aparecen en la leyenda.</span><span class="sxs-lookup"><span data-stu-id="9c02e-237">**Legend text** displays keywords that specify which data appears in the legend.</span></span> <span data-ttu-id="9c02e-238">Use las palabras clave y los formatos personalizados para ayudar a controlar el formato del texto de la leyenda.</span><span class="sxs-lookup"><span data-stu-id="9c02e-238">Use map keywords and custom formats to help control the format of legend text.</span></span> <span data-ttu-id="9c02e-239">Por ejemplo, #FROMVALUE {C2} especifica un formato de moneda con dos posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="9c02e-239">For example, #FROMVALUE {C2} specifies a currency format with two decimal places.</span></span> <span data-ttu-id="9c02e-240">Para obtener más información, vea [Variar la presentación de polígonos, líneas y puntos usando reglas y datos analíticos &#40;Generador de informes y SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="9c02e-240">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="9c02e-241">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c02e-241">See Also</span></span>  
 <span data-ttu-id="9c02e-242">[Mapas &#40;Generador de informes y SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9c02e-242">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9c02e-243">[Agregar, cambiar o eliminar un mapa o una capa de mapa &#40;Generador de informes y SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9c02e-243">[Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9c02e-244">[Personalizar los datos y la presentación de un mapa o una capa de mapa &#40;Generador de informes y SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9c02e-244">[Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9c02e-245">[Solucionar problemas de los informes: informes de mapa &#40;Generador de informes y SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9c02e-245">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9c02e-246">Asistente para mapas y Asistente para capas de mapa &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9c02e-246">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  
