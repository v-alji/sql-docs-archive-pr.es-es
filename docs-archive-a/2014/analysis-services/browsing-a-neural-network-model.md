---
title: Examinar un modelo de red neuronal | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- mining model, neural network
- neural networks
- dependency network
ms.assetid: e4224cb7-115b-4889-ac07-03f096fb55fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab2673d5b1881f74c2bc146b084d2efc7b06d69b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670100"
---
# <a name="browsing-a-neural-network-model"></a><span data-ttu-id="50005-102">Examinar un modelo de red neuronal</span><span class="sxs-lookup"><span data-stu-id="50005-102">Browsing a Neural Network Model</span></span>
  <span data-ttu-id="50005-103">Cuando abre un modelo de red neuronal o de regresión lógica a través de **Examinar**, el modelo se muestra en un visor interactivo, similar al visor de modelos de red neuronal en [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50005-103">When you open a neural network or logistic regression model using **Browse**, the model is displayed in an interactive viewer, similar to the neural network model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="50005-104">El visor sirve para explorar correlaciones y obtener información sobre los patrones del modelo y los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="50005-104">The viewer helps you explore correlations, and get information about the patterns in the model and the underlying data.</span></span>

##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="50005-105">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="50005-105">Explore the Model</span></span>
 <span data-ttu-id="50005-106">Los modelos que se basan en algoritmos de red neuronal o de regresión lógica de [!INCLUDE[msCoName](../includes/msconame-md.md)] se parecen en que analizan los datos como un conjunto de conexiones entre las entradas y salidas conocidas.</span><span class="sxs-lookup"><span data-stu-id="50005-106">Models that are based on [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network or Logistic Regression algorithms are similar in that they analyze data as a set of connections among known inputs and outputs.</span></span> <span data-ttu-id="50005-107">El visor **Examinar** ayuda a explorar esas conexiones mediante los controles siguientes:</span><span class="sxs-lookup"><span data-stu-id="50005-107">The **Browse** viewer helps you to explore those connections, using the following controls:</span></span>

-   [<span data-ttu-id="50005-108">Variables</span><span class="sxs-lookup"><span data-stu-id="50005-108">Variables</span></span>](#BKMK_Variables)

-   [<span data-ttu-id="50005-109">Entradas</span><span class="sxs-lookup"><span data-stu-id="50005-109">Inputs</span></span>](#BKMK_Inputs)

-   [<span data-ttu-id="50005-110">Salidas</span><span class="sxs-lookup"><span data-stu-id="50005-110">Outputs</span></span>](#BKMK_Outputs)

 <span data-ttu-id="50005-111">Si quiere experimentar con este visor, puede crear un modelo con el [Asistente para clasificación &#40;Complementos de minería de datos para Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) y usar las opciones **avanzadas** para cambiar el algoritmo al de Regresión logística de Microsoft en el cuadro de diálogo **Parámetros de algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="50005-111">If you want to experiment with this viewer, you can create a model using the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard, and use the **Advanced** option to change the algorithm to Microsoft Logistic Regression in the **Algorithm Parameters** dialog box.</span></span>

###  <a name="variables"></a><a name="BKMK_Variables"></a><span data-ttu-id="50005-112">Variable</span><span class="sxs-lookup"><span data-stu-id="50005-112">Variables</span></span>
 <span data-ttu-id="50005-113">El panel **Variables** muestra una lista de variables de entrada según el orden en el que surten efecto en el modelo.</span><span class="sxs-lookup"><span data-stu-id="50005-113">The **Variables** pane displays a list of input variables in order of their effect on the model.</span></span> <span data-ttu-id="50005-114">Para filtrar el modelo, se usan los controles de **Entrada** y de **Salida**, que afectan a las variables que se muestran, así como a su orden.</span><span class="sxs-lookup"><span data-stu-id="50005-114">You use the **Input** and **Output** controls to filter the model, affecting the variables that are displayed, as well as their order.</span></span>

 <span data-ttu-id="50005-115">Con este visor, podrá explorar los factores más importantes para determinar si un cliente pertenece con más probabilidad a la categoría Bike Buyer o a la categoría Non-buyer.</span><span class="sxs-lookup"><span data-stu-id="50005-115">Using this viewer, you can explore the factors that are most important in determining whether a customer more likely belongs to the bike buyer category or the non-buyer category.</span></span>

 <span data-ttu-id="50005-116">![Probar el efecto en el resultado de atributos seleccionados](media/dm13-neuralnet-agebuyer1.gif "Probar el efecto en el resultado de atributos seleccionados")</span><span class="sxs-lookup"><span data-stu-id="50005-116">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer1.gif "Testing effect on outcome of selected attributes")</span></span>

##### <a name="explore-variables"></a><span data-ttu-id="50005-117">Explorar las variables</span><span class="sxs-lookup"><span data-stu-id="50005-117">Explore variables</span></span>

1.  <span data-ttu-id="50005-118">Inicialmente, el panel **Variables** se ordenaba por la importancia de los atributos, en función de los filtros actuales.</span><span class="sxs-lookup"><span data-stu-id="50005-118">Initially, the **Variables** pane is sorted in order of the most important attributes, given the current filters.</span></span> <span data-ttu-id="50005-119">La longitud de la barra indica la fuerza del factor.</span><span class="sxs-lookup"><span data-stu-id="50005-119">The length of the bar indicates the strength of the factor.</span></span>

     <span data-ttu-id="50005-120">En el ejemplo, puede ver que los ingresos son el factor con mayor influencia, seguido de la región.</span><span class="sxs-lookup"><span data-stu-id="50005-120">In the example, you can see that income is the most influential factor, followed by region.</span></span> <span data-ttu-id="50005-121">Por otra parte, los clientes con muchos automóviles y muchos hijos probablemente no comprarán una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="50005-121">On the other hand, customers with many cars and many children are highly unlikely to buy a bike.</span></span>

2.  <span data-ttu-id="50005-122">En el panel **Variables**, haga clic en el encabezado de columna para **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="50005-122">In the **Variables** pane, click the column heading for **Attribute**.</span></span>

     <span data-ttu-id="50005-123">Al ordenar según los atributos, puede ver las discretizaciones que se crearon para cada una de las columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="50005-123">By sorting on attribute, you can see the bins that were created for each of the input columns.</span></span> <span data-ttu-id="50005-124">Los valores literales *discretizan* las columnas con valores discretos, como por ejemplo, empleo.</span><span class="sxs-lookup"><span data-stu-id="50005-124">Columns with discrete values, such as occupation, are *binned* by the literal values.</span></span>

3.  <span data-ttu-id="50005-125">Observe los intervalos de valores que se encontraron para **Edad** e **Ingresos**.</span><span class="sxs-lookup"><span data-stu-id="50005-125">Notice the ranges of values that were found for **Age** and **Income**.</span></span>

     <span data-ttu-id="50005-126">Si ninguna de las columnas de entrada son números (es decir, la totalidad de la columna de datos es un tipo de dato numérico continuo), los números se depositan o discretizan en intervalos discretos.</span><span class="sxs-lookup"><span data-stu-id="50005-126">If any of your input columns are numbers (that is, the entire column of data is a continuous numeric data type), the numbers are bucketed, or binned, into discrete ranges.</span></span>

     <span data-ttu-id="50005-127">Para los ingresos, la columna se ha subdividido de grupos, como por ejemplo, 78,4-154,06 (para el nivel de ingresos más elevado).</span><span class="sxs-lookup"><span data-stu-id="50005-127">For Income, the column has been subdivided into groupings such as 78.4-154.06 (for the uppermost income range).</span></span>

     <span data-ttu-id="50005-128">![ordenar para ver cómo se agrupan las variables](media/dm13-nn-bucketing-variables.gif "ordenar para ver cómo se agrupan las variables")</span><span class="sxs-lookup"><span data-stu-id="50005-128">![sort to view how variables were binned](media/dm13-nn-bucketing-variables.gif "sort to view how variables were binned")</span></span>

     <span data-ttu-id="50005-129">Si quiere hacer grupos diferentes, use la herramienta [Cambiar etiquetas &#40;Complementos de minería de datos de SQL Server&#41;](relabel-sql-server-data-mining-add-ins.md) o las funciones de Excel para crear nuevas categorías de ingresos antes de generar el modelo.</span><span class="sxs-lookup"><span data-stu-id="50005-129">If you want different groupings, you should use the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool, or Excel functions, to create new income categories before building the model.</span></span>

4.  <span data-ttu-id="50005-130">Haga clic en **Favorece Sí** para restaurar el gráfico a la vista predeterminada.</span><span class="sxs-lookup"><span data-stu-id="50005-130">Click **Favors Yes** to restore the graph to the default view.</span></span>

     <span data-ttu-id="50005-131">De manera predeterminada, la vista se ordena según el valor de **Favorece** para el primer valor que aparece como resultado.</span><span class="sxs-lookup"><span data-stu-id="50005-131">By default, the view is sorted by the value of **Favors** for the first outcome value.</span></span> <span data-ttu-id="50005-132">Puede cambiar los resultados que se asignan a la primera y segunda columna; para ello, elija un valor nuevo para **Valor 1** y **Valor 2** en **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="50005-132">You can change which outcomes are assigned to the first and second columns by choosing a new value for **Value 1** and **Value 2** in **Output**.</span></span>

5.  <span data-ttu-id="50005-133">Sitúe el mouse sobre la barra coloreada superior del gráfico.</span><span class="sxs-lookup"><span data-stu-id="50005-133">Pause the mouse over the topmost colored bar in the chart.</span></span>

     <span data-ttu-id="50005-134">Aparece una ventana con información sobre herramientas que incluye una puntuación de *importancia*, un par de puntuaciones de *probabilidad* y un par de valores de *mejora respecto al modelo predictivo*.</span><span class="sxs-lookup"><span data-stu-id="50005-134">A ToolTip appears that includes an *importance* score, a pair of *probability* scores, and a pair of *lift* values.</span></span>

    -   <span data-ttu-id="50005-135">La **importancia** se calcula en la totalidad del conjunto de datos y se identifica el atributo que, teniendo en cuenta todas las entradas, tiene mayor correlación con el resultado de destino.</span><span class="sxs-lookup"><span data-stu-id="50005-135">**Importance** is calculated across the entire dataset, and identifies the attribute that, given all inputs, is most correlated with the target outcome.</span></span> <span data-ttu-id="50005-136">El visor ordena los valores del gráfico según las puntuaciones de importancia.</span><span class="sxs-lookup"><span data-stu-id="50005-136">The viewer sorts the values in the chart by the importance scores.</span></span>

    -   <span data-ttu-id="50005-137">La **probabilidad** se calcula para cada conjunto de pares atributo-valor, para los resultados de destino, en la totalidad del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="50005-137">**Probability** is calculated for each set of attribute-value pairs, for the target outcomes, across the entire data set.</span></span>

    -   <span data-ttu-id="50005-138">La **mejora respecto al modelo predictivo** indica el grado de utilidad de un par atributo-valor determinado para promover un resultado u otro.</span><span class="sxs-lookup"><span data-stu-id="50005-138">**Lift** tells you how useful this particular attribute-value pair is for promoting one outcome or another.</span></span>

     <span data-ttu-id="50005-139">Nota: La información sobre herramientas contiene la misma información independientemente de si coloca el mouse sobre una columna u otra.</span><span class="sxs-lookup"><span data-stu-id="50005-139">Note: The ToolTip contains the same information no matter whether you position the mouse over one column or the other.</span></span>

 [<span data-ttu-id="50005-140">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="50005-140">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="50005-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50005-141">Inputs</span></span>
 <span data-ttu-id="50005-142">El panel **Entradas** le permite elegir un conjunto de entradas y aplicarlo como filtro para el modelo, lo cual le permite ver el efecto de esas opciones en el resultado en función de los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="50005-142">The **Inputs** pane lets you choose a set of inputs and apply that as a filter to the model, which lets you see the influence of those choices on the outcome, based on the training data</span></span>

##### <a name="explore-inputs"></a><span data-ttu-id="50005-143">Explorar entradas</span><span class="sxs-lookup"><span data-stu-id="50005-143">Explore inputs</span></span>

1.  <span data-ttu-id="50005-144">Imagine que desea fijar como destino un grupo específico y que sabe los factores que influencian en mayor medida a las compras de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="50005-144">Suppose you want to target a particular group, and see the factors that most influence purchasing in that group.</span></span>

     <span data-ttu-id="50005-145">En el panel **entrada** , haga clic en la **\<All>** celda situada debajo de **atributo**y seleccione **Age**.</span><span class="sxs-lookup"><span data-stu-id="50005-145">In the **Input** pane, click the **\<All>** cell under **Attribute**, and select **Age**.</span></span>

     <span data-ttu-id="50005-146">Para **Valor**, seleccione la categoría de edad más joven.</span><span class="sxs-lookup"><span data-stu-id="50005-146">For **Value**, select the youngest age category.</span></span>

2.  <span data-ttu-id="50005-147">Observe que incluso cuando filtra en una categoría de edad específica, la región Pacífico pasa casi al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="50005-147">Notice that even when you filter on a particular age group, the Pacific region comes to near the top of the list.</span></span> <span data-ttu-id="50005-148">Esto se debe a que los clientes de la región del Pacífico son más proclives a comprar una bicicleta que los clientes de otras regiones.</span><span class="sxs-lookup"><span data-stu-id="50005-148">This is because customers in the Pacific region are far more likely to buy a bike than customers in other regions.</span></span>

     <span data-ttu-id="50005-149">Puesto que la región no es algo en que se pueda influir, se puede quitar esta variable para que no se tenga en cuenta y ver otros factores y volver a cambiar las entradas.</span><span class="sxs-lookup"><span data-stu-id="50005-149">Since region is not something you can influence, to remove this variable from consideration and see other factors, you can change the inputs again.</span></span>

     <span data-ttu-id="50005-150">En el panel **Entrada**, haga clic en la celda vacía en **Edad** y seleccione **Región**.</span><span class="sxs-lookup"><span data-stu-id="50005-150">In the **Input** pane, click the empty cell under **Age**, and select **Region**.</span></span>

     <span data-ttu-id="50005-151">En **Valor**, seleccione **Europa**.</span><span class="sxs-lookup"><span data-stu-id="50005-151">For **Value**, select **Europe**.</span></span>

3.  <span data-ttu-id="50005-152">Siga agregando filtros de entrada para centrarse en un grupo de interés particular.</span><span class="sxs-lookup"><span data-stu-id="50005-152">Continue adding input filters to focus on a group of particular interest.</span></span>

     <span data-ttu-id="50005-153">Por ejemplo, para el atributo de entrada, agregue **Sexo** y seleccione **Femenino** como valor.</span><span class="sxs-lookup"><span data-stu-id="50005-153">For example, for the input attribute, add **Gender**, and select **Female** as the value.</span></span>

     <span data-ttu-id="50005-154">![Probar el efecto en el resultado de atributos seleccionados](media/dm13-neuralnet-agebuyer2.gif "Probar el efecto en el resultado de atributos seleccionados")</span><span class="sxs-lookup"><span data-stu-id="50005-154">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer2.gif "Testing effect on outcome of selected attributes")</span></span>

     <span data-ttu-id="50005-155">Observe cómo cambia la lista de variables.</span><span class="sxs-lookup"><span data-stu-id="50005-155">Notice how the list of variables changes.</span></span> <span data-ttu-id="50005-156">Ahora **Ingresos** es la variable más importante para predecir el resultado de destino.</span><span class="sxs-lookup"><span data-stu-id="50005-156">Now **Income** is the variable that is most important in predicting the target outcome.</span></span>

     <span data-ttu-id="50005-157">El orden en el que se aplican los filtros de entrada no afecta a los resultados.</span><span class="sxs-lookup"><span data-stu-id="50005-157">The order in which you apply the input filters does not affect the results.</span></span>

 [<span data-ttu-id="50005-158">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="50005-158">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="50005-159">Salidas</span><span class="sxs-lookup"><span data-stu-id="50005-159">Outputs</span></span>
 <span data-ttu-id="50005-160">En el panel **Resultados**, puede elegir el resultado que le interesa.</span><span class="sxs-lookup"><span data-stu-id="50005-160">In the **Outputs** pane, you can choose the outcome that you are interested in.</span></span> <span data-ttu-id="50005-161">Las redes neuronales le permiten especificar tantas columnas de resultados como desee, aunque al agregar más resultados aumenta la complejidad del modelo y su procesamiento podría requerir mucho más tiempo.</span><span class="sxs-lookup"><span data-stu-id="50005-161">Neural networks let you specify as many outcome columns as you like, although adding more outputs adds to the complexity of the model and may require a much longer time to process.</span></span>

 <span data-ttu-id="50005-162">Para comparar dos resultados, se deben haber designado como columnas **Predicción** o **Solo predicción**.</span><span class="sxs-lookup"><span data-stu-id="50005-162">To compare two outputs, they must have been designated as **Predict** or **Predict Only** columns.</span></span>

##### <a name="explore-outputs"></a><span data-ttu-id="50005-163">Explorar resultados</span><span class="sxs-lookup"><span data-stu-id="50005-163">Explore outputs</span></span>

1.  <span data-ttu-id="50005-164">Use la lista **Atributo de salida** para seleccionar un atributo.</span><span class="sxs-lookup"><span data-stu-id="50005-164">Use the **Output Attribute** list to select an attribute.</span></span>

2.  <span data-ttu-id="50005-165">Seleccione dos resultados en las listas de Valor 1 y Valor 2.</span><span class="sxs-lookup"><span data-stu-id="50005-165">Select two outcomes from the Value 1 and Value 2 lists.</span></span> <span data-ttu-id="50005-166">Estos dos estados del atributo de salida se compararán en el panel **Variables** .</span><span class="sxs-lookup"><span data-stu-id="50005-166">These two states of the output attribute will be compared in the **Variables** pane.</span></span>

 [<span data-ttu-id="50005-167">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="50005-167">Back To Top</span></span>](#BKMK_Tabs)

## <a name="more-about-neural-network-models"></a><span data-ttu-id="50005-168">Más información acerca de los modelos de red neuronal</span><span class="sxs-lookup"><span data-stu-id="50005-168">More About Neural Network Models</span></span>
 <span data-ttu-id="50005-169">La información del visor se recupera del servidor con un procedimiento almacenado específico para este tipo de modelo: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span><span class="sxs-lookup"><span data-stu-id="50005-169">The information in the viewer is retrieved from the server using a stored procedure specific to this model type: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span></span>

 <span data-ttu-id="50005-170">Si quiere crear un modelo con varios atributos de predicción mediante complementos, use las opciones de modelado **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="50005-170">If you want to create a model with multiple predictable attributes using the add-ins, use the **Advanced** modeling options.</span></span>

 <span data-ttu-id="50005-171">Para más información, vea [Crear estructura de minería de datos &#40;Complementos de minería de datos de SQL Server&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) y [Agregar modelo a estructura &#40;Complementos de minería de datos para Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="50005-171">For more information, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) and [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="50005-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50005-172">See Also</span></span>
 [<span data-ttu-id="50005-173">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="50005-173">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)


