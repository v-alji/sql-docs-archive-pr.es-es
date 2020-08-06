---
title: Ejemplos de consultas de modelos de asociación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- rules [Data Mining]
- association rules
- content queries [DMX]
ms.assetid: 68b39f5c-c439-44ac-8046-6f2d36649059
author: minewiskan
ms.author: owend
ms.openlocfilehash: a19eb2302639c7f13d48a8778969bbeca4fee18d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676743"
---
# <a name="association-model-query-examples"></a><span data-ttu-id="39db7-102">Ejemplos de consultas del modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="39db7-102">Association Model Query Examples</span></span>
  <span data-ttu-id="39db7-103">Cuando se crea una consulta en un modelo de minería de datos, puede tratarse de una consulta de contenido, que proporciona detalles sobre las reglas y los conjuntos de elementos detectados durante el análisis, o una consulta de predicción, que utiliza las asociaciones detectadas en los datos para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="39db7-103">When you create a query against a data mining model, you can create either a content query, which provides details about the rules and itemsets discovered during analysis, or you can create a prediction query, which uses the associations discovered in the data to make predictions.</span></span> <span data-ttu-id="39db7-104">En un modelo de asociación, las predicciones se basan normalmente en reglas y se pueden utilizar para realizar recomendaciones, mientras que las consultas de contenido normalmente exploran la relación entre los conjuntos de elementos.</span><span class="sxs-lookup"><span data-stu-id="39db7-104">For an association model, predictions typically are based on rules, and can be used to make recommendations, whereas queries on content typically explore the relationship among itemsets.</span></span> <span data-ttu-id="39db7-105">También se puede recuperar metadatos sobre el modelo.</span><span class="sxs-lookup"><span data-stu-id="39db7-105">You can also retrieve metadata about the model.</span></span>  
  
 <span data-ttu-id="39db7-106">En esta sección se explica cómo crear estos tipos de consultas en modelos basados en el algoritmo de reglas de asociación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39db7-106">This section explains how to create these kinds of queries for models that are based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span>  
  
 <span data-ttu-id="39db7-107">**Consultas de contenido**</span><span class="sxs-lookup"><span data-stu-id="39db7-107">**Content Queries**</span></span>  
  
 [<span data-ttu-id="39db7-108">Obtener datos de metadatos del modelo utilizando DMX</span><span class="sxs-lookup"><span data-stu-id="39db7-108">Getting model metadata data by using DMX</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="39db7-109">Obtener metadatos del conjunto de filas de esquema</span><span class="sxs-lookup"><span data-stu-id="39db7-109">Getting metadata from the schema rowset</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="39db7-110">Recuperar los parámetros originales del modelo</span><span class="sxs-lookup"><span data-stu-id="39db7-110">Retrieving the original parameters for the model</span></span>](#bkmk_Query3)  
  
 [<span data-ttu-id="39db7-111">Recuperar una lista de conjuntos de elementos y de productos</span><span class="sxs-lookup"><span data-stu-id="39db7-111">Retrieving a list of itemsets and products</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="39db7-112">Devolver los 10 primeros conjuntos de elementos</span><span class="sxs-lookup"><span data-stu-id="39db7-112">Returning the top 10 itemsets</span></span>](#bkmk_Query5)  
  
 <span data-ttu-id="39db7-113">**Consultas de predicción**</span><span class="sxs-lookup"><span data-stu-id="39db7-113">**Prediction Queries**</span></span>  
  
 [<span data-ttu-id="39db7-114">Predecir elementos asociados</span><span class="sxs-lookup"><span data-stu-id="39db7-114">Predicting associated items</span></span>](#bkmk_Query6)  
  
 [<span data-ttu-id="39db7-115">Determinar la confianza por los conjuntos de elementos relacionados</span><span class="sxs-lookup"><span data-stu-id="39db7-115">Determining confidence for related itemsets</span></span>](#bkmk_Query7)  
  
##  <a name="finding-information-about-the-model"></a><a name="bkmk_top2"></a> <span data-ttu-id="39db7-116">Buscar información sobre el modelo</span><span class="sxs-lookup"><span data-stu-id="39db7-116">Finding Information about the Model</span></span>  
 <span data-ttu-id="39db7-117">Todos los modelos de minería de datos exponen el contenido aprendido por el algoritmo de acuerdo con un esquema normalizado, denominado conjunto de filas de esquema del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="39db7-117">All mining models expose the content learned by the algorithm according to a standardized schema, which is named the mining model schema rowset.</span></span> <span data-ttu-id="39db7-118">Puede crear consultas en el conjunto de filas de esquema del modelo de minería de datos utilizando instrucciones de Extensiones de minería de datos (DMX) o los procedimientos almacenados de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39db7-118">You can create queries against the mining model schema rowset either by using Data Mining Extensions (DMX) statements, or by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="39db7-119">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], también se pueden consultar directamente los conjuntos de filas de esquema como tablas del sistema, utilizando una sintaxis parecida a SQL.</span><span class="sxs-lookup"><span data-stu-id="39db7-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can also query the schema rowsets directly as system tables, by using a SQL-like syntax.</span></span>  
  
###  <a name="sample-query-1-getting-model-metadata-by-using-dmx"></a><a name="bkmk_Query1"></a> <span data-ttu-id="39db7-120">Consulta de ejemplo 1: obtener metadatos del modelo usando DMX</span><span class="sxs-lookup"><span data-stu-id="39db7-120">Sample Query 1: Getting Model Metadata by Using DMX</span></span>  
 <span data-ttu-id="39db7-121">La consulta siguiente devuelve metadatos básicos sobre el modelo de asociación, `Association`, como el nombre del modelo, la base de datos en la que se encuentra almacenado y el número de nodos secundarios existentes en él.</span><span class="sxs-lookup"><span data-stu-id="39db7-121">The following query returns basic metadata about the association model, `Association`, such as the name of the model, the database where the model is stored, and the number of child nodes in the model.</span></span> <span data-ttu-id="39db7-122">Esta consulta usa una consulta de contenido DMX para recuperar los metadatos del nodo primario del modelo:</span><span class="sxs-lookup"><span data-stu-id="39db7-122">This query uses a DMX content query to retrieve the metadata from the parent node of the model:</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, NODE_CAPTION,   
NODE_SUPPORT, [CHILDREN_CARDINALITY], NODE_DESCRIPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="39db7-123">El nombre de la columna CHILDREN_CARDINALITY debe ir entre corchetes para distinguirlo de la palabra clave reservada de MDX del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="39db7-123">You must enclose the name of the column, CHILDREN_CARDINALITY, in brackets to distinguish it from the MDX reserved keyword of the same name.</span></span>  
  
 <span data-ttu-id="39db7-124">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-124">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39db7-125">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39db7-125">MODEL_CATALOG</span></span>|<span data-ttu-id="39db7-126">Association Test</span><span class="sxs-lookup"><span data-stu-id="39db7-126">Association Test</span></span>|  
|<span data-ttu-id="39db7-127">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-127">MODEL_NAME</span></span>|<span data-ttu-id="39db7-128">Asociación</span><span class="sxs-lookup"><span data-stu-id="39db7-128">Association</span></span>|  
|<span data-ttu-id="39db7-129">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="39db7-129">NODE_CAPTION</span></span>|<span data-ttu-id="39db7-130">Association Rules Model</span><span class="sxs-lookup"><span data-stu-id="39db7-130">Association Rules Model</span></span>|  
|<span data-ttu-id="39db7-131">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="39db7-131">NODE_SUPPORT</span></span>|<span data-ttu-id="39db7-132">14879</span><span class="sxs-lookup"><span data-stu-id="39db7-132">14879</span></span>|  
|<span data-ttu-id="39db7-133">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="39db7-133">CHILDREN_CARDINALITY</span></span>|<span data-ttu-id="39db7-134">942</span><span class="sxs-lookup"><span data-stu-id="39db7-134">942</span></span>|  
|<span data-ttu-id="39db7-135">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39db7-135">NODE_DESCRIPTION</span></span>|<span data-ttu-id="39db7-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span><span class="sxs-lookup"><span data-stu-id="39db7-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span></span>|  
  
 <span data-ttu-id="39db7-137">Para consultar una definición de lo que significan estas columnas en un modelo de asociación, vea [Contenido del modelo de minería de datos para los modelos de asociación &#40;Analysis Services - Minería de datos&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="39db7-137">For a definition of what these columns mean in an association model, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="39db7-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-138">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-2-getting-additional-metadata-from-the-schema-rowset"></a><a name="bkmk_Query2"></a> <span data-ttu-id="39db7-139">Consulta de ejemplo 2: obtener metadatos adicionales del conjunto de filas de esquema</span><span class="sxs-lookup"><span data-stu-id="39db7-139">Sample Query 2: Getting Additional Metadata from the Schema Rowset</span></span>  
 <span data-ttu-id="39db7-140">Mediante una consulta al conjunto de filas de esquema de minería de datos, puede obtener la misma información que a través de una consulta de contenido DMX.</span><span class="sxs-lookup"><span data-stu-id="39db7-140">By querying the data mining schema rowset, you can find the same information that is returned in a DMX content query.</span></span> <span data-ttu-id="39db7-141">Sin embargo, el conjunto de filas de esquema proporciona algunas columnas adicionales, como la fecha en que se procesó el modelo por última vez, la estructura de minería de datos y el nombre de la columna usada como atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="39db7-141">However, the schema rowset provides some additional columns, such as the date the model was last processed, the mining structure, and the name of the column used as the predictable attribute.</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, SERVICE_NAME, PREDICTION_ENTITY,   
MINING_STRUCTURE, LAST_PROCESSED  
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="39db7-142">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-142">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39db7-143">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39db7-143">MODEL_CATALOG</span></span>|<span data-ttu-id="39db7-144">Adventure Works DW Multidimensional 2012</span><span class="sxs-lookup"><span data-stu-id="39db7-144">Adventure Works DW Multidimensional 2012</span></span>|  
|<span data-ttu-id="39db7-145">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-145">MODEL_NAME</span></span>|<span data-ttu-id="39db7-146">Asociación</span><span class="sxs-lookup"><span data-stu-id="39db7-146">Association</span></span>|  
|<span data-ttu-id="39db7-147">SERVICE_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-147">SERVICE_NAME</span></span>|<span data-ttu-id="39db7-148">Association Rules Model</span><span class="sxs-lookup"><span data-stu-id="39db7-148">Association Rules Model</span></span>|  
|<span data-ttu-id="39db7-149">PREDICTION_ENTITY</span><span class="sxs-lookup"><span data-stu-id="39db7-149">PREDICTION_ENTITY</span></span>|<span data-ttu-id="39db7-150">v Assoc Seq Line Items</span><span class="sxs-lookup"><span data-stu-id="39db7-150">v Assoc Seq Line Items</span></span>|  
|<span data-ttu-id="39db7-151">MINING_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="39db7-151">MINING_STRUCTURE</span></span>|<span data-ttu-id="39db7-152">Asociación</span><span class="sxs-lookup"><span data-stu-id="39db7-152">Association</span></span>|  
|<span data-ttu-id="39db7-153">LAST_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="39db7-153">LAST_PROCESSED</span></span>|<span data-ttu-id="39db7-154">29/9/2007 10:21:24 PM</span><span class="sxs-lookup"><span data-stu-id="39db7-154">9/29/2007 10:21:24 PM</span></span>|  
  
 [<span data-ttu-id="39db7-155">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-155">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-3-retrieving-original-parameters-for-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="39db7-156">Consulta de ejemplo 3: recuperar los parámetros originales para el modelo</span><span class="sxs-lookup"><span data-stu-id="39db7-156">Sample Query 3: Retrieving Original Parameters for Model</span></span>  
 <span data-ttu-id="39db7-157">La consulta siguiente devuelve una única columna con detalles sobre la configuración de parámetros utilizada cuando se creó el modelo.</span><span class="sxs-lookup"><span data-stu-id="39db7-157">The following query returns a single column that contains details about the parameter settings that were used when the model was created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
from $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="39db7-158">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-158">Example results:</span></span>  
  
 <span data-ttu-id="39db7-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span><span class="sxs-lookup"><span data-stu-id="39db7-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span></span>  
  
 [<span data-ttu-id="39db7-160">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-160">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="finding-information-about-rules-and-itemsets"></a><span data-ttu-id="39db7-161">Buscar información sobre las reglas y los conjuntos de elementos</span><span class="sxs-lookup"><span data-stu-id="39db7-161">Finding Information about Rules and Itemsets</span></span>  
 <span data-ttu-id="39db7-162">Los usos más comunes de un modelo de asociación son dos: detectar información sobre conjuntos de elementos frecuentes y extraer detalles sobre reglas y conjuntos de elementos concretos.</span><span class="sxs-lookup"><span data-stu-id="39db7-162">There are two common uses of an association model: to discover information about frequent itemsets, and to extract details about particular rules and itemsets.</span></span> <span data-ttu-id="39db7-163">Por ejemplo, puede que desee extraer una lista de reglas puntuadas como especialmente interesantes, o crear una lista de los conjuntos de elementos más comunes.</span><span class="sxs-lookup"><span data-stu-id="39db7-163">For example, you might want to extract a list of rules that were scored as being especially interesting, or create a list of the most common itemsets.</span></span> <span data-ttu-id="39db7-164">Esta información se recupera utilizando una consulta de contenido DMX.</span><span class="sxs-lookup"><span data-stu-id="39db7-164">You retrieve such information by using a DMX content query.</span></span> <span data-ttu-id="39db7-165">También se puede examinar esta información utilizando el **Visor de asociación de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="39db7-165">You can also browse this information by using the **Microsoft Association Viewer**.</span></span>  
  
###  <a name="sample-query-4-retrieving-list-of-itemsets-and-products"></a><a name="bkmk_Query4"></a> <span data-ttu-id="39db7-166">Consulta de ejemplo 4: recuperar una lista de conjuntos de elementos y productos</span><span class="sxs-lookup"><span data-stu-id="39db7-166">Sample Query 4: Retrieving List of Itemsets and Products</span></span>  
 <span data-ttu-id="39db7-167">La consulta siguiente recupera todos los conjuntos de elementos junto con una tabla anidada que contiene la lista de productos incluidos en cada conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="39db7-167">The following query retrieves all of the itemsets, together with a nested table that lists the products included in each itemset.</span></span> <span data-ttu-id="39db7-168">La columna NODE_NAME contiene el identificador único del conjunto de elementos existente en el modelo, mientras que NODE_CAPTION proporciona una descripción de los elementos.</span><span class="sxs-lookup"><span data-stu-id="39db7-168">The NODE_NAME column contains the unique ID of the itemset within the model, whereas the NODE_CAPTION provides a text description of the items.</span></span> <span data-ttu-id="39db7-169">En este ejemplo, se ha quitado la información de estructura jerárquica de la tabla anidada para que el conjunto de elementos que contenga dos productos genere dos filas en los resultados.</span><span class="sxs-lookup"><span data-stu-id="39db7-169">In this example, the nested table is flattened, so that an itemset that contains two products generates two rows in the results.</span></span> <span data-ttu-id="39db7-170">Se puede omitir la palabra clave FLATTENED si el cliente admite datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="39db7-170">You can omit the FLATTENED keyword if your client supports hierarchical data.</span></span>  
  
```  
SELECT FLATTENED NODE_NAME, NODE_CAPTION,  
NODE_PROBABILITY, NODE_SUPPORT,  
(SELECT ATTRIBUTE_NAME FROM NODE_DISTRIBUTION) as PurchasedProducts  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="39db7-171">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-171">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39db7-172">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-172">NODE_NAME</span></span>|<span data-ttu-id="39db7-173">37</span><span class="sxs-lookup"><span data-stu-id="39db7-173">37</span></span>|  
|<span data-ttu-id="39db7-174">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="39db7-174">NODE_CAPTION</span></span>|<span data-ttu-id="39db7-175">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="39db7-175">Sport-100 = Existing</span></span>|  
|<span data-ttu-id="39db7-176">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="39db7-176">NODE_PROBABILITY</span></span>|<span data-ttu-id="39db7-177">0.291283016331743</span><span class="sxs-lookup"><span data-stu-id="39db7-177">0.291283016331743</span></span>|  
|<span data-ttu-id="39db7-178">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="39db7-178">NODE_SUPPORT</span></span>|<span data-ttu-id="39db7-179">4334</span><span class="sxs-lookup"><span data-stu-id="39db7-179">4334</span></span>|  
|<span data-ttu-id="39db7-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="39db7-181">v Assoc Seq Line Items(Sport-100)</span><span class="sxs-lookup"><span data-stu-id="39db7-181">v Assoc Seq Line Items(Sport-100)</span></span>|  
  
 [<span data-ttu-id="39db7-182">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-182">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-5-returning-top-10-itemsets"></a><a name="bkmk_Query5"></a> <span data-ttu-id="39db7-183">Consulta de ejemplo 5: devolver los 10 primeros conjuntos de elementos</span><span class="sxs-lookup"><span data-stu-id="39db7-183">Sample Query 5: Returning Top 10 Itemsets</span></span>  
 <span data-ttu-id="39db7-184">En este ejemplo se muestra cómo utilizar algunas de las funciones de agrupación y ordenación que DMX proporciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="39db7-184">This example demonstrates how to use some of the grouping and ordering functions that DMX provides by default.</span></span> <span data-ttu-id="39db7-185">La consulta devuelve los 10 mejores conjuntos de elementos ordenados según el soporte para cada nodo.</span><span class="sxs-lookup"><span data-stu-id="39db7-185">The query returns the top 10 itemsets when ordered by the support for each node.</span></span> <span data-ttu-id="39db7-186">Observe que no necesita agrupar explícitamente los resultados, tal como haría en Transact-SQL; sin embargo, puede utilizar solo una función de agregado en cada consulta.</span><span class="sxs-lookup"><span data-stu-id="39db7-186">Note that you do not need to explicitly group the results, as you would in Transact-SQL; however, you can use only one aggregate function in each query.</span></span>  
  
```  
SELECT TOP 10 (NODE_SUPPORT),NODE_NAME, NODE_CAPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="39db7-187">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-187">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39db7-188">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="39db7-188">NODE_SUPPORT</span></span>|<span data-ttu-id="39db7-189">4334</span><span class="sxs-lookup"><span data-stu-id="39db7-189">4334</span></span>|  
|<span data-ttu-id="39db7-190">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-190">NODE_NAME</span></span>|<span data-ttu-id="39db7-191">37</span><span class="sxs-lookup"><span data-stu-id="39db7-191">37</span></span>|  
|<span data-ttu-id="39db7-192">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="39db7-192">NODE_CAPTION</span></span>|<span data-ttu-id="39db7-193">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="39db7-193">Sport-100 = Existing</span></span>|  
  
 [<span data-ttu-id="39db7-194">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-194">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="making-predictions-using-the-model"></a><span data-ttu-id="39db7-195">Realizar predicciones utilizando el modelo</span><span class="sxs-lookup"><span data-stu-id="39db7-195">Making Predictions using the Model</span></span>  
 <span data-ttu-id="39db7-196">Un modelo de reglas de asociación se suele utilizar para generar recomendaciones, que se basan en las correlaciones detectadas en los conjuntos de elementos.</span><span class="sxs-lookup"><span data-stu-id="39db7-196">An association rules model is often used to generate recommendations, which are based on correlations discovered in the itemsets.</span></span> <span data-ttu-id="39db7-197">Por tanto, cuando se crea una consulta de predicción basada en un modelo de reglas de asociación, normalmente se usan las reglas del modelo para realizar estimaciones basadas en nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="39db7-197">Therefore, when you create a prediction query based on an association rules model, you are typically using the rules in the model to make guesses based on new data.</span></span>  <span data-ttu-id="39db7-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) es la función que devuelve las recomendaciones y tiene varios argumentos que se pueden usar para personalizar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="39db7-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) is the function that returns recommendations, and has several arguments that you can use to customize the query results.</span></span>  
  
 <span data-ttu-id="39db7-199">Otro ejemplo de dónde podrían resultar útiles las consultas en un modelo de asociación consiste en devolver la confianza para diversas reglas y conjuntos de elementos con objeto de poder comparar la efectividad de distintas estrategias de ventas cruzadas.</span><span class="sxs-lookup"><span data-stu-id="39db7-199">Another example of where queries on an association model might be useful is to return the confidence for various rules and itemsets so that you can compare the effectiveness of different cross-sell strategies.</span></span> <span data-ttu-id="39db7-200">En los ejemplos siguientes se muestra cómo crear tales consultas.</span><span class="sxs-lookup"><span data-stu-id="39db7-200">The following examples illustrate how to create such queries.</span></span>  
  
###  <a name="sample-query-6-predicting-associated-items"></a><a name="bkmk_Query6"></a> <span data-ttu-id="39db7-201">Consulta de ejemplo 6: predecir elementos asociados</span><span class="sxs-lookup"><span data-stu-id="39db7-201">Sample Query 6: Predicting Associated Items</span></span>  
 <span data-ttu-id="39db7-202">En este ejemplo se usa el modelo de asociación creado en el [Tutorial intermedio de minería de datos &#40;Analysis Services - Minería de datos&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="39db7-202">This example uses the Association model created in the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="39db7-203">Muestra cómo crear una consulta de predicción que indica qué productos se deben recomendar a un cliente que ha comprado un producto determinado.</span><span class="sxs-lookup"><span data-stu-id="39db7-203">It demonstrates how to create a prediction query that tells you what products to recommend to a customer who has purchased a particular product.</span></span> <span data-ttu-id="39db7-204">Este tipo de consulta, donde se deben proporcionar valores para el modelo en una instrucción `SELECT...UNION`, se denomina consulta singleton.</span><span class="sxs-lookup"><span data-stu-id="39db7-204">This type of query, where you provide values to the model in a `SELECT...UNION` statement, is called a singleton query.</span></span> <span data-ttu-id="39db7-205">Dado que la columna del modelo de predicción correspondiente a los nuevos valores es una tabla anidada, se debe utilizar una cláusula `SELECT` para asignar el nuevo valor a la columna de tabla anidada, `[Model]`, y otra cláusula `SELECT` para asignar la columna de tabla anidada a la columna de nivel de caso, `[v Assoc Seq Line Items]`.</span><span class="sxs-lookup"><span data-stu-id="39db7-205">Because the predictable model column that corresponds to the new values is a nested table, you must use one `SELECT` clause to map the new value to the nested table column, `[Model]`, and another `SELECT` clause to map the nested table column to the case-level column, `[v Assoc Seq Line Items]`.</span></span> <span data-ttu-id="39db7-206">Si agrega la palabra clave INCLUDE-STATISTICS a la consulta, podrá ver la probabilidad y el soporte para las recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="39db7-206">Adding the keyword INCLUDE-STATISTICS to the query lets you see the probability and support for the recommendations.</span></span>  
  
```  
SELECT PredictAssociation([Association].[vAssocSeqLineItems],INCLUDE_STATISTICS, 3)  
FROM [Association]  
NATURAL PREDICTION JOIN   
(SELECT  
(SELECT 'Classic Vest' as [Model])  
AS [v Assoc Seq Line Items])  
AS t  
```  
  
 <span data-ttu-id="39db7-207">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-207">Example results:</span></span>  
  
|<span data-ttu-id="39db7-208">Modelo</span><span class="sxs-lookup"><span data-stu-id="39db7-208">Model</span></span>|<span data-ttu-id="39db7-209">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="39db7-209">$SUPPORT</span></span>|<span data-ttu-id="39db7-210">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="39db7-210">$PROBABILITY</span></span>|<span data-ttu-id="39db7-211">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="39db7-211">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="39db7-212">Sport-100</span><span class="sxs-lookup"><span data-stu-id="39db7-212">Sport-100</span></span>|<span data-ttu-id="39db7-213">4334</span><span class="sxs-lookup"><span data-stu-id="39db7-213">4334</span></span>|<span data-ttu-id="39db7-214">0.291283</span><span class="sxs-lookup"><span data-stu-id="39db7-214">0.291283</span></span>|<span data-ttu-id="39db7-215">0.252696</span><span class="sxs-lookup"><span data-stu-id="39db7-215">0.252696</span></span>|  
|<span data-ttu-id="39db7-216">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="39db7-216">Water Bottle</span></span>|<span data-ttu-id="39db7-217">2866</span><span class="sxs-lookup"><span data-stu-id="39db7-217">2866</span></span>|<span data-ttu-id="39db7-218">0.19262</span><span class="sxs-lookup"><span data-stu-id="39db7-218">0.19262</span></span>|<span data-ttu-id="39db7-219">0.175205</span><span class="sxs-lookup"><span data-stu-id="39db7-219">0.175205</span></span>|  
|<span data-ttu-id="39db7-220">Patch kit</span><span class="sxs-lookup"><span data-stu-id="39db7-220">Patch kit</span></span>|<span data-ttu-id="39db7-221">2113</span><span class="sxs-lookup"><span data-stu-id="39db7-221">2113</span></span>|<span data-ttu-id="39db7-222">0.142012</span><span class="sxs-lookup"><span data-stu-id="39db7-222">0.142012</span></span>|<span data-ttu-id="39db7-223">0.132389</span><span class="sxs-lookup"><span data-stu-id="39db7-223">0.132389</span></span>|  
  
 [<span data-ttu-id="39db7-224">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-224">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-7-determining-confidence-for-related-itemsets"></a><a name="bkmk_Query7"></a> <span data-ttu-id="39db7-225">Consulta de ejemplo 7: determinar la confianza para los conjuntos de elementos relacionados</span><span class="sxs-lookup"><span data-stu-id="39db7-225">Sample Query 7: Determining Confidence for Related Itemsets</span></span>  
 <span data-ttu-id="39db7-226">Mientras que las reglas son útiles para generar recomendaciones, los conjuntos de elementos resultan más interesantes para realizar análisis más profundos de los patrones existentes en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="39db7-226">Whereas rules are useful for generating recommendations, itemsets are more interesting for deeper analysis of the patterns in the data set.</span></span> <span data-ttu-id="39db7-227">Por ejemplo, si no quedó satisfecho con las recomendaciones devueltas por la consulta de ejemplo anterior, podría examinar otros conjuntos de elementos que contuviesen el Producto A para tener una idea más clara de si dicho producto es un accesorio que se compra con todo tipo de productos, o si se trata de un producto estrechamente relacionado con las compras de determinados productos.</span><span class="sxs-lookup"><span data-stu-id="39db7-227">For example, if you were not satisfied with the recommendation that are returned by the previous sample query, you could examine other itemsets that contain Product A, to can get a better idea of whether Product A is an accessory that people tend to buy with all kinds of products, or whether A is strongly correlated with purchases of particular products.</span></span> <span data-ttu-id="39db7-228">La manera más fácil de explorar estas relaciones es filtrando los conjuntos de elementos en el Visor de asociación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] ; sin embargo, se puede recuperar la misma información con una consulta.</span><span class="sxs-lookup"><span data-stu-id="39db7-228">The easiest way to explore these relationships is by filtering the itemsets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer; however, you can retrieve the same information with a query.</span></span>  
  
 <span data-ttu-id="39db7-229">La consulta de ejemplo siguiente devuelve todos los conjuntos de elementos que incluyen el elemento Water Bottle, incluido el elemento Water Bottle por sí solo.</span><span class="sxs-lookup"><span data-stu-id="39db7-229">The following sample query returns all itemsets that include the Water Bottle item, including the single item Water bottle.</span></span>  
  
```  
SELECT TOP 100 FROM   
(  
SELECT FLATTENED NODE_CAPTION, NODE_SUPPORT,   
(SELECT ATTRIBUTE_NAME from NODE_DISTRIBUTION  
WHERE ATTRIBUTE_NAME = 'v Assoc Seq Line Items(Water Bottle)') as D  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
) AS Items  
WHERE [D.ATTRIBUTE_NAME] <> NULL  
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="39db7-230">Resultados de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39db7-230">Example results:</span></span>  
  
|<span data-ttu-id="39db7-231">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="39db7-231">NODE_CAPTION</span></span>|<span data-ttu-id="39db7-232">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="39db7-232">NODE_SUPPORT</span></span>|<span data-ttu-id="39db7-233">D.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="39db7-233">D.ATTRIBUTE_NAME</span></span>|  
|-------------------|-------------------|-----------------------|  
|<span data-ttu-id="39db7-234">Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="39db7-234">Water Bottle = Existing</span></span>|<span data-ttu-id="39db7-235">2866</span><span class="sxs-lookup"><span data-stu-id="39db7-235">2866</span></span>|<span data-ttu-id="39db7-236">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="39db7-236">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="39db7-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="39db7-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="39db7-238">1136</span><span class="sxs-lookup"><span data-stu-id="39db7-238">1136</span></span>|<span data-ttu-id="39db7-239">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="39db7-239">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="39db7-240">Road Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="39db7-240">Road Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="39db7-241">1068</span><span class="sxs-lookup"><span data-stu-id="39db7-241">1068</span></span>|<span data-ttu-id="39db7-242">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="39db7-242">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="39db7-243">Water Bottle = Existing, Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="39db7-243">Water Bottle = Existing, Sport-100 = Existing</span></span>|<span data-ttu-id="39db7-244">734</span><span class="sxs-lookup"><span data-stu-id="39db7-244">734</span></span>|<span data-ttu-id="39db7-245">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="39db7-245">v Assoc Seq Line Items(Water Bottle)</span></span>|  
  
 <span data-ttu-id="39db7-246">Esta consulta devuelve tanto las filas de la tabla anidada que cumplen los criterios, como todas las filas externas o de la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="39db7-246">This query returns both the rows from the nested table that match the criteria, and all the rows from the outside or case table.</span></span> <span data-ttu-id="39db7-247">Por consiguiente, se debe agregar una condición que elimine las filas de la tabla de casos que tengan un valor NULL para el nombre del atributo de destino.</span><span class="sxs-lookup"><span data-stu-id="39db7-247">Therefore, you must add a condition that eliminates the case table rows that have a null value for the target attribute name.</span></span>  
  
 [<span data-ttu-id="39db7-248">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="39db7-248">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="function-list"></a><span data-ttu-id="39db7-249">Lista de funciones</span><span class="sxs-lookup"><span data-stu-id="39db7-249">Function List</span></span>  
 <span data-ttu-id="39db7-250">Todos los algoritmos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] son compatibles con un conjunto común de funciones.</span><span class="sxs-lookup"><span data-stu-id="39db7-250">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="39db7-251">Sin embargo, el algoritmo de asociación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] admite las funciones adicionales que se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="39db7-251">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39db7-252">función de predicción</span><span class="sxs-lookup"><span data-stu-id="39db7-252">Prediction Function</span></span>|<span data-ttu-id="39db7-253">Uso</span><span class="sxs-lookup"><span data-stu-id="39db7-253">Usage</span></span>|  
|[<span data-ttu-id="39db7-254">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-254">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="39db7-255">Determina si un nodo es un elemento secundario de otro nodo en el gráfico de red neuronal.</span><span class="sxs-lookup"><span data-stu-id="39db7-255">Determines whether one node is a child of another node in the neural network graph.</span></span>|  
|[<span data-ttu-id="39db7-256">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-256">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="39db7-257">Indica si el nodo especificado contiene el caso actual.</span><span class="sxs-lookup"><span data-stu-id="39db7-257">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="39db7-258">PredictAdjustedProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-258">PredictAdjustedProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictadjustedprobability-dmx)|<span data-ttu-id="39db7-259">Devuelve la probabilidad ponderada.</span><span class="sxs-lookup"><span data-stu-id="39db7-259">Returns the weighted probability.</span></span>|  
|[<span data-ttu-id="39db7-260">PredictAssociation &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-260">PredictAssociation &#40;DMX&#41;</span></span>](/sql/dmx/predictassociation-dmx)|<span data-ttu-id="39db7-261">Predice los miembros de un conjunto de datos asociativo.</span><span class="sxs-lookup"><span data-stu-id="39db7-261">Predicts membership in an associative dataset.</span></span>|  
|[<span data-ttu-id="39db7-262">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-262">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="39db7-263">Devuelve una tabla de valores relacionados con el valor de predicción actual.</span><span class="sxs-lookup"><span data-stu-id="39db7-263">Returns a table of values related to the current predicted value.</span></span>|  
|[<span data-ttu-id="39db7-264">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-264">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="39db7-265">Devuelve el Node_ID de cada caso.</span><span class="sxs-lookup"><span data-stu-id="39db7-265">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="39db7-266">PredictProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-266">PredictProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictprobability-dmx)|<span data-ttu-id="39db7-267">Devuelve la probabilidad del valor de predicción.</span><span class="sxs-lookup"><span data-stu-id="39db7-267">Returns probability for the predicted value.</span></span>|  
|[<span data-ttu-id="39db7-268">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-268">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="39db7-269">Devuelve el valor de soporte de un estado especificado.</span><span class="sxs-lookup"><span data-stu-id="39db7-269">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="39db7-270">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-270">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="39db7-271">Devuelve la varianza del valor de predicción.</span><span class="sxs-lookup"><span data-stu-id="39db7-271">Returns variance for the predicted value.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39db7-272">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39db7-272">See Also</span></span>  
 <span data-ttu-id="39db7-273">[Algoritmo de Asociación de Microsoft](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="39db7-273">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 <span data-ttu-id="39db7-274">[Referencia técnica del algoritmo de Asociación de Microsoft](microsoft-association-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="39db7-274">[Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="39db7-275">Contenido del modelo de minería de datos para los modelos de asociación &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="39db7-275">Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-association-models-analysis-services-data-mining.md)  
  
  
