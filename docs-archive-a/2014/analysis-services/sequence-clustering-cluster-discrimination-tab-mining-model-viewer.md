---
title: Pestaña distinción del clúster de clústeres de secuencia (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.discrimination.f1
ms.assetid: 7dd16479-2633-4f4b-83bf-cf55972a2241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9839a6185933fd87929331558ed63c1d81c6a748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752422"
---
# <a name="sequence-clustering-cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="b2e9f-102">Pestaña Distinción del clúster de agrupación en clústeres de secuencia (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="b2e9f-102">Sequence Clustering Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="b2e9f-103">La pestaña  **Distinción del clúster** del **Visor de agrupación en clústeres de secuencia de Microsoft** compara los clústeres seleccionados de un modelo de agrupación en clústeres de secuencia.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-103">The  **Cluster Discrimination** tab in the **Microsoft Sequence Clustering Viewer** compares selected clusters from a sequence clustering model.</span></span>  
  
 <span data-ttu-id="b2e9f-104">Utilice esta vista de un modelo de agrupación en clústeres de secuencia para comparar dos clústeres y ver qué estados y transiciones son diferentes.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-104">Use this view of a sequence clustering model to compare two clusters and see which states and transitions are different.</span></span>  
  
 <span data-ttu-id="b2e9f-105">**Para más información:** [Algoritmo de clústeres de secuencia de Microsoft](data-mining/microsoft-sequence-clustering-algorithm.md), [Examinar un modelo usando el Visor de clústeres de secuencia de Microsoft](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="b2e9f-105">**For More Information:** [Microsoft Sequence Clustering Algorithm](data-mining/microsoft-sequence-clustering-algorithm.md), [Browse a Model Using the Microsoft Sequence Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="b2e9f-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="b2e9f-106">Options</span></span>  
 <span data-ttu-id="b2e9f-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="b2e9f-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="b2e9f-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-109">**Mining Model**</span></span>  
 <span data-ttu-id="b2e9f-110">Elija esta opción para ver un modelo de minería de datos que se encuentra en la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="b2e9f-111">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="b2e9f-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-112">**Viewer**</span></span>  
 <span data-ttu-id="b2e9f-113">Elija un visor que desee usar para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-113">Choose a viewer to use in exploring the selected mining model.</span></span> <span data-ttu-id="b2e9f-114">Puede utilizar el visor personalizado o el **Visor de árbol de contenido genérico de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-114">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="b2e9f-115">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="b2e9f-116">**Clúster 1**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-116">**Cluster 1**</span></span>  
 <span data-ttu-id="b2e9f-117">Seleccione un clúster de los del modelo.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-117">Select a cluster from those in the model.</span></span>  
  
 <span data-ttu-id="b2e9f-118">**Clúster 2**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-118">**Cluster 2**</span></span>  
 <span data-ttu-id="b2e9f-119">Seleccione un segundo clúster del modelo de minería de datos para compararlo con el **Clúster 1**.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-119">Select a second cluster in the mining model, to compare to **Cluster 1**.</span></span>  
  
 <span data-ttu-id="b2e9f-120">Si no selecciona otro clúster, de forma predeterminada el clúster seleccionado se compara con su complemento, es decir, con todos los casos del modelo que no están en el Clúster 1.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-120">If you do not select another cluster, by default the selected cluster is compared to its complement, meaning all cases in the model that are not in Cluster 1.</span></span>  
  
 <span data-ttu-id="b2e9f-121">**Puntuaciones de distinción para \<cluster 1> y\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="b2e9f-122">Este gráfico proporciona una comparación detallada de los clústeres seleccionados.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-122">This chart provides the detailed comparison of the clusters that you selected.</span></span> <span data-ttu-id="b2e9f-123">En general, un modelo de agrupación en clústeres raramente asigna estados o valores exclusivamente a un único clúster.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-123">In general, a clustering model rarely assigns states or values exclusively to a single cluster.</span></span> <span data-ttu-id="b2e9f-124">Por consiguiente, el visor solo indica que un determinado atributo o estado *favorece* un determinado clúster.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-124">Therefore, the viewer indicates only that a particular attribute or state *favors* a particular cluster.</span></span>  
  
 <span data-ttu-id="b2e9f-125">En general, algún clúster podría contener más de un estado: por ejemplo, un estado común podría ser la compra de una Botella de agua y de un Portabotellas secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-125">Overall, a certain cluster might contain more of one state: for example, a common state might be the purchase of a Water Bottle and Water Bottle Cage in sequence.</span></span> <span data-ttu-id="b2e9f-126">Sin embargo, la secuencia se podría encontrar en otros clústeres que tengan características de definición más importantes.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-126">However, the sequence might be present in other clusters that have more important defining characteristics.</span></span> <span data-ttu-id="b2e9f-127">Por ejemplo, otro clúster podría estar caracterizado más firmemente por unos tiempos de transacción muy cortos, y un análisis revelaría que los elementos [Water Bottle y Water] normalmente se agruparían en este clúster, pero no siempre.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-127">For example, another cluster might be characterized most strongly by very short transaction times, and an analysis would reveal that [Water Bottle and Waterthe items are positioned to might usually be grouped in this cluster, but not always.</span></span>  
  
|<span data-ttu-id="b2e9f-128">Value</span><span class="sxs-lookup"><span data-stu-id="b2e9f-128">Value</span></span>|<span data-ttu-id="b2e9f-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2e9f-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b2e9f-130">**Variables**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-130">**Variables**</span></span>|<span data-ttu-id="b2e9f-131">Un atributo del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-131">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="b2e9f-132">**Valores**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-132">**Values**</span></span>|<span data-ttu-id="b2e9f-133">Un estado del atributo que se incluye en **Variables**.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-133">A state of the attribute that is listed in **Variables**.</span></span>|  
|<span data-ttu-id="b2e9f-134">**Favorece\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="b2e9f-134">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="b2e9f-135">Contiene una barra sombreada que indica con qué intensidad el atributo y el estado se incluyen en **Variables** y **Valor** a favor del clúster seleccionado en **Clúster 1**.</span><span class="sxs-lookup"><span data-stu-id="b2e9f-135">Contains a shaded bar that indicates how strongly the attribute and the state that are listed in **Variables** and **Value** favor the cluster that is selected in **Cluster 1**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2e9f-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2e9f-136">See Also</span></span>  
 <span data-ttu-id="b2e9f-137">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b2e9f-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="b2e9f-138">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b2e9f-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="b2e9f-139">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="b2e9f-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
