---
title: Pestaña distinción del clúster (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.discrimination.f1
ms.assetid: ae7cfff7-ab1c-4cf5-9a91-97b21d15d85f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35435736bcdf1b1962de6babace2def953bbfff0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670684"
---
# <a name="cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="75e7e-102">Pestaña Distinción del clúster (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="75e7e-102">Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="75e7e-103">Utilice la pestaña **Distinción del clúster** para comparar dos clústeres que existan en un modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="75e7e-103">Use the **Cluster Discrimination** tab to compare two clusters that exist in a clustering model.</span></span> <span data-ttu-id="75e7e-104">Puede ver cómo las diferentes combinaciones de atributos y valores se representan dentro de los clústeres.</span><span class="sxs-lookup"><span data-stu-id="75e7e-104">You can see how different combinations of attributes and values are represented within the clusters.</span></span>  
  
 <span data-ttu-id="75e7e-105">**Para obtener más información:** [Algoritmo de clústeres de Microsoft](data-mining/microsoft-clustering-algorithm.md), [Examinar un modelo usando el Visor de clústeres de Microsoft](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="75e7e-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="75e7e-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="75e7e-106">Options</span></span>  
 <span data-ttu-id="75e7e-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="75e7e-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="75e7e-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="75e7e-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="75e7e-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="75e7e-109">**Mining Model**</span></span>  
 <span data-ttu-id="75e7e-110">Elija un modelo de minería de datos de los de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="75e7e-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="75e7e-111">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="75e7e-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="75e7e-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="75e7e-112">**Viewer**</span></span>  
 <span data-ttu-id="75e7e-113">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="75e7e-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="75e7e-114">Puede utilizar el visor personalizado de los modelos de agrupación en clústeres o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75e7e-114">You can use the custom viewer for clustering models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="75e7e-115">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="75e7e-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="75e7e-116">**Clúster 1**</span><span class="sxs-lookup"><span data-stu-id="75e7e-116">**Cluster 1**</span></span>  
 <span data-ttu-id="75e7e-117">Seleccione un clúster, para que pueda compararlo con otro clúster.</span><span class="sxs-lookup"><span data-stu-id="75e7e-117">Select a cluster, so that you can compare it to another cluster.</span></span>  
  
 <span data-ttu-id="75e7e-118">**Clúster 2**</span><span class="sxs-lookup"><span data-stu-id="75e7e-118">**Cluster 2**</span></span>  
 <span data-ttu-id="75e7e-119">Seleccione un segundo clúster de la lista de clústeres del modelo de minería de datos para compararlo con el **Clúster 1**.</span><span class="sxs-lookup"><span data-stu-id="75e7e-119">Select a second cluster from the list of clusters in the mining model, to compare to **Cluster 1**.</span></span> <span data-ttu-id="75e7e-120">También puede comparar un clúster con su complemento, es decir, con todos los casos del modelo excepto los del clúster seleccionado.</span><span class="sxs-lookup"><span data-stu-id="75e7e-120">You can also compare a cluster to its complement, meaning all cases in the model except those in the selected cluster.</span></span>  
  
 <span data-ttu-id="75e7e-121">**Puntuaciones de distinción para \<cluster 1> y\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="75e7e-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="75e7e-122">Las columnas del gráfico proporcionan información sobre cómo se relaciona cada par de atributo-valor con los dos clústeres seleccionados.</span><span class="sxs-lookup"><span data-stu-id="75e7e-122">The columns in the graph provide information about how each attribute-value pair is related to the two selected clusters.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75e7e-123">**Variables**</span><span class="sxs-lookup"><span data-stu-id="75e7e-123">**Variables**</span></span>|<span data-ttu-id="75e7e-124">Un atributo del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="75e7e-124">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="75e7e-125">**Valores**</span><span class="sxs-lookup"><span data-stu-id="75e7e-125">**Values**</span></span>|<span data-ttu-id="75e7e-126">Un valor del atributo seleccionado en **Variables**.</span><span class="sxs-lookup"><span data-stu-id="75e7e-126">A value of the attribute selected in **Variables**.</span></span>|  
|<span data-ttu-id="75e7e-127">**Favorece\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="75e7e-127">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="75e7e-128">El gráfico de barras de la izquierda representa la probabilidad de que el par de atributo-valor seleccionado sea representativo del clúster seleccionado en **Clúster 1**.</span><span class="sxs-lookup"><span data-stu-id="75e7e-128">The bar graph on the left represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 1**.</span></span> <span data-ttu-id="75e7e-129">Puede detener el mouse sobre la barra ver el valor, representado como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="75e7e-129">You can pause the mouse over the bar to see the value, represented as a percentage.</span></span> <span data-ttu-id="75e7e-130">Tenga en cuenta que incluso si el valor es cero, no significa que el valor del atributo-value no se encuentre necesariamente en el clúster, solo que la distribución favorece un clúster sobre el otro.</span><span class="sxs-lookup"><span data-stu-id="75e7e-130">Note that even if the value is zero, it doesn't mean the attribute-value is necessarily missing from the cluster, just that the distribution strongly favors one cluster over the other.</span></span>|  
|<span data-ttu-id="75e7e-131">**Favorece\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="75e7e-131">**Favors \<cluster 2>**</span></span>|<span data-ttu-id="75e7e-132">El gráfico de barras de la derecha representa la probabilidad de que el par de atributo-valor seleccionado sea representativo del clúster seleccionado en **Clúster 2**.</span><span class="sxs-lookup"><span data-stu-id="75e7e-132">The bar graph on the right represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75e7e-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75e7e-133">See Also</span></span>  
 <span data-ttu-id="75e7e-134">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="75e7e-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="75e7e-135">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="75e7e-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="75e7e-136">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="75e7e-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
