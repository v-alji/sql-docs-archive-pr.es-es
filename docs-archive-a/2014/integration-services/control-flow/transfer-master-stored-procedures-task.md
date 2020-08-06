---
title: Tarea Transferir procedimientos almacenados principales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1915a3129eeb6e14c4315c37f2c6c2bf5b0d5412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750058"
---
# <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="02de5-102">Tarea Transferir procedimientos almacenados principales</span><span class="sxs-lookup"><span data-stu-id="02de5-102">Transfer Master Stored Procedures Task</span></span>
  <span data-ttu-id="02de5-103">La tarea Transferir procedimientos almacenados principales transfiere uno o más procedimientos almacenados definidos por el usuario entre las bases de datos **master** en instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02de5-103">The Transfer Master Stored Procedures task transfers one or more user-defined stored procedures between **master** databases on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="02de5-104">Para transferir un procedimiento almacenado de la base de datos **master** , el propietario del procedimiento debe ser dbo.</span><span class="sxs-lookup"><span data-stu-id="02de5-104">To transfer a stored procedure from the **master** database, the owner of the procedure must be dbo.</span></span>  
  
 <span data-ttu-id="02de5-105">La tarea Transferir procedimientos almacenados principales se puede configurar para que transfiera todos los procedimientos almacenados o solo los procedimientos especificados.</span><span class="sxs-lookup"><span data-stu-id="02de5-105">The Transfer Master Stored Procedures task can be configured to transfer all stored procedures or only specified stored procedures.</span></span> <span data-ttu-id="02de5-106">Esta tarea no copia procedimientos almacenados del sistema.</span><span class="sxs-lookup"><span data-stu-id="02de5-106">This task does not copy system stored procedures.</span></span>  
  
 <span data-ttu-id="02de5-107">Es posible que los procedimientos almacenados principales que desea transferir ya existan en el destino.</span><span class="sxs-lookup"><span data-stu-id="02de5-107">The master stored procedures to be transferred may already exist on the destination.</span></span> <span data-ttu-id="02de5-108">La tarea Transferir procedimientos almacenados principales se puede configurar para que haga lo siguiente con los procedimientos almacenados existentes:</span><span class="sxs-lookup"><span data-stu-id="02de5-108">The Transfer Master Stored Procedures task can be configured to handle existing stored procedures in the following ways:</span></span>  
  
-   <span data-ttu-id="02de5-109">Sobrescribir procedimientos almacenados existentes.</span><span class="sxs-lookup"><span data-stu-id="02de5-109">Overwrite existing stored procedures.</span></span>  
  
-   <span data-ttu-id="02de5-110">Hacer que la tarea genere un error cuando existan procedimientos almacenados duplicados.</span><span class="sxs-lookup"><span data-stu-id="02de5-110">Fail the task when duplicate stored procedures exist.</span></span>  
  
-   <span data-ttu-id="02de5-111">Omitir los procedimientos almacenados duplicados.</span><span class="sxs-lookup"><span data-stu-id="02de5-111">Skip duplicate stored procedures.</span></span>  
  
 <span data-ttu-id="02de5-112">Durante la ejecución, la tarea Transferir procedimientos almacenados principales se conecta a los servidores de origen y de destino a través de dos administradores de conexión SMO.</span><span class="sxs-lookup"><span data-stu-id="02de5-112">At run time, the Transfer Master Stored Procedures task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="02de5-113">Los administradores de conexión SMO se configuran independientemente de la tarea Transferir procedimientos almacenados principales y después se hace referencia a ellos en la tarea Transferir procedimientos almacenados principales.</span><span class="sxs-lookup"><span data-stu-id="02de5-113">The SMO connection managers are configured separately from the Transfer Master Stored Procedures task, and then referenced in the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="02de5-114">Los administradores de conexión SMO especifican el servidor y el modo de autenticación que se utilizará para tener acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="02de5-114">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="02de5-115">Para más información, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="02de5-115">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a><span data-ttu-id="02de5-116">Transferir procedimientos almacenados entre instancias de SQL Server</span><span class="sxs-lookup"><span data-stu-id="02de5-116">Transferring Stored Procedures Between Instances of SQL Server</span></span>  
 <span data-ttu-id="02de5-117">La tarea Transferir procedimientos almacenados principales admite un origen y un destino que sea [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02de5-117">The Transfer Master Stored Procedures task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="02de5-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="02de5-118">Events</span></span>  
 <span data-ttu-id="02de5-119">La tarea emite un evento de información que indica el número de procedimientos almacenados transferidos y un evento de advertencia cuando se sobrescribe un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="02de5-119">The task raises an information event that reports the number of stored procedures transferred and a warning event when a stored procedure is overwritten.</span></span>  
  
 <span data-ttu-id="02de5-120">La tarea Transferir procedimientos almacenados principales no indica el progreso incremental de la transferencia; solo indica 0% y 100%.</span><span class="sxs-lookup"><span data-stu-id="02de5-120">The Transfer Master Stored Procedures task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="02de5-121">Valor de ejecución</span><span class="sxs-lookup"><span data-stu-id="02de5-121">Execution Value</span></span>  
 <span data-ttu-id="02de5-122">El valor de ejecución, que se define en la propiedad `ExecutionValue` de la tarea, devuelve el número de procedimientos almacenados transferidos.</span><span class="sxs-lookup"><span data-stu-id="02de5-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of stored procedures transferred.</span></span> <span data-ttu-id="02de5-123">Si se asigna una variable definida por el usuario a la propiedad `ExecValueVariable` de la tarea Transferir procedimientos almacenados principales, se puede hacer que la información de la transferencia de procedimientos almacenados esté disponible para otros objetos del paquete.</span><span class="sxs-lookup"><span data-stu-id="02de5-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Master Stored Procedures task, information about the stored procedure transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="02de5-124">Para más información, vea [Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) y [Usar variables en paquetes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="02de5-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="02de5-125">Entradas del registro</span><span class="sxs-lookup"><span data-stu-id="02de5-125">Log Entries</span></span>  
 <span data-ttu-id="02de5-126">La tarea Transferir procedimientos almacenados principales incluye las siguientes entradas del registro personalizadas:</span><span class="sxs-lookup"><span data-stu-id="02de5-126">The Transfer Master Stored Procedures task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="02de5-127">TransferStoredProceduresTaskStartTransferringObjects  Esta entrada del registro indica que se ha iniciado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="02de5-127">TransferStoredProceduresTaskStartTransferringObjects  This log entry reports that the transfer has started.</span></span> <span data-ttu-id="02de5-128">La entrada del registro incluye la hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="02de5-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="02de5-129">TransferSStoredProceduresTaskFinishedTransferringObjects  Esta entrada del registro indica que ha finalizado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="02de5-129">TransferSStoredProceduresTaskFinishedTransferringObjects  This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="02de5-130">La entrada del registro incluye la hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="02de5-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="02de5-131">Además, una entrada del registro para el evento `OnInformation` indica el número de procedimientos almacenados transferidos, y se escribe una entrada del registro para el evento `OnWarning` por cada procedimiento almacenado que se sobrescribe en el destino.</span><span class="sxs-lookup"><span data-stu-id="02de5-131">In addition, a log entry for the `OnInformation` event reports the number of stored procedures that were transferred, and a log entry for the `OnWarning` event is written for each stored procedure on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="02de5-132">Seguridad y permisos</span><span class="sxs-lookup"><span data-stu-id="02de5-132">Security and Permissions</span></span>  
 <span data-ttu-id="02de5-133">El usuario debe tener permisos para ver la lista de procedimientos almacenados de la base de datos **master** en el origen y debe ser miembro del rol de servidor sysadmin o tener permisos para crear procedimientos almacenados en la base de datos **master** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="02de5-133">The user must have permission to view the list of stored procedure in the **master** database on the source, and must be a member of the sysadmin server role or have permission to created stored procedures in the **master** database on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a><span data-ttu-id="02de5-134">Configuración de la tarea Transferir procedimientos almacenados principales</span><span class="sxs-lookup"><span data-stu-id="02de5-134">Configuration of the Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="02de5-135">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="02de5-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="02de5-136">Para obtener información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="02de5-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="02de5-137">Editor de la tarea Transferir procedimientos almacenados principales &#40;Página General&#41;</span><span class="sxs-lookup"><span data-stu-id="02de5-137">Transfer Master Stored Procedures Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="02de5-138">Editor de la tarea Transferir procedimientos almacenados principales &#40;página Procedimientos almacenados&#41;</span><span class="sxs-lookup"><span data-stu-id="02de5-138">Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;</span></span>](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [<span data-ttu-id="02de5-139">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="02de5-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="02de5-140">Para obtener información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="02de5-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a><span data-ttu-id="02de5-141">Configurar la tarea Transferir procedimientos almacenados principales mediante programación</span><span class="sxs-lookup"><span data-stu-id="02de5-141">Configuring the Transfer Master Stored Procedures Task Programmatically</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="02de5-142">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="02de5-142">Related Tasks</span></span>  
 <span data-ttu-id="02de5-143">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="02de5-143">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="02de5-144">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="02de5-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="02de5-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02de5-145">See Also</span></span>  
 <span data-ttu-id="02de5-146">[Tarea Transferir objetos de SQL Server](transfer-sql-server-objects-task.md) </span><span class="sxs-lookup"><span data-stu-id="02de5-146">[Transfer SQL Server Objects Task](transfer-sql-server-objects-task.md) </span></span>  
 <span data-ttu-id="02de5-147">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="02de5-147">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="02de5-148">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="02de5-148">Control Flow</span></span>](control-flow.md)  
  
  
