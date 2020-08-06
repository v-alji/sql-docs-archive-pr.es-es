---
title: Diseñador de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], structure
- mining structures [Analysis Services], modifying
- data mining editor [Analysis Services]
- Data Mining Designer
- data mining [Analysis Services], modifying
ms.assetid: 2540db5b-2bf3-4b6c-87c8-79c48d71acce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820cde158dfabff525081060369daace0e83c8dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663194"
---
# <a name="data-mining-designer"></a><span data-ttu-id="6a5d0-102">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="6a5d0-102">Data Mining Designer</span></span>
  <span data-ttu-id="6a5d0-103">El diseñador de minería de datos es el entorno principal en el que se trabaja con los modelos de minería de datos en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a5d0-103">Data Mining Designer is the primary environment in which you work with mining models in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="6a5d0-104">Puede obtener acceso al diseñador seleccionando una estructura de minería de datos existente o utilizando el Asistente para minería de datos para crear una nueva estructura y un nuevo modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-104">You can access the designer either by selecting an existing mining structure, or by using the Data Mining Wizard to create a new mining structure and mining model.</span></span> <span data-ttu-id="6a5d0-105">Puede usar el Diseñador de minería de datos para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6a5d0-105">You can use Data Mining Designer to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6a5d0-106">Modificar la estructura y el modelo de minería de datos que se crearon inicialmente con el Asistente para minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-106">Modify the mining structure and the mining model that were initially created by the Data Mining Wizard.</span></span>  
  
-   <span data-ttu-id="6a5d0-107">Crear nuevos modelos basados en una estructura de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-107">Create new models based on an existing mining structure.</span></span>  
  
-   <span data-ttu-id="6a5d0-108">Entrenar y examinar modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-108">Train and browse mining models.</span></span>  
  
-   <span data-ttu-id="6a5d0-109">Comparar modelos mediante gráficos de precisión.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-109">Compare models by using accuracy charts.</span></span>  
  
-   <span data-ttu-id="6a5d0-110">Crear consultas de predicción basadas en modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-110">Create prediction queries based on mining models.</span></span>  
  
## <a name="mining-structure-tab"></a><span data-ttu-id="6a5d0-111">Pestaña Estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-111">Mining Structure Tab</span></span>  
 <span data-ttu-id="6a5d0-112">Utilice la pestaña **Estructura de minería de datos** para agregar columnas y modificar las propiedades de una estructura de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-112">Use the **Mining Structure** tab to add columns and modify the properties of an existing mining structure.</span></span> <span data-ttu-id="6a5d0-113">Las tareas y los temas siguientes proporcionan más información sobre cómo trabajar con estructuras de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="6a5d0-113">The following tasks and topics provide more information about working with mining structures:</span></span>  
  
 [<span data-ttu-id="6a5d0-114">Estructuras de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="6a5d0-114">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="6a5d0-115">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
## <a name="mining-models-tab"></a><span data-ttu-id="6a5d0-116">Pestaña Modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-116">Mining Models Tab</span></span>  
 <span data-ttu-id="6a5d0-117">Utilice la pestaña **Modelos de minería de datos** para administrar modelos de minería de datos existentes y crear otros nuevos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-117">Use the **Mining Models** tab to manage existing mining models and to create new models.</span></span> <span data-ttu-id="6a5d0-118">Los modelos de minería de datos siempre se basan en una estructura de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-118">Mining models are always based on an existing mining structure .</span></span>  
  
 <span data-ttu-id="6a5d0-119">En la pestaña **Modelos de minería de datos** , puede cambiar el tipo de algoritmo, agregar o quitar columnas asociadas con la estructura del modelo, ajustar propiedades de columna específicas del algoritmo, especificar el uso de la columna del modelo de minería de datos y ajustar parámetros de algoritmo asociados con el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-119">In the **Mining Models** tab, you can change the algorithm type, add or remove columns that are associated with the model structure, adjust algorithm-specific column properties, specify the mining model column usage, and adjust algorithm parameters that are associated with the mining model.</span></span> <span data-ttu-id="6a5d0-120">También puede procesar la estructura de minería de datos junto con los modelos seleccionados o con todos los modelos asociados.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-120">You can also process the mining structure together with selected models or with all the associated models.</span></span>  
  
 <span data-ttu-id="6a5d0-121">Vea los temas siguientes para obtener más información sobre cómo trabajar con los modelos de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="6a5d0-121">See the following topics for more information about working with mining models:</span></span>  
  
 [<span data-ttu-id="6a5d0-122">Modelos de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="6a5d0-122">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="6a5d0-123">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-123">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
## <a name="mining-model-viewer-tab"></a><span data-ttu-id="6a5d0-124">Pestaña Visor de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-124">Mining Model Viewer Tab</span></span>  
 <span data-ttu-id="6a5d0-125">Utilice la pestaña **Visor de modelos de minería de datos** para explorar visualmente los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-125">Use the **Mining Model Viewer** tab to visually explore your mining models.</span></span> <span data-ttu-id="6a5d0-126">Cada modelo de minería de datos está asociado con un visor personalizado que muestra el contenido específico de ese modelo.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-126">Each mining model is associated with a custom viewer that displays content that is specific to that model.</span></span> <span data-ttu-id="6a5d0-127">También puede ver el contenido del modelo de minería de datos utilizando el visor de contenido.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-127">You can also view mining model content by using the content viewer.</span></span>  
  
 <span data-ttu-id="6a5d0-128">Vea los temas siguientes para obtener más información sobre cómo explorar los modelos de minería de datos con los visores de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="6a5d0-128">See the following topics for more information about exploring mining models with the data mining viewers:</span></span>  
  
 [<span data-ttu-id="6a5d0-129">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-129">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
 [<span data-ttu-id="6a5d0-130">Tareas y procedimientos del Visor de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-130">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
## <a name="mining-accuracy-chart-tab"></a><span data-ttu-id="6a5d0-131">Pestaña Gráfico de precisión de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-131">Mining Accuracy Chart Tab</span></span>  
 <span data-ttu-id="6a5d0-132">Utilice la pestaña **Gráfico de precisión de minería de datos** para probar la precisión de predicción de un único modelo de minería de datos o para comparar la eficacia de varios modelos de minería de datos contenidos en una estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-132">Use the **Mining Accuracy Chart** tab to test the predictive accuracy of a single mining model, or to compare the effectiveness of multiple mining models contained within a mining structure.</span></span> <span data-ttu-id="6a5d0-133">La pestaña contiene herramientas para filtrar los datos, seleccionar modelos y mostrar los resultados en un gráfico de elevación, en un gráfico de beneficios o en una matriz de clasificación.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-133">The tab contains tools for filtering the data, selecting mining models, and displaying the results in a lift chart, profit chart, or classification matrix.</span></span>  
  
 <span data-ttu-id="6a5d0-134">Vea los siguientes temas para obtener más información acerca de la prueba y la validación de modelos de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="6a5d0-134">See the following topics for more information about testing and validating mining models:</span></span>  
  
 [<span data-ttu-id="6a5d0-135">Prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="6a5d0-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
 [<span data-ttu-id="6a5d0-136">Tareas y procedimientos de prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="6a5d0-136">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
## <a name="mining-model-prediction-tab"></a><span data-ttu-id="6a5d0-137">Pestaña Predicción de modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-137">Mining Model Prediction Tab</span></span>  
 <span data-ttu-id="6a5d0-138">La pestaña **Predicción de modelo de minería de datos** incluye el Generador de consultas de predicción, que se puede usar para crear consultas de predicción DMX (Extensiones de minería de datos).</span><span class="sxs-lookup"><span data-stu-id="6a5d0-138">The **Mining Model Prediction** tab includes Prediction Query Builder, which you can use to create a Data Mining Extensions (DMX) prediction query.</span></span> <span data-ttu-id="6a5d0-139">La pestaña contiene herramientas para especificar modelos de minería de datos y tablas de entrada, asignar las columnas del modelo de minería de datos a las columnas de la tabla de entrada, agregar funciones a una consulta y especificar criterios para cada columna.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-139">The tab contains tools for specifying mining models and input tables, mapping the columns in the mining model to columns in the input table, adding functions to a query, and specifying criteria for each column.</span></span>  
  
 <span data-ttu-id="6a5d0-140">Tras diseñar una consulta, puede utilizar diferentes vistas de la pestaña para mostrar los resultados de la consulta y para modificarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-140">After you design a query, you can use different views in the tab to display the results of the query and to modify the query manually.</span></span> <span data-ttu-id="6a5d0-141">También puede guardar los resultados de la consulta en una tabla de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-141">You can also save the results of the query to a table in a database.</span></span>  
  
 <span data-ttu-id="6a5d0-142">Vea los temas siguientes para obtener más información sobre cómo crear consultas de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="6a5d0-142">See the following topics for more information about creating data mining queries:</span></span>  
  
 [<span data-ttu-id="6a5d0-143">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-143">Data Mining Queries</span></span>](data-mining-queries.md)  
  
 [<span data-ttu-id="6a5d0-144">Tareas y procedimientos de Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-144">Data Mining Query Tasks and How-tos</span></span>](data-mining-query-tasks-and-how-tos.md)  
  
## <a name="see-also"></a><span data-ttu-id="6a5d0-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a5d0-145">See Also</span></span>  
 [<span data-ttu-id="6a5d0-146">Soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="6a5d0-146">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
  
