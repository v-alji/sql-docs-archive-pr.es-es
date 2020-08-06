---
title: Editor de la tarea de procesamiento de Analysis Services (página Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.as.f1
helpviewer_keywords:
- Analysis Services Processing Task Editor
ms.assetid: 5612be78-57cf-4e4e-92cf-6bfa9f971040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aabcfe286b40f58b429227654107d58e8a4ee837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670518"
---
# <a name="analysis-services-processing-task-editor-analysis-services-page"></a><span data-ttu-id="dafd5-102">Editor de la tarea de procesamiento de Analysis Services (página Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="dafd5-102">Analysis Services Processing Task Editor (Analysis Services Page)</span></span>
  <span data-ttu-id="dafd5-103">Utilice la página **Analysis Services** del cuadro de diálogo **Editor de la tarea de procesamiento de Analysis Services** para especificar un administrador de conexiones de Analysis Services, seleccionar los objetos analíticos que se deben procesar y establecer opciones de procesamiento y control de errores.</span><span class="sxs-lookup"><span data-stu-id="dafd5-103">Use the **Analysis Services** page of the **Analysis Services Processing Task Editor** dialog box to specify an Analysis Services connection manager, select the analytic objects to process, and set processing and error handling options.</span></span>  
  
 <span data-ttu-id="dafd5-104">Al procesar modelos tabulares, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dafd5-104">When processing tabular models, keep the following in mind:</span></span>  
  
1.  <span data-ttu-id="dafd5-105">No puede realizar análisis de impacto en modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="dafd5-105">You cannot perform impact analysis on tabular models.</span></span>  
  
2.  <span data-ttu-id="dafd5-106">Algunas opciones de procesamiento para el modo tabular no están expuestas como, por ejemplo, el proceso de desfragmentación y el proceso de recálculo.</span><span class="sxs-lookup"><span data-stu-id="dafd5-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="dafd5-107">Puede llevar a cabo estas funciones mediante la tarea Ejecutar DDL.</span><span class="sxs-lookup"><span data-stu-id="dafd5-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
3.  <span data-ttu-id="dafd5-108">Algunas opciones de procesamiento proporcionadas, como índices de proceso, no son adecuadas para los modelos tabulares y no deben utilizarse.</span><span class="sxs-lookup"><span data-stu-id="dafd5-108">Some processing options provided, such as process indexes, are not appropriate for tabular models and should not be used.</span></span>  
  
4.  <span data-ttu-id="dafd5-109">Los valores de las operaciones por lotes se omiten para los modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="dafd5-109">Batch settings are ignored for tabular models.</span></span>  
  
 <span data-ttu-id="dafd5-110">Para obtener información acerca de esta tarea, vea [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="dafd5-110">To learn about this task, see [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dafd5-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="dafd5-111">Options</span></span>  
 <span data-ttu-id="dafd5-112">**Administrador de conexiones de Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="dafd5-112">**Analysis Services connection manager**</span></span>  
 <span data-ttu-id="dafd5-113">Seleccione un administrador de conexiones de Analysis Services de la lista o haga clic en **Nuevo** para crear uno.</span><span class="sxs-lookup"><span data-stu-id="dafd5-113">Select an existing Analysis Services connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="dafd5-114">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="dafd5-114">**New**</span></span>  
 <span data-ttu-id="dafd5-115">Cree un administrador de conexiones de Analysis Services nuevo.</span><span class="sxs-lookup"><span data-stu-id="dafd5-115">Create a new Analysis Services connection manager.</span></span>  
  
 <span data-ttu-id="dafd5-116">**Temas relacionados:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Referencia de la interfaz de usuario del cuadro de diálogo Agregar administrador de conexiones con Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="dafd5-116">**Related Topics:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="dafd5-117">**Lista de objetos**</span><span class="sxs-lookup"><span data-stu-id="dafd5-117">**Object list**</span></span>  
 |<span data-ttu-id="dafd5-118">Propiedad</span><span class="sxs-lookup"><span data-stu-id="dafd5-118">Property</span></span>|<span data-ttu-id="dafd5-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="dafd5-119">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="dafd5-120">**Nombre de objeto**</span><span class="sxs-lookup"><span data-stu-id="dafd5-120">**Object Name**</span></span>|<span data-ttu-id="dafd5-121">Enumera los nombres de los objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="dafd5-121">Lists the specified object names.</span></span>|  
|<span data-ttu-id="dafd5-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dafd5-122">**Type**</span></span>|<span data-ttu-id="dafd5-123">Enumera los tipos de los objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="dafd5-123">Lists the types of the specified objects.</span></span>|  
|<span data-ttu-id="dafd5-124">**Opciones de proceso**</span><span class="sxs-lookup"><span data-stu-id="dafd5-124">**Process Options**</span></span>|<span data-ttu-id="dafd5-125">Seleccione una opción de procesamiento de la lista.</span><span class="sxs-lookup"><span data-stu-id="dafd5-125">Select a processing option in the list.</span></span><br /><br /> <span data-ttu-id="dafd5-126">**Temas relacionados**: [procesamiento de objetos de modelo multidimensional](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span><span class="sxs-lookup"><span data-stu-id="dafd5-126">**Related Topics**: [Multidimensional Model Object Processing](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span></span>|  
|<span data-ttu-id="dafd5-127">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="dafd5-127">**Settings**</span></span>|<span data-ttu-id="dafd5-128">Enumera los valores de configuración de procesamiento para los objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="dafd5-128">Lists processing settings for the specified objects.</span></span>|  
  
 <span data-ttu-id="dafd5-129">**Add**</span><span class="sxs-lookup"><span data-stu-id="dafd5-129">**Add**</span></span>  
 <span data-ttu-id="dafd5-130">Agregue un objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a la lista.</span><span class="sxs-lookup"><span data-stu-id="dafd5-130">Add an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to the list.</span></span>  
  
 <span data-ttu-id="dafd5-131">**Remove**</span><span class="sxs-lookup"><span data-stu-id="dafd5-131">**Remove**</span></span>  
 <span data-ttu-id="dafd5-132">Seleccione un objeto y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="dafd5-132">Select an object, and then click **Delete**.</span></span>  
  
 <span data-ttu-id="dafd5-133">**Análisis de impacto**</span><span class="sxs-lookup"><span data-stu-id="dafd5-133">**Impact Analysis**</span></span>  
 <span data-ttu-id="dafd5-134">Lleve a cabo el análisis de impacto en el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dafd5-134">Perform impact analysis on the selected object.</span></span>  
  
 <span data-ttu-id="dafd5-135">**Temas relacionados:** [Cuadro de diálogo Análisis de impacto &#40;Analysis Services - Datos multidimensionales&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="dafd5-135">**Related Topics:** [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
 <span data-ttu-id="dafd5-136">**Resumen de configuración de lotes**</span><span class="sxs-lookup"><span data-stu-id="dafd5-136">**Batch Settings Summary**</span></span>  
 |<span data-ttu-id="dafd5-137">Propiedad</span><span class="sxs-lookup"><span data-stu-id="dafd5-137">Property</span></span>|<span data-ttu-id="dafd5-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="dafd5-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="dafd5-139">**Orden de procesamiento**</span><span class="sxs-lookup"><span data-stu-id="dafd5-139">**Processing order**</span></span>|<span data-ttu-id="dafd5-140">Especifica si los objetos se procesan de manera secuencial o en un lote; si se utiliza el procesamiento paralelo, especifica el número de objetos que se deben procesar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="dafd5-140">Specifies whether objects are processed sequentially or in a batch; if parallel processing is used, specifies the number of objects to process concurrently.</span></span>|  
|<span data-ttu-id="dafd5-141">**Modo de transacción**</span><span class="sxs-lookup"><span data-stu-id="dafd5-141">**Transaction mode**</span></span>|<span data-ttu-id="dafd5-142">Especifica el modo de transacción para el procesamiento secuencial.</span><span class="sxs-lookup"><span data-stu-id="dafd5-142">Specifies the transaction mode for sequential processing.</span></span>|  
|<span data-ttu-id="dafd5-143">**Errores de dimensión**</span><span class="sxs-lookup"><span data-stu-id="dafd5-143">**Dimension errors**</span></span>|<span data-ttu-id="dafd5-144">Especifica el comportamiento de la tarea cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="dafd5-144">Specifies the task behavior when errors occur.</span></span>|  
|<span data-ttu-id="dafd5-145">**Ruta del registro de errores de claves de dimensiones**</span><span class="sxs-lookup"><span data-stu-id="dafd5-145">**Dimension key error log path**</span></span>|<span data-ttu-id="dafd5-146">Especifica la ruta de acceso del archivo en el que se registran los errores.</span><span class="sxs-lookup"><span data-stu-id="dafd5-146">Specifies the path of the file to which errors are logged.</span></span>|  
|<span data-ttu-id="dafd5-147">**Procesar objetos afectados**</span><span class="sxs-lookup"><span data-stu-id="dafd5-147">**Process affected objects**</span></span>|<span data-ttu-id="dafd5-148">Indica si los objetos afectados o dependientes también se deben procesar.</span><span class="sxs-lookup"><span data-stu-id="dafd5-148">Indicates whether dependent or affected objects are also processed.</span></span>|  
  
 <span data-ttu-id="dafd5-149">**Cambiar configuración**</span><span class="sxs-lookup"><span data-stu-id="dafd5-149">**Change Settings**</span></span>  
 <span data-ttu-id="dafd5-150">Cambie las opciones de procesamiento y el control de errores en las claves de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="dafd5-150">Change the processing options and the handling of errors in dimension keys.</span></span>  
  
 <span data-ttu-id="dafd5-151">**Temas relacionados:** [Cuadro de diálogo Cambiar configuración &#40;Analysis Services - Datos multidimensionales&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="dafd5-151">**Related Topics:** [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dafd5-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dafd5-152">See Also</span></span>  
 <span data-ttu-id="dafd5-153">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dafd5-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="dafd5-154">[&#40;página general del editor de la tarea procesamiento de Analysis Services&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="dafd5-154">[Analysis Services Processing Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="dafd5-155">Tarea Ejecutar DDL de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dafd5-155">Analysis Services Execute DDL Task</span></span>](control-flow/analysis-services-execute-ddl-task.md)  
  
  
