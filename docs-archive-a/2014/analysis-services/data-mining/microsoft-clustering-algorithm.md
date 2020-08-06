---
title: Algoritmo de clústeres de Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation algorithms [Analysis Services]
- nearest neighbor [Data Mining]
- clustering [Data Mining]
- clusters [Analysis Services]
- relationships [Analysis Services], clusters
- algorithms [data mining]
- classification algorithms [Analysis Services]
- datasets [Analysis Services]
- clustering algorithms [Analysis Services]
ms.assetid: 92a1e67e-f46e-4960-99b2-4d20f6192fbd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9cb14e1e2672cfaef883f0686fc29206b0c8e657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674449"
---
# <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="209f3-102">Algoritmo de clústeres de Microsoft</span><span class="sxs-lookup"><span data-stu-id="209f3-102">Microsoft Clustering Algorithm</span></span>
  <span data-ttu-id="209f3-103">El algoritmo de clústeres de [!INCLUDE[msCoName](../../includes/msconame-md.md)] es un algoritmo de segmentación suministrado por [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="209f3-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Clustering algorithm is a segmentation algorithm provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="209f3-104">El algoritmo utiliza técnicas iterativas para agrupar los casos de un conjunto de datos dentro de clústeres que contienen características similares.</span><span class="sxs-lookup"><span data-stu-id="209f3-104">The algorithm uses iterative techniques to group cases in a dataset into clusters that contain similar characteristics.</span></span> <span data-ttu-id="209f3-105">Estas agrupaciones son útiles para la exploración de datos, la identificación de anomalías en los datos y la creación de predicciones.</span><span class="sxs-lookup"><span data-stu-id="209f3-105">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>

 <span data-ttu-id="209f3-106">Los modelos de agrupación en clústeres identifican las relaciones en un conjunto de datos que no se podrían derivar lógicamente a través de la observación casual.</span><span class="sxs-lookup"><span data-stu-id="209f3-106">Clustering models identify relationships in a dataset that you might not logically derive through casual observation.</span></span> <span data-ttu-id="209f3-107">Por ejemplo, puede discernir lógicamente que las personas que se desplazan a sus trabajos en bicicleta no viven, por lo general, a gran distancia de sus centros de trabajo.</span><span class="sxs-lookup"><span data-stu-id="209f3-107">For example, you can logically discern that people who commute to their jobs by bicycle do not typically live a long distance from where they work.</span></span> <span data-ttu-id="209f3-108">Sin embargo, el algoritmo puede encontrar otras características que no son evidentes acerca de los trabajadores que se desplazan en bicicleta.</span><span class="sxs-lookup"><span data-stu-id="209f3-108">The algorithm, however, can find other characteristics about bicycle commuters that are not as obvious.</span></span> <span data-ttu-id="209f3-109">En el siguiente diagrama, el clúster A representa los datos sobre las personas que suelen conducir hasta el trabajo, en tanto que el clúster B representa los datos sobre las personas que van hasta allí en bicicleta.</span><span class="sxs-lookup"><span data-stu-id="209f3-109">In the following diagram, cluster A represents data about people who tend to drive to work, while cluster B represents data about people who tend to ride bicycles to work.</span></span>

 <span data-ttu-id="209f3-110">![Patrón de clústeres de tendencias de conmutador](../media/clustering-example.gif "Patrón de clústeres de tendencias de conmutador")</span><span class="sxs-lookup"><span data-stu-id="209f3-110">![Cluster pattern of commuter tendencies](../media/clustering-example.gif "Cluster pattern of commuter tendencies")</span></span>

 <span data-ttu-id="209f3-111">El algoritmo de clústeres se diferencia de otros algoritmos de minería de datos, como el algoritmo de árboles de decisión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] , en que no se tiene que designar una columna de predicción para generar un modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="209f3-111">The clustering algorithm differs from other data mining algorithms, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees algorithm, in that you do not have to designate a predictable column to be able to build a clustering model.</span></span> <span data-ttu-id="209f3-112">El algoritmo de clústeres entrena el modelo de forma estricta a partir de las relaciones que existen en los datos y de los clústeres que identifica el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="209f3-112">The clustering algorithm trains the model strictly from the relationships that exist in the data and from the clusters that the algorithm identifies.</span></span>

## <a name="example"></a><span data-ttu-id="209f3-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="209f3-113">Example</span></span>
 <span data-ttu-id="209f3-114">Considere un grupo de personas que comparten información demográfica similar y que adquieren productos similares de la empresa [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="209f3-114">Consider a group of people who share similar demographic information and who buy similar products from the [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] company.</span></span> <span data-ttu-id="209f3-115">Este grupo de personas representa un clúster de datos.</span><span class="sxs-lookup"><span data-stu-id="209f3-115">This group of people represents a cluster of data.</span></span> <span data-ttu-id="209f3-116">En una base de datos pueden existir varios clústeres como éstos.</span><span class="sxs-lookup"><span data-stu-id="209f3-116">Several such clusters may exist in a database.</span></span> <span data-ttu-id="209f3-117">Mediante la observación de las columnas que forman un clúster, puede ver con mayor claridad la forma en que los registros de un conjunto de datos se relacionan entre sí.</span><span class="sxs-lookup"><span data-stu-id="209f3-117">By observing the columns that make up a cluster, you can more clearly see how records in a dataset are related to one another.</span></span>

## <a name="how-the-algorithm-works"></a><span data-ttu-id="209f3-118">Cómo funciona el algoritmo</span><span class="sxs-lookup"><span data-stu-id="209f3-118">How the Algorithm Works</span></span>
 <span data-ttu-id="209f3-119">El algoritmo de clústeres de [!INCLUDE[msCoName](../../includes/msconame-md.md)] identifica primero las relaciones de un conjunto de datos y genera una serie de clústeres basándose en ellas.</span><span class="sxs-lookup"><span data-stu-id="209f3-119">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Clustering algorithm first identifies relationships in a dataset and generates a series of clusters based on those relationships.</span></span> <span data-ttu-id="209f3-120">Un gráfico de dispersión es una forma útil de representar visualmente el modo en que el algoritmo agrupa los datos, tal como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="209f3-120">A scatter plot is a useful way to visually represent how the algorithm groups data, as shown in the following diagram.</span></span> <span data-ttu-id="209f3-121">El gráfico de dispersión representa todos los casos del conjunto de datos; cada caso es un punto del gráfico.</span><span class="sxs-lookup"><span data-stu-id="209f3-121">The scatter plot represents all the cases in the dataset, and each case is a point on the graph.</span></span> <span data-ttu-id="209f3-122">Los clústeres agrupan los puntos del gráfico e ilustran las relaciones que identifica el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="209f3-122">The clusters group points on the graph and illustrate the relationships that the algorithm identifies.</span></span>

 <span data-ttu-id="209f3-123">![Gráfico de dispersión de casos en un conjunto de datos](../media/clustering-plot.gif "Gráfico de dispersión de casos en un conjunto de datos")</span><span class="sxs-lookup"><span data-stu-id="209f3-123">![Scatter plot of cases in a dataset](../media/clustering-plot.gif "Scatter plot of cases in a dataset")</span></span>

 <span data-ttu-id="209f3-124">Después de definir los clústeres, el algoritmo calcula el grado de perfección con que los clústeres representan las agrupaciones de puntos y, a continuación, intenta volver a definir las agrupaciones para crear clústeres que representen mejor los datos.</span><span class="sxs-lookup"><span data-stu-id="209f3-124">After first defining the clusters, the algorithm calculates how well the clusters represent groupings of the points, and then tries to redefine the groupings to create clusters that better represent the data.</span></span> <span data-ttu-id="209f3-125">El algoritmo establece una iteración en este proceso hasta que ya no es posible mejorar los resultados mediante la redefinición de los clústeres.</span><span class="sxs-lookup"><span data-stu-id="209f3-125">The algorithm iterates through this process until it cannot improve the results more by redefining the clusters.</span></span>

 <span data-ttu-id="209f3-126">Puede personalizar el funcionamiento del algoritmo seleccionando una técnica de agrupación en clústeres, limitando el número máximo de clústeres o cambiando la cantidad de soporte que se requiere para crear un clúster.</span><span class="sxs-lookup"><span data-stu-id="209f3-126">You can customize the way the algorithm works by selecting a specifying a clustering technique, limiting the maximum number of clusters, or changing the amount of support required to create a cluster.</span></span> <span data-ttu-id="209f3-127">Para obtener más información, vea [Referencia técnica del algoritmo de clústeres de Microsoft](microsoft-clustering-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-127">For more information, see [Microsoft Clustering Algorithm Technical Reference](microsoft-clustering-algorithm-technical-reference.md).</span></span>

## <a name="data-required-for-clustering-models"></a><span data-ttu-id="209f3-128">Datos requeridos para los modelos de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="209f3-128">Data Required for Clustering Models</span></span>
 <span data-ttu-id="209f3-129">Al preparar los datos para su uso en el entrenamiento de un modelo de agrupación en clústeres, conviene comprender qué requisitos son imprescindibles para el algoritmo concreto, incluidos el volumen de datos necesario y la forma en que estos datos se utilizan.</span><span class="sxs-lookup"><span data-stu-id="209f3-129">When you prepare data for use in training a clustering model, you should understand the requirements for the particular algorithm, including how much data is needed, and how the data is used.</span></span>

 <span data-ttu-id="209f3-130">Los requisitos para un modelo de agrupación en clústeres son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="209f3-130">The requirements for a clustering model are as follows:</span></span>

-   <span data-ttu-id="209f3-131">**Una columna de una sola clave** : cada modelo debe contener una columna numérica o de texto que identifique cada registro de manera única.</span><span class="sxs-lookup"><span data-stu-id="209f3-131">**A single key column** Each model must contain one numeric or text column that uniquely identifies each record.</span></span> <span data-ttu-id="209f3-132">No están permitidas las claves compuestas.</span><span class="sxs-lookup"><span data-stu-id="209f3-132">Compound keys are not allowed.</span></span>

-   <span data-ttu-id="209f3-133">**Columnas de entrada** Cada modelo debe tener al menos una columna de entrada que contenga los valores que se utilizan para generar los clústeres.</span><span class="sxs-lookup"><span data-stu-id="209f3-133">**Input columns** Each model must contain at least one input column that contains the values that are used to build the clusters.</span></span> <span data-ttu-id="209f3-134">Puede tener tantas columnas de entrada como desee, pero dependiendo del número de valores existentes en cada columna, la adición de columnas adicionales podría aumentar el tiempo necesario para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="209f3-134">You can have as many input columns as you want, but depending on the number of values in each column, the addition of extra columns can increase the time it takes to train the model.</span></span>

-   <span data-ttu-id="209f3-135">**Una columna de predicción opcional** El algoritmo no necesita una columna de predicción para generar el modelo, pero puede agregar una columna de predicción de casi cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="209f3-135">**Optional predictable column** The algorithm does not need a predictable column to build the model, but you can add a predictable column of almost any data type.</span></span> <span data-ttu-id="209f3-136">Los valores de la columna de predicción se pueden tratar como entradas del modelo de agrupación en clústeres, o se puede especificar que solo se utilicen para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="209f3-136">The values of the predictable column can be treated as input to the clustering model, or you can specify that it be used for prediction only.</span></span> <span data-ttu-id="209f3-137">Por ejemplo, si desea predecir los ingresos del cliente agrupando en clústeres de acuerdo con datos demográficos como la región o la edad, se deben especificar los ingresos como `PredictOnly` y agregar todas las demás columnas, como la región o la edad, como entradas.</span><span class="sxs-lookup"><span data-stu-id="209f3-137">For example, if you want to predict customer income by clustering on demographics such as region or age, you would specify income as `PredictOnly` and add all the other columns, such as region or age, as inputs.</span></span>

 <span data-ttu-id="209f3-138">Para obtener información más detallada sobre los tipos de contenido y los tipos de datos compatibles con los modelos de agrupación en clústeres, vea la sección Requisitos de [Referencia técnica del algoritmo de clústeres de Microsoft](microsoft-clustering-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-138">For more detailed information about the content types and data types supported for clustering models, see the Requirements section of [Microsoft Clustering Algorithm Technical Reference](microsoft-clustering-algorithm-technical-reference.md).</span></span>

## <a name="viewing-a-clustering-model"></a><span data-ttu-id="209f3-139">Ver un modelo de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="209f3-139">Viewing a Clustering Model</span></span>
 <span data-ttu-id="209f3-140">Para explorar el modelo, puede utilizar el **Visor de clústeres de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="209f3-140">To explore the model, you can use the **Microsoft Cluster Viewer**.</span></span> <span data-ttu-id="209f3-141">Cuando se observa un modelo de agrupación en clústeres, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] presenta los clústeres en un diagrama que muestra las relaciones existentes entre ellos, además de un perfil detallado de cada clúster, una lista de los atributos que diferencian cada clúster de los demás, y las características de todo el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="209f3-141">When you view a clustering model, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] shows you the clusters in a diagram that depicts the relationships among clusters, and also provides a detailed profile of each cluster, a list of the attributes that distinguish each cluster from the others, and the characteristics of the entire training data set.</span></span> <span data-ttu-id="209f3-142">Para obtener más información, vea [Examinar un modelo usando el Visor de clústeres de Microsoft](browse-a-model-using-the-microsoft-cluster-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-142">For more information, see [Browse a Model Using the Microsoft Cluster Viewer](browse-a-model-using-the-microsoft-cluster-viewer.md).</span></span>

 <span data-ttu-id="209f3-143">Si desea obtener más detalles, puede examinar el modelo en el [Visor de árbol de contenido genérico de Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-143">If you want to know more detail, you can browse the model in the [Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span> <span data-ttu-id="209f3-144">El contenido almacenado para el modelo incluye la distribución para todos los valores de cada nodo, la probabilidad de cada clúster y otros datos.</span><span class="sxs-lookup"><span data-stu-id="209f3-144">The content stored for the model includes the distribution for all values in each node, the probability of each cluster, and other information.</span></span> <span data-ttu-id="209f3-145">Para obtener más información, vea [Contenido del modelo de minería de datos para los modelos de agrupación en clústeres &#40;Analysis Services - Minería de datos&#41;](mining-model-content-for-clustering-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-145">For more information, see [Mining Model Content for Clustering Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-clustering-models-analysis-services-data-mining.md).</span></span>

## <a name="creating-predictions"></a><span data-ttu-id="209f3-146">Crear predicciones</span><span class="sxs-lookup"><span data-stu-id="209f3-146">Creating Predictions</span></span>
 <span data-ttu-id="209f3-147">Una vez entrenado el modelo, los resultados se almacenan como un conjunto de patrones que se puede explorar o utilizar para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="209f3-147">After the model has been trained, the results are stored as a set of patterns, which you can explore or use to make predictions.</span></span>

 <span data-ttu-id="209f3-148">Puede crear consultas para devolver predicciones sobre si los nuevos datos se ajustan a los clústeres que se han detectado, o para obtener estadísticas descriptivas sobre los clústeres.</span><span class="sxs-lookup"><span data-stu-id="209f3-148">You can create queries to return predictions about whether new data fits into the clusters that were discovered, or to obtain descriptive statistics about the clusters.</span></span>

 <span data-ttu-id="209f3-149">Para obtener información sobre cómo crear consultas en un modelo de minería de datos, vea [Consultas de minería de datos](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-149">For information about how to create queries against a data mining model, see [Data Mining Queries](data-mining-queries.md).</span></span> <span data-ttu-id="209f3-150">Para obtener ejemplos de cómo usar las consultas con un modelo de agrupación en clústeres, vea [Ejemplos de consultas de modelos de agrupación en clústeres](clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="209f3-150">For examples of how to use queries with a clustering model, see [Clustering Model Query Examples](clustering-model-query-examples.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="209f3-151">Observaciones</span><span class="sxs-lookup"><span data-stu-id="209f3-151">Remarks</span></span>

-   <span data-ttu-id="209f3-152">Admite el uso del Lenguaje de marcado de modelos de predicción (PMML) para crear modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="209f3-152">Supports the use of Predictive Model Markup Language (PMML) to create mining models.</span></span>

-   <span data-ttu-id="209f3-153">Admite la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="209f3-153">Supports drillthrough.</span></span>

-   <span data-ttu-id="209f3-154">Admite el uso de modelos de minería de datos OLAP y la creación de dimensiones de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="209f3-154">Supports the use of OLAP mining models and the creation of data mining dimensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="209f3-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="209f3-155">See Also</span></span>
 <span data-ttu-id="209f3-156">[Algoritmos de minería de datos &#40;Analysis Services de minería de datos&#41;el](data-mining-algorithms-analysis-services-data-mining.md) [algoritmo de clústeres de Microsoft](microsoft-clustering-algorithm-technical-reference.md) [contenido del modelo de minería de datos para los modelos de agrupación en clústeres &#40;Analysis Services-ejemplos de](mining-model-content-for-clustering-models-analysis-services-data-mining.md) [consultas del modelo de agrupación en clústeres](clustering-model-query-examples.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="209f3-156">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) [Microsoft Clustering Algorithm Technical Reference](microsoft-clustering-algorithm-technical-reference.md) [Mining Model Content for Clustering Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-clustering-models-analysis-services-data-mining.md) [Clustering Model Query Examples](clustering-model-query-examples.md)</span></span>

