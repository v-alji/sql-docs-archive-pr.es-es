---
title: 'Lección 2: agregar modelos de minería de datos a la estructura de minería de datos de serie temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75c2a74b-21ce-44fb-a26b-68be4c685c12
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae0bb91fafb53c0c077a4e0d82558b550d0e6070
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662442"
---
# <a name="lesson-2-adding-mining-models-to-the-time-series-mining-structure"></a><span data-ttu-id="43855-102">Lección 2: Adición de modelos de minería de datos a la estructura de minería de datos de serie temporal</span><span class="sxs-lookup"><span data-stu-id="43855-102">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>
  <span data-ttu-id="43855-103">En esta lección, agregará un nuevo modelo de minería de datos a la estructura de minería de datos que acaba de crear en la [Lección 1: crear un modelo de minería de datos de serie temporal y una estructura de minería](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="43855-103">In this lesson, you will add a new mining model to the mining structure that you just created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="43855-104">Instrucción ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="43855-104">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="43855-105">Para agregar un nuevo modelo de minería de datos a una estructura de minería de datos existente, use la instrucción [ALTER Mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="43855-105">In order to add a new mining model to an existing mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="43855-106">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="43855-106">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="43855-107">Identificación de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="43855-107">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="43855-108">Asignación de un nombre al modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="43855-108">Naming the mining model</span></span>  
  
-   <span data-ttu-id="43855-109">Definición de la columna de clave</span><span class="sxs-lookup"><span data-stu-id="43855-109">Defining the key column</span></span>  
  
-   <span data-ttu-id="43855-110">Definición de las columnas de predicción</span><span class="sxs-lookup"><span data-stu-id="43855-110">Defining the predictable columns</span></span>  
  
-   <span data-ttu-id="43855-111">Especificación de los cambios de parámetros y el algoritmo</span><span class="sxs-lookup"><span data-stu-id="43855-111">Specifying the algorithm and any parameter changes</span></span>  
  
 <span data-ttu-id="43855-112">A continuación, se incluye un ejemplo genérico de la instrucción ALTER MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="43855-112">The following is a generic example of the ALTER MINING STRUCTURE statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
   ([<key columns>],  
    <mining model columns>  
   )  
USING <algorithm name>([<algorithm parameters>])  
[WITH DRILLTHROUGH]  
```  
  
 <span data-ttu-id="43855-113">La primera línea de código identifica la estructura de minería de datos existente a la que se agregarán los modelos de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="43855-113">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="43855-114">La siguiente línea de código asigna un nombre al modelo de minería de datos que se agregará a la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="43855-114">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="43855-115">Para obtener información sobre cómo asignar un nombre a un objeto en DMX, consulte [identifiers &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="43855-115">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="43855-116">Las líneas siguientes del código definen columnas de la estructura de minería de datos que utilizará el modelo de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="43855-116">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key columns>],  
<mining model columns>  
```  
  
 <span data-ttu-id="43855-117">Solo puede utilizar columnas que ya existan en la estructura de minería de datos, y la primera columna de la lista debe ser la columna de clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="43855-117">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="43855-118">La siguiente línea de código define el algoritmo de minería de datos que genera el modelo de minería de datos y los parámetros del algoritmo que puede establecer en el algoritmo, y especifica si puede obtener detalles a partir del modelo en la vista detallada de los datos en los casos de entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="43855-118">The next lines of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm, and specify whether you can drill down from the mining model into view detailed data in the training cases:</span></span>  
  
```  
USING <algorithm name>([<algorithm parameters>])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="43855-119">Para obtener más información sobre los parámetros de algoritmo que puede ajustar, vea [referencia técnica del algoritmo de serie temporal de Microsoft](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="43855-119">For more information about the algorithm parameters that you can adjust, see [Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="43855-120">Puede especificar que una columna del modelo de minería de datos se utilice para la predicción mediante la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="43855-120">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="43855-121">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="43855-121">Lesson Tasks</span></span>  
 <span data-ttu-id="43855-122">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="43855-122">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="43855-123">Agregar un modelo de minería de datos de serie temporal nuevo a la estructura.</span><span class="sxs-lookup"><span data-stu-id="43855-123">Add a new time series mining model to the structure.</span></span>  
  
-   <span data-ttu-id="43855-124">Cambiar los parámetros del algoritmo para utilizar un método de análisis y predicción diferente</span><span class="sxs-lookup"><span data-stu-id="43855-124">Change the algorithm parameters to use a different method of analysis and prediction</span></span>  
  
## <a name="adding-an-arima-time-series-model-to-the-structure"></a><span data-ttu-id="43855-125">Agregar un modelo de serie temporal ARIMA a la estructura</span><span class="sxs-lookup"><span data-stu-id="43855-125">Adding an ARIMA Time Series Model to the Structure</span></span>  
 <span data-ttu-id="43855-126">El primer paso es agregar un nuevo modelo de minería de datos de pronóstico a la estructura existente.</span><span class="sxs-lookup"><span data-stu-id="43855-126">The first step is to add a new forecasting mining model to the existing structure.</span></span> <span data-ttu-id="43855-127">De forma predeterminada, el algoritmo de serie temporal de [!INCLUDE[msCoName](../includes/msconame-md.md)] crea los modelos de minería de datos de serie temporal utilizando dos algoritmos, ARIMA y ARTXP, y mezclando los resultados.</span><span class="sxs-lookup"><span data-stu-id="43855-127">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm creates time series mining models by using two algorithms, ARIMA and ARTXP, and blending the results.</span></span> <span data-ttu-id="43855-128">Sin embargo, puede especificar un único algoritmo que utilizar o la mezcla exacta de algoritmos.</span><span class="sxs-lookup"><span data-stu-id="43855-128">However, you can specify a single algorithm to use, or you can specify the exact blend of algorithms.</span></span> <span data-ttu-id="43855-129">En este paso, agregará un modelo nuevo que utiliza solo el algoritmo ARIMA.</span><span class="sxs-lookup"><span data-stu-id="43855-129">In this step, you will add a new model that uses only the ARIMA algorithm.</span></span> <span data-ttu-id="43855-130">Este algoritmo está optimizado para la predicción a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="43855-130">This algorithm is optimized for long-term prediction.</span></span>  
  
#### <a name="to-add-an-arima-time-series-mining-model"></a><span data-ttu-id="43855-131">Para agregar un modelo de minería de datos de serie temporal ARIMA</span><span class="sxs-lookup"><span data-stu-id="43855-131">To add an ARIMA time series mining model</span></span>  
  
1.  <span data-ttu-id="43855-132">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX** para abrir el editor de consultas y una nueva consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="43855-132">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="43855-133">Copie el ejemplo genérico de la instrucción ALTER MINING STRUCTURE en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="43855-133">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="43855-134">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43855-134">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="43855-135">por:</span><span class="sxs-lookup"><span data-stu-id="43855-135">with:</span></span>  
  
    ```  
    [Forecasting_MIXED_Structure]  
    ```  
  
4.  <span data-ttu-id="43855-136">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43855-136">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="43855-137">por:</span><span class="sxs-lookup"><span data-stu-id="43855-137">with:</span></span>  
  
    ```  
    Forecasting_ARIMA  
    ```  
  
5.  <span data-ttu-id="43855-138">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43855-138">Replace the following:</span></span>  
  
    ```  
    <key columns>,  
    ```  
  
     <span data-ttu-id="43855-139">por:</span><span class="sxs-lookup"><span data-stu-id="43855-139">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]  
    ```  
  
     <span data-ttu-id="43855-140">Observe que no necesita repetir ninguna información del tipo de contenido o tipo de datos que proporcionó en la instrucción CREATE MINING MODEL, porque esta información ya está almacenada en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="43855-140">Note that you do not need to repeat any of the date type or content type information that you provided in the CREATE MINING MODEL statement, because this information is already stored in the mining structure.</span></span>  
  
6.  <span data-ttu-id="43855-141">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43855-141">Replace the following:</span></span>  
  
    ```  
    <mining model columns>  
    ```  
  
     <span data-ttu-id="43855-142">por:</span><span class="sxs-lookup"><span data-stu-id="43855-142">with:</span></span>  
  
    ```  
    ([Quantity] PREDICT,  
    [Amount] PREDICT  
    )  
    ```  
  
7.  <span data-ttu-id="43855-143">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43855-143">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([<algorithm parameters>])   
    [WITH DRILLTHROUGH]  
    ```  
  
     <span data-ttu-id="43855-144">por:</span><span class="sxs-lookup"><span data-stu-id="43855-144">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="43855-145">Ahora, la instrucción resultante debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="43855-145">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARIMA]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
8.  <span data-ttu-id="43855-146">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="43855-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
9. <span data-ttu-id="43855-147">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Forecasting_ARIMA.dmx` .</span><span class="sxs-lookup"><span data-stu-id="43855-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARIMA.dmx`.</span></span>  
  
10. <span data-ttu-id="43855-148">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="43855-148">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-artxp-time-series-model-to-the-structure"></a><span data-ttu-id="43855-149">Agregar un modelo de serie temporal ARTXP a la estructura</span><span class="sxs-lookup"><span data-stu-id="43855-149">Adding an ARTXP Time Series Model to the Structure</span></span>  
 <span data-ttu-id="43855-150">El algoritmo ARTXP era el algoritmo de serie temporal predeterminado de SQL Server 2005 y se optimizó para la predicción a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="43855-150">The ARTXP algorithm was the default time series algorithm in SQL Server 2005 and is optimized for short-term prediction.</span></span> <span data-ttu-id="43855-151">Para comparar las predicciones con los tres algoritmos de serie temporal, agregará un modelo más que se basa en el algoritmo ARTXP.</span><span class="sxs-lookup"><span data-stu-id="43855-151">To compare predictions by using all three time series algorithms, you will add one more model that is based on the ARTXP algorithm.</span></span>  
  
#### <a name="to-add-an-artxp-time-series-mining-model"></a><span data-ttu-id="43855-152">Para agregar un modelo de minería de datos de serie temporal ARTXP</span><span class="sxs-lookup"><span data-stu-id="43855-152">To add an ARTXP time series mining model</span></span>  
  
1.  <span data-ttu-id="43855-153">Copie el código siguiente en una ventana de consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="43855-153">Copy the following code into a blank query window.</span></span>  
  
     <span data-ttu-id="43855-154">Observe que no necesita cambiar nada excepto el nombre del nuevo modelo de minería de datos y el valor del parámetro FORECAST_METHOD.</span><span class="sxs-lookup"><span data-stu-id="43855-154">Note that you do not need to change anything except the name of the new mining model, and the value of the FORECAST_METHOD parameter.</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARTXP]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARTXP')  
    WITH DRILLTHROUGH  
    ```  
  
2.  <span data-ttu-id="43855-155">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="43855-155">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
3.  <span data-ttu-id="43855-156">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Forecasting_ARTXP.dmx` .</span><span class="sxs-lookup"><span data-stu-id="43855-156">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARTXP.dmx`.</span></span>  
  
4.  <span data-ttu-id="43855-157">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="43855-157">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="43855-158">En la siguiente lección procesará todos los modelos y la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="43855-158">In the next lesson, you will process all of the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="43855-159">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="43855-159">Next Lesson</span></span>  
 [<span data-ttu-id="43855-160">Lección 3: Procesamiento de la estructura de serie temporal y los modelos</span><span class="sxs-lookup"><span data-stu-id="43855-160">Lesson 3: Processing the Time Series Structure and Models</span></span>](../../2014/tutorials/lesson-3-processing-the-time-series-structure-and-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="43855-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43855-161">See Also</span></span>  
 <span data-ttu-id="43855-162">[Algoritmo de serie temporal de Microsoft](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="43855-162">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 [<span data-ttu-id="43855-163">Microsoft Time Series Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="43855-163">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
