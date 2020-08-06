---
title: Pestaña características del atributo (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.characteristics.f1
ms.assetid: f0c3350d-84c0-4ab8-9fb8-1527c2647299
author: minewiskan
ms.author: owend
ms.openlocfilehash: b29ba482c21bb674a10bc4c9e6c6eccdf30905dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670171"
---
# <a name="attribute-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="4412e-102">Pestaña Características del atributo (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="4412e-102">Attribute Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="4412e-103">Utilice el panel **Características del atributo** para explorar las relaciones entre los resultados y los atributos de entrada en un modelo Bayes Naïve.</span><span class="sxs-lookup"><span data-stu-id="4412e-103">Use the **Attribute Characteristics** pane to explore the relationships between outcomes and input attributes in a Naïve Bayes model.</span></span> <span data-ttu-id="4412e-104">Puede elegir el valor del atributo de destino y, a continuación, ver una lista de los atributos de entrada que tienen el efecto más fuerte sobre los resultados.</span><span class="sxs-lookup"><span data-stu-id="4412e-104">You can choose the value of the target attribute, and then see a list of the input attributes that have the strongest effect on the outcomes.</span></span>  
  
 <span data-ttu-id="4412e-105">**Para más información:** [Algoritmo Bayes naive de Microsoft](data-mining/microsoft-naive-bayes-algorithm.md), [Examinar un modelo usando el visor Bayes naive de Microsoft](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="4412e-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="4412e-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="4412e-106">Options</span></span>  
 <span data-ttu-id="4412e-107">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="4412e-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="4412e-108">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="4412e-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="4412e-109">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="4412e-109">**Mining Model**</span></span>  
 <span data-ttu-id="4412e-110">Elija un modelo de minería de datos que se desea ver de los modelos de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="4412e-110">Choose a mining model to view, from the models in the current mining structure.</span></span> <span data-ttu-id="4412e-111">El modelo de minería de datos se abrirá automáticamente en el visor personalizado más adecuado para el tipo de modelo elegido.</span><span class="sxs-lookup"><span data-stu-id="4412e-111">The mining model will automatically open in a custom viewer that is best for the particular type of model you chose.</span></span>  
  
 <span data-ttu-id="4412e-112">**Visor**</span><span class="sxs-lookup"><span data-stu-id="4412e-112">**Viewer**</span></span>  
 <span data-ttu-id="4412e-113">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4412e-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="4412e-114">Para cada modelo, tiene la opción de un visor personalizado o el Visor de contenido de minería de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4412e-114">For each model, you have the choice of a custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="4412e-115">Los visores de complemento también aparecen en esta lista si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="4412e-115">Plug-in viewers also appear in this list if available.</span></span>  
  
 <span data-ttu-id="4412e-116">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="4412e-116">**Attribute**</span></span>  
 <span data-ttu-id="4412e-117">Elija el atributo de predicción que desee analizar.</span><span class="sxs-lookup"><span data-stu-id="4412e-117">Choose the predictable attribute that you want to analyze.</span></span>  
  
 <span data-ttu-id="4412e-118">**Valor**</span><span class="sxs-lookup"><span data-stu-id="4412e-118">**Value**</span></span>  
 <span data-ttu-id="4412e-119">Elija un estado para el atributo de predicción establecido en **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="4412e-119">Choose a state for the predictable attribute that you set in **Attribute**.</span></span> <span data-ttu-id="4412e-120">Dado que los modelos Bayes Naïve no admiten variables continuas, todos los atributos de destino tienen resultados discretos o de datos discretos.</span><span class="sxs-lookup"><span data-stu-id="4412e-120">Because Naïve Bayes models do not support continuous variables, all target attributes have discrete or discretized outcomes.</span></span> <span data-ttu-id="4412e-121">El atributo Missing siempre se agrega automáticamente a la lista.</span><span class="sxs-lookup"><span data-stu-id="4412e-121">The Missing attribute is always automatically added to the list.</span></span>  
  
 <span data-ttu-id="4412e-122">**Características de\<predictable state>**</span><span class="sxs-lookup"><span data-stu-id="4412e-122">**Characteristics for \<predictable state>**</span></span>  
 <span data-ttu-id="4412e-123">El gráfico contiene las siguientes columnas, que describen cómo los estados de los atributos de entrada están relacionados con el estado de atributo de predicción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4412e-123">The graph contains the following columns, which describe how states of the input attributes are related to the selected predictable attribute state.</span></span>  
  
|<span data-ttu-id="4412e-124">Value</span><span class="sxs-lookup"><span data-stu-id="4412e-124">Value</span></span>|<span data-ttu-id="4412e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4412e-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4412e-126">**Variable**</span><span class="sxs-lookup"><span data-stu-id="4412e-126">**Variable**</span></span>|<span data-ttu-id="4412e-127">Enumera los atributos de entrada del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="4412e-127">Lists the input attributes in the mining model.</span></span>|  
|<span data-ttu-id="4412e-128">**Valores**</span><span class="sxs-lookup"><span data-stu-id="4412e-128">**Values**</span></span>|<span data-ttu-id="4412e-129">Enumera cada estado del atributo de entrada en **Variable**.</span><span class="sxs-lookup"><span data-stu-id="4412e-129">Lists each state of the input attribute in **Variable**.</span></span>|  
|<span data-ttu-id="4412e-130">**Probabilidad**</span><span class="sxs-lookup"><span data-stu-id="4412e-130">**Probability**</span></span>|<span data-ttu-id="4412e-131">La barra representa la probabilidad de que el atributo y el valor de dicha fila estén asociados con el estado seleccionado del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="4412e-131">The bar represents the probability that the attribute and value in that row are associated with the selected state of the predictable attribute.</span></span> <span data-ttu-id="4412e-132">Sitúe el mouse sobre la barra para ver la probabilidad como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="4412e-132">Hover the mouse over the bar to view the probability as a percentage.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4412e-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4412e-133">See Also</span></span>  
 <span data-ttu-id="4412e-134">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4412e-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4412e-135">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="4412e-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="4412e-136">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4412e-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
