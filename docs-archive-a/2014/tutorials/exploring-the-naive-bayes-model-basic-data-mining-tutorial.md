---
title: Explorar el modelo Bayes Naive (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b06708d5-4477-4a51-bf8d-0b1e3c1f9ebb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a26fa972e1ed50e2f4107026210a5935fcb86d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747316"
---
# <a name="exploring-the-naive-bayes-model-basic-data-mining-tutorial"></a><span data-ttu-id="3693e-102">Explorar el modelo Bayes naive (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="3693e-102">Exploring the Naive Bayes Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="3693e-103">El [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Bayes Naive de proporciona varios métodos para mostrar la interacción entre la compra de bicicletas y los atributos de entrada.</span><span class="sxs-lookup"><span data-stu-id="3693e-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm provides several methods for displaying the interaction between bike buying and the input attributes.</span></span>  
  
 <span data-ttu-id="3693e-104">El [!INCLUDE[msCoName](../includes/msconame-md.md)] visor Bayes Naive de proporciona las siguientes pestañas para la exploración de modelos de minería de datos Bayes Naive:</span><span class="sxs-lookup"><span data-stu-id="3693e-104">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for use in exploring Naive Bayes mining models:</span></span>  
  
 
  
##  <a name="dependency-network"></a><a name="DependencyNetwork"></a><span data-ttu-id="3693e-105">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="3693e-105">Dependency Network</span></span>  
 <span data-ttu-id="3693e-106">La pestaña **red de dependencias** funciona de la misma forma que la pestaña **red de dependencias** del [!INCLUDE[msCoName](../includes/msconame-md.md)] visor de árboles.</span><span class="sxs-lookup"><span data-stu-id="3693e-106">The **Dependency Network** tab works in the same way as the **Dependency Network** tab for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer.</span></span> <span data-ttu-id="3693e-107">Cada nodo del visor representa un atributo y las líneas entre los nodos representan relaciones.</span><span class="sxs-lookup"><span data-stu-id="3693e-107">Each node in the viewer represents an attribute, and the lines between nodes represent relationships.</span></span> <span data-ttu-id="3693e-108">En el visor, puede ver todos los atributos que afectan al estado del atributo de predicción, Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="3693e-108">In the viewer, you can see all the attributes that affect the state of the predictable attribute, Bike Buyer.</span></span>  
  
#### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="3693e-109">Para explorar el modelo en la pestaña Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="3693e-109">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="3693e-110">Utilice la lista **modelo de minería de datos** en la parte superior de la pestaña visor de modelos de minería de **datos** para cambiar al `TM_NaiveBayes` modelo.</span><span class="sxs-lookup"><span data-stu-id="3693e-110">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_NaiveBayes` model.</span></span>  
  
2.  <span data-ttu-id="3693e-111">Use la lista de **visores** para cambiar al **visor Bayes Naive de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3693e-111">Use the **Viewer** list to switch to **Microsoft Naive Bayes Viewer**.</span></span>  
  
3.  <span data-ttu-id="3693e-112">Haga clic en el `Bike Buyer` nodo para identificar sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="3693e-112">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="3693e-113">El sombreado rosa indica que todos los atributos influyen en la compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="3693e-113">The pink shading indicates that all of the attributes have an effect on bike buying.</span></span>  
  
4.  <span data-ttu-id="3693e-114">Ajuste el control deslizante para identificar el atributo más influyente.</span><span class="sxs-lookup"><span data-stu-id="3693e-114">Adjust the slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="3693e-115">Conforme baja el control deslizante, solamente permanecen los atributos que afectan en mayor medida a la columna [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="3693e-115">As you lower the slider, only the attributes that have the greatest effect on the [Bike Buyer] column remain.</span></span> <span data-ttu-id="3693e-116">Ajustando el control deslizante, puede detectar que algunos de los atributos más influyentes son el número de automóviles que se posee, la distancia al lugar de trabajo y el número total de hijos.</span><span class="sxs-lookup"><span data-stu-id="3693e-116">By adjusting the slider, you can discover that a few of the most influential attributes are: number of cars owned, commute distance, and total number of children.</span></span>  
 
  
##  <a name="attribute-profiles"></a><a name="AttributeProfiles"></a><span data-ttu-id="3693e-117">Perfiles de atributo</span><span class="sxs-lookup"><span data-stu-id="3693e-117">Attribute Profiles</span></span>  
 <span data-ttu-id="3693e-118">La pestaña **perfiles de atributo** describe el modo en que los distintos Estados de los atributos de entrada afectan al resultado del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="3693e-118">The **Attribute Profiles** tab describes how different states of the input attributes affect the outcome of the predictable attribute.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-profiles-tab"></a><span data-ttu-id="3693e-119">Para explorar el modelo en la pestaña Perfiles del atributo</span><span class="sxs-lookup"><span data-stu-id="3693e-119">To explore the model in the Attribute Profiles tab</span></span>  
  
1.  <span data-ttu-id="3693e-120">En el cuadro **predicción** , compruebe que `Bike Buyer` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3693e-120">In the **Predictable** box, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="3693e-121">Si la **leyenda de minería de datos** está bloqueando la presentación de los **perfiles de atributo**, muévalo fuera del camino.</span><span class="sxs-lookup"><span data-stu-id="3693e-121">If the **Mining Legend** is blocking display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="3693e-122">En el cuadro barras de **histograma** , seleccione **5**.</span><span class="sxs-lookup"><span data-stu-id="3693e-122">In the **Histogram** bars box, select **5**.</span></span>  
  
     <span data-ttu-id="3693e-123">En nuestro modelo, 5 es el número máximo de estados para cualquier variable.</span><span class="sxs-lookup"><span data-stu-id="3693e-123">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
     <span data-ttu-id="3693e-124">Los atributos que afectan al estado de este atributo de predicción aparecen enumerados junto a los valores de cada estado de los atributos de entrada y sus distribuciones en cada estado del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="3693e-124">The attributes that affect the state of this predictable attribute are listed together with the values of each state of the input attributes and their distributions in each state of the predictable attribute.</span></span>  
  
4.  <span data-ttu-id="3693e-125">En la columna **atributos** , busque **número de automóviles propiedad**.</span><span class="sxs-lookup"><span data-stu-id="3693e-125">In the **Attributes** column, find **Number Cars Owned**.</span></span>  <span data-ttu-id="3693e-126">Observe las diferencias en los histogramas de los compradores de bicicletas (la columna con la etiqueta 1) y los no compradores (la columna con la etiqueta 0).</span><span class="sxs-lookup"><span data-stu-id="3693e-126">Notice the differences in the histograms for bike buyers (column labeled 1) and non-buyers (column labeled 0).</span></span> <span data-ttu-id="3693e-127">Una persona que no tenga automóvil o que tenga uno tiene mucha más probabilidad de comprar una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="3693e-127">A person with zero or one car is much more likely to buy a bike.</span></span>  
  
5.  <span data-ttu-id="3693e-128">Haga doble clic en la celda **Number Cars propiedad** de la columna Bike Buyer (columna con la etiqueta 1).</span><span class="sxs-lookup"><span data-stu-id="3693e-128">Double-click the **Number Cars Owned** cell in the bike buyer (column labeled 1) column.</span></span>  
  
     <span data-ttu-id="3693e-129">La **leyenda de minería de datos** muestra una vista más detallada.</span><span class="sxs-lookup"><span data-stu-id="3693e-129">The **Mining Legend** displays a more detailed view.</span></span>  
  
  
##  <a name="attribute-characteristics"></a><a name="AttributeCharacteristics"></a><span data-ttu-id="3693e-130">Características del atributo</span><span class="sxs-lookup"><span data-stu-id="3693e-130">Attribute Characteristics</span></span>  
 <span data-ttu-id="3693e-131">Con la pestaña **características del atributo** , puede seleccionar un atributo y un valor para ver la frecuencia con que aparecen los valores de otros atributos en los casos de valor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3693e-131">With the **Attribute Characteristics** tab, you can select an attribute and value to see how frequently values for other attributes appear in the selected value cases.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-characteristics-tab"></a><span data-ttu-id="3693e-132">Para explorar el modelo en la pestaña Características del atributo</span><span class="sxs-lookup"><span data-stu-id="3693e-132">To explore the model in the Attribute Characteristics tab</span></span>  
  
1.  <span data-ttu-id="3693e-133">En la lista de **atributos** , compruebe que `Bike Buyer` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3693e-133">In the **Attribute** list, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="3693e-134">Establezca el **valor** en **1**.</span><span class="sxs-lookup"><span data-stu-id="3693e-134">Set the **Value** to **1**.</span></span>  
  
     <span data-ttu-id="3693e-135">En el visor, verá que los clientes que no tienen ningún hijo conviviendo con ellos, una distancia corta al trabajo y que viven en la región de Norteamérica tienen más probabilidad de comprar una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="3693e-135">In the viewer, you will see that customers who have no children at home, short commutes, and live in the North America region are more likely to buy a bike.</span></span>  
  
  
##  <a name="attribute-discrimination"></a><a name="AttributeDiscrimination"></a><span data-ttu-id="3693e-136">Distinción de atributos</span><span class="sxs-lookup"><span data-stu-id="3693e-136">Attribute Discrimination</span></span>  
 <span data-ttu-id="3693e-137">Con la pestaña **distinción de atributo** , puede investigar la relación entre dos valores discretos de compra de bicicletas y otros valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="3693e-137">With the **Attribute Discrimination** tab, you can investigate the relationship between two discrete values of bike buying and other attribute values.</span></span> <span data-ttu-id="3693e-138">Dado `TM_NaiveBayes` que el modelo solo tiene dos Estados: 1 y 0, no es necesario realizar ningún cambio en el visor.</span><span class="sxs-lookup"><span data-stu-id="3693e-138">Because the `TM_NaiveBayes` model has only two states, 1 and 0, you do not have to make any changes to the viewer.</span></span>  
  
 <span data-ttu-id="3693e-139">En el visor, podrá ver que las personas que no tienen un automóvil tienden a comprar bicicletas y las personas que tienen dos no suelen comprarlas.</span><span class="sxs-lookup"><span data-stu-id="3693e-139">In the viewer, you can see that people who do not own cars tend to buy bicycles, and people who own two cars tend not to buy bicycles.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3693e-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3693e-140">Related Tasks</span></span>  
 <span data-ttu-id="3693e-141">Vea los temas siguientes para explorar los demás modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="3693e-141">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="3693e-142">Explorar el modelo de árbol de decisión &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3693e-142">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="3693e-143">Explorar el modelo de agrupación en clústeres &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3693e-143">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="3693e-144">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="3693e-144">Next Lesson</span></span>  
 [<span data-ttu-id="3693e-145">Lección 5: probar los modelos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3693e-145">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="3693e-146">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="3693e-146">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="3693e-147">Explorar el modelo de agrupación en clústeres &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3693e-147">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="3693e-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3693e-148">See Also</span></span>  
 <span data-ttu-id="3693e-149">[Examinar un modelo usando el visor Bayes Naive de Microsoft](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="3693e-149">[Browse a Model Using the Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span></span>  
 <span data-ttu-id="3693e-150">[Pestaña distinción de atributos &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="3693e-150">[Attribute Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="3693e-151">[Pestaña perfiles de atributo &#40;el visor de modelos de minería de datos&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="3693e-151">[Attribute Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="3693e-152">[Pestaña características del atributo &#40;visor de modelos de minería de datos&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="3693e-152">[Attribute Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="3693e-153">Pestaña red de dependencias &#40;visor de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3693e-153">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)  
  
  
