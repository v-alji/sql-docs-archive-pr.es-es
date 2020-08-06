---
title: Tarea Transferir mensajes de error | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.f1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952acc28a79fef7e7351c97400e05bc7ba5b9243
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662185"
---
# <a name="transfer-error-messages-task"></a><span data-ttu-id="7d4a9-102">Tarea Transferir mensajes de error</span><span class="sxs-lookup"><span data-stu-id="7d4a9-102">Transfer Error Messages Task</span></span>
  <span data-ttu-id="7d4a9-103">La tarea Transferir mensajes de error transfiere uno o más mensajes de error definidos por el usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entre instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d4a9-103">The Transfer Error Messages task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined error messages between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7d4a9-104">Los mensajes definidos por el usuario son mensajes con un identificador igual o mayor que 50000.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-104">User-defined messages are messages with an identifier that is equal to or greater than 50000.</span></span> <span data-ttu-id="7d4a9-105">Los mensajes con un identificador menor que 50000 son mensajes de error del sistema, y no se pueden transferir mediante la tarea Transferir mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-105">Messages with an identifier less than 50000 are system error messages, and cannot be transferred by using the Transfer Error Messages task.</span></span>  
  
 <span data-ttu-id="7d4a9-106">La tarea Transferir mensajes de error se puede configurar para que transfiera todos los mensajes de error o solo los mensajes de error especificados.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-106">The Transfer Error Messages task can be configured to transfer all error messages, or only the specified error messages.</span></span> <span data-ttu-id="7d4a9-107">Los mensajes de error definidos por el usuario pueden estar disponibles en distintos idiomas y la tarea se puede configurar para que transfiera únicamente los mensajes que estén en los idiomas seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-107">User-defined error messages may be available in a number of different languages and the task can be configured to transfer only messages in selected languages.</span></span> <span data-ttu-id="7d4a9-108">Debe existir una versión en us_english del mensaje que utiliza página de códigos 1033 en el servidor de destino para poder transferir versiones en otros idiomas del mensaje a ese servidor.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-108">A us_english version of the message that uses code page 1033 must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
 <span data-ttu-id="7d4a9-109">La tabla sysmessages de la base de datos maestra contiene todos los mensajes de error, tanto los del sistema como los definidos por el usuario, que usa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d4a9-109">The sysmessages table in the master database contains all the error messages-both system and user-defined-that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses.</span></span>  
  
 <span data-ttu-id="7d4a9-110">Es posible que los mensajes definidos por el usuario que desea transferir ya existan en el destino.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-110">The user-defined messages to be transferred may already exist on the destination.</span></span> <span data-ttu-id="7d4a9-111">Un mensaje de error se define como un mensaje de error duplicado si el identificador y el idioma son iguales.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-111">An error message is defined as a duplicate error message if the identifier and the language are the same.</span></span> <span data-ttu-id="7d4a9-112">La tarea Transferir mensajes de error se puede configurar para haga lo siguiente con los mensajes de error existentes:</span><span class="sxs-lookup"><span data-stu-id="7d4a9-112">The Transfer Error Messages task can be configured to handle existing error messages in the following ways:</span></span>  
  
-   <span data-ttu-id="7d4a9-113">Sobrescribir los mensajes de error existentes.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-113">Overwrite existing error messages.</span></span>  
  
-   <span data-ttu-id="7d4a9-114">Hacer que la tarea genere un error cuando existan mensajes duplicados.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-114">Fail the task when duplicate messages exist.</span></span>  
  
-   <span data-ttu-id="7d4a9-115">Omitir los mensajes de error duplicados.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-115">Skip duplicate error messages.</span></span>  
  
 <span data-ttu-id="7d4a9-116">Durante la ejecución, la tarea Transferir mensajes de error se conecta con los servidores de origen y de destino utilizando uno o dos administradores de conexión SMO.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-116">At run time, the Transfer Error Messages task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="7d4a9-117">El administrador de conexiones SMO se configura independientemente de la tarea Transferir mensajes de error y después se hace referencia a él en la tarea Transferir mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-117">The SMO connection manager is configured separately from the Transfer Error Messages task, and then is referenced in the Transfer Error Messages task.</span></span> <span data-ttu-id="7d4a9-118">El administrador de conexiones SMO especifica el servidor y el modo de autenticación que se utiliza para tener acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-118">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="7d4a9-119">Para más información, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7d4a9-119">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="7d4a9-120">La tarea Transferir mensajes de error admite un origen y un destino que sea [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d4a9-120">The Transfer Error Messages task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="7d4a9-121">No hay restricciones respecto a qué versión hay que usar como origen o como destino.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-121">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="7d4a9-122">Eventos</span><span class="sxs-lookup"><span data-stu-id="7d4a9-122">Events</span></span>  
 <span data-ttu-id="7d4a9-123">La tarea genera un evento de información que indica el número de mensajes de error transferidos.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-123">The task raises an information event that reports the number of error messages that have been transferred.</span></span>  
  
 <span data-ttu-id="7d4a9-124">La tarea Transferir mensajes de error no indica el progreso incremental de la transferencia de mensajes de error; solo indica 0% y 100%.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-124">The Transfer Error Messages task does not report incremental progress of the error message transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="7d4a9-125">Valor de ejecución</span><span class="sxs-lookup"><span data-stu-id="7d4a9-125">Execution Value</span></span>  
 <span data-ttu-id="7d4a9-126">El valor de ejecución, que se define en la propiedad `ExecutionValue` de la tarea, devuelve el número de mensajes de error transferidos.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-126">The execution value, defined in the `ExecutionValue` property of the task, returns the number of error messages that have been transferred.</span></span> <span data-ttu-id="7d4a9-127">Si se asigna una variable definida por el usuario a la propiedad `ExecValueVariable` de la tarea Transferir mensajes de error, se puede hacer que la información de la transferencia de mensajes de error esté disponible para otros objetos del paquete.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-127">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Error Message task, information about the error message transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="7d4a9-128">Para más información, vea [Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) y [Usar variables en paquetes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="7d4a9-128">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="7d4a9-129">Entradas del registro</span><span class="sxs-lookup"><span data-stu-id="7d4a9-129">Log Entries</span></span>  
 <span data-ttu-id="7d4a9-130">La tarea Transferir mensajes de error incluye las siguientes entradas del registro personalizadas:</span><span class="sxs-lookup"><span data-stu-id="7d4a9-130">The Transfer Error Messages task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="7d4a9-131">TransferErrorMessagesTaskStartTransferringObjects    Esta entrada del registro indica que se ha iniciado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-131">TransferErrorMessagesTaskStartTransferringObjects    This log entry reports that the transfer has started.</span></span> <span data-ttu-id="7d4a9-132">La entrada del registro incluye la hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-132">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="7d4a9-133">TransferErrorMessagesTaskFinishedTransferringObjects   Esta entrada del registro indica que ha finalizado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-133">TransferErrorMessagesTaskFinishedTransferringObjects   This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="7d4a9-134">La entrada del registro incluye la hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-134">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="7d4a9-135">Además, una entrada del registro para el evento `OnInformation` indica el número de mensajes de error transferidos, y se escribe una entrada del registro para el evento `OnWarning event` por cada mensaje de error que se sobrescribe en el destino.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-135">In addition, a log entry for the `OnInformation` event reports the number of error messages that were transferred, and a log entry for the `OnWarning event` is written for each error message on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="7d4a9-136">Seguridad y permisos</span><span class="sxs-lookup"><span data-stu-id="7d4a9-136">Security and Permissions</span></span>  
 <span data-ttu-id="7d4a9-137">Para crear mensajes de error, el usuario que ejecuta el paquete debe ser miembro de los roles sysadmin o serveradmin en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-137">To create new error messages, the user that runs the package must be a member of the sysadmin or serveradmin server role on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a><span data-ttu-id="7d4a9-138">Configuración de la tarea Transferir mensajes de error</span><span class="sxs-lookup"><span data-stu-id="7d4a9-138">Configuration of the Transfer Error Messages Task</span></span>  
 <span data-ttu-id="7d4a9-139">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7d4a9-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7d4a9-140">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d4a9-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7d4a9-141">Editor de la tarea Transferir mensajes de error &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="7d4a9-141">Transfer Error Messages Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="7d4a9-142">Editor de la tarea Transferir mensajes de error &#40;página Mensajes&#41;</span><span class="sxs-lookup"><span data-stu-id="7d4a9-142">Transfer Error Messages Task Editor &#40;Messages Page&#41;</span></span>](../transfer-error-messages-task-editor-messages-page.md)  
  
-   [<span data-ttu-id="7d4a9-143">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="7d4a9-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="7d4a9-144">Para obtener información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d4a9-144">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="7d4a9-145">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7d4a9-145">Related Tasks</span></span>  
 <span data-ttu-id="7d4a9-146">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="7d4a9-146">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d4a9-147">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="7d4a9-147">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d4a9-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d4a9-148">See Also</span></span>  
 <span data-ttu-id="7d4a9-149">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7d4a9-149">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="7d4a9-150">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="7d4a9-150">Control Flow</span></span>](control-flow.md)  
  
  
