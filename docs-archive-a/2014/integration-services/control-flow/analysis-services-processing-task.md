---
title: Tarea Procesamiento de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.f1
helpviewer_keywords:
- Analysis Services Processing task
- processing objects [Integration Services]
ms.assetid: e5748836-b4ce-4e17-ab6b-617a336f02f4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19ef8046c06c9131b3ea2eb8ffe267c026808dfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744816"
---
# <a name="analysis-services-processing-task"></a><span data-ttu-id="cebe1-102">Procesamiento de Analysis Services, tarea</span><span class="sxs-lookup"><span data-stu-id="cebe1-102">Analysis Services Processing Task</span></span>
  <span data-ttu-id="cebe1-103">La tarea Procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] procesa objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] como modelos tabulares, cubos, dimensiones y modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="cebe1-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task processes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects such as tabular models, cubes, dimensions, and mining models.</span></span>  
  
 <span data-ttu-id="cebe1-104">Al procesar modelos tabulares, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cebe1-104">When processing tabular models, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="cebe1-105">No puede realizar análisis de impacto en modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="cebe1-105">You cannot perform impact analysis on tabular models.</span></span>  
  
-   <span data-ttu-id="cebe1-106">Algunas opciones de procesamiento para el modo tabular no están expuestas como, por ejemplo, el proceso de desfragmentación y el proceso de recálculo.</span><span class="sxs-lookup"><span data-stu-id="cebe1-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="cebe1-107">Puede llevar a cabo estas funciones mediante la tarea Ejecutar DDL.</span><span class="sxs-lookup"><span data-stu-id="cebe1-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
-   <span data-ttu-id="cebe1-108">Las opciones Procesar índice y Procesar actualización no son adecuadas para los modelos tabulares y no deben usarse.</span><span class="sxs-lookup"><span data-stu-id="cebe1-108">The options Process Index and Process Update are not appropriate for tabular models and should not be used.</span></span>  
  
-   <span data-ttu-id="cebe1-109">Los valores de las operaciones por lotes se omiten para los modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="cebe1-109">Batch settings are ignored for tabular models.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="cebe1-110">incluye diversas tareas que realizan operaciones de Business Intelligence, como la ejecución de instrucciones del lenguaje de definición de datos (DDL) y consultas de predicción de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="cebe1-110">includes a number of tasks that perform business intelligence operations, such as running Data Definition Language (DDL) statements and data mining prediction queries.</span></span> <span data-ttu-id="cebe1-111">Para obtener más información sobre tareas de Business Intelligence relacionadas, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cebe1-111">For more information about related business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cebe1-112">Tarea Ejecutar DDL de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cebe1-112">Analysis Services Execute DDL Task</span></span>](analysis-services-execute-ddl-task.md)  
  
-   [<span data-ttu-id="cebe1-113">Tarea Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="cebe1-113">Data Mining Query Task</span></span>](data-mining-query-task.md)  
  
## <a name="object-processing"></a><span data-ttu-id="cebe1-114">Procesamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="cebe1-114">Object Processing</span></span>  
 <span data-ttu-id="cebe1-115">Pueden procesarse varios objetos a la vez.</span><span class="sxs-lookup"><span data-stu-id="cebe1-115">Multiple objects can be processed at the same time.</span></span> <span data-ttu-id="cebe1-116">Cuando se procesan varios objetos, se definen valores de configuración que se aplicarán al procesamiento de todos los objetos del lote.</span><span class="sxs-lookup"><span data-stu-id="cebe1-116">When processing multiple objects, you define settings that apply to the processing of all the objects in the batch.</span></span>  
  
 <span data-ttu-id="cebe1-117">Los objetos de un lote pueden procesarse de manera secuencial o en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cebe1-117">Objects in a batch can be processed in sequence or in parallel.</span></span> <span data-ttu-id="cebe1-118">Si el lote no contiene objetos para los que el procesamiento secuencial sea importante, debe considerarse el procesamiento paralelo, ya que puede aumentar la velocidad de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="cebe1-118">If the batch does not contain objects for which processing sequence is important, parallel processing can speed up processing.</span></span> <span data-ttu-id="cebe1-119">Si los objetos del lote se procesan en paralelo, se puede configurar la tarea de forma que determine automáticamente el número de objetos que se procesarán simultáneamente, aunque también se puede especificar manualmente este número.</span><span class="sxs-lookup"><span data-stu-id="cebe1-119">If objects in the batch are processed in parallel, you can configure the task to let it determine how many objects to process in parallel, or you can manually specify the number of objects to process at the same time.</span></span> <span data-ttu-id="cebe1-120">Si los objetos se procesan de forma secuencial, se puede establecer un atributo de transacción en el lote especificando todos los objetos de una transacción o utilizando una transacción independiente para cada objeto del lote.</span><span class="sxs-lookup"><span data-stu-id="cebe1-120">If objects are processed sequentially, you can set a transaction attribute on the batch either by enlisting all objects in one transaction or by using a separate transaction for each object in the batch.</span></span>  
  
 <span data-ttu-id="cebe1-121">Al procesar objetos de análisis, puede que también desee procesar los objetos que dependen de ellos.</span><span class="sxs-lookup"><span data-stu-id="cebe1-121">When you process analytic objects, you might also want to process the objects that depend on them.</span></span> <span data-ttu-id="cebe1-122">La tarea Procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluye la opción de procesar los objetos dependientes, además de los seleccionados.</span><span class="sxs-lookup"><span data-stu-id="cebe1-122">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task includes an option to process any dependent objects in addition to the selected objects.</span></span>  
  
 <span data-ttu-id="cebe1-123">Normalmente, las tablas de dimensiones se procesan antes que las tablas de hechos.</span><span class="sxs-lookup"><span data-stu-id="cebe1-123">Typically, you process dimension tables before processing fact tables.</span></span> <span data-ttu-id="cebe1-124">Puede producirse errores si intenta procesar las tablas de hechos antes que las tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="cebe1-124">You may encounter errors if you try to process fact tables before processing the dimension tables.</span></span>  
  
 <span data-ttu-id="cebe1-125">Esta tarea también permite configurar el control de errores en las claves de dimensión.</span><span class="sxs-lookup"><span data-stu-id="cebe1-125">This task also lets you configure the handling of errors in dimension keys.</span></span> <span data-ttu-id="cebe1-126">Por ejemplo, la tarea puede omitir los errores o bien detenerse cuando se alcance un número especificado de errores.</span><span class="sxs-lookup"><span data-stu-id="cebe1-126">For example, the task can ignore errors or stop after a specified number of errors occur.</span></span> <span data-ttu-id="cebe1-127">La tarea puede usar la configuración de errores predeterminada; también se puede definir una configuración de errores personalizada.</span><span class="sxs-lookup"><span data-stu-id="cebe1-127">The task can use the default error configuration, or you can construct a custom error configuration.</span></span> <span data-ttu-id="cebe1-128">En la configuración de errores personalizada, debe especificar el modo en que la tarea controla los errores, así como las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="cebe1-128">In the custom error configuration, you specify how the task handles errors and the error conditions.</span></span> <span data-ttu-id="cebe1-129">Por ejemplo, puede especificar que la tarea debe detenerse cuando se produzca el cuarto error o indicar cómo deben controlarse los valores **Null** en las claves.</span><span class="sxs-lookup"><span data-stu-id="cebe1-129">For example, you can specify that the task should stop running when the fourth error occurs, or specify how the task should handle **Null** key values.</span></span> <span data-ttu-id="cebe1-130">La configuración de errores personalizada puede incluir también la ruta de un archivo de registro de errores.</span><span class="sxs-lookup"><span data-stu-id="cebe1-130">The custom error configuration can also include the path of an error log.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cebe1-131">La tarea Procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solo puede procesar objetos de análisis creados mediante las herramientas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cebe1-131">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task can process only analytic objects created by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools.</span></span>  
  
 <span data-ttu-id="cebe1-132">Esta tarea se suele usar en combinación con una tarea de inserción masiva, que carga datos en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o con una tarea Flujo de datos que implementa un flujo de datos que carga datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="cebe1-132">This task is frequently used in combination with a Bulk Insert task that loads data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, or a Data Flow task that implements a data flow that loads data into a table.</span></span> <span data-ttu-id="cebe1-133">Por ejemplo, la tarea Flujo de datos puede tener un flujo de datos que extraiga los datos de una base de datos transaccional en línea (OLTP) y los cargue en una tabla de hechos de un almacenamiento de datos, tras lo cual se realiza la llamada a la tarea Procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para que procese el cubo generado en el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="cebe1-133">For example, the Data Flow task might have a data flow that extracts data from an online transactional database (OLTP) database and loads it into a fact table in a data warehouse, after which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task is called to process the cube built on the data warehouse.</span></span>  
  
 <span data-ttu-id="cebe1-134">La tarea Procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa un administrador de conexiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para conectarse a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cebe1-134">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="cebe1-135">Para más información, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cebe1-135">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="cebe1-136">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="cebe1-136">Error Handling</span></span>  
  
## <a name="configuration-of-the-analysis-services-processing-task"></a><span data-ttu-id="cebe1-137">Configuración de la tarea Procesamiento de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cebe1-137">Configuration of the Analysis Services Processing Task</span></span>  
 <span data-ttu-id="cebe1-138">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="cebe1-138">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cebe1-139">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cebe1-139">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cebe1-140">Editor de la tarea de procesamiento de Analysis Services &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="cebe1-140">Analysis Services Processing Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="cebe1-141">Editor de la tarea de procesamiento de Analysis Services &#40;página Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cebe1-141">Analysis Services Processing Task Editor &#40;Analysis Services Page&#41;</span></span>](../analysis-services-processing-task-editor-analysis-services-page.md)  
  
-   [<span data-ttu-id="cebe1-142">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="cebe1-142">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="cebe1-143">Para obtener más información sobre cómo configurar estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="cebe1-143">For more information about setting these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="cebe1-144">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="cebe1-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-analysis-services-processing-task"></a><span data-ttu-id="cebe1-145">Configuración mediante programación de la tarea Procesamiento de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cebe1-145">Programmatic Configuration of the Analysis Services Processing Task</span></span>  
 <span data-ttu-id="cebe1-146">Para obtener más información sobre cómo establecer estas propiedades mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cebe1-146">For more information about programmatically setting these properties, click one of the following topics:</span></span>  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.DTSProcessingTask>  
  
  