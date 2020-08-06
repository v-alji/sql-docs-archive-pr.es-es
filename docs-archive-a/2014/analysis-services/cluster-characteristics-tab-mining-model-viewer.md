---
title: Pestaña características del clúster (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.characteristics.f1
ms.assetid: 8e33ed1d-1ce4-405d-895b-7e995b2c910d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 959d94767b6cb27d9ebb6e06c592034fca20ac89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670060"
---
# <a name="cluster-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="e32ff-102">Pestaña Características del clúster (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="e32ff-102">Cluster Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="e32ff-103">La pestaña **Características del clúster** le permite explorar las características de un clúster en un modelo de agrupación en clústeres o el conjunto de todos los casos del modelo.</span><span class="sxs-lookup"><span data-stu-id="e32ff-103">The **Cluster Characteristics** tab lets you explore the characteristics of a cluster in a clustering model, or the set of all cases in the model.</span></span> <span data-ttu-id="e32ff-104">El gráfico muestra la importancia de cada par de atributo-valor como una característica que define el clúster, comparado con otros clústeres.</span><span class="sxs-lookup"><span data-stu-id="e32ff-104">The graph shows the importance of each attribute-value pair as a characteristic that defines the cluster, in comparison with other clusters.</span></span>  
  
 <span data-ttu-id="e32ff-105">**Para obtener más información:** [Algoritmo de clústeres de Microsoft](data-mining/microsoft-clustering-algorithm.md), [Examinar un modelo usando el Visor de clústeres de Microsoft](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="e32ff-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e32ff-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="e32ff-106">Options</span></span>  
 <span data-ttu-id="e32ff-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="e32ff-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="e32ff-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="e32ff-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="e32ff-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="e32ff-109">**Mining Model**</span></span>  
 <span data-ttu-id="e32ff-110">Elija un modelo de minería de datos de los de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="e32ff-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="e32ff-111">El modelo de minería de datos se abrirá en el visor personalizado.</span><span class="sxs-lookup"><span data-stu-id="e32ff-111">The mining model will open in the custom viewer.</span></span>  
  
 <span data-ttu-id="e32ff-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="e32ff-112">**Viewer**</span></span>  
 <span data-ttu-id="e32ff-113">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e32ff-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="e32ff-114">Puede utilizar el visor personalizado asociado a este tipo modelo o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e32ff-114">You can use the custom viewer associated with this model type, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="e32ff-115">También puede utilizar cualquier visor de complemento que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="e32ff-115">You can also use any plug-in viewers that are available.</span></span>  
  
 <span data-ttu-id="e32ff-116">**Clúster**</span><span class="sxs-lookup"><span data-stu-id="e32ff-116">**Cluster**</span></span>  
 <span data-ttu-id="e32ff-117">Elija el clúster que quiere ver, o elija **Población (Todo)** para ver la distribución de atributos del modelo en su conjunto.</span><span class="sxs-lookup"><span data-stu-id="e32ff-117">Choose the cluster you want to view, or choose **Population (All)** to see the distribution of attributes for the model as a whole.</span></span>  
  
 <span data-ttu-id="e32ff-118">**Características de\<cluster>**</span><span class="sxs-lookup"><span data-stu-id="e32ff-118">**Characteristics for \<cluster>**</span></span>  
 <span data-ttu-id="e32ff-119">El gráfico contiene las columnas siguientes, que describen las características del clúster seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e32ff-119">The graph contains the following columns, which describe the characteristics of the selected cluster.</span></span>  
  
|<span data-ttu-id="e32ff-120">Value</span><span class="sxs-lookup"><span data-stu-id="e32ff-120">Value</span></span>|<span data-ttu-id="e32ff-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e32ff-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e32ff-122">**Variable**</span><span class="sxs-lookup"><span data-stu-id="e32ff-122">**Variable**</span></span>|<span data-ttu-id="e32ff-123">Enumera los atributos del modelo de minería de datos que se encuentran en el clúster seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e32ff-123">Lists the attributes from the mining model that are found in the selected cluster.</span></span>|  
|<span data-ttu-id="e32ff-124">**Valores**</span><span class="sxs-lookup"><span data-stu-id="e32ff-124">**Values**</span></span>|<span data-ttu-id="e32ff-125">Enumera los valores de los atributos actuales que se encuentran en el clúster seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="e32ff-125">Lists the values of the current attributes that are found in the currently selected cluster.</span></span>|  
|<span data-ttu-id="e32ff-126">**Probabilidad**</span><span class="sxs-lookup"><span data-stu-id="e32ff-126">**Probability**</span></span>|<span data-ttu-id="e32ff-127">La barra indica la fuerza del par de atributo-valor como una característica distintiva de este clúster.</span><span class="sxs-lookup"><span data-stu-id="e32ff-127">The bar indicates the strength of the attribute-value pair as a distinguishing feature of this cluster.</span></span> <span data-ttu-id="e32ff-128">Si sitúa el mouse sobre la barra, puede ver el valor de probabilidad, representado como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="e32ff-128">If you hover the mouse over the bar, you can see the probability value, represented as a percentage.</span></span> <span data-ttu-id="e32ff-129">Lo que esto indica es, dado este atributo y combinación de valores en un caso determinado, cuál es la probabilidad de que el caso pertenezca a este clúster.</span><span class="sxs-lookup"><span data-stu-id="e32ff-129">What this indicates is, given this attribute and value combination in any particular case, what is the probability that the case would belong in this cluster.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e32ff-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e32ff-130">See Also</span></span>  
 <span data-ttu-id="e32ff-131">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e32ff-131">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e32ff-132">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e32ff-132">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="e32ff-133">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e32ff-133">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
