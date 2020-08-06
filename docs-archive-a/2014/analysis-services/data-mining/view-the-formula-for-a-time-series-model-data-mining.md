---
title: Ver la fórmula de un modelo de serie temporal (minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- ARTXP
- time series algorithms [Analysis Services]
- ARIMA
- time series [Analysis Services]
- Time Series Viewer [Analysis Services]
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
author: minewiskan
ms.author: owend
ms.openlocfilehash: eff61c469d34f084e6a0eb11c49a1c37c7cc97c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662340"
---
# <a name="view-the-formula-for-a-time-series-model-data-mining"></a><span data-ttu-id="4bd14-102">Ver la fórmula de un modelo de serie temporal (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="4bd14-102">View the Formula for a Time Series Model (Data Mining)</span></span>
  <span data-ttu-id="4bd14-103">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] Diseñador de minería de datos del visor de series temporales proporciona la forma más sencilla de ver los detalles de la ecuación de regresión utilizada en un modelo de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="4bd14-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series viewer inData Mining Designer provides the easiest way to view the details of the regression equation used in a time series model.</span></span>  
  
 <span data-ttu-id="4bd14-104">Puede extraer la fórmula de regresión para un modelo de serie temporal consultando el contenido del modelo.</span><span class="sxs-lookup"><span data-stu-id="4bd14-104">You can extract the regression formula for a time series model by querying the model content.</span></span> <span data-ttu-id="4bd14-105">Sin embargo, para ver la fórmula completa de ARTXP o ARIMA, se recomienda usar la **leyenda de minería de datos** del [visor de series temporales de Microsoft](browse-a-model-using-the-microsoft-time-series-viewer.md), que presenta todas las constantes en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="4bd14-105">However, to view the complete ARTXP or ARIMA formula, we recommend that you use the **Mining Legend** of the [Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md), which presents all the constants in a readable format.</span></span>  
  
 <span data-ttu-id="4bd14-106">Si se crea un modelo mixto, los análisis ARIMA y ARTXP se crean en árboles independientes, unidos en el nodo raíz que representa el modelo.</span><span class="sxs-lookup"><span data-stu-id="4bd14-106">If you create a mixed model, the ARIMA and ARTXP analyses are created in separate trees, joined at the root node representing the model.</span></span> <span data-ttu-id="4bd14-107">Las estructuras de los árboles ARIMA y ARTXP son muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="4bd14-107">The structures of the ARIMA and ARTXP trees are very different.</span></span> <span data-ttu-id="4bd14-108">Por ejemplo, el árbol ARTXP es una estructura de árbol, como un árbol de decisión, mientras que el árbol ARIMA representa una serie de medias móviles.</span><span class="sxs-lookup"><span data-stu-id="4bd14-108">For example, the ARTXP tree is in fact a tree structure, like a decision tree, whereas the ARIMA tree represents a series of moving averages.</span></span> <span data-ttu-id="4bd14-109">Por lo tanto, aunque las dos representaciones se presentan en un modelo por comodidad, se deben tratar como dos modelos independientes.</span><span class="sxs-lookup"><span data-stu-id="4bd14-109">Therefore, although the two representations are presented in one model for convenience, they should be treated as two independent models.</span></span> <span data-ttu-id="4bd14-110">Las ecuaciones son también completamente diferentes y no se pueden combinar ni comparar.</span><span class="sxs-lookup"><span data-stu-id="4bd14-110">The equations are also completely different and cannot be combined or compared.</span></span>  
  
 <span data-ttu-id="4bd14-111">También puede ver los modelos de serie temporal mediante el [visor de árbol de contenido genérico de Microsoft](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4bd14-111">You can also view time series models by using the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="4bd14-112">Para obtener más información sobre el contenido de un modelo de serie temporal, vea [contenido del modelo de minería de datos para los modelos de serie temporal &#40;Analysis Services-&#41;de minería de datos ](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4bd14-112">For more information about the content of a time series model, see [Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-view-the-artxp-regression-formula-for-a-time-series-model"></a><span data-ttu-id="4bd14-113">Para ver la fórmula de regresión de ARTXP para un modelo de serie temporal</span><span class="sxs-lookup"><span data-stu-id="4bd14-113">To view the ARTXP regression formula for a time series model</span></span>  
  
1.  <span data-ttu-id="4bd14-114">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione el modelo de serie temporal que desea ver y haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="4bd14-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="4bd14-115">-- o --</span><span class="sxs-lookup"><span data-stu-id="4bd14-115">-- or --</span></span>  
  
     <span data-ttu-id="4bd14-116">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], seleccione el modelo de serie temporal y, a continuación, haga clic en la pestaña **Visor de modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="4bd14-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="4bd14-117">Haga clic en la pestaña **Model** (Modelo).</span><span class="sxs-lookup"><span data-stu-id="4bd14-117">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="4bd14-118">Si el modelo contiene varios árboles, seleccione uno en la lista desplegable **Árbol** .</span><span class="sxs-lookup"><span data-stu-id="4bd14-118">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4bd14-119">Un modelo siempre tendrá varios árboles si tiene más de una serie de datos.</span><span class="sxs-lookup"><span data-stu-id="4bd14-119">A model will always have multiple trees if you have more than one data series.</span></span> <span data-ttu-id="4bd14-120">Sin embargo, no verá tantos árboles en el **Visor de series temporales** como en el [Visor de árbol de contenido genérico de Microsoft](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4bd14-120">However, you will not see as many trees in the **Time Series viewer** as you will see in the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="4bd14-121">Esto se debe a que el Visor de series temporales combina la información de ARIMA y ARTXP para cada serie de datos en una única representación.</span><span class="sxs-lookup"><span data-stu-id="4bd14-121">That is because the Time Series viewer combines the ARIMA and ARTXP information for each data series into a single representation.</span></span>  
  
4.  <span data-ttu-id="4bd14-122">Haga clic en cualquier nodo hoja en el árbol.</span><span class="sxs-lookup"><span data-stu-id="4bd14-122">Click any leaf node in the tree.</span></span>  
  
     <span data-ttu-id="4bd14-123">Los nodos con la etiqueta **Serie de datos** siempre son nodos hoja y contienen una ecuación.</span><span class="sxs-lookup"><span data-stu-id="4bd14-123">Nodes that are labeled as **Data Series** are always leaf nodes and can contain an equation.</span></span> <span data-ttu-id="4bd14-124">Si un nodo **(Todos)** no tiene ningún nodo secundario, también puede contener una ecuación.</span><span class="sxs-lookup"><span data-stu-id="4bd14-124">If an **(All)** node has no child nodes, it can also contain an equation.</span></span>  
  
5.  <span data-ttu-id="4bd14-125">Si la **Leyenda de minería de datos** no está disponible, haga clic con el botón derecho en el nodo y seleccione **Mostrar leyenda**.</span><span class="sxs-lookup"><span data-stu-id="4bd14-125">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
     <span data-ttu-id="4bd14-126">La fórmula de ARTXP se muestra en la primera la mitad de la **Leyenda de minería de datos**, como la **Ecuación de nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="4bd14-126">The ARTXP formula is displayed in the first half of the **Mining Legend**, as the **Tree node equation**.</span></span>  
  
### <a name="to-view-the-arima-formula-for-a-time-series-model"></a><span data-ttu-id="4bd14-127">Para ver la fórmula de ARIMA para un modelo de serie temporal</span><span class="sxs-lookup"><span data-stu-id="4bd14-127">To view the ARIMA formula for a time series model</span></span>  
  
1.  <span data-ttu-id="4bd14-128">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione el modelo de serie temporal que desea ver y haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="4bd14-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="4bd14-129">-- o --</span><span class="sxs-lookup"><span data-stu-id="4bd14-129">-- or --</span></span>  
  
     <span data-ttu-id="4bd14-130">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], seleccione el modelo de serie temporal y, a continuación, haga clic en la pestaña **Visor de modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="4bd14-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="4bd14-131">Haga clic en la pestaña **Model** (Modelo).</span><span class="sxs-lookup"><span data-stu-id="4bd14-131">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="4bd14-132">Si el modelo contiene varios árboles, seleccione uno en la lista desplegable **Árbol** .</span><span class="sxs-lookup"><span data-stu-id="4bd14-132">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4bd14-133">El modelo siempre tendrá varios árboles si incluye más de una serie de datos.</span><span class="sxs-lookup"><span data-stu-id="4bd14-133">The model will always have multiple trees if you include more than one data series.</span></span>  
  
4.  <span data-ttu-id="4bd14-134">Haga clic en cualquier nodo en el árbol.</span><span class="sxs-lookup"><span data-stu-id="4bd14-134">Click any node in the tree.</span></span>  
  
     <span data-ttu-id="4bd14-135">La fórmula de ARIMA se muestra en la segunda la mitad de la **Leyenda de minería de datos**, como la **Ecuación ARIMA**.</span><span class="sxs-lookup"><span data-stu-id="4bd14-135">The ARIMA formula is displayed in the second half of the **Mining Legend**, as the **ARIMA equation**.</span></span>  
  
5.  <span data-ttu-id="4bd14-136">Si la **Leyenda de minería de datos** no está disponible, haga clic con el botón derecho en el nodo y seleccione **Mostrar leyenda**.</span><span class="sxs-lookup"><span data-stu-id="4bd14-136">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd14-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bd14-137">See Also</span></span>  
 <span data-ttu-id="4bd14-138">[Tareas y procedimientos del visor de modelos de minería de datos](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="4bd14-138">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="4bd14-139">[Examinar un modelo mediante el visor de series temporales de Microsoft](browse-a-model-using-the-microsoft-time-series-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4bd14-139">[Browse a Model Using the Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span></span>  
 [<span data-ttu-id="4bd14-140">Ejemplos de consultas de modelos de serie temporal</span><span class="sxs-lookup"><span data-stu-id="4bd14-140">Time Series Model Query Examples</span></span>](time-series-model-query-examples.md)  
  
  
