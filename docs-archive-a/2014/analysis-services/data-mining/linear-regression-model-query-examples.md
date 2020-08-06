---
title: Ejemplos de consultas de modelos de regresión lineal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- content queries [DMX]
ms.assetid: fd3cf312-57a1-44b6-b772-fce6fc1c26d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 02d4b7309d7b5ea3d6295089f0fb2e778b1c9b4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677303"
---
# <a name="linear-regression-model-query-examples"></a><span data-ttu-id="49f7d-102">Ejemplos de consultas de modelos de regresión lineal</span><span class="sxs-lookup"><span data-stu-id="49f7d-102">Linear Regression Model Query Examples</span></span>
  <span data-ttu-id="49f7d-103">Cuando se crea una consulta en un modelo de minería de datos, puede tratarse de una consulta de contenido, que proporciona detalles de los patrones detectados durante el análisis, o de una consulta de predicción, que utiliza los patrones del modelo para realizar predicciones de los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="49f7d-103">When you create a query against a data mining model, you can create a content query, which provides details about the patterns discovered in analysis, or you can create a prediction query, which uses the patterns in the model to make predictions for new data.</span></span> <span data-ttu-id="49f7d-104">Por ejemplo, una consulta de contenido podría proporcionar detalles adicionales sobre la fórmula de regresión, mientras que una consulta de predicción podría indicar si un nuevo punto de datos se ajusta al modelo.</span><span class="sxs-lookup"><span data-stu-id="49f7d-104">For example, a content query might provide additional details about the regression formula, while a prediction query might tell you if a new data point fits the model.</span></span> <span data-ttu-id="49f7d-105">También se pueden recuperar metadatos sobre el modelo mediante una consulta.</span><span class="sxs-lookup"><span data-stu-id="49f7d-105">You can also retrieve metadata about the model by using a query.</span></span>  
  
 <span data-ttu-id="49f7d-106">En esta sección se explica cómo crear consultas para los modelos que se basan en el algoritmo de regresión lineal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="49f7d-106">This section explains how to create queries for models that are based on the Microsoft Linear Regression algorithm.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49f7d-107">Dado que la regresión lineal está basada en un caso especial del algoritmo de árboles de decisión de Microsoft, hay muchas similitudes y algunos modelos de árbol de decisión que utilizan atributos de predicción continuos pueden contener fórmulas de regresión.</span><span class="sxs-lookup"><span data-stu-id="49f7d-107">Because linear regression is based on a special case of the Microsoft Decision Trees algorithm, there are many similarities, and some decision tree models that use continuous predictable attributes can contain regression formulas.</span></span> <span data-ttu-id="49f7d-108">Para más información, vea [Referencia técnica del algoritmo de árboles de decisión de Microsoft](microsoft-decision-trees-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="49f7d-108">For more information, see [Microsoft Decision Trees Algorithm Technical Reference](microsoft-decision-trees-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="49f7d-109">**Consultas de contenido**</span><span class="sxs-lookup"><span data-stu-id="49f7d-109">**Content queries**</span></span>  
  
 [<span data-ttu-id="49f7d-110">Usar el conjunto de filas de esquema de minería de datos para determinar los parámetros que se usan para un modelo</span><span class="sxs-lookup"><span data-stu-id="49f7d-110">Using the Data Mining Schema Rowset to determine parameters used for a model</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="49f7d-111">Usar DMX para devolver la fórmula de regresión del modelo</span><span class="sxs-lookup"><span data-stu-id="49f7d-111">Using DMX to return the regression formula for the model</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="49f7d-112">Devolver solo el coeficiente para el modelo</span><span class="sxs-lookup"><span data-stu-id="49f7d-112">Returning only the coefficient for the model</span></span>](#bkmk_Query3)  
  
 <span data-ttu-id="49f7d-113">**Consultas de predicción**</span><span class="sxs-lookup"><span data-stu-id="49f7d-113">**Prediction queries**</span></span>  
  
 [<span data-ttu-id="49f7d-114">Predecir los ingresos utilizando una consulta singleton</span><span class="sxs-lookup"><span data-stu-id="49f7d-114">Predicting income using a singleton query</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="49f7d-115">Usar funciones de predicción con un modelo de regresión</span><span class="sxs-lookup"><span data-stu-id="49f7d-115">Using prediction functions with a regression model</span></span>](#bkmk_Query5)  
  
##  <a name="finding-information-about-the-linear-regression-model"></a><a name="bkmk_top"></a><span data-ttu-id="49f7d-116">Buscar información sobre el modelo de regresión lineal</span><span class="sxs-lookup"><span data-stu-id="49f7d-116">Finding Information about the Linear Regression Model</span></span>  
 <span data-ttu-id="49f7d-117">La estructura de un modelo de regresión lineal es sumamente simple: el modelo de minería de datos representa los datos como un nodo único, que define la fórmula de regresión.</span><span class="sxs-lookup"><span data-stu-id="49f7d-117">The structure of a linear regression model is extremely simple: the mining model represents the data as a single node, which defines the regression formula.</span></span> <span data-ttu-id="49f7d-118">Para obtener más información, vea [Contenido del modelo de minería de datos para los modelos de regresión logística &#40;Analysis Services - Minería de datos&#41;](mining-model-content-for-logistic-regression-models.md).</span><span class="sxs-lookup"><span data-stu-id="49f7d-118">For more information, see [Mining Model Content for Logistic Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span></span>  
  
 [<span data-ttu-id="49f7d-119">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-119">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-1-using-the-data-mining-schema-rowset-to-determine-parameters-used-for-a-model"></a><a name="bkmk_Query1"></a><span data-ttu-id="49f7d-120">Consulta de ejemplo 1: usar el conjunto de filas de esquema de minería de datos para determinar los parámetros usados para un modelo</span><span class="sxs-lookup"><span data-stu-id="49f7d-120">Sample Query 1: Using the Data Mining Schema Rowset to Determine Parameters Used for a Model</span></span>  
 <span data-ttu-id="49f7d-121">Al consultar el conjunto de filas de esquema de minería de datos, puede buscar los metadatos acerca del modelo.</span><span class="sxs-lookup"><span data-stu-id="49f7d-121">By querying the data mining schema rowset, you can find metadata about the model.</span></span> <span data-ttu-id="49f7d-122">Podría incluirse cuándo se creó el modelo, cuándo se procesó en último lugar, el nombre de la estructura de minería de datos en la que se basa y el nombre de la columna que se usa como atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="49f7d-122">This might include when the model was created, when the model was last processed, the name of the mining structure that the model is based on, and the name of the column designated as the predictable attribute.</span></span> <span data-ttu-id="49f7d-123">También se pueden devolver los parámetros que se utilizaron cuando se creó el modelo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="49f7d-123">You can also return the parameters that were used when the model was first created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM_PredictIncome'  
```  
  
 <span data-ttu-id="49f7d-124">Resultados del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49f7d-124">Sample results:</span></span>  
  
|<span data-ttu-id="49f7d-125">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="49f7d-125">MINING_PARAMETERS</span></span>|  
|------------------------|  
|<span data-ttu-id="49f7d-126">COMPLEXITY_PENALTY=0.9,</span><span class="sxs-lookup"><span data-stu-id="49f7d-126">COMPLEXITY_PENALTY=0.9,</span></span><br /><br /> <span data-ttu-id="49f7d-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="49f7d-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="49f7d-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="49f7d-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="49f7d-129">MINIMUM_SUPPORT=10,</span><span class="sxs-lookup"><span data-stu-id="49f7d-129">MINIMUM_SUPPORT=10,</span></span><br /><br /> <span data-ttu-id="49f7d-130">SCORE_METHOD=4,</span><span class="sxs-lookup"><span data-stu-id="49f7d-130">SCORE_METHOD=4,</span></span><br /><br /> <span data-ttu-id="49f7d-131">SPLIT_METHOD=3,</span><span class="sxs-lookup"><span data-stu-id="49f7d-131">SPLIT_METHOD=3,</span></span><br /><br /> <span data-ttu-id="49f7d-132">FORCE_REGRESSOR=</span><span class="sxs-lookup"><span data-stu-id="49f7d-132">FORCE_REGRESSOR=</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="49f7d-133">La configuración del parámetro, "`FORCE_REGRESSOR =` ", indica que el valor actual del parámetro FORCE_REGRESSOR es NULL.</span><span class="sxs-lookup"><span data-stu-id="49f7d-133">The parameter setting, "`FORCE_REGRESSOR =` ", indicates that the current value for the FORCE_REGRESSOR parameter is null.</span></span>  
  
 [<span data-ttu-id="49f7d-134">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-134">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-2-retrieving-the-regression-formula-for-the-model"></a><a name="bkmk_Query2"></a><span data-ttu-id="49f7d-135">Consulta de ejemplo 2: recuperar la fórmula de regresión del modelo</span><span class="sxs-lookup"><span data-stu-id="49f7d-135">Sample Query 2: Retrieving the Regression Formula for the Model</span></span>  
 <span data-ttu-id="49f7d-136">La consulta siguiente devuelve el contenido del modelo de minería de datos de un modelo de regresión lineal que se generó utilizando el mismo origen de datos que Targeted Mailing, que se utilizó en el [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="49f7d-136">The following query returns the mining model content for a linear regression model that was built by using the same Targeted Mailing data source that was used in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="49f7d-137">Este modelo predice los ingresos de los clientes en función de la edad.</span><span class="sxs-lookup"><span data-stu-id="49f7d-137">This model predicts customer income based on age.</span></span>  
  
 <span data-ttu-id="49f7d-138">La consulta devuelve el contenido del nodo que contiene la fórmula de regresión.</span><span class="sxs-lookup"><span data-stu-id="49f7d-138">The query returns the contents of the node that contains the regression formula.</span></span> <span data-ttu-id="49f7d-139">Cada variable y coeficiente están almacenados en una fila independiente de la tabla NODE_DISTRIBUTION anidada.</span><span class="sxs-lookup"><span data-stu-id="49f7d-139">Each variable and coefficient is stored in a separate row of the nested NODE_DISTRIBUTION table.</span></span> <span data-ttu-id="49f7d-140">Si desea ver la fórmula de regresión completa, utilice el [visor de árboles de Microsoft](browse-a-model-using-the-microsoft-tree-viewer.md), haga clic en el nodo **(todos)** y abra la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="49f7d-140">If you want to view the complete regression formula, use the [Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), click the **(All)** node, and open the **Mining Legend**.</span></span>  
  
```  
SELECT FLATTENED NODE_DISTRIBUTION as t  
FROM LR_PredictIncome.CONTENT  
```  
  
> [!NOTE]  
>  <span data-ttu-id="49f7d-141">Si hace referencia a columnas individuales de la tabla anidada con una consulta como `SELECT <column name> from NODE_DISTRIBUTION`, algunas columnas (como **SUPPORT** o **PROBABILITY**) tienen que escribirse entre corchetes para distinguirlas de las palabras clave reservadas del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="49f7d-141">If you reference individual columns of the nested table by using a query such as `SELECT <column name> from NODE_DISTRIBUTION`, some columns, such as **SUPPORT** or **PROBABILITY**, must be enclosed in brackets to distinguish them from reserved keywords of the same name.</span></span>  
  
 <span data-ttu-id="49f7d-142">Resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="49f7d-142">Expected results:</span></span>  
  
|<span data-ttu-id="49f7d-143">T.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="49f7d-143">t.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="49f7d-144">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="49f7d-144">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="49f7d-145">t.SUPPORT</span><span class="sxs-lookup"><span data-stu-id="49f7d-145">t.SUPPORT</span></span>|<span data-ttu-id="49f7d-146">t.PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="49f7d-146">t.PROBABILITY</span></span>|<span data-ttu-id="49f7d-147">t.VARIANCE</span><span class="sxs-lookup"><span data-stu-id="49f7d-147">t.VARIANCE</span></span>|<span data-ttu-id="49f7d-148">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="49f7d-148">t.VALUETYPE</span></span>|  
|-----------------------|------------------------|---------------|-------------------|----------------|-----------------|  
|<span data-ttu-id="49f7d-149">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="49f7d-149">Yearly Income</span></span>|<span data-ttu-id="49f7d-150">Missing</span><span class="sxs-lookup"><span data-stu-id="49f7d-150">Missing</span></span>|<span data-ttu-id="49f7d-151">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-151">0</span></span>|<span data-ttu-id="49f7d-152">0.000457142857142857</span><span class="sxs-lookup"><span data-stu-id="49f7d-152">0.000457142857142857</span></span>|<span data-ttu-id="49f7d-153">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-153">0</span></span>|<span data-ttu-id="49f7d-154">1</span><span class="sxs-lookup"><span data-stu-id="49f7d-154">1</span></span>|  
|<span data-ttu-id="49f7d-155">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="49f7d-155">Yearly Income</span></span>|<span data-ttu-id="49f7d-156">57220.8876687257</span><span class="sxs-lookup"><span data-stu-id="49f7d-156">57220.8876687257</span></span>|<span data-ttu-id="49f7d-157">17484</span><span class="sxs-lookup"><span data-stu-id="49f7d-157">17484</span></span>|<span data-ttu-id="49f7d-158">0.999542857142857</span><span class="sxs-lookup"><span data-stu-id="49f7d-158">0.999542857142857</span></span>|<span data-ttu-id="49f7d-159">1041275619.52776</span><span class="sxs-lookup"><span data-stu-id="49f7d-159">1041275619.52776</span></span>|<span data-ttu-id="49f7d-160">3</span><span class="sxs-lookup"><span data-stu-id="49f7d-160">3</span></span>|  
|<span data-ttu-id="49f7d-161">Age</span><span class="sxs-lookup"><span data-stu-id="49f7d-161">Age</span></span>|<span data-ttu-id="49f7d-162">471.687717702463</span><span class="sxs-lookup"><span data-stu-id="49f7d-162">471.687717702463</span></span>|<span data-ttu-id="49f7d-163">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-163">0</span></span>|<span data-ttu-id="49f7d-164">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-164">0</span></span>|<span data-ttu-id="49f7d-165">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="49f7d-165">126.969442359327</span></span>|<span data-ttu-id="49f7d-166">7</span><span class="sxs-lookup"><span data-stu-id="49f7d-166">7</span></span>|  
|<span data-ttu-id="49f7d-167">Age</span><span class="sxs-lookup"><span data-stu-id="49f7d-167">Age</span></span>|<span data-ttu-id="49f7d-168">234.680904692439</span><span class="sxs-lookup"><span data-stu-id="49f7d-168">234.680904692439</span></span>|<span data-ttu-id="49f7d-169">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-169">0</span></span>|<span data-ttu-id="49f7d-170">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-170">0</span></span>|<span data-ttu-id="49f7d-171">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-171">0</span></span>|<span data-ttu-id="49f7d-172">8</span><span class="sxs-lookup"><span data-stu-id="49f7d-172">8</span></span>|  
|<span data-ttu-id="49f7d-173">Age</span><span class="sxs-lookup"><span data-stu-id="49f7d-173">Age</span></span>|<span data-ttu-id="49f7d-174">45.4269617936399</span><span class="sxs-lookup"><span data-stu-id="49f7d-174">45.4269617936399</span></span>|<span data-ttu-id="49f7d-175">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-175">0</span></span>|<span data-ttu-id="49f7d-176">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-176">0</span></span>|<span data-ttu-id="49f7d-177">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="49f7d-177">126.969442359327</span></span>|<span data-ttu-id="49f7d-178">9</span><span class="sxs-lookup"><span data-stu-id="49f7d-178">9</span></span>|  
||<span data-ttu-id="49f7d-179">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="49f7d-179">35793.5477381267</span></span>|<span data-ttu-id="49f7d-180">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-180">0</span></span>|<span data-ttu-id="49f7d-181">0</span><span class="sxs-lookup"><span data-stu-id="49f7d-181">0</span></span>|<span data-ttu-id="49f7d-182">1012968919.28372</span><span class="sxs-lookup"><span data-stu-id="49f7d-182">1012968919.28372</span></span>|<span data-ttu-id="49f7d-183">11</span><span class="sxs-lookup"><span data-stu-id="49f7d-183">11</span></span>|  
  
 <span data-ttu-id="49f7d-184">En la comparación, en la **Leyenda de minería de datos**, la fórmula de regresión aparece como sigue:</span><span class="sxs-lookup"><span data-stu-id="49f7d-184">In comparison, in the **Mining Legend**, the regression formula appears as follows:</span></span>  
  
 <span data-ttu-id="49f7d-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span><span class="sxs-lookup"><span data-stu-id="49f7d-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span></span>  
  
 <span data-ttu-id="49f7d-186">Puede ver que, en la **Leyenda de minería de datos**, algunos números se redondean, pero la tabla NODE_DISTRIBUTION y la **Leyenda de minería de datos** contienen básicamente los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="49f7d-186">You can see that in the **Mining Legend**, some numbers are rounded; however, the NODE_DISTRIBUTION table and the **Mining Legend** essentially contain the same values.</span></span>  
  
 <span data-ttu-id="49f7d-187">Los valores de la columna VALUETYPE indican qué tipo de información contiene cada fila, lo que resulta útil si los resultados se procesan mediante programación.</span><span class="sxs-lookup"><span data-stu-id="49f7d-187">The values in the VALUETYPE column tell you what kind of information is contained in each row, which is useful if you are processing the results programmatically.</span></span> <span data-ttu-id="49f7d-188">En la tabla siguiente se muestran los tipos de valores que se generan para una fórmula de regresión lineal.</span><span class="sxs-lookup"><span data-stu-id="49f7d-188">The following table shows the value types that are output for a linear regression formula.</span></span>  
  
|<span data-ttu-id="49f7d-189">VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="49f7d-189">VALUETYPE</span></span>|  
|---------------|  
|<span data-ttu-id="49f7d-190">1 (ausente)</span><span class="sxs-lookup"><span data-stu-id="49f7d-190">1 (Missing)</span></span>|  
|<span data-ttu-id="49f7d-191">3 (continuo)</span><span class="sxs-lookup"><span data-stu-id="49f7d-191">3 (Continuous)</span></span>|  
|<span data-ttu-id="49f7d-192">7 (coeficiente)</span><span class="sxs-lookup"><span data-stu-id="49f7d-192">7 (Coefficient)</span></span>|  
|<span data-ttu-id="49f7d-193">8 (ganancia de puntuación)</span><span class="sxs-lookup"><span data-stu-id="49f7d-193">8 (Score Gain)</span></span>|  
|<span data-ttu-id="49f7d-194">9 (estadísticas)</span><span class="sxs-lookup"><span data-stu-id="49f7d-194">9 (Statistics)</span></span>|  
|<span data-ttu-id="49f7d-195">7 (coeficiente)</span><span class="sxs-lookup"><span data-stu-id="49f7d-195">7 (Coefficient)</span></span>|  
|<span data-ttu-id="49f7d-196">8 (ganancia de puntuación)</span><span class="sxs-lookup"><span data-stu-id="49f7d-196">8 (Score Gain)</span></span>|  
|<span data-ttu-id="49f7d-197">9 (estadísticas)</span><span class="sxs-lookup"><span data-stu-id="49f7d-197">9 (Statistics)</span></span>|  
|<span data-ttu-id="49f7d-198">11 (intersección)</span><span class="sxs-lookup"><span data-stu-id="49f7d-198">11 (Intercept)</span></span>|  
  
 <span data-ttu-id="49f7d-199">Para más información sobre los tipos de valor y las estadísticas usadas en modelos de regresión, vea [Contenido del modelo de minería de datos para los modelos de regresión lineal &#40;Analysis Services - Minería de datos&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="49f7d-199">For more information about the meaning of each value type for regression models, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="49f7d-200">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-200">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-3-returning-only-the-coefficient-for-the-model"></a><a name="bkmk_Query3"></a><span data-ttu-id="49f7d-201">Consulta de ejemplo 3: devolver solo el coeficiente para el modelo</span><span class="sxs-lookup"><span data-stu-id="49f7d-201">Sample Query 3: Returning Only the Coefficient for the Model</span></span>  
 <span data-ttu-id="49f7d-202">Utilizando la enumeración VALUETYPE, puede devolver solo el coeficiente para la ecuación de regresión, como se muestra en la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="49f7d-202">By using the VALUETYPE enumeration, you can return only the coefficient for the regression equation, as shown in the following query:</span></span>  
  
```  
SELECT FLATTENED MODEL_NAME,  
    (SELECT ATTRIBUTE_VALUE, VALUETYPE  
     FROM NODE_DISTRIBUTION  
     WHERE VALUETYPE = 11)   
AS t  
FROM LR_PredictIncome.CONTENT  
```  
  
 <span data-ttu-id="49f7d-203">Esta consulta devuelve dos filas, una del contenido del modelo de minería de datos y la fila de la tabla anidada que contiene el coeficiente.</span><span class="sxs-lookup"><span data-stu-id="49f7d-203">This query returns two rows, one from the mining model content, and the row from the nested table that contains the coefficient.</span></span> <span data-ttu-id="49f7d-204">La columna ATTRIBUTE_NAME no está incluida aquí porque siempre está en blanco para el coeficiente.</span><span class="sxs-lookup"><span data-stu-id="49f7d-204">The ATTRIBUTE_NAME column is not included here because it is always blank for the coefficient.</span></span>  
  
|<span data-ttu-id="49f7d-205">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="49f7d-205">MODEL_NAME</span></span>|<span data-ttu-id="49f7d-206">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="49f7d-206">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="49f7d-207">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="49f7d-207">t.VALUETYPE</span></span>|  
|-----------------|------------------------|-----------------|  
|<span data-ttu-id="49f7d-208">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="49f7d-208">LR_PredictIncome</span></span>|||  
|<span data-ttu-id="49f7d-209">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="49f7d-209">LR_PredictIncome</span></span>|<span data-ttu-id="49f7d-210">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="49f7d-210">35793.5477381267</span></span>|<span data-ttu-id="49f7d-211">11</span><span class="sxs-lookup"><span data-stu-id="49f7d-211">11</span></span>|  
  
 [<span data-ttu-id="49f7d-212">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-212">Return to Top</span></span>](#bkmk_top)  
  
## <a name="making-predictions-from-a-linear-regression-model"></a><span data-ttu-id="49f7d-213">Realizar predicciones a partir de un modelo de regresión lineal</span><span class="sxs-lookup"><span data-stu-id="49f7d-213">Making Predictions from a Linear Regression Model</span></span>  
 <span data-ttu-id="49f7d-214">Puede generar consultas de predicción en modelos de regresión lineal utilizando la pestaña Predicción de modelo de minería de datos del Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="49f7d-214">You can build prediction queries on linear regression models by using the Mining Model Prediction tab in Data Mining Designer.</span></span> <span data-ttu-id="49f7d-215">El generador de consultas de predicción está disponible en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49f7d-215">The prediction query builder is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49f7d-216">También puede crear consultas en modelos de regresión con los Complementos de minería de datos de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] para Excel o los Complementos de minería de datos de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] para Excel.</span><span class="sxs-lookup"><span data-stu-id="49f7d-216">You can also create queries on regression models by using the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining Add-ins for Excel or the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining Add-ins for Excel.</span></span> <span data-ttu-id="49f7d-217">Aunque los Complementos de minería de datos para Excel no crean modelos de regresión, puede examinar y consultar cualquier modelo de minería de datos que esté almacenado en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49f7d-217">Even though the Data Mining Add-ins for Excel do not create regression models, you can browse and query any mining model that is stored on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="49f7d-218">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-218">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-4-predicting-income-using-a-singleton-query"></a><a name="bkmk_Query4"></a><span data-ttu-id="49f7d-219">Consulta de ejemplo 4: predecir los ingresos utilizando una consulta singleton</span><span class="sxs-lookup"><span data-stu-id="49f7d-219">Sample Query 4: Predicting Income using a Singleton Query</span></span>  
 <span data-ttu-id="49f7d-220">La manera más fácil de crear una sola consulta en un modelo de regresión es usar el cuadro de diálogo **Entrada de consulta singleton** .</span><span class="sxs-lookup"><span data-stu-id="49f7d-220">The easiest way to create a single query on a regression model is by using the **Singleton Query Input** dialog box.</span></span> <span data-ttu-id="49f7d-221">Por ejemplo, puede generar la consulta DMX siguiente seleccionando el modelo de regresión adecuado, eligiendo **consulta singleton**y escribiendo `20` como el valor de **Age**.</span><span class="sxs-lookup"><span data-stu-id="49f7d-221">For example, you can build the following DMX query by selecting the appropriate regression model, choosing **Singleton Query**, and then typing `20` as the value for **Age**.</span></span>  
  
```  
SELECT [LR_PredictIncome].[Yearly Income]  
From   [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="49f7d-222">Resultados del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49f7d-222">Sample results:</span></span>  
  
|<span data-ttu-id="49f7d-223">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="49f7d-223">Yearly Income</span></span>|  
|-------------------|  
|<span data-ttu-id="49f7d-224">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="49f7d-224">45227.302092176</span></span>|  
  
 [<span data-ttu-id="49f7d-225">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-225">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-5-using-prediction-functions-with-a-regression-model"></a><a name="bkmk_Query5"></a><span data-ttu-id="49f7d-226">Consulta de ejemplo 5: usar funciones de predicción con un modelo de regresión</span><span class="sxs-lookup"><span data-stu-id="49f7d-226">Sample Query 5: Using Prediction Functions with a Regression Model</span></span>  
 <span data-ttu-id="49f7d-227">Puede utilizar muchas de las funciones de predicción estándar con modelos de regresión lineal.</span><span class="sxs-lookup"><span data-stu-id="49f7d-227">You can use many of the standard prediction functions with linear regression models.</span></span> <span data-ttu-id="49f7d-228">En el ejemplo siguiente se muestra cómo agregar algunas estadísticas descriptivas a los resultados de las consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="49f7d-228">The following example illustrates how to add some descriptive statistics to the prediction query results.</span></span> <span data-ttu-id="49f7d-229">A partir de estos resultados, puede que hay una desviación considerable de la media para este modelo.</span><span class="sxs-lookup"><span data-stu-id="49f7d-229">From these results, you can see that there is considerable deviation from the mean for this model.</span></span>  
  
```  
SELECT  
  ([LR_PredictIncome].[Yearly Income]) as [PredIncome],  
  (PredictStdev([LR_PredictIncome].[Yearly Income])) as [StDev1]  
From  
  [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="49f7d-230">Resultados del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49f7d-230">Sample results:</span></span>  
  
|<span data-ttu-id="49f7d-231">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="49f7d-231">Yearly Income</span></span>|<span data-ttu-id="49f7d-232">StDev1</span><span class="sxs-lookup"><span data-stu-id="49f7d-232">StDev1</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="49f7d-233">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="49f7d-233">45227.302092176</span></span>|<span data-ttu-id="49f7d-234">31827.1726561396</span><span class="sxs-lookup"><span data-stu-id="49f7d-234">31827.1726561396</span></span>|  
  
 [<span data-ttu-id="49f7d-235">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="49f7d-235">Return to Top</span></span>](#bkmk_top)  
  
## <a name="list-of-prediction-functions"></a><span data-ttu-id="49f7d-236">Lista de funciones de predicción</span><span class="sxs-lookup"><span data-stu-id="49f7d-236">List of Prediction Functions</span></span>  
 <span data-ttu-id="49f7d-237">Todos los algoritmos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] son compatibles con un conjunto común de funciones.</span><span class="sxs-lookup"><span data-stu-id="49f7d-237">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="49f7d-238">No obstante, el algoritmo de regresión lineal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] admite las funciones adicionales que se enumeran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="49f7d-238">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49f7d-239">función de predicción</span><span class="sxs-lookup"><span data-stu-id="49f7d-239">Prediction Function</span></span>|<span data-ttu-id="49f7d-240">Uso</span><span class="sxs-lookup"><span data-stu-id="49f7d-240">Usage</span></span>|  
|[<span data-ttu-id="49f7d-241">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-241">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="49f7d-242">Determina si un nodo es un elemento secundario de otro nodo del modelo.</span><span class="sxs-lookup"><span data-stu-id="49f7d-242">Determines whether one node is a child of another node in the model.</span></span>|  
|[<span data-ttu-id="49f7d-243">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-243">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="49f7d-244">Indica si el nodo especificado contiene el caso actual.</span><span class="sxs-lookup"><span data-stu-id="49f7d-244">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="49f7d-245">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-245">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="49f7d-246">Devuelve un valor o un conjunto de valores predichos para una columna especificada.</span><span class="sxs-lookup"><span data-stu-id="49f7d-246">Returns a predicted value, or set of values, for a specified column.</span></span>|  
|[<span data-ttu-id="49f7d-247">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-247">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="49f7d-248">Devuelve el Node_ID de cada caso.</span><span class="sxs-lookup"><span data-stu-id="49f7d-248">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="49f7d-249">PredictStdev &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-249">PredictStdev &#40;DMX&#41;</span></span>](/sql/dmx/predictstdev-dmx)|<span data-ttu-id="49f7d-250">Devuelve la desviación estándar del valor predicho.</span><span class="sxs-lookup"><span data-stu-id="49f7d-250">Returns standard deviation for the predicted value.</span></span>|  
|[<span data-ttu-id="49f7d-251">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-251">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="49f7d-252">Devuelve el valor de soporte de un estado especificado.</span><span class="sxs-lookup"><span data-stu-id="49f7d-252">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="49f7d-253">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-253">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="49f7d-254">Devuelve la varianza de una columna especificada.</span><span class="sxs-lookup"><span data-stu-id="49f7d-254">Returns the variance of a specified column.</span></span>|  
  
 <span data-ttu-id="49f7d-255">Para obtener una lista de las funciones que son comunes a todos los algoritmos de [!INCLUDE[msCoName](../../includes/msconame-md.md)], vea [Algoritmos de minería de datos &#40;Analysis Services: Minería de datos&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="49f7d-255">For a list of the functions that are common to all [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span> <span data-ttu-id="49f7d-256">Para más información sobre cómo usar estas funciones, vea [Referencia de funciones de Extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="49f7d-256">For more information about how to use these functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f7d-257">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49f7d-257">See Also</span></span>  
 <span data-ttu-id="49f7d-258">[Algoritmo de regresión lineal de Microsoft](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="49f7d-258">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="49f7d-259">[Consultas de minería de datos](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="49f7d-259">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="49f7d-260">[Referencia técnica del algoritmo de regresión lineal de Microsoft](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="49f7d-260">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="49f7d-261">Contenido del modelo de minería de datos para los modelos de regresión lineal &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="49f7d-261">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
