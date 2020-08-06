---
title: Agregar o eliminar tareas o contenedores en un flujo de control | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], adding
- adding tasks
- adding containers
- tasks [Integration Services], adding
ms.assetid: 653084c6-87a3-45d5-b458-914ecf24d56a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8338a4143358d732a974287e587f482dc5c36a22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673853"
---
# <a name="add-or-delete-a-task-or-a-container-in-a-control-flow"></a><span data-ttu-id="fab0a-102">Agregar o eliminar tareas o contenedores en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="fab0a-102">Add or Delete a Task or a Container in a Control Flow</span></span>
  <span data-ttu-id="fab0a-103">Cuando se trabaja en el diseñador de flujo de control, el cuadro de herramientas del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] enumera las tareas que proporciona [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para generar flujo de control en un paquete.</span><span class="sxs-lookup"><span data-stu-id="fab0a-103">When you are working in the control flow designer, the Toolbox in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lists the tasks that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides for building control flow in a package.</span></span> <span data-ttu-id="fab0a-104">Para obtener más información sobre el cuadro de herramientas, vea [SSIS Toolbox](../ssis-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="fab0a-104">For more information about the Toolbox, see [SSIS Toolbox](../ssis-toolbox.md).</span></span>  
  
 <span data-ttu-id="fab0a-105">Un paquete puede incluir varias instancias de la misma tarea.</span><span class="sxs-lookup"><span data-stu-id="fab0a-105">A package can include multiple instances of the same task.</span></span> <span data-ttu-id="fab0a-106">Cada instancia de una tarea se identifica de forma exclusiva en el paquete y cada instancia se puede configurar de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="fab0a-106">Each instance of a task is uniquely identified in the package, and you can configure each instance differently.</span></span>  
  
 <span data-ttu-id="fab0a-107">Si se elimina una tarea, las restricciones de precedencia que conectan la tarea a otras tareas y contenedores en el flujo de control también se eliminan.</span><span class="sxs-lookup"><span data-stu-id="fab0a-107">If you delete a task, the precedence constraints that connect the task to other tasks and containers in the control flow are also deleted.</span></span>  
  
 <span data-ttu-id="fab0a-108">Los procedimientos siguientes describen cómo agregar o eliminar una tarea o un contenedor en el flujo de control de un paquete.</span><span class="sxs-lookup"><span data-stu-id="fab0a-108">The following procedures describe how to add or delete a task or container in the control flow of a package.</span></span>  
  
### <a name="to-add-a-task-or-a-container-to-a-control-flow"></a><span data-ttu-id="fab0a-109">Para agregar una tarea o contenedor a un flujo de control</span><span class="sxs-lookup"><span data-stu-id="fab0a-109">To add a task or a container to a control flow</span></span>  
  
1.  <span data-ttu-id="fab0a-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="fab0a-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fab0a-111">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="fab0a-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fab0a-112">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="fab0a-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="fab0a-113">Para abrir el **cuadro de herramientas**, haga clic en **Cuadro de herramientas** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="fab0a-113">To open the **Toolbox**, click **Toolbox** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="fab0a-114">Expanda **Elementos de flujo de control** y **Tareas de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="fab0a-114">Expand **Control Flow Items** and **Maintenance Tasks**.</span></span>  
  
6.  <span data-ttu-id="fab0a-115">Arrastre tareas y contenedores desde el **Cuadro de herramientas** a la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="fab0a-115">Drag tasks and containers from the **Toolbox** to the design surface of the **Control Flow** tab.</span></span>  
  
7.  <span data-ttu-id="fab0a-116">Conecte una tarea o contenedor dentro del flujo de control de paquete arrastrando su conector a otro componente en el flujo de control.</span><span class="sxs-lookup"><span data-stu-id="fab0a-116">Connect a task or container within the package control flow by dragging its connector to another component in the control flow.</span></span>  
  
8.  <span data-ttu-id="fab0a-117">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="fab0a-117">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-task-or-a-container-from-a-control-flow"></a><span data-ttu-id="fab0a-118">Para eliminar una tarea o un contenedor de un flujo de control</span><span class="sxs-lookup"><span data-stu-id="fab0a-118">To delete a task or a container from a control flow</span></span>  
  
1.  <span data-ttu-id="fab0a-119">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="fab0a-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fab0a-120">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="fab0a-120">In Solution Explorer, double-click the package to open it.</span></span> <span data-ttu-id="fab0a-121">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fab0a-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="fab0a-122">Haga clic en la pestaña **Flujo de control** , haga clic con el botón derecho en la tarea o contenedor que quiera eliminar y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fab0a-122">Click the **Control Flow** tab, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
    -   <span data-ttu-id="fab0a-123">Abra el **Explorador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="fab0a-123">Open **Package Explorer**.</span></span> <span data-ttu-id="fab0a-124">En la carpeta **Ejecutables** , haga clic con el botón derecho en la tarea o contenedor que quiera eliminar y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fab0a-124">From the **Executables** folder, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="fab0a-125">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="fab0a-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab0a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fab0a-126">See Also</span></span>  
 <span data-ttu-id="fab0a-127">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="fab0a-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="fab0a-128">[Contenedores de Integration Services](integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="fab0a-128">[Integration Services Containers](integration-services-containers.md) </span></span>  
 [<span data-ttu-id="fab0a-129">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="fab0a-129">Control Flow</span></span>](control-flow.md)  
  
  
