---
title: Tutorial del diagrama del clúster (complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ee8cce3cd2498d765c9b69e7f352b49cb0f115
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670683"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="78382-102">Tutorial del diagrama del clúster (Complementos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="78382-102">Cluster Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="78382-103">Después de crear un modelo de agrupación en clústeres, puede importarlo en Visio con la forma **agrupar** y, a continuación, seguir personalizando y mejorando el diseño.</span><span class="sxs-lookup"><span data-stu-id="78382-103">After you have created a clustering model, you can import it into Visio using the **Cluster** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="78382-104">Las **formas de minería de datos para Visio** incluyen los siguientes controles personalizados para trabajar con diagramas de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="78382-104">The **Data Mining Shapes for Visio** include the following custom controls for working with data mining diagrams:</span></span>  
  
-   <span data-ttu-id="78382-105">Representar los controles del diagrama de clúster</span><span class="sxs-lookup"><span data-stu-id="78382-105">Rendering controls for the cluster diagram</span></span>  
  
     <span data-ttu-id="78382-106">Estas opciones forman parte del **Asistente para clúster** que se inicia cuando se coloca una forma en el área de trabajo de Visio.</span><span class="sxs-lookup"><span data-stu-id="78382-106">These options are part of the **Cluster Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="78382-107">Barra de herramientas de **diseño de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="78382-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="78382-108">Estas opciones se agregan al área de trabajo de Visio con el fin de ayudarle a interactuar con la forma de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="78382-108">These options are added to the Visio workspace to help you interact with the data mining shape.</span></span> <span data-ttu-id="78382-109">Las opciones son diferentes en función del tipo de datos del modelo de minería de datos que esté usando.</span><span class="sxs-lookup"><span data-stu-id="78382-109">The options are different depending on which type of data mining model you are using.</span></span>  
  
## <a name="build-a-cluster-diagram"></a><span data-ttu-id="78382-110">Generar un diagrama de clúster</span><span class="sxs-lookup"><span data-stu-id="78382-110">Build a Cluster Diagram</span></span>  
 <span data-ttu-id="78382-111">Este tutorial muestra cómo crear y personalizar un diagrama de agrupación de clúster en Visio.</span><span class="sxs-lookup"><span data-stu-id="78382-111">This walkthrough demonstrates how to build and customize a clustering diagram in Visio.</span></span>  
  
 <span data-ttu-id="78382-112">Para poder continuar, deberá tener ya disponible un modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="78382-112">To follow along, you should have a clustering model already available.</span></span> <span data-ttu-id="78382-113">Si no tiene un modelo, use el asistente [para clúster &#40;complementos de minería de datos para el Asistente para&#41;de Excel](cluster-wizard-data-mining-add-ins-for-excel.md) y cree un modelo mediante el conjunto de datos de entrenamiento del libro de ejemplo, con todos los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="78382-113">If you do not have a model, use the [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) wizard and create a model using the Training data set in the sample workbook, using all the defaults.</span></span>  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a><span data-ttu-id="78382-114">Usar el Asistente para crear formas clúster de Visio</span><span class="sxs-lookup"><span data-stu-id="78382-114">Use the Cluster Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="78382-115">Si no ve formas de **minería de datos de Microsoft** en la lista **formas** , haga clic en **más formas**, seleccione **Abrir Galería de símbolos**y abra la plantilla desde la ubicación de instalación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="78382-115">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="78382-116">\<drive>: \Archivos de Programa\microsoft SQL Server 2012 DM-ins</span><span class="sxs-lookup"><span data-stu-id="78382-116">\<drive>:\Program files\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="78382-117">Arrastre la forma **clúster** hasta la página.</span><span class="sxs-lookup"><span data-stu-id="78382-117">Drag the **Cluster** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="78382-118">En la página de bienvenida del **Asistente para crear formas clúster de Visio**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78382-118">On the welcome page of the **Cluster Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="78382-119">En la página **seleccionar un origen de datos** del **Asistente para clúster**, elija una conexión a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor que contenga los modelos de minería de datos que desea visualizar.</span><span class="sxs-lookup"><span data-stu-id="78382-119">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that contains the data mining models you want to visualize.</span></span>  
  
5.  <span data-ttu-id="78382-120">Seleccione un modelo de minería de datos adecuado y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78382-120">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="78382-121">Para asegurarse de que elige un modelo de agrupación en clústeres, revise la descripción en el panel **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="78382-121">To make sure you choose a clustering model, review the description in the **Properties** pane.</span></span>  
  
6.  <span data-ttu-id="78382-122">Si la conexión se realiza correctamente, en la página **Opciones del diagrama del clúster**, decida qué tipo de diagrama de clúster desea incluir en la presentación de Visio:</span><span class="sxs-lookup"><span data-stu-id="78382-122">If the connection is successful, on the page, **Options for cluster diagram**, you decide which type of cluster diagram to include in your Visio presentation:</span></span>  
  
     <span data-ttu-id="78382-123">**Mostrar sólo formas de clúster**</span><span class="sxs-lookup"><span data-stu-id="78382-123">**Show cluster shapes only**</span></span>  
     <span data-ttu-id="78382-124">Esta opción crea un diagrama del clúster sencillo, donde cada clúster queda representado por un rectángulo u otra forma que elija</span><span class="sxs-lookup"><span data-stu-id="78382-124">This option creates a simple cluster diagram, with each cluster represented by a rectangle or other shape you choose</span></span>  
  
     <span data-ttu-id="78382-125">**Mostrar clústeres con gráfico de características**</span><span class="sxs-lookup"><span data-stu-id="78382-125">**Show clusters with characteristics chart**</span></span>  
     <span data-ttu-id="78382-126">Esta opción crea el mismo gráfico que anteriormente, pero dentro de las formas habrá histogramas que describen las características del clúster.</span><span class="sxs-lookup"><span data-stu-id="78382-126">This option creates the same chart as above, but inside the shapes are histograms that describe the characteristics of the cluster.</span></span>  
  
     <span data-ttu-id="78382-127">![Ejemplo de gráfico de características de clúster en Visio](media/dm13-visio-cluster-samplecharshape.gif "Ejemplo de gráfico de características de clúster en Visio")</span><span class="sxs-lookup"><span data-stu-id="78382-127">![Example of cluster characteristics chart in Visio](media/dm13-visio-cluster-samplecharshape.gif "Example of cluster characteristics chart in Visio")</span></span>  
  
     <span data-ttu-id="78382-128">**Mostrar clústeres con gráfico de distinción**</span><span class="sxs-lookup"><span data-stu-id="78382-128">**Show clusters with discrimination chart**</span></span>  
     <span data-ttu-id="78382-129">Esta opción crea el mismo gráfico que el diagrama del clúster, pero enumera las características del clúster actual que lo diferencian con mayor claridad de otros clústeres.</span><span class="sxs-lookup"><span data-stu-id="78382-129">This option creates the same chart as the cluster diagram, but instead lists the characteristics of the current cluster that most strongly distinguish it from other clusters.</span></span>  
  
     <span data-ttu-id="78382-130">Puede cambiar a otro tipo de gráfico después de que el asistente haya generado el diagrama; para ello, haga clic con el botón secundario y seleccione un tipo de gráfico nuevo.</span><span class="sxs-lookup"><span data-stu-id="78382-130">You can switch to another chart type after the wizard has built the diagram, by right-clicking a cluster and selecting a new chart type.</span></span> <span data-ttu-id="78382-131">Por ahora, elija la opción **Mostrar clústeres con el gráfico de características**.</span><span class="sxs-lookup"><span data-stu-id="78382-131">For now, choose the option, **Show clusters with characteristics chart**.</span></span>  
  
7.  <span data-ttu-id="78382-132">Deje la opción **número de filas en el gráfico**, como 5.</span><span class="sxs-lookup"><span data-stu-id="78382-132">Leave the option, **Number of rows in the chart**, as 5.</span></span>  
  
     <span data-ttu-id="78382-133">Esta opción no cambia el número de clústeres del modelo; simplemente limita el número de atributos que se pueden mostrar como características de cada clúster.</span><span class="sxs-lookup"><span data-stu-id="78382-133">This option doesn't change the number of clusters in the model; it simply limits the number of attributes that can be displayed as features of each cluster.</span></span>  
  
     <span data-ttu-id="78382-134">Sin embargo, la opción actúa como filtro en los datos del gráfico, por lo que no puede aumentar el número de elementos más adelante.</span><span class="sxs-lookup"><span data-stu-id="78382-134">However, the option acts as a filter on the chart data, so you can't increase the number of items later.</span></span>  
  
8.  <span data-ttu-id="78382-135">Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="78382-135">Click **Advanced**.</span></span>  
  
     <span data-ttu-id="78382-136">El cuadro de diálogo **Opciones de clúster** es donde se personaliza la apariencia visual de las formas utilizadas en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="78382-136">The **Cluster Options** dialog box is where you customize the visual appearance of shapes used in the diagram.</span></span> <span data-ttu-id="78382-137">Puede cambiar los colores que se usan en el gráfico, así como las formas de los clústeres.</span><span class="sxs-lookup"><span data-stu-id="78382-137">You can change the colors used in the graph, and the shape used for clusters.</span></span>  
  
     <span data-ttu-id="78382-138">El control de **variable de sombreado** no funciona en Office 2013.</span><span class="sxs-lookup"><span data-stu-id="78382-138">The **Shading Variable** control does not work in Office 2013.</span></span>  
  
     <span data-ttu-id="78382-139">![hacer clic en Avanzadas para seleccionar colores de forma](media/dm13-visio-clusteroptions-advanced.gif "hacer clic en Avanzadas para seleccionar colores de forma")</span><span class="sxs-lookup"><span data-stu-id="78382-139">![click Advanced to choose shape colors](media/dm13-visio-clusteroptions-advanced.gif "click Advanced to choose shape colors")</span></span>  
  
     <span data-ttu-id="78382-140">**Sugerencia:** Algunos colores se pueden modificar posteriormente mediante los temas de Visio y los controles de edición de formas.</span><span class="sxs-lookup"><span data-stu-id="78382-140">**Tip:** Some colors can be altered later by using Visio themes and shape editing controls.</span></span> <span data-ttu-id="78382-141">Sin embargo, los temas de Visio también invalidarán algunas de estas selecciones de color, por lo que se recomienda comenzar con los colores predeterminados e ir aplicando cambios paulatinamente.</span><span class="sxs-lookup"><span data-stu-id="78382-141">However, Visio themes will also override some of these color selections, so we recommend starting with the default colors and gradually applying changes.</span></span>  
  
9. <span data-ttu-id="78382-142">Haga clic en **Finalizar** para crear el gráfico.</span><span class="sxs-lookup"><span data-stu-id="78382-142">Click **Finish** to create the graph.</span></span>  
  
     <span data-ttu-id="78382-143">El asistente recupera información del modelo de minería de datos, crea las formas y rellena cada clúster con atributos y valores.</span><span class="sxs-lookup"><span data-stu-id="78382-143">The wizard retrieves information from the data mining model, renders the shapes, and populates each cluster with attributes and values.</span></span>  
  
     <span data-ttu-id="78382-144">![una red de dependencias](media/dm13-visiodepnet-defaultgraph.gif "una red de dependencias")</span><span class="sxs-lookup"><span data-stu-id="78382-144">![a dependency network](media/dm13-visiodepnet-defaultgraph.gif "a dependency network")</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="78382-145">Explorar y modificar el diagrama finalizado</span><span class="sxs-lookup"><span data-stu-id="78382-145">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="78382-146">Una vez haya completado el diagrama, puede seguir personalizando la apariencia mediante los controles de Visio, tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78382-146">After the diagram is complete, you can continue to customize the appearance using the Visio controls, as shown in the following example.</span></span>  
  
 <span data-ttu-id="78382-147">![Diagrama de clúster personalizado con Visio](media/dm13-visio-clustercomplete1.gif "Diagrama de clúster personalizado con Visio")</span><span class="sxs-lookup"><span data-stu-id="78382-147">![cluster diagram customized using Visio](media/dm13-visio-clustercomplete1.gif "cluster diagram customized using Visio")</span></span>  
  
 <span data-ttu-id="78382-148">El asistente genera todas las formas básicas de clústeres; use las herramientas siguientes para actualizar y personalizar el diagrama:</span><span class="sxs-lookup"><span data-stu-id="78382-148">All of the basic cluster shapes are generated by the wizard; use the following tools to update and personalize the diagram:</span></span>  
  
1.  <span data-ttu-id="78382-149">Arrastre el control deslizante del control **Opciones de clúster** para filtrar las relaciones más débiles y simplificar el diagrama.</span><span class="sxs-lookup"><span data-stu-id="78382-149">Drag the slider in the **Cluster Options** control, to filter out weaker relationships and simplify the diagram.</span></span>  
  
2.  <span data-ttu-id="78382-150">Use la opción **de página rediseño** de Visio para experimentar con distintos diseños de clúster.</span><span class="sxs-lookup"><span data-stu-id="78382-150">Use the Visio **Re-Layout Page** option to experiment with different cluster layouts.</span></span>  
  
3.  <span data-ttu-id="78382-151">Use la opción **conectores** en la pestaña **diseño** para cambiar el estilo del conector y evitar que las líneas crucen los clústeres.</span><span class="sxs-lookup"><span data-stu-id="78382-151">Use the **Connectors** option on the **Design** tab to change the connector style to keep lines from crossing over clusters.</span></span>  
  
4.  <span data-ttu-id="78382-152">Haga clic en la cinta de opciones de **Complementos** y, a continuación, muestre una de las barras de herramientas personalizadas que se usan para trabajar con diagramas de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="78382-152">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="78382-153">**Diseño**</span><span class="sxs-lookup"><span data-stu-id="78382-153">**Layout**</span></span>  
     <span data-ttu-id="78382-154">Optimiza la organización de los clústeres para que se ajusten en la página actual.</span><span class="sxs-lookup"><span data-stu-id="78382-154">Optimizes the arrangement of clusters to fit in the current page.</span></span>  
  
     <span data-ttu-id="78382-155">**Cambiar tamaño de página**</span><span class="sxs-lookup"><span data-stu-id="78382-155">**Resize Page**</span></span>  
     <span data-ttu-id="78382-156">Este control se ha diseñado para la versiones anteriores de HTML.</span><span class="sxs-lookup"><span data-stu-id="78382-156">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="78382-157">En su lugar, use la página de Visio para cambiar el tamaño de los controles.</span><span class="sxs-lookup"><span data-stu-id="78382-157">Use the Visio page resizing controls instead.</span></span>  
  
     <span data-ttu-id="78382-158">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="78382-158">**Description**</span></span>  
     <span data-ttu-id="78382-159">Si selecciona un clúster, haga clic en esta opción para mostrar los detalles sobre el clúster.</span><span class="sxs-lookup"><span data-stu-id="78382-159">If a cluster is selected, click this option to display details about the cluster.</span></span>  
  
     <span data-ttu-id="78382-160">![hacer clic en Descripción para obtener detalles acerca del clúster](media/dm13-visio-cluster-description-control.gif "hacer clic en Descripción para obtener detalles acerca del clúster")</span><span class="sxs-lookup"><span data-stu-id="78382-160">![click Description to get details about the cluster](media/dm13-visio-cluster-description-control.gif "click Description to get details about the cluster")</span></span>  
  
     <span data-ttu-id="78382-161">**Intensidad del borde**</span><span class="sxs-lookup"><span data-stu-id="78382-161">**Edge Strength**</span></span>  
     <span data-ttu-id="78382-162">Muestra las puntuaciones de confianza en las líneas que conectan los clústeres.</span><span class="sxs-lookup"><span data-stu-id="78382-162">Displays confidence scores on the lines connecting clusters.</span></span>  
  
     <span data-ttu-id="78382-163">Sin embargo, si aplica algún formato especial distinto del predeterminado que genera el asistente, lo cual incluye algunos fondos, es posible que estos números no estén visibles.</span><span class="sxs-lookup"><span data-stu-id="78382-163">However, if you apply any special formatting other than the default generated by the wizard, including some backgrounds, these numbers might not be visible.</span></span>  
  
     <span data-ttu-id="78382-164">**Control deslizante**</span><span class="sxs-lookup"><span data-stu-id="78382-164">**Slider**</span></span>  
     <span data-ttu-id="78382-165">Filtra las líneas entre los clústeres.</span><span class="sxs-lookup"><span data-stu-id="78382-165">Filters the lines between clusters.</span></span> <span data-ttu-id="78382-166">Si se sube el control deslizante, se quitan todas las asociaciones salvo las más importantes.</span><span class="sxs-lookup"><span data-stu-id="78382-166">Moving the slider up removes all but the most important associations.</span></span>  
  
     <span data-ttu-id="78382-167">**Sombreado**</span><span class="sxs-lookup"><span data-stu-id="78382-167">**Shading**</span></span>  
     <span data-ttu-id="78382-168">Este control no funciona en Office 2013.</span><span class="sxs-lookup"><span data-stu-id="78382-168">This control does not work in Office 2013.</span></span>  
  
5.  <span data-ttu-id="78382-169">Use el control **panorámica y zoom** , en el área del **Panel de tareas** de la cinta de opciones **vista** de Visio, para centrarse en un conjunto de clústeres y desplazarse por el diagrama.</span><span class="sxs-lookup"><span data-stu-id="78382-169">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a set of clusters and move around the diagram.</span></span>  
  
6.  <span data-ttu-id="78382-170">Haga clic con el botón secundario en cualquier clúster para ver las opciones específicas de la forma del clúster:</span><span class="sxs-lookup"><span data-stu-id="78382-170">Right-click any cluster to see options specific to the cluster shape:</span></span>  
  
    -   <span data-ttu-id="78382-171">Cambie el tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="78382-171">Change the chart style.</span></span>  
  
    -   <span data-ttu-id="78382-172">Agregue un gráfico de características de clúster.</span><span class="sxs-lookup"><span data-stu-id="78382-172">Add a cluster characteristics chart.</span></span>  
  
    -   <span data-ttu-id="78382-173">Agregue un gráfico de distinción.</span><span class="sxs-lookup"><span data-stu-id="78382-173">Add a cluster discrimination chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78382-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78382-174">See Also</span></span>  
 [<span data-ttu-id="78382-175">Solucionar problemas de diagramas de minería de datos de Visio &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="78382-175">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
