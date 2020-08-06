---
title: Asistente para clúster (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clustering [data mining]
ms.assetid: 85b25625-a7ab-4960-9f9c-df22e8ecae37
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90500ae627bcafd1ca5ce17114dac9df9939691d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670681"
---
# <a name="cluster-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="062e6-102">Asistente para clúster (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="062e6-102">Cluster Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="062e6-103">![Asistente para clúster, cinta de opciones Minería de datos](media/dmc-cluster.gif "Asistente para clúster, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="062e6-103">![Cluster wizard in Data Mining ribbon](media/dmc-cluster.gif "Cluster wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="062e6-104">El Asistente para clúster ayuda a crear un modelo que detecta las filas que comparten características similares y las agrupa para maximizar la distancia entre los grupos.</span><span class="sxs-lookup"><span data-stu-id="062e6-104">The Cluster wizard helps you build a model that detects rows that share similar characteristics and groups them to maximize the distance between groups.</span></span> <span data-ttu-id="062e6-105">Este asistente resulta útil para buscar patrones en todo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="062e6-105">This wizard is useful for finding patterns in all kinds of data.</span></span>  
  
 <span data-ttu-id="062e6-106">El Asistente para clúster utiliza el algoritmo de clústeres de Microsoft y puede personalizarse en gran medida.</span><span class="sxs-lookup"><span data-stu-id="062e6-106">The Cluster wizard uses the Microsoft Clustering algorithm and can be extensively customized.</span></span> <span data-ttu-id="062e6-107">Funciona en los datos de una tabla de Excel, un intervalo de Excel o una consulta de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="062e6-107">It works on existing data from an Excel table, an Excel range, or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] query.</span></span> <span data-ttu-id="062e6-108">La herramienta [detectar categorías](detect-categories-table-analysis-tools-for-excel.md) proporciona una funcionalidad similar, proporcionada en las herramientas de análisis de tabla para Excel.</span><span class="sxs-lookup"><span data-stu-id="062e6-108">Similar functionality is provided by the [Detect Categories](detect-categories-table-analysis-tools-for-excel.md) tool, provided in the Table Analysis Tools for Excel.</span></span> <span data-ttu-id="062e6-109">Sin embargo, la herramienta Detectar categorías no se puede personalizar y debe usar los datos de las tablas de Excel.</span><span class="sxs-lookup"><span data-stu-id="062e6-109">However, the Detect Categories tool cannot be customized and must use data in Excel tables.</span></span>  
  
## <a name="using-the-cluster-wizard"></a><span data-ttu-id="062e6-110">Usar el Asistente para clúster</span><span class="sxs-lookup"><span data-stu-id="062e6-110">Using the Cluster Wizard</span></span>  
  
1.  <span data-ttu-id="062e6-111">En la cinta de opciones minería de datos, haga clic en **clúster**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="062e6-111">In the Data Mining ribbon, click **Cluster**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="062e6-112">En la página **seleccionar datos de origen** , seleccione una tabla o un rango de Excel.</span><span class="sxs-lookup"><span data-stu-id="062e6-112">In the **Select Source Data** page, select an Excel table or range.</span></span> <span data-ttu-id="062e6-113">O bien especifique un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="062e6-113">Or specify and external data source.</span></span>  
  
     <span data-ttu-id="062e6-114">Si utiliza un origen de datos externo, puede crear vistas personalizadas o pegar el texto personalizado de la consulta, y guardar el conjunto de datos como un origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="062e6-114">If you use an external data source, you can create custom views or paste in custom query text, and save the data set as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="062e6-115">En la página **agrupación en clústeres** , puede personalizar la forma en que se compila el modelo.</span><span class="sxs-lookup"><span data-stu-id="062e6-115">On the **Clustering** page, you can customize the way the model is built.</span></span>  
  
    -   <span data-ttu-id="062e6-116">En **número de segmentos**, puede indicar al asistente que cree un número fijo de categorías o dejar que detecte automáticamente el número óptimo de agrupaciones.</span><span class="sxs-lookup"><span data-stu-id="062e6-116">For **Number of segments**, you can tell the wizard to create a fixed number of categories, or let it automatically detect the optimum number of groupings.</span></span>  
  
    -   <span data-ttu-id="062e6-117">Revise la lista de columnas de la lista **columnas de entrada** y anule la selección de las columnas que no sean útiles en la creación de patrones.</span><span class="sxs-lookup"><span data-stu-id="062e6-117">Review the list of columns in the **Input columns** list, and deselect any columns that are not useful in creating patterns.</span></span> <span data-ttu-id="062e6-118">Las columnas que debe excluir son los números de identificación, los nombres de cliente, etcétera.</span><span class="sxs-lookup"><span data-stu-id="062e6-118">Columns you should exclude include ID numbers, customer names, and so on.</span></span>  
  
4.  <span data-ttu-id="062e6-119">Opcionalmente, haga clic en **parámetros** para cambiar los parámetros del algoritmo y personalizar el comportamiento del modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="062e6-119">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="062e6-120">En la página **dividir datos en conjuntos de entrenamiento y de prueba** , especifique la cantidad de datos que se van a conservar para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="062e6-120">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="062e6-121">El resto se utiliza siempre para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="062e6-121">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="062e6-122">La configuración predeterminada es tener un 30 % de datos de prueba y un 70 % de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="062e6-122">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="062e6-123">En la página **Finalizar** , proporcione un nombre descriptivo para el conjunto de datos y el modelo, y establezca las siguientes opciones que controlan cómo se trabaja con el modelo terminado:</span><span class="sxs-lookup"><span data-stu-id="062e6-123">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="062e6-124">**Examinar modelo**.</span><span class="sxs-lookup"><span data-stu-id="062e6-124">**Browse model**.</span></span> <span data-ttu-id="062e6-125">Cuando se selecciona esta opción, en cuanto el asistente finaliza el procesamiento del modelo, se abre una ventana **examinar** para ayudarle a explorar los resultados.</span><span class="sxs-lookup"><span data-stu-id="062e6-125">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="062e6-126">El contenido del visor depende del tipo de modelo que creó.</span><span class="sxs-lookup"><span data-stu-id="062e6-126">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="062e6-127">Para obtener más información, vea [examinar un modelo de agrupación en clústeres](browsing-a-clustering-model.md).</span><span class="sxs-lookup"><span data-stu-id="062e6-127">For more information, see [Browsing a Clustering Model](browsing-a-clustering-model.md).</span></span>  
  
    -   <span data-ttu-id="062e6-128">**Habilitar la obtención de detalles**.</span><span class="sxs-lookup"><span data-stu-id="062e6-128">**Enable drillthrough**.</span></span> <span data-ttu-id="062e6-129">Seleccione esta opción para ver los datos subyacentes desde el modelo terminado.</span><span class="sxs-lookup"><span data-stu-id="062e6-129">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="062e6-130">Esta opción solo está disponible si se crea un modelo de árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="062e6-130">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="062e6-131">**Usar modelo temporal**.</span><span class="sxs-lookup"><span data-stu-id="062e6-131">**Use temporary model**.</span></span> <span data-ttu-id="062e6-132">Si selecciona esta opción, el modelo no se guardará en el servidor.</span><span class="sxs-lookup"><span data-stu-id="062e6-132">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="062e6-133">Se eliminan los modelos temporales al cerrar Excel.</span><span class="sxs-lookup"><span data-stu-id="062e6-133">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-clustering-models"></a><span data-ttu-id="062e6-134">Más información sobre los modelos de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="062e6-134">More about Clustering Models</span></span>  
 <span data-ttu-id="062e6-135">Para cambiar el algoritmo de clústeres usado por este asistente, haga clic en **Opciones avanzadas** y use el cuadro de diálogo **parámetros de algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="062e6-135">You can change the clustering algorithm used by this wizard by clicking **Advanced** and using the **Algorithm Parameters** dialog box.</span></span>  
  
 <span data-ttu-id="062e6-136">El algoritmo de clústeres de Microsoft proporciona estos métodos de clúster:</span><span class="sxs-lookup"><span data-stu-id="062e6-136">The Microsoft Clustering algorithm provides these clustering methods:</span></span>  
  
-   <span data-ttu-id="062e6-137">Mediana-k escalable o sin escala.</span><span class="sxs-lookup"><span data-stu-id="062e6-137">K-means -  scalable or non-scaling.</span></span>  
  
-   <span data-ttu-id="062e6-138">Maximización de la expectativa (EM), escalable o sin escala.</span><span class="sxs-lookup"><span data-stu-id="062e6-138">Expectation Maximization (EM) - scalable or non-scaling.</span></span>  
  
 <span data-ttu-id="062e6-139">También puede utilizar el parámetro CLUSTER_SEED para controlar el valor inicial y asegurarse de que los modelos repetidos con el mismo conjunto de datos tienen los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="062e6-139">You can also use the CLUSTER_SEED parameter to control the starting value and ensure that repeated models using the same data set have the same results.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="062e6-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="062e6-140">Requirements</span></span>  
 <span data-ttu-id="062e6-141">Para usar el Asistente para clúster, debe estar conectado a una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="062e6-141">To use the Cluster wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="062e6-142">Para obtener más información, vea [conectarse a los datos de origen &#40;cliente de minería de datos para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="062e6-142">For more information, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062e6-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="062e6-143">See Also</span></span>  
 <span data-ttu-id="062e6-144">[Crear un modelo de minería de datos](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="062e6-144">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="062e6-145">Detectar categorías &#40;herramientas de análisis de tabla para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="062e6-145">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
  
