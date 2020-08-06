---
title: Algoritmos de minería de datos (SQL Server complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation
- data mining algorithms
- clustering [data mining]
- linear regression
- association [data mining]
- neural networks
- logistic regression
- regression
- sequence analysis
- decision tree [data mining]
- Naive Bayes
- time series [data mining]
ms.assetid: 3a1a62e4-9fb5-4cdb-a6c6-1b8b30d417ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3a73ce5a538756a740afd2db72d585fa54f03cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676274"
---
# <a name="data-mining-algorithms-sql-server-data-mining-add-ins"></a><span data-ttu-id="c327b-102">Algoritmos de minería de datos (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c327b-102">Data Mining Algorithms (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="c327b-103">Los Complementos de minería de datos para Office admiten la creación de modelos analíticos con los siguientes algoritmos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="c327b-103">The Data Mining Add-ins for Office supports creation of analytical models using the following data mining algorithms.</span></span> <span data-ttu-id="c327b-104">Todos los algoritmos se basan en métodos conocidos de aprendizaje automático y los ha implementado Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="c327b-104">All algorithms are based on well-known machine learning methods and have been implemented by Microsoft Research.</span></span>  
  
## <a name="algorithms"></a><span data-ttu-id="c327b-105">Algoritmos</span><span class="sxs-lookup"><span data-stu-id="c327b-105">Algorithms</span></span>  
  
|<span data-ttu-id="c327b-106">Método de aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="c327b-106">Machine learning method</span></span>|<span data-ttu-id="c327b-107">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="c327b-107">How it works</span></span>|  
|-----------------------------|------------------|  
|<span data-ttu-id="c327b-108">Algoritmo de reglas de asociación de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-108">Microsoft Association Rules  algorithm</span></span>|<span data-ttu-id="c327b-109">Detectar qué productos se adquieren juntos o qué eventos se producen juntos, y usar el modelo para crear recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="c327b-109">Discover which products are purchased together or which events occur together, and use the model to create recommendations.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174916.aspx](https://msdn.microsoft.com/library/ms174916.aspx)|  
|<span data-ttu-id="c327b-110">Algoritmo de clústeres de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-110">Microsoft Clustering algorithm</span></span>|<span data-ttu-id="c327b-111">Definir segmentos de mercado, agrupar automáticamente clientes relacionados o buscar relaciones en los datos para usarlas en operaciones de minería de datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c327b-111">Define market segments, automatically group related customers together, or find relationships in data to use in further mining.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174879.aspx](https://msdn.microsoft.com/library/ms174879.aspx)|  
|<span data-ttu-id="c327b-112">Algoritmo de árboles de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-112">Microsoft Decision Trees algorithm</span></span>|<span data-ttu-id="c327b-113">Identificar relaciones desconocidas previamente entre diferentes elementos de los datos para tomar decisiones más informadas o buscar los factores que conducen a resultados específicos.</span><span class="sxs-lookup"><span data-stu-id="c327b-113">Identify previously unknown relationships between various elements of your data to better inform your decisions, or find the factors that lead to specific outcomes.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
|<span data-ttu-id="c327b-114">Algoritmo de regresión lineal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-114">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="c327b-115">Buscar una fórmula matemática que describe los factores que contribuyen a un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="c327b-115">Find a mathematical formula that describes factors that contribute to a numeric outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174824.aspx](https://msdn.microsoft.com/library/ms174824.aspx)|  
|<span data-ttu-id="c327b-116">Algoritmo de regresión logística de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-116">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="c327b-117">Identificar los factores que contribuyen a resultados binarios y aprender a utilizarlos para modificar los resultados.</span><span class="sxs-lookup"><span data-stu-id="c327b-117">Identify the factors that contribute to binary outcomes, and learn how to use those to affect results.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174828.aspx](https://msdn.microsoft.com/library/ms174828.aspx)|  
|<span data-ttu-id="c327b-118">Algoritmo Bayes Naïve de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-118">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="c327b-119">Explorar las relaciones en los datos y buscar las correlacionadas más estrechamente con un resultado.</span><span class="sxs-lookup"><span data-stu-id="c327b-119">Explore relationships in your data and find those mostly closely correlated with an outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174806.aspx](https://msdn.microsoft.com/library/ms174806.aspx)|  
|<span data-ttu-id="c327b-120">Algoritmo de redes neuronales de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-120">Microsoft Neural Networks algorithm</span></span>|<span data-ttu-id="c327b-121">Buscar relaciones ocultas entre varias entradas e incluso varias salidas.</span><span class="sxs-lookup"><span data-stu-id="c327b-121">Find hidden relationships among multiple inputs and even multiple outputs.</span></span> <span data-ttu-id="c327b-122">Se usa para la exploración o la predicción.</span><span class="sxs-lookup"><span data-stu-id="c327b-122">Use for exploration or for prediction.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174941.aspx](https://msdn.microsoft.com/library/ms174941.aspx)|  
|<span data-ttu-id="c327b-123">Algoritmo de serie temporal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c327b-123">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="c327b-124">Usar datos históricos para predecir valores futuros.</span><span class="sxs-lookup"><span data-stu-id="c327b-124">Use historical data to forecast future values.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
  
## <a name="advanced-options"></a><span data-ttu-id="c327b-125">Opciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="c327b-125">Advanced Options</span></span>  
 <span data-ttu-id="c327b-126">Cuando utiliza el Cliente de minería de datos para Excel, tiene la posibilidad de crear sus propias estructuras y modelos de minería de datos u optimizar los parámetros de los algoritmos.</span><span class="sxs-lookup"><span data-stu-id="c327b-126">When you use the Data Mining Client for Excel, you have the option to create your own data mining structures and models, or to fine-tune the parameters of the algorithms.</span></span>  
  
 [<span data-ttu-id="c327b-127">Parámetros de algoritmo &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c327b-127">Algorithm Parameters &#40;SQL Server Data Mining Add-ins&#41;</span></span>](algorithm-parameters-sql-server-data-mining-add-ins.md)  
  
 <span data-ttu-id="c327b-128">Hay dos maneras de personalizar los modelos mediante estas opciones avanzadas:</span><span class="sxs-lookup"><span data-stu-id="c327b-128">There are two ways to customize your models using these advanced options:</span></span>  
  
-   <span data-ttu-id="c327b-129">Use el Asistente para **consulta de minería de datos** para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="c327b-129">Use the **Data Mining Query** wizard to create your model.</span></span>  
  
-   <span data-ttu-id="c327b-130">En el **cliente de minería de datos**, después de iniciar el asistente, haga clic en **parámetros**.</span><span class="sxs-lookup"><span data-stu-id="c327b-130">In the **Data Mining Client**, after you start the wizard, click **Parameters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c327b-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c327b-131">See Also</span></span>  
 <span data-ttu-id="c327b-132">[&#40;de consultas SQL Server complementos de minería de datos&#41;](query-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="c327b-132">[Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="c327b-133">Modelado avanzado &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c327b-133">Advanced Modeling &#40;Data Mining Add-ins for Excel&#41;</span></span>](advanced-modeling-data-mining-add-ins-for-excel.md)  
  
  
