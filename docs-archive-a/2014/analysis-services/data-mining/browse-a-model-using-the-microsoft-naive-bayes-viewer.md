---
title: Examinar un modelo usando el visor Bayes Naive de Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discrimination [Analysis Services]
- naive bayes model [Analysis Services]
- Bayesian classifiers
- mining model content, viewing
- predictive modeling [Analysis Services]
- Naive Bayes Viewer [Analysis Services]
- data mining [Analysis Services], predictive modeling
- Microsoft Naive Bayes Viewer
- histograms [Analysis Services]
- mining models [Analysis Services], predictive modeling
- dependencies [Analysis Services]
ms.assetid: 19743095-63c1-4486-8c1d-2efc143243be
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03469e73d82a389426f91d8757630f50fe78fc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677979"
---
# <a name="browse-a-model-using-the-microsoft-naive-bayes-viewer"></a><span data-ttu-id="f2e23-102">Examinar un modelo usando el visor Bayes naive de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2e23-102">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>
  <span data-ttu-id="f2e23-103">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] visor Bayes Naive de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] muestra los modelos de minería de datos que se generan con el [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo Bayes Naive de.</span><span class="sxs-lookup"><span data-stu-id="f2e23-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm.</span></span> <span data-ttu-id="f2e23-104">El algoritmo Bayes naive de [!INCLUDE[msCoName](../../includes/msconame-md.md)] es un algoritmo de clasificación que se adapta muy bien a las tareas de modelado de predicción.</span><span class="sxs-lookup"><span data-stu-id="f2e23-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm that is highly adaptable to predictive modeling tasks.</span></span> <span data-ttu-id="f2e23-105">Para obtener más información acerca de este algoritmo, vea [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="f2e23-105">For more information about this algorithm, see [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="f2e23-106">Como uno de los principales propósitos de un modelo Bayes naive es ofrecer una manera rápida de explorar los datos de un conjunto de datos, el Visor Bayes naive de [!INCLUDE[msCoName](../../includes/msconame-md.md)] proporciona varios métodos para mostrar la interacción entre los atributos de predicción y los atributos de entrada.</span><span class="sxs-lookup"><span data-stu-id="f2e23-106">Because one of the main purposes of a naive Bayes model is to provide a way to quickly explore the data in a dataset, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides several methods for displaying the interaction between predictable attributes and input attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2e23-107">Si desea ver información detallada acerca de las ecuaciones que se usan en el modelo y los patrones detectados, puede cambiar al Visor de árbol de contenido genérico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2e23-107">If you want to view detailed information about the equations used in the model and the patterns that were discovered, you can switch to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="f2e23-108">Para obtener más información, vea [Examinar un modelo usando el Visor de árbol de contenido genérico de Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) o [Visor de árbol de contenido genérico de Microsoft &#40;Minería de datos&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f2e23-108">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="f2e23-109">Pestañas del visor</span><span class="sxs-lookup"><span data-stu-id="f2e23-109">Viewer Tabs</span></span>  
 <span data-ttu-id="f2e23-110">Cuando se explora un modelo de minería de datos en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], el modelo aparece en la pestaña **Visor de modelos de minería de datos** del visor del diseñador de minería de datos apropiado para el modelo.</span><span class="sxs-lookup"><span data-stu-id="f2e23-110">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="f2e23-111">El Visor Bayes naive de [!INCLUDE[msCoName](../../includes/msconame-md.md)] dispone de las siguientes pestañas para explorar datos:</span><span class="sxs-lookup"><span data-stu-id="f2e23-111">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for exploring data:</span></span>  
  
-   [<span data-ttu-id="f2e23-112">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="f2e23-112">Dependency Network</span></span>](#BKMK_Dependency)  
  
-   [<span data-ttu-id="f2e23-113">Perfiles del atributo</span><span class="sxs-lookup"><span data-stu-id="f2e23-113">Attribute Profiles</span></span>](#BKMK_Profiles)  
  
-   [<span data-ttu-id="f2e23-114">Características del atributo</span><span class="sxs-lookup"><span data-stu-id="f2e23-114">Attribute Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="f2e23-115">Distinción del atributo</span><span class="sxs-lookup"><span data-stu-id="f2e23-115">Attribute Discrimination</span></span>](#BKMK_Discrimination)  
  
##  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="f2e23-116">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="f2e23-116">Dependency Network</span></span>  
 <span data-ttu-id="f2e23-117">La pestaña **Red de dependencias** muestra las dependencias entre los atributos de entrada y los atributos de predicción de un modelo.</span><span class="sxs-lookup"><span data-stu-id="f2e23-117">The **Dependency Network** tab displays the dependencies between the input attributes and the predictable attributes in a model.</span></span> <span data-ttu-id="f2e23-118">El control deslizante de la izquierda del visor se comporta como un filtro que está asociado a la importancia de las dependencias.</span><span class="sxs-lookup"><span data-stu-id="f2e23-118">The slider at the left of the viewer acts as a filter that is tied to the strengths of the dependencies.</span></span> <span data-ttu-id="f2e23-119">Si desplaza el control deslizante hacia abajo, sólo se verán los vínculos más similares.</span><span class="sxs-lookup"><span data-stu-id="f2e23-119">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="f2e23-120">Cuando se selecciona un nodo, el visor resalta las dependencias específicas de dicho nodo.</span><span class="sxs-lookup"><span data-stu-id="f2e23-120">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="f2e23-121">Por ejemplo, si elige un nodo de predicción, el visor también resalta cada uno de los nodos que ayudan a predecir el nodo de predicción.</span><span class="sxs-lookup"><span data-stu-id="f2e23-121">For example, if you choose a predictable node, the viewer also highlights each node that helps predict the predictable node.</span></span>  
  
 <span data-ttu-id="f2e23-122">La leyenda de la parte inferior del visor vincula códigos de color con el tipo de dependencia en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="f2e23-122">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="f2e23-123">Por ejemplo, cuando selecciona un nodo de predicción, este nodo se sombrea en color turquesa y los nodos que predicen el nodo seleccionado aparecen sombreados en color naranja.</span><span class="sxs-lookup"><span data-stu-id="f2e23-123">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="f2e23-124">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f2e23-124">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-profiles"></a><a name="BKMK_Profiles"></a><span data-ttu-id="f2e23-125">Perfiles de atributo</span><span class="sxs-lookup"><span data-stu-id="f2e23-125">Attribute Profiles</span></span>  
 <span data-ttu-id="f2e23-126">La pestaña **Perfiles del atributo** muestra histogramas en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2e23-126">The **Attribute Profiles** tab displays histograms in a grid.</span></span> <span data-ttu-id="f2e23-127">Puede utilizar esta cuadrícula para comparar el atributo de predicción seleccionado en el cuadro **De predicción** con los demás atributos del modelo.</span><span class="sxs-lookup"><span data-stu-id="f2e23-127">You can use this grid to compare the predictable attribute that you select in the **Predictable** box to all other attributes that are in the model.</span></span> <span data-ttu-id="f2e23-128">Cada columna de la pestaña representa un estado del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="f2e23-128">Each column in the tab represents a state of the predictable attribute.</span></span> <span data-ttu-id="f2e23-129">Si el atributo de predicción tiene muchos estados, puede cambiar el número de estados que aparecen en el histograma ajustando las **Barras de histograma**.</span><span class="sxs-lookup"><span data-stu-id="f2e23-129">If the predictable attribute has many states, you can change the number of states that appear in the histogram by adjusting the **Histogram bars**.</span></span> <span data-ttu-id="f2e23-130">Si el número que elige es menor que el número total de estados del atributo, los estados se enumerarán en orden de compatibilidad, con los estados restantes recopilados en un único depósito deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f2e23-130">If the number you choose is less than the total number of states in the attribute, the states are listed in order of support, with the remaining states collected into a single gray bucket.</span></span>  
  
 <span data-ttu-id="f2e23-131">Para mostrar una leyenda de minería de datos que relaciona los colores del histograma con los estados de un atributo, active la casilla **Mostrar leyenda** .</span><span class="sxs-lookup"><span data-stu-id="f2e23-131">To display a Mining Legend that relates the colors of the histogram to the states of an attribute, click the **Show Legend** check box.</span></span> <span data-ttu-id="f2e23-132">La Leyenda de minería de datos también muestra la distribución de casos para cada par de atributo-valor que seleccione.</span><span class="sxs-lookup"><span data-stu-id="f2e23-132">The Mining Legend also displays the distribution of cases for each attribute-value pair that you select.</span></span>  
  
 <span data-ttu-id="f2e23-133">Para copiar el contenido de la cuadrícula en el Portapapeles como una tabla HTML, haga clic con el botón derecho en la pestaña **Perfiles del atributo** y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="f2e23-133">To copy the contents of the grid to the Clipboard as an HTML table, right-click the **Attribute Profiles** tab and select **Copy**.</span></span>  
  
 [<span data-ttu-id="f2e23-134">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f2e23-134">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-characteristics"></a><a name="BKMK_Characteristics"></a><span data-ttu-id="f2e23-135">Características del atributo</span><span class="sxs-lookup"><span data-stu-id="f2e23-135">Attribute Characteristics</span></span>  
 <span data-ttu-id="f2e23-136">Para usar la pestaña **Características del atributo** , seleccione un atributo de predicción en la lista **Atributo** y elija un estado del atributo seleccionado en la lista **Valor** .</span><span class="sxs-lookup"><span data-stu-id="f2e23-136">To use the **Attribute Characteristics** tab, select a predictable attribute from the **Attribute** list and select a state of the selected attribute from the **Value** list.</span></span> <span data-ttu-id="f2e23-137">Al establecer estas variables, la pestaña **Características del atributo** muestra los estados de los atributos que están asociados con el caso seleccionado del atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f2e23-137">When you set these variables, the **Attribute Characteristics** tab displays the states of the attributes that are associated with the selected case of the selected attribute.</span></span> <span data-ttu-id="f2e23-138">Los atributos se ordenan por importancia.</span><span class="sxs-lookup"><span data-stu-id="f2e23-138">The attributes are sorted by importance.</span></span>  
  
 [<span data-ttu-id="f2e23-139">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f2e23-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-discrimination"></a><a name="BKMK_Discrimination"></a><span data-ttu-id="f2e23-140">Distinción de atributos</span><span class="sxs-lookup"><span data-stu-id="f2e23-140">Attribute Discrimination</span></span>  
 <span data-ttu-id="f2e23-141">Para usar la pestaña **Distinción del atributo** , seleccione un atributo de predicción y dos de sus estados en las listas **Atributo**, **Valor 1**y **Valor 2** .</span><span class="sxs-lookup"><span data-stu-id="f2e23-141">To use the **Attribute Discrimination** tab, select a predictable attribute and two of its states from the **Attribute**, **Value 1**, and **Value 2** lists.</span></span> <span data-ttu-id="f2e23-142">La cuadrícula de la pestaña **Distinción del atributo** mostrará entonces la siguiente información en columnas:</span><span class="sxs-lookup"><span data-stu-id="f2e23-142">The grid on the **Attribute Discrimination** tab then displays the following information in columns:</span></span>  
  
 <span data-ttu-id="f2e23-143">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="f2e23-143">**Attribute**</span></span>  
 <span data-ttu-id="f2e23-144">Muestra otros atributos del conjunto de datos que contienen un estado que favorece claramente un estado del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="f2e23-144">Lists other attributes in the dataset that contain a state that highly favors one state of the predictable attribute.</span></span>  
  
 <span data-ttu-id="f2e23-145">**Valores**</span><span class="sxs-lookup"><span data-stu-id="f2e23-145">**Values**</span></span>  
 <span data-ttu-id="f2e23-146">Muestra el valor del atributo en la columna **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="f2e23-146">Shows the value of the attribute in the **Attribute** column.</span></span>  
  
 <span data-ttu-id="f2e23-147">**Favorece\<value 1>**</span><span class="sxs-lookup"><span data-stu-id="f2e23-147">**Favors \<value 1>**</span></span>  
 <span data-ttu-id="f2e23-148">Muestra una barra coloreada que indica la intensidad con la que el valor de atributo favorece el valor de atributo predecible mostrado en **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="f2e23-148">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 1**.</span></span>  
  
 <span data-ttu-id="f2e23-149">**Favorece\<value 2>**</span><span class="sxs-lookup"><span data-stu-id="f2e23-149">**Favors \<value 2>**</span></span>  
 <span data-ttu-id="f2e23-150">Muestra una barra coloreada que indica la intensidad con la que el valor de atributo favorece el valor de atributo predecible mostrado en **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="f2e23-150">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 2**.</span></span>  
  
 [<span data-ttu-id="f2e23-151">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f2e23-151">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="f2e23-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2e23-152">See Also</span></span>  
 <span data-ttu-id="f2e23-153">[Algoritmo Bayes Naive de Microsoft](microsoft-naive-bayes-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="f2e23-153">[Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md) </span></span>  
 <span data-ttu-id="f2e23-154">[Tareas y procedimientos del visor de modelos de minería de datos](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f2e23-154">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="f2e23-155">[Herramientas de minería de datos](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f2e23-155">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="f2e23-156">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f2e23-156">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
