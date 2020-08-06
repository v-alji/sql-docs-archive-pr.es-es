---
title: Predicciones de serie temporal avanzadas (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b614ebdb-07ca-44af-a0ff-893364bd4b71
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 70ebf856ba0782cbf44969aba30602818015582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747792"
---
# <a name="advanced-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="a2f80-102">Predicciones de serie temporal avanzadas (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="a2f80-102">Advanced Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="a2f80-103">Al explorar el modelo de predicción, observó que, aunque las ventas de la mayoría de las regiones siguen un patrón similar, algunas regiones y algunos modelos, como el modelo M200 en la región del Pacífico, muestran tendencias muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="a2f80-103">You saw from exploring the forecasting model that although sales in most of the regions follow a similar pattern, some regions and some models, such as the M200 model in the Pacific region, exhibit very different trends.</span></span> <span data-ttu-id="a2f80-104">Esto no le sorprende, ya que sabe que las diferencias entre regiones son comunes y pueden deberse a muchos factores, como las promociones de marketing, los informes inexactos o los acontecimientos geopolíticos.</span><span class="sxs-lookup"><span data-stu-id="a2f80-104">This does not surprise you, as you know that differences among regions are common and can be caused by many factors, including marketing promotions, inaccurate reporting, or geopolitical events.</span></span>  
  
 <span data-ttu-id="a2f80-105">Sin embargo, los usuarios piden un modelo que se puede aplicar a todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="a2f80-105">However, your users are asking for a model that can be applied worldwide.</span></span> <span data-ttu-id="a2f80-106">Por consiguiente, para reducir el efecto de los factores individuales en las proyecciones, decide crear un modelo de minería de datos basado en medidas agregadas de ventas mundiales.</span><span class="sxs-lookup"><span data-stu-id="a2f80-106">Therefore, to minimize the effect of individual factors on projections, you decide to build a model that is based on aggregated measures of worldwide sales.</span></span> <span data-ttu-id="a2f80-107">Puede usar este modelo para realizar las predicciones de cada región individual.</span><span class="sxs-lookup"><span data-stu-id="a2f80-107">You can then use this model to make predictions for each individual region.</span></span>  
  
 <span data-ttu-id="a2f80-108">En esta tarea, creará todos los orígenes de datos que necesita para realizar las tareas de predicción avanzada.</span><span class="sxs-lookup"><span data-stu-id="a2f80-108">In this task, you will build all the data sources that you need to perform the advanced prediction tasks.</span></span> <span data-ttu-id="a2f80-109">Creará dos vistas de origen de datos que usará como entradas en la consulta de predicción, y una vista de origen de datos que usará para crear un nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="a2f80-109">You will create two data source views for use as inputs to the prediction query, and one data source view to use in building a new model.</span></span>  
  
 <span data-ttu-id="a2f80-110">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="a2f80-110">**Steps**</span></span>  
  
1.  [<span data-ttu-id="a2f80-111">Preparar los datos extendidos de ventas (para la predicción)</span><span class="sxs-lookup"><span data-stu-id="a2f80-111">Prepare the extended sales data (for prediction)</span></span>](#bkmk_newExtendData)  
  
2.  [<span data-ttu-id="a2f80-112">Preparar los datos agregados (para crear el modelo)</span><span class="sxs-lookup"><span data-stu-id="a2f80-112">Prepare the aggregated data (for building the model)</span></span>](#bkmk_newReplaceData)  
  
3.  [<span data-ttu-id="a2f80-113">Preparar los datos de la serie (para la predicción cruzada)</span><span class="sxs-lookup"><span data-stu-id="a2f80-113">Prepare the series data (for cross-prediction)</span></span>](#bkmk_CrossData2)  
  
4.  [<span data-ttu-id="a2f80-114">Predecir mediante EXTEND</span><span class="sxs-lookup"><span data-stu-id="a2f80-114">Predict using EXTEND</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
5.  [<span data-ttu-id="a2f80-115">Crear el modelo de predicción cruzada</span><span class="sxs-lookup"><span data-stu-id="a2f80-115">Create the cross-prediction model</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
6.  [<span data-ttu-id="a2f80-116">Predecir con REPLACE</span><span class="sxs-lookup"><span data-stu-id="a2f80-116">Predict using REPLACE</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
7.  [<span data-ttu-id="a2f80-117">Revisar las nuevas predicciones</span><span class="sxs-lookup"><span data-stu-id="a2f80-117">Review the new predictions</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
##  <a name="creating-the-new-extended-sales-data"></a><a name="bkmk_newExtendData"></a><span data-ttu-id="a2f80-118">Creación de los nuevos datos de ventas extendidos</span><span class="sxs-lookup"><span data-stu-id="a2f80-118">Creating the New Extended Sales Data</span></span>  
 <span data-ttu-id="a2f80-119">Para actualizar los datos de ventas, necesitará obtener las últimas cifras de ventas.</span><span class="sxs-lookup"><span data-stu-id="a2f80-119">To update your sales data, you will need to get the latest sales figures.</span></span> <span data-ttu-id="a2f80-120">Los datos que se acaban de introducir de la región del Pacífico son de interés particular. Allí se inició una promoción de ventas regional para llamar la atención sobre las nuevas tiendas y aumentar el conocimiento de sus productos.</span><span class="sxs-lookup"><span data-stu-id="a2f80-120">Of particular interest are the data just in from the Pacific region, which launched a regional sales promotion to call attention to the new stores and raise awareness of their products.</span></span>  
  
 <span data-ttu-id="a2f80-121">En este escenario, se supone que los datos se han importado desde un libro de Excel que contiene solo tres meses de nuevos datos para un par de regiones.</span><span class="sxs-lookup"><span data-stu-id="a2f80-121">For this scenario, we'll assume that the data has been imported from an Excel workbook that contains just three months of new data for a couple of regions.</span></span> <span data-ttu-id="a2f80-122">Creará una tabla para los datos mediante un script Transact-SQL y, a continuación, definirá una vista del origen de datos que se usará para la predicción.</span><span class="sxs-lookup"><span data-stu-id="a2f80-122">You'll create a table for the data using a Transact-SQL script, and then define a data source view to use for prediction.</span></span>  
  
#### <a name="create-the-table-with-new-sales-data"></a><span data-ttu-id="a2f80-123">Crear la tabla con nuevos datos de ventas</span><span class="sxs-lookup"><span data-stu-id="a2f80-123">Create the table with new sales data</span></span>  
  
1.  <span data-ttu-id="a2f80-124">En una ventana de consulta de Transact-SQL, ejecute la instrucción siguiente para agregar los datos de ventas a la base de datos AdventureWorksDW (o a cualquier otra base de datos).</span><span class="sxs-lookup"><span data-stu-id="a2f80-124">In a Transact-SQL query window, execute the following statement to add the sales data to the AdventureWorksDW database (or any other database).</span></span>  
  
    ```  
    USE [database name];  
    GO  
    IF OBJECT_ID ([dbo].[NewSalesData]) IS NOT NULL   
        DROP TABLE [dbo].[NewSalesData];  
    GO  
    CREATE TABLE [dbo].[NewSalesData]([Series] [nvarchar](255) NULL,  
    [NewDate] [datetime] NULL,  
    [NewQty] [float] NULL,  
    [NewAmount] [money] NULL) ON [PRIMARY]  
  
    GO  
    ```  
  
2.  <span data-ttu-id="a2f80-125">Inserte los nuevos valores mediante el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="a2f80-125">Insert the new values using the following script.</span></span>  
  
    ```  
    INSERT INTO [NewSalesData]  
    (Series,NewDate,NewQty,NewAmount)  
    VALUES('T1000 Pacific', '7/25/08', 55, '$130,170.22'),  
    ('T1000 Pacific', '8/25/08', 50, '$114,435.36 '),  
    ('T1000 Pacific', '9/25/08', 50, '$117,296.24 '),  
    ('T1000 Europe', '7/25/08', 37, '$88,210.00 '),  
    ('T1000 Europe', '8/25/08', 41, '$97,746.00 '),  
    ('T1000 Europe', '9/25/08', 37, '$88,210.00 '),  
    ('T1000 North America', '7/25/08', 69, '$164,500.00 '),  
    ('T1000 North America', '8/25/08', 66, '$157,348.00 '),  
    ('T1000 North America', '9/25/08', 58, '$138,276.00 '),  
    ('M200 Pacific', '7/25/08', 65, '$149,824.35'),  
    ('M200 Pacific', '8/25/08', 54,  '$124,619.46'),  
    ('M200 Pacific', '9/25/08', 61, '$141,143.39'),  
    ('M200 Europe', '7/25/08', 75, '$173,026.00'),  
    ('M200 Europe', '8/25/08', 76, '$175,212.00'),  
    ('M200 Europe', '9/25/08', 84, '$193,731.00'),  
    ('M200 North America', '7/25/08', 94, '$216,916.00'),  
    ('M200 North America', '8/25/08', 94, '$216,891.00'),  
    ('M200 North America', '9/25/08', 91,'$209,943.00');  
    ```  
  
    > [!WARNING]  
    >  <span data-ttu-id="a2f80-126">Se usan comillas con los valores de moneda para evitar problemas con el separador de coma y el símbolo de moneda.</span><span class="sxs-lookup"><span data-stu-id="a2f80-126">The quotation marks are used with the currency values to prevent problems with the comma separator and the currency symbol.</span></span> <span data-ttu-id="a2f80-127">También podría pasar los valores de moneda en este formato: `130170.22`</span><span class="sxs-lookup"><span data-stu-id="a2f80-127">You could also pass in the currency values in this format: `130170.22`</span></span>  
    >   
    >  <span data-ttu-id="a2f80-128">Observe que las fechas usadas en la base de datos de ejemplo han cambiado en esta versión.</span><span class="sxs-lookup"><span data-stu-id="a2f80-128">Note that the dates used in the sample database have changed for this release.</span></span> <span data-ttu-id="a2f80-129">Si está usando una edición anterior de AdventureWorks, quizás necesite ajustar las fechas insertadas en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="a2f80-129">If you are using an earlier edition of AdventureWorks, you might need to adjust the inserted dates accordingly.</span></span>  
  
###  <a name="create-a-data-source-view-using-the-new-sales-data"></a><a name="bkmk_newReplaceData"></a><span data-ttu-id="a2f80-130">Crear una vista del origen de datos con los nuevos datos de ventas</span><span class="sxs-lookup"><span data-stu-id="a2f80-130">Create a data source view using the new sales data</span></span>  
  
1.  <span data-ttu-id="a2f80-131">En el **Explorador de soluciones**, haga clic con el botón secundario en **Vistas del origen de datos**y, a continuación, seleccione **Nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-131">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="a2f80-132">En el Asistente para vistas del origen de datos, realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2f80-132">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="a2f80-133">**Origen de datos**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f80-133">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="a2f80-134">**Seleccionar tablas y vistas**: seleccione la tabla que acaba de crear, NewSalesData.</span><span class="sxs-lookup"><span data-stu-id="a2f80-134">**Select Tables and Views**: Select the table that you just created, NewSalesData.</span></span>  
  
3.  <span data-ttu-id="a2f80-135">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="a2f80-135">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="a2f80-136">En la superficie de diseño de la vista del origen de datos, haga clic con el botón secundario en NewSalesData y seleccione **explorar datos** para comprobar los datos.</span><span class="sxs-lookup"><span data-stu-id="a2f80-136">In the Data Source View design surface, right-click NewSalesData, and then select **Explore Data** to verify the data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a2f80-137">Usará estos datos solo para la predicción, por lo que no importa que sean incompletos.</span><span class="sxs-lookup"><span data-stu-id="a2f80-137">You will use this data for prediction only, so it does not matter that the data is incomplete.</span></span>  
  
##  <a name="creating-the-data-for-the-cross-prediction-model"></a><a name="bkmk_CrossData2"></a><span data-ttu-id="a2f80-138">Crear los datos para el modelo de predicción cruzada</span><span class="sxs-lookup"><span data-stu-id="a2f80-138">Creating the Data for the Cross-Prediction Model</span></span>  
 <span data-ttu-id="a2f80-139">Los datos que se usaron en el modelo de pronóstico original ya están agrupados de algún modo en la vista vTimeSeries. Los diversos modelos de bicicletas se han contraído en un número menor de categorías y los resultados de países individuales se han combinado por regiones.</span><span class="sxs-lookup"><span data-stu-id="a2f80-139">The data that was used in the original forecasting model was already grouped somewhat by the view vTimeSeries, which collapsed several bike models into a smaller number of categories, and merged results from individual countries into regions.</span></span> <span data-ttu-id="a2f80-140">Para crear un modelo que se puede usar para las proyecciones mundiales, creará algunas agregaciones simples adicionales directamente en el Diseñador de vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a2f80-140">To create a model that can be used for world-wide projections, you will create some additional simple aggregations directly in the Data Source View Designer.</span></span> <span data-ttu-id="a2f80-141">La nueva vista del origen de datos contiene solo una suma y un promedio de las ventas de todos los productos para todas las regiones.</span><span class="sxs-lookup"><span data-stu-id="a2f80-141">The new data source view will contain just a sum and an average of the sales of all products for all regions.</span></span>  
  
 <span data-ttu-id="a2f80-142">Después de crear el origen de datos usado para el modelo, debe crear una nueva vista del origen de datos que usará para la predicción.</span><span class="sxs-lookup"><span data-stu-id="a2f80-142">After you have created the data source used for the model, you must create a new data source view to use for prediction.</span></span> <span data-ttu-id="a2f80-143">Por ejemplo, si desea predecir las ventas de Europa con el nuevo modelo mundial, debe suministrar los datos de la región de Europa solamente.</span><span class="sxs-lookup"><span data-stu-id="a2f80-143">For example, if you want to predict sales for Europe using the new worldwide model, you must feed in data for the Europe region only.</span></span> <span data-ttu-id="a2f80-144">De esta forma, configurará una nueva vista del origen de datos que filtra los datos originales y cambiará la condición de filtro para cada conjunto de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="a2f80-144">So you will set up a new data source view that filters the original data, and change the filter condition for each set of prediction queries.</span></span>  
  
#### <a name="to-create-the-model-data-using-a-custom-data-source-view"></a><span data-ttu-id="a2f80-145">Para crear los datos del modelo mediante una vista personalizada del origen de datos</span><span class="sxs-lookup"><span data-stu-id="a2f80-145">To create the model data using a custom data source view</span></span>  
  
1.  <span data-ttu-id="a2f80-146">En el **Explorador de soluciones**, haga clic con el botón secundario en **Vistas del origen de datos**y, a continuación, seleccione **Nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-146">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="a2f80-147">En la página de bienvenida del asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-147">On the welcome page of the wizard, click **Next**.</span></span>  
  
3.  <span data-ttu-id="a2f80-148">En la página **Seleccionar origen de datos** , seleccione [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-148">On the **Select Data Source** page, select [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a2f80-149">En la página, **Seleccione tablas y vistas**, no agregue ninguna tabla, simplemente haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-149">In the page, **Select Tables and Views**, do not add any tables-just click **Next**.</span></span>  
  
5.  <span data-ttu-id="a2f80-150">En la página **finalización del asistente**, escriba el nombre `AllRegions` y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-150">On the page, **Completing the Wizard**, type the name `AllRegions`, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="a2f80-151">Después, haga clic con el botón secundario en la superficie de diseño de la vista del origen de datos en blanco y seleccione **Nueva consulta con nombre**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-151">Next, right-click the blank data source view design surface, and then select **New Named Query**.</span></span>  
  
7.  <span data-ttu-id="a2f80-152">En el cuadro de diálogo **crear consulta con** nombre, en **nombre**, escriba `AllRegions` y para **Descripción**, escriba **suma y promedio de ventas para todos los modelos y regiones**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-152">In the **Create Named Query** dialog box, for **Name**, type `AllRegions`, and for **Description**, type **Sum and average of sales for all models and regions**.</span></span>  
  
8.  <span data-ttu-id="a2f80-153">En el panel de texto SQL, escriba la siguiente instrucción y, a continuación, haga clic en Aceptar:</span><span class="sxs-lookup"><span data-stu-id="a2f80-153">In the SQL text pane, type the following statement and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate,   
    SUM([Quantity]) as SumQty, AVG([Quantity]) as AvgQty,  
    SUM([Amount]) AS SumAmt, AVG([Amount]) AS AvgAmt,  
    'All Regions' as [Region]  
    FROM dbo.vTimeSeries   
    GROUP BY ReportingDate  
    ```  
  
9. <span data-ttu-id="a2f80-154">Haga clic con el botón secundario en la `AllRegions` tabla y seleccione **explorar datos**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-154">Right-click the `AllRegions` table, and then select **Explore Data**.</span></span>  
  
###  <a name="to-create-the-series-data-for-cross-prediction"></a><a name="bkmk_CrossData"></a><span data-ttu-id="a2f80-155">Para crear los datos de la serie para la predicción cruzada</span><span class="sxs-lookup"><span data-stu-id="a2f80-155">To create the series data for cross-prediction</span></span>  
  
1.  <span data-ttu-id="a2f80-156">En el **Explorador de soluciones**, haga clic con el botón secundario en **Vistas del origen de datos**y, a continuación, seleccione **Nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-156">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="a2f80-157">En el Asistente para vistas del origen de datos, realice las selecciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2f80-157">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="a2f80-158">**Origen de datos**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f80-158">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="a2f80-159">**Seleccionar tablas y vistas**: no seleccione ninguna tabla</span><span class="sxs-lookup"><span data-stu-id="a2f80-159">**Select Tables and Views**: Do not select any tables</span></span>  
  
     <span data-ttu-id="a2f80-160">**Nombre**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="a2f80-160">**Name**: `T1000 Pacific Region`</span></span>  
  
3.  <span data-ttu-id="a2f80-161">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="a2f80-161">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="a2f80-162">Haga clic con el botón secundario en la superficie de diseño vacía correspondiente a **T1000 Pacific Region.dsv**y, después, seleccione **Nueva consulta con nombre**.</span><span class="sxs-lookup"><span data-stu-id="a2f80-162">Right-click the empty design surface for **T1000 Pacific Region.dsv**, and then select **New Named Query**.</span></span>  
  
     <span data-ttu-id="a2f80-163">Aparecerá el cuadro de diálogo **Crear consulta con nombre** .</span><span class="sxs-lookup"><span data-stu-id="a2f80-163">The **Create Named Query** dialog box appears.</span></span> <span data-ttu-id="a2f80-164">Vuelva a escribir el nombre y agregue la descripción siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2f80-164">Retype the name, and then add the following description:</span></span>  
  
     <span data-ttu-id="a2f80-165">**Nombre**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="a2f80-165">**Name**: `T1000 Pacific Region`</span></span>  
  
     <span data-ttu-id="a2f80-166">**Descripción**: **filtro `vTimeSeries` por región y modelo**</span><span class="sxs-lookup"><span data-stu-id="a2f80-166">**Description**: **Filter`vTimeSeries`by region and model**</span></span>  
  
5.  <span data-ttu-id="a2f80-167">En el panel de texto, escriba la siguiente consulta y, a continuación, haga clic en Aceptar:</span><span class="sxs-lookup"><span data-stu-id="a2f80-167">In the text pane, type the following query, and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate, ModelRegion, Quantity, Amount  
    FROM dbo.vTimeSeries  
    WHERE (ModelRegion = N'T1000 Pacific')  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a2f80-168">Puesto que deberá crear predicciones para cada serie por separado, puede que desee copiar el texto de la consulta y guardarlo en un archivo de texto para poder usarlo de nuevo con la otra serie de datos.</span><span class="sxs-lookup"><span data-stu-id="a2f80-168">Since you will need to create predictions for each series separately, you might want to copy the query text and save it to a text file so that you can re-use it for the other data series.</span></span>  
  
6.  <span data-ttu-id="a2f80-169">En la superficie de diseño de la vista del origen de datos, haga clic con el botón secundario en T1000 Pacific y seleccione **explorar datos** para comprobar que los datos se filtran correctamente.</span><span class="sxs-lookup"><span data-stu-id="a2f80-169">In the Data Source View design surface, right-click T1000 Pacific, and then select **Explore Data** to verify that the data is filtered correctly.</span></span>  
  
     <span data-ttu-id="a2f80-170">Usará estos datos como la entrada del modelo al crear consultas de predicción cruzada.</span><span class="sxs-lookup"><span data-stu-id="a2f80-170">You will use this data as the input to the model when creating cross-prediction queries.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a2f80-171">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="a2f80-171">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a2f80-172">Predicciones de serie temporal que usan datos actualizados &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a2f80-172">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a2f80-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2f80-173">See Also</span></span>  
 <span data-ttu-id="a2f80-174">[Algoritmo de serie temporal de Microsoft](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="a2f80-174">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 <span data-ttu-id="a2f80-175">[Referencia técnica del algoritmo de serie temporal de Microsoft](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a2f80-175">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="a2f80-176">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="a2f80-176">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  
