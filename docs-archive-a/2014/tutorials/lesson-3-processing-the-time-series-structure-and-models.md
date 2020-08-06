---
title: 'Lección 3: procesar la estructura y los modelos de serie temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 16e27b57-eae1-47a7-a02c-47b6ed487d87
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 493d27c9836eb765c655eba5bbb004e4d48cde40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746642"
---
# <a name="lesson-3-processing-the-time-series-structure-and-models"></a><span data-ttu-id="b2fae-102">Lección 3: Procesamiento de la estructura de serie temporal y los modelos</span><span class="sxs-lookup"><span data-stu-id="b2fae-102">Lesson 3: Processing the Time Series Structure and Models</span></span>
  <span data-ttu-id="b2fae-103">En esta lección, usará la instrucción [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) para procesar las estructuras de minería de datos de serie temporal y los modelos de minería de datos que ha creado.</span><span class="sxs-lookup"><span data-stu-id="b2fae-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement to process the time series mining structures and mining models that you created.</span></span>  
  
 <span data-ttu-id="b2fae-104">Al procesar una estructura de minería de datos, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lee los datos de origen y genera las estructuras que admiten los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b2fae-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="b2fae-105">Siempre tiene que procesar un modelo y estructura de minería de datos después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="b2fae-105">You always have to process a mining model and structure when you first create it.</span></span> <span data-ttu-id="b2fae-106">Si especifica una estructura de minería de datos con INSERT INTO, la instrucción procesa la estructura de minería de datos y todos sus modelos asociados.</span><span class="sxs-lookup"><span data-stu-id="b2fae-106">If you specify the mining structure when using INSERT INTO, the statement processes the mining structure and all its associated mining models.</span></span>  
  
 <span data-ttu-id="b2fae-107">Si agrega un modelo de minería de datos a una estructura de minería de datos que ya se ha procesado, puede usar la instrucción `INSERT INTO MINING MODEL` para procesar solo el nuevo modelo de minería de datos con los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="b2fae-107">When you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to process just the new mining model by using the existing data.</span></span>  
  
 <span data-ttu-id="b2fae-108">Para obtener más información sobre el procesamiento de modelos de minería de datos, vea [requisitos y consideraciones de procesamiento &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b2fae-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="b2fae-109">Instrucción INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="b2fae-109">INSERT INTO Statement</span></span>  
 <span data-ttu-id="b2fae-110">Para entrenar la estructura de minería de datos de serie temporal y todos sus modelos de minería de datos asociados, utilice la instrucción [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="b2fae-110">In order to train the time series mining structure and all its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="b2fae-111">El código de la instrucción se puede dividir en las partes siguientes.</span><span class="sxs-lookup"><span data-stu-id="b2fae-111">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="b2fae-112">Identificación de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="b2fae-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="b2fae-113">Visualización en una lista de las columnas de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="b2fae-113">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="b2fae-114">Definición de los datos de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="b2fae-114">Defining the training data</span></span>  
  
 <span data-ttu-id="b2fae-115">A continuación, se incluye un ejemplo genérico de la instrucción `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="b2fae-115">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="b2fae-116">La primera línea del código identifica la estructura de minería de datos que se entrenará:</span><span class="sxs-lookup"><span data-stu-id="b2fae-116">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="b2fae-117">Las líneas siguientes del código especifican las columnas definidas por la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b2fae-117">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="b2fae-118">Debe incluir en la lista cada una de las columnas de la estructura de minería de datos, y cada columna debe estar asignada a una columna incluida en los datos de la consulta de origen:</span><span class="sxs-lookup"><span data-stu-id="b2fae-118">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="b2fae-119">Las últimas líneas del código definen los datos que se utilizarán para entrenar la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b2fae-119">The final lines of the code define the data that will be used to train the mining structure.</span></span>  
  
```  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="b2fae-120">En esta lección usará `OPENQUERY` para definir los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="b2fae-120">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="b2fae-121">Para obtener más información sobre otros métodos para definir una consulta en los datos de origen, vea [&#60;&#62;de consultas de datos de origen ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="b2fae-121">For more information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="b2fae-122">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="b2fae-122">Lesson Tasks</span></span>  
 <span data-ttu-id="b2fae-123">En esta lección realizará la tarea siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2fae-123">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="b2fae-124">Procesar la estructura de minería de datos Forecasting_MIXED_Structure</span><span class="sxs-lookup"><span data-stu-id="b2fae-124">Process the mining structure Forecasting_MIXED_Structure</span></span>  
  
-   <span data-ttu-id="b2fae-125">Procesar los modelos de minería de datos relacionados Forecasting_MIXED, Forecasting_ARIMA y Forecasting_ARTXP</span><span class="sxs-lookup"><span data-stu-id="b2fae-125">Process the related mining models Forecasting_MIXED, Forecasting_ARIMA, and Forecasting_ARTXP</span></span>  
  
## <a name="processing-the-time-series-mining-structure"></a><span data-ttu-id="b2fae-126">Procesar la estructura de minería de datos de serie temporal</span><span class="sxs-lookup"><span data-stu-id="b2fae-126">Processing the Time Series Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-and-related-mining-models-by-using-insert-into"></a><span data-ttu-id="b2fae-127">Para procesar la estructura de minería de datos y los modelos relacionados mediante INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="b2fae-127">To process the mining structure and related mining models by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="b2fae-128">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b2fae-128">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b2fae-129">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="b2fae-129">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="b2fae-130">Copie el ejemplo genérico de la instrucción INSERT INTO en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="b2fae-130">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b2fae-131">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2fae-131">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="b2fae-132">por:</span><span class="sxs-lookup"><span data-stu-id="b2fae-132">with:</span></span>  
  
    ```  
    Forecasting_MIXED_Structure  
    ```  
  
4.  <span data-ttu-id="b2fae-133">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2fae-133">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="b2fae-134">por:</span><span class="sxs-lookup"><span data-stu-id="b2fae-134">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]   
    ```  
  
5.  <span data-ttu-id="b2fae-135">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2fae-135">Replace the following:</span></span>  
  
    ```  
    OPENQUERY(<source data definition>)  
    ```  
  
     <span data-ttu-id="b2fae-136">por:</span><span class="sxs-lookup"><span data-stu-id="b2fae-136">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2008R2],'SELECT [ReportingDate], [ModelRegion], [Quantity], [Amount]  
    FROM vTimeSeries ORDER BY [ReportingDate]')  
    ```  
  
     <span data-ttu-id="b2fae-137">La consulta de origen hace referencia al [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origen de datos definido en el proyecto de ejemplo IntermediateTutorial.</span><span class="sxs-lookup"><span data-stu-id="b2fae-137">The source query references the  [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the IntermediateTutorial sample project.</span></span> <span data-ttu-id="b2fae-138">Utiliza este origen de datos para tener acceso a la vista vTimeSeries.</span><span class="sxs-lookup"><span data-stu-id="b2fae-138">It uses this data source to access the view vTimeSeries.</span></span> <span data-ttu-id="b2fae-139">Esta vista contiene los datos de origen que se utilizarán para entrenar el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b2fae-139">This view contains the source data that will be used to train the mining model.</span></span> <span data-ttu-id="b2fae-140">Si no está familiarizado con este proyecto o con estas vistas, vea[Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b2fae-140">If you are not familiar with this project or this views, see[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="b2fae-141">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2fae-141">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Forecasting_MIXED_Structure]  
    (  
       [ReportingDate],[ModelRegion],[Quantity],[Amount])  
    )  
    OPENQUERY(  
    [Adventure Works DW 2008R2],  
    'SELECT [ReportingDate],[ModelRegion],[Quantity],[Amount] FROM vTimeSeries ORDER BY [ReportingDate]'  
    )   
    ```  
  
6.  <span data-ttu-id="b2fae-142">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="b2fae-142">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="b2fae-143">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `ProcessForecastingAll.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b2fae-143">In the **Save As** dialog box, browse to the appropriate folder, and name the file `ProcessForecastingAll.dmx`.</span></span>  
  
8.  <span data-ttu-id="b2fae-144">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="b2fae-144">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="b2fae-145">Cuando la consulta termine de ejecutarse, puede crear las predicciones mediante los modelos de minería de datos procesados.</span><span class="sxs-lookup"><span data-stu-id="b2fae-145">After the query has finished running, you can create predictions by using the processed mining models.</span></span> <span data-ttu-id="b2fae-146">En la lección siguiente, creará varias predicciones basadas en los modelos de minería de datos que ha creado.</span><span class="sxs-lookup"><span data-stu-id="b2fae-146">In the next lesson, you will create several predictions based on the mining models that you created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b2fae-147">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="b2fae-147">Next Lesson</span></span>  
 [<span data-ttu-id="b2fae-148">Lección 4: Creación de predicciones de serie temporal con DMX</span><span class="sxs-lookup"><span data-stu-id="b2fae-148">Lesson 4: Creating Time Series Predictions Using DMX</span></span>](../../2014/tutorials/lesson-4-creating-time-series-predictions-using-dmx.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2fae-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2fae-149">See Also</span></span>  
 <span data-ttu-id="b2fae-150">[Requisitos y consideraciones de procesamiento &#40;la minería de datos&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b2fae-150">[Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span></span>  
 <span data-ttu-id="b2fae-151">[&#60;consulta de datos de origen&#62;](/sql/dmx/source-data-query) </span><span class="sxs-lookup"><span data-stu-id="b2fae-151">[&#60;source data query&#62;](/sql/dmx/source-data-query) </span></span>  
 [<span data-ttu-id="b2fae-152">OPENQUERY &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b2fae-152">OPENQUERY &#40;DMX&#41;</span></span>](/sql/dmx/source-data-query-openquery)  
  
  
