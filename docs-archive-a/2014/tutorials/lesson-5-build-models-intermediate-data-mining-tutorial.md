---
title: 'Lección 5: generar modelos de red neuronal y de regresión logística (tutorial intermedio de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- logistic regression [Analysis Services]
- data mining [Analysis Services], tutorials
- neural networks
- tutorials [Data Mining]
- neural network model [Analysis Services]
ms.assetid: 42c3701a-1fd2-44ff-b7de-377345bbbd6b
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a8c9fcf0380582f15fa2bf30d6fdeb97bb2ab1fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671860"
---
# <a name="lesson-5-building-neural-network-and-logistic-regression-models-intermediate-data-mining-tutorial"></a><span data-ttu-id="89bf9-102">Lección 5: Generar modelos de red neuronal y de regresión logística (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="89bf9-102">Lesson 5: Building Neural Network and Logistic Regression Models (Intermediate Data Mining Tutorial)</span></span>
  
  
 <span data-ttu-id="89bf9-103">El departamento de operaciones de [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] está ocupado en un proyecto para mejorar la satisfacción del cliente con su centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="89bf9-103">The Operations department of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] is engaged in a project to improve customer satisfaction with their call center.</span></span> <span data-ttu-id="89bf9-104">Han contratado a un proveedor para administrar el centro de llamadas y proporcionar métricas sobre la efectividad del centro de llamadas, y le han solicitado el análisis de algunos datos preliminares que proporciona el proveedor.</span><span class="sxs-lookup"><span data-stu-id="89bf9-104">They hired a vendor to manage the call center and to report metrics on call center effectiveness, and have asked you to analyze some preliminary data provided by the vendor.</span></span> <span data-ttu-id="89bf9-105">Ellos desean saber si hay algún resultado interesante.</span><span class="sxs-lookup"><span data-stu-id="89bf9-105">They want to know if there are any interesting findings.</span></span> <span data-ttu-id="89bf9-106">En particular, desean saber si los datos sugieren algún problema con el personal o métodos para mejorar la satisfacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="89bf9-106">In particular, they would like to know if the data suggests any staffing problems with staffing or ways to improve customer satisfaction.</span></span>  
  
 <span data-ttu-id="89bf9-107">El conjunto de datos es pequeño y solo cubre un período de 30 días en el funcionamiento del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="89bf9-107">The data set is small and covers only a 30-day period in the operation of the call center.</span></span> <span data-ttu-id="89bf9-108">Los datos hacen un seguimiento del número de operadores nuevos y experimentados en cada turno, el número de llamadas entrantes, el número de pedidos y de problemas que se deben resolver y el tiempo promedio de espera de un cliente para que alguien responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="89bf9-108">The data tracks the number of new and experienced operators in each shift, the number of incoming calls, the number of orders as well as issues that must be resolved, and the average time a customer waits for someone to respond to a call.</span></span> <span data-ttu-id="89bf9-109">Los datos también incluyen una métrica de calidad de servicio basada en la *tasa de abandono*, que es un indicador de la frustración del cliente.</span><span class="sxs-lookup"><span data-stu-id="89bf9-109">The data also includes a service quality metric based on *abandon rate*, which is an indicator of customer frustration.</span></span>  
  
 <span data-ttu-id="89bf9-110">Puesto que no cuenta con expectativas a priori sobre lo que mostrarán los datos, decide usar un modelo de red neuronal para explorar posibles correlaciones.</span><span class="sxs-lookup"><span data-stu-id="89bf9-110">Because you do not have any prior expectations about what the data will show, you decide to use a neural network model to explore possible correlations.</span></span> <span data-ttu-id="89bf9-111">En la exploración se suelen utilizar modelos de red neuronal que pueden analizar relaciones complejas entre muchas entradas y salidas.</span><span class="sxs-lookup"><span data-stu-id="89bf9-111">Neural network models are often used for exploration because they can analyze complex relationships between many inputs and outputs.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="89bf9-112">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="89bf9-112">What You Will Learn</span></span>  
 <span data-ttu-id="89bf9-113">En esta lección, usará el algoritmo de red neuronal para crear un modelo que tanto usted como el equipo de operaciones puedan utilizar para conocer las tendencias en los datos.</span><span class="sxs-lookup"><span data-stu-id="89bf9-113">In this lesson, you will use the neural network algorithm to build a model that you and the Operations team can use to understand the trends in the data.</span></span> <span data-ttu-id="89bf9-114">Como parte de esta lección, intentará responder las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="89bf9-114">As part of this lesson, you will try to answer the following questions:</span></span>  
  
-   <span data-ttu-id="89bf9-115">¿Qué factores afectan a la satisfacción del cliente?</span><span class="sxs-lookup"><span data-stu-id="89bf9-115">What factors affect customer satisfaction?</span></span>  
  
-   <span data-ttu-id="89bf9-116">¿Qué puede realizar el centro de llamadas para mejorar la calidad de servicio?</span><span class="sxs-lookup"><span data-stu-id="89bf9-116">What can the call center do to improve service quality?</span></span>  
  
 <span data-ttu-id="89bf9-117">A continuación, basándose en los resultados, creará un modelo de regresión logística que puede utilizar para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="89bf9-117">Based on the results, you will then build a logistic regression model that you can use for predictions.</span></span> <span data-ttu-id="89bf9-118">El equipo de operaciones utilizará estas predicciones como ayuda para planear el funcionamiento del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="89bf9-118">The predictions will be used by the Operations team as an aid in planning call center operation.</span></span>  
  
 <span data-ttu-id="89bf9-119">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="89bf9-119">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="89bf9-120">Agregar una vista del origen de datos para los datos del centro de llamadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-120">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="89bf9-121">Crear un modelo y una estructura de red neuronal &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-121">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="89bf9-122">Explorar el modelo de centro de llamadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-122">Exploring the Call Center Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-call-center-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="89bf9-123">Agregar un modelo de regresión logística a la estructura del centro de llamadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-123">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="89bf9-124">Crear predicciones para los modelos del centro de llamadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-124">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="89bf9-125">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="89bf9-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="89bf9-126">Agregar una vista del origen de datos para los datos del centro de llamadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-126">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="89bf9-127">Todas las lecciones</span><span class="sxs-lookup"><span data-stu-id="89bf9-127">All Lessons</span></span>  
 [<span data-ttu-id="89bf9-128">Lección 1: crear la solución intermedia de minería de datos &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-128">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="89bf9-129">Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-129">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="89bf9-130">Lección 3: Generar un escenario de cesta de la compra &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-130">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="89bf9-131">Lección 4: generar un escenario de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89bf9-131">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 <span data-ttu-id="89bf9-132">Lección 5: Modelo de red neuronal y de regresión logística (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="89bf9-132">Lesson 5: Neural Network and Logistic Regression Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89bf9-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89bf9-133">See Also</span></span>  
 <span data-ttu-id="89bf9-134">[Tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="89bf9-134">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="89bf9-135">Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="89bf9-135">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
