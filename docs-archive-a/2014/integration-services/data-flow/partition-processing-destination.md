---
title: Destino de procesamiento de particiones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partitionprocessingdest.f1
helpviewer_keywords:
- partitions [Analysis Services], processing
- Partition Processing destination [Integration Services]
- destinations [Integration Services], Partition Processing
ms.assetid: 36c592ff-3f78-4a58-b496-31c1c8eee131
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d32306328f7a0575e55397d5209b4767d0cf1bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670467"
---
# <a name="partition-processing-destination"></a><span data-ttu-id="ea939-102">Destino de procesamiento de particiones</span><span class="sxs-lookup"><span data-stu-id="ea939-102">Partition Processing Destination</span></span>
  <span data-ttu-id="ea939-103">El destino de procesamiento de particiones carga y procesa una partición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea939-103">The Partition Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partition.</span></span> <span data-ttu-id="ea939-104">Para más información sobre particiones, vea [Particiones &#40;Analysis Services - Datos multidimensionales&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="ea939-104">For more information about partitions, see [Partitions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="ea939-105">El destino de procesamiento de particiones incluye las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="ea939-105">The Partition Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="ea939-106">Opciones para ejecutar procesamiento incremental, completo o de actualización.</span><span class="sxs-lookup"><span data-stu-id="ea939-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="ea939-107">Configuración de errores, para especificar si el procesamiento debe omitir los errores o detenerse después de una cantidad de errores especificada.</span><span class="sxs-lookup"><span data-stu-id="ea939-107">Error configuration, to specify whether processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="ea939-108">Asignación de columnas de entrada para columnas de particiones.</span><span class="sxs-lookup"><span data-stu-id="ea939-108">Mapping of input columns to partition columns.</span></span>  
  
 <span data-ttu-id="ea939-109">Para más información sobre el procesamiento de objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vea [Opciones y valores de procesamiento &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="ea939-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea939-110">Las tareas aquí descritas no se aplican a los modelos tabulares de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ea939-110">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="ea939-111">No se pueden asignar las columnas de entrada a las de partición para los modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="ea939-111">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="ea939-112">En su lugar puede usar la tarea Ejecutar DDL de Analysis Services [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) para procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="ea939-112">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="configuration-of-the-partition-processing-destination"></a><span data-ttu-id="ea939-113">Configuración del destino de procesamiento de particiones</span><span class="sxs-lookup"><span data-stu-id="ea939-113">Configuration of the Partition Processing Destination</span></span>  
 <span data-ttu-id="ea939-114">El destino de procesamiento de particiones usa un administrador de conexiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para conectarse al proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene los cubos y particiones que procesa el destino.</span><span class="sxs-lookup"><span data-stu-id="ea939-114">The Partition Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the cubes and partitions the destination processes.</span></span> <span data-ttu-id="ea939-115">Para más información, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ea939-115">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="ea939-116">Este destino tiene una entrada.</span><span class="sxs-lookup"><span data-stu-id="ea939-116">This destination has one input.</span></span> <span data-ttu-id="ea939-117">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="ea939-117">It does not support an error output.</span></span>  
  
 <span data-ttu-id="ea939-118">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="ea939-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ea939-119">Para obtener más información sobre las propiedades que se pueden configurar en el cuadro de diálogo **Editor de destino de procesamiento de particiones** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="ea939-119">For more information about the properties that you can set in the Partition Processing **Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ea939-120">Editor de destino de procesamiento de particiones &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="ea939-120">Partition Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../partition-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="ea939-121">Editor de destino de procesamiento de particiones &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="ea939-121">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../partition-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="ea939-122">Editor de destino de procesamiento de particiones &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="ea939-122">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../partition-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="ea939-123">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="ea939-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="ea939-124">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ea939-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ea939-125">Common Properties</span><span class="sxs-lookup"><span data-stu-id="ea939-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="ea939-126">Propiedades personalizadas del destino de procesamiento de particiones</span><span class="sxs-lookup"><span data-stu-id="ea939-126">Partition Processing Destination Custom Properties</span></span>](partition-processing-destination-custom-properties.md)  
  
 <span data-ttu-id="ea939-127">Para más información sobre cómo establecer las propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ea939-127">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
