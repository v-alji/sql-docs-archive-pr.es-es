---
title: Consultar los conjuntos de filas de esquema de minería de datos (Analysis Services-minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- schema rowsets [Analysis Services], data mining
- data mining [Analysis Services], queries
- mining model content
- data mining [Analysis Services], schema rowsets
- schema rowsets [Analysis Services], retrieving
- data mining [Analysis Services], troubleshooting
ms.assetid: 442d8c29-07c7-45de-9a15-d556059f68d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60c802256454ee68d04392e685fa4acabf6c12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675672"
---
# <a name="querying-the-data-mining-schema-rowsets-analysis-services---data-mining"></a><span data-ttu-id="f772c-102">Consultar los conjuntos de filas de esquema de minería de datos (Analysis Services - Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="f772c-102">Querying the Data Mining Schema Rowsets (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="f772c-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)],muchos de los conjuntos de filas de esquema de minería de datos de OLE DB existentes se han expuesto como un conjunto de tablas del sistema que puede consultar con facilidad utilizando las instrucciones de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="f772c-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], many of the existing OLE DB data mining schema rowsets are exposed as a set of system tables that you can query by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="f772c-104">Creando consultas para el conjunto de filas de esquema de minería de datos, puede identificar los servicios que están disponibles, obtener actualizaciones sobre el estado de los modelos y estructuras, y obtener detalles sobre el contenido o los parámetros del modelo.</span><span class="sxs-lookup"><span data-stu-id="f772c-104">By creating queries against the data mining schema rowset, you can identify the services that are available, get updates on the status of your models and structures, and find out details about the model content or parameters.</span></span> <span data-ttu-id="f772c-105">Para obtener una descripción de los conjuntos de filas de esquema de minería de datos, vea [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="f772c-105">For a description of the data mining schema rowsets, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f772c-106">También puede consultar los conjuntos de filas de esquema de minería de datos utilizando XMLA.</span><span class="sxs-lookup"><span data-stu-id="f772c-106">You can also query the data mining schema rowsets by using XMLA.</span></span> <span data-ttu-id="f772c-107">Para más información sobre cómo hacer esto en SQL Server Management Studio, vea [Crear una consulta de minería de datos utilizando XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="f772c-107">For more information about how to do this in SQL Server Management Studio, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="list-of-data-mining-schema-rowsets"></a><span data-ttu-id="f772c-108">Lista de conjuntos de filas de esquema de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f772c-108">List of Data Mining Schema Rowsets</span></span>  
 <span data-ttu-id="f772c-109">En la tabla siguiente se muestran los conjuntos de filas de esquema de minería de datos que pueden ser útiles para consultar y supervisar.</span><span class="sxs-lookup"><span data-stu-id="f772c-109">The following table lists the data mining schema rowsets that may be useful for querying and monitoring.</span></span>  
  
|<span data-ttu-id="f772c-110">Nombre del conjunto de filas</span><span class="sxs-lookup"><span data-stu-id="f772c-110">Rowset name</span></span>|<span data-ttu-id="f772c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f772c-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f772c-112">DMSCHEMA_MINING_MODELS</span><span class="sxs-lookup"><span data-stu-id="f772c-112">DMSCHEMA_MINING_MODELS</span></span>|<span data-ttu-id="f772c-113">Muestra todos los modelos de minería de datos del contexto actual.</span><span class="sxs-lookup"><span data-stu-id="f772c-113">Lists all mining models in the current context.</span></span><br /><br /> <span data-ttu-id="f772c-114">Incluye información tal como la fecha de creación, los parámetros utilizados para crear el modelo y el tamaño del conjunto de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="f772c-114">Includes such information as the date created, parameters used to create the model, and the size of the training set.</span></span>|  
|<span data-ttu-id="f772c-115">DMSCHEMA_MINING_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f772c-115">DMSCHEMA_MINING_COLUMNS</span></span>|<span data-ttu-id="f772c-116">Muestra todas las columnas utilizadas en modelos de minería de datos en el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="f772c-116">Lists all columns used in mining models in the current context.</span></span><br /><br /> <span data-ttu-id="f772c-117">La información incluye funciones de asignación a columna de origen de estructura de minería de datos, tipo de datos, precisión y funciones de predicción que se pueden utilizar con la columna.</span><span class="sxs-lookup"><span data-stu-id="f772c-117">Information includes mapping to mining structure source column, data type, precision, and prediction functions that can be used with the column.</span></span>|  
|<span data-ttu-id="f772c-118">DMSCHEMA_MINING_STRUCTURES</span><span class="sxs-lookup"><span data-stu-id="f772c-118">DMSCHEMA_MINING_STRUCTURES</span></span>|<span data-ttu-id="f772c-119">Muestra toda la estructura de minería de datos del contexto actual.</span><span class="sxs-lookup"><span data-stu-id="f772c-119">Lists all mining structure in the current context.</span></span><br /><br /> <span data-ttu-id="f772c-120">La información incluye si se rellena la estructura, la última fecha en la que se procesó la estructura y la definición del conjunto de datos de exclusiones para la estructura, si existe.</span><span class="sxs-lookup"><span data-stu-id="f772c-120">Information includes whether the structure is populated, the date the structure was last processed, and the definition of the holdout data set for the structure, if any.</span></span>|  
|<span data-ttu-id="f772c-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f772c-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span></span>|<span data-ttu-id="f772c-122">Muestra todas las columnas utilizadas en estructuras de minería en el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="f772c-122">Lists all columns used in mining structures in the current context.</span></span><br /><br /> <span data-ttu-id="f772c-123">La información incluye el tipo de contenido y el tipo de datos, la nulabilidad y si la columna contiene los datos de tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="f772c-123">Information includes content type and data type, nullability, and whether the column contains nested table data.</span></span>|  
|<span data-ttu-id="f772c-124">DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="f772c-124">DMSCHEMA_MINING_SERVICES</span></span>|<span data-ttu-id="f772c-125">Muestra la lista de servicios o algoritmos de minería que están disponibles en el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="f772c-125">Lists all mining services, or algorithms, that are available on the specified server.</span></span><br /><br /> <span data-ttu-id="f772c-126">La información incluye marcas de modelado compatibles, tipos de entrada y tipos de origen de datos compatibles.</span><span class="sxs-lookup"><span data-stu-id="f772c-126">Information includes supported modeling flags, input types, and supported data source types.</span></span>|  
|<span data-ttu-id="f772c-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f772c-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span></span>|<span data-ttu-id="f772c-128">Muestra todos los parámetros para servicios de minería que están disponibles en la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f772c-128">Lists all parameters for the mining services that are available on the current instance.</span></span><br /><br /> <span data-ttu-id="f772c-129">La información incluye el tipo de datos para cada parámetro, los valores predeterminados y los límites superiores e inferiores.</span><span class="sxs-lookup"><span data-stu-id="f772c-129">Information includes the data type for each parameter, the default values, and the upper and lower limits.</span></span>|  
|<span data-ttu-id="f772c-130">DMSCHEMA_MODEL_CONTENT</span><span class="sxs-lookup"><span data-stu-id="f772c-130">DMSCHEMA_MODEL_CONTENT</span></span>|<span data-ttu-id="f772c-131">Devuelve el contenido del modelo si se ha procesado el modelo.</span><span class="sxs-lookup"><span data-stu-id="f772c-131">Returns the content of the model if the model has been processed.</span></span><br /><br /> <span data-ttu-id="f772c-132">Para obtener más información, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f772c-132">For more information, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>|  
|<span data-ttu-id="f772c-133">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="f772c-133">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="f772c-134">Muestra todas las bases de datos (catálogos) de la instancia actual de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f772c-134">Lists all databases (catalogs) in the current instance of Analysis Services.</span></span>|  
|<span data-ttu-id="f772c-135">MDSCHEMA_INPUT_DATASOURCES</span><span class="sxs-lookup"><span data-stu-id="f772c-135">MDSCHEMA_INPUT_DATASOURCES</span></span>|<span data-ttu-id="f772c-136">Muestra todos los orígenes de datos de la instancia actual de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f772c-136">Lists all data sources in the current instance of Analysis Services.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f772c-137">La lista de la tabla no es completa; muestra solo los conjuntos de filas que pueden tener más interés para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="f772c-137">The list in the table is not comprehensive; it shows only those rowsets that may be of most interest for troubleshooting.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f772c-138">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f772c-138">Examples</span></span>  
 <span data-ttu-id="f772c-139">En la sección siguiente se proporcionan algunos ejemplos de consultas para los conjuntos de filas de esquema de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f772c-139">The following section provides some examples of queries against the data mining schema rowsets.</span></span>  
  
### <a name="example-1-list-data-mining-services"></a><span data-ttu-id="f772c-140">Ejemplo 1: lista de servicios de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f772c-140">Example 1: List Data Mining Services</span></span>  
 <span data-ttu-id="f772c-141">La consulta siguiente devuelve una lista de servicios de minería que están disponibles en el servidor actual, es decir, los algoritmos que están habilitados.</span><span class="sxs-lookup"><span data-stu-id="f772c-141">The following query returns a list of the mining services that are available on the current server, meaning the algorithms that are enabled.</span></span> <span data-ttu-id="f772c-142">Las columnas proporcionadas para cada servicio de minería incluyen las marcas de modelado y tipos de contenido que pueden ser utilizados por cada algoritmo, el GUID para cada servicio y los límites de predicción que se puede haber agregado para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="f772c-142">The columns provided for each mining service include the modeling flags and content types that can be used by each algorithm, the GUID for each service, and any prediction limits that may have been added for each service.</span></span>  
  
```  
SELECT *  
FROM $system.DMSCHEMA_MINING_SERVICES  
```  
  
### <a name="example-2-list-mining-model-parameters"></a><span data-ttu-id="f772c-143">Ejemplo 2: lista de parámetros de modelo de minería</span><span class="sxs-lookup"><span data-stu-id="f772c-143">Example 2: List Mining Model Parameters</span></span>  
 <span data-ttu-id="f772c-144">En el ejemplo siguiente se devuelven los parámetros que se utilizaron para crear un modelo de minería concreto:</span><span class="sxs-lookup"><span data-stu-id="f772c-144">The following example returns the parameters that were used to create a specific mining model:</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
### <a name="example-3-list-all-rowsets"></a><span data-ttu-id="f772c-145">Ejemplo 3: lista de todos los conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="f772c-145">Example 3: List All Rowsets</span></span>  
 <span data-ttu-id="f772c-146">En el ejemplo siguiente se devuelve una lista completa de los conjuntos de filas que están disponibles en el servidor actual:</span><span class="sxs-lookup"><span data-stu-id="f772c-146">The following example returns a comprehensive list of the rowsets that are available on the current server:</span></span>  
  
```  
SELECT *   
FROM $system.DBSCHEMA_TABLES  
```  
  
## <a name="see-also"></a><span data-ttu-id="f772c-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f772c-147">See Also</span></span>  
 [<span data-ttu-id="f772c-148">Conceptos de la solución de problemas (Analysis Services - Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="f772c-148">Troubleshooting Concepts (Analysis Services - Data Mining)</span></span>](https://msdn.microsoft.com/library/cc645881.aspx)  
  
  
