---
title: Tareas y procedimientos de consulta de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], how-to topics
ms.assetid: 1bc2a775-6e62-4c66-a53c-201f2ea66295
author: minewiskan
ms.author: owend
ms.openlocfilehash: 454a3af33d0c18232bb36771235b328a17da6b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677306"
---
# <a name="data-mining-query-tasks-and-how-tos"></a><span data-ttu-id="d804e-102">Tareas y procedimientos de Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d804e-102">Data Mining Query Tasks and How-tos</span></span>
  <span data-ttu-id="d804e-103">La capacidad de crear consultas es esencial para usar los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d804e-103">The ability to create queries is critical if you are to make use of your data mining models.</span></span> <span data-ttu-id="d804e-104">En esta sección se proporcionan enlaces a ejemplos de cómo crear consultas sobre un modelo de minería de datos usando las herramientas proporcionadas en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d804e-104">This section provides links to examples of how to create queries against a data mining model by using the tools provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d804e-105">Si necesita más información sobre qué es una consulta de minería de datos o los tipos diferentes de consultas que puede crear, vea [Consultas de minería de datos](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d804e-105">If you need more information about what a data mining query is, or the different types of queries you can create, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="creating-queries-with-prediction-query-builder"></a><span data-ttu-id="d804e-106">Crear consultas mediante el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="d804e-106">Creating Queries with Prediction Query Builder</span></span>  
 <span data-ttu-id="d804e-107">El Generador de consultas de predicción se proporciona en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] como una manera de generar consultas gráficamente sobre modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d804e-107">The Prediction Query Builder is provided in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a way of graphically building queries against data mining models.</span></span> <span data-ttu-id="d804e-108">Los siguientes temas explican cómo puede seleccionar un modelo, especificar un origen de datos, personalizar las predicciones y guardar la salida.</span><span class="sxs-lookup"><span data-stu-id="d804e-108">The following topics explain how you can select a model, specify a data source, customize the predictions, and save output.</span></span>  
  
-   [<span data-ttu-id="d804e-109">Crear una consulta de predicción con el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="d804e-109">Create a Prediction Query Using the Prediction Query Builder</span></span>](create-a-prediction-query-using-the-prediction-query-builder.md)  
  
-   [<span data-ttu-id="d804e-110">Crear una consulta singleton en el Diseñador de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d804e-110">Create a Singleton Query in the Data Mining Designer</span></span>](create-a-singleton-query-in-the-data-mining-designer.md)  
  
-   [<span data-ttu-id="d804e-111">Crear una consulta de predicción con el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="d804e-111">Create a Prediction Query Using the Prediction Query Builder</span></span>](create-a-prediction-query-using-the-prediction-query-builder.md)  
  
-   [<span data-ttu-id="d804e-112">Ver y guardar los resultados de una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="d804e-112">View and Save the Results of a Prediction Query</span></span>](view-and-save-the-results-of-a-prediction-query.md)  
  
-   [<span data-ttu-id="d804e-113">Modificar manualmente una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="d804e-113">Manually Edit a Prediction Query</span></span>](manually-edit-a-prediction-query.md)  
  
-   [<span data-ttu-id="d804e-114">Aplicar funciones de predicción a un modelo</span><span class="sxs-lookup"><span data-stu-id="d804e-114">Apply Prediction Functions to a Model</span></span>](apply-prediction-functions-to-a-model.md)  
  
-   [<span data-ttu-id="d804e-115">Elegir y asignar datos de entrada para una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="d804e-115">Choose and Map Input Data for a Prediction Query</span></span>](choose-and-map-input-data-for-a-prediction-query.md)  
  
## <a name="using-other-data-mining-query-tools"></a><span data-ttu-id="d804e-116">Usar otras herramientas de consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d804e-116">Using Other Data Mining Query Tools</span></span>  
 <span data-ttu-id="d804e-117">Además de usar el Generador de consultas de predicción, puede escribir directamente una consulta en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando DMX o XMLA.</span><span class="sxs-lookup"><span data-stu-id="d804e-117">In addition to using the Prediction Query Builder, you can type a query directly into [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using DMX or by using XMLA.</span></span> <span data-ttu-id="d804e-118">También puede generar consultas de predicción mediante programación y enviarlas a un servidor [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d804e-118">You can also build prediction queries programmatically and send them to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="d804e-119">En los siguientes temas se proporciona más información sobre cómo crear y trabajar con consultas de predicción fuera del Generador de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="d804e-119">The following topics provide more information about how to create and work with prediction queries outside of the Prediction Query Builder.</span></span>  
  
 [<span data-ttu-id="d804e-120">Crear una consulta de predicción singleton desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="d804e-120">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
 <span data-ttu-id="d804e-121">Describe cómo usar las herramientas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para generar y ejecutar una consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="d804e-121">Describes how to use the tools in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to build and run a prediction query.</span></span>  
  
 [<span data-ttu-id="d804e-122">Crear una consulta de predicción singleton desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="d804e-122">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
 <span data-ttu-id="d804e-123">Describe cómo usar las plantillas que se proporcionan en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para agregar parámetros a una consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="d804e-123">Describes how to use the templates that are provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add parameters to a prediction query.</span></span>  
  
 [<span data-ttu-id="d804e-124">Cambiar el valor del tiempo de espera para las consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d804e-124">Change the Time-out Value for Data Mining Queries</span></span>](change-the-time-out-value-for-data-mining-queries.md)  
 <span data-ttu-id="d804e-125">Describe cómo establecer en el servidor las propiedades que controlan el comportamiento relacionado con las consultas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d804e-125">Describes how to set properties on the server that control behavior related to data mining queries.</span></span>  
  
 [<span data-ttu-id="d804e-126">Crear una consulta de contenido en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d804e-126">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
 <span data-ttu-id="d804e-127">Describe cómo crear consultas que devuelven información detallada que se almacena en el modelo de minería de datos usando los conjuntos de filas del esquema de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d804e-127">Describes how to create queries that return detailed information that is stored in the mining model by using the data mining schema rowsets.</span></span>  
  
 [<span data-ttu-id="d804e-128">Crear una consulta de minería de datos utilizando XMLA</span><span class="sxs-lookup"><span data-stu-id="d804e-128">Create a Data Mining Query by Using XMLA</span></span>](create-a-data-mining-query-by-using-xmla.md)  
 <span data-ttu-id="d804e-129">Describe cómo crear una consulta en el contenido del modelo de minería de datos usando las plantillas XMLA incluidas en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d804e-129">Describes how to create a query against mining model content by using the XMLA templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d804e-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d804e-130">See Also</span></span>  
 <span data-ttu-id="d804e-131">[&#40;de referencia del lenguaje de expresiones y consultas Analysis Services&#41;](https://msdn.microsoft.com/library/gg492188(SQL.130).aspx) </span><span class="sxs-lookup"><span data-stu-id="d804e-131">[Query and Expression Language Reference &#40;Analysis Services&#41;](https://msdn.microsoft.com/library/gg492188(SQL.130).aspx) </span></span>  
 [<span data-ttu-id="d804e-132">Procedimientos almacenados de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d804e-132">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
