---
title: Minería de datos (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
ms.assetid: b1c912da-72f6-4d96-89c8-55a2c4f19e88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7044ee397d457f7924d0db99dbec6659f969f104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675669"
---
# <a name="data-mining-ssas"></a><span data-ttu-id="744ff-102">Minería de datos (SSAS)</span><span class="sxs-lookup"><span data-stu-id="744ff-102">Data Mining (SSAS)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="744ff-103">proporciona una plataforma integrada para las soluciones que incorporan la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="744ff-103">provides an integrated platform for solutions that incorporate data mining.</span></span> <span data-ttu-id="744ff-104">Puede usar datos relacionales o de cubo para crear soluciones de Business Intelligence con análisis predictivos.</span><span class="sxs-lookup"><span data-stu-id="744ff-104">You can use either relational or cube data to create business intelligence solutions with predictive analytics.</span></span>  
  
## <a name="benefits-of-data-mining"></a><span data-ttu-id="744ff-105">Ventajas de la minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-105">Benefits of Data Mining</span></span>  
 <span data-ttu-id="744ff-106">La minería de datos usa principios estadísticos contrastados para detectar patrones en los datos, ayudándole a tomar decisiones inteligentes sobre problemas complejos.</span><span class="sxs-lookup"><span data-stu-id="744ff-106">Data mining uses well-researched statistical principles to discover patterns in your data, helping you make intelligent decisions about complex problems.</span></span> <span data-ttu-id="744ff-107">La aplicación de los algoritmos de minería de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a los datos le permitirá predecir tendencias, identificar patrones, crear reglas y recomendaciones, analizar la secuencia de eventos en conjuntos de datos complejos y obtener nuevos puntos de vista.</span><span class="sxs-lookup"><span data-stu-id="744ff-107">By applying the data mining algorithms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to your data, you can forecast trends, identify patterns, create rules and recommendations, analyze the sequence of events in complex data sets, and gain new insights.</span></span>  
  
 <span data-ttu-id="744ff-108">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la minería de datos es eficaz y accesible, y está integrada con las herramientas preferidas de los usuarios para el análisis y la creación de informes.</span><span class="sxs-lookup"><span data-stu-id="744ff-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], data mining is powerful, accessible, and integrated with the tools that many people prefer to use for analysis and reporting.</span></span> <span data-ttu-id="744ff-109">Vea los vínculos de esta sección para obtener toda la información sobre la minería de datos que necesita para empezar.</span><span class="sxs-lookup"><span data-stu-id="744ff-109">See the links in this section to get the broad background about data mining that you need to get started.</span></span>  
  
## <a name="key-data-mining-features"></a><span data-ttu-id="744ff-110">Características clave de la minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-110">Key Data Mining Features</span></span>  
 <span data-ttu-id="744ff-111">SQL Server proporciona las siguientes características para las soluciones integradas de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="744ff-111">SQL Server provides the following features in support of integrated data mining solutions:</span></span>  
  
-   <span data-ttu-id="744ff-112">Varios orígenes de datos: no es necesario crear un almacenamiento de datos o un cubo OLAP para realizar la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="744ff-112">Multiple data sources: You do not have to create a data warehouse or an OLAP cube to do data mining.</span></span> <span data-ttu-id="744ff-113">Puede usar datos tabulares de proveedores eternos, hojas de cálculo e incluso archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="744ff-113">You can use tabular data from external providers, spreadsheets, and even text files.</span></span> <span data-ttu-id="744ff-114">También puede minar con facilidad cubos OLAP creados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="744ff-114">You can also easily mine OLAP cubes created in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="744ff-115">Sin embargo, no se pueden usar datos de una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="744ff-115">However, you cannot use data from an in-memory database.</span></span>  
  
-   <span data-ttu-id="744ff-116">Limpieza de los datos integrados, administración de datos y ETL: Data Quality Services proporcionan herramientas avanzadas para la generación de perfiles y la limpieza de datos.</span><span class="sxs-lookup"><span data-stu-id="744ff-116">Integrated data cleansing, data management, and ETL: Data Quality Services provides advanced tools for profiling and cleansing data.</span></span> <span data-ttu-id="744ff-117">Se puede usar Integration Services para generar procesos ETL de limpieza de datos, y también para tareas de creación, procesamiento, entrenamiento y actualización de modelos.</span><span class="sxs-lookup"><span data-stu-id="744ff-117">Integration Services can be used to build ETL processes for cleaning data, and also for building, processing, training, and updating models.</span></span>  
  
-   <span data-ttu-id="744ff-118">Varios algoritmos personalizables: además de proporcionar algoritmos como la agrupación en clústeres, las redes neuronales y los árboles de decisión, la plataforma le permite desarrollar sus propios complementos con algoritmos personalizados.</span><span class="sxs-lookup"><span data-stu-id="744ff-118">Multiple customizable algorithms: In addition to providing algorithms such as clustering, neural networks, and decisions trees, the platform supports development of your own custom plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="744ff-119">Infraestructura de prueba del modelo: pruebe los modelos y los conjuntos de datos usando herramientas estadísticas tan importantes como la validación cruzada, las matrices de clasificación, los gráficos de mejora respecto al modelo predictivo y los gráficos de dispersión.</span><span class="sxs-lookup"><span data-stu-id="744ff-119">Model testing infrastructure: Test your models and data sets using important statistical tools as cross-validation, classification matrices, lift charts, and scatter plots.</span></span> <span data-ttu-id="744ff-120">Cree y administre fácilmente conjuntos de prueba y entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="744ff-120">Easily create and manage testing and training sets.</span></span>  
  
-   <span data-ttu-id="744ff-121">Consultas y obtención de detalles: cree consultas de predicción, recupere patrones y estadísticas de modelos, y obtenga información detallada de los datos de los casos.</span><span class="sxs-lookup"><span data-stu-id="744ff-121">Querying and drillthrough: Create prediction queries, retrieve model patterns and statistics, and drill through to case data.</span></span>  
  
-   <span data-ttu-id="744ff-122">Herramientas de cliente: además de los estudios de desarrollo y diseño proporcionados por SQL Server, puede usar los Complementos de minería de datos para Excel para crear, consultar y examinar los modelos.</span><span class="sxs-lookup"><span data-stu-id="744ff-122">Client tools: In addition to the development and design studios provided by SQL Server, you can use the Data Mining Add-ins for Excel to create, query, and browse models.</span></span> <span data-ttu-id="744ff-123">O bien crear clientes personalizados, incluidos servicios web.</span><span class="sxs-lookup"><span data-stu-id="744ff-123">Or, create custom clients, including Web services.</span></span>  
  
-   <span data-ttu-id="744ff-124">Compatibilidad con el lenguaje de scripting y API administrada: todos los objetos de minería de datos son completamente programables.</span><span class="sxs-lookup"><span data-stu-id="744ff-124">Scripting language support and managed API: All data mining objects are fully programmable.</span></span> <span data-ttu-id="744ff-125">El scripting es posible mediante MDX, XMLA o las extensiones de PowerShell para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="744ff-125">Scripting is possible through MDX, XMLA, or the PowerShell extensions for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="744ff-126">Use el lenguaje DMX (Extensiones de minería de datos) para crear rápidamente consultas y scripts.</span><span class="sxs-lookup"><span data-stu-id="744ff-126">Use the Data Mining Extensions (DMX) language for fast querying and scripting.</span></span>  
  
-   <span data-ttu-id="744ff-127">Seguridad e implementación: proporciona seguridad basada en roles a través de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], incluidos permisos distintos para la obtención de detalles del modelo y los datos de la estructura.</span><span class="sxs-lookup"><span data-stu-id="744ff-127">Security and deployment: Provides role-based security through [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including separate permissions for drillthrough to model and structure data.</span></span> <span data-ttu-id="744ff-128">Fácil implementación de modelos en otros servidores, de forma que los usuarios puedan tener acceso a los patrones o realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="744ff-128">Easy deployment of models to other servers, so that users can access the patterns or perform predictions</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="744ff-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="744ff-129">In This Section</span></span>  
 <span data-ttu-id="744ff-130">Los temas de esta sección presentan las características principales de la minería de datos de SQL Server y las tareas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="744ff-130">The topics in this section introduce the principal features of SQL Server Data Mining and related tasks.</span></span>  
  
-   [<span data-ttu-id="744ff-131">Conceptos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-131">Data Mining Concepts</span></span>](data-mining-concepts.md)  
  
-   [<span data-ttu-id="744ff-132">Algoritmos de minería de datos &#40;Analysis Services: Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="744ff-132">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="744ff-133">Estructuras de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="744ff-133">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="744ff-134">Modelos de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="744ff-134">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="744ff-135">Prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="744ff-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
-   [<span data-ttu-id="744ff-136">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-136">Data Mining Queries</span></span>](data-mining-queries.md)  
  
-   [<span data-ttu-id="744ff-137">Soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-137">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
-   [<span data-ttu-id="744ff-138">Herramientas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-138">Data Mining Tools</span></span>](data-mining-tools.md)  
  
-   [<span data-ttu-id="744ff-139">Arquitectura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="744ff-139">Data Mining Architecture</span></span>](data-mining-architecture.md)  
  
-   [<span data-ttu-id="744ff-140">Información general de Seguridad &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="744ff-140">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
  
