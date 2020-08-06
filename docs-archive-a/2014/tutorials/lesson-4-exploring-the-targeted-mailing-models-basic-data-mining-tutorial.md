---
title: 'Lección 4: explorar los modelos de correo directo (tutorial básico de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e00c5b9-a9f8-4503-99ee-377c9cc02d7f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 8659350b126164e06550acdbecec04bb07499c55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747769"
---
# <a name="lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial"></a><span data-ttu-id="02773-102">Lección 4: Explorar los modelos de correo directo (tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="02773-102">Lesson 4: Exploring the Targeted Mailing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="02773-103">Una vez procesados los modelos del proyecto, puede explorarlos para buscar tendencias interesantes.</span><span class="sxs-lookup"><span data-stu-id="02773-103">After the models in your project have been processed, you can explore them to look for interesting trends.</span></span> <span data-ttu-id="02773-104">Puesto que los patrones pueden ser complejos y difíciles simplemente examinando números, Minería de datos de SQL Server proporciona algunas herramientas visuales que le ayudan a investigar los datos y entender las reglas y relaciones que los algoritmos han detectado en los datos.</span><span class="sxs-lookup"><span data-stu-id="02773-104">Because patterns can be complex and difficult simply by looking at numbers, SQL Server Data Mining provides some visual tools that help you investigate the data and understand the rules and relationships that the algorithms have discovered within the data.</span></span> <span data-ttu-id="02773-105">También puede utilizar diversas pruebas de precisión para validar el conjunto de datos o detectar qué modelo funciona mejor antes de implementarlo.</span><span class="sxs-lookup"><span data-stu-id="02773-105">You can also use a variety of accuracy tests to validate your dataset or discover which model performs best before you deploy it.</span></span>  
  
 <span data-ttu-id="02773-106">Cuando se usa [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para explorar los modelos, cada modelo creado aparece en la pestaña **visor de modelos de minería** de datos del diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="02773-106">When you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to explore your models, each model you created is listed in the **Mining Model Viewer** tab in Data Mining Designer.</span></span> <span data-ttu-id="02773-107">Puede usar los visores para explorar los modelos.</span><span class="sxs-lookup"><span data-stu-id="02773-107">You can use the viewers to explore the models.</span></span> <span data-ttu-id="02773-108">Estos visores también están disponibles en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02773-108">These viewers are also available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="02773-109">Cada algoritmo usado para crear un modelo en [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] devuelve un tipo de resultado diferente.</span><span class="sxs-lookup"><span data-stu-id="02773-109">Each algorithm that you used to build a model in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] returns a different type of result.</span></span> <span data-ttu-id="02773-110">Por tanto, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proporciona visores personalizados para cada tipo de modelo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="02773-110">Therefore, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides custom viewers for each type of machine learning model.</span></span>  
  
 <span data-ttu-id="02773-111">Si desea entrar en detalles, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] también proporciona un visor HTML, denominado **visor de árbol de contenido genérico**, que muestra información detallada acerca de los datos del modelo y los patrones encontrados, en formato semitabular.</span><span class="sxs-lookup"><span data-stu-id="02773-111">If you want to get into details, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides an HTML viewer, called the **Generic Content Tree Viewer**, that displays detailed information about the model data and any patterns that were found, in a semi-tabular format.</span></span> <span data-ttu-id="02773-112">Para obtener más información, vea [Examinar un modelo usando el Visor de árbol de contenido genérico de Microsoft](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="02773-112">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
 <span data-ttu-id="02773-113">En esta lección examinará los resultados de los tres modelos.</span><span class="sxs-lookup"><span data-stu-id="02773-113">In this lesson you will look at the results from your three models.</span></span> <span data-ttu-id="02773-114">Cada tipo de modelo se basa en un algoritmo diferente y proporciona visiones diferentes de los datos.</span><span class="sxs-lookup"><span data-stu-id="02773-114">Each model type is based on a different algorithm and provides different insights into the data.</span></span>  
  
-   <span data-ttu-id="02773-115">El modelo Árbol de decisión le indica los factores que influyen en la compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="02773-115">The Decision Tree model tells you about factors that influence bike buying.</span></span>  
  
-   <span data-ttu-id="02773-116">El modelo Agrupación en clústeres agrupa los clientes por atributos, como el comportamiento de compra de bicicletas y otros atributos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="02773-116">The Clustering model groups your customers by attributes that include their bike buying behavior and other selected attributes.</span></span>  
  
-   <span data-ttu-id="02773-117">El modelo Bayes naive le permite examinar las relaciones entre los diferentes atributos.</span><span class="sxs-lookup"><span data-stu-id="02773-117">The Naive Bayes model enables you to explore the relationship between different attributes.</span></span>  
  
 <span data-ttu-id="02773-118">Vea los temas siguientes para obtener más información sobre cada uno de los visores de modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="02773-118">See the following topics to learn more about each of the mining model viewers.</span></span>  
  
-   [<span data-ttu-id="02773-119">Explorar el modelo de árbol de decisión &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="02773-119">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="02773-120">Explorar el modelo de agrupación en clústeres &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="02773-120">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="02773-121">Explorar el modelo Bayes Naive &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="02773-121">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="02773-122">Los tres modelos se pueden ver mediante el **visor de árbol de contenido genérico**, para extraer fórmulas, valores de datos, etc.</span><span class="sxs-lookup"><span data-stu-id="02773-122">All three models can be viewed using the **Generic Content Tree Viewer**, to extract formulas, data values, and so forth.</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="02773-123">Primera tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="02773-123">First Task in Lesson</span></span>  
 [<span data-ttu-id="02773-124">Explorar el modelo de árbol de decisión &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="02773-124">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="02773-125">Lección anterior</span><span class="sxs-lookup"><span data-stu-id="02773-125">Previous Lesson</span></span>  
 [<span data-ttu-id="02773-126">Lección 3: Adición y procesamiento de modelos</span><span class="sxs-lookup"><span data-stu-id="02773-126">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="02773-127">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="02773-127">Next Lesson</span></span>  
 [<span data-ttu-id="02773-128">Lección 5: probar los modelos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="02773-128">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="02773-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02773-129">See Also</span></span>  
 <span data-ttu-id="02773-130">[Tareas y procedimientos del visor de modelos de minería de datos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="02773-130">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="02773-131">Visores de modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="02773-131">Data Mining Model Viewers</span></span>](../../2014/analysis-services/data-mining/data-mining-model-viewers.md)  
  
  
