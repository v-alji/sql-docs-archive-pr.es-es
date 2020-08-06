---
title: Editor de la tarea transferir procedimientos almacenados principales (página procedimientos almacenados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.storedprocedures.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f9fad408b54d4ef27d4c5d06b0d352f366ad9c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747098"
---
# <a name="transfer-master-stored-procedures-task-editor-stored-procedures-page"></a><span data-ttu-id="32c23-102">Editor de la tarea Transferir procedimientos almacenados principales (página Procedimientos almacenados)</span><span class="sxs-lookup"><span data-stu-id="32c23-102">Transfer Master Stored Procedures Task Editor (Stored Procedures Page)</span></span>
  <span data-ttu-id="32c23-103">Use la página **Procedimientos almacenados** del cuadro de diálogo **Editor de la tarea Transferir procedimientos almacenados principales** a fin de especificar las propiedades para copiar uno o más procedimientos definidos por el usuario desde la base de datos **maestra** en una instancia de la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a una base de datos **maestra** de otra instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32c23-103">Use the **Stored Procedures** page of the **Transfer Master Stored Procedures Task Editor** dialog box to specify properties for copying one or more user-defined stored procedures from the **master** database in one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to a **master** database in another instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="32c23-104">Para obtener más información acerca de esta tarea, vea [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="32c23-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32c23-105">Esta tarea transfiere solo los procedimientos almacenados definidos por el usuario que pertenecen a **dbo** desde una base de datos **master** del servidor de origen a una base de datos **master** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="32c23-106">A los usuarios se les debe conceder el permiso CREATE PROCEDURE en la base de datos **maestra** del servidor de destino o deben ser miembros del rol fijo del servidor **sysadmin** del servidor de destino para crear procedimientos almacenados en dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="32c23-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="32c23-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="32c23-107">Options</span></span>  
 <span data-ttu-id="32c23-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="32c23-108">**SourceConnection**</span></span>  
 <span data-ttu-id="32c23-109">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="32c23-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="32c23-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="32c23-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="32c23-111">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="32c23-112">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="32c23-112">**IfObjectExists**</span></span>  
 <span data-ttu-id="32c23-113">Seleccione el modo en que la tarea debe controlar los procedimientos almacenados definidos por el usuario que tengan el mismo nombre que los que ya existen en la base de datos **maestra** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-113">Select how the task should handle user-defined stored procedures of the same name that already exist in the **master** database on the destination server.</span></span>  
  
 <span data-ttu-id="32c23-114">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="32c23-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="32c23-115">Value</span><span class="sxs-lookup"><span data-stu-id="32c23-115">Value</span></span>|<span data-ttu-id="32c23-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c23-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32c23-117">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="32c23-117">**FailTask**</span></span>|<span data-ttu-id="32c23-118">La tarea genera un error si ya existen procedimientos almacenados con el mismo nombre en la base de datos **maestra** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-118">Task fails if stored procedures of the same name already exist in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="32c23-119">**Sobrescribir**</span><span class="sxs-lookup"><span data-stu-id="32c23-119">**Overwrite**</span></span>|<span data-ttu-id="32c23-120">La tarea sobrescribe los procedimientos almacenados con el mismo nombre en la base de datos **maestra** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-120">Task overwrites stored procedures of the same name in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="32c23-121">**Skip**</span><span class="sxs-lookup"><span data-stu-id="32c23-121">**Skip**</span></span>|<span data-ttu-id="32c23-122">La tarea omite los procedimientos almacenados con el mismo nombre que ya existen en la base de datos **maestra** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-122">Task skips stored procedures of the same name that exist in the **master** database on the destination server.</span></span>|  
  
 <span data-ttu-id="32c23-123">**TransferAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="32c23-123">**TransferAllStoredProcedures**</span></span>  
 <span data-ttu-id="32c23-124">Seleccione esta opción si todos los procedimientos almacenados definidos por el usuario de la base de datos **maestra** del servidor de origen deben copiarse al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-124">Select whether all user-defined stored procedures in the **master** database on the source server should be copied to the destination server.</span></span>  
  
|<span data-ttu-id="32c23-125">Value</span><span class="sxs-lookup"><span data-stu-id="32c23-125">Value</span></span>|<span data-ttu-id="32c23-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c23-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32c23-127">**True**</span><span class="sxs-lookup"><span data-stu-id="32c23-127">**True**</span></span>|<span data-ttu-id="32c23-128">Copie todos los procedimientos almacenados definidos por el usuario de la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="32c23-128">Copy all user-defined stored procedures in the **master** database.</span></span>|  
|<span data-ttu-id="32c23-129">**False**</span><span class="sxs-lookup"><span data-stu-id="32c23-129">**False**</span></span>|<span data-ttu-id="32c23-130">Copie solamente los procedimientos almacenados especificados.</span><span class="sxs-lookup"><span data-stu-id="32c23-130">Copy only the specified stored procedures.</span></span>|  
  
 <span data-ttu-id="32c23-131">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="32c23-131">**StoredProceduresList**</span></span>  
 <span data-ttu-id="32c23-132">Seleccione los procedimientos almacenados definidos por el usuario de la base de datos **maestra** del servidor de origen que deben copiarse a la base de datos **maestra** de destino.</span><span class="sxs-lookup"><span data-stu-id="32c23-132">Select which user-defined stored procedures in the **master** database on the source server should be copied to the destination **master** database.</span></span> <span data-ttu-id="32c23-133">Esta opción solo está disponible cuando **TransferAllStoredProcedures** se establece en **False**.</span><span class="sxs-lookup"><span data-stu-id="32c23-133">This option is only available when **TransferAllStoredProcedures** is set to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c23-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32c23-134">See Also</span></span>  
 <span data-ttu-id="32c23-135">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="32c23-135">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="32c23-136">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="32c23-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="32c23-137">[Editor de la tarea transferir procedimientos almacenados principales &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="32c23-137">[Transfer Master Stored Procedures Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="32c23-138">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="32c23-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="32c23-139">Administrador de conexiones SMO</span><span class="sxs-lookup"><span data-stu-id="32c23-139">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
