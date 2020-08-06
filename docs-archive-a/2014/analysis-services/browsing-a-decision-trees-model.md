---
title: Examinar un modelo de árboles de decisión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- tree viewer
- mining model, decision tree
- decision tree [data mining]
- dependency network
ms.assetid: 6b3dd1ae-caff-41c3-817b-802dc020ff88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 809d2e494cfa7a6c4078acf95c2c70a0e68c188d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670111"
---
# <a name="browsing-a-decision-trees-model"></a><span data-ttu-id="d3b02-102">Examinar un modelo de árboles de decisión</span><span class="sxs-lookup"><span data-stu-id="d3b02-102">Browsing a Decision Trees Model</span></span>
  <span data-ttu-id="d3b02-103">Al abrir un modelo de clasificación con **examinar**, el modelo se muestra en un visor de árbol de decisión interactivo, similar al [!INCLUDE[msCoName](../includes/msconame-md.md)] visor de árboles de decisión de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3b02-103">When you open a classification model using **Browse**, the model is displayed in an interactive decision tree viewer, similar to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d3b02-104">El visor muestra los resultados de clasificación en forma de gráfico, que se ha diseñado para resaltar los criterios que distinguen un grupo de datos de otro.</span><span class="sxs-lookup"><span data-stu-id="d3b02-104">The viewer displays the results of classification as a graph that is designed to highlight the criteria that differentiate one group of data from another.</span></span> <span data-ttu-id="d3b02-105">También puede explorar en profundidad los subconjuntos individuales del árbol y recuperar los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="d3b02-105">You can also drill down into individual subsets of the tree and retrieve the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="d3b02-106">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="d3b02-106">Explore the Model</span></span>  
 <span data-ttu-id="d3b02-107">Los modelos basados en el algoritmo de árboles de decisión tienen gran cantidad de información interesante que se puede explorar.</span><span class="sxs-lookup"><span data-stu-id="d3b02-107">Models based on the Decision Trees algorithm have lots of interesting information to explore.</span></span> <span data-ttu-id="d3b02-108">La ventana **examinar** incluye las pestañas y los paneles siguientes para ayudarle a conocer los patrones y predecir los resultados con el gráfico:</span><span class="sxs-lookup"><span data-stu-id="d3b02-108">The **Browse** window includes the following tabs and panes to help you learn the patterns and predict outcomes using the graph:</span></span>  
  
-   [<span data-ttu-id="d3b02-109">Árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="d3b02-109">Decision Tree</span></span>](#BKMK_DecisionTree)  
  
-   [<span data-ttu-id="d3b02-110">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="d3b02-110">Dependency Network</span></span>](#BKMK_DNetwork)  
  
 <span data-ttu-id="d3b02-111">Para experimentar con árboles de decisión, puede utilizar los datos de ejemplo en la pestaña Datos de aprendizaje (o Datos de origen) del libro de datos de ejemplo y generar un modelo de árbol de decisión con Bike Buyer como atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="d3b02-111">To experiment with a decision trees model, you can use the sample data on the Training Data (or Source Data) tab of the sample data workbook, and build a decision tree model using Bike Buyer as the predictable attribute.</span></span>  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a><span data-ttu-id="d3b02-112">Árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="d3b02-112">Decision Tree</span></span>  
 <span data-ttu-id="d3b02-113">Esta vista se ha diseñado para ayudarle a conocer y explorar los factores que generan resultados.</span><span class="sxs-lookup"><span data-stu-id="d3b02-113">This view is intended to help you understand and explore the factors that lead to an outcome.</span></span>  
  
 <span data-ttu-id="d3b02-114">El gráfico de árboles de decisión se puede leer de izquierda a derecha como sigue:</span><span class="sxs-lookup"><span data-stu-id="d3b02-114">The decision tree graph can be read from left to right as follows:</span></span>  
  
-   <span data-ttu-id="d3b02-115">Los rectángulos, que se conocen como *nodos*, contienen subconjuntos de los datos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-115">The rectangles, which are referred to as *nodes*, contain subsets of the data.</span></span> <span data-ttu-id="d3b02-116">La etiqueta del nodo indica las características de definición de ese subconjunto.</span><span class="sxs-lookup"><span data-stu-id="d3b02-116">The label on the node tells you the defining characteristics of that subset.</span></span>  
  
-   <span data-ttu-id="d3b02-117">El nodo situado más a la izquierda, con la etiqueta **todo**, representa el conjunto de datos completo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-117">The leftmost node, labeled **All**, represents the complete data set.</span></span> <span data-ttu-id="d3b02-118">Todos los nodos siguientes representan subconjuntos de los datos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-118">All subsequent nodes represent subsets of the data.</span></span>  
  
-   <span data-ttu-id="d3b02-119">Un árbol de decisión contiene muchas *divisiones*o lugares en los que los datos difieren en varios conjuntos basados en atributos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-119">A decision tree contains many *splits*, or places where the data diverges into multiple sets based on attributes.</span></span>  
  
     <span data-ttu-id="d3b02-120">Por ejemplo, la primera división en el modelo de ejemplo divide el conjunto de datos en tres grupos de edad.</span><span class="sxs-lookup"><span data-stu-id="d3b02-120">For example, the first split in the sample model divides the dataset into three groups by age.</span></span>  
  
-   <span data-ttu-id="d3b02-121">La división inmediatamente después del nodo **todos** es la más importante porque muestra la condición primaria que divide este conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="d3b02-121">The split immediately after the **All** node is most important because it shows the primary condition that divides this dataset.</span></span>  
  
     <span data-ttu-id="d3b02-122">Las divisiones adicionales se muestran a la derecha.</span><span class="sxs-lookup"><span data-stu-id="d3b02-122">Additional splits occur to the right.</span></span> <span data-ttu-id="d3b02-123">Por tanto, cuando se analizan diferentes segmentos del árbol, podrá saber qué atributos tuvieron mayor influencia en el comportamiento de compra.</span><span class="sxs-lookup"><span data-stu-id="d3b02-123">Thus, by analyzing different segments of the tree, you can learn which attributes had the most influence on purchasing behavior.</span></span>  
  
 <span data-ttu-id="d3b02-124">![Gráfico de redes de dependencias para un modelo de asociación](media/dm13-dec-tree-split-definition.gif "Gráfico de redes de dependencias para un modelo de asociación")</span><span class="sxs-lookup"><span data-stu-id="d3b02-124">![Dependency network graph for an association model](media/dm13-dec-tree-split-definition.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="d3b02-125">Con esta información, puede dirigir una campaña de marketing hacia aquellos clientes que puedan necesitar simplemente el estímulo para realizar una compra.</span><span class="sxs-lookup"><span data-stu-id="d3b02-125">Using this information, you might focus a marketing campaign on customers that might simply need encouragement to make a purchase.</span></span>  
  
##### <a name="explore-the-decision-tree"></a><span data-ttu-id="d3b02-126">Explorar el árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="d3b02-126">Explore the decision tree</span></span>  
  
1.  <span data-ttu-id="d3b02-127">Haga clic en el nodo **todos** y examine la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="d3b02-127">Click the **All** node, and look at the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="d3b02-128">Muestra el recuento exacto de casos en el conjunto de datos de aprendizaje, así como un análisis desglosado de los resultados.</span><span class="sxs-lookup"><span data-stu-id="d3b02-128">It displays the exact count of cases in the training data set, as well as a breakdown of the outcomes.</span></span>  
  
     <span data-ttu-id="d3b02-129">Puede ver los mismos detalles en la información sobre herramientas si sitúa el mouse sobre un nodo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-129">You can view the same information in a tooltip if you pause the mouse over a node.</span></span>  
  
2.  <span data-ttu-id="d3b02-130">Haga clic en los signo más y menos junto a cada nodo para expandir o contraer del árbol.</span><span class="sxs-lookup"><span data-stu-id="d3b02-130">Click the plus and minus signs next to each node to expand or collapse the tree.</span></span>  
  
     <span data-ttu-id="d3b02-131">También puede usar el control deslizante **Mostrar nivel** para expandir o reducir el árbol.</span><span class="sxs-lookup"><span data-stu-id="d3b02-131">You can also use the **Show Level** slider to expand or shrink the tree.</span></span>  
  
3.  <span data-ttu-id="d3b02-132">Se habrá dado cuenta de que algunos nodos son más oscuros que otros.</span><span class="sxs-lookup"><span data-stu-id="d3b02-132">Notice that some nodes are darker than others?</span></span>  
  
     <span data-ttu-id="d3b02-133">De forma predeterminada, el **rellenado** se usa como variable de sombreado, lo que significa que la intensidad del color muestra qué nodos tienen la mayor compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d3b02-133">By default, **Population** is used as the shading variable, which means that the intensity of the color shows you which nodes have the most support.</span></span>  
  
     <span data-ttu-id="d3b02-134">Por consiguiente el nodo en el extremo izquierdo es el más oscuro porque contiene el conjunto de datos completo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-134">Therefore the leftmost node is darkest, because it contains the entire dataset.</span></span>  
  
4.  <span data-ttu-id="d3b02-135">Cambie el valor de **fondo** de **todos los casos** a **sí**.</span><span class="sxs-lookup"><span data-stu-id="d3b02-135">Change the value for **Background** from **All Cases** to **Yes**.</span></span>  
  
     <span data-ttu-id="d3b02-136">![cambiar el gráfico de árboles de decisión para resaltar los compradores](media/dm13-dectreeshadedbuyer.gif "cambiar el gráfico de árboles de decisión para resaltar los compradores")</span><span class="sxs-lookup"><span data-stu-id="d3b02-136">![changing decision tree graph to highlight buyers](media/dm13-dectreeshadedbuyer.gif "changing decision tree graph to highlight buyers")</span></span>  
  
5.  <span data-ttu-id="d3b02-137">Ahora la intensidad de color indica cuántos clientes en cada nodo compraron una bicicleta, que es el comportamiento que le interesa.</span><span class="sxs-lookup"><span data-stu-id="d3b02-137">Now the intensity of the color tells you how many customers in each node purchased a bike, which is the behavior you are interested in.</span></span>  
  
     <span data-ttu-id="d3b02-138">Observe las barras coloreadas en cada nodo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-138">Notice the colored bars within each node.</span></span> <span data-ttu-id="d3b02-139">Es un histograma que muestra la distribución de los resultados en este subconjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-139">This is a histogram that shows the distribution of outcomes within this subset of data.</span></span> <span data-ttu-id="d3b02-140">Por ejemplo, en el árbol de decisión Bike Buyer de ejemplo, la barra coloreada muestra la proporción de clientes que compraron bicicletas (sí valores) frente a aquellos que no lo hicieron (ningún valor).</span><span class="sxs-lookup"><span data-stu-id="d3b02-140">For example, in the sample Bike Buyer decision tree, the colored bar shows the proportion of customers who bought bikes (Yes values) vs. those who did not (No values).</span></span> <span data-ttu-id="d3b02-141">Para obtener los valores exactos, puede hacer clic en el nodo y ver la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="d3b02-141">To get the exact values, you can click the node and view the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="d3b02-142">Si observa el gráfico, podrá ver cómo cada subconjunto de datos se va descomponiendo en grupos más pequeños y los atributos que se usan con mayor frecuencia en la predicción de resultados.</span><span class="sxs-lookup"><span data-stu-id="d3b02-142">By following the graph, you can see how each subset of data is further decomposed into smaller groups, and which attributes are most useful in predicting an outcome.</span></span>  
  
     <span data-ttu-id="d3b02-143">Basta con ver la intensidad del sombreado para centrarse en los grupos que le interesan y obtener información más detallada para compararlos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-143">Just by looking at the intensity of the shading, you can focus on a couple groups of interest, and get more detailed data on them for comparison.</span></span> <span data-ttu-id="d3b02-144">Por ejemplo, estos grupos muestran bastantes posibilidades de comprar bicicletas:</span><span class="sxs-lookup"><span data-stu-id="d3b02-144">For example, these groups have a fairly high probability of buying bikes:</span></span>  
  
    -   <span data-ttu-id="d3b02-145">Age >= 32 y \< 53 and Yearly Income > = 26000 y secundarios = 0</span><span class="sxs-lookup"><span data-stu-id="d3b02-145">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children = 0</span></span>  
  
         <span data-ttu-id="d3b02-146">Total de casos: 1150</span><span class="sxs-lookup"><span data-stu-id="d3b02-146">Total cases: 1150</span></span>  
  
         <span data-ttu-id="d3b02-147">Probabilidad de comprador de bicicletas: 18%</span><span class="sxs-lookup"><span data-stu-id="d3b02-147">Bike buyer probability: 18%</span></span>  
  
    -   <span data-ttu-id="d3b02-148">Age >= 32 y \< 53 and Yearly Income > = 26000 y secundarios no = 0 y estado civil = ' single '</span><span class="sxs-lookup"><span data-stu-id="d3b02-148">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children not = 0 and Marital Status = 'Single'</span></span>  
  
         <span data-ttu-id="d3b02-149">Total de casos: 402</span><span class="sxs-lookup"><span data-stu-id="d3b02-149">Total cases: 402</span></span>  
  
         <span data-ttu-id="d3b02-150">Probabilidad de ser comprador de bicicletas: 16 %</span><span class="sxs-lookup"><span data-stu-id="d3b02-150">Bike buyer probability: 16%</span></span>  
  
7.  <span data-ttu-id="d3b02-151">Cambie el valor de **background** de **sí** a **no** y vea cómo cambia el gráfico.</span><span class="sxs-lookup"><span data-stu-id="d3b02-151">Change the value for **Background** from **Yes** to **No** and see how the graph changes.</span></span>  
  
     <span data-ttu-id="d3b02-152">![Gráfico de redes de dependencias para un modelo de asociación](media/dm13-dec-tree-background-no.gif "Gráfico de redes de dependencias para un modelo de asociación")</span><span class="sxs-lookup"><span data-stu-id="d3b02-152">![Dependency network graph for an association model](media/dm13-dec-tree-background-no.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="d3b02-153">**Sugerencias**</span><span class="sxs-lookup"><span data-stu-id="d3b02-153">**Tips**</span></span>  
  
-   <span data-ttu-id="d3b02-154">Si los datos se pueden dividir en varias series, se crea otro modelo para cada conjunto de datos que desee modelar.</span><span class="sxs-lookup"><span data-stu-id="d3b02-154">If your data can be divided into multiple series, a different model is built for each set of data that you want to model.</span></span>  
  
-   <span data-ttu-id="d3b02-155">En el modelo de datos de ejemplo, solo hay un resultado predecible, Bike Buyer, pero Supongamos que tiene información sobre si el cliente ha adquirido un plan de servicio y desea predecirlo también.</span><span class="sxs-lookup"><span data-stu-id="d3b02-155">In the sample data model, there is only one predictable outcome - Bike Buyer - but suppose you had information about whether the customer purchased a service plan and wanted to predict that as well.</span></span> <span data-ttu-id="d3b02-156">En ese caso tendría esos datos en una columna independiente e incluiría dos atributos de predicción en el modelo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-156">In that case you would have that data in a separate column, and include two predictable attributes in the model.</span></span>  
  
     <span data-ttu-id="d3b02-157">Haga clic en la opción **histograma** , en la esquina superior izquierda del panel del árbol de decisión, para cambiar el número máximo de Estados que pueden aparecer en los histogramas del árbol.</span><span class="sxs-lookup"><span data-stu-id="d3b02-157">Click the **Histogram** option, in the upper left corner of the Decision Tree pane, to change the maximum number of states that can appear in the histograms in the tree.</span></span> <span data-ttu-id="d3b02-158">Esto resulta útil si el atributo de predicción tiene muchos estados.</span><span class="sxs-lookup"><span data-stu-id="d3b02-158">This is useful if the predictable attribute has many states.</span></span> <span data-ttu-id="d3b02-159">Los estados aparecen en una histograma en orden de popularidad de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="d3b02-159">The states appear in a histogram in order of popularity from left to right.</span></span>  
  
-   <span data-ttu-id="d3b02-160">También puede usar las opciones de la pestaña **árbol de decisión** para influir en el modo en que se muestra el árbol, al acercar o alejar, o al ajustar el tamaño del gráfico para que se ajuste a la ventana.</span><span class="sxs-lookup"><span data-stu-id="d3b02-160">You can also use the options on the **Decision Tree** tab to affect how the tree is displayed, by zooming in or out, or sizing the graph to fit the window.</span></span>  
  
-   <span data-ttu-id="d3b02-161">Use **Expansión predeterminada** para configurar el número predeterminado de niveles que van a aparecer en todos los árboles del modelo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-161">Use **Default Expansion** to set the default number of levels that are displayed for all trees in the model.</span></span>  
  
-   <span data-ttu-id="d3b02-162">Seleccione **Mostrar nombre largo** para mostrar el nombre completo del atributo, incluido el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-162">Select **Show long name** to display the full name of the attribute, including the data source.</span></span> <span data-ttu-id="d3b02-163">Los nombres cortos y largos son los mismos, a menos que los casos se hayan obtenido de un origen de datos distinto al de los atributos de cada caso.</span><span class="sxs-lookup"><span data-stu-id="d3b02-163">Short names and long names are the same unless your cases are obtained from a different data source than the attributes for each case.</span></span>  
  
 [<span data-ttu-id="d3b02-164">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="d3b02-164">Back To Top</span></span>](#bkmk_Top)  
  
###  <a name="dependency-network"></a><a name="BKMK_DNetwork"></a><span data-ttu-id="d3b02-165">Red de dependencias</span><span class="sxs-lookup"><span data-stu-id="d3b02-165">Dependency Network</span></span>  
 <span data-ttu-id="d3b02-166">La vista **red de dependencias** muestra las conexiones entre los atributos de entrada y los atributos de predicción del modelo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-166">The **Dependency Network** view displays the connections between the input attributes and the predictable attributes in the model.</span></span>  
  
1.  <span data-ttu-id="d3b02-167">Haga clic en el control deslizante y arrástrelo a la izquierda del visor</span><span class="sxs-lookup"><span data-stu-id="d3b02-167">Click and drag the slider at the left of the viewer</span></span>  
  
     <span data-ttu-id="d3b02-168">En la parte superior, se muestran todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="d3b02-168">At the top position, all connections are shown.</span></span> <span data-ttu-id="d3b02-169">Cuando desplace el control deslizante hacia abajo, solamente se muestran en el visor los vínculos de mayor importancia.</span><span class="sxs-lookup"><span data-stu-id="d3b02-169">When you drag the slider down, only the strongest links are shown in the viewer.</span></span>  
  
2.  <span data-ttu-id="d3b02-170">Ahora haga clic en el nodo Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="d3b02-170">Now click the Bike Buyer node.</span></span>  
  
     <span data-ttu-id="d3b02-171">![Vista de red de dependencia de árboles de decisión](media/dm13-dectree-depnet.gif "Vista de red de dependencia de árboles de decisión")</span><span class="sxs-lookup"><span data-stu-id="d3b02-171">![Dependency network view for decision trees](media/dm13-dectree-depnet.gif "Dependency network view for decision trees")</span></span>  
  
     <span data-ttu-id="d3b02-172">Cuando se selecciona un nodo, el visor resalta las dependencias específicas de dicho nodo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-172">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="d3b02-173">En este caso, el visor resalta cada nodo que le ayude a predecir el resultado.</span><span class="sxs-lookup"><span data-stu-id="d3b02-173">In this case, the viewer highlights each node that helps predict the outcome.</span></span>  
  
3.  <span data-ttu-id="d3b02-174">Si el visor contiene muchos nodos, puede buscar nodos específicos mediante el botón **Buscar nodo** .</span><span class="sxs-lookup"><span data-stu-id="d3b02-174">If the viewer contains many nodes, you can search for specific nodes by using the **Find Node** button.</span></span> <span data-ttu-id="d3b02-175">Al hacer clic en **Buscar nodo** se abre el cuadro de diálogo **Buscar nodo** , en el que puede utilizar un filtro para buscar y seleccionar nodos específicos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-175">Clicking **Find Node** opens the **Find Node** dialog box, in which you can use a filter to search for and select specific nodes.</span></span>  
  
4.  <span data-ttu-id="d3b02-176">La leyenda de la parte inferior del visor vincula códigos de color con el tipo de dependencia en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="d3b02-176">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="d3b02-177">Por ejemplo, cuando selecciona un nodo de predicción, este nodo se sombrea en color turquesa y los nodos que predicen el nodo seleccionado aparecen sombreados en color naranja.</span><span class="sxs-lookup"><span data-stu-id="d3b02-177">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="d3b02-178">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="d3b02-178">Back To Top</span></span>](#bkmk_Top)  
  
### <a name="drill-through-to-underlying-data"></a><span data-ttu-id="d3b02-179">Obtener información detallada en datos subyacentes</span><span class="sxs-lookup"><span data-stu-id="d3b02-179">Drill through to Underlying Data</span></span>  
 <span data-ttu-id="d3b02-180">Varios tipos de modelos admiten la capacidad de obtener *detalles* del modelo en los datos de casos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="d3b02-180">Several types of models support the ability to *drill through* from the model to the underlying case data.</span></span> <span data-ttu-id="d3b02-181">Esto puede resultar muy útil para ponerse en contacto con los clientes de un sector determinado o para obtener los datos necesarios para realizar un análisis más profundo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-181">This can be very useful if you want to contact customers in a particular segment or pull out the data to perform further analysis.</span></span>  
  
##### <a name="get-case-data"></a><span data-ttu-id="d3b02-182">Obtener datos de un caso</span><span class="sxs-lookup"><span data-stu-id="d3b02-182">Get case data</span></span>  
  
1.  <span data-ttu-id="d3b02-183">Haga clic con el botón secundario del mouse en el nodo del árbol que contiene los datos deseados y seleccione una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="d3b02-183">Right-click the node in the tree that contains the desired data and select one of these options:</span></span>  
  
    -   <span data-ttu-id="d3b02-184">**Obtención de detalles del modelo**.</span><span class="sxs-lookup"><span data-stu-id="d3b02-184">**Drill Through Model**.</span></span> <span data-ttu-id="d3b02-185">Esta opción obtiene los casos que pertenecen al nodo seleccionado y los guarda en una tabla de Excel.</span><span class="sxs-lookup"><span data-stu-id="d3b02-185">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="d3b02-186">Obtendrá solamente las columnas de los datos que se usaron realmente en la generación del modelo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-186">You get back only the columns of data that were actually used in building the model.</span></span>  
  
    -   <span data-ttu-id="d3b02-187">Obtener **detalles de las columnas**de la estructura.</span><span class="sxs-lookup"><span data-stu-id="d3b02-187">**Drill Through Structure Columns**.</span></span> <span data-ttu-id="d3b02-188">Esta opción obtiene los casos que pertenecen al nodo seleccionado y los guarda en una tabla de Excel.</span><span class="sxs-lookup"><span data-stu-id="d3b02-188">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="d3b02-189">Obtiene toda la información que estaba disponible en los datos subyacentes cuando se compiló, incluso una columna no se utilizó en el modelo.</span><span class="sxs-lookup"><span data-stu-id="d3b02-189">You get all information that was available in the underlying data when you built it, even of a column wasn't used in the model.</span></span> <span data-ttu-id="d3b02-190">Por ejemplo, puede haber excluido la dirección del cliente y código postal porque esos campos no resultan útiles con el análisis, pero los ha dejado en la estructura.</span><span class="sxs-lookup"><span data-stu-id="d3b02-190">For example, you might have excluded the customer address and zip code because those fields are not useful with analysis, but left them in the structure.</span></span>  
  
     <span data-ttu-id="d3b02-191">Vuelva a Excel para ver los datos.</span><span class="sxs-lookup"><span data-stu-id="d3b02-191">Return to Excel to view your data.</span></span> <span data-ttu-id="d3b02-192">El visor Examinar ejecuta una consulta, guarda los datos en una hoja de cálculo nueva y etiqueta los resultados.</span><span class="sxs-lookup"><span data-stu-id="d3b02-192">The Browse viewer runs a query, saves the data to a table in a new worksheet, and labels the results.</span></span>  
  
     <span data-ttu-id="d3b02-193">![los resultados de la obtención de detalles se guardan en Excel](media/dm13-dectree-drillthroughresults.gif "los resultados de la obtención de detalles se guardan en Excel")</span><span class="sxs-lookup"><span data-stu-id="d3b02-193">![results of drillthrough are saved to Excel](media/dm13-dectree-drillthroughresults.gif "results of drillthrough are saved to Excel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b02-194">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3b02-194">See Also</span></span>  
 [<span data-ttu-id="d3b02-195">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b02-195">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
