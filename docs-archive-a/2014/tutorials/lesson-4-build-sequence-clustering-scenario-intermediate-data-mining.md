---
title: 'Lección 4: generar un escenario de agrupación en clústeres de secuencia (tutorial intermedio de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- sequence clustering algorithms [Analysis Services]
- tutorials [Data Mining]
ms.assetid: 63436bbd-0f73-4012-b6f1-358c81e4d92a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0f417c685d8af898de7c66ffe82045fa76b582e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743707"
---
# <a name="lesson-4-building-a-sequence-clustering-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="c3881-102">Lección 4: Generar un escenario de agrupación en clústeres de secuencia (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="c3881-102">Lesson 4: Building a Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="c3881-103">El departamento de marketing de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] desea saber cómo se mueven los clientes por el sitio web de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3881-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to understand how customers move through the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Web site.</span></span> <span data-ttu-id="c3881-104">La empresa cree que existe un patrón según el cual los clientes incluyen productos en las cestas de la compra.</span><span class="sxs-lookup"><span data-stu-id="c3881-104">The company suspects that there is a pattern to the order in which customers put products into their shopping baskets.</span></span> <span data-ttu-id="c3881-105">Desean analizar el orden de secuencias de compra para obtener información sobre el modo en que los clientes agregan los elementos relacionados a la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="c3881-105">They want to analyze the order of purchase sequences to learn how customers add related items to their baskets.</span></span> <span data-ttu-id="c3881-106">Posteriormente, esta información se puede utilizar para mejorar el flujo del sitio web y propiciar que los clientes adquieran productos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c3881-106">They can then use this information to streamline the flow of the Web site so that it leads customers to purchase additional products.</span></span>  
  
 <span data-ttu-id="c3881-107">Después de completar las tareas de esta lección, habrá creado un modelo de minería de datos que use el algoritmo de clústeres de secuencia de [!INCLUDE[msCoName](../includes/msconame-md.md)] para predecir cuál será el siguiente artículo que los clientes incluirán en la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="c3881-107">After you complete the tasks in this lesson, you will have created a mining model that uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm to predict the next item that customers will put into their shopping baskets.</span></span> <span data-ttu-id="c3881-108">Experimentará con dos versiones del modelo: una que analiza solo el orden de productos en la cesta y otra que contiene datos demográficos adicionales del cliente para la agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="c3881-108">You will experiment with two versions of the model: one that analyzes only the order of products in the basket, and one that contains some additional customer demographics for clustering.</span></span> <span data-ttu-id="c3881-109">Finalmente, utilizará los modelos para crear predicciones que puede utilizar para recomendar productos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="c3881-109">Finally, you will use the models to create predictions that you can use to recommend products to customers.</span></span>  
  
 <span data-ttu-id="c3881-110">Para completar las tareas de la lección, utilizará la estructura de minería de datos Market Basket que creó en la [Lección 3: generar un escenario de cesta de la compra &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c3881-110">To complete the tasks in the lesson, you will use the market basket mining structure that you created in [Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="c3881-111">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c3881-111">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="c3881-112">Crear una estructura de modelos de minería de datos de clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-112">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="c3881-113">Procesar el modelo de agrupación en clústeres de secuencia</span><span class="sxs-lookup"><span data-stu-id="c3881-113">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
-   [<span data-ttu-id="c3881-114">Explorar el modelo de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-114">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c3881-115">Crear un modelo de agrupación en clústeres de secuencia relacionado &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-115">Creating a Related Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="c3881-116">Crear predicciones en un modelo de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-116">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c3881-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="c3881-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c3881-118">Crear una estructura de modelos de minería de datos de clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-118">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="c3881-119">Todas las lecciones</span><span class="sxs-lookup"><span data-stu-id="c3881-119">All Lessons</span></span>  
 [<span data-ttu-id="c3881-120">Lección 1: crear la solución intermedia de minería de datos &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-120">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="c3881-121">Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-121">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="c3881-122">Lección 3: Generar un escenario de cesta de la compra &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-122">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="c3881-123">Lección 4: Escenario de agrupación en clústeres de secuencia (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="c3881-123">Lesson 4: Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="c3881-124">Lección 5: Generar modelos de red neuronal y de regresión logística &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c3881-124">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3881-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3881-125">See Also</span></span>  
 <span data-ttu-id="c3881-126">[Tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="c3881-126">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="c3881-127">Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c3881-127">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
