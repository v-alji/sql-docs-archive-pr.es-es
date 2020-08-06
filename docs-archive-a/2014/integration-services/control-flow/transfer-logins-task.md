---
title: Tarea Transferir inicios de sesión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.f1
helpviewer_keywords:
- Transfer Logins task [Integration Services]
ms.assetid: 1df60fd6-c019-405d-8155-c330dbac2cc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d42d39b6cc7c2f350e3e3adc774be23934981369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662182"
---
# <a name="transfer-logins-task"></a><span data-ttu-id="6dd9e-102">Tarea Transferir inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="6dd9e-102">Transfer Logins Task</span></span>
  <span data-ttu-id="6dd9e-103">La tarea Transferir inicios de sesión transfiere uno o varios inicios de sesión entre instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dd9e-103">The Transfer Logins task transfers one or more logins between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="transfer-logins-between-instances-of-sql-server"></a><span data-ttu-id="6dd9e-104">Transferir inicios de sesión entre instancias de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6dd9e-104">Transfer Logins Between Instances of SQL Server</span></span>  
 <span data-ttu-id="6dd9e-105">La tarea Transferir inicios de sesión admite un origen y un destino que sea [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dd9e-105">The Transfer Logins task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="6dd9e-106">Eventos</span><span class="sxs-lookup"><span data-stu-id="6dd9e-106">Events</span></span>  
 <span data-ttu-id="6dd9e-107">La tarea Transferir inicios de sesión emite un evento de información que indica el número de inicios de sesión transferidos y un evento de advertencia cuando se sobrescribe un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-107">The task raises an information event that reports the number of logins transferred and a warning event when a login is overwritten.</span></span>  
  
 <span data-ttu-id="6dd9e-108">La tarea Transferir inicios de sesión no indica el progreso incremental de la transferencia; solo indica 0% y 100%.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-108">The Transfer Logins task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="6dd9e-109">Valor de ejecución</span><span class="sxs-lookup"><span data-stu-id="6dd9e-109">Execution Value</span></span>  
 <span data-ttu-id="6dd9e-110">El valor de ejecución, que se define en la propiedad `ExecutionValue` de la tarea, devuelve el número de inicios de sesión transferidos.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-110">The execution value, defined in the `ExecutionValue` property of the task, returns the number of logins transferred.</span></span> <span data-ttu-id="6dd9e-111">Si se asigna una variable definida por el usuario a la propiedad `ExecValueVariable` de la tarea Transferir inicios de sesión, se puede hacer que la información de la transferencia de inicios de sesión esté disponible para otros objetos del paquete.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-111">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Logins task, information about the login transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="6dd9e-112">Para más información, vea [Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) y [Usar variables en paquetes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6dd9e-112">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="6dd9e-113">Entradas del registro</span><span class="sxs-lookup"><span data-stu-id="6dd9e-113">Log Entries</span></span>  
 <span data-ttu-id="6dd9e-114">La tarea Transferir inicios de sesión incluye las siguientes entradas del registro personalizadas:</span><span class="sxs-lookup"><span data-stu-id="6dd9e-114">The Transfer Logins task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="6dd9e-115">TransferLoginsTaskStarTransferringObjects    Esta entrada del registro indica que se ha iniciado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-115">TransferLoginsTaskStarTransferringObjects    This log entry reports the transfer has started.</span></span> <span data-ttu-id="6dd9e-116">La entrada del registro incluye la hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-116">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="6dd9e-117">TransferLoginsTaskFinishedTransferringObjects    Esta entrada del registro indica que ha finalizado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-117">TransferLoginsTaskFinishedTransferringObjects   This log entry reports the transfer has completed.</span></span> <span data-ttu-id="6dd9e-118">La entrada del registro incluye la hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-118">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="6dd9e-119">Además, una entrada del registro para el evento `OnInformation` indica el número de inicios de sesión transferidos, y se escribe una entrada del registro para el evento `OnWarning` por cada inicio de sesión que se sobrescribe en el destino.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-119">In addition, a log entry for the `OnInformation` event reports the number of logins that were transferred, and a log entry for the `OnWarning` event is written for each login on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="6dd9e-120">Seguridad y permisos</span><span class="sxs-lookup"><span data-stu-id="6dd9e-120">Security and Permissions</span></span>  
 <span data-ttu-id="6dd9e-121">Para examinar inicios de sesión en el servidor de origen y crear inicios de sesión en el servidor de destino, el usuario debe ser miembro del rol de servidor sysadmin en ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-121">To browse logins on the source server and to create logins on the destination server, the user must be a member of the sysadmin server role on both servers.</span></span>  
  
## <a name="configuration-of-the-transfer-logins-task"></a><span data-ttu-id="6dd9e-122">Configuración de la tarea Transferir inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="6dd9e-122">Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="6dd9e-123">La tarea Transferir inicios de sesión se puede configurar para que transfiera todos los inicios de sesión, solo los inicios de sesión especificados o solo todos los inicios de sesión que tengan acceso a las bases de datos especificadas.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-123">The Transfer Logins task can be configured to transfer all logins, only specified logins, or all logins that have access to specified databases only.</span></span> <span data-ttu-id="6dd9e-124">El inicio de sesión sa no se puede transferir.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-124">The sa login cannot be transferred.</span></span> <span data-ttu-id="6dd9e-125">Se puede cambiar el nombre del inicio de sesión sa, aunque tampoco se podrá transferir el inicio de sesión sa con el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-125">The sa login may be renamed; however, the renamed sa login cannot be transferred either.</span></span>  
  
 <span data-ttu-id="6dd9e-126">También puede indicar si la tarea copia los identificadores de seguridad (SID) asociados a los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-126">You can also indicate whether the task copies the security identifiers (SIDs) associated with the logins.</span></span> <span data-ttu-id="6dd9e-127">Si se utiliza la tarea Transferir inicios de sesión en combinación con la tarea Transferir bases de datos, se deben copiar los SID al destino; de lo contrario, la base de datos de destino no reconocería los inicios de sesión transferidos.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-127">If the Transfer Logins task is used in conjunction with the Transfer Database task the SIDs must be copied to the destination; otherwise, the transferred logins are not recognized by the destination database.</span></span>  
  
 <span data-ttu-id="6dd9e-128">En el destino, los inicios de sesión transferidos se deshabilitan y se asignan contraseñas aleatorias.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-128">At the destination, the transferred logins are disabled and assigned random passwords.</span></span> <span data-ttu-id="6dd9e-129">Un miembro del rol sysadmin en el servidor de destino debe cambiar las contraseñas y habilitar los inicios de sesión para que se puedan utilizar.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-129">A member of the sysadmin role on the destination server must change the passwords and enable the logins before the logins can be used.</span></span>  
  
 <span data-ttu-id="6dd9e-130">Es posible que los inicios de sesión transferidos ya existan en el destino.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-130">The logins to be transferred may already exist on the destination.</span></span> <span data-ttu-id="6dd9e-131">La tarea Transferir inicios de sesión se puede configurar para haga lo siguiente con los inicios de sesión existentes:</span><span class="sxs-lookup"><span data-stu-id="6dd9e-131">The Transfer Logins task can be configured to handle existing logins in the following ways:</span></span>  
  
-   <span data-ttu-id="6dd9e-132">Sobrescribir los inicios de sesión existentes.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-132">Overwrite existing logins.</span></span>  
  
-   <span data-ttu-id="6dd9e-133">Hacer que la tarea genere un error cuando existan inicios de sesión duplicados.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-133">Fail the task when duplicate logins exist.</span></span>  
  
-   <span data-ttu-id="6dd9e-134">Omitir los inicios de sesión duplicados.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-134">Skip duplicate logins.</span></span>  
  
 <span data-ttu-id="6dd9e-135">Durante la ejecución, la tarea Transferir inicios de sesión se conecta a los servidores de origen y de destino utilizando dos administradores de conexión SMO.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-135">At run time, the Transfer Logins task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="6dd9e-136">Los administradores de conexión SMO se configuran independientemente de la tarea Transferir inicios de sesión y después se hace referencia a ellos en la tarea Transferir inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-136">The SMO connection managers are configured separately from the Transfer Logins task, and then referenced in the Transfer Logins task.</span></span> <span data-ttu-id="6dd9e-137">Los administradores de conexión SMO especifican el servidor y el modo de autenticación que se utilizará para tener acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-137">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="6dd9e-138">Para más información, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6dd9e-138">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="6dd9e-139">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="6dd9e-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="6dd9e-140">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dd9e-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="6dd9e-141">Editor de la tarea Transferir inicios de sesión &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="6dd9e-141">Transfer Logins Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="6dd9e-142">Editor de la tarea Transferir inicios de sesión &#40;página Inicios de sesión&#41;</span><span class="sxs-lookup"><span data-stu-id="6dd9e-142">Transfer Logins Task Editor &#40;Logins Page&#41;</span></span>](../transfer-logins-task-editor-logins-page.md)  
  
-   [<span data-ttu-id="6dd9e-143">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="6dd9e-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="6dd9e-144">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="6dd9e-144">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="6dd9e-145">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="6dd9e-145">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-transfer-logins-task"></a><span data-ttu-id="6dd9e-146">Configuración mediante programación de la tarea Transferir inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="6dd9e-146">Programmatic Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="6dd9e-147">Para obtener más información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dd9e-147">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferLoginsTask.TransferLoginsTask>  
  
  
