---
title: Editor de destino de procesamiento de particiones (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a0f79dfcc9c0d98d871a49618f4dabfb8a3bbac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672156"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="bc866-102">Editor de destino de procesamiento de particiones (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="bc866-102">Partition Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="bc866-103">Use la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de procesamiento de particiones** para especificar una conexión a un proyecto de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc866-103">Use the **Connection Manager** page of the **Partition Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bc866-104">Para obtener más información acerca del destino de procesamiento de particiones, vea [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="bc866-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc866-105">Las tareas aquí descritas no se aplican a los modelos tabulares de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bc866-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="bc866-106">No se pueden asignar las columnas de entrada a las de partición para los modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="bc866-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="bc866-107">En su lugar puede usar la tarea Ejecutar DDL de Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) para procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="bc866-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc866-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="bc866-108">Options</span></span>  
 <span data-ttu-id="bc866-109">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="bc866-109">**Connection manager**</span></span>  
 <span data-ttu-id="bc866-110">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bc866-110">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="bc866-111">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="bc866-111">**New**</span></span>  
 <span data-ttu-id="bc866-112">Permite crear una conexión con el cuadro de diálogo **Agregar administrador de conexiones de Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="bc866-112">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="bc866-113">**Lista de particiones disponibles**</span><span class="sxs-lookup"><span data-stu-id="bc866-113">**List of available partitions**</span></span>  
 <span data-ttu-id="bc866-114">Seleccione la partición para procesar.</span><span class="sxs-lookup"><span data-stu-id="bc866-114">Select the partition to process.</span></span>  
  
 <span data-ttu-id="bc866-115">**Método de procesamiento**</span><span class="sxs-lookup"><span data-stu-id="bc866-115">**Processing method**</span></span>  
 <span data-ttu-id="bc866-116">Seleccione el método de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="bc866-116">Select the processing method.</span></span> <span data-ttu-id="bc866-117">El valor predeterminado de esta opción es **Completa**.</span><span class="sxs-lookup"><span data-stu-id="bc866-117">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="bc866-118">Value</span><span class="sxs-lookup"><span data-stu-id="bc866-118">Value</span></span>|<span data-ttu-id="bc866-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc866-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc866-120">Agregar (incremental)</span><span class="sxs-lookup"><span data-stu-id="bc866-120">Add (incremental)</span></span>|<span data-ttu-id="bc866-121">Realiza un procesamiento incremental de la partición.</span><span class="sxs-lookup"><span data-stu-id="bc866-121">Perform an incremental processing of the partition.</span></span>|  
|<span data-ttu-id="bc866-122">Completo</span><span class="sxs-lookup"><span data-stu-id="bc866-122">Full</span></span>|<span data-ttu-id="bc866-123">Realiza un procesamiento completo de la partición.</span><span class="sxs-lookup"><span data-stu-id="bc866-123">Perform full processing of the partition.</span></span>|  
|<span data-ttu-id="bc866-124">Solo datos</span><span class="sxs-lookup"><span data-stu-id="bc866-124">Data only</span></span>|<span data-ttu-id="bc866-125">Realiza un procesamiento de actualización de la partición.</span><span class="sxs-lookup"><span data-stu-id="bc866-125">Perform an update processing of the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc866-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc866-126">See Also</span></span>  
 <span data-ttu-id="bc866-127">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bc866-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bc866-128">[&#40;página asignaciones del editor de destino de procesamiento de particiones&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="bc866-128">[Partition Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="bc866-129">Editor de destino de procesamiento de particiones &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="bc866-129">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
