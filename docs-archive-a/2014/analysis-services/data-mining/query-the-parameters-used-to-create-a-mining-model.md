---
title: Consultar los parámetros usados para crear un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
author: minewiskan
ms.author: owend
ms.openlocfilehash: a3802a0d70579f613accbe6abd310da909751b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746621"
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a><span data-ttu-id="60bba-102">Consultar los parámetros usados para crear un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="60bba-102">Query the Parameters Used to Create a Mining Model</span></span>
  <span data-ttu-id="60bba-103">La composición de un modelo de minería de datos no solo se ve afectada por los casos de entrenamiento, sino también por los parámetros que se establecieron al crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="60bba-103">The composition of a mining model is affected not only by the training cases, but by the parameters that were set when the model was created.</span></span> <span data-ttu-id="60bba-104">Por lo tanto, es posible que la recuperación de la configuración de parámetros de un modelo existente resulte de utilidad para comprender mejor el comportamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="60bba-104">Therefore, you might find it useful to retrieve the parameter settings of an existing model to better understand the behavior of the model.</span></span> <span data-ttu-id="60bba-105">La recuperación de parámetros también resulta útil al documentar una versión determinada del modelo.</span><span class="sxs-lookup"><span data-stu-id="60bba-105">Retrieving parameters is also useful when documenting a particular version of that model.</span></span>  
  
 <span data-ttu-id="60bba-106">Para buscar los parámetros que se utilizaron al crear el modelo, cree una consulta en uno de los conjuntos de filas de esquema del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="60bba-106">To find the parameters that were used when the model was created, you create a query against one of the mining model schema rowsets.</span></span> <span data-ttu-id="60bba-107">En [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], estos conjuntos de filas de esquema se exponen como un conjunto de vistas del sistema que se pueden consultar fácilmente mediante la sintaxis de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="60bba-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], these schema rowsets are exposed as a set of system views that you can query easily by using Transact-SQL syntax.</span></span> <span data-ttu-id="60bba-108">Este procedimiento describe cómo crear una consulta que devuelva los parámetros que se utilizaron para crear el modelo de minería de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="60bba-108">This procedure describes how to create a query that returns the parameters that were used to create the specified mining model.</span></span>  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a><span data-ttu-id="60bba-109">Para abrir una ventana Consulta para una consulta de conjunto de filas de esquema</span><span class="sxs-lookup"><span data-stu-id="60bba-109">To open a Query window for a schema rowset query</span></span>  
  
1.  <span data-ttu-id="60bba-110">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene el modelo que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="60bba-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the model you want to query.</span></span>  
  
2.  <span data-ttu-id="60bba-111">Haga clic con el botón derecho en el nombre de la instancia, seleccione **Nueva consulta**y, después, seleccione **DMX**.</span><span class="sxs-lookup"><span data-stu-id="60bba-111">Right-click the instance name, select **New Query**, and then select **DMX**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60bba-112"> También puede crear una consulta en un modelo de minería de datos utilizando la plantilla **MDX** .</span><span class="sxs-lookup"><span data-stu-id="60bba-112">You can also create a query against a data mining model by using the **MDX** template.</span></span>  
  
3.  <span data-ttu-id="60bba-113">Si la instancia contiene varias bases de datos, seleccione la base de datos que contiene el modelo que desea consultar en la lista **Bases de datos disponibles** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="60bba-113">If the instance contains multiple databases, select the database that contains the model you want to query from the **Available Databases** list in the toolbar.</span></span>  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a><span data-ttu-id="60bba-114">Para devolver los parámetros de un modelo de minería de datos existente</span><span class="sxs-lookup"><span data-stu-id="60bba-114">To return model parameters for an existing mining model</span></span>  
  
1.  <span data-ttu-id="60bba-115">En el panel de consulta DMX, escriba o pegue el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="60bba-115">In the DMX query pane, type or paste the following text:</span></span>  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  <span data-ttu-id="60bba-116">En el Explorador de objetos, seleccione el modelo de minería de datos que desee y, a continuación, arrástrelo hasta el panel Consulta DMX y sitúelo entre las comillas simples.</span><span class="sxs-lookup"><span data-stu-id="60bba-116">In Object Explorer, select the mining model you want, and then drag it into the DMX Query pane, between the single quotation marks.</span></span>  
  
3.  <span data-ttu-id="60bba-117">Presione F5 o haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="60bba-117">Press F5, or click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60bba-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60bba-118">Example</span></span>  
 <span data-ttu-id="60bba-119">El código siguiente devuelve una lista de los parámetros que se utilizaron para crear el modelo de minería de datos generado en el [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="60bba-119">The following code returns a list of the parameters that were used to create the mining model that you build in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="60bba-120">Estos parámetros incluyen los valores explícitos para cualquier parámetro predeterminado utilizado por los servicios de minería de datos ofrecidos por los proveedores en el servidor.</span><span class="sxs-lookup"><span data-stu-id="60bba-120">These parameters include the explicit values for any defaults used by the mining services available from providers on the server.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 <span data-ttu-id="60bba-121">En el ejemplo de código se devuelven los parámetros siguientes para el modelo de agrupación en clústeres:</span><span class="sxs-lookup"><span data-stu-id="60bba-121">The code example returns the following parameters for the clustering model:</span></span>  
  
 <span data-ttu-id="60bba-122">Resultados del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60bba-122">eExample Results:</span></span>  
  
 <span data-ttu-id="60bba-123">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60bba-123">MINING_PARAMETERS</span></span>  
  
 <span data-ttu-id="60bba-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span><span class="sxs-lookup"><span data-stu-id="60bba-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60bba-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60bba-125">See Also</span></span>  
 <span data-ttu-id="60bba-126">[Tareas y procedimientos de consulta de minería de datos](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="60bba-126">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="60bba-127">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="60bba-127">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
