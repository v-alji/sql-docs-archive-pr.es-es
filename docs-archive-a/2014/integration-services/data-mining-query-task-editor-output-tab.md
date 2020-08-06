---
title: Editor de la tarea consulta de minería de datos (pestaña salida) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.output.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 62f9e015-6fe0-4396-ad90-3ad51bf00025
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1508972b0487daa90f52af723d58185944a19a58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748838"
---
# <a name="data-mining-query-task-editor-output-tab"></a><span data-ttu-id="dbbc8-102">Editor de la tarea Consulta de minería de datos (pestaña Salida)</span><span class="sxs-lookup"><span data-stu-id="dbbc8-102">Data Mining Query Task Editor (Output Tab)</span></span>
  <span data-ttu-id="dbbc8-103">Use la pestaña **Salida** del cuadro de diálogo **Editor de la tarea Consulta de minería de datos** para especificar el destino de la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-103">Use the **Output** tab of the **Data Mining Query Task Editor** dialog box to specify the destination of the prediction query.</span></span>  
  
 <span data-ttu-id="dbbc8-104">Para obtener información sobre cómo implementar la minería de datos en paquetes, vea [Tarea Consulta de minería de datos](control-flow/data-mining-query-task.md) y [Soluciones de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="dbbc8-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="dbbc8-105">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="dbbc8-105">General Options</span></span>  
 <span data-ttu-id="dbbc8-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dbbc8-106">**Name**</span></span>  
 <span data-ttu-id="dbbc8-107">Escriba un nombre único para la tarea Consulta de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="dbbc8-108">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbbc8-109">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="dbbc8-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dbbc8-110">**Description**</span></span>  
 <span data-ttu-id="dbbc8-111">Escriba una descripción de la tarea Consulta de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="output-tab-options"></a><span data-ttu-id="dbbc8-112">Opciones de la pestaña Salida</span><span class="sxs-lookup"><span data-stu-id="dbbc8-112">Output Tab Options</span></span>  
 <span data-ttu-id="dbbc8-113">**Connection**</span><span class="sxs-lookup"><span data-stu-id="dbbc8-113">**Connection**</span></span>  
 <span data-ttu-id="dbbc8-114">Seleccione un administrador de conexiones de la lista o haga clic en **Nuevo** para crear uno.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-114">Select a connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="dbbc8-115">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="dbbc8-115">**New**</span></span>  
 <span data-ttu-id="dbbc8-116">Cree un administrador de conexiones nuevo.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-116">Create a new connection manager.</span></span> <span data-ttu-id="dbbc8-117">Solo se pueden usar los tipos de administrador de conexiones ADO.NET y OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-117">Only the ADO.NET and OLE DB connection manager types can be used.</span></span>  
  
 <span data-ttu-id="dbbc8-118">**Tabla de salida**</span><span class="sxs-lookup"><span data-stu-id="dbbc8-118">**Output table**</span></span>  
 <span data-ttu-id="dbbc8-119">Especifique la tabla en la que la consulta de predicción escribe los resultados.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-119">Specify the table to which the prediction query writes its results.</span></span>  
  
 <span data-ttu-id="dbbc8-120">**Quitar y volver a crear la tabla de salida**</span><span class="sxs-lookup"><span data-stu-id="dbbc8-120">**Drop and re-create the output table**</span></span>  
 <span data-ttu-id="dbbc8-121">Indica si la consulta de predicción debe sobrescribir el contenido de la tabla de destino quitando y volviendo a crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="dbbc8-121">Indicate whether the prediction query should overwrite content in the destination table by dropping and then re-creating the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbbc8-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbbc8-122">See Also</span></span>  
 <span data-ttu-id="dbbc8-123">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dbbc8-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="dbbc8-124">[Editor de la tarea consulta de minería de datos &#40;pestaña modelo de minería de datos&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="dbbc8-124">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="dbbc8-125">[Editor de la tarea consulta de minería de datos &#40;pestaña consulta&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="dbbc8-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 [<span data-ttu-id="dbbc8-126">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="dbbc8-126">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
