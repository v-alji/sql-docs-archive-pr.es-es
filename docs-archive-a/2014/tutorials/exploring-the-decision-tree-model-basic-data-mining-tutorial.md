---
title: Explorar el modelo de árbol de decisión (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2e1472c2-3f3e-4dae-acb3-62fca374d397
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a2c7f063d7cb73cdc431fb1bc94188c9266c10c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747318"
---
# <a name="exploring-the-decision-tree-model-basic-data-mining-tutorial"></a><span data-ttu-id="2b306-102">Explorar el modelo de árbol de decisión (tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="2b306-102">Exploring the Decision Tree Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="2b306-103">El algoritmo de árboles de decisión de [!INCLUDE[msCoName](../includes/msconame-md.md)] predice qué columnas influyen en la decisión de comprar una bicicleta en función de las columnas restantes del conjunto de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2b306-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm predicts which columns influence the decision to purchase a bike based upon the remaining columns in the training set.</span></span>  
  

  
##  <a name="decision-tree-tab"></a><a name="Decision_Tree_Tab"></a><span data-ttu-id="2b306-104">Pestaña árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="2b306-104">Decision Tree Tab</span></span>  
 <span data-ttu-id="2b306-105">En la pestaña **árbol de decisión** , puede ver los árboles de decisión para cada atributo de predicción del conjunto de información.</span><span class="sxs-lookup"><span data-stu-id="2b306-105">On the **Decision Tree** tab, you can view decision trees for every predictable attribute in the dataset.</span></span>  
  
 <span data-ttu-id="2b306-106">En este caso, el modelo predice solo una columna, Bike Buyer, por lo que solo hay un árbol para ver.</span><span class="sxs-lookup"><span data-stu-id="2b306-106">In this case, the model predicts only one column, Bike Buyer, so there is only one tree to view.</span></span> <span data-ttu-id="2b306-107">Si hubiera más árboles, podría usar el cuadro de **árbol** para elegir otro árbol.</span><span class="sxs-lookup"><span data-stu-id="2b306-107">If there were more trees, you could use the **Tree** box to choose another tree.</span></span>  
  
 <span data-ttu-id="2b306-108">Al ver el `TM_Decision_Tree` modelo en el visor de árboles de decisión, puede ver los atributos más importantes en el lado izquierdo del gráfico.</span><span class="sxs-lookup"><span data-stu-id="2b306-108">As you view the `TM_Decision_Tree` model in the Decision Tree viewer, you can see the most important attributes at the left side of the chart.</span></span> <span data-ttu-id="2b306-109">"Más importante" significa que estos atributos tienen la mayor influencia en el resultado.</span><span class="sxs-lookup"><span data-stu-id="2b306-109">"Most important" means that these attributes have the greatest influence on the outcome.</span></span> <span data-ttu-id="2b306-110">Los atributos situados más abajo en el árbol (a la derecha del gráfico) tiene menos efecto.</span><span class="sxs-lookup"><span data-stu-id="2b306-110">Attributes further down the tree (to the right of the chart) have less of an effect.</span></span>  
  
 <span data-ttu-id="2b306-111">En este ejemplo, la edad es el factor único más importante para predecir la compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="2b306-111">In this example, age is the single most important factor in predicting bike buying.</span></span> <span data-ttu-id="2b306-112">El modelo agrupa los clientes por edad y, a continuación, muestra el siguiente atributo más importante para cada grupo de edad.</span><span class="sxs-lookup"><span data-stu-id="2b306-112">The model groups customers by age, and then shows the next more important attribute for each age group.</span></span> <span data-ttu-id="2b306-113">Por ejemplo, en el grupo de clientes de entre 34 y 40 años, el número de automóviles en propiedad es el factor de predicción más seguro después de la edad.</span><span class="sxs-lookup"><span data-stu-id="2b306-113">For example, in the group of customers aged 34 to 40, the number of cars owned is the strongest predictor after age.</span></span>  
  
#### <a name="to-explore-the-model-in-the-decision-tree-tab"></a><span data-ttu-id="2b306-114">Para explorar el modelo en la pestaña Árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="2b306-114">To explore the model in the Decision Tree tab</span></span>  
  
1.  <span data-ttu-id="2b306-115">Seleccione la pestaña **Visor de modelo de minería de datos** en **Diseñador de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="2b306-115">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
     <span data-ttu-id="2b306-116">De forma predeterminada, el diseñador se abre en el primer modelo que se agregó a la estructura, en este caso, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="2b306-116">By default, the designer opens to the first model that was added to the structure -- in this case, `TM_Decision_Tree`.</span></span>  
  
2.  <span data-ttu-id="2b306-117">Utilice los botones de lupa para ajustar el tamaño de presentación del árbol.</span><span class="sxs-lookup"><span data-stu-id="2b306-117">Use the magnifying glass buttons to adjust the size of the tree display.</span></span>  
  
     <span data-ttu-id="2b306-118">De manera predeterminada, el Visor de árboles de [!INCLUDE[msCoName](../includes/msconame-md.md)] solo muestra los primeros tres niveles del árbol.</span><span class="sxs-lookup"><span data-stu-id="2b306-118">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer shows only the first three levels of the tree.</span></span> <span data-ttu-id="2b306-119">Si el árbol contiene menos de tres niveles, el visor mostrará solo los niveles existentes.</span><span class="sxs-lookup"><span data-stu-id="2b306-119">If the tree contains fewer than three levels, the viewer shows only the existing levels.</span></span> <span data-ttu-id="2b306-120">Puede ver más niveles mediante el control deslizante **Mostrar nivel** o la lista de **expansión predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="2b306-120">You can view more levels by using the **Show Level** slider or the **Default Expansion** list.</span></span>  
  
3.  <span data-ttu-id="2b306-121">**Nivel** de presentación en la cuarta barra.</span><span class="sxs-lookup"><span data-stu-id="2b306-121">Slide **Show Level** to the fourth bar.</span></span>  
  
4.  <span data-ttu-id="2b306-122">Cambie el valor de **fondo** a `1` .</span><span class="sxs-lookup"><span data-stu-id="2b306-122">Change the **Background** value to `1`.</span></span>  
  
     <span data-ttu-id="2b306-123">Al cambiar la configuración de **fondo** , puede ver rápidamente el número de casos de cada nodo que tienen el valor de destino de `1` para [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="2b306-123">By changing the **Background** setting, you can quickly see the number of cases in each node that have the target value of `1` for [Bike Buyer].</span></span> <span data-ttu-id="2b306-124">Recuerde que en este escenario en concreto, cada caso representa un cliente.</span><span class="sxs-lookup"><span data-stu-id="2b306-124">Remember that in this particular scenario, each case represents a customer.</span></span> <span data-ttu-id="2b306-125">El valor `1` indica que el cliente ha adquirido previamente una bicicleta; el valor **0** indica que el cliente no ha comprado una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="2b306-125">The value `1` indicates that the customer previously purchased a bike; the value **0** indicates that the customer has not purchased a bike.</span></span> <span data-ttu-id="2b306-126">Cuanto más oscuro sea el sombreado del nodo, mayor será el porcentaje de casos del nodo que tienen el valor de destino.</span><span class="sxs-lookup"><span data-stu-id="2b306-126">The darker the shading of the node, the higher the percentage of cases in the node that have the target value.</span></span>  
  
5.  <span data-ttu-id="2b306-127">Coloque el cursor sobre el nodo con la etiqueta **todo**.</span><span class="sxs-lookup"><span data-stu-id="2b306-127">Place your cursor over the node labeled **All**.</span></span> <span data-ttu-id="2b306-128">Se mostrará información sobre herramientas con los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="2b306-128">An tooltip will display the following information:</span></span>  
  
    -   <span data-ttu-id="2b306-129">Número total de casos</span><span class="sxs-lookup"><span data-stu-id="2b306-129">Total number of cases</span></span>  
  
    -   <span data-ttu-id="2b306-130">Número de casos de personas que no han comprado bicicletas</span><span class="sxs-lookup"><span data-stu-id="2b306-130">Number of non bike buyer cases</span></span>  
  
    -   <span data-ttu-id="2b306-131">Número de casos de personas que han comprado bicicletas</span><span class="sxs-lookup"><span data-stu-id="2b306-131">Number of bike buyer cases</span></span>  
  
    -   <span data-ttu-id="2b306-132">Número de casos con valores que faltan para [Bike Buyer]</span><span class="sxs-lookup"><span data-stu-id="2b306-132">Number of cases with missing values for [Bike Buyer]</span></span>  
  
     <span data-ttu-id="2b306-133">También puede colocar el cursor sobre cualquier nodo del árbol para ver la condición necesaria para alcanzar ese nodo desde el nodo anterior.</span><span class="sxs-lookup"><span data-stu-id="2b306-133">Alternately, place your cursor over any node in the tree to see the condition that is required to reach that node from the node that comes before it.</span></span> <span data-ttu-id="2b306-134">También puede ver esta misma información en la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="2b306-134">You can also view this same information in the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="2b306-135">Haga clic en el nodo de **Age >= 34 y < 41**.</span><span class="sxs-lookup"><span data-stu-id="2b306-135">Click on the node for **Age >=34 and < 41**.</span></span> <span data-ttu-id="2b306-136">El histograma se muestra como una barra horizontal delgada a lo largo del nodo y representa la distribución de los clientes con este intervalo de edad que anteriormente compraron (rosa) o no compraron (azul) una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="2b306-136">The histogram is displayed as a thin horizontal bar across the node and represents the distribution of customers in this age range who previously did (pink) and did not (blue) purchase a bike.</span></span> <span data-ttu-id="2b306-137">El visor nos muestra que es probable que los clientes con edades comprendidas entre 34 y 40 años sin automóvil o con uno compren una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="2b306-137">The Viewer shows us that customers between the ages of 34 and 40 with one or no cars are likely to purchase a bike.</span></span> <span data-ttu-id="2b306-138">Si vamos un poco más lejos, vemos que la probabilidad de comprar una bicicleta aumenta si el cliente tiene una edad comprendida entre 38 y 40 años.</span><span class="sxs-lookup"><span data-stu-id="2b306-138">Taking it one step further, we find that the likelihood to purchase a bike increases if the customer is actually age 38 to 40.</span></span>  
  
 <span data-ttu-id="2b306-139">Como habilitó la obtención de detalles cuando creó la estructura y el modelo, puede recuperar información detallada de los casos del modelo y de la estructura de minería de datos, incluidas las columnas que no se incluyeron en el modelo de minería de datos (por ejemplo, emailAddress y FirstName).</span><span class="sxs-lookup"><span data-stu-id="2b306-139">Because you enabled drillthrough when you created the structure and model, you can retrieve detailed information from the model cases and mining structure, including those columns that were not included in the mining model (e.g., emailAddress, FirstName).</span></span>  
  
 <span data-ttu-id="2b306-140">Para obtener más información, vea [Consultas de obtención de detalles &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2b306-140">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-drill-through-to-case-data"></a><span data-ttu-id="2b306-141">Para obtener información detallada de los datos del caso</span><span class="sxs-lookup"><span data-stu-id="2b306-141">To drill through to case data</span></span>  
  
1.  <span data-ttu-id="2b306-142">Haga clic con el botón secundario en un nodo y seleccione obtener **detalles** y **solo columnas del modelo**.</span><span class="sxs-lookup"><span data-stu-id="2b306-142">Right-click a node, and select **Drill Through** then **Model Columns Only**.</span></span>  
  
     <span data-ttu-id="2b306-143">Los detalles de cada caso de entrenamiento se muestran en formato de hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="2b306-143">The details for each training case are displayed in spreadsheet format.</span></span> <span data-ttu-id="2b306-144">Estos detalles proceden de la vista vTargetMail que seleccionó como la tabla de casos al generar la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2b306-144">These details come from the vTargetMail view that you selected as the case table when building the mining structure.</span></span>  
  
2.  <span data-ttu-id="2b306-145">Haga clic con el botón secundario en un nodo y seleccione obtener **detalles** y, a continuación, **columnas de modelo y estructura**.</span><span class="sxs-lookup"><span data-stu-id="2b306-145">Right-click a node, and select **Drill Through** then **Model and Structure Columns**.</span></span>  
  
     <span data-ttu-id="2b306-146">Se muestra la misma hoja de cálculo con las columnas de estructura anexadas al final.</span><span class="sxs-lookup"><span data-stu-id="2b306-146">The same spreadsheet displays with the structure columns appended to the end.</span></span>  
  
  
###  <a name="dependency-network-tab"></a><a name="Dependency_Network_Tab"></a><span data-ttu-id="2b306-147">Pestaña red de dependencias</span><span class="sxs-lookup"><span data-stu-id="2b306-147">Dependency Network Tab</span></span>  
 <span data-ttu-id="2b306-148">La pestaña **red de dependencias** muestra las relaciones entre los atributos que contribuyen a la capacidad de predicción del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2b306-148">The **Dependency Network** tab displays the relationships between the attributes that contribute to the predictive ability of the mining model.</span></span> <span data-ttu-id="2b306-149">El visor Red de dependencias reafirma nuestra conclusión de que la edad y la región son factores importantes para predecir la compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="2b306-149">The Dependency Network viewer reinforces our findings that Age and Region are important factors in predicting bike buying.</span></span>  
  
##### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="2b306-150">Para explorar el modelo en la pestaña Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="2b306-150">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="2b306-151">Haga clic en el `Bike Buyer` nodo para identificar sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="2b306-151">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="2b306-152">El nodo central de la red de dependencias, `Bike Buyer` , representa el atributo de predicción del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2b306-152">The center node for the dependency network, `Bike Buyer`, represents the predictable attribute in the mining model.</span></span> <span data-ttu-id="2b306-153">En el gráfico se resaltan todos los nodos conectados que afectan al atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="2b306-153">The graph highlights any connected nodes that have an effect on the predictable attribute.</span></span>  
  
2.  <span data-ttu-id="2b306-154">Ajuste el control deslizante **todos los vínculos** para identificar el atributo más influyente.</span><span class="sxs-lookup"><span data-stu-id="2b306-154">Adjust the **All Links** slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="2b306-155">Al arrastrar hacia abajo el control deslizante, se quitan del gráfico los atributos que solo tienen un efecto débil en la columna [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="2b306-155">As you drag down the slider, attributes that have only a weak effect on the [Bike Buyer] column are removed from the graph.</span></span> <span data-ttu-id="2b306-156">Ajustando el control deslizante, descubrirá que la edad y la región son los factores más importantes para predecir si alguien va a comprar una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="2b306-156">By adjusting the slider, you can discover that Age and Region are the greatest factors in predicting whether someone is a bike buyer.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="2b306-157">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2b306-157">Related Tasks</span></span>  
 <span data-ttu-id="2b306-158">Vea estos temas para explorar los datos con las demás clases de modelos.</span><span class="sxs-lookup"><span data-stu-id="2b306-158">See these topics to explore the data using the other kinds of models.</span></span>  
  
-   [<span data-ttu-id="2b306-159">Explorar el modelo de agrupación en clústeres &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b306-159">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="2b306-160">Explorar el modelo Bayes Naive &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b306-160">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2b306-161">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="2b306-161">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2b306-162">Explorar el modelo de agrupación en clústeres &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b306-162">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b306-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b306-163">See Also</span></span>  
 <span data-ttu-id="2b306-164">[Tareas y procedimientos del visor de modelos de minería de datos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="2b306-164">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="2b306-165">[Pestaña árbol de decisión &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="2b306-165">[Decision Tree Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="2b306-166">[Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="2b306-166">[Dependency Network Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="2b306-167">Examinar un modelo usando el Visor de árboles de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b306-167">Browse a Model Using the Microsoft Tree Viewer</span></span>](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
  
