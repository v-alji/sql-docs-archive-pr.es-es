---
title: Pestaña perfiles del clúster (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.profiles.f1
ms.assetid: 1ebafa1f-74e9-4c05-b278-a690fa8543bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7ec1ce5b5204ae81a9313ca7b7e5df58c98c5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670680"
---
# <a name="cluster-profiles-tab-mining-model-viewer"></a><span data-ttu-id="0c6eb-102">Pestaña Perfiles del clúster (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0c6eb-102">Cluster Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="0c6eb-103">Utilice la pestaña **Perfiles del clúster** para obtener una vista general de los clústeres que ha descubierto el algoritmo en un modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-103">Use the **Cluster Profiles** tab for an overall view of the clusters that the algorithm discovered within a clustering model.</span></span> <span data-ttu-id="0c6eb-104">La pestaña muestra cada atributo junto con la distribución del atributo en cada clúster.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-104">The tab displays each attribute, together with the distribution of the attribute in each cluster.</span></span>  
  
 <span data-ttu-id="0c6eb-105">**Para obtener más información:** [Algoritmo de clústeres de Microsoft](data-mining/microsoft-clustering-algorithm.md), [Examinar un modelo usando el Visor de clústeres de Microsoft](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="0c6eb-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c6eb-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c6eb-106">Options</span></span>  
 <span data-ttu-id="0c6eb-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="0c6eb-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="0c6eb-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-109">**Mining Model**</span></span>  
 <span data-ttu-id="0c6eb-110">Elija un modelo de minería de datos de los de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="0c6eb-111">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="0c6eb-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-112">**Viewer**</span></span>  
 <span data-ttu-id="0c6eb-113">Elija un visor para ver el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="0c6eb-114">Puede utilizar el visor personalizado del modelo de minería de datos o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c6eb-114">You can use the custom viewer for the mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="0c6eb-115">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="0c6eb-116">**Mostrar leyenda**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-116">**Show Legend**</span></span>  
 <span data-ttu-id="0c6eb-117">Seleccione esta opción para mostrar una clave que muestre la asignación de colores en el visor a los valores de la columna **Estados** .</span><span class="sxs-lookup"><span data-stu-id="0c6eb-117">Select this option to display a key that shows the mapping of colors in the viewer to values in the **States** column.</span></span>  
  
 <span data-ttu-id="0c6eb-118">**Barras de histograma**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-118">**Histogram Bars**</span></span>  
 <span data-ttu-id="0c6eb-119">Cambie este valor para controlar cuántos estados se incluyen en cada histograma.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-119">Change this value to control how many states are included in each histogram.</span></span> <span data-ttu-id="0c6eb-120">Si hay más estados de los que ha elegido mostrar, aparecen en el histograma los estados con la probabilidad más alta, y el resto de los estados se agrupan en **Otros**.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-120">If there are more states than you choose to display, the states with the highest probability are shown in the histogram, and the remaining states are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="0c6eb-121">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-121">**Attributes**</span></span>  
 <span data-ttu-id="0c6eb-122">Enumera las columnas incluidas en el modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-122">Lists the columns that are in the clustering model.</span></span> <span data-ttu-id="0c6eb-123">Los histogramas de cada atributo muestran cómo se distribuye el atributo entre los clústeres identificados por el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-123">The histograms for each attribute show how the attribute is distributed among the clusters identified by the algorithm.</span></span>  
  
 <span data-ttu-id="0c6eb-124">**States**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-124">**States**</span></span>  
 <span data-ttu-id="0c6eb-125">Proporciona una clave que denota qué color representa cada estado en la fila de clústeres correspondiente, o un control deslizante con rombo que indica la distribución de los valores numéricos continuos.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-125">Provides a key that either denotes what color represents each state in the corresponding row of clusters, or a slider with diamond that indicates the distribution of continuous numeric values.</span></span> <span data-ttu-id="0c6eb-126">Puede mostrar u ocultar esta columna mediante la casilla **Mostrar leyenda** .</span><span class="sxs-lookup"><span data-stu-id="0c6eb-126">You can show or hide this column by using the **Show Legend** check box.</span></span>  
  
 <span data-ttu-id="0c6eb-127">**Perfiles del clúster**</span><span class="sxs-lookup"><span data-stu-id="0c6eb-127">**Cluster Profiles**</span></span>  
 <span data-ttu-id="0c6eb-128">Esta sección contiene una columna para cada clúster del modelo.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-128">This section contains a column for each cluster in the model.</span></span> <span data-ttu-id="0c6eb-129">Para cada atributo, el histograma muestra la distribución de los valores en el atributo solo para ese clúster.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-129">For each attribute, the histogram shows the distribution of the values in the attribute for just that cluster.</span></span> <span data-ttu-id="0c6eb-130">El gráfico también tiene una columna para **Población**, que también utiliza histogramas para mostrar la distribución de valores de cada atributo, pero para todos los casos del modelo.</span><span class="sxs-lookup"><span data-stu-id="0c6eb-130">The chart also has a column for **Population**, which also uses histograms to display the distribution of values for each attribute, but for all cases in the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6eb-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c6eb-131">See Also</span></span>  
 <span data-ttu-id="0c6eb-132">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="0c6eb-132">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="0c6eb-133">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="0c6eb-133">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="0c6eb-134">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="0c6eb-134">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
