---
title: Predicciones de serie temporal que usan datos actualizados (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af73681d-ce1c-4b6e-b195-6df3d2fb5275
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2017defaba74071b1a12bee14a5d8907e4c71cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662390"
---
# <a name="time-series-predictions-using-updated-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="88601-102">Predicciones de serie temporal que usan datos actualizados (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="88601-102">Time Series Predictions using Updated Data (Intermediate Data Mining Tutorial)</span></span>
    
## <a name="creating-predictions-using-the-extended-sales-data"></a><span data-ttu-id="88601-103">Crear predicciones mediante datos extendidos de ventas</span><span class="sxs-lookup"><span data-stu-id="88601-103">Creating Predictions using the Extended Sales Data</span></span>  
 <span data-ttu-id="88601-104">En esta lección, creará una consulta de predicción que agrega los nuevos datos de ventas al modelo.</span><span class="sxs-lookup"><span data-stu-id="88601-104">In this lesson, you will create a prediction query that adds the new sales data to the model.</span></span> <span data-ttu-id="88601-105">Al extender el modelo con datos nuevos, puede obtener predicciones actualizadas que incluyan los nuevos puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="88601-105">By extending the model with new data, you can get up-to-date predictions that include the newest data points.</span></span>  
  
 <span data-ttu-id="88601-106">La creación de predicciones de serie temporal que usan datos nuevos es fácil: simplemente agregue el parámetro EXTEND_MODEL_CASES a la función [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) , especifique el origen de los nuevos datos y especifique cuántas predicciones desea obtener.</span><span class="sxs-lookup"><span data-stu-id="88601-106">Creating time series predictions that use new data is easy: you simply add the parameter EXTEND_MODEL_CASES to the [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) function, specify the source of the new data, and specify how many predictions you want to get.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="88601-107">El parámetro EXTEND_MODEL_CASES es opcional; de forma predeterminada, el modelo se amplía en cualquier momento que se crea una consulta de predicción de serie temporal combinando nuevos datos como entradas.</span><span class="sxs-lookup"><span data-stu-id="88601-107">The parameter EXTEND_MODEL_CASES is optional; by default the model is extended any time that you create a time series prediction query by joining new data as inputs.</span></span>  
  
#### <a name="to-build-the-prediction-query-and-add-new-data"></a><span data-ttu-id="88601-108">Para crear la consulta de predicción y agregar nuevos datos</span><span class="sxs-lookup"><span data-stu-id="88601-108">To build the prediction query and add new data</span></span>  
  
1.  <span data-ttu-id="88601-109">Si el modelo aún no está abierto, haga doble clic en la estructura de previsión y, en el diseñador de minería de datos, haga clic en la pestaña **predicción de modelo de minería** de datos.</span><span class="sxs-lookup"><span data-stu-id="88601-109">If the model is not already open, double-click the Forecasting structure, and in Data Mining Designer, click the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="88601-110">En el panel **modelo de minería de datos** , la previsión del modelo ya debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="88601-110">In the **Mining Model** pane, the model Forecasting should already be selected.</span></span> <span data-ttu-id="88601-111">Si no está seleccionada, haga clic en **Seleccionar modelo**y, a continuación, seleccione el modelo, previsión.</span><span class="sxs-lookup"><span data-stu-id="88601-111">If it is not selected, click **Select Model**, and then select the model, Forecasting.</span></span>  
  
3.  <span data-ttu-id="88601-112">En el panel **seleccionar tabla (s) de entrada** , haga clic en **seleccionar tabla de casos**.</span><span class="sxs-lookup"><span data-stu-id="88601-112">In the **Select Input Table(s)** pane, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="88601-113">En el cuadro de diálogo **seleccionar tabla** , seleccione el origen de datos [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88601-113">In the **Select Table** dialog box, select the data source, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
     <span data-ttu-id="88601-114">En la lista de vistas del origen de datos, seleccione NewSalesData y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88601-114">From the list of data source views, select NewSalesData and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="88601-115">Haga clic con el botón secundario en la superficie del área de diseño y seleccione **modificar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="88601-115">Right-click the surface of the design area and select **Modify Connections**.</span></span>  
  
6.  <span data-ttu-id="88601-116">Mediante el cuadro de diálogo **modificar asignación** , asigne las columnas del modelo a las columnas de los datos externos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="88601-116">Using the **Modify Mapping** dialog box, map the columns in the model to the columns in the external data as follows:</span></span>  
  
    -   <span data-ttu-id="88601-117">Asigne la columna ReportingDate del modelo de minería de datos a la columna NewDate de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="88601-117">Map the ReportingDate column in the mining model to the NewDate column in the input data.</span></span>  
  
    -   <span data-ttu-id="88601-118">Asigne la columna amount del modelo de minería de datos a la columna NewAmount de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="88601-118">Map the Amount column in the mining model to the NewAmount column in the input data.</span></span>  
  
    -   <span data-ttu-id="88601-119">Asigne la columna quantity del modelo de minería de datos a la columna NewQty de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="88601-119">Map the Quantity column in the mining model to the NewQty column in the input data.</span></span>  
  
    -   <span data-ttu-id="88601-120">Asigne la columna ModelRegion del modelo de minería de datos a la columna de la serie en los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="88601-120">Map the ModelRegion column in the mining model to the Series column in the input data.</span></span>  
  
7.  <span data-ttu-id="88601-121">Ahora creará la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="88601-121">Now you will build the prediction query.</span></span>  
  
     <span data-ttu-id="88601-122">Primero, agregue una columna a la consulta de predicción para generar la serie a la que se aplica la predicción.</span><span class="sxs-lookup"><span data-stu-id="88601-122">First, add a column to the prediction query to output the series the prediction applies to.</span></span>  
  
    1.  <span data-ttu-id="88601-123">En la cuadrícula, haga clic en la primera fila vacía, en **origen**y, a continuación, seleccione previsión.</span><span class="sxs-lookup"><span data-stu-id="88601-123">In the grid, click the first empty row, under **Source**, and then select Forecasting.</span></span>  
  
    2.  <span data-ttu-id="88601-124">En la columna **campo** , seleccione región del modelo y, en **alias**, escriba `Model Region` .</span><span class="sxs-lookup"><span data-stu-id="88601-124">In the **Field** column, select Model Region and for **Alias**, type `Model Region`.</span></span>  
  
8.  <span data-ttu-id="88601-125">A continuación, agregue y modifique la función de predicción.</span><span class="sxs-lookup"><span data-stu-id="88601-125">Next, add and edit the prediction function.</span></span>  
  
    1.  <span data-ttu-id="88601-126">Haga clic en una fila vacía y, en **origen**, seleccione **función de predicción**.</span><span class="sxs-lookup"><span data-stu-id="88601-126">Click an empty row, and under **Source**, select **Prediction Function**.</span></span>  
  
    2.  <span data-ttu-id="88601-127">En **campo**, seleccione **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="88601-127">For **Field**, select **PredictTimeSeries**.</span></span>  
  
    3.  <span data-ttu-id="88601-128">En **alias**, escriba **valores predichos**.</span><span class="sxs-lookup"><span data-stu-id="88601-128">For **Alias**, type **Predicted Values**.</span></span>  
  
    4.  <span data-ttu-id="88601-129">Arrastre la cantidad de campo del panel **modelo de minería de datos** a la columna **criterios o argumento** .</span><span class="sxs-lookup"><span data-stu-id="88601-129">Drag the field Quantity from the **Mining Model** pane into the **Criteria/Argument** column.</span></span>  
  
    5.  <span data-ttu-id="88601-130">En la columna **criterios o argumento** , después del nombre del campo, escriba el texto siguiente: **5, EXTEND_MODEL_CASES**</span><span class="sxs-lookup"><span data-stu-id="88601-130">In the **Criteria/Argument** column, after the field name, type the following text:  **5,EXTEND_MODEL_CASES**</span></span>  
  
         <span data-ttu-id="88601-131">El texto completo del cuadro de texto **criterios/argumento** debe ser el siguiente:`[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span><span class="sxs-lookup"><span data-stu-id="88601-131">The complete text of the **Criteria/Argument** text box should be as follows: `[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span></span>  
  
9. <span data-ttu-id="88601-132">Haga clic en **resultados** y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="88601-132">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="88601-133">Las predicciones comienzan en julio (el primer segmento de tiempo después del final de los datos originales) y terminan en noviembre (el quinto segmento de tiempo después del final de los datos originales).</span><span class="sxs-lookup"><span data-stu-id="88601-133">The predictions begin in July (the first time slice after the end of the original data) and end at November (the fifth time slice after the end of the original data).</span></span>  
  
 <span data-ttu-id="88601-134">Puede ver que para usar este tipo de consulta de predicción de forma eficaz, debe saber cuándo finalizan los datos antiguos, así como el número de segmentos de tiempo que están en los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="88601-134">You can see that to use this type of prediction query effectively, you need to know when the old data ends, as well as how many time slices there are in the new data.</span></span>  
  
 <span data-ttu-id="88601-135">Por ejemplo, en este modelo, la serie de datos original finalizaba en junio, y los datos corresponden a los meses de julio, agosto y septiembre.</span><span class="sxs-lookup"><span data-stu-id="88601-135">For example, in this model, the original data series ended in June, and the data is for the months of July, August, and September.</span></span>  
  
 <span data-ttu-id="88601-136">Las predicciones que usan EXTEND_MODEL_CASES siempre comienzan por el final de la serie de datos original.</span><span class="sxs-lookup"><span data-stu-id="88601-136">Predictions that use EXTEND_MODEL_CASES always begin at the end of the original data series.</span></span> <span data-ttu-id="88601-137">Por tanto, si solo desea obtener las predicciones de los meses desconocidos, debe especificar el punto inicial y el punto final para la predicción.</span><span class="sxs-lookup"><span data-stu-id="88601-137">Therefore, if you want to get only the predictions for the unknown months, you need to specify the starting point and the end point for prediction.</span></span> <span data-ttu-id="88601-138">Ambos valores se especifican como un número de segmentos de tiempo que comienzan al final de los datos antiguos.</span><span class="sxs-lookup"><span data-stu-id="88601-138">Both values are specified as a number of time slices starting at the end of the old data.</span></span>  
  
 <span data-ttu-id="88601-139">El siguiente procedimiento muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="88601-139">The following procedure demonstrates how to do this.</span></span>  
  
### <a name="change-the-start-and-end-points-of-the-predictions"></a><span data-ttu-id="88601-140">Cambiar los puntos inicial y final de las predicciones</span><span class="sxs-lookup"><span data-stu-id="88601-140">Change the start and end points of the predictions</span></span>  
  
1.  <span data-ttu-id="88601-141">En Generador de consultas de predicción, haga clic en **consulta** para cambiar a la vista DMX.</span><span class="sxs-lookup"><span data-stu-id="88601-141">In Prediction Query Builder, click **Query** to switch to DMX view.</span></span>  
  
2.  <span data-ttu-id="88601-142">Busque la instrucción DMX que contiene la función PredictTimeSeries y cámbiela de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="88601-142">Locate the DMX statement that contains the PredictTimeSeries function and change it as follows:</span></span>  
  
     `PredictTimeSeries([Forecasting 12].[Quantity],4,6,EXTEND_MODEL_CASES)`  
  
3.  <span data-ttu-id="88601-143">Haga clic en **resultados** y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="88601-143">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="88601-144">Ahora las predicciones comienzan en octubre (el cuarto segmento de tiempo, contando desde el final de los datos originales) y terminan en diciembre (el sexto segmento de tiempo, contando desde el final de los datos originales).</span><span class="sxs-lookup"><span data-stu-id="88601-144">Now the predictions begin at October (the fourth time slice, counting from the end of the original data) and end at December (the sixth time slice, counting from the end of the original data).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="88601-145">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="88601-145">Next Task in Lesson</span></span>  
 [<span data-ttu-id="88601-146">Predicciones de serie temporal que usan datos de reemplazo &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="88601-146">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="88601-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88601-147">See Also</span></span>  
 <span data-ttu-id="88601-148">[Referencia técnica del algoritmo de serie temporal de Microsoft](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="88601-148">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="88601-149">Contenido del modelo de minería de datos para los modelos de serie temporal &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="88601-149">Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)  
  
  
