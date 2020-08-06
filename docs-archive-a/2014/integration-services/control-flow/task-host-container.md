---
title: Contenedor del host de la tarea | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.taskhostcontainer.f1
helpviewer_keywords:
- containers [Integration Services], Task Host
- Task Host container
ms.assetid: 7394a2c2-1b07-427d-b94a-9792e7783d35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4429d564cea0f08d5c2408199a8f1837b38389b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676117"
---
# <a name="task-host-container"></a><span data-ttu-id="4f0d3-102">contenedor de tarea</span><span class="sxs-lookup"><span data-stu-id="4f0d3-102">Task Host Container</span></span>
  <span data-ttu-id="4f0d3-103">El contenedor del host de la tarea encapsula una tarea individual.</span><span class="sxs-lookup"><span data-stu-id="4f0d3-103">The task host container encapsulates a single task.</span></span> <span data-ttu-id="4f0d3-104">En el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , el host de la tarea no se configura por separado, sino al establecer las propiedades de la tarea que encapsula.</span><span class="sxs-lookup"><span data-stu-id="4f0d3-104">In [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the task host is not configured separately; instead, it is configured when you set the properties of the task it encapsulates.</span></span> <span data-ttu-id="4f0d3-105">Para obtener más información sobre las tareas encapsuladas por los contenedores del host de la tarea, vea [Integration Services Tasks](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="4f0d3-105">For more information about the tasks that the task host containers encapsulate, see [Integration Services Tasks](integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="4f0d3-106">Este contenedor extiende el uso las de variables y los controladores de eventos al nivel de tarea.</span><span class="sxs-lookup"><span data-stu-id="4f0d3-106">This container extends the use of variables and event handlers to the task level.</span></span> <span data-ttu-id="4f0d3-107">Para obtener más información, vea [Controladores de eventos de Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) y [Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="4f0d3-107">For more information, see [Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="configuration-of-the-task-host"></a><span data-ttu-id="4f0d3-108">Configuración del host de la tarea</span><span class="sxs-lookup"><span data-stu-id="4f0d3-108">Configuration of the Task Host</span></span>  
 <span data-ttu-id="4f0d3-109">Puede establecer propiedades en la ventana **Propiedades** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4f0d3-109">You can set properties in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="4f0d3-110">Para obtener información sobre cómo establecer estas propiedades en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vea [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="4f0d3-110">For information about setting these properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="4f0d3-111">Para obtener información sobre cómo establecer mediante programación estas propiedades, vea <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="4f0d3-111">For information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4f0d3-112">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4f0d3-112">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4f0d3-113">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="4f0d3-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f0d3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f0d3-114">See Also</span></span>  
 [<span data-ttu-id="4f0d3-115">Contenedores de Integration Services</span><span class="sxs-lookup"><span data-stu-id="4f0d3-115">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
