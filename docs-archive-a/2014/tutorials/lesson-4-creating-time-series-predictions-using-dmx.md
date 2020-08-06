---
title: 'Lección 4: crear predicciones de serie temporal con DMX | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6b883e43-209d-489a-8dc3-9349f88acae8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 772e5f5f71ca82dd18fec48730522c80e907414f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743706"
---
# <a name="lesson-4-creating-time-series-predictions-using-dmx"></a><span data-ttu-id="b4d25-102">Lección 4: Creación de predicciones de serie temporal con DMX</span><span class="sxs-lookup"><span data-stu-id="b4d25-102">Lesson 4: Creating Time Series Predictions Using DMX</span></span>
  <span data-ttu-id="b4d25-103">En esta lección y en la lección siguiente, utilizará extensiones de minería de datos (DMX) para crear distintos tipos de predicciones en función de los modelos de serie temporal creados en la [Lección 1: crear un modelo de minería de datos de serie temporal y una estructura](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) de minería de datos y la [Lección 2: agregar modelos de minería de datos a la estructura de minería](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)de datos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b4d25-103">In this lesson and the following lesson, you will use Data Mining Extensions (DMX) to create different types of predictions based on the time series models that you created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) and [Lesson 2: Adding Mining Models to the Time Series Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span></span>  
  
 <span data-ttu-id="b4d25-104">Con un modelo de serie temporal, tiene muchas opciones para realizar predicciones:</span><span class="sxs-lookup"><span data-stu-id="b4d25-104">With a time series model, you have many options for making predictions:</span></span>  
  
-   <span data-ttu-id="b4d25-105">Usar los patrones y datos existentes en el modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="b4d25-105">Use the existing patterns and data in the mining model</span></span>  
  
-   <span data-ttu-id="b4d25-106">Usar los patrones existentes en el modelo de minería de datos pero suministrar datos nuevos</span><span class="sxs-lookup"><span data-stu-id="b4d25-106">Use the existing patterns in the mining model but supply new data</span></span>  
  
-   <span data-ttu-id="b4d25-107">Agregue datos nuevos al modelo o actualice el modelo.</span><span class="sxs-lookup"><span data-stu-id="b4d25-107">Add new data to the model or update the model.</span></span>  
  
 <span data-ttu-id="b4d25-108">A continuación se resume la sintaxis para realizar estos tipos de predicción:</span><span class="sxs-lookup"><span data-stu-id="b4d25-108">The syntax for making these prediction types is summarized below:</span></span>  
  
 <span data-ttu-id="b4d25-109">Predicción de serie temporal predeterminada</span><span class="sxs-lookup"><span data-stu-id="b4d25-109">Default time series prediction</span></span>  
 <span data-ttu-id="b4d25-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) para devolver el número especificado de predicciones del modelo de minería de datos entrenado.</span><span class="sxs-lookup"><span data-stu-id="b4d25-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) to return the specified number of predictions from the trained mining model.</span></span>  
  
 <span data-ttu-id="b4d25-111">Por ejemplo, consulte [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) o [ejemplos de consultas de modelos de serie temporal](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="b4d25-111">For example, see [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) or [Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="b4d25-112">EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="b4d25-112">EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="b4d25-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) con el argumento EXTEND_MODEL_CASES para agregar nuevos datos, ampliar la serie y crear predicciones basadas en el modelo de minería de datos actualizado.</span><span class="sxs-lookup"><span data-stu-id="b4d25-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the EXTEND_MODEL_CASES argument to add new data, extend the series, and create predictions based on the updated mining model.</span></span>  
  
 <span data-ttu-id="b4d25-114">Este tutorial contiene un ejemplo de cómo utilizar EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="b4d25-114">This tutorial contains an example of how to use EXTEND_MODEL_CASES.</span></span>  
  
 <span data-ttu-id="b4d25-115">REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="b4d25-115">REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="b4d25-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) con el argumento REPLACE_MODEL_CASES para reemplazar los datos originales por una nueva serie de datos y, a continuación, cree predicciones basadas en la aplicación de los patrones del modelo de minería de datos a la nueva serie de datos.</span><span class="sxs-lookup"><span data-stu-id="b4d25-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the REPLACE_MODEL_CASES argument to replace the original data with a new data series, and then create predictions based on applying the patterns in the mining model to the new data series.</span></span>  
  
 <span data-ttu-id="b4d25-117">Para obtener un ejemplo de cómo usar REPLACE_MODEL_CASES, vea [Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b4d25-117">For an example of how to use REPLACE_MODEL_CASES, see [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="b4d25-118">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="b4d25-118">Lesson Tasks</span></span>  
 <span data-ttu-id="b4d25-119">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4d25-119">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="b4d25-120">Crear una consulta para obtener las predicciones predeterminadas según los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="b4d25-120">Create a query to get the default predictions based on existing data.</span></span>  
  
 <span data-ttu-id="b4d25-121">En la lección siguiente, realizará las tareas relacionadas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4d25-121">In the following lesson you will perform the following related tasks:</span></span>  
  
-   <span data-ttu-id="b4d25-122">Crear una consulta para proporcionar datos nuevos y actualizar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="b4d25-122">Create a query to supply new data and get updated predictions.</span></span>  
  
 <span data-ttu-id="b4d25-123">Además de crear consultas manualmente utilizando DMX, también puede crear predicciones con el generador de consultas de predicción de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4d25-123">In addition to creating queries manually by using DMX, you can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="simple-time-series-prediction-query"></a><span data-ttu-id="b4d25-124">Consulta simple de predicción de serie temporal</span><span class="sxs-lookup"><span data-stu-id="b4d25-124">Simple Time Series Prediction Query</span></span>  
 <span data-ttu-id="b4d25-125">El primer paso es utilizar la instrucción `SELECT FROM` junto con la función `PredictTimeSeries` para crear predicciones de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b4d25-125">The first step is to use the `SELECT FROM` statement together with the `PredictTimeSeries` function to create time series predictions.</span></span> <span data-ttu-id="b4d25-126">Los modelos de serie temporal admiten una sintaxis simplificada para crear predicciones: no es necesario proporcionar ninguna entrada, sino que solo tiene que especificar el número de predicciones que crear.</span><span class="sxs-lookup"><span data-stu-id="b4d25-126">Time series models support a simplified syntax for creating predictions: you do not need to supply any inputs, but only have to specify the number of predictions to create.</span></span> <span data-ttu-id="b4d25-127">A continuación, se incluye un ejemplo genérico de la instrucción:</span><span class="sxs-lookup"><span data-stu-id="b4d25-127">The following is a generic example of the statement you will use:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model name>]   
WHERE [<criteria>]  
```  
  
 <span data-ttu-id="b4d25-128">La lista de selección puede contener columnas del modelo, como el nombre de la línea de producto para la que está creando las predicciones, o las funciones de predicción, como [Lag &#40;dmx&#41;](/sql/dmx/lag-dmx) o [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), que son específicamente para los modelos de minería de datos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="b4d25-128">The select list can contain columns from the model, such as the name of the product line that you are creating the predictions for, or prediction functions, such as [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) or [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), which are specifically for time series mining models.</span></span>  
  
#### <a name="to-create-a-simple-time-series-prediction-query"></a><span data-ttu-id="b4d25-129">Para crear una consulta simple de predicción de serie temporal</span><span class="sxs-lookup"><span data-stu-id="b4d25-129">To create a simple time series prediction query</span></span>  
  
1.  <span data-ttu-id="b4d25-130">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b4d25-130">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b4d25-131">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="b4d25-131">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="b4d25-132">Copie el ejemplo genérico de la instrucción en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="b4d25-132">Copy the generic example of the statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b4d25-133">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4d25-133">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="b4d25-134">por:</span><span class="sxs-lookup"><span data-stu-id="b4d25-134">with:</span></span>  
  
    ```  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    ```  
  
     <span data-ttu-id="b4d25-135">La primera línea recupera un valor del modelo de minería de datos que identifica la serie.</span><span class="sxs-lookup"><span data-stu-id="b4d25-135">The first line retrieves a value from the mining model that identifies the series.</span></span>  
  
     <span data-ttu-id="b4d25-136">La segunda y tercera líneas utilizan la función `PredictTimeSeries`.</span><span class="sxs-lookup"><span data-stu-id="b4d25-136">The second and third lines use the `PredictTimeSeries` function.</span></span> <span data-ttu-id="b4d25-137">Cada línea predice un atributo diferente, `[Quantity]` o `[Amount]`.</span><span class="sxs-lookup"><span data-stu-id="b4d25-137">Each line predicts a different attribute, `[Quantity]` or `[Amount]`.</span></span> <span data-ttu-id="b4d25-138">Los números después de los nombres de los atributos de predicción especifican el número de pasos temporales para realizar la predicción.</span><span class="sxs-lookup"><span data-stu-id="b4d25-138">The numbers after the names of the predictable attributes specify the number of time steps to predict.</span></span>  
  
     <span data-ttu-id="b4d25-139">La cláusula `AS` se utiliza con el fin de proporcionar un nombre para la columna que devuelve cada función de predicción.</span><span class="sxs-lookup"><span data-stu-id="b4d25-139">The `AS` clause is used to provide a name for the column that is returned by each prediction function.</span></span> <span data-ttu-id="b4d25-140">Si no proporciona un alias, de forma predeterminada ambas columnas se devuelven con la etiqueta `Expression`.</span><span class="sxs-lookup"><span data-stu-id="b4d25-140">If you do not supply an alias, by default both columns are returned with the label, `Expression`.</span></span>  
  
4.  <span data-ttu-id="b4d25-141">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4d25-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="b4d25-142">por:</span><span class="sxs-lookup"><span data-stu-id="b4d25-142">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="b4d25-143">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4d25-143">Replace the following:</span></span>  
  
    ```  
    WHERE [criteria>]   
    ```  
  
     <span data-ttu-id="b4d25-144">por:</span><span class="sxs-lookup"><span data-stu-id="b4d25-144">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="b4d25-145">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4d25-145">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    FROM   
    [Forecasting_MIXED]  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
6.  <span data-ttu-id="b4d25-146">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="b4d25-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="b4d25-147">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `SimpleTimeSeriesPrediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b4d25-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SimpleTimeSeriesPrediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="b4d25-148">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="b4d25-148">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="b4d25-149">La consulta devuelve seis predicciones para cada una de las dos combinaciones de producto y región que se especifican en la cláusula `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="b4d25-149">The query returns 6 predictions for each of the two combinations of product and region that are specified in the `WHERE` clause.</span></span>  
  
 <span data-ttu-id="b4d25-150">En la lección siguiente, creará una consulta que proporciona los datos nuevos al modelo y comparará los resultados de esa predicción con la recién creada.</span><span class="sxs-lookup"><span data-stu-id="b4d25-150">In the next lesson, you will create a query that supplies new data to the model, and compare the results of that prediction with the one you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b4d25-151">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="b4d25-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b4d25-152">Lección 5: Extensión del modelo de serie temporal</span><span class="sxs-lookup"><span data-stu-id="b4d25-152">Lesson 5: Extending the Time Series Model</span></span>](../../2014/tutorials/lesson-5-extending-the-time-series-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4d25-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4d25-153">See Also</span></span>  
 <span data-ttu-id="b4d25-154">[&#41;PredictTimeSeries &#40;DMX](/sql/dmx/predicttimeseries-dmx) </span><span class="sxs-lookup"><span data-stu-id="b4d25-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span></span>  
 <span data-ttu-id="b4d25-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span><span class="sxs-lookup"><span data-stu-id="b4d25-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span></span>  
 <span data-ttu-id="b4d25-156">[Ejemplos de consultas de modelos de serie temporal](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="b4d25-156">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="b4d25-157">Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b4d25-157">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
  
