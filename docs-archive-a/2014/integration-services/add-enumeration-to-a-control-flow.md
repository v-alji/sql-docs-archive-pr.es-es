---
title: Agregar enumeración a un flujo de control | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding enumerations
- Foreach Loop containers
- control flow [Integration Services], enumerations
- repeating workflows
- enumerations [Integration Services]
ms.assetid: f212b5fb-3cc4-422e-9b7c-89eb769a812a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59b8569880fdf1a49f5f2ca1f6841841f9790af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672242"
---
# <a name="add-enumeration-to-a-control-flow"></a><span data-ttu-id="bdea8-102">Agregar enumeración a un flujo de control</span><span class="sxs-lookup"><span data-stu-id="bdea8-102">Add Enumeration to a Control Flow</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="bdea8-103">incluye el contenedor de bucles Para cada uno, un elemento de flujo de control que simplifica la inclusión de una construcción de bucle que enumera archivos y objetos en el flujo de control de un paquete.</span><span class="sxs-lookup"><span data-stu-id="bdea8-103">includes the Foreach Loop container, a control flow element that makes it simple to include a looping construct that enumerates files and objects in the control flow of a package.</span></span> <span data-ttu-id="bdea8-104">Para más información, vea [Contenedor Foreach Loop](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="bdea8-104">For more information, see [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="bdea8-105">El contenedor de bucles Foreach no proporciona una funcionalidad, sino solamente la estructura en la que se genera el flujo de control repetible, se especifica un tipo de enumerador y se configura el enumerador.</span><span class="sxs-lookup"><span data-stu-id="bdea8-105">The Foreach Loop container provides no functionality; it provides only the structure in which you build the repeatable control flow, specify an enumerator type, and configure the enumerator.</span></span> <span data-ttu-id="bdea8-106">Para proporcionar la funcionalidad del contenedor, debe incluir por lo menos una tarea en el contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="bdea8-106">To provide container functionality, you must include at least one task in the Foreach Loop container.</span></span> <span data-ttu-id="bdea8-107">Para más información, consulte [Integration Services Tasks](control-flow/integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="bdea8-107">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="bdea8-108">El contenedor de bucles Foreach puede incluir un flujo de control con varias tareas y otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="bdea8-108">The Foreach Loop container can include a control flow with multiple tasks and other containers.</span></span> <span data-ttu-id="bdea8-109">Agregar tareas y contenedores a un contenedor de bucles Foreach es similar a agregarlas a un paquete, salvo que las tareas y contenedores se arrastran al contenedor de bucles Foreach en lugar de al paquete.</span><span class="sxs-lookup"><span data-stu-id="bdea8-109">Adding tasks and containers to a Foreach Loop container is similar to adding them to a package, except you drag the tasks and containers to the Foreach Loop container instead of to the package.</span></span> <span data-ttu-id="bdea8-110">Si el contenedor de bucles Foreach incluye más de una tarea o contenedor, puede conectarlos mediante restricciones de precedencia, tal y como se hace en un paquete.</span><span class="sxs-lookup"><span data-stu-id="bdea8-110">If the Foreach Loop container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="bdea8-111">Para obtener más información, vea [Restricciones de precedencia](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="bdea8-111">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
### <a name="to-implement-a-foreach-loop-container-in-a-control-flow"></a><span data-ttu-id="bdea8-112">Para implementar un contenedor de bucles Foreach en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="bdea8-112">To implement a Foreach Loop container in a control flow</span></span>  
  
1.  <span data-ttu-id="bdea8-113">Agregue el contenedor de bucles Foreach al paquete.</span><span class="sxs-lookup"><span data-stu-id="bdea8-113">Add the Foreach Loop container to the package.</span></span> <span data-ttu-id="bdea8-114">Para obtener más información, vea [Agregar o eliminar una tarea o un contenedor en un flujo de control](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="bdea8-114">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="bdea8-115">.</span><span class="sxs-lookup"><span data-stu-id="bdea8-115">.</span></span>  
  
2.  <span data-ttu-id="bdea8-116">Agregue tareas y contenedores al contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="bdea8-116">Add tasks and containers to the Foreach Loop container.</span></span> <span data-ttu-id="bdea8-117">Para obtener más información, vea [Agregar o eliminar una tarea o un contenedor en un flujo de control](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="bdea8-117">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="bdea8-118">.</span><span class="sxs-lookup"><span data-stu-id="bdea8-118">.</span></span>  
  
3.  <span data-ttu-id="bdea8-119">Conecte tareas y contenedores en el contenedor de bucles Foreach mediante restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="bdea8-119">Connect tasks and containers in the Foreach Loop container using precedence constraints.</span></span> <span data-ttu-id="bdea8-120">Para más información, vea [Conectar tareas y contenedores mediante una restricción de precedencia predeterminada](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="bdea8-120">For more information, see [Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span></span>  
  
4.  <span data-ttu-id="bdea8-121">Configure el contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="bdea8-121">Configure the Foreach Loop container.</span></span> <span data-ttu-id="bdea8-122">Para más información, vea [configurar un contenedor de bucles Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="bdea8-122">For more information, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdea8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdea8-123">See Also</span></span>  
 <span data-ttu-id="bdea8-124">[Agregar o eliminar una tarea o un contenedor en un flujo de control](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="bdea8-124">[Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="bdea8-125">[Agrupar o desagrupar componentes](group-or-ungroup-components.md) </span><span class="sxs-lookup"><span data-stu-id="bdea8-125">[Group or Ungroup Components](group-or-ungroup-components.md) </span></span>  
 <span data-ttu-id="bdea8-126">[Restricciones de precedencia](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="bdea8-126">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="bdea8-127">[Agregar iteración a un flujo de control](add-iteration-to-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="bdea8-127">[Add Iteration to a Control Flow](add-iteration-to-a-control-flow.md) </span></span>  
 [<span data-ttu-id="bdea8-128">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="bdea8-128">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
