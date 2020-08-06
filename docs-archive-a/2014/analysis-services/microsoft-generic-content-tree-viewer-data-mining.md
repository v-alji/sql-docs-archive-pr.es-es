---
title: Visor de árbol de contenido genérico de Microsoft (minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.contentviewer.f1
ms.assetid: 751b4393-f6fd-48c1-bcef-bdca589ce34c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0dab06d6af8f2c5af029d9ce831f518faa4067e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749520"
---
# <a name="microsoft-generic-content-tree-viewer-data-mining"></a><span data-ttu-id="1a12b-102">Visor de árbol de contenido genérico de Microsoft (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="1a12b-102">Microsoft Generic Content Tree Viewer (Data Mining)</span></span>
  <span data-ttu-id="1a12b-103">El **Visor de árbol de contenido genérico de Microsoft** muestra información detallada sobre el contenido de un modelo de minería de datos en un formato de tabla HTML normalizado.</span><span class="sxs-lookup"><span data-stu-id="1a12b-103">The **Microsoft Generic Content Tree Viewer** displays detailed information about the contents of a data mining mode in a standardized HTML table format.</span></span> <span data-ttu-id="1a12b-104">Esta vista es útil porque expone la estructura subyacente del modelo, así como los detalles sobre los coeficientes, la distribución de valores y mucho más.</span><span class="sxs-lookup"><span data-stu-id="1a12b-104">This view is useful because it exposes the underlying structure of the model, as well details about coefficients, the distribution of values, and much more.</span></span>  
  
 <span data-ttu-id="1a12b-105">El contenido real que se muestra en la tabla varía en función del algoritmo utilizado y puede incluir columnas, reglas, propiedades, atributos, nodos y fórmulas.</span><span class="sxs-lookup"><span data-stu-id="1a12b-105">The actual content displayed in the table varies depending on the algorithm that was used and might include columns, rules, properties, attributes, nodes, and formulas.</span></span> <span data-ttu-id="1a12b-106">Para obtener más información sobre el contenido del modelo y cómo interpretar la información para cada tipo de modelo, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1a12b-106">For more information about model content, and how to interpret the information for each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="1a12b-107">La información que se muestra en el visor usa una estructura común basada en el conjunto de filas de esquema de contenido de los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1a12b-107">The information that is displayed in the viewer uses a common structure that is based on the content schema rowset for mining models.</span></span> <span data-ttu-id="1a12b-108">El conjunto de filas de esquema de contenido es un marco genérico para almacenar los patrones, las estadísticas y otro contenido de un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1a12b-108">The content schema rowset is a generic framework for storing patterns, statistics, and other contents of a data mining model.</span></span> <span data-ttu-id="1a12b-109">Para obtener una lista de las columnas del conjunto de filas de esquema de minería de datos de los modelos de minería de datos, vea [Conjunto de filas DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="1a12b-109">For a list of the columns in the data mining schema rowset for mining models, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a12b-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="1a12b-110">Options</span></span>  
 <span data-ttu-id="1a12b-111">**Título del nodo (Id. único)**</span><span class="sxs-lookup"><span data-stu-id="1a12b-111">**Node caption (Unique ID)**</span></span>  
 <span data-ttu-id="1a12b-112">Este panel muestra una lista de todos los nodos del modelo de minería seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1a12b-112">This pane displays a list of all the nodes in the selected mining model.</span></span> <span data-ttu-id="1a12b-113">La manera en que se organizan los nodos en el árbol es diferente según el tipo de modelo que se está viendo.</span><span class="sxs-lookup"><span data-stu-id="1a12b-113">The way the nodes are arranged in the tree is different depending on the type of model you are viewing.</span></span>  
  
 <span data-ttu-id="1a12b-114">Puede hacer clic en cada nodo para mostrar información detallada en el panel **Detalles del nodo** .</span><span class="sxs-lookup"><span data-stu-id="1a12b-114">You can click each node to display details about the node in the **Node details** pane.</span></span>  
  
 <span data-ttu-id="1a12b-115">**Detalles del nodo**</span><span class="sxs-lookup"><span data-stu-id="1a12b-115">**Node details**</span></span>  
 <span data-ttu-id="1a12b-116">Muestra información detallada sobre el contenido del nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1a12b-116">Displays detailed information about the content of the selected node.</span></span> <span data-ttu-id="1a12b-117">Cada nodo almacena su información en un formato normalizado, pero el contenido e importancia de cada línea de la tabla dependen del tipo de modelo o del tipo de nodo que se está viendo.</span><span class="sxs-lookup"><span data-stu-id="1a12b-117">Each node stores its information in a standardized format, but the contents and significance of each line of the table depends on the type of model or type of node that you are viewing.</span></span> <span data-ttu-id="1a12b-118">Por ejemplo, la información almacenada para un nodo que representa una regla de un modelo de asociación contiene información diferente que un nodo que representa un árbol de un modelo de árboles de decisión.</span><span class="sxs-lookup"><span data-stu-id="1a12b-118">For example, the information stored for a node that represents a rule in an association model contains different information than a node that represents a tree in a decision trees model.</span></span>  
  
 <span data-ttu-id="1a12b-119">Para obtener más información sobre cómo interpretar la información de nodo de un tipo de modelo específico, vea [Contenido del modelo de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1a12b-119">For information about how to interpret the node information for a specific model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a12b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a12b-120">See Also</span></span>  
 <span data-ttu-id="1a12b-121">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1a12b-121">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1a12b-122">[Visores de modelos de minería de datos &#40;diseñador de modelos de minería de datos&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="1a12b-122">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="1a12b-123">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1a12b-123">Data Mining Queries</span></span>](data-mining/data-mining-queries.md)  
  
  
