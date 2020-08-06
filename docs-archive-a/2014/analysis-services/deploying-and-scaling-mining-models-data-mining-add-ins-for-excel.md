---
title: Implementar y escalar modelos de minería de datos (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- manage
ms.assetid: 4c617375-6b01-4a71-9680-de0cbf2cff05
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd2839144d4d1667da09830aaabd1ec3f17a9c21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675044"
---
# <a name="deploying-and-scaling-mining-models-data-mining-add-ins-for-excel"></a><span data-ttu-id="07cdd-102">Implementar y ampliar modelos de minería de datos (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="07cdd-102">Deploying and Scaling Mining Models (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="07cdd-103">Las herramientas del grupo **uso del modelo** y **Administración** se proporcionan para ayudarle a administrar y examinar modelos de minería de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="07cdd-103">The tools in the **Model Usage** and **Management** group are provided to help you manage and browse existing mining models.</span></span> <span data-ttu-id="07cdd-104">Puede utilizar estas herramientas para ver cualquier modelo que esté almacenado en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], no solo los creados mediante los complementos.</span><span class="sxs-lookup"><span data-stu-id="07cdd-104">You can use these tools to view any models that are stored on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], not just those created using the add-ins.</span></span>  
  
 <span data-ttu-id="07cdd-105">Si se tienen los permisos necesarios, se pueden eliminar, modificar, cambiar de nombre o procesar modelos y estructuras de minería de datos existentes sin salir de Excel.</span><span class="sxs-lookup"><span data-stu-id="07cdd-105">If you have the necessary permissions, you can delete, modify, rename, or process existing mining models and structures without leaving Excel.</span></span>  
  
## <a name="model-usage-toolbar"></a><span data-ttu-id="07cdd-106">Barra de herramientas Uso del modelo</span><span class="sxs-lookup"><span data-stu-id="07cdd-106">Model Usage Toolbar</span></span>  
  
### <a name="browse"></a><span data-ttu-id="07cdd-107">Examinar</span><span class="sxs-lookup"><span data-stu-id="07cdd-107">Browse</span></span>  
 <span data-ttu-id="07cdd-108">Use el Asistente para **examinar** para seleccionar un modelo de minería de datos existente y, a continuación, ver y explorar el modelo en un visor que contiene varios gráficos y herramientas.</span><span class="sxs-lookup"><span data-stu-id="07cdd-108">Use the **Browse** wizard to select an existing data mining model, and then view and explore the model in a viewer that contains multiple graphs and tools.</span></span>  
  
 <span data-ttu-id="07cdd-109">Para obtener más información, vea [examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="07cdd-109">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="document-model"></a><span data-ttu-id="07cdd-110">Modelo para documentación</span><span class="sxs-lookup"><span data-stu-id="07cdd-110">Document Model</span></span>  
 <span data-ttu-id="07cdd-111">Haga clic en **modelo de documento** para iniciar un asistente que crea un informe de las estructuras y los modelos de minería de datos que ha creado.</span><span class="sxs-lookup"><span data-stu-id="07cdd-111">Click **Document Model** to start a wizard that creates a report of the mining structures and mining models that you have created.</span></span> <span data-ttu-id="07cdd-112">Puede crear informes básicos o avanzados.</span><span class="sxs-lookup"><span data-stu-id="07cdd-112">You can create basic or advanced reports.</span></span> <span data-ttu-id="07cdd-113">Los informes incluyen columnas y metadatos del modelo, por lo que son útiles para documentar el trabajo y hacer un seguimiento de los cambios en los modelos.</span><span class="sxs-lookup"><span data-stu-id="07cdd-113">The reports include column and model metadata, so are useful for documenting your work and tracking changes in models.</span></span>  
  
 <span data-ttu-id="07cdd-114">Para obtener más información, vea [documentar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="07cdd-114">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
### <a name="query"></a><span data-ttu-id="07cdd-115">Consultar</span><span class="sxs-lookup"><span data-stu-id="07cdd-115">Query</span></span>  
 <span data-ttu-id="07cdd-116">Haga clic en **consulta** para iniciar el Asistente para **consultas** .</span><span class="sxs-lookup"><span data-stu-id="07cdd-116">Click **Query** to start the **Query** wizard.</span></span> <span data-ttu-id="07cdd-117">El asistente le guía de forma interactiva por el proceso de creación de una consulta de predicción en un modelo de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="07cdd-117">The wizard interactively walks you through the process of creating a prediction query against an existing data mining model.</span></span>  
  
 <span data-ttu-id="07cdd-118">Para personalizar aún más la consulta o generar consultas no incluidas en el asistente, simplemente haga clic en el botón **avanzadas** para iniciar la **consulta de minería de datos editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="07cdd-118">To further customize the query, or build queries not included in the wizard, just click the **Advanced** button to start the **Data Mining Query Advanced Editor**.</span></span>  
  
 <span data-ttu-id="07cdd-119">Para obtener más información, vea [&#40;de consultas SQL Server complementos de minería de datos&#41;](query-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="07cdd-119">For more information, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="data-mining-advanced-query-editor"></a><span data-ttu-id="07cdd-120">Editor de consultas avanzadas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="07cdd-120">Data Mining Advanced Query Editor</span></span>  
 <span data-ttu-id="07cdd-121">En este editor, puede utilizar plantillas de Extensiones de minería de datos (DMX) para iniciar rápidamente una consulta y, después, modificar sus entradas, salidas, algoritmos y parámetros para crear un modelo de minería de datos, una estructura de minería de datos o una consulta de predicción personalizados.</span><span class="sxs-lookup"><span data-stu-id="07cdd-121">In this editor, you can use Data Mining Extensions (DMX) templates to jumpstart a query, and then modify the inputs, outputs, algorithms, and parameters to create a custom mining model, mining structure, or prediction query.</span></span>  
  
 <span data-ttu-id="07cdd-122">Para obtener más información, vea [Editor de consultas avanzadas de minería de datos](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="07cdd-122">For more information, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="management"></a><span data-ttu-id="07cdd-123">Administración</span><span class="sxs-lookup"><span data-stu-id="07cdd-123">Management</span></span>  
 <span data-ttu-id="07cdd-124">Use el Asistente para **administrar modelos** para ver los modelos existentes en la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="07cdd-124">Use the **Manage Models** wizard to view existing models on the current connection.</span></span> <span data-ttu-id="07cdd-125">También puede eliminar, cambiar el nombre, procesar o importar y exportar modelos y estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="07cdd-125">You can also delete, rename, process, or import and export mining models and structures.</span></span>  
  
 <span data-ttu-id="07cdd-126">Para obtener más información, vea [administrar modelos &#40;SQL Server complementos de minería de datos&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="07cdd-126">For more information, see [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07cdd-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07cdd-127">See Also</span></span>  
 <span data-ttu-id="07cdd-128">[Crear un modelo de minería de datos](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="07cdd-128">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="07cdd-129">Validar modelos y usar modelos para la predicción &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="07cdd-129">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
