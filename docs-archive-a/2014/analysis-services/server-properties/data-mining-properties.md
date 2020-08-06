---
title: Propiedades de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ClusterCount property
- AllowedProvidersInOpenRowset property
- MinimumSeriesValue property
- ScoreMethod property
- MinimumImportance property
- ModellingCardinality property
- BrentTolerance property
- ComplexityPenalty property
- MaximumItemsetCount property
- MinimumSupport property
- AllowSessionMiningModels property
- HoldoutPercentage property
- ClusterCountPrior property
- MaximumSequenceStates property
- OptimizedPredictionCount property
- data mining [Analysis Services], properties
- MaximumStates property
- MaximumContinuousInputAttributes property
- MaximumOutputAttributes property
- AllowAdHocOpenRowsetQueries property
- Enabled property
- HistoricModelGap property
- SampleSize property
- MaximumInputAttributes property
- PeriodicityHint property
- MissingValueSubstitution property
- SplitMethod property
- ForceRegressor property
- MaximumBucketsForContinuousSplit property
- MaxConcurrentPredictionQueries property
- MinimumItemsetSize property
- AcyclicGraph property
- HoldoutMethod property
- StoppingTolerance property
- properties [data mining]
- AutoDetectPeriodicity property
- HoldoutTolerance property
- MinimumLeafCases property
- HoldoutSeed property
- MinimumClusterCases property
- ClusterCountDeviation property
- MinimumDependencyProbability property
- ClusteringMethod property
- MaximumItemsetSize property
- HiddenNodeRatio property
- MaximumSeriesValue property
ms.assetid: 9bc9abed-180a-4bd8-b2eb-89c62fa88110
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ed1c47faafeb0c680e6afb6f8e509c426760da2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752406"
---
# <a name="data-mining-properties"></a><span data-ttu-id="377ba-102">Propiedades de minería de datos</span><span class="sxs-lookup"><span data-stu-id="377ba-102">Data Mining Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="377ba-103">admite las propiedades de servidor de minería de datos descritas en las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="377ba-103">supports the data mining server properties listed in the following tables.</span></span> <span data-ttu-id="377ba-104">Para obtener más información sobre las propiedades de servidor adicionales y cómo establecerlas, vea [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="377ba-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="377ba-105">**Se aplica a:** Modo de servidor multidimensional únicamente</span><span class="sxs-lookup"><span data-stu-id="377ba-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="377ba-106">Categoría no específica</span><span class="sxs-lookup"><span data-stu-id="377ba-106">Non-Specific Category</span></span>  
 `AllowSessionMiningModels`  
 <span data-ttu-id="377ba-107">Una propiedad booleana que indica si se pueden crear modelos de minería de datos de sesión.</span><span class="sxs-lookup"><span data-stu-id="377ba-107">A Boolean property that indicates whether session mining models can be created.</span></span>  
  
 <span data-ttu-id="377ba-108">El valor predeterminado para esta propiedad es False, que indica que no se pueden crear modelos de minería de datos de sesión.</span><span class="sxs-lookup"><span data-stu-id="377ba-108">The default value for this property is false, which indicates that session mining models cannot be created.</span></span>  
  
 `AllowAdHocOpenRowsetQueries`  
 <span data-ttu-id="377ba-109">Una propiedad booleana que indica si se permiten consultas ad hoc de conjuntos de filas abiertos.</span><span class="sxs-lookup"><span data-stu-id="377ba-109">A Boolean property that indicates whether adhoc open rowset queries are allowed.</span></span>  
  
 <span data-ttu-id="377ba-110">El valor predeterminado para esta propiedad es False, que indica que las consultas de conjuntos de filas abiertos no están permitidas durante una sesión.</span><span class="sxs-lookup"><span data-stu-id="377ba-110">The default value for this property is false, which indicates that open rowset queries are not allowed during a session.</span></span>  
  
 `AllowedProvidersInOpenRowset`  
 <span data-ttu-id="377ba-111">Una propiedad de cadena que identifica los proveedores que están permitidos en un conjunto de filas abierto; se compone de una lista separada por comas/puntos y coma de ProgID de proveedor, o en caso contrario [All].</span><span class="sxs-lookup"><span data-stu-id="377ba-111">A string property that identifies which providers are allowed in an open rowset, consisting of a comma/semi-colon separated list of provider ProgIDs, or else [All].</span></span>  
  
 `MaxConcurrentPredictionQueries`  
 <span data-ttu-id="377ba-112">Una propiedad de entero de 32 bits con signo que define el máximo de consultas de predicción simultáneas.</span><span class="sxs-lookup"><span data-stu-id="377ba-112">A signed 32-bit integer property that defines the maximum number of concurrent prediction queries.</span></span>  
  
## <a name="algorithms-category"></a><span data-ttu-id="377ba-113">Categoría Algoritmos</span><span class="sxs-lookup"><span data-stu-id="377ba-113">Algorithms Category</span></span>  
 `Microsoft_Association_Rules\ Enabled`  
 <span data-ttu-id="377ba-114">Una propiedad booleana que indica si el algoritmo Microsoft_Association_Rules está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-114">A Boolean property that indicates whether the Microsoft_Association_Rules algorithm is enabled.</span></span>  
  
 `Microsoft_Clustering\ Enabled`  
 <span data-ttu-id="377ba-115">Una propiedad booleana que indica si el algoritmo Microsoft_Clustering está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-115">A Boolean property that indicates whether the Microsoft_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Decision_Trees\ Enabled`  
 <span data-ttu-id="377ba-116">Una propiedad booleana que indica si el algoritmo Microsoft_DecisionTrees está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-116">A Boolean property that indicates whether the Microsoft_DecisionTrees algorithm is enabled.</span></span>  
  
 `Microsoft_Naive_Bayes\ Enabled`  
 <span data-ttu-id="377ba-117">Una propiedad booleana que indica si el algoritmo Microsoft_ Naive_Bayes está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-117">A Boolean property that indicates whether the Microsoft_ Naive_Bayes algorithm is enabled.</span></span>  
  
 `Microsoft_Neural_Network\ Enabled`  
 <span data-ttu-id="377ba-118">Una propiedad booleana que indica si el algoritmo Microsoft_Neural_Network está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-118">A Boolean property that indicates whether the Microsoft_Neural_Network algorithm is enabled.</span></span>  
  
 `Microsoft_Sequence_Clustering\ Enabled`  
 <span data-ttu-id="377ba-119">Una propiedad booleana que indica si el algoritmo Microsoft_Sequence_Clustering está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-119">A Boolean property that indicates whether the Microsoft_Sequence_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Time_Series\ Enabled`  
 <span data-ttu-id="377ba-120">Una propiedad booleana que indica si el algoritmo Microsoft_Time_Series está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-120">A Boolean property that indicates whether the Microsoft_Time_Series algorithm is enabled.</span></span>  
  
 `Microsoft_Linear_Regression\ Enabled`  
 <span data-ttu-id="377ba-121">Una propiedad booleana que indica si el algoritmo Microsoft_Linear_Regression está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-121">A Boolean property that indicates whether the Microsoft_Linear_Regression algorithm is enabled.</span></span>  
  
 `Microsoft_Logistic_Regression\ Enabled`  
 <span data-ttu-id="377ba-122">Una propiedad booleana que indica si el algoritmo Microsoft_Logistic_Regression está habilitado.</span><span class="sxs-lookup"><span data-stu-id="377ba-122">A Boolean property that indicates whether the Microsoft_Logistic_Regression algorithm is enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="377ba-123">Además de las propiedades que definen los servicios de minería de datos disponibles en el servidor, existen propiedades de minería de datos que definen el comportamiento de algoritmos concretos.</span><span class="sxs-lookup"><span data-stu-id="377ba-123">In addition to properties that define the data mining services available on the server, there are data mining properties that define the behavior of specific algorithms.</span></span> <span data-ttu-id="377ba-124">Estas propiedades se configuran al crear un modelo de minería de datos individual, no en el nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="377ba-124">You configure these properties when you create an individual data mining model, not at the server level.</span></span> <span data-ttu-id="377ba-125">Para obtener más información, vea [Algoritmos de minería de datos &#40;Analysis Services: Minería de datos&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="377ba-125">For more information, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377ba-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="377ba-126">See Also</span></span>  
 <span data-ttu-id="377ba-127">[Arquitectura física &#40;Analysis Services:&#41;de minería de datos](../data-mining/physical-architecture-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="377ba-127">[Physical Architecture &#40;Analysis Services - Data Mining&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="377ba-128">[Configurar las propiedades del servidor en Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="377ba-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="377ba-129">Determinar el modo de servidor de una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="377ba-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
