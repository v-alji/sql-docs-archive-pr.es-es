---
title: Probar la precisión con los gráficos de elevación (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 822d414b-4a39-473f-80c3-53476e30655a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a3dcdd1d1b78911f5ffd37a383532abdd4814c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747276"
---
# <a name="testing-accuracy-with-lift-charts-basic-data-mining-tutorial"></a><span data-ttu-id="515d7-102">Probar la exactitud con gráficos de mejora respecto al modelo predictivo (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="515d7-102">Testing Accuracy with Lift Charts (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="515d7-103">En la pestaña **gráfico de precisión de minería** de datos del diseñador de minería de datos, puede calcular el grado en que cada uno de los modelos realiza las predicciones y comparar los resultados de cada modelo directamente con los resultados de los otros modelos.</span><span class="sxs-lookup"><span data-stu-id="515d7-103">On the **Mining Accuracy Chart** tab of Data Mining Designer, you can calculate how well each of your models makes predictions, and compare the results of each model directly against the results of the other models.</span></span> <span data-ttu-id="515d7-104">Este método de comparación se conoce como gráfico de *elevación*.</span><span class="sxs-lookup"><span data-stu-id="515d7-104">This method of comparison is referred to as a *lift chart*.</span></span> <span data-ttu-id="515d7-105">Normalmente, la exactitud de la predicción de un modelo de minería de datos se cuantifica mediante la mejora respecto al modelo predictivo o la exactitud de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="515d7-105">Typically, the predictive accuracy of a mining model is measured by either lift or classification accuracy.</span></span> <span data-ttu-id="515d7-106">En este tutorial utilizaremos solamente el gráfico de mejora respecto al modelo predictivo.</span><span class="sxs-lookup"><span data-stu-id="515d7-106">For this tutorial we will use the lift chart only.</span></span>  
  
 <span data-ttu-id="515d7-107">En este tema, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="515d7-107">In this topic, you will perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="515d7-108">Elegir los datos de entrada</span><span class="sxs-lookup"><span data-stu-id="515d7-108">Choose the Input Data</span></span>](#BKMK_InputData)  
  
-   [<span data-ttu-id="515d7-109">Configurar parámetros del gráfico de precisión</span><span class="sxs-lookup"><span data-stu-id="515d7-109">Configure Accuracy Chart Parameters</span></span>](#BKMK_Selecting)  
  
##  <a name="choosing-the-input-data"></a><a name="BKMK_InputData"></a><span data-ttu-id="515d7-110">Elección de los datos de entrada</span><span class="sxs-lookup"><span data-stu-id="515d7-110">Choosing the Input Data</span></span>  
 <span data-ttu-id="515d7-111">El primer paso a la hora de probar la precisión de los modelos de minería de datos consiste en seleccionar el origen de datos que usará para realizar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="515d7-111">The first step in testing the accuracy of your mining models is to select the data source that you will use for testing.</span></span> <span data-ttu-id="515d7-112">Probará la exactitud de los modelos con sus datos de prueba y, a continuación, los utilizará con datos externos.</span><span class="sxs-lookup"><span data-stu-id="515d7-112">You will test how well the models perform against your testing data and then you will use them with external data.</span></span>  
  
#### <a name="to-select-the-data-set"></a><span data-ttu-id="515d7-113">Para seleccionar el conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="515d7-113">To select the data set</span></span>  
  
1.  <span data-ttu-id="515d7-114">Cambie a la pestaña **Gráfico de precisión de minería de datos** del Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y seleccione la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="515d7-114">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="515d7-115">En el cuadro de grupo **Seleccionar un conjunto de datos para usarlo en un gráfico de precisión** , seleccione **Usar casos de prueba de estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="515d7-115">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span> <span data-ttu-id="515d7-116">Estos son los datos de prueba que separó cuando creó la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="515d7-116">This is the testing data that you set aside when you created the mining structure.</span></span>  
  
     <span data-ttu-id="515d7-117">Para obtener más información sobre las demás opciones, vea [elegir un tipo de gráfico de precisión y establecer las opciones del gráfico](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span><span class="sxs-lookup"><span data-stu-id="515d7-117">For more information on the other options, see [Choose an Accuracy Chart Type and Set Chart Options](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span></span>  
  
##  <a name="setting-accuracy-chart-parameters"></a><a name="BKMK_Selecting"></a><span data-ttu-id="515d7-118">Establecer los parámetros del gráfico de precisión</span><span class="sxs-lookup"><span data-stu-id="515d7-118">Setting Accuracy Chart Parameters</span></span>  
 <span data-ttu-id="515d7-119">Para crear un gráfico de precisión, debe definir tres cosas:</span><span class="sxs-lookup"><span data-stu-id="515d7-119">To create an accuracy chart, you must define three things:</span></span>  
  
-   <span data-ttu-id="515d7-120">¿Qué modelos debe incluir en el gráfico de precisión?</span><span class="sxs-lookup"><span data-stu-id="515d7-120">Which models should you include in the accuracy chart?</span></span>  
  
-   <span data-ttu-id="515d7-121">¿Qué atributo de predicción desea medir?</span><span class="sxs-lookup"><span data-stu-id="515d7-121">Which predictable attribute do you want to measure?</span></span> <span data-ttu-id="515d7-122">Algunos modelos pueden tener varios objetivos, pero cada gráfico solo puede medir un resultado cada vez.</span><span class="sxs-lookup"><span data-stu-id="515d7-122">Some models might have multiple targets, but each chart can measure only one outcome at a time.</span></span>  
  
     <span data-ttu-id="515d7-123">Para usar una columna como **nombre de columna de predicción** en un gráfico de precisión, las columnas deben tener el tipo de uso de `Predict` o `Predict Only` .</span><span class="sxs-lookup"><span data-stu-id="515d7-123">To use a column as the **Predictable Column Name** in an accuracy chart, the columns must have the usage type of `Predict` or `Predict Only`.</span></span> <span data-ttu-id="515d7-124">Además, el tipo de contenido de la columna de destino debe ser `Discrete` o `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="515d7-124">Also, the content type of the target column must be either `Discrete` or `Discretized`.</span></span> <span data-ttu-id="515d7-125">Es decir, no puede medir la precisión en salidas numéricas continuas con el gráfico de elevación.</span><span class="sxs-lookup"><span data-stu-id="515d7-125">In other words, you cannot measure accuracy against continuous numeric outputs using the lift chart.</span></span>  
  
-   <span data-ttu-id="515d7-126">¿Desea medir la precisión general del modelo o su precisión en la predicción de un valor determinado (por ejemplo, [Bike Buyer] = ' Yes ')</span><span class="sxs-lookup"><span data-stu-id="515d7-126">Do you want to measure the model's general accuracy, or its accuracy  in predicting a particular value (such as [Bike Buyer] = 'Yes')</span></span>  
  
#### <a name="to-generate-the-lift-chart"></a><span data-ttu-id="515d7-127">Para generar el gráfico de elevación</span><span class="sxs-lookup"><span data-stu-id="515d7-127">To generate the lift chart</span></span>  
  
1.  <span data-ttu-id="515d7-128">En la pestaña **Selección de entrada** del Diseñador de minería de datos, en **Seleccione las columnas del modelo de minería de datos de predicción que se mostrarán en el gráfico de elevación**, active la casilla correspondiente a **Sincronizar valores y columnas de predicción**.</span><span class="sxs-lookup"><span data-stu-id="515d7-128">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
2.  <span data-ttu-id="515d7-129">En la columna **Nombre de columna de predicción** , compruebe que **Bike Buyer** está seleccionado para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="515d7-129">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
3.  <span data-ttu-id="515d7-130">En la columna **Mostrar** , seleccione cada uno de los modelos.</span><span class="sxs-lookup"><span data-stu-id="515d7-130">In the **Show** column, select each of the models.</span></span>  
  
     <span data-ttu-id="515d7-131">De forma predeterminada, todos los modelos de la estructura de minería de datos aparecen seleccionados.</span><span class="sxs-lookup"><span data-stu-id="515d7-131">By default, all the models in the mining structure are selected.</span></span> <span data-ttu-id="515d7-132">Puede decidir no incluir un modelo específico, pero para este tutorial deje todos los modelos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="515d7-132">You can decide not to include a model, but for this tutorial leave all the models selected.</span></span>  
  
4.  <span data-ttu-id="515d7-133">En la columna **Valor de predicción** , seleccione **1**.</span><span class="sxs-lookup"><span data-stu-id="515d7-133">In the **Predict Value** column, select **1**.</span></span> <span data-ttu-id="515d7-134">El mismo valor se rellena automáticamente para cada modelo que tiene la misma columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="515d7-134">The same value is automatically filled in for each model that has the same predictable column.</span></span>  
  
5.  <span data-ttu-id="515d7-135">Seleccione la pestaña **gráfico de elevación** .</span><span class="sxs-lookup"><span data-stu-id="515d7-135">Select the **Lift Chart** tab.</span></span>  
  
     <span data-ttu-id="515d7-136">Al hacer clic en la pestaña, se ejecuta una consulta de predicción para obtener predicciones de los datos de prueba, y se comparan los resultados con los valores conocidos.</span><span class="sxs-lookup"><span data-stu-id="515d7-136">When you click the tab, a prediction query is executed to get predictions for the test data, and the results are compared against the known values.</span></span> <span data-ttu-id="515d7-137">Los resultados se trazan en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="515d7-137">The results are plotted on the graph.</span></span>  
  
     <span data-ttu-id="515d7-138">Si especificó un resultado de destino determinado mediante la opción de **valor de predicción** , el gráfico de elevación traza los resultados de los intentos aleatorios y los resultados de un modelo ideal.</span><span class="sxs-lookup"><span data-stu-id="515d7-138">If you specified a particular target outcome using the **Predict Value** option, the lift chart plots the results of random guesses and the results of an ideal model.</span></span>  
  
    -   <span data-ttu-id="515d7-139">La línea de suposición aleatoria muestra cuál sería el grado de precisión del modelo sin utilizar ningún dato para informar de sus predicciones: es decir, una división 50-50 entre dos resultados.</span><span class="sxs-lookup"><span data-stu-id="515d7-139">The random guess line shows how accurate the model would be without using any data to inform its predictions: that is, a 50-50 split between two outcomes.</span></span> <span data-ttu-id="515d7-140">El gráfico de elevación ayuda a visualizar la mejora del funcionamiento del modelo con respecto a una estimación aleatoria.</span><span class="sxs-lookup"><span data-stu-id="515d7-140">The lift chart helps you visualize how much better your model performs in comparison to a random guess.</span></span>  
  
    -   <span data-ttu-id="515d7-141">La línea del modelo ideal representa el límite superior de precisión.</span><span class="sxs-lookup"><span data-stu-id="515d7-141">The ideal model line represents the upper bound of accuracy.</span></span> <span data-ttu-id="515d7-142">Muestra el beneficio máximo posible que podría conseguir si el modelo siempre hiciera sus predicciones con precisión.</span><span class="sxs-lookup"><span data-stu-id="515d7-142">It shows you the maximum possible benefit you could achieve if your model always predicted accurately.</span></span>  
  
     <span data-ttu-id="515d7-143">Los modelos de minería de datos que creó estarán normalmente entre estos dos extremos.</span><span class="sxs-lookup"><span data-stu-id="515d7-143">The mining models you created will usually fall between these two extremes.</span></span> <span data-ttu-id="515d7-144">Cualquier mejora de la estimación aleatoria se considera una *elevación*.</span><span class="sxs-lookup"><span data-stu-id="515d7-144">Any improvement from the random guess is considered to be *lift*.</span></span>  
  
6.  <span data-ttu-id="515d7-145">Utilice la leyenda para buscar las líneas coloreadas que representan el modelo ideal y el modelo de suposición aleatoria.</span><span class="sxs-lookup"><span data-stu-id="515d7-145">Use the legend to locate the colored lines representing the Ideal Model and the Random Guess Model.</span></span>  
  
     <span data-ttu-id="515d7-146">Observará que el `TM_Decision_Tree` modelo proporciona la mejor elevación, con lo que se consiguen los modelos Bayes de agrupación en clústeres y Naive.</span><span class="sxs-lookup"><span data-stu-id="515d7-146">You'll notice that the `TM_Decision_Tree` model provides the greatest lift,  outperforming both the Clustering and Naive Bayes models.</span></span>  
  
 <span data-ttu-id="515d7-147">Para obtener una explicación detallada de un gráfico de elevación similar al creado en esta lección, vea el [gráfico de elevación &#40;Analysis Services-&#41;de minería de datos ](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="515d7-147">For an in-depth explanation of a lift chart similar to the one created in this lesson, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="515d7-148">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="515d7-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="515d7-149">Probar un modelo filtrado &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="515d7-149">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="515d7-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="515d7-150">See Also</span></span>  
 <span data-ttu-id="515d7-151">[Gráfico de elevación &#40;Analysis Services:&#41;de minería de datos](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="515d7-151">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="515d7-152">Pestaña gráfico de elevación &#40;vista gráfico de precisión de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="515d7-152">Lift Chart Tab &#40;Mining Accuracy Chart View&#41;</span></span>](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md)  
  
  
