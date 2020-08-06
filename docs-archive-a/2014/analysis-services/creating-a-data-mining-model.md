---
title: Crear un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining models, creating
- forecasting [data mining]
- mining models, creating
- clustering [data mining]
- association [data mining]
- data modeling [data mining]
- estimation
- classification [data mining]
ms.assetid: 804b7db3-1f6a-4f73-a81d-bbe02520d7c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1e27739d3733c0b48dc6cff3e83e01f9cb12bce7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673939"
---
# <a name="creating-a-data-mining-model"></a><span data-ttu-id="0e314-102">Crear un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="0e314-102">Creating a Data Mining Model</span></span>
  <span data-ttu-id="0e314-103">El modelado de datos es el paso de la minería de datos donde se generan patrones y tendencias aplicando *algoritmos* a los datos.</span><span class="sxs-lookup"><span data-stu-id="0e314-103">Data modeling is the step of data mining where you build patterns and trends by applying *algorithms* to data.</span></span> <span data-ttu-id="0e314-104">Después, puede utilizar esos patrones para el análisis, o para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="0e314-104">Later you can use those patterns for analysis, or to make predictions.</span></span>  
  
 <span data-ttu-id="0e314-105">Los Complementos de minería de datos para Office admiten la minería de datos a través de asistentes que facilitan la creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="0e314-105">The Data Mining Add-ins for Office support data mining through wizards that make it easy to create models.</span></span> <span data-ttu-id="0e314-106">Los asistentes analizan los datos, identifican las correlaciones, calculan la importancia estadística de todas las variables y seleccionan automáticamente el mejor modelo.</span><span class="sxs-lookup"><span data-stu-id="0e314-106">The wizards analyze the data, identify correlations, compute statistical significance of all variables, and automatically select the best model.</span></span>  
  
 <span data-ttu-id="0e314-107">Aunque esta funcionalidad es tan eficaz como las herramientas de minería de datos que proporciona [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , la combinación de asistentes y la conocida interfaz de Excel facilita la creación, la modificación y el uso de la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="0e314-107">Although this functionality is every bit as powerful as the data mining tools provided by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the combination of wizards and the familiar Excel interface makes it easy to create, modify, and use data mining.</span></span>  
  
## <a name="advanced-data-mining"></a><span data-ttu-id="0e314-108">Avanzados (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e314-108">Advanced (Data Mining)</span></span>  
 <span data-ttu-id="0e314-109">Los asistentes avanzados permiten crear nuevos modelos de minería de datos, basados en los datos almacenados en Excel, mediante el uso de uno de los algoritmos de minería de datos en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e314-109">The Advanced wizards let you create new data mining models, based on data stored in Excel, by using one of the data mining algorithms in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="create-mining-structure"></a><span data-ttu-id="0e314-110">Crear estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="0e314-110">Create Mining Structure</span></span>  
 <span data-ttu-id="0e314-111">El Asistente para crear estructuras de minería de datos le permite generar una nueva estructura de minería de datos que podrá usar como base para varios modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="0e314-111">The Create Mining Structure wizard helps you build a new data mining structure, which you can use as the basis for multiple mining models.</span></span> <span data-ttu-id="0e314-112">El asistente le da la opción de reservar una parte de los datos y usarla como conjunto de prueba; de este modo, podrá evaluar todos los modelos que usan los mismos datos de acuerdo con un estándar de pruebas coherente.</span><span class="sxs-lookup"><span data-stu-id="0e314-112">The wizard gives you the option to set aside a portion of the data to use as a testing set, so that you can evaluate all models that use the same data according to a consistent testing standard.</span></span>  
  
 [<span data-ttu-id="0e314-113">Crear &#40;de estructura de minería de datos SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-113">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
### <a name="add-model-to-structure"></a><span data-ttu-id="0e314-114">Agregar modelo a estructura</span><span class="sxs-lookup"><span data-stu-id="0e314-114">Add Model to Structure</span></span>  
 <span data-ttu-id="0e314-115">El Asistente para agregar modelos a una estructura le permite elegir una estructura de minería de datos existente y crear un nuevo modelo de minería de datos para ella.</span><span class="sxs-lookup"><span data-stu-id="0e314-115">The Add Model to Structure wizard lets you choose an existing data mining structure and create a new data mining model for it.</span></span> <span data-ttu-id="0e314-116">Puede agregar varios modelos de minería de datos a una estructura, cambiar los parámetros o elegir distintos algoritmos de minería de datos, y personalizar la salida.</span><span class="sxs-lookup"><span data-stu-id="0e314-116">You can add multiple mining models to a structure, changing the parameters or choosing different data mining algorithms, and customize the output.</span></span>  
  
 [<span data-ttu-id="0e314-117">Agregar modelo a estructura &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-117">Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;</span></span>](add-model-to-structure-data-mining-add-ins-for-excel.md)  
  
## <a name="analyze-key-influencers-analyze"></a><span data-ttu-id="0e314-118">Analizar influenciadores clave (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-118">Analyze Key Influencers (Analyze)</span></span>  
 <span data-ttu-id="0e314-119">Elija una columna o valor de salida de interés y el algoritmo analizará todos los datos de entrada para identificar los factores que ejercen mayor influencia en el destino.</span><span class="sxs-lookup"><span data-stu-id="0e314-119">You choose a column or output value of interest, and then the algorithm analyzes all the input data to identify the factors that have the most influence on the target.</span></span> <span data-ttu-id="0e314-120">Opcionalmente, puede crear un informe que compare dos valores, de modo que pueda ver cómo cambian los influenciadores.</span><span class="sxs-lookup"><span data-stu-id="0e314-120">Optionally, you can create a report that compares any two values, so that you can see how the influencers change.</span></span>  
  
 <span data-ttu-id="0e314-121">La herramienta **analizar influenciadores clave** usa el algoritmo Bayes Naive de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-121">The **Analyze Key Influencers** tool uses the Microsoft Naïve Bayes algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-122">Analizar influenciadores clave &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-122">Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;</span></span>](analyze-key-influencers-table-analysis-tools-for-excel.md)  
  
## <a name="associate-data-mining"></a><span data-ttu-id="0e314-123">Asociar (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e314-123">Associate (Data Mining)</span></span>  
 <span data-ttu-id="0e314-124">El Asistente para **asociar** genera un modelo de asociación que detecta asociaciones entre elementos que aparecen en varias transacciones: por ejemplo, en el análisis de la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="0e314-124">The **Associate** wizard builds an association model that detects associations between items that appear in multiple transactions: for example, in market basket analysis.</span></span>  
  
 [<span data-ttu-id="0e314-125">Asistente para Asociación &#40;cliente de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-125">Associate Wizard &#40;Data Mining Client for Excel&#41;</span></span>](associate-wizard-data-mining-client-for-excel.md)  
  
## <a name="classify-data-mining"></a><span data-ttu-id="0e314-126">Clasificar (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e314-126">Classify (Data Mining)</span></span>  
 <span data-ttu-id="0e314-127">El Asistente para **clasificar** genera un modelo de clasificación que analiza los factores que han contribuido a un resultado de destino.</span><span class="sxs-lookup"><span data-stu-id="0e314-127">The  **Classify** wizard builds a classification model that analyzes the factors that contributed to a target outcome.</span></span> <span data-ttu-id="0e314-128">Puede utilizar varios algoritmos con este asistente, incluidos los de árboles de decisión, Bayes naive y redes neuronales.</span><span class="sxs-lookup"><span data-stu-id="0e314-128">You can use multiple algorithms with this wizard, including Decision Trees, Naïve Bayes, and Neural Networks.</span></span>  
  
 [<span data-ttu-id="0e314-129">Asistente para clasificar &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-129">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="cluster-data-mining"></a><span data-ttu-id="0e314-130">Clúster (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e314-130">Cluster (Data Mining)</span></span>  
 <span data-ttu-id="0e314-131">El Asistente para **clúster** genera un modelo de agrupación en clústeres que detecta grupos de filas que comparten características similares.</span><span class="sxs-lookup"><span data-stu-id="0e314-131">The **Cluster** wizard builds a clustering model that detects groups of rows that share similar characteristics.</span></span> <span data-ttu-id="0e314-132">La agrupación en clústeres (a veces denominada *segmentación*) es una técnica de aprendizaje sin supervisión que resulta muy útil al tratar de comprender patrones y agrupaciones en nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="0e314-132">Clustering (sometimes called *segmentation*) is an unsupervised learning technique that is very useful when trying to understand patterns and groupings in new data.</span></span>  
  
 <span data-ttu-id="0e314-133">El algoritmo de clústeres de secuencia de Microsoft admite varias modalidades de agrupación en clústeres Expectation maximization (EM) y mediana-K</span><span class="sxs-lookup"><span data-stu-id="0e314-133">The Microsoft Clustering algorithm supports several varieties of both K-means and Expectation maximization (EM) clustering</span></span>  
  
 <span data-ttu-id="0e314-134">[Asistente para clúster &#40;complementos de minería de datos para Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="0e314-134">[Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="detect-categories-analyze"></a><span data-ttu-id="0e314-135">Detectar categorías (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-135">Detect Categories (Analyze)</span></span>  
 <span data-ttu-id="0e314-136">La herramienta **detectar categorías** le permite agregar cualquier conjunto de datos y aplicar la agrupación en clústeres para buscar agrupaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="0e314-136">The **Detect Categories** tool lets you add any data set and apply clustering to find groupings of data.</span></span> <span data-ttu-id="0e314-137">Resulta útil para buscar similitudes y para crear grupos que se van a analizar.</span><span class="sxs-lookup"><span data-stu-id="0e314-137">It's useful for finding similarities and for creating groups to further analyze.</span></span>  
  
 <span data-ttu-id="0e314-138">La herramienta **detectar categorías** usa el algoritmo de clústeres de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-138">The **Detect Categories** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-139">Detectar categorías &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-139">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
## <a name="estimate-data-mining"></a><span data-ttu-id="0e314-140">Estimación (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e314-140">Estimate (Data Mining)</span></span>  
 <span data-ttu-id="0e314-141">El Asistente para estimación de datos genera un modelo de estimación que extrae patrones de datos y los usa para predecir valores numéricos, de fecha o de hora continuos.</span><span class="sxs-lookup"><span data-stu-id="0e314-141">The Estimate wizard builds an estimation model that extracts data patterns and uses the patterns to predict continuous numeric, date, or time values.</span></span> <span data-ttu-id="0e314-142">Utiliza el algoritmo de árboles de decisión de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e314-142">It uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-143">Asistente para estimación &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-143">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="fill-from-example-analyze"></a><span data-ttu-id="0e314-144">Rellenar desde ejemplo (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-144">Fill From Example (Analyze)</span></span>  
 <span data-ttu-id="0e314-145">La herramienta **rellenar desde ejemplo** le ayuda a imputar valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="0e314-145">The **Fill From Example** tool helps you impute missing values.</span></span> <span data-ttu-id="0e314-146">Proporcione algunos ejemplos de cómo deben ser los valores ausentes, y la herramienta creará patrones basados en todos los datos de la tabla; a continuación, recomendará nuevos valores basados en patrones de los datos.</span><span class="sxs-lookup"><span data-stu-id="0e314-146">You provide some examples of what the missing values should be, and the tool builds patterns based on all data in the table, and then recommends new values based on patterns in the data.</span></span>  
  
 <span data-ttu-id="0e314-147">La herramienta **rellenar desde ejemplo** usa el algoritmo de regresión logística de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-147">The **Fill From Example** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-148">Rellenar a partir de ejemplo &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-148">Fill From Example &#40;Table Analysis Tools for Excel&#41;</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-analyze"></a><span data-ttu-id="0e314-149">Pronóstico (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-149">Forecast (Analyze)</span></span>  
 <span data-ttu-id="0e314-150">La herramienta **previsión** toma los datos que cambian con el tiempo y predice valores futuros.</span><span class="sxs-lookup"><span data-stu-id="0e314-150">The **Forecast** tool takes data that changes over time, and predicts future values.</span></span>  
  
 <span data-ttu-id="0e314-151">La herramienta **pronóstico** utiliza el algoritmo de serie temporal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-151">The **Forecast** tool uses the Microsoft Time Series algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-152">Previsión &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-152">Forecast &#40;Table Analysis Tools for Excel&#41;</span></span>](forecast-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-data-mining"></a><span data-ttu-id="0e314-153">Pronóstico (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e314-153">Forecast (Data Mining)</span></span>  
 <span data-ttu-id="0e314-154">El Asistente para **pronóstico** genera un modelo de pronóstico que detecta patrones en una serie de celdas y, a continuación, pronostica valores adicionales.</span><span class="sxs-lookup"><span data-stu-id="0e314-154">The **Forecast** wizard builds a forecasting model that detects patterns in a series of cells, and then forecasts additional values.</span></span>  
  
 [<span data-ttu-id="0e314-155">Asistente para previsión &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-155">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="highlight-exceptions-analyze"></a><span data-ttu-id="0e314-156">Resaltar excepciones (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-156">Highlight Exceptions (Analyze)</span></span>  
 <span data-ttu-id="0e314-157">La herramienta **resaltar excepciones** analiza patrones en una tabla de datos y busca filas y valores que no se ajustan al patrón.</span><span class="sxs-lookup"><span data-stu-id="0e314-157">The **Highlight Exceptions** tool analyzes patterns in a table of data and finds rows and values that don't fit the pattern.</span></span> <span data-ttu-id="0e314-158">Seguidamente, puede revisarlos, corregirlos y volver a ejecutar el modelo o marcar valores para acciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0e314-158">You can then review and correct them and rerun the model, or flag values for later action.</span></span>  
  
 <span data-ttu-id="0e314-159">La herramienta **resaltar excepciones** usa el algoritmo de clústeres de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-159">The **Highlight Exceptions** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-160">Resaltar excepciones &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-160">Highlight Exceptions &#40;Table Analysis Tools for Excel&#41;</span></span>](highlight-exceptions-table-analysis-tools-for-excel.md)  
  
## <a name="prediction-calculator-analyze"></a><span data-ttu-id="0e314-161">Cálculo de predicción (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-161">Prediction Calculator (Analyze)</span></span>  
 <span data-ttu-id="0e314-162">Esta herramienta crea un modelo que analiza los factores que producen los resultados buscados, y después predice un resultado para cualquier nueva entrada, en función de criterios derivados de estos patrones. También genera una hoja de cálculo interactiva de toma de decisiones que permite puntuar nuevas entradas.</span><span class="sxs-lookup"><span data-stu-id="0e314-162">This tool creates a model that analyzes the factors leading to target outcomes, and then predicts a result for any new input, based on criteria derived from these patterns It also generates an interactive decision making worksheet that lets you easily score new inputs.</span></span> <span data-ttu-id="0e314-163">También puede crear una versión impresa de la hoja de cálculo de puntuaciones para su uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0e314-163">You can also create a printed version of the scoring worksheet for offline use.</span></span>  
  
 <span data-ttu-id="0e314-164">La herramienta **cálculo de predicción** usa el algoritmo de regresión logística de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-164">The **Prediction Calculator** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-165">Cálculo de predicción &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-165">Prediction Calculator &#40;Table Analysis Tools for Excel&#41;</span></span>](prediction-calculator-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-goal-seek-analyze"></a><span data-ttu-id="0e314-166">Escenario: Buscar objetivo (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-166">Scenario: Goal Seek (Analyze)</span></span>  
 <span data-ttu-id="0e314-167">En la herramienta **Buscar objetivo** , especifique un valor de destino y la herramienta identifica los factores subyacentes que deben cambiar para cumplir ese destino.</span><span class="sxs-lookup"><span data-stu-id="0e314-167">In the **Goal Seek** tool, you specify a target value, and the tool identifies the underlying factors that must change to meet that target.</span></span> <span data-ttu-id="0e314-168">Por ejemplo, si sabe que debe aumentar la satisfacción de las llamadas en un 20 %, puede pedir al modelo que prediga los factores que deben cambiar para producir ese objetivo.</span><span class="sxs-lookup"><span data-stu-id="0e314-168">For example, if you know that you must increase call satisfaction by 20%, you can ask the model to predict the factors that should change to produce that goal.</span></span>  
  
 <span data-ttu-id="0e314-169">La herramienta **Buscar objetivo** usa el algoritmo de regresión logística de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-169">The **Goal Seek** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="0e314-170">detalles</span><span class="sxs-lookup"><span data-stu-id="0e314-170">details</span></span>  
  
 [<span data-ttu-id="0e314-171">Escenario de búsqueda de objetivo &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-171">Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](goal-seek-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-what-if-scenario-analyze"></a><span data-ttu-id="0e314-172">Escenario: Escenario Y si (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-172">Scenario: What-If Scenario (Analyze)</span></span>  
 <span data-ttu-id="0e314-173">La herramienta de **análisis de si** complementa la herramienta **Buscar objetivo** .</span><span class="sxs-lookup"><span data-stu-id="0e314-173">The **What-If Analysis** tool complements the **Goal Seek** tool.</span></span> <span data-ttu-id="0e314-174">Con esta herramienta, se introduce el valor que se desea cambiar y el modelo predice si el cambio será suficiente para obtener el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="0e314-174">With this tool, you entered the value you want to change, and the model predicts whether that change will be sufficient to achieve the desired outcome.</span></span> <span data-ttu-id="0e314-175">Por ejemplo, podría solicitar al modelo que infiera si la adición de un operador de llamadas adicional incrementaría la satisfacción del cliente en un punto.</span><span class="sxs-lookup"><span data-stu-id="0e314-175">For example, you might ask the model to infer whether adding one extra call operator would increase customer satisfaction by one point.</span></span>  
  
 <span data-ttu-id="0e314-176">La herramienta y **si** usa el algoritmo de regresión logística de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-176">The **What-If** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-177">Escenario y si &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-177">What-If Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](what-if-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="shopping-basket-analysis-analyze"></a><span data-ttu-id="0e314-178">Análisis de la cesta de compras (Analizar)</span><span class="sxs-lookup"><span data-stu-id="0e314-178">Shopping Basket Analysis (Analyze)</span></span>  
 <span data-ttu-id="0e314-179">La herramienta de análisis de la **cesta de compras** crea grupos de productos que se suelen comprar juntos, para identificar patrones que se pueden utilizar en las ventas cruzadas o en la venta de ventas.</span><span class="sxs-lookup"><span data-stu-id="0e314-179">The **Shopping Basket Analysis** tool creates groups of products that are frequently purchased together, to identify patterns that can be used in cross-selling or up-selling.</span></span> <span data-ttu-id="0e314-180">También genera informes basados en el precio y el costo de paquetes de productos relacionados, para ayudar a la toma de decisiones.</span><span class="sxs-lookup"><span data-stu-id="0e314-180">It also generates reports based on the price and cost of related product bundles, to aid in decision-making.</span></span>  
  
 <span data-ttu-id="0e314-181">También puede utilizar esta herramienta para los eventos que ocurren juntos con frecuencia, los factores que dan como resultado un diagnóstico o para cualquier otro posible conjunto de causas y resultados.</span><span class="sxs-lookup"><span data-stu-id="0e314-181">You can also use this tool for events that frequently occur together, factors leading to a diagnosis, or any other set of potential causes and outcomes.</span></span>  
  
 <span data-ttu-id="0e314-182">La herramienta de análisis de la **cesta de compras** utiliza el algoritmo de Asociación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e314-182">The **Shopping Basket Analysis** tool uses the Microsoft Association algorithm.</span></span>  
  
 [<span data-ttu-id="0e314-183">Análisis de la cesta de compras &#40;tabla análisis para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-183">Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;</span></span>](shopping-basket-analysis-table-analysistools-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e314-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e314-184">See Also</span></span>  
 <span data-ttu-id="0e314-185">[Explorar y limpiar datos](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="0e314-185">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="0e314-186">[Validar modelos y usar modelos para la predicción &#40;complementos de minería de datos para Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0e314-186">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="0e314-187">Implementar y escalar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e314-187">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
