---
title: Tutorial del diagrama de red de dependencias (complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, dependency network
- shapes, data mining
- shapes, network
- dependencies
- diagram, dependency network
- data mining layout toolbar
- dependency network
ms.assetid: aac732a8-5262-4649-b7d7-3ccf6f9cfa8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07f97dac7ffb0211f0ff1e1b58c2e0792d026174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676723"
---
# <a name="dependency-network-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="169b3-102">Tutorial del diagrama de red de dependencias (Complementos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="169b3-102">Dependency Network Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="169b3-103">Existen diversos tipos de modelos de minería de datos que usan gráficos de red como una forma para explorar las relaciones entre los datos.</span><span class="sxs-lookup"><span data-stu-id="169b3-103">Several different types of data mining models use a network graph as a way of exploring relationships in the data.</span></span> <span data-ttu-id="169b3-104">Puede importar estos modelos en Visio con la forma **red de dependencias** y, a continuación, seguir personalizando y mejorando el diseño.</span><span class="sxs-lookup"><span data-stu-id="169b3-104">You can import these models into Visio using the **Dependency Network** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="169b3-105">Las **formas de minería de datos para Visio** incluyen los siguientes controles personalizados para trabajar con diagramas de red de dependencias:</span><span class="sxs-lookup"><span data-stu-id="169b3-105">The **Data Mining Shapes for Visio** include the following custom controls for working with dependency network diagrams:</span></span>  
  
-   <span data-ttu-id="169b3-106">Representar controles para el gráfico de red</span><span class="sxs-lookup"><span data-stu-id="169b3-106">Rendering controls for the network graph</span></span>  
  
     <span data-ttu-id="169b3-107">Estas opciones forman parte del asistente que se inician cuando se coloca una forma en el área de trabajo de Visio.</span><span class="sxs-lookup"><span data-stu-id="169b3-107">These options are part of the wizard that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="169b3-108">Barra de herramientas de **diseño de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="169b3-108">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="169b3-109">Estas opciones se agregan al área de trabajo de Visio con el fin de ayudarle con el gráfico de red de dependencias.</span><span class="sxs-lookup"><span data-stu-id="169b3-109">These options are added to the Visio workspace to help you interact with the dependency network graph.</span></span>  
  
## <a name="build-a-dependency-network-graph"></a><span data-ttu-id="169b3-110">Generar un gráfico de red de dependencias</span><span class="sxs-lookup"><span data-stu-id="169b3-110">Build a Dependency Network Graph</span></span>  
 <span data-ttu-id="169b3-111">Coloque una forma en la página de Visio para iniciar el **Asistente para crear formas de red de dependencias de .net** y establecer opciones de diagrama.</span><span class="sxs-lookup"><span data-stu-id="169b3-111">You drop a shape onto the Visio page to launch the **Dependency Net Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-dependency-net-visio-shape-wizard"></a><span data-ttu-id="169b3-112">Usar el Asistente para crear formas red de dependencias de Visio</span><span class="sxs-lookup"><span data-stu-id="169b3-112">Use the Dependency Net Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="169b3-113">Si no ve formas de **minería de datos de Microsoft** en la lista **formas** , haga clic en **más formas**, seleccione **Abrir Galería de símbolos**y abra la plantilla desde la ubicación de instalación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="169b3-113">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="169b3-114">\<drive>: \Archivos de programa (x85) \Microsoft SQL Server 2012 DM-ins</span><span class="sxs-lookup"><span data-stu-id="169b3-114">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="169b3-115">Arrastre la forma **red de dependencias** hasta la página para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="169b3-115">Drag the **Dependency Network** shape onto the page to start the wizard.</span></span> <span data-ttu-id="169b3-116">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="169b3-116">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="169b3-117">En la página de bienvenida del **Asistente para crear formas red de dependencias de Visio**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="169b3-117">On the welcome page of the **Dependency Network Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="169b3-118">En la página **seleccionar un origen de datos** del **Asistente para crear formas red de dependencias de Visio**, elija una conexión a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor que tenga el modelo que desea visualizar.</span><span class="sxs-lookup"><span data-stu-id="169b3-118">On the **Select a Data Source** page of the **Dependency Network Visio Shape Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="169b3-119">Seleccione un modelo de minería de datos adecuado y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="169b3-119">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="169b3-120">Para seleccionar un modelo adecuado, puede revisar el nombre, la descripción, las columnas y el tipo de datos en el panel **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="169b3-120">To select an appropriate model, you can review the name, description, columns, and type of data in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="169b3-121">Esta forma admite modelos que se hayan creado con estos algoritmos:</span><span class="sxs-lookup"><span data-stu-id="169b3-121">This shape supports models created by using these algorithms:</span></span>  
  
    -   <span data-ttu-id="169b3-122">Bayes Naive</span><span class="sxs-lookup"><span data-stu-id="169b3-122">Naïve Bayes</span></span>  
  
    -   <span data-ttu-id="169b3-123">Árboles de decisión</span><span class="sxs-lookup"><span data-stu-id="169b3-123">Decision Trees</span></span>  
  
    -   <span data-ttu-id="169b3-124">Reglas de asociación</span><span class="sxs-lookup"><span data-stu-id="169b3-124">Association Rules</span></span>  
  
6.  <span data-ttu-id="169b3-125">En la página, **Seleccione los nodos que se van a representar**, personalice el tamaño del gráfico y, si lo desea, filtre solo para incluir determinados nodos.</span><span class="sxs-lookup"><span data-stu-id="169b3-125">On the page, **Select Nodes to Render**, customize the size of the graph, and optionally filter to only include certain nodes.</span></span>  
  
     <span data-ttu-id="169b3-126">Con un conjunto de objetos grande, un gráfico de dependencias puede ser enorme y contener muchos objetos relacionados, representados como *nodos*.</span><span class="sxs-lookup"><span data-stu-id="169b3-126">With a large dataset, a dependency graph can become huge, and contain many related objects, represented as *nodes*.</span></span> <span data-ttu-id="169b3-127">Mediante este cuadro de diálogo, podrá crear un gráfico de red personalizado que incluya solo los nodos de interés.</span><span class="sxs-lookup"><span data-stu-id="169b3-127">By using this dialog box, you can create a custom network graph that includes only the nodes of interest.</span></span>  
  
     <span data-ttu-id="169b3-128">[marcador de posición Art]</span><span class="sxs-lookup"><span data-stu-id="169b3-128">[art placeholder]</span></span>  
  
     <span data-ttu-id="169b3-129">**Número de nodos que va a capturar**</span><span class="sxs-lookup"><span data-stu-id="169b3-129">**Number of nodes to fetch**</span></span>  
     <span data-ttu-id="169b3-130">Si el modelo contiene menos nodos de los que se ha especificado, este valor no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="169b3-130">If the model contains fewer than the specified number of nodes, this setting has no effect.</span></span> <span data-ttu-id="169b3-131">Si el modelo contiene más nodos de los que se han especificado, solo se mostrarán los nodos más determinantes.</span><span class="sxs-lookup"><span data-stu-id="169b3-131">If the model contains more nodes than the specified number, only the strongest nodes are displayed.</span></span>  
  
     <span data-ttu-id="169b3-132">**El nombre contiene**</span><span class="sxs-lookup"><span data-stu-id="169b3-132">**Name contains**</span></span>  
     <span data-ttu-id="169b3-133">Deje este cuadro en blanco y haga clic en la flecha verde para recuperar todos los nodos del modelo.</span><span class="sxs-lookup"><span data-stu-id="169b3-133">Leave this box blank and click the green arrow to retrieve all nodes in the model.</span></span>  
  
     <span data-ttu-id="169b3-134">O bien, escriba una cadena y haga clic en la flecha verde para devolver solo los nodos que contienen la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="169b3-134">Or, type a string and click the green arrow to return only those nodes that contain the specified string.</span></span>  
  
     <span data-ttu-id="169b3-135">La mayoría de los modelos que puede crear con los datos de ejemplo no son grandes, por lo tanto, para este ejemplo, incremente el número de nodos a 10 y haga clic en la flecha verde para ejecutar una consulta y obtener la lista de todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="169b3-135">Most of the models that you can create with the sample data are not big, so for this example, increase the number of nodes to 10, and then click the green arrow to run a query and get the list of all nodes.</span></span>  
  
7.  <span data-ttu-id="169b3-136">Haga clic en **avanzadas** para establecer las opciones de sombreado y forma del gráfico.</span><span class="sxs-lookup"><span data-stu-id="169b3-136">Click **Advanced** to set shading and shape options for the graph.</span></span>  
  
8.  <span data-ttu-id="169b3-137">Haga clic en **cerrar** para salir del cuadro de diálogo Opciones **avanzadas** y, a continuación, haga clic en **Finalizar** para crear el gráfico.</span><span class="sxs-lookup"><span data-stu-id="169b3-137">Click **Close** to exit the **Advanced** options dialog box, and then click **Finish** to create the graph.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="169b3-138">Explorar y modificar el diagrama finalizado</span><span class="sxs-lookup"><span data-stu-id="169b3-138">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="169b3-139">Una vez que Visio ha creado el gráfico de red de dependencias, podrá proseguir con la modificación y mejora del gráfico mediante las características de Visio.</span><span class="sxs-lookup"><span data-stu-id="169b3-139">After Visio has created the network dependency graph, you can continue to modify and enhance the graph by using the features in Visio.</span></span>  
  
 <span data-ttu-id="169b3-140">El gráfico siguiente muestra el diseño predeterminado de un gráfico de red de dependencias.</span><span class="sxs-lookup"><span data-stu-id="169b3-140">The following graphic shows the default layout of a dependency network graph.</span></span>  
  
 <span data-ttu-id="169b3-141">[marcador de posición Art]</span><span class="sxs-lookup"><span data-stu-id="169b3-141">[art placeholder]</span></span>  
  
1.  <span data-ttu-id="169b3-142">Use el control **panorámica y zoom** , en el área del **Panel de tareas** de la cinta de opciones **vista** de Visio, para centrarse en una sección del gráfico y desplazarse por el diagrama.</span><span class="sxs-lookup"><span data-stu-id="169b3-142">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a section of the graph and move around the diagram.</span></span>  
  
2.  <span data-ttu-id="169b3-143">Experimente con distintos diseños de gráfico proporcionados por la opción **de página rediseño** de Visio.</span><span class="sxs-lookup"><span data-stu-id="169b3-143">Experiment with different graph layouts provided by the Visio **Re-Layout Page** option.</span></span>  
  
3.  <span data-ttu-id="169b3-144">Haga clic en la cinta de opciones de **Complementos** y, a continuación, muestre una de las barras de herramientas personalizadas que se usan para trabajar con diagramas de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="169b3-144">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="169b3-145">**Diseño**</span><span class="sxs-lookup"><span data-stu-id="169b3-145">**Layout**</span></span>  
     <span data-ttu-id="169b3-146">Optimiza el diseño de los nodos en la página y cambia la vista de manera que todos los nodos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="169b3-146">Optimizes the layout of nodes on the page, and changes the view so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="169b3-147">**Cambiar tamaño de página**</span><span class="sxs-lookup"><span data-stu-id="169b3-147">**Resize Page**</span></span>  
     <span data-ttu-id="169b3-148">Cambia el tamaño de la página de manera que todos los nodos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="169b3-148">Changes the size of the page so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="169b3-149">**Intensidad del borde**</span><span class="sxs-lookup"><span data-stu-id="169b3-149">**Edge Strength**</span></span>  
     <span data-ttu-id="169b3-150">Alterna la presentación de la intensidad del borde para todo el gráfico.</span><span class="sxs-lookup"><span data-stu-id="169b3-150">Toggles display of edge strength for the entire graph.</span></span> <span data-ttu-id="169b3-151">Un borde es una conexión entre nodos.</span><span class="sxs-lookup"><span data-stu-id="169b3-151">An edge is a connection between nodes.</span></span> <span data-ttu-id="169b3-152">Puede utilizar el control deslizante para filtrar las conexiones que no son fuertes.</span><span class="sxs-lookup"><span data-stu-id="169b3-152">You can use the slider control to filter out connections that are not strong.</span></span>  
  
     <span data-ttu-id="169b3-153">**Control deslizante**</span><span class="sxs-lookup"><span data-stu-id="169b3-153">**Slider**</span></span>  
     <span data-ttu-id="169b3-154">El **control deslizante** le ayuda a controlar la intensidad de las relaciones que se muestran en el diagrama de red de dependencias.</span><span class="sxs-lookup"><span data-stu-id="169b3-154">The **Slider** helps you control the strength of the relationships that are displayed in the dependency network diagram.</span></span>  
  
     <span data-ttu-id="169b3-155">Cada nodo del gráfico representa un estado.</span><span class="sxs-lookup"><span data-stu-id="169b3-155">Each node in the graph represents a state.</span></span> <span data-ttu-id="169b3-156">Una flecha representa una transición entre dos estados y la probabilidad asociada a la transición.</span><span class="sxs-lookup"><span data-stu-id="169b3-156">An arrow represents a transition between two states and the probability that is associated with the transition.</span></span> <span data-ttu-id="169b3-157">Para reducir el número de nodos del gráfico, mueva la barra del control deslizante hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="169b3-157">To reduce the number of nodes in the graph, move the slider bar up.</span></span>  
  
     <span data-ttu-id="169b3-158">Para aumentar el número de nodos del gráfico, mueva la barra del control deslizante hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="169b3-158">To increase the number of nodes in the graph, move the slider bar down.</span></span>  
  
     <span data-ttu-id="169b3-159">**Agregar elementos**</span><span class="sxs-lookup"><span data-stu-id="169b3-159">**Add Items**</span></span>  
     <span data-ttu-id="169b3-160">Abre el cuadro de diálogo **seleccionar los nodos que se van a representar** para que pueda seleccionar los nuevos nodos que desea agregar al gráfico.</span><span class="sxs-lookup"><span data-stu-id="169b3-160">Opens the **Select Nodes to Render** dialog box so that you can select new nodes to add to the graph.</span></span>  
  
4.  <span data-ttu-id="169b3-161">Puede hacer que los gráficos sean todo lo sencillos o elaborados que desee, así como agregar anotaciones mientras está conectado al modelo.</span><span class="sxs-lookup"><span data-stu-id="169b3-161">You can make the graphs as simple or elaborate as you like, and add annotations, while staying connected to the model.</span></span>  
  
     <span data-ttu-id="169b3-162">[art placeholder]</span><span class="sxs-lookup"><span data-stu-id="169b3-162">[ art placeholder]</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="169b3-163">El resaltado de los nodos dependientes y otras opciones del menú contextual que estaban disponibles en versiones anteriores de los complementos no funcionan en Office 2013.</span><span class="sxs-lookup"><span data-stu-id="169b3-163">Highlighting of dependent nodes and other shortcut menu options that were available in previous versions of the Add-Ins do not work in Office 2013.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169b3-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="169b3-164">See Also</span></span>  
 [<span data-ttu-id="169b3-165">Solucionar problemas de diagramas de minería de datos de Visio &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="169b3-165">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
