---
title: 'Lección 3: generar un escenario de cesta de la compra (tutorial intermedio de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a281aa62fbf08393c95f12ded9886ac212b3165f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747773"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="13f03-102">Lección 3: Generar un escenario de cesta de la compra (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="13f03-102">Lesson 3: Building a Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="13f03-103">El departamento de marketing de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] desea mejorar el sitio web de la empresa para promover las ventas cruzadas.</span><span class="sxs-lookup"><span data-stu-id="13f03-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to improve the company Web site to promote cross-selling.</span></span> <span data-ttu-id="13f03-104">Como parte de la actualización del sitio, desean contar con la capacidad de predecir los productos cuya adquisición podría interesar a los clientes, basándose en otros productos que ya se encuentran en sus cestas de la compra en línea.</span><span class="sxs-lookup"><span data-stu-id="13f03-104">As part of the site update, they would like the ability to predict products that a customer might want to purchase, based on the other products that are already in the customer's online shopping basket.</span></span> <span data-ttu-id="13f03-105">El departamento de marketing también desea comprender mejor el comportamiento de compra de los clientes, de forma que puedan diseñar el sitio web para que los elementos que tienden a comprarse juntos aparezcan agrupados.</span><span class="sxs-lookup"><span data-stu-id="13f03-105">The marketing department also wants to understand customer purchasing behavior better, so that they can design the Web site so that the items that tend to be purchased together appear together.</span></span> <span data-ttu-id="13f03-106">Han aprendido que la minería de datos resulta especialmente útil para este tipo de *análisis de la cesta de la compra* y le han solicitado el desarrollo de un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="13f03-106">They have learned that data mining is especially useful for this kind of *market basket analysis* and have asked you to develop a data mining model.</span></span>  
  
 <span data-ttu-id="13f03-107">Después de completar las tareas de esta lección, tendrá un modelo de minería de datos que muestra los grupos de elementos de las transacciones históricas del cliente.</span><span class="sxs-lookup"><span data-stu-id="13f03-107">After you complete the tasks in this lesson, you will have a mining model that shows groups of items from historical customer transactions.</span></span> <span data-ttu-id="13f03-108">Además, puede utilizar el modelo de minería de datos para predecir elementos adicionales que un cliente puede desear comprar.</span><span class="sxs-lookup"><span data-stu-id="13f03-108">Additionally, you can use the mining model to predict additional items that a customer may want to purchase.</span></span>  
  
 <span data-ttu-id="13f03-109">Para completar las tareas de esta lección, usará la solución y el origen de datos que creó en la primera lección del [tutorial intermedio de minería de datos &#40;Analysis Services-data mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="13f03-109">To complete the tasks in this lesson, you will use the solution and data source that you created in the first lesson of the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="13f03-110">Modificará esta solución agregando una vista del origen de datos que contiene tablas sobre el cliente, incluso una tabla anidada de sus compras.</span><span class="sxs-lookup"><span data-stu-id="13f03-110">You will modify this solution by adding a data source view that contains tables about the customer, including a nested table of customer purchases.</span></span>  <span data-ttu-id="13f03-111">A continuación, generará un modelo de minería de datos que utiliza el algoritmo de reglas de asociación de Microsoft, que es adecuado en escenarios de cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="13f03-111">You will then build a mining model that uses the Microsoft Association Rules algorithm, which is suited to market basket scenarios.</span></span>  
  
 <span data-ttu-id="13f03-112">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="13f03-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="13f03-113">Agregar una vista del origen de datos con tablas anidadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-113">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="13f03-114">Crear una estructura de cesta de la compra y un modelo &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-114">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="13f03-115">Modificar y procesar el modelo de cesta de la compra &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-115">Modifying and Processing the Market Basket Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="13f03-116">Explorar los modelos de cesta de la compra &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-116">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="13f03-117">Filtrar una tabla anidada en un modelo de minería de datos &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-117">Filtering a Nested Table in a Mining Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="13f03-118">Predicción de asociaciones &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-118">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="13f03-119">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="13f03-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="13f03-120">Agregar una vista del origen de datos con tablas anidadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-120">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="13f03-121">Todas las lecciones</span><span class="sxs-lookup"><span data-stu-id="13f03-121">All Lessons</span></span>  
 [<span data-ttu-id="13f03-122">Lección 1: crear la solución intermedia de minería de datos &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-122">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="13f03-123">Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-123">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="13f03-124">Lección 3: Escenario de cesta de la compra (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="13f03-124">Lesson 3: Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="13f03-125">Lección 4: generar un escenario de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-125">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="13f03-126">Lección 5: Generar modelos de red neuronal y de regresión logística &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-126">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="13f03-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13f03-127">See Also</span></span>  
 <span data-ttu-id="13f03-128">[Tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="13f03-128">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="13f03-129">[Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="13f03-129">[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="13f03-130">Lección 4: generar un escenario de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="13f03-130">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
