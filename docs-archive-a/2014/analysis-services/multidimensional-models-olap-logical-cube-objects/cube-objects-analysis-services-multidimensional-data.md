---
title: Objetos de cubo (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e6dfb75be696ab26893e668b99dc36c7340f86c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673936"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="6046c-102">Objetos de cubo (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="6046c-102">Cube Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-cube-objects"></a><span data-ttu-id="6046c-103">Introducción a los objetos de cubo</span><span class="sxs-lookup"><span data-stu-id="6046c-103">Introducing Cube Objects</span></span>  
 <span data-ttu-id="6046c-104">Un objeto <xref:Microsoft.AnalysisServices.Cube> simple se compone de la información básica, dimensiones y grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="6046c-104">A simple <xref:Microsoft.AnalysisServices.Cube> object is composed of: basic information, dimensions, and measure groups.</span></span> <span data-ttu-id="6046c-105">La información básica incluye el nombre del cubo, la medida predeterminada del cubo, el origen de datos, el modo de almacenamiento y otros aspectos.</span><span class="sxs-lookup"><span data-stu-id="6046c-105">Basic information includes the name of the cube, the default measure of the cube, the data source, the storage mode, and others.</span></span>  
  
 <span data-ttu-id="6046c-106">La colección Dimensions contiene el conjunto real de dimensiones que se utilizan en el cubo de la colección de dimensiones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6046c-106">The Dimensions collection contains the actual set of dimensions used in the cube from the database dimensions colection.</span></span> <span data-ttu-id="6046c-107">Todas las dimensiones deben estar definidas en la colección de dimensiones de la base de datos para hacer referencia a ellas en el cubo.</span><span class="sxs-lookup"><span data-stu-id="6046c-107">All dimensions have to be defined in the dimensions collection of the database before being referenced in the cube.</span></span> <span data-ttu-id="6046c-108">Las dimensiones privadas no están disponibles en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6046c-108">Private dimensions are not available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6046c-109">Los grupos de medida son conjuntos de medidas del cubo.</span><span class="sxs-lookup"><span data-stu-id="6046c-109">Measure groups are sets of measures in the cube.</span></span> <span data-ttu-id="6046c-110">Un grupo de medida es una colección de medidas con una vista del origen de datos común y un conjunto común de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="6046c-110">A measure group is a collection of measures that have a common data source view and a common set of dimensions.</span></span> <span data-ttu-id="6046c-111">El grupo de medida es la unidad de proceso de las medidas; los grupos de medida se pueden procesar de forma individual y, a continuación, se pueden examinar.</span><span class="sxs-lookup"><span data-stu-id="6046c-111">A measure group is the unit of process for measures; measure groups can be processed individually and then browsed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6046c-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6046c-112">In this section</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6046c-113">Tema</span><span class="sxs-lookup"><span data-stu-id="6046c-113">Topic</span></span>||  
|[<span data-ttu-id="6046c-114">Acciones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="6046c-114">Actions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="6046c-115">Agregaciones y diseños de agregaciones</span><span class="sxs-lookup"><span data-stu-id="6046c-115">Aggregations and Aggregation Designs</span></span>](aggregations-and-aggregation-designs.md)||  
|[<span data-ttu-id="6046c-116">Cálculos</span><span class="sxs-lookup"><span data-stu-id="6046c-116">Calculations</span></span>](calculations.md)||  
|[<span data-ttu-id="6046c-117">Celdas de cubo &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="6046c-117">Cube Cells &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-cells-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="6046c-118">Propiedades del cubo</span><span class="sxs-lookup"><span data-stu-id="6046c-118">Cube Properties</span></span>](cube-properties-multidimensional-model-programming.md)||  
|[<span data-ttu-id="6046c-119">Almacenamiento de cubos &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="6046c-119">Cube Storage &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-storage-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="6046c-120">Traducciones de cubo</span><span class="sxs-lookup"><span data-stu-id="6046c-120">Cube Translations</span></span>](cube-translations.md)||  
|[<span data-ttu-id="6046c-121">Relaciones de dimensión</span><span class="sxs-lookup"><span data-stu-id="6046c-121">Dimension Relationships</span></span>](dimension-relationships.md)||  
|[<span data-ttu-id="6046c-122">Indicadores clave de rendimiento &#40;KPI&#41; en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="6046c-122">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[<span data-ttu-id="6046c-123">Medidas y grupos de medida</span><span class="sxs-lookup"><span data-stu-id="6046c-123">Measures and Measure Groups</span></span>](../multidimensional-models/measures-and-measure-groups.md)||  
|[<span data-ttu-id="6046c-124">Particiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="6046c-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partitions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="6046c-125">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="6046c-125">Perspectives</span></span>](perspectives.md)||  
  
  
