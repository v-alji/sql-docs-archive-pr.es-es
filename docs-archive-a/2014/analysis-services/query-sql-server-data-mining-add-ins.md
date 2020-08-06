---
title: Consulta (SQL Server complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90794aae8a3d664d47ab251ffdd954f22d48f992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748970"
---
# <a name="query-sql-server-data-mining-add-ins"></a><span data-ttu-id="991ca-102">Consulta (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="991ca-102">Query (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="991ca-103">![Botón Modelo de consultas, cinta de opciones Minería de datos](media/dmc-query.gif "Botón Modelo de consultas, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="991ca-103">![Query Model button, Data Mining ribbon](media/dmc-query.gif "Query Model button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="991ca-104">El Asistente para **Consulta** le permite interactuar con modelos de minería de datos existentes con el fin de realizar predicciones a partir de los datos de una tabla de Excel, un rango de Excel u otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="991ca-104">The **Query** wizard helps you interact with existing mining models to make predictions based on data in an Excel table, an Excel range, or another data source.</span></span> <span data-ttu-id="991ca-105">El proceso de aplicar nuevos datos a un modelo existente para predecir tendencias se denomina *consulta de predicción*.</span><span class="sxs-lookup"><span data-stu-id="991ca-105">The process of applying new data to an existing model to predict trends is called a *prediction query*.</span></span>  
  
 <span data-ttu-id="991ca-106">El asistente para **Consulta** también proporciona un editor avanzado para la creación o modificación de modelos de minería de datos, para la generación de consultas personalizadas o para trabajar con estructuras que no admiten otras herramientas, como conjuntos de datos anidados.</span><span class="sxs-lookup"><span data-stu-id="991ca-106">The **Query** wizard also provides an advanced editor for creating or modifying data mining models, for generating custom queries, or for working with structures not supported in the other tools, such as nested datasets.</span></span>  
  
-   <span data-ttu-id="991ca-107">Utilice el editor de texto para escribir o pegar en las instrucciones de extensiones de minería de datos (DMX) que ha creado en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="991ca-107">Use the text editor to type or paste in the Data Mining Extensions (DMX) statements you've created elsewhere.</span></span>  
  
-   <span data-ttu-id="991ca-108">Use el Generador de consultas interactivo para crear una instrucción DMX personalizada con la ayuda de plantillas y cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="991ca-108">Use the interactive Query Builder to compose a custom DMX statement with the help of templates and dialog boxes.</span></span>  
  
-   <span data-ttu-id="991ca-109">Cree instrucciones DMX para administrar o para realizar copias de seguridad de modelos y estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="991ca-109">Create DMX statements to manage or back up mining models and structures.</span></span>  
  
## <a name="using-the-query-wizard"></a><span data-ttu-id="991ca-110">Usar el Asistente para consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="991ca-110">Using the Query Wizard</span></span>  
  
1.  <span data-ttu-id="991ca-111">En primer lugar, debe especificar un origen de datos para usarlo como entrada.</span><span class="sxs-lookup"><span data-stu-id="991ca-111">First, you must specify a source for the data to use as input.</span></span> <span data-ttu-id="991ca-112">Puede usar datos de una tabla o un rango de Excel existente, o bien especificar una instrucción SQL para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="991ca-112">You can use data in an existing Excel table or range, or you can specify a SQL statement to retrieve the data.</span></span>  
  
2.  <span data-ttu-id="991ca-113">A continuación, el asistente muestra una lista de los modelos de minería de datos del servidor al que está conectado.</span><span class="sxs-lookup"><span data-stu-id="991ca-113">Next, the wizard presents a list of data mining models on the server to which you are connected.</span></span> <span data-ttu-id="991ca-114">Si conoce el modelo que desea usar y está familiarizado con la minería de datos, puede hacer clic también en **Avanzadas** para abrir el **Editor de consultas avanzadas de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="991ca-114">If you know the model you want and are familiar with data mining, you can also click **Advanced** to open the **Data Mining Advanced Query Editor**.</span></span>  
  
3.  <span data-ttu-id="991ca-115">Dependiendo del tipo de modelo que elija, deberá especificar la columna que contenga los datos que desea evaluar y deberá definir asignaciones entre las columnas de datos de entrada y las columnas del modelo.</span><span class="sxs-lookup"><span data-stu-id="991ca-115">Depending on the type of model that you choose, you must specify the column that contains the data to be evaluated, and define mappings between the input data columns and the model columns.</span></span> <span data-ttu-id="991ca-116">En función del algoritmo que elija, podrá establecer otras propiedades en el modelo.</span><span class="sxs-lookup"><span data-stu-id="991ca-116">Depending on the algorithm you choose, you can set other properties on the model.</span></span>  
  
4.  <span data-ttu-id="991ca-117">Por último, el asistente le ofrece también la posibilidad de elegir una o varias predicciones, y especificar un destino donde guardar los resultados.</span><span class="sxs-lookup"><span data-stu-id="991ca-117">Finally, the wizard also gives you the ability to choose one or more predictions, and specify a destination in which to store the results.</span></span>  
  
 <span data-ttu-id="991ca-118">En cualquier momento puede hacer clic en **Avanzadas** para cambiar al **Editor de consultas avanzadas de minería de datos**, que le permitirá controlar mejor cada parte de la instrucción DMX.</span><span class="sxs-lookup"><span data-stu-id="991ca-118">At any time, you can click **Advanced** to switch to the **Data Mining Advanced Query Editor**, which gives you more control over each part of the DMX statement.</span></span> <span data-ttu-id="991ca-119">Para obtener más información acerca de cómo usar las herramientas avanzadas de edición de consultas, vea [Editor de consultas avanzadas de minería de datos](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="991ca-119">For more information about how to use the advanced query editing tools, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="991ca-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="991ca-120">Requirements</span></span>  
 <span data-ttu-id="991ca-121">Para utilizar el **Asistente para consultade minería de datos** , debe estar conectado a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="991ca-121">To use the **Query** wizard, you must be connected to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="991ca-122">Además, el servidor debe contener como mínimo un modelo de minería de datos de un tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="991ca-122">Moreover, the server must contain at least one data mining model of an appropriate type.</span></span> <span data-ttu-id="991ca-123">Si no hay disponible ningún modelo de minería de datos, puede crear uno con los asistentes que ofrece el Cliente de minería de datos para Excel.</span><span class="sxs-lookup"><span data-stu-id="991ca-123">If no mining models are available, you can create one by using the wizards provided in the Data Mining Client for Excel.</span></span> <span data-ttu-id="991ca-124">Para obtener información acerca de cómo crear un nuevo modo de minería de datos mediante un asistente, vea [crear un modelo de minería de datos](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="991ca-124">For information about how to create a new mining mode by using a wizard, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991ca-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="991ca-125">See Also</span></span>  
 <span data-ttu-id="991ca-126">[Implementar y escalar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="991ca-126">[Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="991ca-127">Cliente de minería de datos para Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="991ca-127">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
