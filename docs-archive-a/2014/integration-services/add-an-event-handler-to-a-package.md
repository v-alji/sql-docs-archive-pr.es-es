---
title: Agregar un controlador de eventos a un paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- event handlers [Integration Services], creating
ms.assetid: 5e56885d-8658-480a-bed9-3f2f8003fd78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 007d81a395e06ac5a97210cd3e3ed6eea91aee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672254"
---
# <a name="add-an-event-handler-to-a-package"></a><span data-ttu-id="0d59c-102">agregar un controlador de eventos a un paquete</span><span class="sxs-lookup"><span data-stu-id="0d59c-102">Add an Event Handler to a Package</span></span>
  <span data-ttu-id="0d59c-103">En tiempo de ejecución, los contenedores y tareas producen eventos.</span><span class="sxs-lookup"><span data-stu-id="0d59c-103">At run time, containers and tasks raise events.</span></span> <span data-ttu-id="0d59c-104">Puede crear controladores de eventos personalizados que respondan a estos eventos ejecutando un flujo de trabajo cuando se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="0d59c-104">You can create custom event handlers that respond to these events by running a workflow when the event is raised.</span></span> <span data-ttu-id="0d59c-105">Por ejemplo, puede crear un controlador de eventos que envíe un mensaje de correo electrónico cuando una tarea genera un error.</span><span class="sxs-lookup"><span data-stu-id="0d59c-105">For example, you can create an event handler that sends an e-mail message when a task fails.</span></span>  
  
 <span data-ttu-id="0d59c-106">Un controlador de eventos es similar a un paquete.</span><span class="sxs-lookup"><span data-stu-id="0d59c-106">An event handler is similar to a package.</span></span> <span data-ttu-id="0d59c-107">Al igual que un paquete, un controlador de eventos puede proporcionar un ámbito para variables, e incluye un flujo de control y flujos de datos opcionales.</span><span class="sxs-lookup"><span data-stu-id="0d59c-107">Like a package, an event handler can provide scope for variables, and includes a control flow and optional data flows.</span></span> <span data-ttu-id="0d59c-108">Puede generar controladores de eventos para paquetes, el contenedor de bucles Foreach, el contenedor de bucles For, el contenedor de secuencias y todas las tareas.</span><span class="sxs-lookup"><span data-stu-id="0d59c-108">You can build event handlers for packages, the Foreach Loop container, the For Loop container, the Sequence container, and all tasks.</span></span>  
  
 <span data-ttu-id="0d59c-109">Puede crear controladores de eventos mediante la superficie de diseño de la pestaña **Controladores de eventos** en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d59c-109">You create event handlers by using the design surface of the **Event Handlers** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="0d59c-110">Cuando la pestaña **Controladores de eventos** se encuentra activa, los nodos **Elementos de flujo de control** y **Tareas del plan de mantenimiento** del cuadro de herramientas en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] contienen la tarea y los contenedores para generar el flujo de control en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d59c-110">When the **Event Handlers** tab is active, the **Control Flow Items** and **Maintenance Plan Tasks** nodes of the Toolbox in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer contain the task and containers for building the control flow in the event handler.</span></span> <span data-ttu-id="0d59c-111">Los nodos **Orígenes de flujo de datos**, **Transformaciones**y **Destinos de flujo de datos** contienen los orígenes de datos, transformaciones y destinos para generar los flujos de datos en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d59c-111">The **Data Flow Sources**, **Transformations**, **and Data Flow Destinations** nodes contain the data sources, transformations, and destinations for building the data flows in the event handler.</span></span> <span data-ttu-id="0d59c-112">Para obtener más información, consulte [Control Flow](control-flow/control-flow.md) y [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0d59c-112">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="0d59c-113">La pestaña **Controlador de eventos** también incluye el área de Administradores de **conexión** , donde se crean y modifican los administradores de conexión que usan los controladores de eventos para conectarse a los servidores y orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="0d59c-113">The **Event Handlers** tab also includes the **Connections** Managers area where you can create and modify the connection managers that event handlers use to connect to servers and data sources.</span></span> <span data-ttu-id="0d59c-114">Para obtener más información, vea [Crear administradores de conexiones](../../2014/integration-services/create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="0d59c-114">For more information, see [Create Connection Managers](../../2014/integration-services/create-connection-managers.md).</span></span>  
  
### <a name="to-create-an-event-handler"></a><span data-ttu-id="0d59c-115">Para crear un controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="0d59c-115">To create an event handler</span></span>  
  
1.  <span data-ttu-id="0d59c-116">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="0d59c-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0d59c-117">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="0d59c-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0d59c-118">Haga clic en la pestaña **Controladores de eventos** .</span><span class="sxs-lookup"><span data-stu-id="0d59c-118">Click the **Event Handlers** tab.</span></span>  
  
     <span data-ttu-id="0d59c-119">![Captura de pantalla de la superficie de diseño con el controlador de eventos](media/eventhandlers.gif "Captura de pantalla de la superficie de diseño con el controlador de eventos")</span><span class="sxs-lookup"><span data-stu-id="0d59c-119">![Screenshot of design surface with event handler](media/eventhandlers.gif "Screenshot of design surface with event handler")</span></span>  
  
     <span data-ttu-id="0d59c-120">La creación del flujo de control y de los flujos de datos en un controlador de eventos se asemeja a la creación del flujo de control y de los flujos de datos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="0d59c-120">Creating the control flow and data flows in an event handler is similar to creating the control flow and data flows in a package.</span></span> <span data-ttu-id="0d59c-121">Para obtener más información, consulte [Control Flow](control-flow/control-flow.md) y [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0d59c-121">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
4.  <span data-ttu-id="0d59c-122">En la lista **Ejecutable** , seleccione el ejecutable para el que desee crear un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d59c-122">In the **Executable** list, select the executable for which you want to create an event handler.</span></span>  
  
5.  <span data-ttu-id="0d59c-123">En la lista **Controlador de eventos** , seleccione el controlador que desee crear.</span><span class="sxs-lookup"><span data-stu-id="0d59c-123">In the **Event handler** list, select the event handler you want to build.</span></span>  
  
6.  <span data-ttu-id="0d59c-124">Haga clic en el vínculo en la superficie de diseño de la pestaña **Controlador de eventos** .</span><span class="sxs-lookup"><span data-stu-id="0d59c-124">Click the link on the design surface of the **Event Handler** tab.</span></span>  
  
7.  <span data-ttu-id="0d59c-125">Agregue elementos del flujo de control al controlador de eventos y conecte elementos mediante una restricción de precedencia, arrastrando la restricción de un elemento del flujo de control a otro.</span><span class="sxs-lookup"><span data-stu-id="0d59c-125">Add control flow items to the event handler, and connect items using a precedence constraint by dragging the constraint from one control flow item to another.</span></span> <span data-ttu-id="0d59c-126">Para más información, consulte [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0d59c-126">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
8.  <span data-ttu-id="0d59c-127">De forma opcional, puede agregar una tarea Flujo de datos y, en la superficie de diseño de la pestaña **Flujo de datos** , crear un flujo de datos para el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d59c-127">Optionally, add a Data Flow task, and on the design surface of the **Data Flow** tab, create a data flow for the event handler.</span></span> <span data-ttu-id="0d59c-128">Para más información, consulte [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0d59c-128">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
9. <span data-ttu-id="0d59c-129">En el menú **Archivo** , haga clic en **Guardar los elementos seleccionados** para guardar el paquete.</span><span class="sxs-lookup"><span data-stu-id="0d59c-129">On the **File** menu, click **Save Selected Items** to save the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d59c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d59c-130">See Also</span></span>  
 <span data-ttu-id="0d59c-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="0d59c-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span></span>  
 [<span data-ttu-id="0d59c-132">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0d59c-132">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
