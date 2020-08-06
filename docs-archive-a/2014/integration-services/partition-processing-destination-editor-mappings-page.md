---
title: Editor de destino de procesamiento de particiones (página asignaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.mapping.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: e75b766c-85ba-453e-9576-4a1a34f91ecc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3855b15c7ebf1f6fa95c941931869064d552680e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676570"
---
# <a name="partition-processing-destination-editor-mappings-page"></a><span data-ttu-id="59d6a-102">Editor de destino de procesamiento de particiones (página Asignaciones)</span><span class="sxs-lookup"><span data-stu-id="59d6a-102">Partition Processing Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="59d6a-103">Utilice la página **Asignaciones** del cuadro de diálogo **Editor de destino de procesamiento de particiones** para asignar columnas de entrada a columnas de partición.</span><span class="sxs-lookup"><span data-stu-id="59d6a-103">Use the **Mappings** page of the **Partition Processing Destination Editor** dialog box to map input columns to partition columns.</span></span>  
  
 <span data-ttu-id="59d6a-104">Para obtener más información acerca del destino de procesamiento de particiones, vea [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="59d6a-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59d6a-105">Las tareas aquí descritas no se aplican a los modelos tabulares de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="59d6a-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="59d6a-106">No se pueden asignar las columnas de entrada a las de partición para los modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="59d6a-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="59d6a-107">En su lugar puede usar la tarea Ejecutar DDL de Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) para procesar la partición.</span><span class="sxs-lookup"><span data-stu-id="59d6a-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="59d6a-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="59d6a-108">Options</span></span>  
 <span data-ttu-id="59d6a-109">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="59d6a-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="59d6a-110">Muestra la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="59d6a-110">View the list of available input columns.</span></span> <span data-ttu-id="59d6a-111">Utilice una operación de arrastrar y colocar para asignar columnas de entrada disponibles de la tabla a columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="59d6a-111">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="59d6a-112">**Columnas de destino disponibles**</span><span class="sxs-lookup"><span data-stu-id="59d6a-112">**Available Destination Columns**</span></span>  
 <span data-ttu-id="59d6a-113">Muestra la lista de columnas de destino disponibles.</span><span class="sxs-lookup"><span data-stu-id="59d6a-113">View the list of available destination columns.</span></span> <span data-ttu-id="59d6a-114">Utilice una operación de arrastrar y colocar para asignar columnas de destino disponibles de la tabla a columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="59d6a-114">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="59d6a-115">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="59d6a-115">**Input Column**</span></span>  
 <span data-ttu-id="59d6a-116">Muestra las columnas de entrada seleccionadas de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="59d6a-116">View input columns selected from the table above.</span></span> <span data-ttu-id="59d6a-117">Puede cambiar las asignaciones utilizando la lista de **Columnas de entrada disponibles**.</span><span class="sxs-lookup"><span data-stu-id="59d6a-117">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="59d6a-118">**Columna de destino**</span><span class="sxs-lookup"><span data-stu-id="59d6a-118">**Destination Column**</span></span>  
 <span data-ttu-id="59d6a-119">Muestra las columnas de destino disponibles, independientemente de si están asignadas o no.</span><span class="sxs-lookup"><span data-stu-id="59d6a-119">View each available destination column, whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d6a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59d6a-120">See Also</span></span>  
 <span data-ttu-id="59d6a-121">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="59d6a-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="59d6a-122">[Editor de destino de procesamiento de particiones &#40;página Administrador de conexiones&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="59d6a-122">[Partition Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="59d6a-123">Editor de destino de procesamiento de particiones &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="59d6a-123">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
