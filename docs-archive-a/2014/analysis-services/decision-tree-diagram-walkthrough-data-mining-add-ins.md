---
title: Tutorial del diagrama de árbol de decisión (complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- shapes, data mining
- diagram, decision tree
- Visio shapes, decision tree
- decision tree [data mining]
ms.assetid: 9566f6a2-c750-4125-ba5e-42c7251a78c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: bbe54db1ab3d00d074917db770a9a731f884f49a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671812"
---
# <a name="decision-tree-diagram-walkthrough--data-mining-add-ins"></a><span data-ttu-id="fc3fa-102">Tutorial del diagrama de árbol de decisión (complementos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="fc3fa-102">Decision Tree Diagram Walkthrough  (Data Mining Add-ins)</span></span>
  <span data-ttu-id="fc3fa-103">Si ha creado un modelo de árbol de decisión, podrá crear un diagrama personalizado en Visio con la forma Árbol de decisión o la forma Red de dependencias.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-103">If you have created a decision tree model, you can create a customized diagram in Visio by using either the Decision Tree shape or the Dependency Network shape.</span></span> <span data-ttu-id="fc3fa-104">En este tema se describen las personalizaciones que puede realizar con la forma **árbol de decisión** y estos controles:</span><span class="sxs-lookup"><span data-stu-id="fc3fa-104">This topic describes the customizations you can perform using the **Decision Tree** shape and these controls:</span></span>  
  
-   <span data-ttu-id="fc3fa-105">Representar los controles del diagrama de árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="fc3fa-105">Rendering controls for the decision tree diagram</span></span>  
  
     <span data-ttu-id="fc3fa-106">Estas opciones forman parte del **Asistente para árbol de decisión** que se inicia cuando se coloca una forma en el área de trabajo de Visio.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-106">These options are part of the **Decision Tree Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="fc3fa-107">Barra de herramientas de **diseño de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="fc3fa-108">Estas opciones se agregan al área de trabajo de Visio con el fin de ayudarle a interactuar con la forma.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-108">These options are added to the Visio workspace to help you interact with the shape.</span></span>  
  
## <a name="build-a-decision-tree-diagram"></a><span data-ttu-id="fc3fa-109">Generar un diagrama de árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="fc3fa-109">Build a Decision Tree Diagram</span></span>  
 <span data-ttu-id="fc3fa-110">Coloque la forma árbol de decisión en la página de Visio para iniciar el **Asistente para crear formas árbol de decisión de Visio** y establecer las opciones del diagrama.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-110">You drop the Decision Tree shape onto the Visio page to launch the **Decision Tree Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-decision-tree-wizard"></a><span data-ttu-id="fc3fa-111">Usar el Asistente para árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="fc3fa-111">Use the Decision Tree Wizard</span></span>  
  
1.  <span data-ttu-id="fc3fa-112">Si no ve formas de **minería de datos de Microsoft** en la lista **formas** , haga clic en **más formas**, seleccione **Abrir Galería de símbolos**y abra la plantilla desde la ubicación de instalación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-112">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="fc3fa-113">\<drive>: \Archivos de programa (x85) \Microsoft SQL Server 2012 DM-ins</span><span class="sxs-lookup"><span data-stu-id="fc3fa-113">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="fc3fa-114">Arrastre la forma **árbol de decisión** hasta la página.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-114">Drag the **Decision Tree** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="fc3fa-115">En la página de bienvenida del **Asistente para crear formas árbol de decisión de Visio**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-115">On the welcome page of the **Decision Tree Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="fc3fa-116">En la página **seleccionar un origen de datos** del **Asistente para clúster**, elija una conexión a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor que tenga el modelo que desea visualizar.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-116">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="fc3fa-117">Seleccione un modelo de minería de datos adecuado y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-117">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="fc3fa-118">Este tipo de diagrama admite modelos creados mediante el algoritmo de árboles de decisión o de regresión lineal.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-118">This diagram type supports models created using the Decision Trees or Linear Regression algorithm.</span></span>  
  
6.  <span data-ttu-id="fc3fa-119">En la página **Seleccionar árbol de decisión** , elija un árbol individual para mostrar.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-119">On the **Select Decision Tree** page, choose an individual tree to display.</span></span>  
  
     <span data-ttu-id="fc3fa-120">Un árbol modela las interacciones que conducen a un resultado determinado que se ha modelado. por lo tanto, incluso si el modelo contiene varios resultados, solo puede mostrar un árbol cada vez.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-120">A tree models the interactions that lead to a particular outcome you've modeled; therefore, even if your model contains multiple outcomes, you can display only one tree at a time.</span></span>  
  
7.  <span data-ttu-id="fc3fa-121">En el cuadro de diálogo **Seleccionar árbol de decisión** , también puede establecer estas opciones de representación:</span><span class="sxs-lookup"><span data-stu-id="fc3fa-121">In the **Select Decision Tree** dialog box, you can also set these rendering options:</span></span>  
  
     <span data-ttu-id="fc3fa-122">**Profundidad máxima de representación**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-122">**Maximum Rendering Depth**</span></span>  
     <span data-ttu-id="fc3fa-123">Esta opción se usa para controlar la cantidad de nodos que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-123">Use this option to control how many nodes are displayed.</span></span>  
  
     <span data-ttu-id="fc3fa-124">Un árbol de decisión puede ser muy profundo y crear un diagrama que no cabe en la página.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-124">A decision tree might go very deep, creating a diagram that does not fit on the page.</span></span> <span data-ttu-id="fc3fa-125">Este control se usa para centrarse en los nodos del extremo izquierdo, que son los más importantes.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-125">Use this control to focus on the leftmost nodes, which are more important.</span></span>  
  
     <span data-ttu-id="fc3fa-126">El valor predeterminado es tres niveles de nodos.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-126">The default is three levels of nodes.</span></span>  
  
     <span data-ttu-id="fc3fa-127">**Seleccionar un color y un texto para los valores**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-127">**Select color and display text for values**</span></span>  
     <span data-ttu-id="fc3fa-128">Elija el color que representará cada uno de los resultados.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-128">Choose the color that will represent each one of the outcomes.</span></span> <span data-ttu-id="fc3fa-129">Si no especifica colores, se generan automáticamente mediante los colores del tema de vídeo.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-129">If you do not specify colors, they are automatically generated using the current video theme colors.</span></span>  
  
8.  <span data-ttu-id="fc3fa-130">Haga clic en **avanzadas** para personalizar las siguientes opciones para cada uno de los nodos del diagrama de árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-130">Click **Advanced** to customize the following options for each of the nodes in the decision tree diagram.</span></span>  
  
     <span data-ttu-id="fc3fa-131">**Variable de sombreado** y **Estado**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-131">**Shading Variable** and **State**</span></span>  
     <span data-ttu-id="fc3fa-132">Elija el resultado de destino que desea mostrar en el diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-132">Choose the target outcome that you want to show in the tree diagram.</span></span>  
  
     <span data-ttu-id="fc3fa-133">**Mostrar histograma**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-133">**Show Histogram**</span></span>  
     <span data-ttu-id="fc3fa-134">Agrega un gráfico a cada nodo que muestra las reglas que definen el nodo.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-134">Adds a chart to each node that shows the rules that define that node.</span></span>  
  
     <span data-ttu-id="fc3fa-135">**Mostrar etiqueta**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-135">**Show Label**</span></span>  
     <span data-ttu-id="fc3fa-136">Agrega nombres de columna al histograma.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-136">Adds column names to the histogram.</span></span>  
  
     <span data-ttu-id="fc3fa-137">**Mostrar la probabilidad**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-137">**Show Probability**</span></span>  
     <span data-ttu-id="fc3fa-138">Muestra la probabilidad de cada valor.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-138">Displays the probability of each value.</span></span>  
  
     <span data-ttu-id="fc3fa-139">**Mostrar compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-139">**Show Support**</span></span>  
     <span data-ttu-id="fc3fa-140">Muestra el soporte de cada valor.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-140">Displays the support for each value.</span></span>  
  
     <span data-ttu-id="fc3fa-141">**Mostrar pie**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-141">**Show Footer**</span></span>  
     <span data-ttu-id="fc3fa-142">Agrega un pie de página que reúne a todos los valores mostrados.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-142">Adds a footer that sums all displayed values.</span></span>  
  
     <span data-ttu-id="fc3fa-143">**Mostrar encabezado**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-143">**Show Header**</span></span>  
     <span data-ttu-id="fc3fa-144">Agrega encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-144">Adds column headings.</span></span>  
  
     <span data-ttu-id="fc3fa-145">**Mostrar estados con compatibilidad cero**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-145">**Show states with zero support**</span></span>  
     <span data-ttu-id="fc3fa-146">Permite mostrar los valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-146">Lets you display missing values.</span></span>  
  
9. <span data-ttu-id="fc3fa-147">Haga clic en **Finalizar** para crear el gráfico.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-147">Click **Finish** to create the graph.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="fc3fa-148">En algunos entornos, los conectores del gráfico podrían producir errores de representación en Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-148">In some environments, connectors in the chart might fail to render in Office 2013.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="fc3fa-149">Explorar y modificar el diagrama finalizado</span><span class="sxs-lookup"><span data-stu-id="fc3fa-149">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="fc3fa-150">Después de haber completado el **Asistente para crear formas árbol de decisión de Visio**, Visio crea un diagrama de árbol en la página que muestra gráficamente las reglas que conducen al resultado predicho.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-150">After you have completed the **Decision Tree Visio Shape Wizard**, Visio creates a tree diagram on the page that graphically displays the rules that lead to the predicted outcome.</span></span>  
  
 <span data-ttu-id="fc3fa-151">Puede seguir modificando la forma si usa los controles siguientes para diagramas de árbol de decisión:</span><span class="sxs-lookup"><span data-stu-id="fc3fa-151">You can continue to modify the shape by using the following controls for decision tree diagrams:</span></span>  
  
#### <a name="using-the-decision-tree-option-menus"></a><span data-ttu-id="fc3fa-152">Usar los menús de opción del árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="fc3fa-152">Using the decision tree option menus</span></span>  
  
1.  <span data-ttu-id="fc3fa-153">Haga clic en la cinta de opciones de **Complementos** y, a continuación, muestre una de las barras de herramientas personalizadas que se usan para trabajar con diagramas de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="fc3fa-153">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="fc3fa-154">**Diseño**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-154">**Layout**</span></span>  
     <span data-ttu-id="fc3fa-155">Optimiza la organización del árbol para que se ajuste a la página actual.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-155">Optimizes the arrangement of the tree to fit the current page.</span></span>  
  
     <span data-ttu-id="fc3fa-156">**Cambiar tamaño de página**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-156">**Resize Page**</span></span>  
     <span data-ttu-id="fc3fa-157">Este control se ha diseñado para la versiones anteriores de HTML.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-157">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="fc3fa-158">En su lugar, use la página de Visio para cambiar el tamaño de los controles.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-158">Use the Visio page resizing controls instead,</span></span>  
  
     <span data-ttu-id="fc3fa-159">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-159">**Description**</span></span>  
     <span data-ttu-id="fc3fa-160">Cuando se selecciona un nodo del árbol, haga clic en esta opción para mostrar los detalles sobre los casos del nodo.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-160">When a node of the tree is selected, click this option to display details about the cases in the node.</span></span>  
  
2.  <span data-ttu-id="fc3fa-161">Use la opción de **Página rediseño** de la cinta de opciones **diseño** de Visio para experimentar con distintos diseños de árbol.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-161">Use the **Re-Layout Page** option in the Visio **Design** ribbon to experiment with different tree layouts.</span></span>  
  
3.  <span data-ttu-id="fc3fa-162">Use la opción **conectores** en la pestaña **diseño** para cambiar los conectores usados entre los nodos del árbol.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-162">Use the **Connectors** option on the **Design** tab to change the connectors used between nodes in the tree.</span></span>  
  
4.  <span data-ttu-id="fc3fa-163">Use el control **panorámica y zoom** , en el área del **Panel de tareas** de la cinta de opciones **vista** de Visio, para centrarse en un área determinada del diagrama.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-163">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a particular area of the diagram.</span></span>  
  
5.  <span data-ttu-id="fc3fa-164">Haga clic con el botón secundario en cualquier nodo del árbol y elija en el menú contextual las opciones específicas de los diagramas de árbol de decisión:</span><span class="sxs-lookup"><span data-stu-id="fc3fa-164">Right-click any node in the tree, and choose from these shortcut menu options specific to decision tree diagrams:</span></span>  
  
     <span data-ttu-id="fc3fa-165">**Mejorar diseño de página**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-165">**Improve Page Layout**</span></span>  
     <span data-ttu-id="fc3fa-166">Distribuye uniformemente los nodos en la página y ajusta la vista de la misma para que se vean todos ellos.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-166">Distributes the nodes evenly on the page and adjusts the page view to see all nodes.</span></span>  
  
     <span data-ttu-id="fc3fa-167">**Mover secundarios a nueva página**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-167">**Move Children to New Page**</span></span>  
     <span data-ttu-id="fc3fa-168">Mueve los elementos secundarios del nodo seleccionado actualmente a una página nueva.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-168">Moves the children of the currently selected node to a new page.</span></span>  
  
     <span data-ttu-id="fc3fa-169">**Contraer nodos secundarios**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-169">**Collapse Child Nodes**</span></span>  
     <span data-ttu-id="fc3fa-170">Oculta los elementos secundarios del nodo seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-170">Hides the children of the currently selected node.</span></span>  
  
     <span data-ttu-id="fc3fa-171">**Expandir nodos secundarios**</span><span class="sxs-lookup"><span data-stu-id="fc3fa-171">**Expand Child Nodes**</span></span>  
     <span data-ttu-id="fc3fa-172">Muestra los nodos secundarios del nodo seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc3fa-172">Displays the children of the currently selected node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3fa-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc3fa-173">See Also</span></span>  
 [<span data-ttu-id="fc3fa-174">Solucionar problemas de diagramas de minería de datos de Visio &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="fc3fa-174">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
