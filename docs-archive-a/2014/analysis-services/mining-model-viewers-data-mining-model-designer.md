---
title: Visores de modelos de minería de datos (diseñador de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.viewers.f1
ms.assetid: 4ba391d5-c97b-4848-ba7c-7d096fa4b7dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4cc1c9d72a08ef49ed2f4f466953d2ba61394178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749518"
---
# <a name="mining-model-viewers-data-mining-model-designer"></a><span data-ttu-id="7556b-102">Visores de modelos de minería de datos (Diseñador de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="7556b-102">Mining Model Viewers (Data Mining Model Designer)</span></span>
  <span data-ttu-id="7556b-103">Use la pestaña **Visor de modelos de minería de datos** para explorar los modelos de minería de datos que contiene una estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7556b-103">Use the **Mining Model Viewer** tab to explore the mining models that a mining structure contains.</span></span>

 <span data-ttu-id="7556b-104">Primero seleccione el modelo de minería de datos y, a continuación, seleccione un visor.</span><span class="sxs-lookup"><span data-stu-id="7556b-104">First you select the mining model and then you select a viewer.</span></span> <span data-ttu-id="7556b-105">Cada modelo siempre tiene dos visores disponibles: un visor personalizado, que puede incluir varias pestañas, y el visor genérico.</span><span class="sxs-lookup"><span data-stu-id="7556b-105">Each model always has two viewers available: a custom viewer, which can include multiple tabs, and the generic viewer.</span></span>

 <span data-ttu-id="7556b-106">Para consultar un tutorial sobre cómo usar cada visor, vea [Visores de modelos de minería de datos](data-mining/data-mining-model-viewers.md).</span><span class="sxs-lookup"><span data-stu-id="7556b-106">For a walkthrough of how to use each viewer, see [Data Mining Model Viewers](data-mining/data-mining-model-viewers.md).</span></span>

## <a name="common-options"></a><span data-ttu-id="7556b-107">Opciones comunes</span><span class="sxs-lookup"><span data-stu-id="7556b-107">Common Options</span></span>
 <span data-ttu-id="7556b-108">**Actualizar el contenido del visor** Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="7556b-108">**Refresh viewer content** Reload the mining model in the viewer.</span></span>

 <span data-ttu-id="7556b-109">**Modelo de minería de datos** Elija esta opción para ver un modelo de minería de datos que se encuentra en la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="7556b-109">**Mining Model** Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="7556b-110">El modelo de minería de datos se abrirá primero en su visor personalizado asociado.</span><span class="sxs-lookup"><span data-stu-id="7556b-110">The mining model will first open in its associated custom viewer.</span></span>

 <span data-ttu-id="7556b-111">**Visor** Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7556b-111">**Viewer** Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="7556b-112">Esta lista incluye los visores que [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proporciona para cada modelo de minería de datos, el [!INCLUDE[msCoName](../includes/msconame-md.md)] visor de contenido de minería de datos y los visores de complementos.</span><span class="sxs-lookup"><span data-stu-id="7556b-112">This list includes the viewers that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides for each mining model, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer, and any plug-in viewers.</span></span>

 <span data-ttu-id="7556b-113">El siguiente diagrama muestra un visor personalizado y el visor genérico para el mismo modelo.</span><span class="sxs-lookup"><span data-stu-id="7556b-113">The following diagram shows a custom viewer and the generic viewer for the same model.</span></span>

-   <span data-ttu-id="7556b-114">El diagrama superior muestra el visor de un modelo de minería de datos basado en el algoritmo de serie temporal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7556b-114">The upper diagram shows the viewer for a mining model based on the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="7556b-115">Este visor personalizado determinado crea automáticamente un gráfico de serie temporal y proporciona cinco predicciones.</span><span class="sxs-lookup"><span data-stu-id="7556b-115">This particular custom viewer automatically creates a graph of the time series and provides five predictions.</span></span>

-   <span data-ttu-id="7556b-116">El diagrama inferior muestra el mismo modelo que se presenta mediante el **Visor de árbol de contenido genérico de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="7556b-116">The lower diagram shows the same model displayed using the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="7556b-117">Este visor muestra el contenido del modelo de minería de datos según un esquema normalizado.</span><span class="sxs-lookup"><span data-stu-id="7556b-117">This viewer presents the contents of the mining model according to a standardized schema.</span></span> <span data-ttu-id="7556b-118">Para más información, vea [Visor de árbol de contenido genérico de Microsoft &#40;minería de datos&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7556b-118">For more information, see [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span></span>

 <span data-ttu-id="7556b-119">![Información general del diseñador del modelo de minería de datos](media/generic-mining-model-tab1.gif "Información general del diseñador del modelo de minería de datos")</span><span class="sxs-lookup"><span data-stu-id="7556b-119">![Overview of mining model designer](media/generic-mining-model-tab1.gif "Overview of mining model designer")</span></span>

## <a name="viewers-and-their-components"></a><span data-ttu-id="7556b-120">Visores y sus componentes</span><span class="sxs-lookup"><span data-stu-id="7556b-120">Viewers and Their Components</span></span>
 <span data-ttu-id="7556b-121">Según el modelo que seleccione, verá un visor personalizado, personalizado para el algoritmo que se usara para crear el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7556b-121">Depending on the model that you select, you will see a different custom viewer, tailored to the algorithm that you used to create the selected data mining model.</span></span> <span data-ttu-id="7556b-122">Cada visor personalizado tiene diversas herramientas y cuadros de diálogo para ayudarle a explorar las estadísticas y los patrones del modelo.</span><span class="sxs-lookup"><span data-stu-id="7556b-122">Each custom viewer has a variety of tools and dialog boxes for helping you explore the statistics and patterns in the model.</span></span>

 <span data-ttu-id="7556b-123">En la lista siguiente se describen las opciones de cada uno de los visores personalizados.</span><span class="sxs-lookup"><span data-stu-id="7556b-123">The following list describes the options in each of the custom viewers.</span></span>

### <a name="microsoft-association-rules-algorithm"></a><span data-ttu-id="7556b-124">Algoritmo de reglas de asociación de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-124">Microsoft Association Rules Algorithm</span></span>

-   [<span data-ttu-id="7556b-125">Examinar un modelo usando el Visor de reglas de asociación de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-125">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)

    -   [<span data-ttu-id="7556b-126">Pestaña conjuntos &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-126">Itemsets Tab &#40;Mining Model Viewer&#41;</span></span>](itemsets-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-127">Pestaña reglas &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-127">Rules Tab &#40;Mining Model Viewer&#41;</span></span>](rules-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-128">Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-128">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

### <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="7556b-129">Algoritmo de clústeres de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-129">Microsoft Clustering Algorithm</span></span>

-   [<span data-ttu-id="7556b-130">Examinar un modelo usando el Visor de clústeres de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-130">Browse a Model Using the Microsoft Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)

    -   [<span data-ttu-id="7556b-131">Pestaña diagrama del clúster &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-131">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-132">Pestaña perfiles del clúster &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-132">Cluster Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-133">Pestaña características del clúster &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-133">Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-134">Pestaña distinción del clúster &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-134">Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-135">Cuadro de diálogo leyenda de minería de datos &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-135">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-decision-tree-algorithm"></a><span data-ttu-id="7556b-136">Algoritmo de árboles de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-136">Microsoft Decision Tree Algorithm</span></span>

-   [<span data-ttu-id="7556b-137">Examinar un modelo usando el Visor de árboles de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-137">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)

    -   [<span data-ttu-id="7556b-138">Pestaña árbol de decisión &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-138">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-139">Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-139">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-140">Cuadro de diálogo leyenda de minería de datos &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-140">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="7556b-141">Algoritmo de regresión lineal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-141">Microsoft Linear Regression Algorithm</span></span>

-   [<span data-ttu-id="7556b-142">Examinar un modelo usando el Visor de redes neuronales de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-142">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="7556b-143">Pestaña árbol de decisión &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-143">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-144">Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-144">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-145">Cuadro de diálogo leyenda de minería de datos &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-145">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-logistic-regression-algorithm"></a><span data-ttu-id="7556b-146">Algoritmo de regresión logística de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-146">Microsoft Logistic Regression Algorithm</span></span>

-   [<span data-ttu-id="7556b-147">Examinar un modelo usando el Visor de redes neuronales de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-147">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

### <a name="microsoft-nave-bayes-algorithm"></a><span data-ttu-id="7556b-148">Algoritmo Bayes naive de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-148">Microsoft Naïve Bayes Algorithm</span></span>

-   [<span data-ttu-id="7556b-149">Examinar un modelo usando el visor Bayes naive de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-149">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)

    -   [<span data-ttu-id="7556b-150">Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-150">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-151">Pestaña perfiles de atributo &#40;el visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-151">Attribute Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-152">Pestaña características del atributo &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-152">Attribute Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-153">Pestaña distinción de atributos &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-153">Attribute Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-discrimination-tab-mining-model-viewer.md)

### <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="7556b-154">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="7556b-154">Microsoft Neural Network Algorithm</span></span>

-   [<span data-ttu-id="7556b-155">Examinar un modelo usando el Visor de redes neuronales de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-155">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="7556b-156">Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-156">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-157">Visor de modelos de minería de datos &#40;de red neuronal&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-157">Neural Network &#40;Mining Model Viewer&#41;</span></span>](neural-network-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-158">Cuadro de diálogo Buscar nodo &#40;el visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-158">Find Node Dialog Box &#40;Mining Model Viewer&#41;</span></span>](find-node-dialog-box-mining-model-viewer.md)

### <a name="microsoft-sequence-clustering-algorithm"></a><span data-ttu-id="7556b-159">Algoritmo de clústeres de secuencia de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-159">Microsoft Sequence Clustering Algorithm</span></span>

-   [<span data-ttu-id="7556b-160">Examinar un modelo usando el Visor de clústeres de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-160">Browse a Model Using the Microsoft Sequence Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)

    -   [<span data-ttu-id="7556b-161">Pestaña diagrama de clústeres de secuencia &#40;visor de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7556b-161">Sequence Clustering Cluster Diagram Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-162">Pestaña perfiles del clúster de clústeres de secuencia &#40;visor de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7556b-162">Sequence Clustering Cluster Profiles Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-163">Pestaña características del clúster de clústeres de secuencia &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-163">Sequence Clustering Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-164">Pestaña distinción del clúster de secuencia de clústeres &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-164">Sequence Clustering Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="7556b-165">Pestaña transición del clúster de clústeres de secuencia &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-165">Sequence Clustering Cluster Transition Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-transition-tab-mining-model-viewer.md)

### <a name="microsoft-time-series-algorithm"></a><span data-ttu-id="7556b-166">Algoritmo de serie temporal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-166">Microsoft Time Series Algorithm</span></span>

-   [<span data-ttu-id="7556b-167">Examinar un modelo usando el Visor de serie temporal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7556b-167">Browse a Model Using the Microsoft Time Series Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)

    -   [<span data-ttu-id="7556b-168">Pestaña modelo &#40;visores de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-168">Model Tab &#40;Mining Model Viewers&#41;</span></span>](model-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="7556b-169">Pestaña gráfico &#40;visores de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-169">Chart Tab &#40;Mining Model Viewers&#41;</span></span>](chart-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="7556b-170">Cuadro de diálogo leyenda de minería de datos &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7556b-170">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

## <a name="see-also"></a><span data-ttu-id="7556b-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7556b-171">See Also</span></span>
 <span data-ttu-id="7556b-172">[Modelos de minería de datos vista &#40;diseñador de modelos de minería de datos&#41;](mining-models-view-data-mining-model-designer.md) [vista estructura de minería de datos &#40;diseñador de modelos de minería](mining-structure-view-data-mining-model-designer.md) de datos&#41;el diseñador de gráficos de precisión de minería de [datos](mining-accuracy-chart-designer-data-mining.md) &#40;[predicción](prediction-query-builder-data-mining.md)&#41;generador de consultas &#40;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7556b-172">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Structure View &#40;Data Mining Model Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span></span>


