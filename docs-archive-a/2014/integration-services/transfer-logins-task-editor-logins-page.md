---
title: Editor de la tarea transferir inicios de sesión (página inicios de sesión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.logins.f1
helpviewer_keywords:
- Transfer Logins Task Editor
ms.assetid: bf244c24-bd45-4ece-b66b-78b488f35c5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33fea6c78df75b7eebe8987f952dce33bdc4407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678240"
---
# <a name="transfer-logins-task-editor-logins-page"></a><span data-ttu-id="d388f-102">Editor de la tarea Transferir inicios de sesión (página Inicios de sesión)</span><span class="sxs-lookup"><span data-stu-id="d388f-102">Transfer Logins Task Editor (Logins Page)</span></span>
  <span data-ttu-id="d388f-103">Utilice la página **Inicios de sesión** del cuadro de diálogo **Editor de la tarea Transferir inicios de sesión** para especificar propiedades para copiar uno o varios inicios de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a otra.</span><span class="sxs-lookup"><span data-stu-id="d388f-103">Use the **Logins** page of the **Transfer Logins Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="d388f-104">Para obtener más información acerca de esta tarea, vea [Transfer Logins Task](control-flow/transfer-logins-task.md).</span><span class="sxs-lookup"><span data-stu-id="d388f-104">For more information about this task, see [Transfer Logins Task](control-flow/transfer-logins-task.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d388f-105">Cuando se ejecuta la tarea Transferir inicios de sesión, se crean inicios de sesión en el servidor de destino con contraseñas aleatorias y se deshabilitan las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d388f-105">When the Transfer Logins task is executed, logins are created on the destination server with random passwords and the passwords are disabled.</span></span> <span data-ttu-id="d388f-106">Para utilizar estos inicios de sesión, un miembro del rol fijo de servidor **sysadmin** debe cambiar las contraseñas y, a continuación, habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="d388f-106">To use these logins, a member of the **sysadmin** fixed server role must change the passwords and then enable them.</span></span> <span data-ttu-id="d388f-107">El inicio de sesión **sa** no se puede transferir.</span><span class="sxs-lookup"><span data-stu-id="d388f-107">The **sa** login cannot be transferred.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d388f-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="d388f-108">Options</span></span>  
 <span data-ttu-id="d388f-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="d388f-109">**SourceConnection**</span></span>  
 <span data-ttu-id="d388f-110">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="d388f-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="d388f-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="d388f-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="d388f-112">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="d388f-113">**LoginsToTransfer**</span><span class="sxs-lookup"><span data-stu-id="d388f-113">**LoginsToTransfer**</span></span>  
 <span data-ttu-id="d388f-114">Seleccione los inicios de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que va a copiar del servidor de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-114">Select the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins to copy from the source to the destination server.</span></span> <span data-ttu-id="d388f-115">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="d388f-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="d388f-116">Value</span><span class="sxs-lookup"><span data-stu-id="d388f-116">Value</span></span>|<span data-ttu-id="d388f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d388f-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d388f-118">**AllLogins**</span><span class="sxs-lookup"><span data-stu-id="d388f-118">**AllLogins**</span></span>|<span data-ttu-id="d388f-119">Todos los inicios de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el servidor de origen se copiarán al de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-119">All [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins on the source server will be copied to the destination server.</span></span>|  
|<span data-ttu-id="d388f-120">**SelectedLogins**</span><span class="sxs-lookup"><span data-stu-id="d388f-120">**SelectedLogins**</span></span>|<span data-ttu-id="d388f-121">Solo los inicios de sesión especificados con **LoginsList** se copiarán al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-121">Only logins specified with **LoginsList** will be copied to the destination server.</span></span>|  
|<span data-ttu-id="d388f-122">**AllLoginsFromSelectedDatabases**</span><span class="sxs-lookup"><span data-stu-id="d388f-122">**AllLoginsFromSelectedDatabases**</span></span>|<span data-ttu-id="d388f-123">Todos los inicios de sesión de las bases de datos especificadas con **DatabasesList** se copiarán al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-123">All logins from the databases specified with **DatabasesList** will be copied to the destination server.</span></span>|  
  
 <span data-ttu-id="d388f-124">**LoginsList**</span><span class="sxs-lookup"><span data-stu-id="d388f-124">**LoginsList**</span></span>  
 <span data-ttu-id="d388f-125">Seleccione los inicios de sesión en el servidor de origen que se copiarán al de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-125">Select the logins on the source server to be copied to the destination server.</span></span> <span data-ttu-id="d388f-126">Esta opción solo está disponible cuando se selecciona **SelectedLogins** para **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="d388f-126">This option is only available when **SelectedLogins** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="d388f-127">**DatabasesList**</span><span class="sxs-lookup"><span data-stu-id="d388f-127">**DatabasesList**</span></span>  
 <span data-ttu-id="d388f-128">Seleccione las bases de datos en el servidor de origen que contienen inicios de sesión que se copiarán al de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-128">Select the databases on the source server that contain logins to be copied to the destination server.</span></span> <span data-ttu-id="d388f-129">Esta opción solo está disponible cuando se selecciona **AllLoginsFromSelectedDatabases** para **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="d388f-129">This option is only available when **AllLoginsFromSelectedDatabases** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="d388f-130">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="d388f-130">**IfObjectExists**</span></span>  
 <span data-ttu-id="d388f-131">Seleccione cómo debe administrar la tarea los inicios de sesión con el mismo nombre que existan ya en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-131">Select how the task should handle logins of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="d388f-132">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="d388f-132">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="d388f-133">Value</span><span class="sxs-lookup"><span data-stu-id="d388f-133">Value</span></span>|<span data-ttu-id="d388f-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d388f-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d388f-135">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="d388f-135">**FailTask**</span></span>|<span data-ttu-id="d388f-136">La tarea genera un error si existen ya inicios de sesión con el mismo nombre en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-136">Task fails if logins of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="d388f-137">**Sobrescribir**</span><span class="sxs-lookup"><span data-stu-id="d388f-137">**Overwrite**</span></span>|<span data-ttu-id="d388f-138">La tarea sobrescribe los inicios de sesión con el mismo nombre en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-138">Task overwrites logins of the same name on the destination server.</span></span>|  
|<span data-ttu-id="d388f-139">**Skip**</span><span class="sxs-lookup"><span data-stu-id="d388f-139">**Skip**</span></span>|<span data-ttu-id="d388f-140">La tarea omite los inicios de sesión con el mismo nombre que existan en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-140">Task skips logins of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="d388f-141">**CopySids**</span><span class="sxs-lookup"><span data-stu-id="d388f-141">**CopySids**</span></span>  
 <span data-ttu-id="d388f-142">Seleccione esta opción si los identificadores de seguridad asociados a los inicios de sesión deben copiarse al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d388f-142">Select whether the security identifiers associated with the logins should be copied to the destination server.</span></span> <span data-ttu-id="d388f-143">**CopySids** debe establecerse en **True** si la tarea Transferir inicios de sesión se utiliza junto con la tarea Transferir bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d388f-143">**CopySids** must be set to **True** if the Transfer Logins task is used along with the Transfer Database task.</span></span> <span data-ttu-id="d388f-144">De lo contrario, la base de datos transferida no reconocerá los inicios de sesión copiados.</span><span class="sxs-lookup"><span data-stu-id="d388f-144">Otherwise, the copied logins will not be recognized by the transferred database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d388f-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d388f-145">See Also</span></span>  
 <span data-ttu-id="d388f-146">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d388f-146">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d388f-147">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d388f-147">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="d388f-148">[Editor de la tarea transferir inicios de sesión &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d388f-148">[Transfer Logins Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d388f-149">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="d388f-149">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="d388f-150">[Administrador de conexiones SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d388f-150">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="d388f-151">[Contraseñas seguras](../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="d388f-151">[Strong Passwords](../relational-databases/security/strong-passwords.md) </span></span>  
 [<span data-ttu-id="d388f-152">Consideraciones de seguridad para una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d388f-152">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
