---
title: Pestaña red de dependencias (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.dependencynetwork.f1
ms.assetid: e58ce1b7-20d6-42cb-ade5-916da8471e09
author: minewiskan
ms.author: owend
ms.openlocfilehash: 94ce82524445ffb8999c671c736087362ef0adfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744425"
---
# <a name="dependency-network-tab-mining-model-viewer"></a><span data-ttu-id="7df4a-102">Pestaña Red de dependencias (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="7df4a-102">Dependency Network Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="7df4a-103">La pestaña **Red de dependencias** proporciona una vista gráfica de todos los atributos que contiene el modelo de minería de datos, y muestra cómo se relacionan los atributos.</span><span class="sxs-lookup"><span data-stu-id="7df4a-103">The **Dependency Net** tab provides a graphical view of all attributes that the mining model contains, and shows how the attributes are related.</span></span>  
  
 <span data-ttu-id="7df4a-104">La pestaña **Red de dependencias**  se utiliza para varios tipos de modelos de minería de datos, incluidos los modelos Bayes Naïve, modelos de árboles de decisión y modelos de asociación.</span><span class="sxs-lookup"><span data-stu-id="7df4a-104">The **Dependency Net**  tab is used for several types of mining models, including Naïve Bayes models, decision tree models, and association models.</span></span> <span data-ttu-id="7df4a-105">Para obtener más información sobre cómo interpretar el contenido de la pestaña **Red de dependencias**  en el contexto de estos modelos, vea los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="7df4a-105">For more information about how to interpret the contents of the **Dependency Net**  tab in the context of these models, see the following links:</span></span>  
  
 [<span data-ttu-id="7df4a-106">Examinar un modelo usando el Visor de árboles de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7df4a-106">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
 [<span data-ttu-id="7df4a-107">Examinar un modelo usando el visor Bayes naive de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7df4a-107">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
 [<span data-ttu-id="7df4a-108">Examinar un modelo usando el Visor de reglas de asociación de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7df4a-108">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a><span data-ttu-id="7df4a-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="7df4a-109">Options</span></span>  
 <span data-ttu-id="7df4a-110">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="7df4a-110">**Refresh viewer content**</span></span>  
 <span data-ttu-id="7df4a-111">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="7df4a-111">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="7df4a-112">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="7df4a-112">**Mining Model**</span></span>  
 <span data-ttu-id="7df4a-113">Elija un modelo de minería de datos que desea ver de los modelos de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="7df4a-113">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="7df4a-114">El modelo de minería de datos se abrirá en un visor personalizado.</span><span class="sxs-lookup"><span data-stu-id="7df4a-114">The mining model will open in a custom viewer.</span></span> <span data-ttu-id="7df4a-115">El algoritmo que se usa para crear el modelo determina el tipo de visor personalizado que se utiliza para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="7df4a-115">The type of custom viewer that is used for each model is determined by the algorithm that you used to create the model.</span></span>  
  
 <span data-ttu-id="7df4a-116">**Visor**</span><span class="sxs-lookup"><span data-stu-id="7df4a-116">**Viewer**</span></span>  
 <span data-ttu-id="7df4a-117">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7df4a-117">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="7df4a-118">Para cada modelo, puede utilizar el visor personalizado que se proporciona para cada modelo de minería de datos o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7df4a-118">For each model, you can use either the custom viewer is provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="7df4a-119">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="7df4a-119">You can also use plug-in viewers if available.</span></span> <span data-ttu-id="7df4a-120">El Visor de árbol de contenido genérico de Microsoft se puede utilizar con todos los modelos, y representa el contenido del modelo en una tabla HTML.</span><span class="sxs-lookup"><span data-stu-id="7df4a-120">The Microsoft Content Tree Viewer can be used with all models, and represents the model content in an HTML table.</span></span>  
  
 <span data-ttu-id="7df4a-121">**Acercar**</span><span class="sxs-lookup"><span data-stu-id="7df4a-121">**Zoom In**</span></span>  
 <span data-ttu-id="7df4a-122">Acerque el diagrama para que pueda ver los atributos con más detalle.</span><span class="sxs-lookup"><span data-stu-id="7df4a-122">Zoom in to the diagram, so that you can see the attributes in more detail.</span></span>  
  
 <span data-ttu-id="7df4a-123">**Alejar**</span><span class="sxs-lookup"><span data-stu-id="7df4a-123">**Zoom Out**</span></span>  
 <span data-ttu-id="7df4a-124">Aleje el diagrama para que pueda ver más atributos y los vínculos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="7df4a-124">Zoom out from the diagram, so that you can see more attributes and the links between them.</span></span>  
  
 <span data-ttu-id="7df4a-125">**Copiar vista del gráfico**</span><span class="sxs-lookup"><span data-stu-id="7df4a-125">**Copy Graph View**</span></span>  
 <span data-ttu-id="7df4a-126">Copie la sección visible del diagrama en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="7df4a-126">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="7df4a-127">**Copiar todo el gráfico**</span><span class="sxs-lookup"><span data-stu-id="7df4a-127">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="7df4a-128">Copie el diagrama completo en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="7df4a-128">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="7df4a-129">**Vínculos**</span><span class="sxs-lookup"><span data-stu-id="7df4a-129">**Links**</span></span>  
 <span data-ttu-id="7df4a-130">Mueva el control deslizante hacia la derecha de los atributos para ajustar el número de vínculos (bordes) que muestra el visor.</span><span class="sxs-lookup"><span data-stu-id="7df4a-130">Adjust how many links (edges) and nodes the viewer shows by adjusting the slider to the right of the attributes.</span></span> <span data-ttu-id="7df4a-131">Si arrastra la barra deslizante hacia abajo, aumenta el valor de umbral para que solo se muestren los vínculos más fuertes.</span><span class="sxs-lookup"><span data-stu-id="7df4a-131">Dragging the slider bar down increases the threshold value, so that only the strongest links are shown.</span></span> <span data-ttu-id="7df4a-132">Para cada tipo modelo, se utiliza un valor ligeramente diferente para representar los vínculos en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="7df4a-132">For each model type, a slightly different value is used to represent the links in the graph:</span></span>  
  
-   <span data-ttu-id="7df4a-133">En un modelo de **árboles de decisión** , los bordes representan la fuerza de predicción de la conexión, determinada en parte por el resultado de la división.</span><span class="sxs-lookup"><span data-stu-id="7df4a-133">In a **decision tree** model, the edges represent the predictive strength of the connection, determined partly by the split score.</span></span>  
  
-   <span data-ttu-id="7df4a-134">En un modelo **Bayes Naïve** , los vínculos entre dos nodos pueden ir en ambas direcciones: es decir, nodo A puede predecir el nodo B y viceversa.</span><span class="sxs-lookup"><span data-stu-id="7df4a-134">In a **Naïve Bayes** model, the links between two nodes can go either way: that is, node A can predict the node B, and vice versa.</span></span> <span data-ttu-id="7df4a-135">La puntuación asociada al borde representa la fuerza de predicción de la conexión.</span><span class="sxs-lookup"><span data-stu-id="7df4a-135">The score associated with the edge represents the predictive strength of the connection.</span></span>  
  
-   <span data-ttu-id="7df4a-136">En un **modelo de asociación**, los bordes entre los nodos representan la puntuación de importancia de la regla que conecta dos conjuntos de elementos.</span><span class="sxs-lookup"><span data-stu-id="7df4a-136">In an **association model**, the edges between nodes represent the importance score of the rule that connects two itemsets.</span></span>  
  
 <span data-ttu-id="7df4a-137">Una regla general para todos los tipos de modelo es que cuánto más fuerte es el vínculo, más fuerte es la relación de predicción entre los dos atributos.</span><span class="sxs-lookup"><span data-stu-id="7df4a-137">A general rule for all model types is that the stronger the link, the stronger the predictive relationship between the two attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df4a-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7df4a-138">See Also</span></span>  
 <span data-ttu-id="7df4a-139">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7df4a-139">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="7df4a-140">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7df4a-140">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="7df4a-141">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7df4a-141">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
