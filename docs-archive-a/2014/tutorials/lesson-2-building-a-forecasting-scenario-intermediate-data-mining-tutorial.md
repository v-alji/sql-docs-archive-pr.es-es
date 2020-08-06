---
title: 'Lección 2: generar un escenario de previsión (tutorial intermedio de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c81d5846df0a37c2b4182cb92fea86ce6f3417a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662439"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="475ce-102">Lección 2: generar un escenario de pronóstico (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="475ce-102">Lesson 2: Building a Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="475ce-103">Como analista de ventas de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], se le ha solicitado un pronóstico de las ventas de productos para el próximo año.</span><span class="sxs-lookup"><span data-stu-id="475ce-103">As the sales analyst for [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you have been asked to forecast the sales of products for the next year.</span></span> <span data-ttu-id="475ce-104">En concreto, se le ha solicitado que compare las previsiones de las distintas regiones y líneas de productos.</span><span class="sxs-lookup"><span data-stu-id="475ce-104">In particular, you have been asked to compare forecasts for the different regions and product lines.</span></span> <span data-ttu-id="475ce-105">Además, debe determinar si las ventas de diferentes productos varían en función de la época del año.</span><span class="sxs-lookup"><span data-stu-id="475ce-105">Additionally, you have been asked to determine whether sales of different products vary depending on the time of the year.</span></span>  
  
 <span data-ttu-id="475ce-106">Para hallar la información solicitada, en esta lección resumirá los datos de ventas mensuales de la compañía y también resumirá las cifras de ventas en tres regiones: Europa, Norteamérica y Pacífico.</span><span class="sxs-lookup"><span data-stu-id="475ce-106">To find the requested information, in this lesson you will summarize the company's sales data at the monthly level, and you will also summarize sales figures by three regions: Europe, North America, and the Pacific.</span></span>  
  
 <span data-ttu-id="475ce-107">Una vez que haya completado las tareas de esta lección, podrá responder a las preguntas siguientes:</span><span class="sxs-lookup"><span data-stu-id="475ce-107">After you complete the tasks in this lesson, you will be able to answer the following questions:</span></span>  
  
-   <span data-ttu-id="475ce-108">¿Cómo cambian las ventas de los diferentes modelos de bicicleta a lo largo del año?</span><span class="sxs-lookup"><span data-stu-id="475ce-108">How do the sales of different bike models change over time?</span></span>  
  
-   <span data-ttu-id="475ce-109">¿Hay diferencias entre los patrones de ventas en las tres regiones?</span><span class="sxs-lookup"><span data-stu-id="475ce-109">Are there differences between the patterns for sales in the three regions?</span></span>  
  
-   <span data-ttu-id="475ce-110">¿Podemos predecir picos de ventas?</span><span class="sxs-lookup"><span data-stu-id="475ce-110">Can we forecast sales peaks?</span></span>  
  
 <span data-ttu-id="475ce-111">La lección se puede completar en dos partes:</span><span class="sxs-lookup"><span data-stu-id="475ce-111">The lesson can be completed in two parts:</span></span>  
  
-   <span data-ttu-id="475ce-112">La primera parte presenta los conceptos básicos de cómo crear y usar un modelo de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="475ce-112">Part One introduces the basics of how to create and use a time series model.</span></span>  
  
-   <span data-ttu-id="475ce-113">La segunda parte le guía por la creación de un modelo general de series temporales basándose en todas las regiones.</span><span class="sxs-lookup"><span data-stu-id="475ce-113">Part Two walks you through creation of a general time series model, based on all regions.</span></span> <span data-ttu-id="475ce-114">Puede usar este modelo general para la *predicción cruzada*.</span><span class="sxs-lookup"><span data-stu-id="475ce-114">You can use this general model for *cross-prediction*.</span></span>  
  
 <span data-ttu-id="475ce-115">Para completar las tareas de esta lección, que se enumeran a continuación, usará el [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origen de datos creado en la [Lección 1: crear la solución intermedia de minería de datos &#40;tutorial intermedio de minería de datos&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="475ce-115">To complete the tasks in this lesson, which are listed below, you will use the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source that you created in [Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="475ce-116">Las fechas de la base de datos de ejemplo de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] se han actualizado para esta versión.</span><span class="sxs-lookup"><span data-stu-id="475ce-116">The dates in the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sample database have been updated for this release.</span></span> <span data-ttu-id="475ce-117">Si usa una versión anterior de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], puede crear el modelo según estos pasos, pero podría ver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="475ce-117">If you use an earlier version of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you can build the model following these steps, but you might see different results.</span></span>  
  
 <span data-ttu-id="475ce-118">**Crear un modelo de pronóstico simple**</span><span class="sxs-lookup"><span data-stu-id="475ce-118">**Creating a Simple Forecasting Model**</span></span>  
  
-   [<span data-ttu-id="475ce-119">Agregar una vista del origen de datos para la previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-119">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-120">Crear una estructura de pronóstico y un modelo &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-120">Creating a Forecasting Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-121">Modificar la estructura de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-121">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-122">Personalizar y procesar el modelo de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-122">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-123">Explorar el modelo de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-123">Exploring the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-124">Crear predicciones de serie temporal &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-124">Creating Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="475ce-125">**Crear un modelo de pronóstico general para predicciones cruzadas**</span><span class="sxs-lookup"><span data-stu-id="475ce-125">**Creating a General Forecasting Model for Cross-Prediction**</span></span>  
  
-   [<span data-ttu-id="475ce-126">Predicciones de serie temporal avanzadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-126">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-127">Predicciones de serie temporal que usan datos actualizados &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-127">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="475ce-128">Predicciones de serie temporal que usan datos de reemplazo &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-128">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="475ce-129">Comparar las predicciones de modelos de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-129">Comparing Predictions for Forecasting Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="475ce-130">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="475ce-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="475ce-131">Agregar una vista del origen de datos para la previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-131">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="475ce-132">Descripción de los requisitos de un modelo de serie temporal &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-132">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="475ce-133">Todas las lecciones</span><span class="sxs-lookup"><span data-stu-id="475ce-133">All Lessons</span></span>  
 [<span data-ttu-id="475ce-134">Lección 1: crear la solución intermedia de minería de datos &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-134">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="475ce-135">Lección 2: Escenario de pronóstico (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="475ce-135">Lesson 2: Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="475ce-136">Lección 3: Generar un escenario de cesta de la compra &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-136">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="475ce-137">Lección 4: generar un escenario de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-137">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="475ce-138">Lección 5: Generar modelos de red neuronal y de regresión logística &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="475ce-138">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="475ce-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="475ce-139">See Also</span></span>  
 <span data-ttu-id="475ce-140">[Tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="475ce-140">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="475ce-141">[Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="475ce-141">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="475ce-142">Algoritmo de serie temporal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="475ce-142">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
