---
title: 'Lección 5: ampliar el modelo de serie temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7aad4946-c903-4e25-88b9-b087c20cb67d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2716e985897f8115d189d9410b7cdb13fb1af291
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670713"
---
# <a name="lesson-5-extending-the-time-series-model"></a><span data-ttu-id="d689c-102">Lección 5: Extensión del modelo de serie temporal</span><span class="sxs-lookup"><span data-stu-id="d689c-102">Lesson 5: Extending the Time Series Model</span></span>
  <span data-ttu-id="d689c-103">En [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, es posible agregar datos nuevos a un modelo de serie temporal e incorporarlos automáticamente al mismo.</span><span class="sxs-lookup"><span data-stu-id="d689c-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, you can add new data to a time series model and automatically incorporate the new data into the model.</span></span> <span data-ttu-id="d689c-104">Los nuevos datos se agregan a un modelo de minería de datos de serie temporal de una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d689c-104">You add new data to a time series mining model in one of two ways:</span></span>  
  
-   <span data-ttu-id="d689c-105">Usando una instrucción PREDICTION JOIN  para unir los datos de un origen externo a los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="d689c-105">Use a PREDICTION JOIN to join data in an external source to the training data.</span></span>  
  
-   <span data-ttu-id="d689c-106">Usando una consulta de predicción singleton para proporcionar los datos segmento a segmento.</span><span class="sxs-lookup"><span data-stu-id="d689c-106">Use a singleton prediction query to provide data one slice at a time.</span></span>  
  
 <span data-ttu-id="d689c-107">Por ejemplo, suponga que entrenó el modelo de minería de datos con los datos de ventas existentes hace algunos meses.</span><span class="sxs-lookup"><span data-stu-id="d689c-107">For example, assume that you trained the mining model on existing sales data some months ago.</span></span> <span data-ttu-id="d689c-108">Al conseguir ventas nuevas, podría desear actualizar las predicciones de ventas para incorporar los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d689c-108">When you get new sales, you might want to update the sales predictions to incorporate the new data.</span></span> <span data-ttu-id="d689c-109">Puede hacer esto en un paso, proporcionando las nuevas cifras de ventas como datos de entrada y generando predicciones nuevas basadas en el conjunto de datos compuesto.</span><span class="sxs-lookup"><span data-stu-id="d689c-109">You can do this in one step, by supplying the new sales figures as input data and generating new predictions based on the composite data set.</span></span>  
  
## <a name="making-predictions-with-extend_model_cases"></a><span data-ttu-id="d689c-110">Realizar predicciones con EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d689c-110">Making Predictions with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="d689c-111">A continuación se muestran ejemplos genéricos de una predicción de serie temporal que usa EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="d689c-111">The following are generic examples of a time series prediction using EXTEND_MODEL_CASES.</span></span> <span data-ttu-id="d689c-112">El primer ejemplo permite especificar el número de predicciones a partir del último estadio temporal del modelo original:</span><span class="sxs-lookup"><span data-stu-id="d689c-112">The first example enables you to specify the number of predictions starting from the last time step of the original model:</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>]  
```  
  
 <span data-ttu-id="d689c-113">El segundo ejemplo permite especificar el estadio temporal donde las predicciones deberían iniciarse y donde deberían finalizar.</span><span class="sxs-lookup"><span data-stu-id="d689c-113">The second example enables you to specify the time step where predictions should start, and where they should end.</span></span> <span data-ttu-id="d689c-114">Esta opción es importante al extender los casos del modelo porque, de forma predeterminada, los estadios temporales que se usan para las consultas de predicción siempre se inician al final de la serie original.</span><span class="sxs-lookup"><span data-stu-id="d689c-114">This option is important when you extend the model cases because, by default, the time steps used for prediction queries always start at the end of the original series.</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n-start, n-end, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>}  
```  
  
 <span data-ttu-id="d689c-115">En este tutorial, creará ambos tipos de consultas.</span><span class="sxs-lookup"><span data-stu-id="d689c-115">In this tutorial, you will create both kinds of queries.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-on-a-time-series-model"></a><span data-ttu-id="d689c-116">Para crear una consulta de predicción singleton en un modelo de serie temporal</span><span class="sxs-lookup"><span data-stu-id="d689c-116">To create a singleton prediction query on a time series model</span></span>  
  
1.  <span data-ttu-id="d689c-117">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="d689c-117">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="d689c-118">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="d689c-118">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="d689c-119">Copie el ejemplo genérico de la instrucción singleton en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="d689c-119">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="d689c-120">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-120">Replace the following:</span></span>  
  
    ```  
    SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
    ```  
  
     <span data-ttu-id="d689c-121">por:</span><span class="sxs-lookup"><span data-stu-id="d689c-121">with:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    ```  
  
     <span data-ttu-id="d689c-122">La primera línea recupera un valor del modelo que identifica la serie.</span><span class="sxs-lookup"><span data-stu-id="d689c-122">The first line retrieves a value from the model that identifies the series.</span></span>  
  
     <span data-ttu-id="d689c-123">La segunda línea contiene la función de predicción, que obtiene seis predicciones para Quantity.</span><span class="sxs-lookup"><span data-stu-id="d689c-123">The second line contains the prediction function, which gets 6 predictions for Quantity.</span></span> <span data-ttu-id="d689c-124">Se asigna un alias, `PredictQty`, a la columna del resultado de la predicción para que los resultados se entiendan más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="d689c-124">An alias, `PredictQty`, is assigned to the prediction result column to make it easier to understand the results.</span></span>  
  
4.  <span data-ttu-id="d689c-125">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-125">Replace the following:</span></span>  
  
    ```  
    FROM <mining model>  
    ```  
  
     <span data-ttu-id="d689c-126">por:</span><span class="sxs-lookup"><span data-stu-id="d689c-126">with:</span></span>  
  
    ```  
    FROM [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="d689c-127">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-127">Replace the following:</span></span>  
  
    ```  
    PREDICTION JOIN <source query>  
    ```  
  
     <span data-ttu-id="d689c-128">por:</span><span class="sxs-lookup"><span data-stu-id="d689c-128">with:</span></span>  
  
    ```  
    NATURAL PREDICTION JOIN   
    (  
       SELECT 1 AS [Reporting Date],  
       '10' AS [Quantity],  
       'M200 Europe' AS [Model Region]  
       UNION SELECT  
       2 AS [Reporting Date],  
       15 AS [Quantity]),  
       'M200 Europe' AS [Model Region]  
    ) AS t  
    ```  
  
6.  <span data-ttu-id="d689c-129">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-129">Replace the following:</span></span>  
  
    ```  
    [WHERE <criteria>]  
    ```  
  
     <span data-ttu-id="d689c-130">por:</span><span class="sxs-lookup"><span data-stu-id="d689c-130">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="d689c-131">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-131">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    FROM  
       [Forecasting_MIXED]  
    NATURAL PREDICTION JOIN   
       SELECT 1 AS [ReportingDate],  
      '10' AS [Quantity],  
      'M200 Europe' AS [ModelRegion]  
    UNION SELECT  
      2 AS [ReportingDate],  
      15 AS [Quantity]),  
      'M200 Europe' AS [ModelRegion]  
    ) AS t  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
7.  <span data-ttu-id="d689c-132">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="d689c-132">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="d689c-133">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Singleton_TimeSeries_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="d689c-133">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_TimeSeries_Query.dmx`.</span></span>  
  
9. <span data-ttu-id="d689c-134">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="d689c-134">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="d689c-135">La consulta devuelve predicciones de la cantidad de ventas de la bicicleta M200 en las regiones de Europa y Pacífico.</span><span class="sxs-lookup"><span data-stu-id="d689c-135">The query returns predictions of sales quantity for the M200 bicycle in the Europe and Pacific regions.</span></span>  
  
## <a name="understanding-prediction-start-with-extend_model_cases"></a><span data-ttu-id="d689c-136">Descripción del inicio de la predicción con EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d689c-136">Understanding Prediction Start with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="d689c-137">Ahora que ha creado predicciones basadas en el modelo original, puede comparar con datos nuevos los resultados para ver cómo afecta a las predicciones la actualización de los datos de ventas.</span><span class="sxs-lookup"><span data-stu-id="d689c-137">Now that you have created predictions based on the original model, and with new data, you can compare the results to see how updating the sales data affects the predictions.</span></span> <span data-ttu-id="d689c-138">Antes, revise el código recién creado y observe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-138">Before you do so, review the code that you just created, and notice the following:</span></span>  
  
-   <span data-ttu-id="d689c-139">Proporcionó datos nuevos solo para la región de Europa.</span><span class="sxs-lookup"><span data-stu-id="d689c-139">You supplied new data for only the Europe region.</span></span>  
  
-   <span data-ttu-id="d689c-140">Proporcionó solo datos nuevos para dos meses.</span><span class="sxs-lookup"><span data-stu-id="d689c-140">You supplied only two months' worth of new data.</span></span>  
  
 <span data-ttu-id="d689c-141">La tabla siguiente muestra cómo los valores nuevos proporcionados para M200 en Europa afectan a las predicciones.</span><span class="sxs-lookup"><span data-stu-id="d689c-141">The following table shows how the new values supplied for M200 Europe affect predictions.</span></span> <span data-ttu-id="d689c-142">No proporcionó ningún dato nuevo para el producto M200 en la región de Pacífico, pero esta serie se presenta para poder comparar:</span><span class="sxs-lookup"><span data-stu-id="d689c-142">You did not provide any new data for the M200 product in the Pacific region, but this series is presented for comparison:</span></span>  
  
 <span data-ttu-id="d689c-143">**Producto y región: M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="d689c-143">**Product and Region: M200 Europe**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="d689c-144">Modelo existente (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="d689c-144">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="d689c-145">Modelo con datos de ventas actualizados (`PredictTimeSeries` con `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="d689c-145">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="d689c-146">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-146">M200 Europe</span></span>|<span data-ttu-id="d689c-147">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-147">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-148">77</span><span class="sxs-lookup"><span data-stu-id="d689c-148">77</span></span>|<span data-ttu-id="d689c-149">10</span><span class="sxs-lookup"><span data-stu-id="d689c-149">10</span></span>|  
|<span data-ttu-id="d689c-150">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-150">M200 Europe</span></span>|<span data-ttu-id="d689c-151">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-151">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-152">64</span><span class="sxs-lookup"><span data-stu-id="d689c-152">64</span></span>|<span data-ttu-id="d689c-153">15</span><span class="sxs-lookup"><span data-stu-id="d689c-153">15</span></span>|  
|<span data-ttu-id="d689c-154">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-154">M200 Europe</span></span>|<span data-ttu-id="d689c-155">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-155">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-156">59</span><span class="sxs-lookup"><span data-stu-id="d689c-156">59</span></span>|<span data-ttu-id="d689c-157">72</span><span class="sxs-lookup"><span data-stu-id="d689c-157">72</span></span>|  
|<span data-ttu-id="d689c-158">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-158">M200 Europe</span></span>|<span data-ttu-id="d689c-159">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-159">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-160">56</span><span class="sxs-lookup"><span data-stu-id="d689c-160">56</span></span>|<span data-ttu-id="d689c-161">69</span><span class="sxs-lookup"><span data-stu-id="d689c-161">69</span></span>|  
|<span data-ttu-id="d689c-162">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-162">M200 Europe</span></span>|<span data-ttu-id="d689c-163">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-163">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-164">56</span><span class="sxs-lookup"><span data-stu-id="d689c-164">56</span></span>|<span data-ttu-id="d689c-165">68</span><span class="sxs-lookup"><span data-stu-id="d689c-165">68</span></span>|  
|<span data-ttu-id="d689c-166">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-166">M200 Europe</span></span>|<span data-ttu-id="d689c-167">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-167">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-168">74</span><span class="sxs-lookup"><span data-stu-id="d689c-168">74</span></span>|<span data-ttu-id="d689c-169">89</span><span class="sxs-lookup"><span data-stu-id="d689c-169">89</span></span>|  
  
 <span data-ttu-id="d689c-170">**Producto y región: M200 Pacific**</span><span class="sxs-lookup"><span data-stu-id="d689c-170">**Product and Region: M200 Pacific**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="d689c-171">Modelo existente (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="d689c-171">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="d689c-172">Modelo con datos de ventas actualizados (`PredictTimeSeries` con `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="d689c-172">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="d689c-173">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d689c-173">M200 Pacific</span></span>|<span data-ttu-id="d689c-174">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-174">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-175">41</span><span class="sxs-lookup"><span data-stu-id="d689c-175">41</span></span>|<span data-ttu-id="d689c-176">41</span><span class="sxs-lookup"><span data-stu-id="d689c-176">41</span></span>|  
|<span data-ttu-id="d689c-177">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d689c-177">M200 Pacific</span></span>|<span data-ttu-id="d689c-178">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-178">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-179">44</span><span class="sxs-lookup"><span data-stu-id="d689c-179">44</span></span>|<span data-ttu-id="d689c-180">44</span><span class="sxs-lookup"><span data-stu-id="d689c-180">44</span></span>|  
|<span data-ttu-id="d689c-181">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d689c-181">M200 Pacific</span></span>|<span data-ttu-id="d689c-182">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-182">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-183">38</span><span class="sxs-lookup"><span data-stu-id="d689c-183">38</span></span>|<span data-ttu-id="d689c-184">38</span><span class="sxs-lookup"><span data-stu-id="d689c-184">38</span></span>|  
|<span data-ttu-id="d689c-185">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d689c-185">M200 Pacific</span></span>|<span data-ttu-id="d689c-186">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-186">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-187">41</span><span class="sxs-lookup"><span data-stu-id="d689c-187">41</span></span>|<span data-ttu-id="d689c-188">41</span><span class="sxs-lookup"><span data-stu-id="d689c-188">41</span></span>|  
|<span data-ttu-id="d689c-189">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d689c-189">M200 Pacific</span></span>|<span data-ttu-id="d689c-190">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-190">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-191">36</span><span class="sxs-lookup"><span data-stu-id="d689c-191">36</span></span>|<span data-ttu-id="d689c-192">36</span><span class="sxs-lookup"><span data-stu-id="d689c-192">36</span></span>|  
|<span data-ttu-id="d689c-193">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d689c-193">M200 Pacific</span></span>|<span data-ttu-id="d689c-194">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-194">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-195">39</span><span class="sxs-lookup"><span data-stu-id="d689c-195">39</span></span>|<span data-ttu-id="d689c-196">39</span><span class="sxs-lookup"><span data-stu-id="d689c-196">39</span></span>|  
  
 <span data-ttu-id="d689c-197">A raíz de estos resultados, puede observar dos cuestiones:</span><span class="sxs-lookup"><span data-stu-id="d689c-197">From these results, you can see two things:</span></span>  
  
-   <span data-ttu-id="d689c-198">Las primeras dos predicciones para la serie M200 Europa son exactamente iguales que los nuevos datos que proporcionó.</span><span class="sxs-lookup"><span data-stu-id="d689c-198">The first two predictions for the M200 Europe series are exactly the same as the new data you supplied.</span></span> <span data-ttu-id="d689c-199">Por diseño, Analysis Services devuelve los nuevos datos reales en lugar de realizar una predicción.</span><span class="sxs-lookup"><span data-stu-id="d689c-199">By design, Analysis Services returns the actual new data points instead of making a prediction.</span></span> <span data-ttu-id="d689c-200">Eso se debe a que al extender los casos del modelo, los pasos temporales utilizados para las consultas de predicción siempre se inician al final de la serie original.</span><span class="sxs-lookup"><span data-stu-id="d689c-200">That is because when you extend the model cases, the time steps used for prediction queries always start at the end of the original series.</span></span> <span data-ttu-id="d689c-201">Por tanto, si agrega dos datos nuevos, las dos primeras predicciones devueltas se superponen a los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d689c-201">Therefore, if you add two new data points, the first two predictions returned overlap with the new data.</span></span>  
  
-   <span data-ttu-id="d689c-202">Una vez agotados todos los nuevos datos, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] realiza predicciones basadas en el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="d689c-202">After all the new data points are used up, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] makes predictions based on the updated model.</span></span> <span data-ttu-id="d689c-203">Por consiguiente, a partir de septiembre de 2005, puede ver la diferencia entre las predicciones para M200 Europa del modelo original, en la columna de la izquierda, y el modelo que utiliza EXTEND_MODEL_CASES, en la columna de la derecha.</span><span class="sxs-lookup"><span data-stu-id="d689c-203">Therefore, starting in September 2005, you can see the difference between predictions for M200 Europe from the original model, in the left-hand column, and the model that uses EXTEND_MODEL_CASES, in the right-hand column.</span></span> <span data-ttu-id="d689c-204">Las predicciones son diferentes porque el modelo se ha actualizado con datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d689c-204">The predictions are different because the model has been updated with the new data.</span></span>  
  
## <a name="using-start-and-end-time-steps-to-control-predictions"></a><span data-ttu-id="d689c-205">Usar pasos temporales de inicio y de fin para controlar las predicciones</span><span class="sxs-lookup"><span data-stu-id="d689c-205">Using Start and End Time Steps to Control Predictions</span></span>  
 <span data-ttu-id="d689c-206">Al extender un modelo, los datos nuevos siempre se asocian al final de la serie.</span><span class="sxs-lookup"><span data-stu-id="d689c-206">When you extend a model, the new data is always attached to the end of the series.</span></span> <span data-ttu-id="d689c-207">Sin embargo, para la predicción, los intervalos de tiempo usados en las consultas de predicción se inician al final de la serie original.</span><span class="sxs-lookup"><span data-stu-id="d689c-207">However, for the purpose of prediction, the time slices used for prediction queries start at the end of the original series.</span></span> <span data-ttu-id="d689c-208">Si únicamente desea obtener las predicciones nuevas al agregar datos nuevos, debe especificar el punto inicial como un número de intervalos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d689c-208">If you want to obtain only the new predictions when you add the new data, you must specify the starting point as a number of time slices.</span></span> <span data-ttu-id="d689c-209">Por ejemplo, si va a agregar dos datos nuevos y desea realizar cuatro predicciones nuevas, haría lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d689c-209">For example, if you are adding two new data points and want to make four new predictions, you would do the following:</span></span>  
  
-   <span data-ttu-id="d689c-210">Cree una instrucción PREDICTION JOIN en un modelo de serie temporal y especifique los datos nuevos correspondientes a dos meses.</span><span class="sxs-lookup"><span data-stu-id="d689c-210">Create a PREDICTION JOIN on a time series model, and specify two months of new data.</span></span>  
  
-   <span data-ttu-id="d689c-211">Solicite predicciones para cuatro intervalos de tiempo, donde el punto inicial es el intervalo de tiempo 3 y el punto final es el intervalo de tiempo 6.</span><span class="sxs-lookup"><span data-stu-id="d689c-211">Request predictions for four time slices, where the starting point is 3, and the ending point is time slice 6.</span></span>  
  
 <span data-ttu-id="d689c-212">En otras palabras, si los datos nuevos contienen n intervalos de tiempo y solicita predicciones para los pasos temporales 1 a n, las predicciones coincidirán con el mismo período que los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d689c-212">In other words, if your new data contains n time slices, and you request predictions for time steps 1 through n, the predictions will coincide with the same period as the new data.</span></span> <span data-ttu-id="d689c-213">Para obtener nuevas predicciones de un período de tiempo que no cubren los datos, debe iniciar las predicciones en el intervalo de tiempo n+1 tras la nueva serie de datos o asegurarse de que solicita intervalos de tiempo adicionales.</span><span class="sxs-lookup"><span data-stu-id="d689c-213">To get new predictions for a time periods not covered by your data, you must either start predictions at the time slice n+1 after the new data series, or make sure that you request additional time slices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d689c-214">Si agrega nuevos datos, no puede realizar predicciones históricas.</span><span class="sxs-lookup"><span data-stu-id="d689c-214">You cannot make historical predictions when you add new data.</span></span>  
  
 <span data-ttu-id="d689c-215">En el ejemplo siguiente se muestra la instrucción DMX que permite obtener solo las predicciones nuevas para las dos series del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d689c-215">The following example shows the DMX statement that lets you get only the new predictions for the two series in the previous example.</span></span>  
  
```  
SELECT [Model Region],  
PredictTimeSeries([Quantity],3,6, EXTEND_MODEL_CASES) AS PredictQty  
FROM  
   [Forecasting_MIXED]  
NATURAL PREDICTION JOIN   
   SELECT 1 AS [ReportingDate],  
  '10' AS [Quantity],  
  'M200 Europe' AS [ModelRegion]  
UNION SELECT  
  2 AS [ReportingDate],  
  15 AS [Quantity]),  
  'M200 Europe' AS [ModelRegion]  
) AS t  
WHERE [ModelRegion] = 'M200 Europe'  
```  
  
 <span data-ttu-id="d689c-216">Los resultados de la predicción se inician en el intervalo de tiempo 3, que está después de los datos nuevos para 2 meses que proporcionó.</span><span class="sxs-lookup"><span data-stu-id="d689c-216">The prediction results start at time slice 3, which is after the 2 months of new data that you supplied.</span></span>  
  
 <span data-ttu-id="d689c-217">**Producto y región: M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="d689c-217">**Product and Region: M200 Europe**</span></span>  
  
 <span data-ttu-id="d689c-218">Modelo con datos actualizados (PredictTimeSeries con EXTEND_MODEL_CASES)</span><span class="sxs-lookup"><span data-stu-id="d689c-218">Model with updated data (PredictTimeSeries with EXTEND_MODEL_CASES)</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="d689c-219">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-219">M200 Europe</span></span>|<span data-ttu-id="d689c-220">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-220">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-221">72</span><span class="sxs-lookup"><span data-stu-id="d689c-221">72</span></span>|  
|<span data-ttu-id="d689c-222">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-222">M200 Europe</span></span>|<span data-ttu-id="d689c-223">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-223">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-224">69</span><span class="sxs-lookup"><span data-stu-id="d689c-224">69</span></span>|  
|<span data-ttu-id="d689c-225">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-225">M200 Europe</span></span>|<span data-ttu-id="d689c-226">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-226">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-227">68</span><span class="sxs-lookup"><span data-stu-id="d689c-227">68</span></span>|  
|<span data-ttu-id="d689c-228">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="d689c-228">M200 Europe</span></span>|<span data-ttu-id="d689c-229">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d689c-229">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d689c-230">89</span><span class="sxs-lookup"><span data-stu-id="d689c-230">89</span></span>|  
  
## <a name="making-predictions-with-replace_model_cases"></a><span data-ttu-id="d689c-231">Realizar predicciones con REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d689c-231">Making Predictions with REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="d689c-232">La sustitución de los casos del modelo resulta útil si desear entrenar un modelo en un conjunto de casos y, a continuación, aplicar ese modelo a una serie de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="d689c-232">Replacing the model cases is useful when you want to train a model on one set of cases and then apply that model to a different data series.</span></span> <span data-ttu-id="d689c-233">Un tutorial detallado de este escenario se presenta en la [Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d689c-233">A detailed walkthrough of this scenario is presented in [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d689c-234">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d689c-234">See Also</span></span>  
 <span data-ttu-id="d689c-235">[Ejemplos de consultas de modelos de serie temporal](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="d689c-235">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="d689c-236">PredictTimeSeries &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="d689c-236">PredictTimeSeries &#40;DMX&#41;</span></span>](/sql/dmx/predicttimeseries-dmx)  
  
  
