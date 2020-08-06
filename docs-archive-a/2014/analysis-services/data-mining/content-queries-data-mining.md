---
title: Consultas de contenido (minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c4f4a5a8-a230-4222-bece-9d563501f65f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44b162c34f5f505462a713205d8434484473afa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677958"
---
# <a name="content-queries-data-mining"></a><span data-ttu-id="91376-102">Consultas de contenido (minería de datos)</span><span class="sxs-lookup"><span data-stu-id="91376-102">Content Queries (Data Mining)</span></span>
  <span data-ttu-id="91376-103">Una consulta de contenido es una manera de extraer información sobre las estadísticas internas y la estructura del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="91376-103">A content query is a way of extracting information about the internal statistics and structure of the mining model.</span></span> <span data-ttu-id="91376-104">A veces, una consulta de contenido puede proporcionar detalles que no están disponibles con facilidad en el visor.</span><span class="sxs-lookup"><span data-stu-id="91376-104">Sometimes a content query can provide details that are not readily available in the viewer.</span></span> <span data-ttu-id="91376-105">También puede usar los resultados de una consulta de contenido para extraer información mediante programación para otros usos.</span><span class="sxs-lookup"><span data-stu-id="91376-105">You can also use the results of a content query to extract information programmatically for other uses.</span></span>  
  
 <span data-ttu-id="91376-106">En esta sección se proporciona información general sobre los tipos de información que se pueden recuperar usando una consulta de contenido, así como la sintaxis DMX general para este tipo de consultas.</span><span class="sxs-lookup"><span data-stu-id="91376-106">This section provides general information about the types of information that you can retrieve by using a content query, and the general DMX syntax for content queries.</span></span>  
  
 [<span data-ttu-id="91376-107">Consultas básicas de contenido</span><span class="sxs-lookup"><span data-stu-id="91376-107">Basic Content Queries</span></span>](#bkmk_ContentQuery)  
  
-   [<span data-ttu-id="91376-108">Consultas en datos de estructura y de caso</span><span class="sxs-lookup"><span data-stu-id="91376-108">Queries on Structure and Case Data</span></span>](#bkmk_Structure)  
  
-   [<span data-ttu-id="91376-109">Consultas en los patrones de modelo</span><span class="sxs-lookup"><span data-stu-id="91376-109">Queries on Model Patterns</span></span>](#bkmk_Patterns)  
  
 [<span data-ttu-id="91376-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="91376-110">Examples</span></span>](#bkmk_Examples)  
  
-   [<span data-ttu-id="91376-111">Consulta de contenido en un modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="91376-111">Content Query on an Association Model</span></span>](#bkmk_Assoc)  
  
-   [<span data-ttu-id="91376-112">Consulta de contenido en un modelo de árboles de decisión</span><span class="sxs-lookup"><span data-stu-id="91376-112">Content Query on a Decision Trees Model</span></span>](#bkmk_DecTree)  
  
 [<span data-ttu-id="91376-113">Trabajar con los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="91376-113">Working with the Query Results</span></span>](#bkmk_Results)  
  
##  <a name="basic-content-queries"></a><a name="bkmk_ContentQuery"></a><span data-ttu-id="91376-114">Consultas básicas de contenido</span><span class="sxs-lookup"><span data-stu-id="91376-114">Basic Content Queries</span></span>  
 <span data-ttu-id="91376-115">Puede crear consultas de contenido mediante el Generador de consultas de predicción, use las plantillas de consulta de contenido DMX incluidas en SQL Server Management Studio, o escribir consultas directamente en DMX.</span><span class="sxs-lookup"><span data-stu-id="91376-115">You can create content queries by using the Prediction Query Builder, use the DMX content query templates that are provided in SQL Server Management Studio, or write queries directly in DMX.</span></span> <span data-ttu-id="91376-116">A diferencia de las consultas de predicción, no es necesario combinar datos externos, por lo que las consultas de contenido son fáciles de crear.</span><span class="sxs-lookup"><span data-stu-id="91376-116">Unlike prediction queries you do not need to join external data, so content queries are easy to write.</span></span>  
  
 <span data-ttu-id="91376-117">Esta sección proporciona información general sobre los tipos de consultas de contenido que puede crear.</span><span class="sxs-lookup"><span data-stu-id="91376-117">This section provides an overview of the types of content queries you can create.</span></span>  
  
-   <span data-ttu-id="91376-118">Las consultas en los datos de casos o de estructura de minería de datos permiten ver los datos detallados que se utilizaron para entrenar.</span><span class="sxs-lookup"><span data-stu-id="91376-118">Queries on the mining structure or case data let you view the detailed data that was used for training.</span></span>  
  
-   <span data-ttu-id="91376-119">Las consultas en el modelo pueden devolver patrones, listas de atributos, fórmulas, etc.</span><span class="sxs-lookup"><span data-stu-id="91376-119">Queries on the model can return patterns, lists of attributes, formulas, and so forth.</span></span>  
  
###  <a name="queries-on-structure-and-case-data"></a><a name="bkmk_Structure"></a> <span data-ttu-id="91376-120">Consultas en los datos de casos y de estructura</span><span class="sxs-lookup"><span data-stu-id="91376-120">Queries on Structure and Case Data</span></span>  
 <span data-ttu-id="91376-121">DMX admite consultas en los datos almacenados en caché que se usan para compilar estructuras y modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="91376-121">DMX supports queries on the cached data that is used to build mining structures and models.</span></span> <span data-ttu-id="91376-122">De forma predeterminada, esta caché se crea al definir la estructura de minería de datos, y se rellena al procesar la estructura o el modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-122">By default, this cache is created when you define the mining structure, and is populated when you process the structure or model.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="91376-123">No debe borrar ni eliminar esta caché si desea separar los datos en conjuntos de entrenamiento y de prueba.</span><span class="sxs-lookup"><span data-stu-id="91376-123">This cache cannot be cleared or deleted if you need to separate data into training and testing sets.</span></span> <span data-ttu-id="91376-124">Si se borra, no podrá consultar los datos de los casos.</span><span class="sxs-lookup"><span data-stu-id="91376-124">If the cache is cleared, you cannot query the case data.</span></span>  
  
 <span data-ttu-id="91376-125">En los siguientes ejemplos se muestran los patrones comunes para crear consultas en los datos de los casos, o consultas en los datos de la minería de datos:</span><span class="sxs-lookup"><span data-stu-id="91376-125">The following examples show the common patterns for creating queries on the case data, or queries on the data in the mining structure:</span></span>  
  
 <span data-ttu-id="91376-126">**Obtener todos los casos de un modelo**</span><span class="sxs-lookup"><span data-stu-id="91376-126">**Get all the cases for a model**</span></span>  
 `SELECT FROM <model>.CASES`  
  
 <span data-ttu-id="91376-127">Use esta instrucción para recuperar las columnas especificadas de los datos de los casos usados para compilar un modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-127">Use this statement to retrieve specified columns from the case data used to build a model.</span></span> <span data-ttu-id="91376-128">Debe tener permisos de obtención de detalles en el modelo para ejecutar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="91376-128">You must have drillthrough permissions on the model to run this query.</span></span>  
  
 <span data-ttu-id="91376-129">**Ver todos los datos incluidos en la estructura**</span><span class="sxs-lookup"><span data-stu-id="91376-129">**View all the data that is included in the structure**</span></span>  
 `SELECT FROM <structure>.CASES`  
  
 <span data-ttu-id="91376-130">Use esta instrucción para ver todos los datos existentes en la estructura, incluso las columnas que no están incluidas en un modelo de minería de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="91376-130">Use this statement to view all the data that is included in the structure, including columns that are not included in a particular mining model.</span></span> <span data-ttu-id="91376-131">Debe tener permisos de obtención de detalles en el modelo, así como en la estructura, para recuperar datos de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="91376-131">You must have drillthrough permissions on the model, as well as on the structure, to retrieve data from the mining structure.</span></span>  
  
 <span data-ttu-id="91376-132">**Obtener un intervalo de valores**</span><span class="sxs-lookup"><span data-stu-id="91376-132">**Get range of values**</span></span>  
 `SELECT DISTINCT RangeMin(<column>), RangeMax(<column>) FROM <model>`  
  
 <span data-ttu-id="91376-133">Use esta instrucción para buscar el valor mínimo, el valor máximo y la media de una columna continua, o de los cubos de una columna de datos discretos.</span><span class="sxs-lookup"><span data-stu-id="91376-133">Use this statement to find the minimum value, maximum value, and mean of a continuous column, or of the buckets of a DISCRETIZED column.</span></span>  
  
 <span data-ttu-id="91376-134">**Obtener valores distintos**</span><span class="sxs-lookup"><span data-stu-id="91376-134">**Get distinct values**</span></span>  
 `SELECT DISTINCT <column>FROM <model>`  
  
 <span data-ttu-id="91376-135">Use esta instrucción para recuperar todos los valores de una columna discreta.</span><span class="sxs-lookup"><span data-stu-id="91376-135">Use this statement to retrieve all the values of a DISCRETE column.</span></span>  <span data-ttu-id="91376-136">No use esta instrucción para las columnas DISCRETIZED; use las funciones `RangeMin` y `RangeMax` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="91376-136">Do not use this statement for DISCRETIZED columns; use the `RangeMin` and `RangeMax` functions instead.</span></span>  
  
 <span data-ttu-id="91376-137">**Buscar los casos que se usaron para el entrenamiento de un modelo o una estructura**</span><span class="sxs-lookup"><span data-stu-id="91376-137">**Find the cases that were used to train a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTrainingCase()`  
  
 <span data-ttu-id="91376-138">Use esta instrucción para obtener el conjunto completo de datos empleado en el entrenamiento de un modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-138">Use this statement to get the complete set of data that was used in a training a model.</span></span>  
  
 <span data-ttu-id="91376-139">**Buscar los casos que se usan para probar un modelo o una estructura**</span><span class="sxs-lookup"><span data-stu-id="91376-139">**Find the cases that are used for testing a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTestingCase()`  
  
 <span data-ttu-id="91376-140">Use esta instrucción para obtener los datos que se han reservado para la prueba de modelos de minería de datos relacionados con una estructura específica.</span><span class="sxs-lookup"><span data-stu-id="91376-140">Use this statement to get the data that has been set aside for testing mining models related to a specific structure.</span></span>  
  
 <span data-ttu-id="91376-141">**Obtención de detalles de un patrón de modelo concreto en los datos de casos subyacentes**</span><span class="sxs-lookup"><span data-stu-id="91376-141">**Drillthrough from a specific model pattern to underlying case data**</span></span>  
 `SELECT FROM <model>.CASESWHERE IsTrainingCase() AND IsInNode(<node>)`  
  
 <span data-ttu-id="91376-142">Use esta instrucción para recuperar datos detallados de los casos de un modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="91376-142">Use this statement to retrieve detailed case data from a trained model.</span></span> <span data-ttu-id="91376-143">Debe especificar un nodo concreto: por ejemplo, debe conocer el identificador de nodo del clúster, la rama específica del árbol de decisión, etc. Además, debe tener permisos de obtención de detalles en el modelo para ejecutar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="91376-143">You must specify a specific node: for example, you must know the node ID of the cluster, the specific branch of the decision tree, etc. Moreover, you must have drillthrough permissions on the model to run this query.</span></span>  
  
###  <a name="queries-on-model-patterns-statistics-and-attributes"></a><a name="bkmk_Patterns"></a><span data-ttu-id="91376-144">Consultas en los patrones, estadísticas y atributos del modelo</span><span class="sxs-lookup"><span data-stu-id="91376-144">Queries on Model Patterns, Statistics, and Attributes</span></span>  
 <span data-ttu-id="91376-145">El contenido de un modelo de minería de datos es útil para muchos propósitos.</span><span class="sxs-lookup"><span data-stu-id="91376-145">The content of a data mining model is useful for many purposes.</span></span> <span data-ttu-id="91376-146">Con una consulta de contenido del modelo, puede:</span><span class="sxs-lookup"><span data-stu-id="91376-146">With a model content query, you can:</span></span>  
  
-   <span data-ttu-id="91376-147">Extraer fórmulas o probabilidades para realizar sus propios cálculos.</span><span class="sxs-lookup"><span data-stu-id="91376-147">Extract formulas or probabilities for making your own calculations.</span></span>  
  
-   <span data-ttu-id="91376-148">Para un modelo de asociación, recuperar las reglas que se utilizan para generar una predicción.</span><span class="sxs-lookup"><span data-stu-id="91376-148">For an association model, retrieve the rules that are used to generate a prediction.</span></span>  
  
-   <span data-ttu-id="91376-149">Recuperar las descripciones de reglas concretas para poder usarlas en una aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="91376-149">Retrieve the descriptions of specific rules so that you can use the rules in a custom application.</span></span>  
  
-   <span data-ttu-id="91376-150">Ver las medias móviles detectadas por un modelo de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="91376-150">View the moving averages detected by a time series model.</span></span>  
  
-   <span data-ttu-id="91376-151">Obtener la fórmula de regresión de algún segmento de la línea de tendencia.</span><span class="sxs-lookup"><span data-stu-id="91376-151">Obtain the regression formula for some segment of the trend line.</span></span>  
  
-   <span data-ttu-id="91376-152">Recuperar la información procesable sobre los clientes identificados como miembros de un clúster concreto.</span><span class="sxs-lookup"><span data-stu-id="91376-152">Retrieve actionable information about customers identified as being part of a specific cluster.</span></span>  
  
 <span data-ttu-id="91376-153">En los siguientes ejemplos se muestran algunos de los modelos comunes para crear consultas en el contenido del modelo:</span><span class="sxs-lookup"><span data-stu-id="91376-153">The following examples show some of the common patterns for creating queries on the model content:</span></span>  
  
 <span data-ttu-id="91376-154">**Obtener patrones del modelo**</span><span class="sxs-lookup"><span data-stu-id="91376-154">**Get patterns from the model**</span></span>  
 `SELECT FROM <model>.CONTENT`  
  
 <span data-ttu-id="91376-155">Use esta instrucción para recuperar información detallada sobre nodos específicos del modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-155">Use this statement to retrieve detailed information about specific nodes in the model.</span></span> <span data-ttu-id="91376-156">Dependiendo del tipo de algoritmo, el nodo puede contener reglas y fórmulas, estadísticas de compatibilidad y varianza, etc.</span><span class="sxs-lookup"><span data-stu-id="91376-156">Depending on the algorithm type, the node can contain rules and formulas, support and variance statistics, and so forth.</span></span>  
  
 <span data-ttu-id="91376-157">**Recuperar los atributos usados en un modelo entrenado**</span><span class="sxs-lookup"><span data-stu-id="91376-157">**Retrieve attributes used in a trained model**</span></span>  
 `CALL System.GetModelAttributes(<model>)`  
  
 <span data-ttu-id="91376-158">Use este procedimiento almacenado para recuperar la lista de atributos usados por un modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-158">Use this stored procedure to retrieve the list of attributes that were used by a model.</span></span> <span data-ttu-id="91376-159">Esta información es útil para determinar los atributos que se eliminaron como resultado de la selección de características, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="91376-159">This information is useful for determining attributes that were eliminated as a result of feature selection, for example.</span></span>  
  
 <span data-ttu-id="91376-160">**Recuperar el contenido almacenado en una dimensión de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="91376-160">**Retrieve content stored in a data mining dimension**</span></span>  
 `SELECT FROM <model>.DIMENSIONCONTENT`  
  
 <span data-ttu-id="91376-161">Use esta instrucción para recuperar los datos de una dimensión de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="91376-161">Use this statement to retrieve the data from a data mining dimension.</span></span>  
  
 <span data-ttu-id="91376-162">Este tipo de consulta es principalmente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="91376-162">This query type is principally for internal use.</span></span> <span data-ttu-id="91376-163">Sin embargo, no todos los algoritmos son compatibles con esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="91376-163">However, not all algorithms support this functionality.</span></span> <span data-ttu-id="91376-164">Una marca indica la compatibilidad en el conjunto de filas de esquema MINING_SERVICES.</span><span class="sxs-lookup"><span data-stu-id="91376-164">Support is indicated by a flag in the MINING_SERVICES schema rowset.</span></span>  
  
 <span data-ttu-id="91376-165">Si desarrolla su propio algoritmo de complemento, podría usar esta instrucción para comprobar el contenido del modelo para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="91376-165">If you develop your own plug-in algorithm, you might use this statement to verify the content of your model for testing.</span></span>  
  
 <span data-ttu-id="91376-166">**Obtener la representación PMML de un modelo**</span><span class="sxs-lookup"><span data-stu-id="91376-166">**Get the PMML representation of a model**</span></span>  
 `SELECT * FROM <model>.PMML`  
  
 <span data-ttu-id="91376-167">Obtiene un documento XML que representa el modelo en formato PMML.</span><span class="sxs-lookup"><span data-stu-id="91376-167">Gets an XML document that represents the model in PMML format.</span></span> <span data-ttu-id="91376-168">No se admiten todos los tipos de modelos.</span><span class="sxs-lookup"><span data-stu-id="91376-168">Not all model types are supported.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_Examples"></a> <span data-ttu-id="91376-169">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="91376-169">Examples</span></span>  
 <span data-ttu-id="91376-170">Aunque algún contenido del modelo es estándar en todos los algoritmos, algunas partes del contenido varían en gran medida dependiendo del algoritmo que se usa para compilar el modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-170">Although some model content is standard across algorithms, some parts of the content vary greatly depending on the algorithm that you used to build the model.</span></span> <span data-ttu-id="91376-171">Por consiguiente, al crear una consulta de contenido, debe comprender qué información del modelo resulta más útil para su modelo específico.</span><span class="sxs-lookup"><span data-stu-id="91376-171">Therefore, when you create a content query, you must understand what information in the model is most useful to your specific model.</span></span>  
  
 <span data-ttu-id="91376-172">En esta sección se proporcionan algunos ejemplos para mostrar cómo la elección del algoritmo afecta al tipo de información que se almacena en el modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-172">A few examples are provided in this section to illustrate how the choice of algorithm affects the kind of information that is stored in the model.</span></span> <span data-ttu-id="91376-173">Para más información sobre el contenido del modelo de minería de datos y el contenido específico de cada tipo de modelo, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="91376-173">For more information about mining model content, and the content that is specific to each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
###  <a name="example-1-content-query-on-an-association-model"></a><a name="bkmk_Assoc"></a> <span data-ttu-id="91376-174">Ejemplo 1: consulta de contenido en un modelo de asociación</span><span class="sxs-lookup"><span data-stu-id="91376-174">Example 1: Content Query on an Association Model</span></span>  
 <span data-ttu-id="91376-175">La instrucción `SELECT FROM <model>.CONTENT`devuelve diferentes tipos de información, según el tipo de modelo que esté consultando.</span><span class="sxs-lookup"><span data-stu-id="91376-175">The statement, `SELECT FROM <model>.CONTENT`, returns different kinds of information, depending on the type of model you are querying.</span></span> <span data-ttu-id="91376-176">Para un modelo de asociación, una información clave es el *tipo de nodo*.</span><span class="sxs-lookup"><span data-stu-id="91376-176">For an association model, a key piece of information is the *node type*.</span></span> <span data-ttu-id="91376-177">Los nodos son como contenedores de información en el contenido del modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-177">Nodes are like containers for information in the model content.</span></span> <span data-ttu-id="91376-178">En un modelo de asociación, los nodos que representan reglas tienen un valor NODE_TYPE de 8, mientras que los nodos que representan conjuntos de elementos tienen un valor NODE_TYPE de 7.</span><span class="sxs-lookup"><span data-stu-id="91376-178">In an association model, nodes that represent rules have a NODE_TYPE value of 8, whereas nodes that represent itemsets have a NODE_TYPE value of 7.</span></span>  
  
 <span data-ttu-id="91376-179">Así, la consulta siguiente devuelve los 10 mejores conjuntos de elementos, clasificados según el soporte (la ordenación predeterminada).</span><span class="sxs-lookup"><span data-stu-id="91376-179">Thus, the following query returns the top 10 itemsets, ranked by support (the default ordering).</span></span>  
  
```  
SELECT TOP 10 NODE_DESCRIPTION, NODE_PROBABILITY, SUPPORT  
FROM <model>.CONTENT WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="91376-180">La consulta siguiente se basa en esta información.</span><span class="sxs-lookup"><span data-stu-id="91376-180">The following query builds on this information.</span></span> <span data-ttu-id="91376-181">La consulta devuelve tres columnas: el identificador del nodo, la regla completa y el producto en el lado derecho del conjunto de elementos; es decir, el producto que se predice que está asociado a otros productos como parte de un conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="91376-181">The query returns three columns: the ID of the node, the complete rule, and the product on the right-hand side of the itemset-that is, the product that is predicted to be associated with some other products as part of an itemset.</span></span>  
  
```  
SELECT FLATTENED NODE_UNIQUE_NAME, NODE_DESCRIPTION,  
     (SELECT RIGHT(ATTRIBUTE_NAME, (LEN(ATTRIBUTE_NAME)-LEN('Association model name')))   
FROM NODE_DISTRIBUTION  
WHERE LEN(ATTRIBUTE_NAME)>2  
)   
AS RightSideProduct  
FROM [<Association model name>].CONTENT  
WHERE NODE_TYPE = 8   
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="91376-182">La palabra clave FLATTENED indica que el conjunto de filas anidado se debe convertir en una tabla plana.</span><span class="sxs-lookup"><span data-stu-id="91376-182">The FLATTENED keyword indicates that the nested rowset should be converted into a flattened table.</span></span> <span data-ttu-id="91376-183">El atributo que representa el producto situado en el lado derecho de la regla se encuentra dentro de la tabla NODE_DISTRIBUTION; por consiguiente, solo recuperamos la fila que contiene un nombre de atributo, agregando el requisito de que la longitud sea mayor que 2.</span><span class="sxs-lookup"><span data-stu-id="91376-183">The attribute that represents the product on the right-hand side of the rule is contained in the NODE_DISTRIBUTION table; therefore, we retrieve only the row that contains an attribute name, by adding a requirement that the length be greater than 2.</span></span>  
  
 <span data-ttu-id="91376-184">Se utiliza una función de cadena sencilla para quitar el nombre del modelo de la tercera columna.</span><span class="sxs-lookup"><span data-stu-id="91376-184">A simple string function is used to remove the name of the model from the third column.</span></span> <span data-ttu-id="91376-185">(Normalmente, el nombre del modelo se antepone a los valores de las columnas anidadas).</span><span class="sxs-lookup"><span data-stu-id="91376-185">(Usually the model name is prefixed to the values of nested columns.)</span></span>  
  
 <span data-ttu-id="91376-186">La cláusula WHERE especifica que el valor de NODE_TYPE debe ser 8 para recuperar solo reglas.</span><span class="sxs-lookup"><span data-stu-id="91376-186">The WHERE clause specifies that the value of NODE_TYPE should be 8, to retrieve only rules.</span></span>  
  
 <span data-ttu-id="91376-187">Para obtener más ejemplos, vea [Ejemplos de consultas del modelo de asociación](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="91376-187">For more examples, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
###  <a name="example-2-content-query-on-a-decision-trees-model"></a><a name="bkmk_DecTree"></a> <span data-ttu-id="91376-188">Ejemplo 2: consulta de contenido en un modelo de árboles de decisión</span><span class="sxs-lookup"><span data-stu-id="91376-188">Example 2: Content Query on a Decision Trees Model</span></span>  
 <span data-ttu-id="91376-189">Un modelo del árbol de decisión se puede utilizar para la predicción así como para la clasificación.</span><span class="sxs-lookup"><span data-stu-id="91376-189">A decision tree model can be used for prediction as well as for classification.</span></span>  <span data-ttu-id="91376-190">En este ejemplo se supone que está utilizando el modelo para predecir un resultado, pero también desea descubrir qué factores o reglas se pueden utilizar para clasificar el resultado.</span><span class="sxs-lookup"><span data-stu-id="91376-190">This example assumes that you are using the model to predict an outcome, but you also want to find out which factors or rules can be used to classify the outcome.</span></span>  
  
 <span data-ttu-id="91376-191">En un modelo de árbol de decisión, los nodos se utilizan para representar árboles y nodos de hoja.</span><span class="sxs-lookup"><span data-stu-id="91376-191">In a decision tree model, nodes are used to represent both trees and leaf nodes.</span></span> <span data-ttu-id="91376-192">El título de cada nodo contiene la descripción de la ruta de acceso al resultado.</span><span class="sxs-lookup"><span data-stu-id="91376-192">The caption for each node contains the description of the path to the outcome.</span></span> <span data-ttu-id="91376-193">Por consiguiente, para realizar el seguimiento de la ruta de acceso de cualquier resultado determinado, debe identificar el nodo que lo contiene y obtener los detalles de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="91376-193">Therefore, to trace the path for any particular outcome, you need to identify the node that contains it, and get the details for that node.</span></span>  
  
 <span data-ttu-id="91376-194">En la consulta de predicción, agregue la función de predicción [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx) para obtener el identificador del nodo relacionado, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91376-194">In your prediction query, you add the prediction function [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), to get the ID of the related node, as shown in the following example:</span></span>  
  
```  
SELECT  Predict([Bike Buyer]), PredictNodeID([Bike Buyer])   
FROM [<decision tree model name>]  
PREDICTION JOIN   
<input rowset>   
```  
  
 <span data-ttu-id="91376-195">Una vez obtenido el identificador del nodo que contiene el resultado, puede recuperar la regla o la ruta de acceso que explica la predicción creando una consulta de contenido que incluya NODE_CAPTION como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="91376-195">Once you have the ID of the node that contains the outcome, you can retrieve the rule or path that explains the prediction by creating a content query that includes the NODE_CAPTION, as follows:</span></span>  
  
```  
SELECT NODE_CAPTION  
FROM [<decision tree model name>]   
WHERE NODE_UNIQUE_NAME= '<node id>'  
```  
  
 <span data-ttu-id="91376-196">Para obtener más ejemplos, vea [Ejemplos de consultas de modelos de árboles de decisión](decision-trees-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="91376-196">For more examples, see [Decision Trees Model Query Examples](decision-trees-model-query-examples.md).</span></span>  
  
##  <a name="working-with-the-query-results"></a><a name="bkmk_Results"></a><span data-ttu-id="91376-197">Trabajar con los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="91376-197">Working with the Query Results</span></span>  
 <span data-ttu-id="91376-198">Como demuestran los ejemplos, las consultas de contenido devuelven principalmente conjuntos de filas tabulares, pero también pueden incluir información de columnas anidadas.</span><span class="sxs-lookup"><span data-stu-id="91376-198">As the examples demonstrate, content queries mostly return tabular rowsets, but can also include information from nested columns.</span></span> <span data-ttu-id="91376-199">Es posible simplificar el conjunto de filas que se devuelven, pero esto puede dificultar el trabajo con los resultados.</span><span class="sxs-lookup"><span data-stu-id="91376-199">You can flatten the rowset that is returned, but this can make working with results more complex.</span></span> <span data-ttu-id="91376-200">El contenido del nodo NODE_DISTRIBUTION en concreto está anidado, pero contiene información muy interesante sobre el modelo.</span><span class="sxs-lookup"><span data-stu-id="91376-200">The content of the NODE_DISTRIBUTION node in particular is nested, but contains much interesting information about the model.</span></span>  
  
 <span data-ttu-id="91376-201">Para obtener más información sobre cómo trabajar con conjuntos de filas jerárquicos, vea la especificación OLEDB en MSDN.</span><span class="sxs-lookup"><span data-stu-id="91376-201">For more information about how to work with hierarchical rowsets, see the OLEDB specification on MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91376-202">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91376-202">See Also</span></span>  
 <span data-ttu-id="91376-203">[Descripción de la instrucción SELECT de DMX](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="91376-203">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 [<span data-ttu-id="91376-204">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="91376-204">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
