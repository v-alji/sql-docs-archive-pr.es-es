---
title: Crear predicciones de serie temporal (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: fb22cffa-ac99-4d34-ac4a-9c93068e33e8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1175cdffd1512e0cb876b9565dd0727a9f094c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670238"
---
# <a name="creating-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="9647e-102">Crear predicciones de serie temporal (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="9647e-102">Creating Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="9647e-103">En las tareas anteriores de esta lección, creó un modelo de serie temporal y exploró los resultados.</span><span class="sxs-lookup"><span data-stu-id="9647e-103">In the previous tasks in this lesson, you created a time series model and explored the results.</span></span> <span data-ttu-id="9647e-104">De forma predeterminada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] siempre crea un conjunto de cinco (5) predicciones para un modelo de serie temporal y muestra los valores de predicción como parte del gráfico de pronóstico.</span><span class="sxs-lookup"><span data-stu-id="9647e-104">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] always creates a set of five (5) predictions for a time series model and displays the predicted values as part of the forecasting chart.</span></span> <span data-ttu-id="9647e-105">Sin embargo, también puede crear predicciones personalizadas si crea consultas de predicción de las extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="9647e-105">However, you can also create forecasts by building Data Mining Extensions (DMX) prediction queries.</span></span>  
  
 <span data-ttu-id="9647e-106">En esta tarea, creará una consulta de predicción que genera las mismas predicciones que vio en el visor.</span><span class="sxs-lookup"><span data-stu-id="9647e-106">In this task, you will create a prediction query that generates the same predictions that you saw in the viewer.</span></span> <span data-ttu-id="9647e-107">En esta tarea se supone que el usuario ya ha completado las lecciones del Tutorial básico de minería de datos y está familiarizado con el uso del Generador de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="9647e-107">This task assumes that you have already completed the lessons in the Basic Data Mining Tutorial and are familiar with how to use Prediction Query Builder.</span></span> <span data-ttu-id="9647e-108">Ahora obtendrá información sobre la creación de consultas específicas de los modelos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="9647e-108">You will now learn how to create queries specific to time series models.</span></span>  
  
## <a name="creating-time-series-predictions"></a><span data-ttu-id="9647e-109">Crear predicciones de serie temporal</span><span class="sxs-lookup"><span data-stu-id="9647e-109">Creating Time Series Predictions</span></span>  
 <span data-ttu-id="9647e-110">Generalmente, el primer paso para crear una consulta de predicción consiste en seleccionar un modelo de minería de datos y una tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="9647e-110">Typically, the first step in creating a prediction query is to select a mining model and input table.</span></span> <span data-ttu-id="9647e-111">Sin embargo, un modelo de serie temporal no requiere una entrada adicional para una predicción normal.</span><span class="sxs-lookup"><span data-stu-id="9647e-111">However, a time series model does not require additional input for a regular prediction.</span></span> <span data-ttu-id="9647e-112">Por consiguiente, no necesita especificar ningún origen de datos nuevo al realizar las predicciones, a menos que esté agregando datos al modelo o reemplazándolos.</span><span class="sxs-lookup"><span data-stu-id="9647e-112">Therefore, you do not need to specify a new source of data when making predictions, unless you are adding data to the model or replacing the data.</span></span>  
  
 <span data-ttu-id="9647e-113">En esta lección, debe especificar el número de pasos de la predicción.</span><span class="sxs-lookup"><span data-stu-id="9647e-113">For this lesson, you must specify the number of prediction steps.</span></span> <span data-ttu-id="9647e-114">Puede especificar el nombre de serie con el fin de obtener una predicción para una combinación determinada de producto y región.</span><span class="sxs-lookup"><span data-stu-id="9647e-114">You can specify the series name, to get a prediction for a particular combination of a product and a region.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="9647e-115">Para seleccionar un modelo de minería de datos y una tabla de entrada</span><span class="sxs-lookup"><span data-stu-id="9647e-115">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="9647e-116">En la pestaña **predicción de modelo de minería** de datos del diseñador de minería de datos, en el cuadro modelo de **minería** de datos, haga clic en **Seleccionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="9647e-116">On the **Mining Model Prediction** tab of the Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="9647e-117">En el cuadro de diálogo **Seleccionar modelo de minería de datos** , expanda la estructura previsión, seleccione el modelo de **previsión** en la lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9647e-117">In the **Select Mining Model** dialog box, expand the Forecasting structure, select the **Forecasting** model from the list, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9647e-118">Omita el cuadro **seleccionar tabla (s) de entrada** .</span><span class="sxs-lookup"><span data-stu-id="9647e-118">Ignore the **Select Input Table(s)** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9647e-119">En un modelo de serie temporal no necesita especificar ninguna entrada independiente a menos que esté haciendo una predicción cruzada.</span><span class="sxs-lookup"><span data-stu-id="9647e-119">For a time series model, you do not need to specify a separate input unless you are doing cross-prediction.</span></span>  
  
4.  <span data-ttu-id="9647e-120">En la columna **origen** , en la cuadrícula de la pestaña **predicción de modelo de minería de datos** , haga clic en la celda de la primera fila vacía y, a continuación, seleccione modelo de minería de datos de **previsión**.</span><span class="sxs-lookup"><span data-stu-id="9647e-120">In the **Source** column, in the grid on the **Mining Model Prediction** tab, click the cell in the first empty row, and then select **Forecasting mining model**.</span></span>  
  
5.  <span data-ttu-id="9647e-121">En la columna **campo** , seleccione **región del modelo**.</span><span class="sxs-lookup"><span data-stu-id="9647e-121">In the **Field** column, select **Model Region**.</span></span>  
  
     <span data-ttu-id="9647e-122">Esta acción agrega el identificador de la serie a la consulta de predicción para indicar la combinación de modelo y la región a las que se aplica la predicción.</span><span class="sxs-lookup"><span data-stu-id="9647e-122">This action adds the series identifier to the prediction query to indicate the combination of model and region to which the prediction applies.</span></span>  
  
6.  <span data-ttu-id="9647e-123">Haga clic en la siguiente fila vacía de la columna **origen** y, a continuación, seleccione **función de predicción**.</span><span class="sxs-lookup"><span data-stu-id="9647e-123">Click the next empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
7.  <span data-ttu-id="9647e-124">En la columna **campo** , seleccione **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="9647e-124">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9647e-125">También puede usar la función `Predict` con modelos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="9647e-125">You can also use the `Predict` function with time series models.</span></span> <span data-ttu-id="9647e-126">Sin embargo, la función de predicción solo crea una predicción para cada serie de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9647e-126">However, by default, the Predict function creates only one prediction for each series.</span></span> <span data-ttu-id="9647e-127">Por lo tanto, para especificar varios pasos de predicción, debe usar la función **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="9647e-127">Therefore, to specify multiple prediction steps, you must use the **PredictTimeSeries** function.</span></span>  
  
8.  <span data-ttu-id="9647e-128">En el panel **modelo de minería de datos** , seleccione la columna del modelo de minería de datos **amount.**</span><span class="sxs-lookup"><span data-stu-id="9647e-128">In the **Mining Model** pane, select the mining model column, **Amount.**</span></span> <span data-ttu-id="9647e-129">Arrastre amount hasta el cuadro **criterios o argumentos** de la función **PredictTimeSeries** que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9647e-129">Drag Amount to the **Criteria/Arguments** box for the **PredictTimeSeries** function that you added earlier.</span></span>  
  
9. <span data-ttu-id="9647e-130">Haga clic en el cuadro **criterios y argumentos** y escriba una coma seguida de **5**, después del nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="9647e-130">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="9647e-131">El texto del cuadro **criterios o argumentos** ahora debería mostrar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9647e-131">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[Amount],5`  
  
10. <span data-ttu-id="9647e-132">En la columna **alias** , escriba `PredictAmount` .</span><span class="sxs-lookup"><span data-stu-id="9647e-132">In the **Alias** column, type `PredictAmount`.</span></span>  
  
11. <span data-ttu-id="9647e-133">Haga clic en la siguiente fila vacía de la columna **origen** y, a continuación, vuelva a seleccionar la **función de predicción** .</span><span class="sxs-lookup"><span data-stu-id="9647e-133">Click the next empty row in the **Source** column, and then select **Prediction Function** again.</span></span>  
  
12. <span data-ttu-id="9647e-134">En la columna **campo** , seleccione **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="9647e-134">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
13. <span data-ttu-id="9647e-135">En el panel **modelo de minería de datos** , seleccione la columna quantity y arrástrela al cuadro **criterios o argumentos** de la segunda función **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="9647e-135">In the **Mining Model** pane, select the column Quantity, and then drag it into the **Criteria/Arguments** box for the second **PredictTimeSeries** function.</span></span>  
  
14. <span data-ttu-id="9647e-136">Haga clic en el cuadro **criterios y argumentos** y escriba una coma seguida de **5**, después del nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="9647e-136">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="9647e-137">El texto del cuadro **criterios o argumentos** ahora debería mostrar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9647e-137">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[ Quantity],5`  
  
15. <span data-ttu-id="9647e-138">En la columna **alias** , escriba `PredictQuantity` .</span><span class="sxs-lookup"><span data-stu-id="9647e-138">In the **Alias** column, type `PredictQuantity`.</span></span>  
  
16. <span data-ttu-id="9647e-139">Haga clic en **cambiar a vista de resultado de consulta**.</span><span class="sxs-lookup"><span data-stu-id="9647e-139">Click **Switch to query result view**.</span></span>  
  
     <span data-ttu-id="9647e-140">Los resultados de la consulta se muestran en formato tabular.</span><span class="sxs-lookup"><span data-stu-id="9647e-140">The results of the query are displayed in tabular format.</span></span>  
  
 <span data-ttu-id="9647e-141">Recuerde que creó tres tipos diferentes de resultados en el generador de consultas, uno que usa los valores de una columna y dos que reciben los valores predichos de una función de predicción.</span><span class="sxs-lookup"><span data-stu-id="9647e-141">Remember that you created three different types of results in the query builder, one that uses values from a column, and two that get predicted values from a prediction function.</span></span> <span data-ttu-id="9647e-142">Por consiguiente, los resultados de la consulta contienen tres columnas independientes.</span><span class="sxs-lookup"><span data-stu-id="9647e-142">Therefore, the results of the query contain three separate columns.</span></span> <span data-ttu-id="9647e-143">La primera columna contiene la lista de combinaciones de productos y regiones.</span><span class="sxs-lookup"><span data-stu-id="9647e-143">The first column contains the list of product and region combinations.</span></span> <span data-ttu-id="9647e-144">La segunda y tercera columnas contienen cada una tabla anidada de los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="9647e-144">The second and third columns each contain a nested table of prediction results.</span></span> <span data-ttu-id="9647e-145">Cada tabla anidada contiene el incremento de tiempo y los valores predichos, como en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="9647e-145">Each nested table contains the time step and predicted values, such as the following table:</span></span>  
  
 <span data-ttu-id="9647e-146">Resultados de ejemplo (las cantidades se truncan a dos decimales):</span><span class="sxs-lookup"><span data-stu-id="9647e-146">Example results (amounts are truncated to two decimal places):</span></span>  
  
 <span data-ttu-id="9647e-147">**M200 Europe PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="9647e-147">**M200 Europe PredictAmount**</span></span>  
  
|<span data-ttu-id="9647e-148">$TIME</span><span class="sxs-lookup"><span data-stu-id="9647e-148">$TIME</span></span>|<span data-ttu-id="9647e-149">Importe</span><span class="sxs-lookup"><span data-stu-id="9647e-149">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="9647e-150">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-150">7/25/2008</span></span>|<span data-ttu-id="9647e-151">99978,00</span><span class="sxs-lookup"><span data-stu-id="9647e-151">99978.00</span></span>|  
|<span data-ttu-id="9647e-152">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-152">8/25/2008</span></span>|<span data-ttu-id="9647e-153">145575,07</span><span class="sxs-lookup"><span data-stu-id="9647e-153">145575.07</span></span>|  
|<span data-ttu-id="9647e-154">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-154">9/25/2008</span></span>|<span data-ttu-id="9647e-155">116835,19</span><span class="sxs-lookup"><span data-stu-id="9647e-155">116835.19</span></span>|  
|<span data-ttu-id="9647e-156">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-156">10/25/2008</span></span>|<span data-ttu-id="9647e-157">116537,38</span><span class="sxs-lookup"><span data-stu-id="9647e-157">116537.38</span></span>|  
|<span data-ttu-id="9647e-158">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-158">11/25/2008</span></span>|<span data-ttu-id="9647e-159">107760,55</span><span class="sxs-lookup"><span data-stu-id="9647e-159">107760.55</span></span>|  
  
 <span data-ttu-id="9647e-160">**M200 Europe PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="9647e-160">**M200 Europe PredictQuantity**</span></span>  
  
|<span data-ttu-id="9647e-161">$TIME</span><span class="sxs-lookup"><span data-stu-id="9647e-161">$TIME</span></span>|<span data-ttu-id="9647e-162">Cantidad</span><span class="sxs-lookup"><span data-stu-id="9647e-162">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="9647e-163">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-163">7/25/2008</span></span>|<span data-ttu-id="9647e-164">52</span><span class="sxs-lookup"><span data-stu-id="9647e-164">52</span></span>|  
|<span data-ttu-id="9647e-165">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-165">8/25/2008</span></span>|<span data-ttu-id="9647e-166">67</span><span class="sxs-lookup"><span data-stu-id="9647e-166">67</span></span>|  
|<span data-ttu-id="9647e-167">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-167">9/25/2008</span></span>|<span data-ttu-id="9647e-168">58</span><span class="sxs-lookup"><span data-stu-id="9647e-168">58</span></span>|  
|<span data-ttu-id="9647e-169">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-169">10/25/2008</span></span>|<span data-ttu-id="9647e-170">57</span><span class="sxs-lookup"><span data-stu-id="9647e-170">57</span></span>|  
|<span data-ttu-id="9647e-171">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-171">11/25/2008</span></span>|<span data-ttu-id="9647e-172">54</span><span class="sxs-lookup"><span data-stu-id="9647e-172">54</span></span>|  
  
 <span data-ttu-id="9647e-173">**M200 Norteamérica-PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="9647e-173">**M200 North America - PredictAmount**</span></span>  
  
|<span data-ttu-id="9647e-174">$TIME</span><span class="sxs-lookup"><span data-stu-id="9647e-174">$TIME</span></span>|<span data-ttu-id="9647e-175">Importe</span><span class="sxs-lookup"><span data-stu-id="9647e-175">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="9647e-176">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-176">7/25/2008</span></span>|<span data-ttu-id="9647e-177">348533,93</span><span class="sxs-lookup"><span data-stu-id="9647e-177">348533.93</span></span>|  
|<span data-ttu-id="9647e-178">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-178">8/25/2008</span></span>|<span data-ttu-id="9647e-179">340097,98</span><span class="sxs-lookup"><span data-stu-id="9647e-179">340097.98</span></span>|  
|<span data-ttu-id="9647e-180">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-180">9/25/2008</span></span>|<span data-ttu-id="9647e-181">257986,19</span><span class="sxs-lookup"><span data-stu-id="9647e-181">257986.19</span></span>|  
|<span data-ttu-id="9647e-182">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-182">10/25/2008</span></span>|<span data-ttu-id="9647e-183">374658,24</span><span class="sxs-lookup"><span data-stu-id="9647e-183">374658.24</span></span>|  
|<span data-ttu-id="9647e-184">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-184">11/25/2008</span></span>|<span data-ttu-id="9647e-185">379241,44</span><span class="sxs-lookup"><span data-stu-id="9647e-185">379241.44</span></span>|  
  
 <span data-ttu-id="9647e-186">**M200 Norteamérica-PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="9647e-186">**M200 North America - PredictQuantity**</span></span>  
  
|<span data-ttu-id="9647e-187">$TIME</span><span class="sxs-lookup"><span data-stu-id="9647e-187">$TIME</span></span>|<span data-ttu-id="9647e-188">Cantidad</span><span class="sxs-lookup"><span data-stu-id="9647e-188">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="9647e-189">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-189">7/25/2008</span></span>|<span data-ttu-id="9647e-190">272</span><span class="sxs-lookup"><span data-stu-id="9647e-190">272</span></span>|  
|<span data-ttu-id="9647e-191">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-191">8/25/2008</span></span>|<span data-ttu-id="9647e-192">152</span><span class="sxs-lookup"><span data-stu-id="9647e-192">152</span></span>|  
|<span data-ttu-id="9647e-193">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-193">9/25/2008</span></span>|<span data-ttu-id="9647e-194">250</span><span class="sxs-lookup"><span data-stu-id="9647e-194">250</span></span>|  
|<span data-ttu-id="9647e-195">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-195">10/25/2008</span></span>|<span data-ttu-id="9647e-196">181</span><span class="sxs-lookup"><span data-stu-id="9647e-196">181</span></span>|  
|<span data-ttu-id="9647e-197">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="9647e-197">11/25/2008</span></span>|<span data-ttu-id="9647e-198">290</span><span class="sxs-lookup"><span data-stu-id="9647e-198">290</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="9647e-199">Las fechas usadas en la base de datos de ejemplo han cambiado en esta versión.</span><span class="sxs-lookup"><span data-stu-id="9647e-199">The dates that are used in the sample database have changed for this release.</span></span> <span data-ttu-id="9647e-200">Si está usando una versión anterior de los datos de ejemplo, podría ver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="9647e-200">If you are using an earlier version of the sample data, you might see different results.</span></span>  
  
## <a name="saving-the-prediction-results"></a><span data-ttu-id="9647e-201">Guardar los resultados de una predicción</span><span class="sxs-lookup"><span data-stu-id="9647e-201">Saving the Prediction Results</span></span>  
 <span data-ttu-id="9647e-202">Dispone de varias opciones distintas para usar los resultado de la predicción.</span><span class="sxs-lookup"><span data-stu-id="9647e-202">You have several different options for using the prediction results.</span></span> <span data-ttu-id="9647e-203">Puede simplificar los resultados, copiar los datos desde la vista Resultados y pegarlos en una hoja de cálculo de Excel o en otro archivo.</span><span class="sxs-lookup"><span data-stu-id="9647e-203">You can flatten the results, copy the data from the Results view, and paste it into an Excel worksheet or other file.</span></span>  
  
 <span data-ttu-id="9647e-204">Para simplificar el proceso de guardar los resultados, el Diseñador de minería de datos también proporciona la capacidad de guardar los datos en una vista de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9647e-204">To simplify the process of saving results, Data Mining Designer also provides the ability to save the data to a data source view.</span></span> <span data-ttu-id="9647e-205">La funcionalidad de guardar los resultados en una vista del origen de datos solo está disponible en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9647e-205">The functionality for saving results to a data source view is available only in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9647e-206">Los resultados solo se puede almacenar en un formato plano.</span><span class="sxs-lookup"><span data-stu-id="9647e-206">The results can only be stored in a flattened format.</span></span>  
  
#### <a name="to-flatten-the-results-in-the-results-pane"></a><span data-ttu-id="9647e-207">Para quitar información de estructura jerárquica de los resultados en el panel Resultados</span><span class="sxs-lookup"><span data-stu-id="9647e-207">To flatten the results in the Results pane</span></span>  
  
1.  <span data-ttu-id="9647e-208">En el Generador de consultas de predicción, haga clic en **cambiar a vista de diseño de consulta**.</span><span class="sxs-lookup"><span data-stu-id="9647e-208">In the Prediction Query Builder, click **Switch to query design view**.</span></span>  
  
     <span data-ttu-id="9647e-209">La vista cambia para permitir la modificación manual del texto de las consultas DMX.</span><span class="sxs-lookup"><span data-stu-id="9647e-209">The view changes to allow manual editing of the DMX query text.</span></span>  
  
2.  <span data-ttu-id="9647e-210">Escriba la palabra clave `FLATTENED` después de la palabra clave `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="9647e-210">Type the `FLATTENED` keyword after the `SELECT` keyword.</span></span> <span data-ttu-id="9647e-211">El texto completo de la consulta debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="9647e-211">The complete query text should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    ```  
  
3.  <span data-ttu-id="9647e-212">Opcionalmente, puede escribir una cláusula para restringir los resultados, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9647e-212">Optionally, you can type a clause to restrict the results, such as the following example:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    WHERE [Forecasting].[Model Region] = 'M200 North America'   
    OR [Forecasting].[Model Region] = 'M200 Europe'  
  
    ```  
  
4.  <span data-ttu-id="9647e-213">Haga clic en **cambiar a vista de resultado de consulta**.</span><span class="sxs-lookup"><span data-stu-id="9647e-213">Click **Switch to query result view**.</span></span>  
  
#### <a name="to-export-prediction-query-results"></a><span data-ttu-id="9647e-214">Para exportar los resultados de una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="9647e-214">To export prediction query results</span></span>  
  
1.  <span data-ttu-id="9647e-215">Haga clic en **Guardar resultados**de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9647e-215">Click **Save query results**.</span></span>  
  
2.  <span data-ttu-id="9647e-216">En el cuadro de diálogo **Guardar resultado de consulta de minería de datos** , en **origen de datos**, seleccione [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9647e-216">In the **Save Data Mining Query Result** dialog box, for **Data Source**, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="9647e-217">También puede crear un origen de datos si desea guardar los datos en una base de datos relacional diferente.</span><span class="sxs-lookup"><span data-stu-id="9647e-217">You can also create a data source if you want to save the data to a different relational database.</span></span>  
  
3.  <span data-ttu-id="9647e-218">En la columna **nombre de tabla** , escriba un nuevo nombre de tabla temporal, como **predicciones de prueba**.</span><span class="sxs-lookup"><span data-stu-id="9647e-218">In the **Table Name** column, type a new temporary table name, such as **Test Predictions**.</span></span>  
  
4.  <span data-ttu-id="9647e-219">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="9647e-219">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9647e-220">Para ver la tabla que creó, cree una conexión al motor de base de datos de la instancia donde guardó los datos y cree una consulta.</span><span class="sxs-lookup"><span data-stu-id="9647e-220">To view the table that you created, create a connection to the database engine of the instance where you saved the data, and create a query.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="9647e-221">Conclusión</span><span class="sxs-lookup"><span data-stu-id="9647e-221">Conclusion</span></span>  
 <span data-ttu-id="9647e-222">Ha aprendido a crear un modelo de serie temporal básico, a interpretar los pronósticos y a crear predicciones.</span><span class="sxs-lookup"><span data-stu-id="9647e-222">You have learned how to build a basic time series model, interpret the forecasts, and create predictions.</span></span>  
  
 <span data-ttu-id="9647e-223">Las tareas restantes de este tutorial son opcionales y describen las predicciones de serie temporal avanzadas.</span><span class="sxs-lookup"><span data-stu-id="9647e-223">The remaining tasks in this tutorial are optional, and describe advanced time series predictions.</span></span> <span data-ttu-id="9647e-224">Si decide continuar, aprenderá a agregar nuevos datos al modelo y a crear predicciones acerca de la serie extendida.</span><span class="sxs-lookup"><span data-stu-id="9647e-224">If you decide to go on, you will learn how to add new data to your model and create predictions on the extended series.</span></span> <span data-ttu-id="9647e-225">También aprenderá a realizar una predicción cruzada, mediante la tendencia del modelo, pero reemplazará los datos con una nueva serie de datos.</span><span class="sxs-lookup"><span data-stu-id="9647e-225">You will also learn how to perform cross-prediction, by using the trend in the model but replacing the data with a new series of data.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9647e-226">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="9647e-226">Next Lesson</span></span>  
 [<span data-ttu-id="9647e-227">Predicciones de serie temporal avanzadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="9647e-227">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="9647e-228">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9647e-228">See Also</span></span>  
 [<span data-ttu-id="9647e-229">Ejemplos de consultas de modelos de serie temporal</span><span class="sxs-lookup"><span data-stu-id="9647e-229">Time Series Model Query Examples</span></span>](../../2014/analysis-services/data-mining/time-series-model-query-examples.md)  
  
  
