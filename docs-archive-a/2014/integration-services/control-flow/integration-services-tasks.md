---
title: Tareas de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Integration Services], tasks
- files [Integration Services], task options
- workflow tasks [Integration Services]
- Integration Services, tasks
- adding package tasks
- tasks [Integration Services], listed
- SSIS tasks
- SSIS, tasks
- control flow [Integration Services], tasks
- tasks [Integration Services]
- grouping tasks
- tasks [Integration Services], about tasks
- SQL Server Integration Services tasks
- data preparation tasks [Integration Services]
- directory operations [Integration Services]
ms.assetid: 75c8901d-6966-4af3-abe5-10af6dd9313b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5fa58dec1e05a0333c295efc7f00a1d6df935792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671619"
---
# <a name="integration-services-tasks"></a><span data-ttu-id="fb6e8-102">Tareas de Integration Services</span><span class="sxs-lookup"><span data-stu-id="fb6e8-102">Integration Services Tasks</span></span>
  <span data-ttu-id="fb6e8-103">Las tareas son elementos de flujo de control que definen las unidades de trabajo que se realizan en un flujo de control de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-103">Tasks are control flow elements that define units of work that are performed in a package control flow.</span></span> <span data-ttu-id="fb6e8-104">Un paquete de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] consta de una o más tareas.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-104">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package is made up of one or more tasks.</span></span> <span data-ttu-id="fb6e8-105">Si el paquete contiene más de una tarea, las tareas se conectan y ordenan en el flujo de control mediante restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-105">If the package contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span>  
  
 <span data-ttu-id="fb6e8-106">También puede escribir tareas personalizadas mediante un lenguaje de programación compatible con COM, como Visual Basic, o un lenguaje de programación .NET, como C#.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-106">You can also write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span>  
  
 <span data-ttu-id="fb6e8-107">El Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)], la herramienta gráfica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para trabajar con paquetes, proporciona la superficie de diseño para crear flujos de control de paquetes y proporciona editores personalizados para configurar las tareas.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the graphical tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] for working with packages, provides the design surface for creating package control flow, and provides custom editors for configuring tasks.</span></span> <span data-ttu-id="fb6e8-108">También se puede programar el modelo de objetos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para crear paquetes mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-108">You can also program the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model to create packages programmatically.</span></span>  
  
## <a name="types-of-tasks"></a><span data-ttu-id="fb6e8-109">Tipos de tareas</span><span class="sxs-lookup"><span data-stu-id="fb6e8-109">Types of Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="fb6e8-110">incluye los siguientes tipos de tareas.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-110">includes the following types of tasks.</span></span>  
  
 <span data-ttu-id="fb6e8-111">tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="fb6e8-111">Data Flow Task</span></span>  
 <span data-ttu-id="fb6e8-112">Tarea que ejecuta flujos de datos para extraer datos, aplicar transformaciones de nivel de columna y cargar datos.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-112">The task that runs data flows to extract data, apply column level transformations, and load data.</span></span>  
  
 <span data-ttu-id="fb6e8-113">Tareas de preparación de datos</span><span class="sxs-lookup"><span data-stu-id="fb6e8-113">Data Preparation Tasks</span></span>  
 <span data-ttu-id="fb6e8-114">Estas tareas llevan a cabo los procesos siguientes: copiar archivos y directorios; descargar archivos y datos; ejecutar métodos web; aplicar operaciones a documentos XML; y generar perfiles de los datos para la limpieza.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-114">These tasks do the following processes: copy files and directories; download files and data; run Web methods; apply operations to XML documents; and profile data for cleansing.</span></span>  
  
 <span data-ttu-id="fb6e8-115">Tareas de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="fb6e8-115">Workflow Tasks</span></span>  
 <span data-ttu-id="fb6e8-116">Tareas que se comunican con otros procesos para ejecutar paquetes, ejecutar programas o archivos por lotes, enviar y recibir mensajes entre paquetes, enviar mensajes de correo electrónico, leer datos de Instrumental de administración de Windows (WMI) y detectar eventos de WMI.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-116">The tasks that communicate with other processes to run packages, run programs or batch files, send and receive messages between packages, send e-mail messages, read Windows Management Instrumentation (WMI) data, and watch for WMI events.</span></span>  
  
 <span data-ttu-id="fb6e8-117">Tareas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb6e8-117">SQL Server Tasks</span></span>  
 <span data-ttu-id="fb6e8-118">Tareas de acceso, copia, inserción, eliminación y modificación de objetos y datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb6e8-118">The tasks that access, copy, insert, delete, and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects and data.</span></span>  
  
 <span data-ttu-id="fb6e8-119">Tareas de scripting</span><span class="sxs-lookup"><span data-stu-id="fb6e8-119">Scripting Tasks</span></span>  
 <span data-ttu-id="fb6e8-120">Tareas que amplían la funcionalidad de los paquetes mediante scripts.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-120">The tasks that extend package functionality by using scripts.</span></span>  
  
 <span data-ttu-id="fb6e8-121">Tareas de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fb6e8-121">Analysis Services Tasks</span></span>  
 <span data-ttu-id="fb6e8-122">Tareas de creación, modificación, eliminación y procesamiento de objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb6e8-122">The tasks that create, modify, delete, and process [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="fb6e8-123">Tareas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="fb6e8-123">Maintenance Tasks</span></span>  
 <span data-ttu-id="fb6e8-124">Tareas que realizan funciones administrativas como crear copias de seguridad y reducir bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , volver a generar y reorganizar índices, y ejecutar trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb6e8-124">The tasks that perform administrative functions such as backing up and shrinking [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, rebuilding and reorganizing indexes, and running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="fb6e8-125">Tareas personalizadas</span><span class="sxs-lookup"><span data-stu-id="fb6e8-125">Custom Tasks</span></span>  
 <span data-ttu-id="fb6e8-126">Además, también puede escribir tareas personalizadas mediante un lenguaje de programación compatible con COM, como Visual Basic, o un lenguaje de programación .NET, como C#.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-126">Additionally, you can write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span> <span data-ttu-id="fb6e8-127">Si quiere tener acceso a una tarea personalizada en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , puede crear y registrar una interfaz de usuario para la tarea.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-127">If you want to access your custom task in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can create and register a user interface for the task.</span></span> <span data-ttu-id="fb6e8-128">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="fb6e8-128">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="configuration-of-tasks"></a><span data-ttu-id="fb6e8-129">Configuración de tareas</span><span class="sxs-lookup"><span data-stu-id="fb6e8-129">Configuration of Tasks</span></span>  
 <span data-ttu-id="fb6e8-130">Un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] puede contener una tarea individual, como una tarea Ejecutar SQL que elimina registros de una tabla de base de datos cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-130">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can contain a single task, such as an Execute SQL task that deletes records in a database table when the package runs.</span></span> <span data-ttu-id="fb6e8-131">No obstante, los paquetes suelen contener varias tareas y cada tarea se establece para ejecutarse en el contexto del flujo de control de paquete.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-131">However, packages typically contain several tasks, and each task is set to run within the context of the package control flow.</span></span> <span data-ttu-id="fb6e8-132">Los controladores de eventos, que son flujos de trabajo que se ejecutan en respuesta a eventos de tiempo de ejecución, también puede tener tareas.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-132">Event handlers, which are workflows that run in response to run-time events, can also have tasks.</span></span>  
  
 <span data-ttu-id="fb6e8-133">Para obtener más información sobre cómo agregar una tarea a un paquete mediante el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Agregar o eliminar tareas o contenedores en un flujo de control](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="fb6e8-133">For more information about adding a task to a package using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>  
  
 <span data-ttu-id="fb6e8-134">Para obtener más información sobre cómo agregar una tarea a un paquete mediante programación, vea [Agregar tareas mediante programación](../building-packages-programmatically/adding-tasks-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="fb6e8-134">For more information about adding a task to a package programmatically, see [Adding Tasks Programmatically](../building-packages-programmatically/adding-tasks-programmatically.md).</span></span>  
  
 <span data-ttu-id="fb6e8-135">Cada tarea puede configurarse individualmente a través de los cuadros de diálogo personalizados para cada tarea proporcionados por el diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a través de la ventana Propiedades incluida en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb6e8-135">Each task can be configured individually using the custom dialog boxes for each task that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides, or the Properties window included in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="fb6e8-136">En un paquete, se pueden incluir varias tareas del mismo tipo (por ejemplo, seis tareas Ejecutar SQL) y cada tarea se puede configurar de una manera diferente.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-136">A package can include multiple tasks of the same type-for example, six Execute SQL tasks-and each task can be configured differently.</span></span> <span data-ttu-id="fb6e8-137">Para obtener más información, vea [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="fb6e8-137">For more information, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="tasks-connections-and-groups"></a><span data-ttu-id="fb6e8-138">Grupos y conexiones de tareas</span><span class="sxs-lookup"><span data-stu-id="fb6e8-138">Tasks Connections and Groups</span></span>  
 <span data-ttu-id="fb6e8-139">Si una tarea contiene más de una tarea, dichas tareas se conectan y ordenan en el flujo de control mediante restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-139">If the task contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span> <span data-ttu-id="fb6e8-140">Para obtener más información, vea [Restricciones de precedencia](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="fb6e8-140">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="fb6e8-141">Las tareas pueden agruparse y ejecutarse como una sola unidad de trabajo o repetirse en un bucle.</span><span class="sxs-lookup"><span data-stu-id="fb6e8-141">Tasks can be grouped together and performed as a single unit of work, or repeated in a loop.</span></span> <span data-ttu-id="fb6e8-142">Para obtener más información, consulte [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md)y [Sequence Container](sequence-container.md).</span><span class="sxs-lookup"><span data-stu-id="fb6e8-142">For more information, see [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md), and [Sequence Container](sequence-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fb6e8-143">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="fb6e8-143">Related Tasks</span></span>  
 [<span data-ttu-id="fb6e8-144">Agregar o eliminar tareas o contenedores en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="fb6e8-144">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
  
