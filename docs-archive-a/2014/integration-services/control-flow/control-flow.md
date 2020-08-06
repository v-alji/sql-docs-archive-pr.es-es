---
title: Flujo de control | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], elements
- SSIS control flow elements
- SQL Server Integration Services control flow elements
ms.assetid: 0cc042a9-1a7f-49ed-9f47-091653d5ef6e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81ace5d285a67c6fee8a3a568ed89bc564193c42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672217"
---
# <a name="control-flow"></a><span data-ttu-id="cc022-102">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="cc022-102">Control Flow</span></span>
  <span data-ttu-id="cc022-103">Un paquete consta de un flujo de control y, opcionalmente, uno o varios flujos de datos.</span><span class="sxs-lookup"><span data-stu-id="cc022-103">A package consists of a control flow and, optionally, one or more data flows.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cc022-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] proporciona tres tipos diferentes de elementos de flujo de control: los contenedores que proporcionan las estructuras de los paquetes, las tareas que proporcionan la funcionalidad y las restricciones de precedencia que conectan los ejecutables, los contenedores y las tareas en un flujo de control ordenado.</span><span class="sxs-lookup"><span data-stu-id="cc022-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] provides three different types of control flow elements: containers that provide structures in packages, tasks that provide functionality, and precedence constraints that connect the executables, containers, and tasks into an ordered control flow.</span></span>

 <span data-ttu-id="cc022-105">Para obtener más información, consulte [Precedence Constraints](precedence-constraints.md), [Integration Services Containers](integration-services-containers.md)y [Integration Services Tasks](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="cc022-105">For more information, see [Precedence Constraints](precedence-constraints.md), [Integration Services Containers](integration-services-containers.md), and [Integration Services Tasks](integration-services-tasks.md).</span></span>

 <span data-ttu-id="cc022-106">El siguiente diagrama muestra un flujo de control que posee un contenedor y seis tareas.</span><span class="sxs-lookup"><span data-stu-id="cc022-106">The following diagram shows a control flow that has one container and six tasks.</span></span> <span data-ttu-id="cc022-107">Cinco de las tareas se definen en el nivel de paquete y una de ellas se define en el nivel de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc022-107">Five of the tasks are defined at the package level, and one task is defined at the container level.</span></span> <span data-ttu-id="cc022-108">La tarea se encuentra dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc022-108">The task is inside a container.</span></span>

 <span data-ttu-id="cc022-109">![Flujo de control con seis tareas y un contenedor](../media/ssis-controlflowelmt.gif "Flujo de control con seis tareas y un contenedor")</span><span class="sxs-lookup"><span data-stu-id="cc022-109">![Control flow with six tasks and a container](../media/ssis-controlflowelmt.gif "Control flow with six tasks and a container")</span></span>

 <span data-ttu-id="cc022-110">La arquitectura de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] admite el anidamiento de contenedores, y un flujo de control puede incluir varios niveles de contenedores anidados.</span><span class="sxs-lookup"><span data-stu-id="cc022-110">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] architecture supports the nesting of containers, and a control flow can include multiple levels of nested containers.</span></span> <span data-ttu-id="cc022-111">Por ejemplo, un paquete puede incluir un contenedor tal como un contenedor de bucles Foreach, que a su vez puede contener otro contenedor de bucles Foreach y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="cc022-111">For example, a package could contain a container such as a Foreach Loop container, which in turn could contain another Foreach Loop container and so on.</span></span>

 <span data-ttu-id="cc022-112">Los controladores de eventos también poseen flujos de control, que se generan con los mismos tipos de elementos de flujo de control.</span><span class="sxs-lookup"><span data-stu-id="cc022-112">Event handlers also have control flows, which are built using the same kinds of control flow elements.</span></span>

## <a name="control-flow-implementation"></a><span data-ttu-id="cc022-113">Implementación de flujo de control</span><span class="sxs-lookup"><span data-stu-id="cc022-113">Control Flow Implementation</span></span>
 <span data-ttu-id="cc022-114">Puede crear el flujo de control en un paquete mediante la pestaña **Flujo de control** en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc022-114">You create the control flow in a package by using the **Control Flow** tab in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="cc022-115">Cuando la pestaña **Flujo de control** está activa, el cuadro de herramientas enumera las tareas y los contenedores que se pueden agregar al flujo de control.</span><span class="sxs-lookup"><span data-stu-id="cc022-115">When the **Control Flow** tab is active, the Toolbox lists the tasks and containers that you can add to the control flow.</span></span>

 <span data-ttu-id="cc022-116">El siguiente diagrama muestra el flujo de control de un paquete simple en el diseñador de flujo de control.</span><span class="sxs-lookup"><span data-stu-id="cc022-116">The following diagram shows the control flow of a simple package in the control flow designer.</span></span> <span data-ttu-id="cc022-117">El flujo de control que se muestra en el diagrama se compone de tres tareas de nivel de paquete y un contenedor de nivel de paquete que contiene tres tareas.</span><span class="sxs-lookup"><span data-stu-id="cc022-117">The control flow shown in the diagram is made up of three package-level tasks and one package-level container that contains three tasks.</span></span> <span data-ttu-id="cc022-118">Las tareas y el contenedor se conectan mediante restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="cc022-118">The tasks and container are connected by using precedence constraints.</span></span>

 <span data-ttu-id="cc022-119">![Captura de pantalla del diseñador de flujo de control con paquete](../media/samplecontrolflow.gif "Captura de pantalla del diseñador de flujo de control con paquete")</span><span class="sxs-lookup"><span data-stu-id="cc022-119">![Screenshot of control flow designer with package](../media/samplecontrolflow.gif "Screenshot of control flow designer with package")</span></span>

 <span data-ttu-id="cc022-120">Crear un flujo de control incluye las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="cc022-120">Creating a control flow includes the following tasks:</span></span>

-   <span data-ttu-id="cc022-121">Agregar contenedores que implementan flujos de trabajo repetidos en un paquete o dividen un flujo de control en subconjuntos.</span><span class="sxs-lookup"><span data-stu-id="cc022-121">Adding containers that implement repeating workflows in a package or divide a control flow into subsets.</span></span>

-   <span data-ttu-id="cc022-122">Agregar tareas que admiten flujo de datos, preparan datos, realizan flujo de trabajo y funciones de inteligencia empresarial e implementan script.</span><span class="sxs-lookup"><span data-stu-id="cc022-122">Adding tasks that support data flow, prepare data, perform workflow and business intelligence functions, and implement script.</span></span>

     [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="cc022-123">incluye una serie de tareas que se pueden usar para crear un flujo de control que cumple con los requisitos empresariales del paquete.</span><span class="sxs-lookup"><span data-stu-id="cc022-123">includes a variety of tasks that you can use to create control flow that meets the business requirements of the package.</span></span> <span data-ttu-id="cc022-124">Si el paquete tiene que trabajar con datos, el flujo de control debe incluir por lo menos una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="cc022-124">If the package has to work with data, the control flow must include at least one Data Flow task.</span></span> <span data-ttu-id="cc022-125">Por ejemplo, es posible que un paquete deba extraer datos, agregar valores de datos y luego escribir los resultados en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cc022-125">For example, a package might have to extract data, aggregate data values, and then write the results to a data source.</span></span>  <span data-ttu-id="cc022-126">Para más información, vea [Tareas de Integration Services](integration-services-tasks.md) y [Agregar o eliminar tareas o contenedores en un flujo de control](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="cc022-126">For more information, see [Integration Services Tasks](integration-services-tasks.md) and [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>

-   <span data-ttu-id="cc022-127">Conectar contenedores y tareas en un flujo de control ordenado mediante restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="cc022-127">Connecting containers and tasks into an ordered control flow by using precedence constraints.</span></span>

     <span data-ttu-id="cc022-128">Después de agregar una tarea o contenedor a la superficie de diseño de la pestaña **Flujo de control** , el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] agrega automáticamente un conector al elemento.</span><span class="sxs-lookup"><span data-stu-id="cc022-128">After you add a task or container to the design surface of the **Control Flow** tab, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically adds a connector to the item.</span></span> <span data-ttu-id="cc022-129">Si un paquete incluye dos o más elementos, tareas o contenedores, puede combinarlos en un flujo de control arrastrando sus conectores desde un elemento a otro.</span><span class="sxs-lookup"><span data-stu-id="cc022-129">If a package includes two or more items, tasks or containers, you can join them into a control flow by dragging their connectors from one item to another.</span></span>

     <span data-ttu-id="cc022-130">El conector entre dos elementos representa una restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="cc022-130">The connector between two items represents a precedence constraint.</span></span> <span data-ttu-id="cc022-131">Una restricción de precedencia define la relación entre dos elementos conectados.</span><span class="sxs-lookup"><span data-stu-id="cc022-131">A precedence constraint defines the relationship between the two connected items.</span></span> <span data-ttu-id="cc022-132">Especifica el orden en que las tareas y contenedores se ejecutan en el tiempo de ejecución y las condiciones bajo las cuales se ejecutan las tareas y contenedores.</span><span class="sxs-lookup"><span data-stu-id="cc022-132">It specifies the order in which tasks and containers are executed at run time and the conditions under which tasks and containers run.</span></span> <span data-ttu-id="cc022-133">Por ejemplo, una restricción de precedencia puede especificar que una tarea debe ejecutarse correctamente para que la próxima tarea en el flujo de control pueda ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="cc022-133">For example, a precedence constraint can specify that a task must succeed for the next task in the control flow to run.</span></span> <span data-ttu-id="cc022-134">Para obtener más información, vea [Restricciones de precedencia](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="cc022-134">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>

-   <span data-ttu-id="cc022-135">Agregar administradores de conexión.</span><span class="sxs-lookup"><span data-stu-id="cc022-135">Adding connection managers.</span></span>

     <span data-ttu-id="cc022-136">Muchas tareas requieren una conexión a un origen de datos y tiene que agregar al paquete los administradores de conexión que la tarea requiere.</span><span class="sxs-lookup"><span data-stu-id="cc022-136">Many tasks require a connection to a data source, and you have to add the connection managers that the task requires to the package.</span></span> <span data-ttu-id="cc022-137">Según el tipo de enumerador que usa, el contenedor de bucles Foreach también puede requerir un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="cc022-137">Depending on the enumerator type it uses, the Foreach Loop container may also require a connection manager.</span></span> <span data-ttu-id="cc022-138">Puede agregar los administradores de conexión a medida que genera el flujo de control elemento por elemento o antes de empezar a generar el flujo de control.</span><span class="sxs-lookup"><span data-stu-id="cc022-138">You can add the connection managers as you construct the control flow item by item or before you start to construct the control flow.</span></span> <span data-ttu-id="cc022-139">Para más información, vea [Conexiones de Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md) y [Crear administradores de conexiones](../create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="cc022-139">For more information, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) and [Create Connection Managers](../create-connection-managers.md).</span></span>

 <span data-ttu-id="cc022-140">El Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] también incluye varias características de tiempo de diseño que se pueden usar para administrar la superficie de diseño y hacer que el flujo de control se autodocumente.</span><span class="sxs-lookup"><span data-stu-id="cc022-140">[!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer also includes many design-time features that you can use to manage the design surface and make the control flow self-documenting.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="cc022-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="cc022-141">Related Tasks</span></span>

-   [<span data-ttu-id="cc022-142">Agregar o eliminar tareas o contenedores en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="cc022-142">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)

-   [<span data-ttu-id="cc022-143">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="cc022-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)

-   [<span data-ttu-id="cc022-144">Agrupar o desagrupar componentes</span><span class="sxs-lookup"><span data-stu-id="cc022-144">Group or Ungroup Components</span></span>](../group-or-ungroup-components.md)

