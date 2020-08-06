---
title: 'Lección 1: crear la solución de minería de datos intermedia (tutorial intermedio de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: d8e3f89f-091c-434e-8f67-639f073edcdf
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: e1a69c78fee37abef8bb899ecf9a635fa7c7dba1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663237"
---
# <a name="lesson-1-creating-the-intermediate-data-mining-solution-intermediate-data-mining-tutorial"></a><span data-ttu-id="2b9df-102">Lección 1: Crear la solución de minería de datos intermedia (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="2b9df-102">Lesson 1: Creating the Intermediate Data Mining Solution (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="2b9df-103">En el Tutorial básico de minería de datos, creó un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que contiene una solución de minería de datos sencilla basada en la nueva base de datos [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b9df-103">In the Basic Data Mining tutorial, you created an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project that contains a simple data mining solution based on the new [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="2b9df-104">Para este tutorial, creará un proyecto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] independiente utilizando [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b9df-104">For this tutorial, you will create a separate [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project by using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2b9df-105">Creará un nuevo origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que usa [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]y le agregará varias vistas del origen de datos nuevas para admitir los escenarios y tipos de modelo.</span><span class="sxs-lookup"><span data-stu-id="2b9df-105">You will create a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source that uses [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], and add several new data source views to that data source, to support the scenarios and model types.</span></span>  
  
 <span data-ttu-id="2b9df-106">Esta lección consta de la tarea siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b9df-106">This lesson consists of the following task:</span></span>  
  
-   [<span data-ttu-id="2b9df-107">Crear una solución y un origen de datos &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-107">Creating a Solution and Data Source &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-solution-and-data-source-intermediate-data-mining-tutorial.md)  
  
## <a name="next-step"></a><span data-ttu-id="2b9df-108">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="2b9df-108">Next Step</span></span>  
 [<span data-ttu-id="2b9df-109">Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-109">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="2b9df-110">Todas las lecciones</span><span class="sxs-lookup"><span data-stu-id="2b9df-110">All Lessons</span></span>  
 <span data-ttu-id="2b9df-111">Lección 1: Creación de la solución de minería de datos intermedia</span><span class="sxs-lookup"><span data-stu-id="2b9df-111">Lesson 1: Creating the Intermediate Data Mining Solution</span></span>  
  
 [<span data-ttu-id="2b9df-112">Lección 2: generar un escenario de previsión &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-112">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="2b9df-113">Lección 3: Generar un escenario de cesta de la compra &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-113">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="2b9df-114">Lección 4: generar un escenario de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-114">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="2b9df-115">Lección 5: Generar modelos de red neuronal y de regresión logística &#40;Tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-115">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b9df-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b9df-116">See Also</span></span>  
 <span data-ttu-id="2b9df-117">[Tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="2b9df-117">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="2b9df-118">Crear y consultar modelos de minería de datos con DMX: tutoriales &#40;Analysis Services - minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9df-118">Creating and Querying Data Mining Models with DMX: Tutorials &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/create-query-data-mining-models-dmx-tutorials.md)  
  
  
