---
title: Tarea Transferir trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.f1
helpviewer_keywords:
- Transfer Jobs task [Integration Services]
ms.assetid: 1bf33885-9c5b-47e4-a549-f5920b66a1de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d692934d5f7c8c1449b123ee8b9caf1d8bb34744
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662184"
---
# <a name="transfer-jobs-task"></a><span data-ttu-id="4d8d9-102">Tarea Transferir trabajos</span><span class="sxs-lookup"><span data-stu-id="4d8d9-102">Transfer Jobs Task</span></span>
  <span data-ttu-id="4d8d9-103">La tarea Transferir trabajos transfiere uno o varios trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entre instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d8d9-103">The Transfer Jobs task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4d8d9-104">La tarea Transferir trabajos se puede configurar para que transfiera todos los trabajos o solo los trabajos especificados.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-104">The Transfer Jobs task can be configured to transfer all jobs, or only specified jobs.</span></span> <span data-ttu-id="4d8d9-105">También puede indicar si los trabajos transferidos se habilitarán en el destino.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-105">You can also indicate whether the transferred jobs are enabled at the destination.</span></span>  
  
 <span data-ttu-id="4d8d9-106">Es posible que los trabajos transferidos ya existan en el destino.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-106">The jobs to be transferred may already exist on the destination.</span></span> <span data-ttu-id="4d8d9-107">La tarea Transferir trabajos se puede configurar para haga lo siguiente con los trabajos existentes:</span><span class="sxs-lookup"><span data-stu-id="4d8d9-107">The Transfer Jobs task can be configured to handle existing jobs in the following ways:</span></span>  
  
-   <span data-ttu-id="4d8d9-108">Sobrescribir los trabajos existentes.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-108">Overwrite existing jobs.</span></span>  
  
-   <span data-ttu-id="4d8d9-109">Hacer que la tarea genere un error cuando existan trabajos duplicados.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-109">Fail the task when duplicate jobs exist.</span></span>  
  
-   <span data-ttu-id="4d8d9-110">Omitir los trabajos duplicados.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-110">Skip duplicate jobs.</span></span>  
  
 <span data-ttu-id="4d8d9-111">Durante la ejecución, la tarea Transferir trabajos se conecta a los servidores de origen y de destino utilizando uno o dos administradores de conexión SMO.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-111">At run time, the Transfer Jobs task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="4d8d9-112">El administrador de conexiones SMO se configura independientemente de la tarea Transferir trabajos y después se hace referencia a él en la tarea Transferir trabajos.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-112">The SMO connection manager is configured separately from the Transfer Jobs task, and then is referenced in the Transfer Jobs task.</span></span> <span data-ttu-id="4d8d9-113">El administrador de conexiones SMO especifica el servidor y el modo de autenticación que se utiliza para tener acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-113">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="4d8d9-114">Para más información, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4d8d9-114">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-jobs-between-instances-of-sql-server"></a><span data-ttu-id="4d8d9-115">Transferir trabajos entre instancias de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d8d9-115">Transferring Jobs Between Instances of SQL Server</span></span>  
 <span data-ttu-id="4d8d9-116">La tarea Transferir trabajos admite un origen y un destino que sea [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d8d9-116">The Transfer Jobs task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="4d8d9-117">No hay restricciones respecto a qué versión hay que usar como origen o como destino.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-117">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="4d8d9-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="4d8d9-118">Events</span></span>  
 <span data-ttu-id="4d8d9-119">La tarea Transferir trabajos emite un evento de información que indica el número de trabajos transferidos y un evento de advertencia cuando se sobrescribe un trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-119">The Transfer Jobs task raises an information event that reports the number of jobs transferred and a warning event when a job is overwritten.</span></span> <span data-ttu-id="4d8d9-120">La tarea no indica el progreso incremental de la transferencia de los trabajos; solo indica 0% y 100%.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-120">The task does not report incremental progress of the job transfer; it reports only 0% and 100% completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="4d8d9-121">Valor de ejecución</span><span class="sxs-lookup"><span data-stu-id="4d8d9-121">Execution Value</span></span>  
 <span data-ttu-id="4d8d9-122">El valor de ejecución, que se define en la propiedad `ExecutionValue` de la tarea, devuelve el número de trabajos transferidos.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of jobs that are transferred.</span></span> <span data-ttu-id="4d8d9-123">Si se asigna una variable definida por el usuario a la propiedad `ExecValueVariable` de la tarea Transferir trabajos, se puede hacer que la información de la transferencia de trabajos esté disponible para otros objetos del paquete.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Jobs task, information about the job transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="4d8d9-124">Para más información, vea [Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) y [Usar variables en paquetes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4d8d9-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="4d8d9-125">Entradas del registro</span><span class="sxs-lookup"><span data-stu-id="4d8d9-125">Log Entries</span></span>  
 <span data-ttu-id="4d8d9-126">La tarea Transferir trabajos incluye las siguientes entradas del registro personalizadas:</span><span class="sxs-lookup"><span data-stu-id="4d8d9-126">The Transfer Jobs task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="4d8d9-127">TransferJobsTaskStarTransferringObjects   Esta entrada del registro indica que se ha iniciado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-127">TransferJobsTaskStarTransferringObjects   This log entry reports that the transfer has started.</span></span> <span data-ttu-id="4d8d9-128">La entrada del registro incluye la hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="4d8d9-129">TransferJobsTaskFinishedTransferringObjects   Esta entrada del registro indica que ha finalizado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-129">TransferJobsTaskFinishedTransferringObjects    This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="4d8d9-130">La entrada del registro incluye la hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="4d8d9-131">Además, una entrada del registro para el evento `OnInformation` indica el número de trabajos transferidos y se escribe una entrada del registro para el evento `OnWarning` por cada trabajo que se sobrescribe en el destino.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-131">In addition, a log entry for the `OnInformation` event reports the number of jobs that were transferred and a log entry for the `OnWarning` event is written for each job on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="4d8d9-132">Seguridad y permisos</span><span class="sxs-lookup"><span data-stu-id="4d8d9-132">Security and Permissions</span></span>  
 <span data-ttu-id="4d8d9-133">Para transferir trabajos, el usuario debe ser miembro del rol fijo de servidor sysadmin o de uno de los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos msdb tanto en la instancia de origen como en la de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d8d9-133">To transfer jobs, the user must be a member of the sysadmin fixed server role or one of the fixed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles on the msdb database on the both the source and destination instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="configuration-of-the-transfer-jobs-task"></a><span data-ttu-id="4d8d9-134">Configuración de la tarea Transferir trabajos</span><span class="sxs-lookup"><span data-stu-id="4d8d9-134">Configuration of the Transfer Jobs Task</span></span>  
 <span data-ttu-id="4d8d9-135">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4d8d9-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4d8d9-136">Para obtener información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4d8d9-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4d8d9-137">Editor de la tarea Transferir trabajos &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="4d8d9-137">Transfer Jobs Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="4d8d9-138">Editor de la tarea Transferir trabajos &#40;página Trabajos&#41;</span><span class="sxs-lookup"><span data-stu-id="4d8d9-138">Transfer Jobs Task Editor &#40;Jobs Page&#41;</span></span>](../transfer-jobs-task-editor-jobs-page.md)  
  
-   [<span data-ttu-id="4d8d9-139">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="4d8d9-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="4d8d9-140">Para obtener información acerca de cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d8d9-140">For information about programmatically setting these properties, click the of the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferJobsTask.TransferJobsTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="4d8d9-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4d8d9-141">Related Tasks</span></span>  
 <span data-ttu-id="4d8d9-142">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="4d8d9-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="4d8d9-143">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="4d8d9-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d8d9-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d8d9-144">See Also</span></span>  
 <span data-ttu-id="4d8d9-145">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="4d8d9-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="4d8d9-146">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="4d8d9-146">Control Flow</span></span>](control-flow.md)  
  
  
