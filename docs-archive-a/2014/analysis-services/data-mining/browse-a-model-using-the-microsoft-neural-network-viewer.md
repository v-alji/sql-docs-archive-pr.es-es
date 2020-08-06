---
title: Examinar un modelo mediante el visor de red neuronal de Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
- classification mining model [Analysis Services]
- Microsoft Neural Network Viewer
- regression algorithms [Analysis Services]
- Neural Network Viewer [Analysis Services]
- neural network model [Analysis Services]
ms.assetid: 2343d746-c4f4-499b-9d3c-17d63310a9a3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 77e08955d09b7995e34ac94b75f809a303ca0d2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677976"
---
# <a name="browse-a-model-using-the-microsoft-neural-network-viewer"></a><span data-ttu-id="f821a-102">Examinar un modelo usando el Visor de redes neuronales de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f821a-102">Browse a Model Using the Microsoft Neural Network Viewer</span></span>
  <span data-ttu-id="f821a-103">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] visor de red neuronal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] muestra los modelos de minería de datos que se generan con el [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo de red neuronal de.</span><span class="sxs-lookup"><span data-stu-id="f821a-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm.</span></span> <span data-ttu-id="f821a-104">El algoritmo de red neuronal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] crea modelos de minería de datos de regresión y de clasificación que pueden analizar entradas y salidas múltiples, y es muy útil para los análisis de final abierto y la exploración.</span><span class="sxs-lookup"><span data-stu-id="f821a-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm creates classification and regression mining models that can analyze multiple inputs and outputs, and is very useful for open-ended analyses and exploration.</span></span> <span data-ttu-id="f821a-105">Para obtener más información acerca de este algoritmo, vea [Microsoft Neural Network Algorithm](microsoft-neural-network-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="f821a-105">For more information about this algorithm, see [Microsoft Neural Network Algorithm](microsoft-neural-network-algorithm.md).</span></span>  
  
 <span data-ttu-id="f821a-106">Cuando se explora un modelo usando el Visor de redes neuronales de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , se suele elegir un determinado atributo y estado de destino, y después se usa el visor para ver cómo afectan al resultado los atributos de entrada.</span><span class="sxs-lookup"><span data-stu-id="f821a-106">When you explore a model using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network Viewer, you typically pick some target attribute and state, and then use the viewer to see how input attributes affect the outcome</span></span>  
  
 <span data-ttu-id="f821a-107">Por ejemplo, suponga que conoce estos hechos sobre una clase de clientes potenciales:</span><span class="sxs-lookup"><span data-stu-id="f821a-107">For example, suppose you know these facts about a class of potential customers:</span></span>  
  
-   <span data-ttu-id="f821a-108">Mediana edad (40 a 50 años).</span><span class="sxs-lookup"><span data-stu-id="f821a-108">Middle aged (40 to 50 years old).</span></span>  
  
-   <span data-ttu-id="f821a-109">Tiene casa en propiedad.</span><span class="sxs-lookup"><span data-stu-id="f821a-109">Owns a home.</span></span>  
  
-   <span data-ttu-id="f821a-110">Tiene dos hijos que todavía viven en casa.</span><span class="sxs-lookup"><span data-stu-id="f821a-110">Has two children who still live at home.</span></span>  
  
 <span data-ttu-id="f821a-111">¿Cómo puede correlacionar estos atributos con la probabilidad de que el cliente haga una compra?</span><span class="sxs-lookup"><span data-stu-id="f821a-111">How can you correlate these attributes with the likelihood that the customer will make a purchase?</span></span>  
  
 <span data-ttu-id="f821a-112">Mediante la construcción de un modelo de red neuronal que use los hábitos de compra como resultado de destino, puede explorar diversas combinaciones de atributos del cliente, tales como ingresos altos, y descubrir qué combinación de atributos es más probable que influya en los hábitos de compra.</span><span class="sxs-lookup"><span data-stu-id="f821a-112">By building a neural network model using purchasing behavior as the target outcome, you can explore multiple combinations on customer attributes, such as high income, and discover which combination of attributes is most likely to influence purchasing behavior.</span></span> <span data-ttu-id="f821a-113">Por ejemplo, puede que descubra que el factor determinante es la distancia entre su domicilio y el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f821a-113">For example, you might discover that the determining factor is the distance that they commute to work.</span></span>  
  
 <span data-ttu-id="f821a-114">Si necesita información más detallada, como las ecuaciones que representan cada patrón descubierto, puede cambiar de vista y usar el Visor de árbol de contenido genérico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f821a-114">If you need to more view detailed information, such as the equations that represent each pattern that was discovered, you can switch views and use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="f821a-115">Para obtener más información, vea [Examinar un modelo usando el Visor de árbol de contenido genérico de Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) o [Visor de árbol de contenido genérico de Microsoft &#40;Minería de datos&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f821a-115">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="f821a-116">Pestañas del visor</span><span class="sxs-lookup"><span data-stu-id="f821a-116">Viewer Tabs</span></span>  
 <span data-ttu-id="f821a-117">Cuando se explora un modelo de minería de datos en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], el modelo aparece en la pestaña **Visor de modelos de minería de datos** del visor del diseñador de minería de datos apropiado para el modelo.</span><span class="sxs-lookup"><span data-stu-id="f821a-117">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="f821a-118">El Visor de redes neuronales de [!INCLUDE[msCoName](../../includes/msconame-md.md)] ofrece las siguientes pestañas para usarlas con el fin de explorar modelos de minería de datos de redes neuronales:</span><span class="sxs-lookup"><span data-stu-id="f821a-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network Viewer provides the following tabs for use in exploring neural network mining models:</span></span>  
  
-   [<span data-ttu-id="f821a-119">Entradas</span><span class="sxs-lookup"><span data-stu-id="f821a-119">Inputs</span></span>](#BKMK_Inputs)  
  
-   [<span data-ttu-id="f821a-120">Salidas</span><span class="sxs-lookup"><span data-stu-id="f821a-120">Outputs</span></span>](#BKMK_Outputs)  
  
-   [<span data-ttu-id="f821a-121">Variables</span><span class="sxs-lookup"><span data-stu-id="f821a-121">Variables</span></span>](#BKMK_Characteristics)  
  
###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="f821a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f821a-122">Inputs</span></span>  
 <span data-ttu-id="f821a-123">Use la pestaña **Entradas** para elegir los atributos y los valores que usará el modelo como entradas.</span><span class="sxs-lookup"><span data-stu-id="f821a-123">Use the **Inputs** tab to choose the attributes and values that the model used as inputs.</span></span> <span data-ttu-id="f821a-124">De forma predeterminada, el visor se abre con todos los atributos incluidos.</span><span class="sxs-lookup"><span data-stu-id="f821a-124">By default, the viewer opens with all attributes included.</span></span> <span data-ttu-id="f821a-125">En esta vista predeterminada, el modelo elige qué valores de los atributos son los más importantes que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="f821a-125">In this default view, the model chooses which attribute values are the most important to display.</span></span>  
  
 <span data-ttu-id="f821a-126">Para seleccionar un atributo de entrada, haga clic en la columna **Atributo** de la cuadrícula **Entrada** y, después, seleccione un atributo de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f821a-126">To select an input attribute, click inside the **Attribute** column of the **Input** grid, and select an attribute from the drop-down list.</span></span> <span data-ttu-id="f821a-127">(En la lista solo están incluidos los atributos presentes en el modelo).</span><span class="sxs-lookup"><span data-stu-id="f821a-127">(Only attributes that are included in the model are included in the list.)</span></span>  
  
 <span data-ttu-id="f821a-128">El primer valor distinto aparece en la columna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="f821a-128">The first distinct value appears under the **Value** column.</span></span> <span data-ttu-id="f821a-129">Si hace clic en el valor predeterminado aparece una lista que contiene los posibles estados del atributo asociado.</span><span class="sxs-lookup"><span data-stu-id="f821a-129">Clicking the default value reveals a list that contains all the possible states of the associated attribute.</span></span> <span data-ttu-id="f821a-130">Puede seleccionar el estado que desea investigar.</span><span class="sxs-lookup"><span data-stu-id="f821a-130">You can select the state that you want to investigate.</span></span> <span data-ttu-id="f821a-131">Puede seleccionar tantos atributos como desee.</span><span class="sxs-lookup"><span data-stu-id="f821a-131">You can select as many attributes as you want.</span></span>  
  
 [<span data-ttu-id="f821a-132">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f821a-132">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="f821a-133">Salidas</span><span class="sxs-lookup"><span data-stu-id="f821a-133">Outputs</span></span>  
 <span data-ttu-id="f821a-134">Use la pestaña **Salidas** para elegir el atributo de resultados que se debe investigar.</span><span class="sxs-lookup"><span data-stu-id="f821a-134">Use the **Outputs** tab to choose the outcome attribute to investigate.</span></span> <span data-ttu-id="f821a-135">Puede elegir dos estados resultantes cualesquiera para compararlos, suponiendo que las columnas se definieron como atributos de predicción cuando se creó el modelo.</span><span class="sxs-lookup"><span data-stu-id="f821a-135">You can choose any two outcome states to compare, assuming the columns were defined as predictable attributes when the model was created.</span></span>  
  
 <span data-ttu-id="f821a-136">Use la lista **Atributo de salida** para seleccionar un atributo.</span><span class="sxs-lookup"><span data-stu-id="f821a-136">Use the **OutputAttribute** list to select an attribute.</span></span> <span data-ttu-id="f821a-137">Después puede seleccionar dos estados asociados con el atributo en las listas **Valor 1** y **Valor 2** .</span><span class="sxs-lookup"><span data-stu-id="f821a-137">You can then select two states that are associated with the attribute from the **Value 1** and **Value 2** lists.</span></span> <span data-ttu-id="f821a-138">Estos dos estados del atributo de salida se compararán en el panel **Variables** .</span><span class="sxs-lookup"><span data-stu-id="f821a-138">These two states of the output attribute will be compared in the **Variables** pane.</span></span>  
  
 [<span data-ttu-id="f821a-139">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f821a-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="variables"></a><a name="BKMK_Characteristics"></a><span data-ttu-id="f821a-140">Variable</span><span class="sxs-lookup"><span data-stu-id="f821a-140">Variables</span></span>  
 <span data-ttu-id="f821a-141">La cuadrícula de la pestaña **Variables** contiene las columnas siguientes: **Atributo**, **Valor**, **Favorece [valor 1]** y **Favorece [valor 2]**.</span><span class="sxs-lookup"><span data-stu-id="f821a-141">The grid in the **Variables** tab contains the following columns: **Attribute**, **Value**, **Favors [value 1]**, and **Favors [value 2]**.</span></span> <span data-ttu-id="f821a-142">De forma predeterminada, las columnas se ordenan por la intensidad de **Favorece [valor 1]**.</span><span class="sxs-lookup"><span data-stu-id="f821a-142">By default, the columns are sorted by the strength of **Favors [value 1]**.</span></span> <span data-ttu-id="f821a-143">Si hace clic en un encabezado de columna, cambia el orden de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f821a-143">Clicking a column heading changes the sort order to the selected column.</span></span>  
  
 <span data-ttu-id="f821a-144">Una barra a la derecha del atributo muestra el estado del atributo de entrada que el estado del atributo de salida favorece.</span><span class="sxs-lookup"><span data-stu-id="f821a-144">A bar to the right of the attribute shows which state of the output attribute the specified input attribute state favors.</span></span> <span data-ttu-id="f821a-145">El tamaño de la barra muestra la intensidad con la que el estado de salida favorece al estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="f821a-145">The size of the bar shows how strongly the output state favors the input state.</span></span>  
  
 [<span data-ttu-id="f821a-146">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f821a-146">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="f821a-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f821a-147">See Also</span></span>  
 <span data-ttu-id="f821a-148">[Algoritmo de red neuronal de Microsoft](microsoft-neural-network-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="f821a-148">[Microsoft Neural Network Algorithm](microsoft-neural-network-algorithm.md) </span></span>  
 <span data-ttu-id="f821a-149">[Tareas y procedimientos del visor de modelos de minería de datos](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f821a-149">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="f821a-150">[Tareas y procedimientos del visor de modelos de minería de datos](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f821a-150">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="f821a-151">[Herramientas de minería de datos](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f821a-151">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="f821a-152">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f821a-152">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
