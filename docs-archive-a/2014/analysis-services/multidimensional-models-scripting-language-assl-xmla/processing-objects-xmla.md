---
title: Procesar objetos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- objects [XML for Analysis]
- XML for Analysis, objects
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
- writeback [Analysis Services], XML for Analysis
- out-of-line bindings
- processing objects [XML for Analysis]
- XMLA, objects
ms.assetid: a65b3249-303d-49c6-98af-6ac6eed11a03
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e59c7953ae8fc7d3cfceafa7b0e9d8c7186daf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748975"
---
# <a name="processing-objects-xmla"></a><span data-ttu-id="76b90-102">Procesar objetos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="76b90-102">Processing Objects (XMLA)</span></span>
  <span data-ttu-id="76b90-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , el procesamiento es el paso o la serie de pasos que convierten los datos en información para el análisis empresarial.</span><span class="sxs-lookup"><span data-stu-id="76b90-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], processing is the step or series of steps that turn data into information for business analysis.</span></span> <span data-ttu-id="76b90-104">El procesamiento varía en función del tipo de objeto, pero siempre forma parte de la conversión de datos en información.</span><span class="sxs-lookup"><span data-stu-id="76b90-104">Processing is different depending on the type of object, but processing is always part of turning data into information.</span></span>  
  
 <span data-ttu-id="76b90-105">Para procesar un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objeto, puede usar el comando [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="76b90-105">To process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object, you can use the [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) command.</span></span> <span data-ttu-id="76b90-106">El comando `Process` puede procesar los siguientes objetos en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="76b90-106">The `Process` command can process the following objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance:</span></span>  
  
-   <span data-ttu-id="76b90-107">Cubos</span><span class="sxs-lookup"><span data-stu-id="76b90-107">Cubes</span></span>  
  
-   <span data-ttu-id="76b90-108">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="76b90-108">Databases</span></span>  
  
-   <span data-ttu-id="76b90-109">Dimensions</span><span class="sxs-lookup"><span data-stu-id="76b90-109">Dimensions</span></span>  
  
-   <span data-ttu-id="76b90-110">Grupos de medida</span><span class="sxs-lookup"><span data-stu-id="76b90-110">Measure groups</span></span>  
  
-   <span data-ttu-id="76b90-111">Modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="76b90-111">Mining models</span></span>  
  
-   <span data-ttu-id="76b90-112">Estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="76b90-112">Mining structures</span></span>  
  
-   <span data-ttu-id="76b90-113">Particiones</span><span class="sxs-lookup"><span data-stu-id="76b90-113">Partitions</span></span>  
  
 <span data-ttu-id="76b90-114">Para controlar el procesamiento de los objetos, pueden establecerse diversas propiedades del comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="76b90-114">To control the processing of objects, the `Process` command has various properties that can be set.</span></span> <span data-ttu-id="76b90-115">El comando `Process` tiene propiedades para controlar: qué cantidad de procesamiento se va a realizar, qué objetos se van a procesar, si se van a utilizar o no enlaces fuera de línea, cómo controlar los errores y cómo administrar las tablas de reescritura.</span><span class="sxs-lookup"><span data-stu-id="76b90-115">The `Process` command has properties that control: how much processing will be done, which objects will be processed, whether to use out-of-line bindings, how to handle errors, and how to manage writeback tables.</span></span>  
  
## <a name="specifying-processing-options"></a><span data-ttu-id="76b90-116">Especificar opciones de procesamiento</span><span class="sxs-lookup"><span data-stu-id="76b90-116">Specifying Processing Options</span></span>  
 <span data-ttu-id="76b90-117">La propiedad [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) del `Process` comando especifica la opción de procesamiento que se va a utilizar al procesar el objeto.</span><span class="sxs-lookup"><span data-stu-id="76b90-117">The [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) property of the `Process` command specifies the processing option to use when processing the object.</span></span> <span data-ttu-id="76b90-118">Para más información sobre las opciones de procesamiento, vea [Opciones y valores de procesamiento &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="76b90-118">For more information about processing options, see [Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span></span>  
  
 <span data-ttu-id="76b90-119">En la tabla siguiente se enumeran las constantes para la propiedad `Type` y los diversos objetos que se pueden procesar con cada una de las constantes.</span><span class="sxs-lookup"><span data-stu-id="76b90-119">The following table lists the constants for the `Type` property and the various objects that can be processed using each constant.</span></span>  
  
|<span data-ttu-id="76b90-120">Valor de`Type`</span><span class="sxs-lookup"><span data-stu-id="76b90-120">`Type` value</span></span>|<span data-ttu-id="76b90-121">Objetos aplicables</span><span class="sxs-lookup"><span data-stu-id="76b90-121">Applicable objects</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="76b90-122">*ProcessFull*</span><span class="sxs-lookup"><span data-stu-id="76b90-122">*ProcessFull*</span></span>|<span data-ttu-id="76b90-123">Cubo, base de datos, dimensión, grupo de medida, modelo de minería de datos, estructura de minería de datos, partición</span><span class="sxs-lookup"><span data-stu-id="76b90-123">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="76b90-124">*ProcessAdd*</span><span class="sxs-lookup"><span data-stu-id="76b90-124">*ProcessAdd*</span></span>|<span data-ttu-id="76b90-125">Dimensión, partición</span><span class="sxs-lookup"><span data-stu-id="76b90-125">Dimension, partition</span></span>|  
|<span data-ttu-id="76b90-126">*ProcessUpdate*</span><span class="sxs-lookup"><span data-stu-id="76b90-126">*ProcessUpdate*</span></span>|<span data-ttu-id="76b90-127">Dimensión</span><span class="sxs-lookup"><span data-stu-id="76b90-127">Dimension</span></span>|  
|<span data-ttu-id="76b90-128">*ProcessIndexes*</span><span class="sxs-lookup"><span data-stu-id="76b90-128">*ProcessIndexes*</span></span>|<span data-ttu-id="76b90-129">Dimensión, cubo, grupo de medida, partición</span><span class="sxs-lookup"><span data-stu-id="76b90-129">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="76b90-130">*ProcessData*</span><span class="sxs-lookup"><span data-stu-id="76b90-130">*ProcessData*</span></span>|<span data-ttu-id="76b90-131">Dimensión, cubo, grupo de medida, partición</span><span class="sxs-lookup"><span data-stu-id="76b90-131">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="76b90-132">*ProcessDefault*</span><span class="sxs-lookup"><span data-stu-id="76b90-132">*ProcessDefault*</span></span>|<span data-ttu-id="76b90-133">Cubo, base de datos, dimensión, grupo de medida, modelo de minería de datos, estructura de minería de datos, partición</span><span class="sxs-lookup"><span data-stu-id="76b90-133">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="76b90-134">*ProcessClear*</span><span class="sxs-lookup"><span data-stu-id="76b90-134">*ProcessClear*</span></span>|<span data-ttu-id="76b90-135">Cubo, base de datos, dimensión, grupo de medida, modelo de minería de datos, estructura de minería de datos, partición</span><span class="sxs-lookup"><span data-stu-id="76b90-135">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="76b90-136">*ProcessStructure*</span><span class="sxs-lookup"><span data-stu-id="76b90-136">*ProcessStructure*</span></span>|<span data-ttu-id="76b90-137">Cubo, estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="76b90-137">Cube, mining structure</span></span>|  
|<span data-ttu-id="76b90-138">*ProcessClearStructureOnly*</span><span class="sxs-lookup"><span data-stu-id="76b90-138">*ProcessClearStructureOnly*</span></span>|<span data-ttu-id="76b90-139">Estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="76b90-139">Mining structure</span></span>|  
|<span data-ttu-id="76b90-140">*ProcessScriptCache*</span><span class="sxs-lookup"><span data-stu-id="76b90-140">*ProcessScriptCache*</span></span>|<span data-ttu-id="76b90-141">Cubo</span><span class="sxs-lookup"><span data-stu-id="76b90-141">Cube</span></span>|  
  
 <span data-ttu-id="76b90-142">Para obtener más información sobre el procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objetos, vea [procesamiento multidimensional del objeto de modelo](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="76b90-142">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
## <a name="specifying-objects-to-be-processed"></a><span data-ttu-id="76b90-143">Especificar los objetos que se van a procesar</span><span class="sxs-lookup"><span data-stu-id="76b90-143">Specifying Objects to be Processed</span></span>  
 <span data-ttu-id="76b90-144">La propiedad de [objeto](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `Process` comando contiene el identificador de objeto del objeto que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="76b90-144">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Process` command contains the object identifier of the object to be processed.</span></span> <span data-ttu-id="76b90-145">En un comando `Process` solamente puede especificarse un objeto, si bien al procesar un objeto también se procesan sus objetos secundarios.</span><span class="sxs-lookup"><span data-stu-id="76b90-145">Only one object can be specified in a `Process` command, but processing an object also processes any child objects.</span></span> <span data-ttu-id="76b90-146">Por ejemplo, al procesar un grupo de medida de un cubo se procesan todas las particiones de dicho grupo de medida, mientras que al procesar una base de datos se procesan todos los objetos contenidos en ésta (incluidos los cubos, las dimensiones y las estructuras de minería de datos).</span><span class="sxs-lookup"><span data-stu-id="76b90-146">For example, processing a measure group in a cube processes all the partitions for that measure group, while processing a database processes all the objects, including cubes, dimensions, and mining structures, that are contained by the database.</span></span>  
  
 <span data-ttu-id="76b90-147">Si establece el atributo `ProcessAffectedObjects` del comando `Process` en true, también se procesa cualquier objeto relacionado afectado por el procesamiento del objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="76b90-147">If you set the `ProcessAffectedObjects` attribute of the `Process` command to true, any related object affected by processing the specified object is also processed.</span></span> <span data-ttu-id="76b90-148">Por ejemplo, si una dimensión se actualiza de forma incremental mediante la opción de procesamiento *ProcessUpdate* del `Process` comando, cualquier partición cuyas agregaciones se invaliden debido a la adición o eliminación de miembros también la procesa [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] si `ProcessAffectedObjects` se establece en true.</span><span class="sxs-lookup"><span data-stu-id="76b90-148">For example, if a dimension is incrementally updated by using the *ProcessUpdate* processing option in the `Process` command, any partition whose aggregations are invalidated because of members being added or deleted is also processed by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] if `ProcessAffectedObjects` is set to true.</span></span> <span data-ttu-id="76b90-149">En este caso, un único comando `Process` puede procesar varios objetos de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], si bien [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determina qué objetos deberán procesarse además del objeto único especificado en el comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="76b90-149">In this case, a single `Process` command can process multiple objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, but [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines which objects besides the single object specified in the `Process` command must also be processed.</span></span>  
  
 <span data-ttu-id="76b90-150">No obstante, puede procesar diversos objetos (como dimensiones) al mismo tiempo si utiliza varios comandos `Process` dentro de un comando `Batch`.</span><span class="sxs-lookup"><span data-stu-id="76b90-150">However, you can process multiple objects, such as dimensions, at the same time by using multiple `Process` commands within a `Batch` command.</span></span> <span data-ttu-id="76b90-151">Las operaciones por lotes proporcionan un control más preciso para el procesamiento en serie o en paralelo de los objetos de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que el uso del atributo `ProcessAffectedObjects`; además, permiten optimizar el enfoque del procesamiento para bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="76b90-151">Batch operations provide a finer level of control for serial or parallel processing of objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance than using the `ProcessAffectedObjects` attribute, and let you to tune your processing approach for larger [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="76b90-152">Para obtener más información sobre cómo realizar operaciones por lotes, vea [realizar operaciones por lotes &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="76b90-152">For more information about performing batch operations, see [Performing Batch Operations &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span></span>  
  
## <a name="specifying-out-of-line-bindings"></a><span data-ttu-id="76b90-153">Especificar enlaces fuera de línea</span><span class="sxs-lookup"><span data-stu-id="76b90-153">Specifying Out-of-Line Bindings</span></span>  
 <span data-ttu-id="76b90-154">Si el `Process` comando no está incluido en un `Batch` comando, opcionalmente puede especificar enlaces fuera de línea en las propiedades [bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)y [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) del `Process` comando para los objetos que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="76b90-154">If the `Process` command is not contained by a `Batch` command, you can optionally specify out-of-line bindings in the [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla), and [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) properties of the `Process` command for the objects to be processed.</span></span> <span data-ttu-id="76b90-155">Los enlaces fuera de línea son referencias a orígenes de datos, vistas del origen de datos y otros objetos en los que el enlace existe solamente durante la ejecución del comando `Process` y que invalidan cualquier enlace existente asociado a los objetos que se procesan.</span><span class="sxs-lookup"><span data-stu-id="76b90-155">Out-of-line bindings are references to data sources, data source views, and other objects in which the binding exists only during the execution of the `Process` command, and which override any existing bindings associated with the objects being processed.</span></span> <span data-ttu-id="76b90-156">Si no se especifican enlaces fuera de línea, se utilizan los enlaces actualmente asociados a los objetos que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="76b90-156">If out-of-line bindings are not specified, the bindings currently associated with the objects to be processed are used.</span></span>  
  
 <span data-ttu-id="76b90-157">Los enlaces fuera de línea se utilizan en las circunstancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="76b90-157">Out-of-line bindings are used in the following circumstances:</span></span>  
  
-   <span data-ttu-id="76b90-158">Procesamiento incremental de una partición, donde debe especificarse una tabla de hechos alternativa o aplicarse un filtro a la tabla de hechos existente para asegurarse de que las filas no se cuentan dos veces.</span><span class="sxs-lookup"><span data-stu-id="76b90-158">Incrementally processing a partition, in which an alternative fact table or a filter on the existing fact table must be specified to make sure that rows are not counted twice.</span></span>  
  
-   <span data-ttu-id="76b90-159">Usar una tarea flujo de datos en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para proporcionar datos mientras se procesa una dimensión, un modelo de minería de datos o una partición.</span><span class="sxs-lookup"><span data-stu-id="76b90-159">Using a data flow task in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to provide data while processing a dimension, mining model, or partition.</span></span>  
  
 <span data-ttu-id="76b90-160">Los enlaces fuera de línea se describen como parte de Analysis Services Scripting Language (ASSL).</span><span class="sxs-lookup"><span data-stu-id="76b90-160">Out-of-line bindings are described as part of the Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="76b90-161">Para obtener más información sobre los enlaces fuera de línea en ASSL, vea [orígenes de datos y enlaces &#40;&#41;SSAS multidimensionales ](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="76b90-161">For more information about out-of-line bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span></span>  
  
### <a name="incrementally-updating-partitions"></a><span data-ttu-id="76b90-162">Actualizar particiones de forma incremental</span><span class="sxs-lookup"><span data-stu-id="76b90-162">Incrementally Updating Partitions</span></span>  
 <span data-ttu-id="76b90-163">La actualización incremental de una partición ya procesada suele requerir un enlace fuera de línea, ya que el enlace especificado para la partición hace referencia a datos de la tabla de hechos ya agregados en la partición.</span><span class="sxs-lookup"><span data-stu-id="76b90-163">Incrementally updating an already processed partition typically requires an out-of-line binding because the binding specified for the partition references fact table data already aggregated within the partition.</span></span> <span data-ttu-id="76b90-164">Al actualizar incrementalmente una partición ya procesada mediante el comando `Process`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="76b90-164">When incrementally updating an already processed partition by using the `Process` command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] performs the following actions:</span></span>  
  
-   <span data-ttu-id="76b90-165">Crea una partición temporal con una estructura idéntica a la de la partición que se va a actualizar incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="76b90-165">Creates a temporary partition with a structure identical to that of the partition to be incrementally updated.</span></span>  
  
-   <span data-ttu-id="76b90-166">Procesa la partición temporal, utilizando el enlace fuera de línea especificado en el comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="76b90-166">Processes the temporary partition, using the out-of-line binding specified in the `Process` command.</span></span>  
  
-   <span data-ttu-id="76b90-167">Mezcla la partición temporal con la partición existente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="76b90-167">Merges the temporary partition with the existing selected partition.</span></span>  
  
 <span data-ttu-id="76b90-168">Para obtener más información acerca de cómo mezclar particiones mediante XML for Analysis (XMLA), consulte [mezclar particiones &#40;&#41;XMLA ](merging-partitions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="76b90-168">For more information about merging partitions using XML for Analysis (XMLA), see [Merging Partitions &#40;XMLA&#41;](merging-partitions-xmla.md).</span></span>  
  
## <a name="handling-processing-errors"></a><span data-ttu-id="76b90-169">Controlar los errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="76b90-169">Handling Processing Errors</span></span>  
 <span data-ttu-id="76b90-170">La propiedad [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) del `Process` comando permite especificar cómo controlar los errores encontrados durante el procesamiento de un objeto.</span><span class="sxs-lookup"><span data-stu-id="76b90-170">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property of the `Process` command lets you specify how to handle errors encountered while processing an object.</span></span> <span data-ttu-id="76b90-171">Por ejemplo, durante el procesamiento de una dimensión, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encuentra un valor duplicado en la columna de clave del atributo clave.</span><span class="sxs-lookup"><span data-stu-id="76b90-171">For example, while processing a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encounters a duplicate value in the key column of the key attribute.</span></span> <span data-ttu-id="76b90-172">Dado que las claves de atributo deben ser únicas, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] descarta los registros duplicados.</span><span class="sxs-lookup"><span data-stu-id="76b90-172">Because attribute keys must be unique, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] discards the duplicate records.</span></span> <span data-ttu-id="76b90-173">En función de la propiedad [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) de `ErrorConfiguration` , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] podría:</span><span class="sxs-lookup"><span data-stu-id="76b90-173">Based on the [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) property of `ErrorConfiguration`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] could:</span></span>  
  
-   <span data-ttu-id="76b90-174">Omitir el error y continuar el procesamiento de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="76b90-174">Ignore the error and continue processing the dimension.</span></span>  
  
-   <span data-ttu-id="76b90-175">Devolver un mensaje que indique que [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encontró una clave duplicada y continuar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="76b90-175">Return a message that states [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encountered a duplicate key and continue processing.</span></span>  
  
 <span data-ttu-id="76b90-176">Hay muchas condiciones similares para las que `ErrorConfiguration` proporciona opciones durante la ejecución de un comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="76b90-176">There are many similar conditions for which `ErrorConfiguration` provides options during a `Process` command.</span></span>  
  
## <a name="managing-writeback-tables"></a><span data-ttu-id="76b90-177">Administrar tablas de reescritura</span><span class="sxs-lookup"><span data-stu-id="76b90-177">Managing Writeback Tables</span></span>  
 <span data-ttu-id="76b90-178">Si el comando `Process` encuentra una partición habilitada para escritura (o un cubo o grupo de medida para este tipo de partición) que aún no se haya procesado por completo, puede que aún no exista una tabla de reescritura para esa partición.</span><span class="sxs-lookup"><span data-stu-id="76b90-178">If the `Process` command encounters a write-enabled partition, or a cube or measure group for such a partition, that is not already fully processed, a writeback table may not already exist for that partition.</span></span> <span data-ttu-id="76b90-179">La propiedad [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) del `Process` comando determina si [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] debe crear una tabla de reescritura.</span><span class="sxs-lookup"><span data-stu-id="76b90-179">The [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) property of the `Process` command determines whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should create a writeback table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="76b90-180">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="76b90-180">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="76b90-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="76b90-181">Description</span></span>  
 <span data-ttu-id="76b90-182">En el ejemplo siguiente se procesa completamente la base de datos de ejemplo [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76b90-182">The following example fully processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="76b90-183">Código</span><span class="sxs-lookup"><span data-stu-id="76b90-183">Code</span></span>  
  
```  
<Process xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
  </Object>  
  <Type>ProcessFull</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
### <a name="description"></a><span data-ttu-id="76b90-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="76b90-184">Description</span></span>  
 <span data-ttu-id="76b90-185">En el ejemplo siguiente se procesa de forma incremental la partición **Internet_Sales_2004da** en el grupo de medida **Internet sales** del cubo **Adventure Works DW** en la [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] base de datos de ejemplo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76b90-185">The following example incrementally processes the **Internet_Sales_2004** partition in the **Internet Sales** measure group of the **Adventure Works DW** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="76b90-186">El `Process` comando agrega las agregaciones para las fechas de pedido posteriores al 31 de diciembre de 2006 a la partición mediante un enlace de consulta fuera de línea en la `Bindings` propiedad del `Process` comando para recuperar las filas de la tabla de hechos desde las que se van a generar agregaciones que se van a agregar a la partición.</span><span class="sxs-lookup"><span data-stu-id="76b90-186">The `Process` command is adding aggregations for order dates later than December 31, 2006 to the partition by using an out-of-line query binding in the `Bindings` property of the `Process` command to retrieve the fact table rows from which to generate aggregations to add to the partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="76b90-187">Código</span><span class="sxs-lookup"><span data-stu-id="76b90-187">Code</span></span>  
  
```  
<Process ProcessAffectedObjects="true" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2006</PartitionID>  
  </Object>  
  <Bindings>  
    <Binding>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2006</PartitionID>  
      <Source xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="QueryBinding">  
        <DataSourceID>Adventure Works DW</DataSourceID>  
        <QueryDefinition>  
          SELECT  
            [dbo].[FactInternetSales].[ProductKey],  
            [dbo].[FactInternetSales].[OrderDateKey],  
            [dbo].[FactInternetSales].[DueDateKey],  
            [dbo].[FactInternetSales].[ShipDateKey],   
            [dbo].[FactInternetSales].[CustomerKey],   
            [dbo].[FactInternetSales].[PromotionKey],  
            [dbo].[FactInternetSales].[CurrencyKey],  
            [dbo].[FactInternetSales].[SalesTerritoryKey],  
            [dbo].[FactInternetSales].[SalesOrderNumber],  
            [dbo].[FactInternetSales].[SalesOrderLineNumber],  
            [dbo].[FactInternetSales].[RevisionNumber],  
            [dbo].[FactInternetSales].[OrderQuantity],  
            [dbo].[FactInternetSales].[UnitPrice],  
            [dbo].[FactInternetSales].[ExtendedAmount],  
            [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
            [dbo].[FactInternetSales].[DiscountAmount],  
            [dbo].[FactInternetSales].[ProductStandardCost],  
            [dbo].[FactInternetSales].[TotalProductCost],  
            [dbo].[FactInternetSales].[SalesAmount],  
            [dbo].[FactInternetSales].[TaxAmt],  
            [dbo].[FactInternetSales].[Freight],  
            [dbo].[FactInternetSales].[CarrierTrackingNumber],  
            [dbo].[FactInternetSales].[CustomerPONumber]  
          FROM [dbo].[FactInternetSales]  
          WHERE OrderDateKey > '1280'  
        </QueryDefinition>  
      </Source>  
    </Binding>  
  </Bindings>  
  <Type>ProcessAdd</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
  
