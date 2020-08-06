---
title: 'Lección 1: crear un modelo de minería de datos y una estructura de minería de datos de serie temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b201f2b8-9ab5-425b-9ff3-fe321a60a7b7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2513bc3837dd224f6561eb0015ced538ea3add8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663861"
---
# <a name="lesson-1-creating-a-time-series-mining-model-and-mining-structure"></a><span data-ttu-id="e9525-102">Lección 1: Creación de un modelo de minería de datos de serie temporal y una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e9525-102">Lesson 1: Creating a Time Series Mining Model and Mining Structure</span></span>
  <span data-ttu-id="e9525-103">En esta lección, creará un modelo de minería de datos que le permita predecir valores a lo largo del tiempo, según datos históricos.</span><span class="sxs-lookup"><span data-stu-id="e9525-103">In this lesson, you will create a mining model that allows you to predict values over time, based on historical data.</span></span> <span data-ttu-id="e9525-104">Al crear el modelo, la estructura subyacente se generará automáticamente y se utilizará como base para otros modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e9525-104">When you create the model, the underlying structure will be generated automatically and can be used as the basis for additional mining models.</span></span>  
  
 <span data-ttu-id="e9525-105">En esta lección se supone que conoce los modelos de predicción y los requisitos del algoritmo de serie temporal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9525-105">This lesson assumes that you are familiar with forecasting models and with the requirements of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="e9525-106">Para más información, consulte [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="e9525-106">For more information, see [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span></span>  
  
## <a name="create-mining-model-statement"></a><span data-ttu-id="e9525-107">Instrucción CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="e9525-107">CREATE MINING MODEL Statement</span></span>  
 <span data-ttu-id="e9525-108">Con el fin de crear un modelo de minería de datos directamente y generar automáticamente la estructura de minería de datos subyacente, se usa la instrucción [Create Mining model &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) .</span><span class="sxs-lookup"><span data-stu-id="e9525-108">In order to create a mining model directly and automatically generate the underlying mining structure, you use the [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) statement.</span></span> <span data-ttu-id="e9525-109">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9525-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="e9525-110">Asignación de un nombre al modelo</span><span class="sxs-lookup"><span data-stu-id="e9525-110">Naming the model</span></span>  
  
-   <span data-ttu-id="e9525-111">Definición de la marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="e9525-111">Defining the time stamp</span></span>  
  
-   <span data-ttu-id="e9525-112">Definición de la columna de clave de la serie opcional</span><span class="sxs-lookup"><span data-stu-id="e9525-112">Defining the optional series key column</span></span>  
  
-   <span data-ttu-id="e9525-113">Definición del atributo o atributos de predicción</span><span class="sxs-lookup"><span data-stu-id="e9525-113">Defining the predictable attribute or attributes</span></span>  
  
 <span data-ttu-id="e9525-114">A continuación, se incluye un ejemplo genérico de la instrucción CREATE MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="e9525-114">The following is a generic example of the CREATE MINING MODEL statement:</span></span>  
  
```  
CREATE MINING MODEL [<Mining Structure Name>]  
(  
   <key columns>,  
   <predictable attribute columns>  
)  
USING <algorithm name>([parameter list])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="e9525-115">En la primera línea del código se define el nombre del modelo de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="e9525-115">The first line of the code defines the name of the mining model:</span></span>  
  
```  
CREATE MINING MODEL [Mining Model Name]  
```  
  
 <span data-ttu-id="e9525-116">Analysis Services genera un nombre para la estructura subyacente anexando "_structure" al nombre del modelo, con lo que se asegura de que el nombre de la estructura sea distinto del nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="e9525-116">Analysis Services automatically generates a name for the underlying structure, by appending "_structure" to the model name, which ensures that the structure name is unique from the model name.</span></span> <span data-ttu-id="e9525-117">Para obtener información sobre cómo asignar un nombre a un objeto en DMX, consulte [identifiers &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="e9525-117">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="e9525-118">La línea siguiente de código define la columna de clave para el modelo de minería de datos, que en el caso de un modelo de serie temporal identifica singularmente un incremento de tiempo en los datos del origen.</span><span class="sxs-lookup"><span data-stu-id="e9525-118">The next line of the code defines the key column for the mining model, which in the case of a time series model uniquely identifies a time step in the source data.</span></span> <span data-ttu-id="e9525-119">El paso de tiempo se identifica con las `KEY TIME` palabras clave después del nombre de columna y los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="e9525-119">The time step is identified with the `KEY TIME` keywords after the column name and data types.</span></span> <span data-ttu-id="e9525-120">Si el modelo de serie temporal tiene una clave de serie independiente, se identifica con la palabra clave `KEY`.</span><span class="sxs-lookup"><span data-stu-id="e9525-120">If the time series model has a separate series key, it is identified by using the `KEY` keyword.</span></span>  
  
```  
<key columns>  
```  
  
 <span data-ttu-id="e9525-121">La línea siguiente del código se utiliza para definir las columnas del modelo que se predecirá.</span><span class="sxs-lookup"><span data-stu-id="e9525-121">The next line of the code is used to define the columns in the model that will be predicted.</span></span> <span data-ttu-id="e9525-122">Puede tener varios atributos de predicción en un único modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e9525-122">You can have multiple predictable attributes in a single mining model.</span></span> <span data-ttu-id="e9525-123">Cuando hay varios atributos de predicción, el algoritmo de serie temporal de Microsoft genera un análisis independiente para cada serie:</span><span class="sxs-lookup"><span data-stu-id="e9525-123">When there are multiple predictable attributes, the Microsoft Time Series algorithm generates a separate analysis for each series:</span></span>  
  
```  
<predictable attribute columns>  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="e9525-124">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="e9525-124">Lesson Tasks</span></span>  
 <span data-ttu-id="e9525-125">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9525-125">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="e9525-126">Crear una consulta en blanco</span><span class="sxs-lookup"><span data-stu-id="e9525-126">Create a new blank query</span></span>  
  
-   <span data-ttu-id="e9525-127">Modificar la consulta para crear la el modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e9525-127">Alter the query to create the mining model</span></span>  
  
-   <span data-ttu-id="e9525-128">Ejecución de la consulta</span><span class="sxs-lookup"><span data-stu-id="e9525-128">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="e9525-129">Crear la consulta</span><span class="sxs-lookup"><span data-stu-id="e9525-129">Creating the Query</span></span>  
 <span data-ttu-id="e9525-130">El primer paso es conectarse a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y crear una consulta DMX en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9525-130">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="e9525-131">Para crear una consulta DMX mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9525-131">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e9525-132">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9525-132">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9525-133">En el cuadro de diálogo **conectar con el servidor** , en **tipo de servidor**, seleccione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="e9525-133">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="e9525-134">En **nombre del servidor**, escriba `LocalHost` o el nombre de la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a la que desea conectarse para esta lección.</span><span class="sxs-lookup"><span data-stu-id="e9525-134">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="e9525-135">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e9525-135">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="e9525-136">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="e9525-136">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="e9525-137">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="e9525-137">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="e9525-138">Modificar la consulta</span><span class="sxs-lookup"><span data-stu-id="e9525-138">Altering the Query</span></span>  
 <span data-ttu-id="e9525-139">El paso siguiente es modificar la instrucción CREATE MINING MODEL para crear el modelo de minería de datos que se usa para la predicción, junto con su estructura de minería de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="e9525-139">The next step is to modify the CREATE MINING MODEL statement to create the mining model used for forecasting, together with its underlying mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-model-statement"></a><span data-ttu-id="e9525-140">Para personalizar la instrucción CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="e9525-140">To customize the CREATE MINING MODEL statement</span></span>  
  
1.  <span data-ttu-id="e9525-141">En el Editor de consultas, copie el ejemplo genérico de la instrucción CREATE MINING MODEL en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="e9525-141">In Query Editor, copy the generic example of the CREATE MINING MODEL statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="e9525-142">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9525-142">Replace the following:</span></span>  
  
    ```  
    [mining model name]   
    ```  
  
     <span data-ttu-id="e9525-143">por:</span><span class="sxs-lookup"><span data-stu-id="e9525-143">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
3.  <span data-ttu-id="e9525-144">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9525-144">Replace the following:</span></span>  
  
    ```  
    <key columns>  
    ```  
  
     <span data-ttu-id="e9525-145">por:</span><span class="sxs-lookup"><span data-stu-id="e9525-145">with:</span></span>  
  
    ```  
    [Reporting Date] DATE KEY TIME,  
    [Model Region] TEXT KEY  
    ```  
  
     <span data-ttu-id="e9525-146">La palabra clave `TIME KEY` indica que la columna ReportingDate contiene los valores de incremento de tiempo utilizados para ordenar los valores.</span><span class="sxs-lookup"><span data-stu-id="e9525-146">The `TIME KEY` keyword indicates that the ReportingDate column contains the time step values used to order the values.</span></span> <span data-ttu-id="e9525-147">Los incrementos de tiempo pueden ser fechas y horas, números enteros o cualquier tipo de datos ordenado, siempre que los valores sean únicos y los datos estén ordenados.</span><span class="sxs-lookup"><span data-stu-id="e9525-147">Time steps can be dates and times, integers, or any ordered data type, so long as the values are unique and the data is sorted.</span></span>  
  
     <span data-ttu-id="e9525-148">Las palabras clave `TEXT` y `KEY` indican que la columna ModelRegion contiene una clave de serie adicional.</span><span class="sxs-lookup"><span data-stu-id="e9525-148">The `TEXT` and `KEY` keywords indicate that the ModelRegion column contains an additional series key.</span></span> <span data-ttu-id="e9525-149">Puede tener únicamente una clave de serie y los valores de la columna deben ser distintos.</span><span class="sxs-lookup"><span data-stu-id="e9525-149">You can have only one series key, and the values in the column must be distinct.</span></span>  
  
4.  <span data-ttu-id="e9525-150">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9525-150">Replace the following:</span></span>  
  
    ```  
    < predictable attribute columns> )  
    ```  
  
     <span data-ttu-id="e9525-151">por:</span><span class="sxs-lookup"><span data-stu-id="e9525-151">with:</span></span>  
  
    ```  
    [Quantity] LONG CONTINUOUS PREDICT,  
    [Amount] DOUBLE CONTINUOUS PREDICT  
    )  
    ```  
  
5.  <span data-ttu-id="e9525-152">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9525-152">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([parameter list])  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="e9525-153">por:</span><span class="sxs-lookup"><span data-stu-id="e9525-153">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series(AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="e9525-154">El parámetro de algoritmo, `AUTO_DETECT_PERIODICITY` = 0.8, indica que desea que el algoritmo detecte los ciclos en los datos.</span><span class="sxs-lookup"><span data-stu-id="e9525-154">The algorithm parameter, `AUTO_DETECT_PERIODICITY` = 0.8, indicates that you want the algorithm to detect cycles in the data.</span></span> <span data-ttu-id="e9525-155">Si se establece este valor más próximo a 1, se favorece la detección de muchos patrones pero puede desacelerar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e9525-155">Setting this value closer to 1 favors the discovery of many patterns but can slow processing.</span></span>  
  
     <span data-ttu-id="e9525-156">El parámetro de algoritmo, `FORECAST_METHOD`, indica si desea analizar los datos utilizando ARTXP, ARIMA o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="e9525-156">The algorithm parameter, `FORECAST_METHOD`, indicates whether you want the data to be analyzed using ARTXP, ARIMA, or a mixture of both.</span></span>  
  
     <span data-ttu-id="e9525-157">La palabra clave, `WITH DRILLTHROUGH`, especifica que desea poder ver estadísticas detalladas de los datos de origen cuando el modelo se complete.</span><span class="sxs-lookup"><span data-stu-id="e9525-157">The keyword, `WITH DRILLTHROUGH`, specify that you want to be able to view detailed statistics in the source data after the model is complete.</span></span> <span data-ttu-id="e9525-158">Debe agregar esta cláusula si desea examinar el modelo utilizando el Visor de series temporales de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9525-158">You must add this clause if you want to browse the model by using the Microsoft Time Series Viewer.</span></span> <span data-ttu-id="e9525-159">No se requiere para la predicción.</span><span class="sxs-lookup"><span data-stu-id="e9525-159">It is not required for prediction.</span></span>  
  
     <span data-ttu-id="e9525-160">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9525-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING MODEL [Forecasting_MIXED]  
         (  
        [Reporting Date] DATE KEY TIME,  
        [Model Region] TEXT KEY,  
        [Quantity] LONG CONTINUOUS PREDICT,  
        [Amount] DOUBLE CONTINUOUS PREDICT  
        )  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
  
    ```  
  
6.  <span data-ttu-id="e9525-161">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="e9525-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="e9525-162">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Forecasting_MIXED.dmx` .</span><span class="sxs-lookup"><span data-stu-id="e9525-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_MIXED.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="e9525-163">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="e9525-163">Executing the Query</span></span>  
 <span data-ttu-id="e9525-164">El último paso es ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="e9525-164">The final step is to execute the query.</span></span> <span data-ttu-id="e9525-165">Después de crear y guardar una consulta, debe ejecutarse para crear el modelo y su estructura de minería de datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e9525-165">After a query is created and saved, it needs to be executed to create the mining model and its mining structure on the server.</span></span> <span data-ttu-id="e9525-166">Para obtener más información acerca de la ejecución de consultas en el editor de consultas, vea [motor de base de datos editor de consultas &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e9525-166">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="e9525-167">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="e9525-167">To execute the query</span></span>  
  
-   <span data-ttu-id="e9525-168">En el editor de consultas, en la barra de herramientas, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e9525-168">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="e9525-169">El estado de la consulta se muestra en la pestaña **mensajes** , en la parte inferior del editor de consultas, una vez finalizada la ejecución de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e9525-169">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="e9525-170">En Mensajes, debe aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9525-170">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="e9525-171">Ahora existe una nueva estructura denominada **Forecasting_MIXED_Structure** en el servidor, junto con el **Forecasting_MIXED**del modelo de minería de datos relacionado.</span><span class="sxs-lookup"><span data-stu-id="e9525-171">A new structure named **Forecasting_MIXED_Structure** now exists on the server, together with the related mining model **Forecasting_MIXED**.</span></span>  
  
 <span data-ttu-id="e9525-172">En la lección siguiente, agregará un modelo de minería de datos a la **Forecasting_MIXED** estructura de minería de datos que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="e9525-172">In the next lesson, you will add a mining model to the **Forecasting_MIXED** mining structure that you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="e9525-173">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="e9525-173">Next Lesson</span></span>  
 [<span data-ttu-id="e9525-174">Lección 2: Adición de modelos de minería de datos a la estructura de minería de datos de serie temporal</span><span class="sxs-lookup"><span data-stu-id="e9525-174">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9525-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9525-175">See Also</span></span>  
 <span data-ttu-id="e9525-176">[Contenido del modelo de minería de datos para los modelos de serie temporal &#40;Analysis Services-minería de datos&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e9525-176">[Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="e9525-177">Microsoft Time Series Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="e9525-177">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
