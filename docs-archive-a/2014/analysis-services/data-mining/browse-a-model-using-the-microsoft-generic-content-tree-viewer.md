---
title: Examinar un modelo usando el visor de árbol de contenido genérico de Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
ms.assetid: 4a5f7c51-c704-4214-b05d-21cf735e6d96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90d47262a09060a11020e50b3724753799d2d188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677319"
---
# <a name="browse-a-model-using-the-microsoft-generic-content-tree-viewer"></a><span data-ttu-id="a686c-102">Examinar un modelo usando el Visor de árbol de contenido genérico de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a686c-102">Browse a Model Using the Microsoft Generic Content Tree Viewer</span></span>
  <span data-ttu-id="a686c-103">El Visor de contenido genérico del modelo de minería de datos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] proporciona información detallada sobre los patrones encontrados por el algoritmo de minería de datos, y también ofrece acceso a diversas estadísticas generadas durante el proceso de análisis.</span><span class="sxs-lookup"><span data-stu-id="a686c-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer provides detailed information about the patterns found by the mining algorithm, and also provides access to various statistics generated during the analysis process.</span></span> <span data-ttu-id="a686c-104">La cantidad y el tipo de información dependen del algoritmo utilizado, pero pueden incluir las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="a686c-104">The amount and type of information depends on the algorithm that was used, but can include the following categories:</span></span>  
  
-   <span data-ttu-id="a686c-105">Segmentos de datos y sus características.</span><span class="sxs-lookup"><span data-stu-id="a686c-105">Segments of data, and their characteristics.</span></span>  
  
-   <span data-ttu-id="a686c-106">Estadísticas descriptivas sobre cada grupo o sobre el conjunto completo de datos.</span><span class="sxs-lookup"><span data-stu-id="a686c-106">Descriptive statistics about each group or about the whole set of data.</span></span>  
  
-   <span data-ttu-id="a686c-107">Número de bifurcaciones o nodos secundarios de un árbol.</span><span class="sxs-lookup"><span data-stu-id="a686c-107">The number of branches or child nodes in a tree.</span></span>  
  
-   <span data-ttu-id="a686c-108">Diversos cálculos, como la varianza y la media, para un clúster o un conjunto completo de datos.</span><span class="sxs-lookup"><span data-stu-id="a686c-108">Calculations, such as variance and mean, for a cluster or a whole set of data.</span></span>  
  
 <span data-ttu-id="a686c-109">Ver esta información puede servir de ayuda para entender mejor los resultados del análisis.</span><span class="sxs-lookup"><span data-stu-id="a686c-109">Viewing this information can help you better understand the results of your analysis.</span></span> <span data-ttu-id="a686c-110">También se pueden identificar distintas maneras de ajustar y volver a entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="a686c-110">You can also identify ways to fine-tune, and then retrain, your model.</span></span> <span data-ttu-id="a686c-111">O bien, se puede decidir volver a entrenar el modelo usando un algoritmo diferente.</span><span class="sxs-lookup"><span data-stu-id="a686c-111">Or, you might decide to retrain by using a different algorithm.</span></span>  
  
## <a name="viewing-mining-model-content"></a><span data-ttu-id="a686c-112">Ver contenido del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a686c-112">Viewing Mining Model Content</span></span>  
 <span data-ttu-id="a686c-113">El Visor de contenido genérico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] muestra las columnas, las reglas, las propiedades, los atributos, los nodos y otro tipo de contenido del *conjunto de filas de esquema de contenido* del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a686c-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer displays the columns, rules, properties, attributes, nodes, and other content from the *content schema rowset* of the mining model.</span></span> <span data-ttu-id="a686c-114">El conjunto de filas de esquema de contenido es un marco genérico para presentar información detallada sobre el contenido de un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a686c-114">The content schema rowset is a generic framework for presenting detailed information about the content of a data mining model.</span></span>  
  
 <span data-ttu-id="a686c-115">Esta información detallada está contenida en una tabla HTML que representa los patrones, los clústeres, o los árboles del modelo como nodos.</span><span class="sxs-lookup"><span data-stu-id="a686c-115">This detailed information is contained in an HTML table that represents the patterns, clusters, or trees in the model as nodes.</span></span> <span data-ttu-id="a686c-116">Puede hacer clic en cada nodo y expandirlo para ver más información, tal como las fórmulas o el recuento de valores distintos para un atributo numérico.</span><span class="sxs-lookup"><span data-stu-id="a686c-116">You can click on each node and expand it to see more detail, such as the formulas or the count of distinct values for a numeric attribute.</span></span> <span data-ttu-id="a686c-117">También puede explorar las relaciones de elementos primarios y secundarios entre los nodos.</span><span class="sxs-lookup"><span data-stu-id="a686c-117">You can also explore the child-parent relationships among the nodes.</span></span>  
  
 <span data-ttu-id="a686c-118">Para obtener más información sobre el significado general de los términos que se usan en el contenido del modelo de minería de datos, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a686c-118">For more information about the general meaning of the terms used in the mining model content, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span> <span data-ttu-id="a686c-119">El tema también contiene vínculos a información acerca del contenido del modelo de minería de datos para tipos específicos de modelos.</span><span class="sxs-lookup"><span data-stu-id="a686c-119">The topic also contains links to information about mining model content for specific types of models.</span></span> <span data-ttu-id="a686c-120">Cada tipo de modelo de minería de datos contiene información muy específica del algoritmo y de los patrones localizados en los datos, de modo que se recomienda consultar el tema de referencia técnica de cada tipo de modelo para comprender cada tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="a686c-120">Each type of mining model contains information that is highly specific to the algorithm and the patterns found in the data, so we recommend that you consult the technical reference topic for each model type in order to fully understand each model type.</span></span>  
  
## <a name="querying-mining-model-content"></a><span data-ttu-id="a686c-121">Consultar el contenido del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a686c-121">Querying Mining Model Content</span></span>  
 <span data-ttu-id="a686c-122">La información proporcionada por el Visor de árbol de contenido genérico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] también se encuentra disponible si se consulta el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a686c-122">The same information that is provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer is also available by querying the mining model.</span></span> <span data-ttu-id="a686c-123">Puede crear consultas en el contenido del modelo de minería de datos usando instrucciones de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="a686c-123">You can create queries against mining model content by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="a686c-124">Por ejemplo, en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], se puede realizar una consulta de contenido ejecutando la siguiente instrucción de DMX:</span><span class="sxs-lookup"><span data-stu-id="a686c-124">For example, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can run a content query by executing the following DMX statement:</span></span>  
  
```  
SELECT * FROM [<mining model name>].CONTENT  
```  
  
 <span data-ttu-id="a686c-125">Para obtener más información, vea [Consultas de minería de datos](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a686c-125">For more information, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a686c-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a686c-126">See Also</span></span>  
 <span data-ttu-id="a686c-127">[Visor de árbol de contenido genérico de Microsoft &#40;minería de datos&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a686c-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span></span>  
 [<span data-ttu-id="a686c-128">Algoritmos de minería de datos &#40;Analysis Services: Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a686c-128">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
  
