---
title: Contenedor de secuencias | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sequencecontainer.f1
helpviewer_keywords:
- Sequence container
- grouping control flows
- containers [Integration Services], Sequence
- subset control flow [Integration Services]
ms.assetid: 7731f91e-b8b3-4d96-a0d9-73f568547cb3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b972f923e2134363ba1b378beebebbeb1e5d6bb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674246"
---
# <a name="sequence-container"></a><span data-ttu-id="c519d-102">contenedor de secuencias</span><span class="sxs-lookup"><span data-stu-id="c519d-102">Sequence Container</span></span>
  <span data-ttu-id="c519d-103">El contenedor de secuencias define un flujo de control que es un subconjunto del flujo de control de paquete.</span><span class="sxs-lookup"><span data-stu-id="c519d-103">The Sequence container defines a control flow that is a subset of the package control flow.</span></span> <span data-ttu-id="c519d-104">Los contenedores de secuencias agrupan el paquete en varios flujos de control independientes, cada uno con una o varias tareas y contenedores que se ejecutan en el flujo de control global del paquete.</span><span class="sxs-lookup"><span data-stu-id="c519d-104">Sequence containers group the package into multiple separate control flows, each containing one or more tasks and containers that run within the overall package control flow.</span></span>  
  
 <span data-ttu-id="c519d-105">El contenedor de secuencias puede incluir varias tareas, además de otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="c519d-105">The Sequence container can include multiple tasks in addition to other containers.</span></span> <span data-ttu-id="c519d-106">Agregar tareas y contenedores a un contenedor de secuencias es similar a agregarlas a un paquete, salvo que se arrastran las tareas y contenedores al contenedor de secuencias en lugar de al contenedor de paquetes.</span><span class="sxs-lookup"><span data-stu-id="c519d-106">Adding tasks and containers to a Sequence container is similar to adding them to a package, except you drag the tasks and containers to the Sequence container instead of to the package container.</span></span> <span data-ttu-id="c519d-107">Si el contenedor de secuencias incluye más de una tarea o contenedor, puede conectarlos mediante restricciones de precedencia, tal como se hace en un paquete.</span><span class="sxs-lookup"><span data-stu-id="c519d-107">If the Sequence container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="c519d-108">Para obtener más información, vea [Restricciones de precedencia](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c519d-108">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="c519d-109">El uso de un contenedor de secuencias ofrece muchas ventajas:</span><span class="sxs-lookup"><span data-stu-id="c519d-109">There are many benefits of using a Sequence container:</span></span>  
  
-   <span data-ttu-id="c519d-110">Permite deshabilitar grupos de tareas para centrar la depuración en un subconjunto del flujo de control del paquete.</span><span class="sxs-lookup"><span data-stu-id="c519d-110">Disabling groups of tasks to focus package debugging on one subset of the package control flow.</span></span>  
  
-   <span data-ttu-id="c519d-111">Permite administrar propiedades en varias tareas de una ubicación estableciendo propiedades en un contenedor de secuencias en lugar de hacerlo en las tareas individuales.</span><span class="sxs-lookup"><span data-stu-id="c519d-111">Managing properties on multiple tasks in one location by setting properties on a Sequence container instead of on the individual tasks.</span></span>  
  
     <span data-ttu-id="c519d-112">Por ejemplo, puede establecer la propiedad `Disable` del contenedor de secuencias en `True` para deshabilitar todas las tareas y contenedores en el contenedor de secuencias.</span><span class="sxs-lookup"><span data-stu-id="c519d-112">For example, you can set the `Disable` property of the Sequence container to `True` to disable all the tasks and containers in the Sequence container.</span></span>  
  
-   <span data-ttu-id="c519d-113">Proporciona un ámbito para variables usadas por un grupo de tareas y contenedores relacionados.</span><span class="sxs-lookup"><span data-stu-id="c519d-113">Providing scope for variables that a group of related tasks and containers use.</span></span>  
  
-   <span data-ttu-id="c519d-114">Permite agrupar muchas tareas de modo que se puedan administrar más fácilmente mediante la contracción y expansión del contenedor de secuencias.</span><span class="sxs-lookup"><span data-stu-id="c519d-114">Grouping many tasks so you can more easily managed them by collapsing and expanding the Sequence container.</span></span>  
  
     <span data-ttu-id="c519d-115">También puede crear grupos de tareas, que se expanden y contraen mediante el cuadro **Grupo** .</span><span class="sxs-lookup"><span data-stu-id="c519d-115">You can also create task groups, which expand and collapse using the **Group** box.</span></span> <span data-ttu-id="c519d-116">Pero el cuadro **Grupo** es una característica de tiempo de diseño que no tiene propiedades o comportamiento de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c519d-116">However, the **Group** box is a design-time feature that has no properties or run-time behavior.</span></span> <span data-ttu-id="c519d-117">Para obtener más información, vea [Agrupar o desagrupar componentes](../group-or-ungroup-components.md)</span><span class="sxs-lookup"><span data-stu-id="c519d-117">For more information, see [Group or Ungroup Components](../group-or-ungroup-components.md)</span></span>  
  
-   <span data-ttu-id="c519d-118">Permite establecer un atributo de transacción en el contenedor de secuencias para definir una transacción para un subconjunto del flujo de control del paquete.</span><span class="sxs-lookup"><span data-stu-id="c519d-118">Set a transaction attribute on the Sequence container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="c519d-119">De esta manera, puede administrar las transacciones en mayor detalle.</span><span class="sxs-lookup"><span data-stu-id="c519d-119">In this way, you can manage transactions at a more granular level.</span></span>  
  
     <span data-ttu-id="c519d-120">Por ejemplo, si un contenedor de secuencias incluye dos tareas relacionadas, una tarea que elimina datos de una tabla y otra tarea que inserta datos en una tabla, puede configurar una transacción para garantizar que se revierta la acción de eliminación si la acción de inserción no se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="c519d-120">For example, if a Sequence container includes two related tasks, one task that deletes data in a table and another task that inserts data into a table, you can configure a transaction to ensure that the delete action is rolled back if the insert action fails.</span></span> <span data-ttu-id="c519d-121">Para más información, vea [Transacciones de Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="c519d-121">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-sequence-container"></a><span data-ttu-id="c519d-122">Configuración del contenedor de secuencias</span><span class="sxs-lookup"><span data-stu-id="c519d-122">Configuration of the Sequence Container</span></span>  
 <span data-ttu-id="c519d-123">El contenedor de secuencias no tiene interfaz de usuario personalizada y solo se puede configurar en la ventana **Propiedades** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c519d-123">The Sequence container has no custom user interface and you can configure it only in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="c519d-124">Para obtener más información sobre cómo establecer estas propiedades mediante programación, vea la documentación de la clase **T:Microsoft.SqlServer.Dts.Runtime.Sequence** en la Guía del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="c519d-124">For information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.Sequence** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c519d-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c519d-125">Related Tasks</span></span>  
 <span data-ttu-id="c519d-126">Para obtener información sobre cómo establecer las propiedades del componente en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vea [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="c519d-126">For information about how to set properties of the component in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c519d-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c519d-127">See Also</span></span>  
 <span data-ttu-id="c519d-128">[Agregar o eliminar tareas o contenedores en un flujo de control](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="c519d-128">[Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="c519d-129">[Conectar tareas y contenedores mediante una restricción de precedencia predeterminada](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="c519d-129">[Connect Tasks and Containers by Using a Default Precedence Constraint](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="c519d-130">Contenedores de Integration Services</span><span class="sxs-lookup"><span data-stu-id="c519d-130">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
