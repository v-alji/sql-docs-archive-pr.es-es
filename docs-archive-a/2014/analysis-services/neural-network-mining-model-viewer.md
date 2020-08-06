---
title: Red neuronal (visor de modelos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.neuralnet.f1
ms.assetid: 18d87e7b-a821-40ea-9bd8-c6fecf189a1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 39ca8d3cd9f2a327abd8558b13a018ceda27968d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671719"
---
# <a name="neural-network-mining-model-viewer"></a><span data-ttu-id="83ff6-102">Red neuronal (Visor de modelos de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="83ff6-102">Neural Network (Mining Model Viewer)</span></span>
  <span data-ttu-id="83ff6-103">Utilice el **Visor de redes neuronales** para explorar modelos de minería de datos basados en el algoritmo de red neuronal de [!INCLUDE[msCoName](../includes/msconame-md.md)] o en el algoritmo de regresión logística de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83ff6-103">Use the **Neural Net** viewer to explore mining models that are based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="83ff6-104">**Para obtener más información:** [Algoritmo de red neuronal de Microsoft](data-mining/microsoft-neural-network-algorithm.md), [Algoritmo de regresión logística de Microsoft](data-mining/microsoft-logistic-regression-algorithm.md),[Examinar un modelo usando el Visor de redes neuronales de Microsoft](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="83ff6-104">**For More Information:** [Microsoft Neural Network Algorithm](data-mining/microsoft-neural-network-algorithm.md), [Microsoft Logistic Regression Algorithm](data-mining/microsoft-logistic-regression-algorithm.md),[Browse a Model Using the Microsoft Neural Network Viewer](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="83ff6-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="83ff6-105">Options</span></span>  
 <span data-ttu-id="83ff6-106">**Actualizar el contenido del visor**</span><span class="sxs-lookup"><span data-stu-id="83ff6-106">**Refresh viewer content**</span></span>  
 <span data-ttu-id="83ff6-107">Vuelva a cargar el modelo de minería de datos en el visor.</span><span class="sxs-lookup"><span data-stu-id="83ff6-107">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="83ff6-108">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="83ff6-108">**Mining Model**</span></span>  
 <span data-ttu-id="83ff6-109">Elija un modelo de minería de datos que desea ver de los modelos de la estructura de minería de datos actual.</span><span class="sxs-lookup"><span data-stu-id="83ff6-109">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="83ff6-110">El modelo de minería de datos se abrirá en el visor asociado.</span><span class="sxs-lookup"><span data-stu-id="83ff6-110">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="83ff6-111">**Visor**</span><span class="sxs-lookup"><span data-stu-id="83ff6-111">**Viewer**</span></span>  
 <span data-ttu-id="83ff6-112">Elija un visor para explorar el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="83ff6-112">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="83ff6-113">Puede utilizar el visor personalizado o el **Visor de árbol de contenido genérico de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="83ff6-113">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="83ff6-114">También puede utilizar visores de complemento si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="83ff6-114">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="83ff6-115">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="83ff6-115">**Input**</span></span>  
 <span data-ttu-id="83ff6-116">Use esta área para elegir atributos y valores de entrada, para que pueda explorar después cómo éstos afectan al resultado.</span><span class="sxs-lookup"><span data-stu-id="83ff6-116">Use this area to choose input attributes and values, so that you can later explore how these affect the outcome.</span></span>  
  
|<span data-ttu-id="83ff6-117">Value</span><span class="sxs-lookup"><span data-stu-id="83ff6-117">Value</span></span>|<span data-ttu-id="83ff6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="83ff6-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83ff6-119">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="83ff6-119">**Attribute**</span></span>|<span data-ttu-id="83ff6-120">Elija un atributo de entrada en la lista.</span><span class="sxs-lookup"><span data-stu-id="83ff6-120">Choose an input attribute from the list.</span></span> <span data-ttu-id="83ff6-121">Si deja la selección como predeterminada, **\<All>** el gráfico muestra una lista de todos los atributos de entrada, clasificados por su impacto en el atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="83ff6-121">If you leave the selection as the default, **\<All>**, the chart shows a list of all input attributes, ranked by their impact on the predictable attribute.</span></span>|  
|<span data-ttu-id="83ff6-122">**Valor**</span><span class="sxs-lookup"><span data-stu-id="83ff6-122">**Value**</span></span>|<span data-ttu-id="83ff6-123">Elija un valor para el atributo de entrada.</span><span class="sxs-lookup"><span data-stu-id="83ff6-123">Choose a value for the input attribute.</span></span>|  
  
 <span data-ttu-id="83ff6-124">**Salida**</span><span class="sxs-lookup"><span data-stu-id="83ff6-124">**Output**</span></span>  
 <span data-ttu-id="83ff6-125">Utilice estos controles para elegir un atributo y valor de predicción para analizar y comparar en el gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="83ff6-125">Use these controls to choose a predictable attribute and value to analyze and compare in the bar graph.</span></span> <span data-ttu-id="83ff6-126">Si no cambia las selecciones, el gráfico de barras compara los dos estados del resultado superiores.</span><span class="sxs-lookup"><span data-stu-id="83ff6-126">If you do not change the selections, the bar graph compares the top two outcome states.</span></span>  
  
|<span data-ttu-id="83ff6-127">Value</span><span class="sxs-lookup"><span data-stu-id="83ff6-127">Value</span></span>|<span data-ttu-id="83ff6-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="83ff6-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83ff6-129">**Atributo de salida**</span><span class="sxs-lookup"><span data-stu-id="83ff6-129">**Output Attribute**</span></span>|<span data-ttu-id="83ff6-130">Elija un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="83ff6-130">Choose a predictable attribute.</span></span> <span data-ttu-id="83ff6-131">Si no definió la columna como una columna de predicción cuando creó el modelo, no podrá agregarla aquí.</span><span class="sxs-lookup"><span data-stu-id="83ff6-131">If you did not define the column as a predictable one when you created the model, you cannot add it here.</span></span>|  
|<span data-ttu-id="83ff6-132">**Valor 1**</span><span class="sxs-lookup"><span data-stu-id="83ff6-132">**Value 1**</span></span>|<span data-ttu-id="83ff6-133">Elija un estado del atributo de predicción para compararlo con el estado contenido en el **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="83ff6-133">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span><br /><br /> <span data-ttu-id="83ff6-134">Puede comparar cualesquiera dos valores discretos o de datos discretos; sin embargo, no puede comparar un valor con su complemento, como lo haría en otros visores.</span><span class="sxs-lookup"><span data-stu-id="83ff6-134">You can compare any two discrete or discretized values; however, you cannot compare a value to its complement, as you can in other viewers.</span></span>|  
|<span data-ttu-id="83ff6-135">**Valor 2**</span><span class="sxs-lookup"><span data-stu-id="83ff6-135">**Value 2**</span></span>|<span data-ttu-id="83ff6-136">Seleccione un estado del atributo de predicción para compararlo con el estado contenido en el **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="83ff6-136">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span>|  
  
 <span data-ttu-id="83ff6-137">**Variables**</span><span class="sxs-lookup"><span data-stu-id="83ff6-137">**Variables**</span></span>  
 <span data-ttu-id="83ff6-138">Esta parte de la pestaña **Red neuronal** contiene un gráfico de barras interactivo, que responde a las selecciones realizadas para los atributos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="83ff6-138">This part of the **Neural Network** tab contains an interactive bar graph, which responds to the selections that you made for input and outcome attributes.</span></span> <span data-ttu-id="83ff6-139">Dado que una red neural calcula la probabilidad de que un determinado valor influya en un determinado resultado, puede elegir cualquier combinación de entradas, y el gráfico de barras mostrará cómo afecta esa combinación al par de resultados que está comparando.</span><span class="sxs-lookup"><span data-stu-id="83ff6-139">Because a neural network calculates the likelihood that a particular value influences a particular outcome, you can choose any combination of inputs, and the bar chart will display how that combination affects the pair of outcomes that you are comparing.</span></span>  
  
|<span data-ttu-id="83ff6-140">Value</span><span class="sxs-lookup"><span data-stu-id="83ff6-140">Value</span></span>|<span data-ttu-id="83ff6-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="83ff6-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83ff6-142">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="83ff6-142">**Attribute**</span></span>|<span data-ttu-id="83ff6-143">Muestra el nombre del atributo de entrada seleccionado en **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="83ff6-143">Shows the name of the input attribute you selected in **Attribute**.</span></span>|  
|<span data-ttu-id="83ff6-144">**Valor**</span><span class="sxs-lookup"><span data-stu-id="83ff6-144">**Value**</span></span>|<span data-ttu-id="83ff6-145">Muestra el valor del atributo de entrada seleccionado.</span><span class="sxs-lookup"><span data-stu-id="83ff6-145">Shows the value for the selected input attribute.</span></span>|  
|<span data-ttu-id="83ff6-146">**Favorece\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="83ff6-146">**Favors \<Value 1>**</span></span>|<span data-ttu-id="83ff6-147">Muestra una barra que indica en qué medida esta combinación de atributo-valor afecta al resultado del destino elegido en **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="83ff6-147">Displays a bar that indicates how much this particular attribute-value combination affects the target outcome chosen in **Value 1**.</span></span>|  
|<span data-ttu-id="83ff6-148">**Favorece\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="83ff6-148">**Favors \<Value 2>**</span></span>|<span data-ttu-id="83ff6-149">Muestra una barra que indica en qué medida esta combinación de atributo-valor afecta al resultado del destino elegido en **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="83ff6-149">Displays a bar that indicates how much this particular attribute-value combination affects the target outcome chosen in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83ff6-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83ff6-150">See Also</span></span>  
 <span data-ttu-id="83ff6-151">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="83ff6-151">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="83ff6-152">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="83ff6-152">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="83ff6-153">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="83ff6-153">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
