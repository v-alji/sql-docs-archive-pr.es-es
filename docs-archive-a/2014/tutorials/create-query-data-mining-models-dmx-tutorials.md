---
title: 'Crear y consultar modelos de minería de datos con DMX: Tutoriales (Analysis Services-minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 145b81a7-c0c3-4ca3-bb32-0b482423b9a0
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 22ed01105a32f460bcbeb2c067299fdf62af2eed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661727"
---
# <a name="creating-and-querying-data-mining-models-with-dmx-tutorials-analysis-services---data-mining"></a><span data-ttu-id="c85f9-102">Crear y consultar modelos de minería de datos con DMX: tutoriales (Analysis Services - minería de datos)</span><span class="sxs-lookup"><span data-stu-id="c85f9-102">Creating and Querying Data Mining Models with DMX: Tutorials (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="c85f9-103">Después de crear una solución de minería de datos mediante [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puede crear consultas en los modelos de minería de datos para predecir tendencias, recuperar patrones en los datos y medir la precisión de los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="c85f9-103">After you have created a data mining solution by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you can create queries against the data mining models to predict trends, retrieve patterns in the data, and measure the accuracy of the mining models.</span></span>  
  
 <span data-ttu-id="c85f9-104">Los tutoriales paso a paso de la lista siguiente le ayudarán a obtener información sobre cómo compilar y ejecutar consultas de minería de datos mediante [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , de modo que pueda sacar el máximo partido de los datos.</span><span class="sxs-lookup"><span data-stu-id="c85f9-104">The step-by-step tutorials in the following list will help you learn how to build and run data mining queries by using [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] so that you can get the most from your data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c85f9-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c85f9-105">In This Section</span></span>  
  
-   [<span data-ttu-id="c85f9-106">Tutorial DMX de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="c85f9-106">Bike Buyer DMX Tutorial</span></span>](../../2014/tutorials/bike-buyer-dmx-tutorial.md)  
  
     <span data-ttu-id="c85f9-107">Este tutorial le guía por la creación de una nueva estructura de minería de datos y nuevos modelos de minería datos usando el lenguaje DMX (Extensiones de minería de datos) y explica cómo crear consultas de predicción DMX.</span><span class="sxs-lookup"><span data-stu-id="c85f9-107">This tutorial walks you through the creation of a new mining structure and mining models by using the Data Mining Extensions (DMX) language, and explains how to create DMX prediction queries.</span></span>  
  
-   [<span data-ttu-id="c85f9-108">Tutorial DMX de Market Basket</span><span class="sxs-lookup"><span data-stu-id="c85f9-108">Market Basket DMX Tutorial</span></span>](../../2014/tutorials/market-basket-dmx-tutorial.md)  
  
     <span data-ttu-id="c85f9-109">Este tutorial usa un escenario típico de cesta de compras, en el que se buscan asociaciones entre los productos que los clientes adquieren juntos.</span><span class="sxs-lookup"><span data-stu-id="c85f9-109">This tutorial uses a typical market basket scenario, where you find associations between the products that customers purchase together.</span></span> <span data-ttu-id="c85f9-110">En este tutorial también se muestra cómo usar las tablas anidadas al crear una estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="c85f9-110">This tutorial also demonstrates how to use nested tables when you create a mining structure.</span></span> <span data-ttu-id="c85f9-111">Generará y entrenará un modelo basado en esta estructura y, a continuación, creará predicciones mediante DMX.</span><span class="sxs-lookup"><span data-stu-id="c85f9-111">You build and train a model based on this structure, and then create predictions using DMX.</span></span>  
  
-   [<span data-ttu-id="c85f9-112">Tutorial DMX de predicción de series temporales</span><span class="sxs-lookup"><span data-stu-id="c85f9-112">Time Series Prediction DMX Tutorial</span></span>](../../2014/tutorials/time-series-prediction-dmx-tutorial.md)  
  
     <span data-ttu-id="c85f9-113">Este tutorial crea un modelo de pronóstico para mostrar el uso de la instrucción CREATE MODEL (DMX).</span><span class="sxs-lookup"><span data-stu-id="c85f9-113">This tutorial creates a forecasting model to illustrate the use of the CREATE MODEL (DMX) statement.</span></span> <span data-ttu-id="c85f9-114">A continuación, agregará modelos relacionados y personalizará el comportamiento de cada uno de ellos cambiando los parámetros del algoritmo de serie temporal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c85f9-114">You then add related models and customize the behavior of each by changing the parameters of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="c85f9-115">Por último, creará predicciones y las actualizará con nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="c85f9-115">Finally you create predictions and update the predictions with new data.</span></span> <span data-ttu-id="c85f9-116">La capacidad de actualizar una serie temporal al realizar predicciones se agregó en [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c85f9-116">The ability to update a time series while making predictions was added in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c85f9-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="c85f9-117">Reference</span></span>  
 [<span data-ttu-id="c85f9-118">Algoritmos de minería de datos &#40;Analysis Services: Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c85f9-118">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="c85f9-119">Referencia de Extensiones de minería de datos &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="c85f9-119">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
## <a name="related-sections"></a><span data-ttu-id="c85f9-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c85f9-120">Related Sections</span></span>  
  
-   [<span data-ttu-id="c85f9-121">Tutorial básico de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c85f9-121">Basic Data Mining Tutorial</span></span>](../../2014/tutorials/basic-data-mining-tutorial.md)  
  
     <span data-ttu-id="c85f9-122">En este tutorial se presentan conceptos básicos, como por ejemplo, cómo crear un proyecto y cómo generar estructuras y modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="c85f9-122">This tutorial introduces basic concepts, such as how to create a project and how to build mining structures and mining models.</span></span>  
  
-   [<span data-ttu-id="c85f9-123">Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c85f9-123">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
     <span data-ttu-id="c85f9-124">Este tutorial contiene varias lecciones independientes y en cada una de ellas se presenta un tipo de modelo diferente.</span><span class="sxs-lookup"><span data-stu-id="c85f9-124">This tutorial contains a number of independent lessons, each introducing you to a different model type.</span></span> <span data-ttu-id="c85f9-125">Cada lección le guía por el proceso de creación de un modelo, exploración y personalización del modelo y creación de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="c85f9-125">Each lesson walks you through the process of creating a model, exploring the model, and then customizing the model and creating prediction queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85f9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c85f9-126">See Also</span></span>  
 <span data-ttu-id="c85f9-127">[Soluciones de minería de datos](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="c85f9-127">[Data Mining Solutions](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span></span>  
 <span data-ttu-id="c85f9-128">[Herramientas de minería de datos](../../2014/analysis-services/data-mining/data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c85f9-128">[Data Mining Tools](../../2014/analysis-services/data-mining/data-mining-tools.md) </span></span>  
 [<span data-ttu-id="c85f9-129">Proyectos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c85f9-129">Data Mining Projects</span></span>](../../2014/analysis-services/data-mining/data-mining-projects.md)  
  
  
