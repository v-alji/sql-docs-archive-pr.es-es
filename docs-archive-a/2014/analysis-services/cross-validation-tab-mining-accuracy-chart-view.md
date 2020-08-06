---
title: Pestaña validación cruzada (vista gráfico de precisión de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.crossvalidation.f1
ms.assetid: bd215a68-1ad7-4046-9c44-ec8e2be13a64
author: minewiskan
ms.author: owend
ms.openlocfilehash: 867bd6d1abffb29ec3eb2a8a78e562e5cbcc5b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671853"
---
# <a name="cross-validation-tab-mining-accuracy-chart-view"></a><span data-ttu-id="3a419-102">Pestaña Validación cruzada (vista Gráfico de precisión de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="3a419-102">Cross-Validation Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="3a419-103">La validación cruzada le permite dividir una estructura de minería de datos en secciones transversales y entrenar y probar de forma iterativa los modelos con cada sección transversal.</span><span class="sxs-lookup"><span data-stu-id="3a419-103">Cross-validation lets you partition a mining structure into cross-sections and iteratively train and test models against each cross-section.</span></span> <span data-ttu-id="3a419-104">Se especifican varios subconjuntos en los que se dividirán los datos, y cada uno se usa a su vez como datos de pruebas, mientras que los datos restantes se usan para entrenar un nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="3a419-104">You specify a number of folds to divide the data into, and each fold is used in turn as the test data, whereas the remaining data is used to train a new model.</span></span> <span data-ttu-id="3a419-105">A continuación, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] genera un conjunto de medidas de precisión estándar para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="3a419-105">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] then generates a set of standard accuracy metrics for each model.</span></span> <span data-ttu-id="3a419-106">Al comparar las medidas de los modelos generados para cada sección transversal, puede hacerse una idea del grado de confiabilidad del modelo de minería con respecto a todo el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3a419-106">By comparing the metrics for the models generated for each cross-section, you can get a good idea of how reliable the mining model is for the whole data set.</span></span>  
  
 <span data-ttu-id="3a419-107">Para obtener más información, vea [Validación cruzada &#40;Analysis Services - Minería de datos&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3a419-107">For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a419-108">La validación cruzada no se puede usar con modelos que se hayan generado con el algoritmo de serie temporal de [!INCLUDE[msCoName](../includes/msconame-md.md)] o con el algoritmo de clústeres de secuencia de [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a419-108">Cross-validation cannot be used with models that were built by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span> <span data-ttu-id="3a419-109">Si ejecuta el informe en una estructura de minería de datos que contiene estos tipos de modelos, los modelos no se incluirán en el informe.</span><span class="sxs-lookup"><span data-stu-id="3a419-109">If you run the report on a mining structure that contains these types of models, the models will not be included in the report.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="3a419-110">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="3a419-110">Task List</span></span>  
  
-   <span data-ttu-id="3a419-111">Especifique el número de subconjuntos.</span><span class="sxs-lookup"><span data-stu-id="3a419-111">Specify the number of folds.</span></span>  
  
-   <span data-ttu-id="3a419-112">Especifique el número máximo de casos para utilizar en la validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="3a419-112">Specify the maximum number of cases to use for cross-validation.</span></span>  
  
-   <span data-ttu-id="3a419-113">Especifique la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="3a419-113">Specify the predictable column.</span></span>  
  
-   <span data-ttu-id="3a419-114">Si lo desea, puede especificar un estado de predicción.</span><span class="sxs-lookup"><span data-stu-id="3a419-114">Optionally, specify a predictable state.</span></span>  
  
-   <span data-ttu-id="3a419-115">Además, puede establecer parámetros que controlen cómo se evalúa la precisión de la predicción.</span><span class="sxs-lookup"><span data-stu-id="3a419-115">Optionally, set parameters that control how the accuracy of prediction is assessed.</span></span>  
  
-   <span data-ttu-id="3a419-116">Haga clic en **Obtener resultados** para mostrar los resultados de la validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="3a419-116">Click **Get Results** to display the results of cross-validation.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="3a419-117">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3a419-117">UI element list</span></span>  
 <span data-ttu-id="3a419-118">**Recuento de plegamientos**</span><span class="sxs-lookup"><span data-stu-id="3a419-118">**Fold Count**</span></span>  
 <span data-ttu-id="3a419-119">Especifique el número de subconjuntos, o particiones, que desea crear.</span><span class="sxs-lookup"><span data-stu-id="3a419-119">Specify the number of folds, or partitions, to create.</span></span> <span data-ttu-id="3a419-120">El valor mínimo es 2, lo que significa que se usa la mitad del conjunto de datos para las pruebas y la otra mitad para el aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="3a419-120">The minimum value is 2, meaning that half the data set is used for testing and half for training.</span></span>  
  
 <span data-ttu-id="3a419-121">El valor máximo es 10 para las estructuras de minería de datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="3a419-121">The maximum value is 10 for session mining structures.</span></span>  
  
 <span data-ttu-id="3a419-122">El valor máximo es 256, si la estructura de minería de datos está almacenada en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a419-122">The maximum value is 256 if the mining structure is stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a419-123">Cuando aumenta el número de subconjuntos, el tiempo que se necesita para realizar la validación cruzada aumenta de igual forma en n.</span><span class="sxs-lookup"><span data-stu-id="3a419-123">As you increase the number of folds, the time that is required to perform cross-validation similarly increases by n.</span></span> <span data-ttu-id="3a419-124">Pueden producirse problemas de rendimiento si el número de casos es elevado y el valor de **Recuento de plegamientos** también es elevado.</span><span class="sxs-lookup"><span data-stu-id="3a419-124">You might experience performance issues if the number of cases is large and the value of **Fold Count** is also large.</span></span>  
  
 <span data-ttu-id="3a419-125">**Número máximo de casos**</span><span class="sxs-lookup"><span data-stu-id="3a419-125">**Max Cases**</span></span>  
 <span data-ttu-id="3a419-126">Especifique el número máximo de casos para utilizar en la validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="3a419-126">Specify the maximum number of cases to use for cross-validation.</span></span> <span data-ttu-id="3a419-127">El número de casos en cualquier subconjunto determinado es igual al valor **Máximo de casos** dividido por el valor de **Recuento de plegamientos** .</span><span class="sxs-lookup"><span data-stu-id="3a419-127">The number of cases in any particular fold is equal to the **Max Cases** value divided by the **Fold Count** value.</span></span>  
  
 <span data-ttu-id="3a419-128">Si usa **0**, todos los casos de los datos de origen se usarán para la validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="3a419-128">If you use **0**, all cases in the source data are used for cross-validation.</span></span>  
  
 <span data-ttu-id="3a419-129">No hay ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3a419-129">There is no default value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a419-130">El tiempo de proceso también aumenta a medida que aumenta el número de casos.</span><span class="sxs-lookup"><span data-stu-id="3a419-130">As you increase the number of cases, processing time also increases.</span></span>  
  
 <span data-ttu-id="3a419-131">**Atributo de destino**</span><span class="sxs-lookup"><span data-stu-id="3a419-131">**Target Attribute**</span></span>  
 <span data-ttu-id="3a419-132">Seleccione una columna de la lista de columnas de predicción que se encuentra en todos los modelos.</span><span class="sxs-lookup"><span data-stu-id="3a419-132">Select a column from the list of predictable columns found in all models.</span></span> <span data-ttu-id="3a419-133">Solo puede seleccionar una columna predecible cada vez que realice validación cruzada.</span><span class="sxs-lookup"><span data-stu-id="3a419-133">You can only select one predictable column every time that you perform cross-validation.</span></span>  
  
 <span data-ttu-id="3a419-134">Para probar solo los modelos de agrupación en clústeres, seleccione **Clúster**.</span><span class="sxs-lookup"><span data-stu-id="3a419-134">To test only clustering models, select **Cluster**.</span></span>  
  
 <span data-ttu-id="3a419-135">**Estado de destino**</span><span class="sxs-lookup"><span data-stu-id="3a419-135">**Target State**</span></span>  
 <span data-ttu-id="3a419-136">Escriba un valor o seleccione un valor de destino en una lista desplegable de valores.</span><span class="sxs-lookup"><span data-stu-id="3a419-136">Type a value, or select a target value from a drop-down list of values.</span></span>  
  
 <span data-ttu-id="3a419-137">El valor predeterminado es `null`, que indica que se probarán todos los estados.</span><span class="sxs-lookup"><span data-stu-id="3a419-137">The default value is `null`, indicating that all states are to be tested.</span></span>  
  
 <span data-ttu-id="3a419-138">Se deshabilita para modelos de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="3a419-138">Disabled for clustering models.</span></span>  
  
 <span data-ttu-id="3a419-139">**Target\*\*\*\*Umbral** de destino  </span><span class="sxs-lookup"><span data-stu-id="3a419-139">**Target**  **Threshold**</span></span>  
 <span data-ttu-id="3a419-140">Especifique un valor entre 0 y 1 que indique la probabilidad de la predicción anterior que se considera que un estado predicho es correcto.</span><span class="sxs-lookup"><span data-stu-id="3a419-140">Specify a value between 0 and 1 that indicates the prediction probability above which a predicted state is considered to be correct.</span></span> <span data-ttu-id="3a419-141">El valor se puede establecer en 0,1 incrementos.</span><span class="sxs-lookup"><span data-stu-id="3a419-141">The value can be set in 0.1 increments.</span></span>  
  
 <span data-ttu-id="3a419-142">El valor predeterminado es `null`, lo que indica que la predicción más probable se cuenta como correcta.</span><span class="sxs-lookup"><span data-stu-id="3a419-142">The default is `null`, indicating that the most probable prediction is counted as correct.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a419-143">Aunque puede establecer el valor en 0,0, si usa este valor aumentará el tiempo de proceso y no producirá resultados significativos.</span><span class="sxs-lookup"><span data-stu-id="3a419-143">Although you can set the value to 0.0, using this value will increase processing time and not yield meaningful results.</span></span>  
  
 <span data-ttu-id="3a419-144">**Obtener resultados**</span><span class="sxs-lookup"><span data-stu-id="3a419-144">**Get Results**</span></span>  
 <span data-ttu-id="3a419-145">Haga clic para comenzar la validación cruzada del modelo utilizando los parámetros especificados.</span><span class="sxs-lookup"><span data-stu-id="3a419-145">Click to begin cross-validation of the model using the specified parameters.</span></span>  
  
 <span data-ttu-id="3a419-146">El modelo se divide en el número especificado de subconjuntos y para cada uno se prueba un modelo independiente.</span><span class="sxs-lookup"><span data-stu-id="3a419-146">The model is partitioned into the specified number of folds and a separate model is tested for each fold.</span></span> <span data-ttu-id="3a419-147">Por consiguiente, podría tardar algún tiempo para que la validación cruzada devuelva resultados.</span><span class="sxs-lookup"><span data-stu-id="3a419-147">Therefore, it might take some time for cross-validation to return the results.</span></span>  
  
 <span data-ttu-id="3a419-148">Para más información sobre cómo interpretar los resultados del informe de validación cruzada, vea [Medidas en el informe de validación cruzada](data-mining/measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="3a419-148">For more information about how to interpret the results of the cross-validation report, see [Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md).</span></span>  
  
## <a name="setting-the-accuracy-threshold"></a><span data-ttu-id="3a419-149">Establecer el umbral de precisión</span><span class="sxs-lookup"><span data-stu-id="3a419-149">Setting the Accuracy Threshold</span></span>  
 <span data-ttu-id="3a419-150">Puede controlar el estándar para medir la exactitud de la predicción estableciendo un valor para **Umbral de** **destino**.</span><span class="sxs-lookup"><span data-stu-id="3a419-150">You can control the standard for measuring prediction accuracy by setting a value for **Target** **Threshold**.</span></span> <span data-ttu-id="3a419-151">Un umbral representa un tipo de barra de precisión.</span><span class="sxs-lookup"><span data-stu-id="3a419-151">A threshold represents a kind of accuracy bar.</span></span> <span data-ttu-id="3a419-152">A cada predicción se le asigna una probabilidad de que el valor predicho sea correcto.</span><span class="sxs-lookup"><span data-stu-id="3a419-152">Each prediction is assigned a probability that the predicted value is correct.</span></span> <span data-ttu-id="3a419-153">Por consiguiente, si establece en 1 el valor de **Umbral** **de destino** , está requiriendo que la probabilidad para cualquier predicción determinada sea bastante alta para contabilizarse como una predicción correcta.</span><span class="sxs-lookup"><span data-stu-id="3a419-153">Therefore, if you set the **Target** **Threshold** value closer to 1, you are requiring that the probability for any particular prediction to be fairly high to be counted as a good prediction.</span></span> <span data-ttu-id="3a419-154">Y a la inversa, si establece en 0 **Umbral** **de destino** , incluso las predicciones con valores de probabilidad más bajos se cuentan como predicciones "buenas".</span><span class="sxs-lookup"><span data-stu-id="3a419-154">Conversely, if you set **Target** **Threshold** closer to 0, even predictions with lower probability values are counted as "good" predictions.</span></span>  
  
 <span data-ttu-id="3a419-155">No hay ningún valor de umbral recomendado porque la probabilidad de cualquier predicción depende de la cantidad de datos y del tipo de predicción que se está realizando.</span><span class="sxs-lookup"><span data-stu-id="3a419-155">There is no recommended threshold value because the probability of any prediction depends on the amount of data and the type of prediction you are making.</span></span> <span data-ttu-id="3a419-156">Debería revisar algunas predicciones en niveles de probabilidad diferentes para determinar una barra de precisión adecuada para sus datos.</span><span class="sxs-lookup"><span data-stu-id="3a419-156">You should review some predictions at different probability levels to determine an appropriate accuracy bar for your data.</span></span> <span data-ttu-id="3a419-157">Es importante que haga esto, porque el valor que establece para **Umbral** **de destino** afecta a la precisión medida del modelo.</span><span class="sxs-lookup"><span data-stu-id="3a419-157">It is important that you do this, because the value that you set for **Target** **Threshold** affects the measured accuracy of the model.</span></span>  
  
 <span data-ttu-id="3a419-158">Por ejemplo, suponga que se hacen tres predicciones para un estado de destino determinado, y las probabilidades de cada predicción son 0,05, 0,15 y 0,8.</span><span class="sxs-lookup"><span data-stu-id="3a419-158">For example, suppose three predictions are made for a particular target state, and the probabilities of each prediction are 0.05, 0.15, and 0.8.</span></span> <span data-ttu-id="3a419-159">Si establece el umbral en 0,5, solamente se tiene en cuenta una predicción como correcta.</span><span class="sxs-lookup"><span data-stu-id="3a419-159">If you set the threshold to 0.5, only one prediction is counted as being correct.</span></span> <span data-ttu-id="3a419-160">Si establece **Umbral** **de destino** en 0,10, se tienen en cuenta dos predicciones como correctas.</span><span class="sxs-lookup"><span data-stu-id="3a419-160">If you set **Target** **Threshold** to 0.10, two predictions are counted as being correct.</span></span>  
  
 <span data-ttu-id="3a419-161">Cuando **Target** **umbral** de destino está establecido en `null` , que es el valor predeterminado, la predicción más probable para cada caso se considera correcta.</span><span class="sxs-lookup"><span data-stu-id="3a419-161">When **Target** **Threshold** is set to `null`, which is the default value, the most probable prediction for each case is counted as correct.</span></span> <span data-ttu-id="3a419-162">En el ejemplo recién citado, 0,05, 0,15 y 0,8 son las probabilidades de las predicciones de tres casos diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a419-162">In the example just cited, 0.05, 0.15, and 0.8 are the probabilities for predictions in three different cases.</span></span> <span data-ttu-id="3a419-163">Aunque las probabilidades son muy distintas, cada una se contaría como correcta, porque cada caso genera solo una predicción y éstas son las mejores predicciones para estos casos.</span><span class="sxs-lookup"><span data-stu-id="3a419-163">Although the probabilities are very different, each prediction would be counted as correct, because each case generates only one prediction and these are the best predictions for these cases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a419-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a419-164">See Also</span></span>  
 <span data-ttu-id="3a419-165">[Pruebas y validación &#40;&#41;de minería de datos](data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3a419-165">[Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="3a419-166">[Analysis Services de &#40;de validación cruzada&#41;de minería de datos](data-mining/cross-validation-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3a419-166">[Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="3a419-167">[Medidas en el informe de validación cruzada](data-mining/measures-in-the-cross-validation-report.md) </span><span class="sxs-lookup"><span data-stu-id="3a419-167">[Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md) </span></span>  
 [<span data-ttu-id="3a419-168">Procedimientos almacenados de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3a419-168">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
