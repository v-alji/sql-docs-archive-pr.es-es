---
title: Ver modelos de minería de datos en Visio (complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3c1e63c058295b93e2562c64a6df90a30273a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671190"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a><span data-ttu-id="09364-102">Ver los modelos de minería de datos en Visio (Complementos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="09364-102">Viewing Data Mining Models in Visio (Data Mining Add-ins)</span></span>
  <span data-ttu-id="09364-103">Las formas de Visio para minería de datos le permiten conectarse a un servidor y crear un diagrama que represente un modelo de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="09364-103">The Visio shapes for data mining let you connect to a server and create a diagram representing an existing data mining model.</span></span> <span data-ttu-id="09364-104">Posteriormente, se pueden personalizar los diagramas mediante los controles de Visio, pero también puede explorar en profundidad datos, exponer algunas de las estadísticas subyacentes y trabajar con el modelo subyacente.</span><span class="sxs-lookup"><span data-stu-id="09364-104">The diagrams can then be customized using Visio controls, but you can also drill down into data, expose some of the underlying statistics, and work with the underlying model.</span></span>  
  
## <a name="building-a-model-diagram"></a><span data-ttu-id="09364-105">Crear un diagrama del modelo</span><span class="sxs-lookup"><span data-stu-id="09364-105">Building a Model Diagram</span></span>  
 <span data-ttu-id="09364-106">Al abrir el archivo que contiene las formas de Visio para la minería de datos, el panel **formas** muestra las formas siguientes.</span><span class="sxs-lookup"><span data-stu-id="09364-106">When you open the file containing the Visio shapes for data mining, the **Shapes** pane shows the following shapes.</span></span>  
  
 <span data-ttu-id="09364-107">Si no ve las formas de minería de datos al abrir Visio, abra el archivo de plantilla desde la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="09364-107">If you do not see the data mining shapes when you open Visio, open the template file from the installation folder.</span></span>  
  
 <span data-ttu-id="09364-108">![DM](media/dm-stencil.gif "DM")</span><span class="sxs-lookup"><span data-stu-id="09364-108">![DM](media/dm-stencil.gif "DM")</span></span>  
  
 <span data-ttu-id="09364-109">Para usar una forma, arrástrela hasta la página.</span><span class="sxs-lookup"><span data-stu-id="09364-109">To use a shape, drag it to the page.</span></span> <span data-ttu-id="09364-110">Cada forma abre un asistente diferente que ayuda a seleccionar datos de origen, establecer opciones específicas del tipo de diagrama y especificar sombreado y otras opciones de presentación.</span><span class="sxs-lookup"><span data-stu-id="09364-110">Each of the shapes opens a different wizard, which helps you select source data, set options for the specific diagram type, and specify shading and other display options.</span></span>  
  
 <span data-ttu-id="09364-111">En la tabla siguiente se muestran los tipos de modelos que se pueden usar con cada tipo de diagrama.</span><span class="sxs-lookup"><span data-stu-id="09364-111">The following table lists the types of models that you can use with each type of diagram.</span></span>  
  
|<span data-ttu-id="09364-112">Forma de Visio</span><span class="sxs-lookup"><span data-stu-id="09364-112">Visio shape</span></span>|<span data-ttu-id="09364-113">Modelos admitidos</span><span class="sxs-lookup"><span data-stu-id="09364-113">Supported models</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="09364-114">Árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="09364-114">Decision Tree</span></span>|<span data-ttu-id="09364-115">Esta forma se usa para modelos basados en los algoritmos de árboles de decisión o de regresión linear.</span><span class="sxs-lookup"><span data-stu-id="09364-115">Use this shape for models based on the decision tree or linear regression algorithms.</span></span>|  
|<span data-ttu-id="09364-116">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="09364-116">Dependency Network</span></span>|<span data-ttu-id="09364-117">Esta forma se usa para modelos basados en cualquiera de los algoritmos siguientes: Bayes naive, Árboles de decisión o Reglas de asociación.</span><span class="sxs-lookup"><span data-stu-id="09364-117">Use this shape for models based on any of the following algorithms: Naive Bayes, Decision Trees, or Association Rules.</span></span>|  
|<span data-ttu-id="09364-118">Clúster</span><span class="sxs-lookup"><span data-stu-id="09364-118">Cluster</span></span>|<span data-ttu-id="09364-119">Esta forma se usa para modelos basados en algoritmos de clústeres.</span><span class="sxs-lookup"><span data-stu-id="09364-119">Use this shape for models based on clustering algorithms.</span></span>|  
  
 <span data-ttu-id="09364-120">El asistente puede ofrecer distintas opciones en función del tipo de datos del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="09364-120">Depending on the type of data in your mining model, the wizard may offer different options.</span></span> <span data-ttu-id="09364-121">Por ejemplo, las columnas que contienen números continuos se visualizan de forma diferente que las variables de categorías.</span><span class="sxs-lookup"><span data-stu-id="09364-121">For example, columns that contain continuous numbers are visualized differently than categorical variables.</span></span>  
  
## <a name="working-with-completed-shapes"></a><span data-ttu-id="09364-122">Trabajar con formas completadas</span><span class="sxs-lookup"><span data-stu-id="09364-122">Working with Completed Shapes</span></span>  
 <span data-ttu-id="09364-123">Una vez haya completado el diagrama, puede utilizarlo para examinar el modelo de minería de datos o para mejorara el diagrama e incluirlo en presentaciones.</span><span class="sxs-lookup"><span data-stu-id="09364-123">After the diagram is complete, you can use it to browse the data mining model or enhance the diagram for use in presentations.</span></span>  
  
### <a name="visio-menus"></a><span data-ttu-id="09364-124">Menús de Visio</span><span class="sxs-lookup"><span data-stu-id="09364-124">Visio Menus</span></span>  
 <span data-ttu-id="09364-125">Visio proporciona una variedad de controles de representación, temas y menús contextuales para ayudarle a mejorar los diagramas.</span><span class="sxs-lookup"><span data-stu-id="09364-125">Visio provides a variety of rendering controls, themes, and shortcut menus to help enhance a diagram.</span></span>  
  
-   <span data-ttu-id="09364-126">Los temas de Visio se usan para modificar los colores del diagrama.</span><span class="sxs-lookup"><span data-stu-id="09364-126">Use Visio themes to alter diagram colors.</span></span>  
  
-   <span data-ttu-id="09364-127">Cambie los conectores o el diseño del diagrama.</span><span class="sxs-lookup"><span data-stu-id="09364-127">Change connectors or diagram layout.</span></span>  
  
### <a name="data-mining-menus"></a><span data-ttu-id="09364-128">Menús de minería de datos</span><span class="sxs-lookup"><span data-stu-id="09364-128">Data Mining Menus</span></span>  
 <span data-ttu-id="09364-129">Estas barras de herramientas y elementos de menú los proporcionan los complementos específicos de cada forma o tipo de modelo</span><span class="sxs-lookup"><span data-stu-id="09364-129">These toolbars and menu items are provided by the add-ins that are specific to each shape or model type</span></span>  
  
-   <span data-ttu-id="09364-130">Cada tipo de diagrama tiene un menú contextual para la forma que permite tener acceso a opciones especiales.</span><span class="sxs-lookup"><span data-stu-id="09364-130">Each diagram type has a shortcut menu for the shape that lets you access special options.</span></span> <span data-ttu-id="09364-131">Aunque muchas de las opciones de este menú son comunes para todas las formas de Visio, algunas son exclusivas de las plantillas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="09364-131">Although many options in this menu are common to all Visio shapes, some options are unique to the data mining templates</span></span>  
  
     <span data-ttu-id="09364-132">Por ejemplo, en un diagrama de árbol de decisión, puede hacer clic en un nodo y, después, contraer los nodos secundarios para que el diagrama sea más sencillo, o trasladar los nodos secundarios a otra página distinta.</span><span class="sxs-lookup"><span data-stu-id="09364-132">For example, in a decision tree diagram, you can click an individual node and then collapse the child nodes to make the diagram simpler, or move child nodes to a separate page.</span></span>  
  
-   <span data-ttu-id="09364-133">Dado que la forma está vinculada a los datos del modelo, también se puede realizar cierto nivel de exploración con el diagrama:</span><span class="sxs-lookup"><span data-stu-id="09364-133">Because the shape is bound to the model data, you can also do some amount of exploration using the diagram:</span></span>  
  
     <span data-ttu-id="09364-134">Filtrar los nodos que se muestran, o cambiar el nivel del árbol o la profundidad del gráfico.</span><span class="sxs-lookup"><span data-stu-id="09364-134">Filter the nodes that are displayed, or change the level of the tree or depth of the graph.</span></span>  
  
     <span data-ttu-id="09364-135">Acercar secciones específicas, buscar nodos que contengan un determinado atributo o filtrar un gráfico de dependencias por sus bordes (probabilidad).</span><span class="sxs-lookup"><span data-stu-id="09364-135">Zoom in on specific sections, search for nodes that contain a certain attribute, or filter a dependency graph by its edges (probability).</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="09364-136">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="09364-136">Walkthroughs</span></span>  
 <span data-ttu-id="09364-137">Para obtener ejemplos de cómo trabajar con un diagrama completado y cómo interpretarlo, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="09364-137">For examples of how to work with and interpret a completed diagram, see these topics:</span></span>  
  
 [<span data-ttu-id="09364-138">Tutorial del diagrama del clúster</span><span class="sxs-lookup"><span data-stu-id="09364-138">Cluster Diagram Walkthrough</span></span>](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="09364-139">Tutorial del diagrama de red de dependencias</span><span class="sxs-lookup"><span data-stu-id="09364-139">Dependency Net Diagram Walkthrough</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="09364-140">Tutorial del diagrama de árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="09364-140">Decision Tree Diagram Walkthrough</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a><span data-ttu-id="09364-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09364-141">See Also</span></span>  
 [<span data-ttu-id="09364-142">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="09364-142">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
