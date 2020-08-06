---
title: Editor de la tarea consulta de minería de datos (pestaña consulta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.query.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 72b1755d-d226-46c5-b862-0c9333196a10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6005c92d0d48850461c01353ddf94c61140d0f2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748836"
---
# <a name="data-mining-query-task-editor-query-tab"></a><span data-ttu-id="d13d2-102">Editor de la tarea Consulta de minería de datos (pestaña Consulta)</span><span class="sxs-lookup"><span data-stu-id="d13d2-102">Data Mining Query Task Editor (Query Tab)</span></span>
  <span data-ttu-id="d13d2-103">Use la pestaña **Consulta** del cuadro de diálogo **Tarea Consulta de minería de datos** para crear consultas de predicción según un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d13d2-103">Use the **Query** tab of the **Data Mining Query Task** dialog box to create prediction queries based on a mining model.</span></span> <span data-ttu-id="d13d2-104">En este cuadro de diálogo también puede enlazar parámetros y conjuntos de resultados con variables.</span><span class="sxs-lookup"><span data-stu-id="d13d2-104">In this dialog box you can also bind parameters and result sets to variables.</span></span>  
  
 <span data-ttu-id="d13d2-105">Para obtener información sobre cómo implementar la minería de datos en paquetes, vea [Tarea Consulta de minería de datos](control-flow/data-mining-query-task.md) y [Soluciones de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="d13d2-105">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="d13d2-106">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="d13d2-106">General Options</span></span>  
 <span data-ttu-id="d13d2-107">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d13d2-107">**Name**</span></span>  
 <span data-ttu-id="d13d2-108">Escriba un nombre único para la tarea Consulta de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d13d2-108">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="d13d2-109">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="d13d2-109">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d13d2-110">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="d13d2-110">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="d13d2-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d13d2-111">**Description**</span></span>  
 <span data-ttu-id="d13d2-112">Escriba una descripción de la tarea Consulta de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d13d2-112">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="build-query-tab-options"></a><span data-ttu-id="d13d2-113">Opciones de la pestaña Generar consulta</span><span class="sxs-lookup"><span data-stu-id="d13d2-113">Build Query Tab Options</span></span>  
 <span data-ttu-id="d13d2-114">**Consulta de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="d13d2-114">**Data mining query**</span></span>  
 <span data-ttu-id="d13d2-115">Escriba una consulta de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d13d2-115">Type a data mining query.</span></span>  
  
 <span data-ttu-id="d13d2-116">**Temas relacionados:**  [Referencia de Extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/data-mining-extensions-dmx-reference)</span><span class="sxs-lookup"><span data-stu-id="d13d2-116">**Related Topics:**  [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference)</span></span>  
  
 <span data-ttu-id="d13d2-117">**Generar nueva consulta**</span><span class="sxs-lookup"><span data-stu-id="d13d2-117">**Build New Query**</span></span>  
 <span data-ttu-id="d13d2-118">Cree la consulta de minería de datos con una herramienta gráfica.</span><span class="sxs-lookup"><span data-stu-id="d13d2-118">Create the data mining query using a graphical tool.</span></span>  
  
 <span data-ttu-id="d13d2-119">**Temas relacionados:** [Data Mining Query](control-flow/data-mining-query.md)</span><span class="sxs-lookup"><span data-stu-id="d13d2-119">**Related Topics:** [Data Mining Query](control-flow/data-mining-query.md)</span></span>  
  
## <a name="parameter-mapping-tab-options"></a><span data-ttu-id="d13d2-120">Opciones de la pestaña Asignación de parámetros</span><span class="sxs-lookup"><span data-stu-id="d13d2-120">Parameter Mapping Tab Options</span></span>  
 <span data-ttu-id="d13d2-121">**Nombre de parámetro**</span><span class="sxs-lookup"><span data-stu-id="d13d2-121">**Parameter Name**</span></span>  
 <span data-ttu-id="d13d2-122">Opcionalmente, actualice el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d13d2-122">Optionally, update the parameter name.</span></span> <span data-ttu-id="d13d2-123">Para asignar el parámetro a una variable, seleccione una variable de la lista **Nombre de variable** .</span><span class="sxs-lookup"><span data-stu-id="d13d2-123">Map the parameter to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="d13d2-124">**Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="d13d2-124">**Variable Name**</span></span>  
 <span data-ttu-id="d13d2-125">Seleccione una variable de la lista para asignarla al parámetro.</span><span class="sxs-lookup"><span data-stu-id="d13d2-125">Select a variable in the list to map it to the parameter.</span></span>  
  
 <span data-ttu-id="d13d2-126">**Add**</span><span class="sxs-lookup"><span data-stu-id="d13d2-126">**Add**</span></span>  
 <span data-ttu-id="d13d2-127">Agregue un parámetro a la lista.</span><span class="sxs-lookup"><span data-stu-id="d13d2-127">Add to a parameter to the list.</span></span>  
  
 <span data-ttu-id="d13d2-128">**Remove**</span><span class="sxs-lookup"><span data-stu-id="d13d2-128">**Remove**</span></span>  
 <span data-ttu-id="d13d2-129">Seleccione un parámetro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="d13d2-129">Select a parameter, and then click **Remove**.</span></span>  
  
## <a name="result-set-tab-options"></a><span data-ttu-id="d13d2-130">Opciones de la pestaña Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="d13d2-130">Result Set Tab Options</span></span>  
 <span data-ttu-id="d13d2-131">**Nombre del resultado**</span><span class="sxs-lookup"><span data-stu-id="d13d2-131">**Result Name**</span></span>  
 <span data-ttu-id="d13d2-132">Opcionalmente, actualice el nombre del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d13d2-132">Optionally, update the result set name.</span></span> <span data-ttu-id="d13d2-133">Para asignar el resultado a una variable, seleccione una variable de la lista **Nombre de variable** .</span><span class="sxs-lookup"><span data-stu-id="d13d2-133">Map the result to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="d13d2-134">Para agregar un resultado, haga clic en **Agregar**y escriba un nombre único para el resultado.</span><span class="sxs-lookup"><span data-stu-id="d13d2-134">After you have added a result by clicking **Add**, provide a unique name for the result.</span></span>  
  
 <span data-ttu-id="d13d2-135">**Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="d13d2-135">**Variable Name**</span></span>  
 <span data-ttu-id="d13d2-136">Seleccione una variable de la lista para asignarla al conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d13d2-136">Select a variable in the list to map it to the result set.</span></span>  
  
 <span data-ttu-id="d13d2-137">**Tipo de resultado**</span><span class="sxs-lookup"><span data-stu-id="d13d2-137">**Result Type**</span></span>  
 <span data-ttu-id="d13d2-138">Indique si desea devolver una fila única o un conjunto de resultados completo.</span><span class="sxs-lookup"><span data-stu-id="d13d2-138">Indicate whether to return a single row or a full result set.</span></span>  
  
 <span data-ttu-id="d13d2-139">**Add**</span><span class="sxs-lookup"><span data-stu-id="d13d2-139">**Add**</span></span>  
 <span data-ttu-id="d13d2-140">Agregue un conjunto de resultados a la lista.</span><span class="sxs-lookup"><span data-stu-id="d13d2-140">Add a result set to the list.</span></span>  
  
 <span data-ttu-id="d13d2-141">**Remove**</span><span class="sxs-lookup"><span data-stu-id="d13d2-141">**Remove**</span></span>  
 <span data-ttu-id="d13d2-142">Seleccione un resultado y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="d13d2-142">Select a result, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13d2-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d13d2-143">See Also</span></span>  
 <span data-ttu-id="d13d2-144">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d13d2-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d13d2-145">[Editor de la tarea consulta de minería de datos &#40;pestaña modelo de minería de datos&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="d13d2-145">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="d13d2-146">[Editor de la tarea consulta de minería de datos &#40;pestaña salida&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="d13d2-146">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="d13d2-147">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="d13d2-147">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
